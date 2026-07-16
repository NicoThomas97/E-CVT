# e-CVT MGU 体感可实现性仿真模型规范

最后更新：2026-07-16

## 1. 目的和边界

本文件定义后续仿真的建模边界。目标不是生成展示页里的平滑趋势曲线，而是回答：

> 在真实 e-CVT MGU 的机械、电机、电控、热和传感器约束下，是否存在一组参数窗口，可以实现“巡航看踏频、冲刺看意图、爬坡看脚感力矩、曲柄低谷附近变比”的骑手体感逻辑。

仿真不能证明量产可靠性。它不能替代寿命、密封、防水、跌落冲击、润滑退化、噪声老化、法规认证和用户滥用测试。它能做的是缩小台架和样机验证范围，明确哪些参数必须实测，哪些架构在热、效率、变比速度、相位控制或轮端扭矩连续性上已经构成 No-Go。

## 2. 仿真阶段

| 阶段 | 名称 | 目标 | 输出 |
| --- | --- | --- | --- |
| P0 | 最小可用模型 | 建立车辆纵向动力学 + 骑手 + 电机 + 理想/限速 e-CVT | 判断四类体感逻辑是否存在理论可行窗口 |
| P1 | 机构差异模型 | 区分 two-motor planetary、traction CVP、belt CVT、stepped gearbox、series/virtual-chain | 判断不同机构约束是否破坏体感 |
| P2 | HIL / 台架模型 | 用台架效率、热、执行器、传感器、控制器实测参数替换假设 | 验证轮端扭矩连续性、相位变比、热降额 |
| P3 | 实车闭环模型 | 加入真实骑手、坡度、路面、环境温度、故障注入和主观评分 | 验证仿真指标与主观体感是否一致 |

P0 可以用来否定明显不可行方案；P1 用来比较机构风险；P2/P3 才能支撑“工程上可实现”的判断。

## 3. 符号约定

- `v`：车速。
- `omega_w`：轮速。
- `omega_c`：曲柄角速度 / 踏频。
- `phi_c`：曲柄相位。
- `T_ped`：骑手踩踏力矩。
- `T_m`：电机输出力矩。
- `T_w`：轮端驱动力矩。
- `r = omega_c / omega_w`：有效传动比，本文把它理解为“骑手侧角速度到轮侧角速度的等效比”。
- `r_cmd`：控制器请求传动比。
- `theta`：坡度角。
- `eta_drv`：传动效率。

不同机构的真实传动比定义可能不同。模型中应保留映射层，避免把展示用“齿比”直接当成机械内部齿数比。

## 4. 模块定义

| 模块 | 状态变量 | 输入 | 输出 | 关键约束 |
| --- | --- | --- | --- | --- |
| 车辆纵向动力学 | `v, x, omega_w` | `T_w, F_brake, theta, wind` | 车速、轮速、坡度负载 | 路载、坡度、滚阻、风阻、惯量 |
| 骑手模型 | `phi_c, omega_c, T_ped, fatigue_state` | 骑手意图、目标踏频、坡度感知 | 踩踏力矩、踏频、功率 | 踩踏力矩波形必须能表达 12 点低谷 |
| e-CVT / 传动模型 | `r, dr/dt, mode, actuator_state` | `r_cmd, T_load, omega_c, omega_w` | 实际传动比、效率、延迟 | `r_min <= r <= r_max`，`abs(dr/dt) <= rdot_max` |
| 电机 / 逆变器 | `omega_m, T_m, I, V, Temp_m` | 助力请求、电池状态、温度 | 电机扭矩、电功率、损耗 | 转矩-转速-电流-温度限值，扭矩爬升限制 |
| 热模型 | `Temp_motor, Temp_inv, Temp_cvt` | 铜损、铁损、机械摩擦损、环境温度 | 降额系数 | RC 热网络，超温降额 |
| 控制器 | `intent_state, climb_state, r_cmd, T_m_cmd` | 踏频、脚踏力矩、相位、坡度、车速 | 变比命令、电机命令 | 模式切换、权重切换、滞回、防抖 |
| 传感器 / 延迟 | `filter_state, fault_flags` | 真实物理量、噪声、偏置、丢包 | 估计踏频、力矩、相位、坡度 | 采样、滤波、延迟、故障注入 |
| 自由轮 / 棘轮 | `engaged/freewheel` | 轮速、曲柄速度、扭矩方向 | 接合状态、回接冲击 | 不允许回接产生明显轮端扭矩阶跃 |
| 能耗统计 | `E_batt, SOC` | 电功率、效率、再加速需求 | 能耗、热损失分布 | 与基准传动方案比较 |

## 5. 基本方程

车辆纵向动力学：

```text
m_eff * dv/dt =
  T_w / R_w
  - m * g * sin(theta)
  - Crr * m * g * cos(theta)
  - 0.5 * rho * CdA * v_rel^2
  - F_brake
```

骑手功率：

```text
P_rider = T_ped * omega_c
d(phi_c)/dt = omega_c
```

传动和轮端力矩的抽象形式：

```text
r_min <= r <= r_max
abs(dr/dt) <= rdot_max
abs(d2r/dt2) <= rddot_max
T_w = eta_drv(r, T, omega, Temp_cvt) * f_ratio(r, T_ped, T_m, mode)
```

具体 `f_ratio` 不应提前固定。不同机构需要不同映射：

- traction CVP：`eta_drv` 必须考虑变比、输入扭矩、接触损失和温度。
- two-motor planetary：需要行星排运动学和电功率循环项。
- stepped gearbox：`r` 是离散状态，换挡窗口和扭矩交接比连续 `dr/dt` 更重要。
- series/virtual-chain：机械 `r` 退化为软件虚拟负载和轮端扭矩映射。

电机功率和损耗：

```text
P_mech = T_m * omega_m
T_m <= T_max(omega_m, Temp_motor, V_batt)
dT_m/dt <= torque_slew_limit
P_batt = P_mech / eta_motor_inv(T_m, omega_m, Temp_motor)
```

热模型：

```text
C_i * dTemp_i/dt =
  Q_loss_i
  - sum((Temp_i - Temp_j) / R_ij)
  - (Temp_i - Temp_amb) / R_iamb
```

相位窗口：

```text
phi_valley = argmin(T_ped(phi_c)) in current crank cycle
e_phi = wrap(phi_shift_actual - phi_valley)
```

若 e-CVT 执行动作会引入可感知反扭矩、链张力扰动或轮端扭矩波动，则较大的变比动作应优先压到低谷窗口内；若机构真实扰动极小，则相位窗口可以从硬约束降级为舒适性优化项。

## 6. 控制目标

### 6.1 巡航

巡航时以踏频为主：

```text
min J_cruise =
  w_c * (omega_c - omega_c_target)^2
  + w_r * (dr/dt)^2
  + w_Tw * (dT_w/dt)^2
  + w_E * P_batt
```

要求：

- 稳态踏频误差可接受。
- 不因过度追踪导致齿比来回抖动。
- 变比动作不造成明显拖拽、空踩或噪声。

### 6.2 冲刺

冲刺时先看意图，电机先响应，齿比后跟随：

```text
intent_sprint =
  dT_ped/dt high
  or domega_c/dt high
  or rider torque above threshold
  with speed / grade / assist context
```

控制顺序：

1. 电机扭矩快速补足轮端需求。
2. 允许真实踏频短时上扬。
3. 传动比平滑升高，避免突然压低踏频。
4. 骑手力矩回落后退出冲刺，目标踏频回到巡航设定，但保持较高齿比进入高速巡航。

关键不是“变比越快越好”，而是 `ratio lag` 期间电机能否补扭，且热、电流和轮端扭矩连续性不超限。

### 6.3 爬坡

爬坡时以脚感力矩舒适区为主，踏频为次级约束：

```text
min J_climb =
  w_Tped * distance_to_comfort_band(T_ped)^2
  + w_Tw * (dT_w/dt)^2
  + w_heat * thermal_penalty
  + w_c_secondary * (omega_c - omega_c_ref)^2
```

要求：

- 允许目标踏频动态变化。
- 通过齿比和电机扭矩共同把 `T_ped` 拉回舒适中间区。
- 长坡热降额后仍要评估是否能维持脚感，不能只看前几秒。

## 7. 方程和控制目标来源

本节用于避免把“标准物理关系”“公开证据支持的结构能力”“控制策略假设”和“必须实测的参数”混在一起。后续仿真时，每个模块都应标注来源等级；没有来源的参数只能做敏感性扫描，不能写成工程结论。

| 方程 / 表达 | 用途 | 来源类型 | 依据边界 | 后续使用方式 |
| --- | --- | --- | --- | --- |
| `m_eff * dv/dt = T_w / R_w - ...` | 计算车速、坡度负载和轮端扭矩需求 | 标准理论 | 来自车辆纵向动力学。坡度、滚阻、风阻、惯量项是通用建模方法，不是本项目假设 | P0 可直接使用；`m_eff`、`Crr`、`CdA`、`R_w` 需要实测或敏感性扫描 |
| `P_rider = T_ped * omega_c` | 把踩踏力矩和踏频换算为骑手功率 | 标准理论 | 来自旋转机械功率关系 `P = T * omega` | 可直接使用；`T_ped` 波形和骑手舒适区必须来自功率计/人体测试 |
| `d(phi_c)/dt = omega_c` | 建立曲柄相位和踏频关系 | 标准运动学 | 角速度与角位移的基本关系 | 可直接使用；相位传感器精度、采样延迟和滤波延迟必须实测 |
| `r_min <= r <= r_max` | 限制 e-CVT 可用变比范围 | 工程约束 | Owuru/enviolo/Gobao/Avinox 等公开资料可证明连续变比或 e-CVT 方向存在，但不能给出本项目最终内部变比 | P0 可用公开范围做初始扫描；P1/P2 必须换成本机构实测范围 |
| `abs(dr/dt) <= rdot_max`、`abs(d2r/dt2) <= rddot_max` | 限制变比速度、变比加速度和执行器能力 | 工程约束 + 弱假设 | 公开资料通常不会给出高负载下连续变比速度；展会/媒体值不能直接等同本机构能力 | 只能做敏感性扫描；P2 必须用台架测得的 `rdot_max`、延迟和高负载降额替换 |
| `T_w = eta_drv(...) * f_ratio(...)` | 把骑手、电机和传动系统映射到轮端扭矩 | 架构抽象 | 这是刻意保留的抽象层，不是某一种 e-CVT 的真实方程。不同机构的 `f_ratio` 不同 | P1 阶段按 two-motor planetary、traction CVP、belt CVT、stepped gearbox、virtual-chain 分别展开 |
| `P_mech = T_m * omega_m` | 计算电机机械功率 | 标准理论 | 来自旋转机械功率关系 | 可直接使用；电机转矩-转速边界必须来自电机 map 或测功机 |
| `T_m <= T_max(...)`、`dT_m/dt <= torque_slew_limit` | 限制电机可输出扭矩和扭矩响应速度 | 工程约束 | 电机、电池、逆变器、温度共同决定；公开峰值扭矩不能代表持续能力 | P0 可做参数扫描；P2 必须用测功机和控制器测试数据 |
| `P_batt = P_mech / eta_motor_inv(...)` | 估算电池侧功率和电机/逆变器损耗 | 标准能量关系 + 实测 map | 公式形式成立，但效率 map 不能凭空假设 | 需要电机/逆变器效率 map；没有 map 时只能做宽范围敏感性扫描 |
| `C_i * dTemp_i/dt = ...` | 估算电机、逆变器、传动机构温升和降额 | 标准热模型 | 来自集中参数 RC 热网络，是早期系统热仿真的常用形式 | 结构可用；`C_i`、`R_ij`、`R_iamb`、`Q_loss_i` 必须由热测试识别 |
| `phi_valley = argmin(T_ped(phi_c))` | 寻找曲柄周期内踩踏力矩低谷 | 标准数学表达 + 控制假设 | `argmin` 是数学定义；“低谷附近变比更舒服”是本项目控制假设，公开 e-bike 证据不足 | 必须用曲柄相位、功率计和主观评价验证；对无扰动连续 e-CVT 可降级为优化项 |
| `min J_cruise` | 巡航时优先维持目标踏频并抑制抖动、能耗和轮端扭矩波动 | 控制目标 | Owuru/enviolo 等成熟产品支持“目标踏频/首选踏频”方向，但权重不是公开事实 | 可作为控制器设计目标；`w_c`、`w_r`、`w_Tw`、`w_E` 需要标定 |
| `intent_sprint = dT_ped/dt high ...` | 判断骑手突然加速 / 冲刺意图 | 控制假设 + 类比证据 | 力矩传感、踏频变化、车速/坡度上下文是合理输入；“电机先补扭、齿比后跟随”的完整体感需验证 | 先做状态机/阈值扫描，再用实车数据校准误判率和响应延迟 |
| `min J_climb` | 爬坡时优先把脚踏力矩拉回舒适区，踏频降为次级约束 | 产品体感假设 | 这是本项目差异化假设。公开产品多强调目标踏频，尚不足以证明“脚感力矩舒适区优先”已经成熟量产 | 必须作为重点验证项；需要骑手舒适区实验、长坡热模型和高负载变比台架数据 |
| Go / No-Go 参数窗口 | 判断体感逻辑是否成立 | 验证规则 | 规则来自工程验证方法，不等同具体阈值 | 阈值必须来自项目目标、台架测试或人体试验；仿真只能找参数窗口，不能发明阈值 |

使用原则：

- 标准理论方程可以直接进 P0 模型，但参数仍要注明是实测、公开来源还是敏感性扫描。
- 控制目标函数只表达“控制器想优化什么”，不能单独证明体感成立。
- 公开产品证据可以证明某类能力存在，例如目标踏频、连续变比、自动换挡；不能直接证明本项目高功率 e-CVT MGU 在 10° 爬坡、冲刺补扭和曲柄低谷变比下也成立。
- 所有弱假设必须在仿真输出中表现为参数窗口，而不是单条漂亮曲线。

## 8. 参数证据分级

### 强证据，可直接作为模型结构或初始参数来源

- 自行车纵向动力学、功率计关系 `P = T * omega`、热 RC 建模方法。
- E2Drives / Owuru 官方公开的 BB 附近一体模块、两电机、belts、planetary gearing、ratchets/freewheel、共享 PCB。
- E2Drives Gen1 官方公开的 600 W peak、65-120 Nm、265% ratio range、4.6 kg。
- Decathlon LD920E / Owuru 已上市城市车证明“目标踏频 + 连续变比”不是纯概念。
- enviolo / NuVinci 成熟 CVP 和 preferred cadence / AUTOMATiQ 路线。
- Pinion MGU 的量产有级 MGU、Auto.Shift、Pre.Select、Start.Select、负载换挡等功能逻辑。

### 中证据，可作边界和类比，不能作最终验证

- Gobao X-system 官方高功率 eCVT MGU 参数和传感器/AI 控制描述。
- Avinox MG Concept 展会图卡、媒体报道和 booth/OCR 参数。
- Toyota HSD、GM Voltec 等汽车 eCVT 的受控自由度、模式切换、扭矩协调和 jerk 管理。
- EV CVT ratio optimization、电机热约束、人机协同控制论文。

### 弱假设，必须敏感性扫描

- CVT / 齿轮 / 皮带 / 棘轮效率 map。
- 传动比执行速度 `rdot_max`、加速度 `rddot_max`、响应延迟。
- 高负载连续变比能力。
- 电机连续扭矩、热容量、散热路径、降额曲线。
- 传感器延迟、噪声、偏置、相位识别误差。
- 曲柄低谷窗口宽度和人体可感知轮端 jerk / 踩踏力矩波动阈值。
- 高功率 Owuru Ride、Avinox MG Concept、Gobao X1/X1P 的未公开最终量产参数。

## 9. 体感判定指标

| 指标 | 定义 | 关注场景 |
| --- | --- | --- |
| cadence tracking | `e_c = omega_c - omega_c_target` 的 RMS、P95、稳态误差、恢复时间 | 巡航、冲刺恢复 |
| pedal torque comfort | `T_ped` 落在舒适区的时间占比、P95、峰值和力矩波动 | 爬坡、起步 |
| wheel torque continuity | `T_w` 阶跃、`dT_w/dt`、回接冲击和反扭矩 | 全场景 |
| ratio lag | `e_r = r_cmd - r`、延迟、上升时间、跟踪误差 | 冲刺、爬坡 |
| thermal derating | 降额开始时间、降额深度、恢复时间 | 10° 爬坡、高负载连续变比 |
| energy penalty | `E_ecvt / E_baseline - 1` 和热损失分布 | 巡航、长坡 |
| crank-phase shift error | `e_phi = wrap(phi_shift_actual - phi_valley)` | 曲柄低谷变比 |
| fallback quality | 故障后可骑/可推/固定比状态下的扭矩连续性 | 传感器、执行器、低电故障 |

通过条件必须按场景定义，不允许只看平均值。P95、最差窗口、故障恢复和主观评分都要纳入。

## 10. 场景定义

| 场景 | 目的 | 必须记录 |
| --- | --- | --- |
| 平路巡航突然加速 | 验证“巡航看踏频，冲刺看意图” | 踩踏力矩上升率、电机补扭、真实踏频短时上扬、齿比后跟随、冲刺后高齿比巡航 |
| 10° 爬坡 | 验证“爬坡看脚感力矩” | 踩踏力矩舒适区占比、目标踏频动态变化、热降额、低速高扭矩效率 |
| 起步 | 验证起步速比和助力建立 | 起步前传动比、首个半圈踩踏力矩、轮端扭矩阶跃、坡道/载重影响 |
| 滑行恢复 | 验证 Pre.Select 类逻辑 | 滑行车速、预选比、恢复踩踏时相位和回接冲击 |
| 高负载连续变比 | 验证机构真实能力 | 高扭矩下 `rdot`、效率、温度、轮端扭矩连续性 |
| 传感器故障 | 验证降级 | 力矩、踏频、相位、轮速、IMU 故障下的状态机和扭矩限制 |

## 11. Go / No-Go 参数窗口

| 参数窗口 | Go 条件 | No-Go 含义 |
| --- | --- | --- |
| 传动比范围 | 所有目标速度/坡度下，`r_required` 落在 `[r_min, r_max]` 内 | 不能宣称巡航踏频或爬坡脚感成立 |
| 变比速度 / 延迟 | `r` 能在体感允许时间内跟随 `r_cmd`，且大变比动作能落入相位窗口或被电机补偿 | 不能宣称“齿比后跟随”或“低谷变比” |
| 电机瞬态扭矩 | `ratio lag` 期间电机能补足轮端扭矩缺口，不触发限流/限扭 | 不能宣称“冲刺看意图，电机先响应” |
| 连续热能力 | 10° 爬坡和高负载变比中，降额后仍满足脚感力矩和轮端连续性 | 不能宣称真实爬坡体感成立 |
| 传动效率 | 能耗惩罚和热损失不超过项目定义阈值 | 短时体感成立，也不能宣称可用体验成立 |
| 轮端扭矩连续性 | 变比、自由轮回接、故障恢复时 `T_w` 无不可接受阶跃/jerk | 不能宣称平顺或高级体感 |
| 曲柄相位估计 | 相位误差、采样延迟、滤波延迟小于低谷控制窗口 | 不能宣称按 12 点 / 低谷附近变比 |
| 传感器降级 | 任一关键传感器异常时进入可解释、安全、无突兀扭矩模式 | 不能宣称量产级控制逻辑可接受 |

具体阈值必须来自项目标定、台架测量或人体试验；仿真阶段只负责找到满足所有指标的参数窗口，不能发明阈值。

## 12. 建议数据结构

```yaml
model:
  vehicle:
    m_eff: measured_or_sensitivity
    wheel_radius: measured
    CdA: coast_down_or_sensitivity
    Crr: coast_down_or_sensitivity
  rider:
    cadence_target_map: measured_or_calibrated
    torque_comfort_band: rider_test_required
    crank_phase_torque_map: measured_with_power_meter
  drivetrain:
    architecture: two_motor_planetary | traction_cvp | belt_cvt | stepped_gearbox | virtual_chain
    r_min: evidence_or_sensitivity
    r_max: evidence_or_sensitivity
    rdot_max: bench_test_required
    rddot_max: bench_test_required
    eta_map: bench_test_required
    backlash_or_freewheel: architecture_specific
  motor:
    torque_speed_limit: dyno_test_required
    power_limit: dyno_test_required
    torque_slew: controller_test_required
    efficiency_map: dyno_test_required
  thermal:
    rc_network: identified_from_temperature_tests
    temp_limits: component_spec
    derating_curve: controller_spec_or_test
  controller:
    mode_logic: cruise | sprint | climb | launch | coast | limp
    intent_detector: calibrated
    cadence_weight: mode_dependent
    torque_weight: mode_dependent
    phase_shift_window: measured_or_calibrated
  sensors:
    latency: measured
    noise: measured
    bias: measured
    dropout: fault_injection
    fault_policy: safety_design
```

## 13. 下一步

1. 先用 P0 做参数敏感性扫描，范围来自 `02_matrices/ecvt_mgu_technical_evidence_database.csv` 和公开论文。
2. 对 two-motor planetary、traction CVP、stepped gearbox 三条最相关路线做 P1 对比。
3. 明确台架必须实测的参数：效率 map、`rdot_max`、高负载变比、热降额、电机扭矩 slew、相位识别误差、自由轮回接冲击。
4. 只有 P2/P3 数据闭环后，才能把“体感逻辑可实现”写成工程结论。
