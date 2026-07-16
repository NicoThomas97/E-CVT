# 场景价值假设：High-end eMTB / gravity / technical climbing

最后更新：2026-07-05

## 1. 当前判断

高端 eMTB 不是 e-CVT MGU 的弱场景。它是强痛点、高战略价值、高验证门槛场景。

本场景的核心问题不是“e-CVT 能不能自动变速”，而是：

> e-CVT MGU 能否在不破坏重量、效率、NVH 和骑手控制信任的前提下，解决后拨/飞轮/链条外露易损、后轮动态和技术爬坡痛点？

Avinox MG Concept Tech Details 已经把 eMTB 相关价值具体化为非簧载质量降低、扭矩平滑、负载换挡和虚拟档位控制。它虽然还不是最终公开 datasheet，但已经可以按 Avinox 量产方向信息和准量产目标输入。如果能证明这些收益，eMTB 是最能体现 e-CVT MGU 架构价值的场景之一。如果不能证明，电子外变 + 高性能中置电机仍会是更稳妥的路线。

## 2. 痛点结构

### 2.1 外露传动易损

eMTB 在石头、树根、泥沙、摔车、侧向冲击、跳跃落地和高扭矩踩踏中，后拨、飞轮和链条是高风险外露件。电子外变可以改善换挡逻辑，但不能根除外露传动易损。

证据与支撑：

- `F018`：SRAM Eagle Powertrain 官方证据说明电子外变和 eMTB 驱动系统已经能深度集成。
- `F034`：Avinox MG Concept 发布/媒体证据提到无后拨、多片飞轮和单速链/皮带路线。
- `F047`：Avinox Tech Details 图卡显示 legacy toolkit 被替代，Avinox MG drivetrain 采用单速外传动叙事，并宣称 3 times more durable、traditional drivetrain 10% less efficient。
- `scenario_hypothesis` 依据 `emtb_pain_points_and_ecvt_mgu_opportunity.md` 中对后拨、飞轮、链条外露痛点的整理。

### 2.2 簧下质量和后轮动态

全避震 eMTB 对后轮质量、轮组维护和悬架响应敏感。花鼓 CVT/内变可以减少后拨，但会把复杂机构和质量放在后轮侧。e-CVT MGU 的结构机会在于把复杂度放回车架中心。

证据与支撑：

- `F041`：enviolo 官方证据证明 hub CVT 能解决自动踏频和低维护，但也构成 e-CVT MGU 的替代压力。
- `F044`：Avinox Tech Details 图卡宣称 reduced unsprung mass `>1.1 kg`，这是 eMTB 后轮/悬架动态价值的重要量产方向/准量产目标。
- `ecvt_mgu_scenario_matrix.csv` 已将花鼓 CVT/内变在激进 eMTB 中的后轮质量和骑感限制列为替代边界。

### 2.3 技术爬坡和骑手控制

eMTB 经常在低速、高扭矩、突然变坡、站姿踩踏和湿滑路面中工作。e-CVT MGU 若能支持负载/静止变比、目标踏频和虚拟档/手动覆盖，理论上可以降低误换挡和链路冲击。

证据与支撑：

- `F026`：Gobao 官方 X-system 证据支持目标踏频和连续变比。
- `F032`、`F036`：Avinox MG Concept 媒体/展会信号提到 cadence-based auto mode、虚拟档、负载或静止换挡。
- `F044-F046`：Avinox Tech Details 图卡把这些能力具体化为 torque smoothing、assist remain/overrun、300 Nm shift under load、<0.1 s shifting window、constant torque output、100%-520% range 和 1-13 virtual gears；本项目应按量产方向/准量产目标处理。

## 3. e-CVT MGU 的独特收益假设

对 eMTB，e-CVT MGU 必须证明的独特收益不是“自动”，而是以下组合：

1. 去掉或显著减少后拨/多片飞轮依赖。
2. 把变速复杂度从后轮侧移到中置，保留后轮轻量和悬架响应空间。
3. 低速高扭矩技术爬坡中自动给出合适变比。
4. 保留高级骑手需要的手动覆盖、虚拟档位或可锁定模式。
5. 通过扭矩平滑、fast response with no overshoot 和可控 overrun 提升高端骑感。
6. 让 OEM 能讲清旗舰差异化：后端简化、中心化传动、低维护和高控制可信度。

## 4. 替代方案边界

| 替代方案 | 已能解决 | 仍可能留给 e-CVT MGU 的空间 |
| --- | --- | --- |
| 电子外变 + 高性能中置 | 自动/电子换挡、运动用户熟悉、重量和生态成熟 | 后拨、飞轮、链条仍外露；冲击和维护痛点未根除 |
| 花鼓 CVT/内变 + 中置 | 去后拨、低维护、停启友好 | 后轮质量、悬架响应、轮组维护和运动骑感压力 |
| 有级 gearbox MGU | 低维护、封闭传动、后拨取消、量产参照 | 连续目标踏频、自然感、噪声和运动控制体验需要比较 |
| 普通高性能中置 + 外变 | 轻、强、成熟、用户熟悉 | 无法解决外露传动和后轮结构自由度问题 |

## 5. 必须验证的问题

| 维度 | 需要证明 | 失败信号 |
| --- | --- | --- |
| 重量和包络 | 相比高性能中置 + 外变，重量、Q-factor、离地间隙和车架布置可接受 | 整车明显变重、影响操控或限制悬架设计 |
| 效率 | 技术爬坡、巡航和高速转场不显著吞续航 | e-CVT 在常用区间效率损失过大 |
| NVH | 电机和变速噪声不破坏高端 eMTB 感知 | 高频噪声、变比调整声或链/带噪声明显 |
| 控制可信度 | 站姿重踩、突然变坡、湿滑路面下响应可预测 | 骑手觉得系统抢控制或节奏不可预期 |
| 扭矩平滑 | Avinox 式 fast response with no overshoot 和 assist remain/overrun 可被骑手感知为自然，而不是迟钝或拖拽 | overrun 过长、响应过冲或节奏怪异 |
| 耐久 | 摔车、石击、泥水、清洗、跳跃落地后仍可靠 | 传感器、线束、密封或执行器成为故障点 |
| 售后 | 外部易损件减少后，整机维修成本和时间可接受 | 从换后拨变成高价总成返修 |

## 6. 当前证据强弱

较强：

- `V004/F026/F027`：Gobao 官方证据支持 e-CVT MGU、目标踏频和系统集成方向。
- `V008/F018`：SRAM 官方证据证明电子外变是强替代。
- `V027/V028/V029/V032/F031-F036/F043-F048`：Avinox MG Concept 已是 eMTB 量产方向/准量产产品定义信号，而不只是媒体热度。

较弱或待验证：

- eMTB 后拨/飞轮/链条损坏频率目前多为行业经验和内部分析，仍需补媒体、售后、车店或用户证据。
- Avinox MG Concept 内部机制、测试基准和最终公开 datasheet 未官方闭环，但 Tech Details 图卡已可作为量产方向验证目标。
- e-CVT MGU 在 eMTB 的效率、热、NVH、冲击寿命和骑手接受度无公开硬数据。

## 7. 下一步建议

- 补查 eMTB 后拨/飞轮/链条损坏与维护频率的媒体、售后、车店和用户证据。
- 找 Pinion MGU eMTB 用户反馈，重点看重量、噪声、换挡感、可靠性和售后。
- 对比电子外变 eMTB 用户对 Auto Shift、Coast Shift、手动控制的真实接受度。
- 样机验证优先做技术爬坡、跳跃落地后可靠性、泥水清洗后可靠性、手动覆盖可信度、扭矩平滑和 overrun 可接受度。
