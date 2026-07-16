# e-CVT MGU 骑手体感可实现性深度研究

最后更新：2026-07-16

## 1. 研究问题

本轮不再讨论“网页怎么讲清楚”，而是回答一个更硬的问题：

> 真正的 e-CVT MGU，能不能通过机械结构、电机控制、传感器和控制算法，实现“巡航看踏频、冲刺看意图、爬坡看脚感力矩、曲柄低谷附近变比”的骑手体感逻辑？

当前结论要分层看：

- “目标踏频 + 自动连续/电子变比”已经被 Owuru / E2Drives、enviolo AUTOMATiQ、Pinion Auto.Shift、Bosch eShift 生态从不同路线证明为可实现 UX。
- “冲刺时电机先响应、齿比后跟随”在控制理论和汽车 eCVT/EV 传动优化中成立，但 e-bike 产品公开证据还不足，需要用电机瞬态扭矩、变比延迟、轮端扭矩连续性和热模型验证。
- “爬坡看脚感力矩”是本产品定义中最有价值、也最缺公开证据的部分。现有产品更多公开的是 preferred cadence，而不是 pedal torque comfort band。
- “曲柄 12 点 / 力矩低谷换比”对有级换挡和有明显执行扰动的机构很重要；对真正连续、低扰动 e-CVT，它可能从硬约束降级为舒适性优化项。

一句话判断：

> 你的体感逻辑在控制目标上是合理的，但不能由现有公开证据直接证明。它必须进入“机构参数 + 电机补扭 + 热效率 + 人机体感”联合模型，并最终通过台架和样车验证。

对应结构化材料：

- `02_matrices/ecvt_mgu_technical_evidence_database.csv`
- `02_matrices/ecvt_mgu_transmission_architecture_matrix.csv`
- `02_matrices/ecvt_mgu_rider_feel_feasibility_matrix.csv`
- `03_analysis/40_feasibility_and_validation/ecvt_mgu_simulation_model_spec.md`

## 2. 证据分层

| 证据层 | 能证明什么 | 不能证明什么 |
| --- | --- | --- |
| 官方产品页 / 官方零售页 | 产品存在、功能口径、部分规格和商业成熟度 | 独立效率、热、寿命、真实体感质量 |
| 专利 | 机构可能性、传感器/控制流程、保护范围 | 当前产品是否采用、性能是否达标 |
| 论文 | 建模方法、控制方法、可迁移方程 | 具体 e-bike MGU 参数和量产边界 |
| 媒体试骑 / 展会图卡 | 市场信号、体验描述、产品方向 | 可重复工程验证和最终 datasheet |
| 论坛/二手信息 | 故障线索和用户口碑 | 不能作为事实源，除非回查官方或实测 |

本轮采用的核心证据清单见 `02_matrices/ecvt_mgu_technical_evidence_database.csv`。其中最关键的是：

- E2Drives / OWURU / Decathlon：证明目标踏频 + 连续变比城市车 UX 已经存在。
- enviolo：证明 preferred cadence + CVP 作为成熟替代路线存在。
- Pinion / Bosch：证明 Auto.Shift、Start.Select、Pre.Select、电子换挡集成、起步/滑行场景已经成熟。
- Gobao / Avinox：证明高功率 e-CVT MGU 是当前竞品方向，但仍缺独立工程验证。
- Toyota / GM / EV transmission papers：提供受控自由度、模式切换、扭矩协调、ratio optimization 和热约束的建模思想。

## 3. e-bike 成熟产品拆解

### 3.1 Owuru / E2Drives

Owuru / E2Drives 是最接近“真实 e-CVT MGU”的成熟线索。官方技术页公开了 bottom-bracket 附近一体模块、自动传动、两个电机、belts、planetary gearing、ratchets/freewheel 和共享 PCB。Gen1 官方口径包含 600 W peak、65-120 Nm、265% ratio range、4.6 kg，并已在 Decathlon LD 920 E 城市车上作为 OEM fit 出现。

可支持的判断：

- 目标踏频 + 用户不操心档位的 UX 成立。
- 两电机 + 行星/皮带/棘轮的 e-bike 尺度模块不是纯概念。
- 城市车低功率/中等负载场景已经有商业化证据。

仍不能证明：

- 高功率 eMTB/cargo 的 10° 长坡热稳定。
- 高负载连续变比的效率和寿命。
- 冲刺时电机补扭和齿比后跟随的体感质量。
- 断电/低电/执行器故障后的可骑回策略。

### 3.2 enviolo / NuVinci

enviolo 是成熟 traction CVP 路线，不是中置 MGU，但对目标踏频 UX 很重要。它证明 preferred cadence / AUTOMATiQ 类控制可以被用户接受，也能与低维护封闭传动、皮带、城市/trekking/cargo 场景结合。

可支持的判断：

- 巡航看踏频的 UX 不是新假设。
- 连续变比在负载和低速场景比传统外变更自然。
- city / utility 场景已经有强替代压力：用户未必需要 motor-internal e-CVT 才能得到“省心自动变速”。

仍不能证明：

- 中置高功率 e-CVT MGU 的热和扭矩密度。
- 运动型 eMTB 的效率、重量和脚感。
- 曲柄相位窗口和冲刺意图识别。

### 3.3 Pinion MGU / Bosch eShift

Pinion MGU 是量产 stepped gearbox MGU 标杆。它不是 e-CVT，但它把 Auto.Shift、Start.Select、Pre.Select、负载换挡和低维护集成做成了可销售系统。Bosch eShift 则证明整车电控可以把多个 partner drivetrain 纳入统一 HMI/App/显示/诊断生态。

可支持的判断：

- 起步速比和滑行预选是成熟功能，不是展示页概念。
- preferred cadence 可以和手动覆盖共存。
- 有级系统对曲柄相位、降扭窗口和执行器时序更敏感。

仍不能证明：

- 真连续 e-CVT 的效率和热。
- 爬坡时 pedal torque comfort 优先是否比 target cadence 更好。
- 高功率 e-CVT 的断电固定比、低电变比能力和故障降级。

## 4. 新高功率 e-CVT MGU 线索

### 4.1 Gobao X-system

Gobao 官方 X-system 页面是当前最重要的高功率 e-CVT MGU 官方信号。它公开了 motor + transmission in one unit、ECVT、preferred cadence、cadence/torque/speed/gradient 输入、手动模式、connected service 和 120/150 Nm、1200/1500 W、400/500% 等规格口径。

这对你的产品方向很关键，因为它把“多传感器 + 自动传动比 + 高功率 MGU”写成了官方产品路线。

但它仍不是完整工程证据。缺口包括：

- 持续功率和热降额曲线。
- e-CVT 效率 map。
- 高扭矩低速连续变比能力。
- 长坡、泥水、冲击、寿命和故障降级。
- OEM 装车和独立测试。

### 4.2 Avinox MG Concept

Avinox MG Concept 公开信息主要来自展会图卡和媒体报道。它对产品定义价值很高，因为它把低维护单速外传动、虚拟档位、自动/手动、静止/负载换挡、锁止、倒车、charging 等功能组合成了非常接近整车系统的方向。

但 Avinox 的内部机制在不同媒体中存在“连续 / 有级 / 未确认”描述差异，因此不能把它当成已经证明的 e-CVT 机械路线。更稳妥的口径是：

- 它是强竞争信号和高质量产品定义参考。
- 它不是最终工程参数来源。
- `45 dB`、`300 N·m`、`520%` 等只可作为展会图卡/媒体级研究目标或竞品参考，不能写成自有量产承诺。

## 5. 汽车 e-CVT / CVT 类比

汽车 e-CVT 对 e-bike 的价值不在于照搬硬件，而在于控制思想。

可迁移：

- 行星排/差动机构的受控自由度：通过电机控制一个节点速度，使系统表现为无级变速。
- 模式切换：起步、巡航、爬坡、回收、滑行和故障模式可以用状态机管理。
- 扭矩协调：变比或模式变化时保持轮端扭矩连续。
- jerk 管理：不只控制转速，还要控制轮端扭矩和冲击。
- 热约束：最优传动比必须考虑电机/控制器/传动损耗和温度，而不是只追求踏频。

不可直接迁移：

- 汽车没有人腿曲柄相位和踩踏力矩低谷。
- 汽车没有“踏频舒适区”和“脚下力矩一致性”这种强人机耦合目标。
- Toyota/GM 的双电机、高压电池、多离合器、油冷和整车重量边界不能直接下放到 e-bike。
- 汽车 CVT 的效率/热容忍度和 e-bike 完全不同。

因此，汽车资料只能作为“控制架构和模式管理参考”，不能作为 e-bike e-CVT MGU 可实现性的直接证明。

## 6. 专利和论文给出的模型边界

专利能证明很多机构和传感器方案曾被设计过，但大多不直接回答骑手体感问题。本轮重点价值：

- 扭矩传感和零点校准类专利说明：没有稳定 rider input，自动变比无从谈起。
- 自行车/小型 CVT 专利说明：连续变比机构在 bicycle-scale 有历史积累。
- GM Voltec 等 power-split 专利说明：电机 + 行星排 + 模式切换是成熟控制思想。

论文价值主要在建模方法：

- 自行车纵向动力学和功率计模型用于建立坡度、车速、踏频、脚踏功率之间的关系。
- EV CVT ratio optimization 用于生成最优传动比轨迹，但必须加入人腿踏频/力矩目标。
- 电机热约束论文说明：传动比优化如果不考虑热，很容易得到不可实现的漂亮曲线。
- human-in-the-loop e-bike 控制论文说明：骑手和电机可能协作，也可能“抢力”，控制目标要把 rider effort 纳入。

结论是：公开论文足够支持建立真实模型，但不够直接给出 e-bike e-CVT MGU 的完整参数。

## 7. 架构判断

详细矩阵见 `02_matrices/ecvt_mgu_transmission_architecture_matrix.csv`。简化判断如下：

| 架构 | 近期适配性 | 核心风险 |
| --- | --- | --- |
| stepped gearbox + auto shift | 最高，已有 Pinion 量产参考 | 不是连续变比，无法完全表达 e-CVT 体感 |
| traction CVP | city/utility 成熟，高功率运动场景风险中高 | 效率、热、重量和极端变比损失 |
| two-motor planetary eCVT | 最接近目标形态，潜力高 | 双电机热、电功率循环、棘轮/自由轮、控制复杂度 |
| power-split eCVT | 控制思想强，硬件照搬差 | 成本、重量、双电机/高压系统复杂 |
| belt/pulley CVT | 可做但包装和磨损不讨巧 | 夹紧力、滑移、泥水、热 |
| series/virtual-chain | 体感软件自由度最大 | 总效率、法规、失效即无机械传动 |
| hydrostatic CVT | 常规 e-bike 不建议 | 效率、重量、油温、维护 |

如果目标仍是“像 Avinox MG / Gobao 那样电机集成 e-CVT 的整车系统”，最值得深入的是 two-motor planetary / differential eCVT 和 traction CVP 两条路线，并保留 stepped gearbox + auto shift 作为近期可量产对照组。

## 8. 体感逻辑可实现性判断

### 8.1 巡航看踏频

可实现性：高。

理由：Owuru、enviolo、Pinion Auto.Shift 和 Bosch eShift 生态都已经以不同方式证明 preferred cadence / target cadence 是可实现交互。

关键验证项：

- 稳态踏频误差。
- 变比抖动和噪声。
- 真实效率和能耗。

### 8.2 冲刺看意图

可实现性：中。

理由：控制逻辑成立，但公开 e-bike 产品证据不够。它要求系统识别 rider torque rise / cadence acceleration，然后先用电机补扭，再让齿比跟随。这里的关键不是“齿比瞬间变化”，而是 ratio lag 期间轮端扭矩不能塌，踏频短时上扬不能失控。

关键验证项：

- 电机 torque slew 和电流限值。
- 变比延迟。
- 冲刺后目标踏频恢复和高齿比巡航保持。
- 误判恢复。

### 8.3 爬坡看脚感力矩

可实现性：中低到中。

理由：这是最符合你产品差异化的逻辑，但公开竞品很少直接证明“维持 pedal torque comfort band”。多数成熟产品还是围绕 preferred cadence。爬坡时真正难的是低速高扭矩下的效率、热、执行器能力和电机连续扭矩余量。

关键验证项：

- 10° 长坡热降额后，脚感力矩是否仍在中间区。
- 高负载下变比是否仍能连续/平顺执行。
- 踏频目标动态变化是否被用户感知为自然，而不是系统不稳定。

### 8.4 曲柄低谷附近变比

可实现性：中。

理由：曲柄相位窗口对有级换挡和有执行冲击的机构很重要。对真正连续、低扰动 e-CVT，它不是绝对必要，但仍可作为减少脚感扰动的优化手段。

关键验证项：

- 曲柄相位估计延迟和误差。
- 低谷窗口宽度。
- 变比动作是否足够短或足够小。
- 窗口外变比时的脚感冲击是否可感知。

## 9. 必须先补齐的参数

以下参数如果没有，后续仿真只能做敏感性扫描，不能做确定性结论：

- e-CVT 变比范围、`rdot_max`、`rddot_max`、执行延迟。
- 高负载变比能力和保护边界。
- e-CVT 效率 map：至少覆盖车速、踏频、扭矩、坡度对应工况。
- 电机扭矩-转速-电流-温度限制。
- 连续功率和热降额曲线。
- 轮端扭矩连续性和自由轮/棘轮回接冲击。
- 踩踏力矩舒适区的用户标定范围。
- 曲柄相位识别误差和传感器延迟。
- 故障降级：力矩传感器、踏频、轮速、IMU、执行器、低电/断电。

## 10. 建议技术路线

### 第一阶段：证据闭环

继续追：

- E2Drives / Owuru 高功率 Ride 的官方 datasheet、结构、效率和热。
- Gobao X-system 最终 X1/X1P datasheet、OEM 装车、持续性能。
- Avinox MG Concept 官方 press kit、专利、内部机构确认和最终规格。
- enviolo CVP 执行器速度、效率/热和故障 fallback。
- Pinion/Bosch 电子换挡传感器、降扭窗口和错误码逻辑。

### 第二阶段：P0 / P1 仿真

按 `03_analysis/40_feasibility_and_validation/ecvt_mgu_simulation_model_spec.md` 建立模型，先做敏感性扫描：

- ratio range。
- ratio rate / delay。
- motor torque reserve。
- efficiency penalty。
- thermal derating。
- crank phase error。

输出应该是参数窗口，而不是单条曲线。

### 第三阶段：台架

台架优先做：

- 效率 map。
- 高负载连续变比。
- 10° 等效长坡热循环。
- 电机 torque slew 和限流。
- 自由轮/棘轮回接。
- 曲柄低谷窗口变比对脚感扰动的影响。

### 第四阶段：样车

样车验证重点不是只问“是否能自动变速”，而是：

- 巡航时是否稳。
- 冲刺时是否跟脚。
- 长坡时脚下力矩是否一致。
- 系统误判后用户是否能快速纠正。
- 低电/故障时是否可骑、可推、可解释。

## 11. 当前结论

现有证据不能证明你的 e-CVT MGU 体感逻辑一定能实现，但足以证明这不是空想：

- 目标踏频和连续/自动变比 UX 已经有成熟产品证据。
- 高功率 e-CVT MGU 是明确竞品方向，但仍处在证据不足阶段。
- 汽车 eCVT 和 EV transmission 论文能提供控制与建模方法。
- 真正薄弱处集中在爬坡脚感力矩、变比延迟、电机补扭、效率热和故障降级。

下一步不应继续只做页面或概念定义，而应进入“证据参数化仿真 + 台架验证定义”。只有当仿真找到参数窗口，并且台架能实测支持，才能把“巡航看踏频、冲刺看意图、爬坡看脚感力矩”写成工程可实现的产品能力。

