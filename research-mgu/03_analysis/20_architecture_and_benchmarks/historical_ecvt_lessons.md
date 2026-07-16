# e-CVT / 自动无级路线历史启发

最后更新：2026-07-04

## 1. 本文件用途

本文件不是竞品规格表，而是用历史和相邻路线回答一个问题：

> 自动无级变速为什么有吸引力，又为什么不一定能自然变成一个成功的中置集成变速产品？

证据来源包括 V009、V015、V016、V030、V031、V033-V039 以及 v6 findings F037-F041、F049-F058。

## 2. 已知路线分层

| 路线 | 当前用途 |
| --- | --- |
| enviolo Automatic / CVP hub | 证明城市、utility 和 trekking 中“目标踏频 + 自动 CVT”已经有成熟替代方案 |
| E2Drives / OWURU / Decathlon LD 920 E | 官方链条证明 OWURU/E2Drives Gen 1 城市车方案、Decathlon OEM fit、目标踏频和连续变速 UX 已经不是纯媒体线索 |
| Owuru Ride / Owuru high-power gearbox unit | 证明高功率连续变速中置路线正在向 eMTB/cargo 扩展，但仍是 prototype/媒体阶段 |
| Valeo Cyclee | 历史 integrated motor + automatic gearbox 线索，用来提醒商业化和生态风险 |
| Revonte ONE | 历史 integrated motor + CVT 线索，目前仅保留为未充分核验线索 |

## 3. 关键经验

### 3.1 无级和目标踏频是有用户价值的

E2Drives、OWURU 和 Decathlon 官方页面已经补齐了城市车技术链：E2Drives 把 Propulsive Module 定义为底部支架附近的自动传动和双电机一体方案，OWURU 页面把它描述为目标踏频控制和自动连续变速，Decathlon LD 920 E 官方商品页证明它已有 OEM 装车。Transition Velo 和 DOWNTOWN 的媒体测试进一步说明，用户设定踏频后让系统自动适配路况，可以让城市骑行变得直觉、平顺，而且不用反复判断该升档还是降档。

这个结论对 e-CVT MGU 很重要：用户真正买到的不是“技术先进”，而是“不用想档位也能轻松起步、爬坡、通勤”。

但这个价值在城市车上已经可以被 Owuru、enviolo 等路线部分实现。因此 e-CVT MGU 不能只说自己有自动踏频，必须说明为什么中置集成比 hub CVT 或外部自动系统更适合 OEM。

### 3.2 高功率化会把问题从 UX 转移到工程验证

Owuru Ride、E-MOUNTAINBIKE 的 Owuru gearbox unit 和 Gobao X-system 都把无级/连续变比推向更高扭矩、更高功率和 eMTB/cargo 方向。此时核心问题不再是“用户喜不喜欢自动”，而是：

- 低速高载时效率是否可接受。
- 长坡和满载是否热衰减。
- 传动机构寿命和密封是否能覆盖真实用户。
- 站姿重踩、冲击、轮胎打滑时控制是否稳定。
- 软件是否能让骑手信任，而不是觉得被系统接管。

### 3.3 “自动变速”不是护城河

Bosch eShift、Shimano AUTO SHIFT、SRAM Eagle Powertrain、enviolo Automatic、Rohloff E-14 都已经从不同角度解决了自动/电子换挡。e-CVT MGU 的护城河只能来自系统收益组合：

- 去后拨/多级飞轮。
- 中置质量和后轮简化。
- 目标踏频和连续变比体验。
- 封闭低维护传动。
- 电机、传动、电池、显示、诊断和防盗统一。

缺任何一项，都可能被更便宜、更成熟的替代方案压住。

### 3.4 历史项目提醒：好技术不等于好产品

Valeo Cyclee 和 Revonte ONE 都是必须继续追溯的历史线索。现有证据还不能说明它们的商业结果和失败原因，但它们提醒我们不要只看 demo 或媒体热度。

正式立项前需要查清：

- 是否获得稳定 OEM 装车。
- 为什么没有形成广泛装车或持续声量。
- 供应链、售后、成本、重量、效率、噪音、软件和法规哪个环节造成阻力。
- 整车厂是否愿意把核心传动风险交给单一系统供应商。

### 3.5 城市成功不等于 eMTB/cargo 成功

LD 920 E 的城市体验不能直接外推到高功率 eMTB 或重载 cargo。城市车证明的是“目标踏频/不用操心换挡”体验成立，并且现在已经有 E2Drives/OWURU/Decathlon 官方链条支撑；高功率 e-CVT MGU 还需要额外证明热、寿命、效率、极端工况控制、服务策略和非 Decathlon OEM 状态。

## 4. 对立项判断的直接启发

e-CVT MGU 的最强机会不是所有车型，而是同时满足以下条件的车型：

- 真实用户不想管理档位。
- 频繁起步、坡道、载重或泥沙冲击让外部传动成为痛点。
- OEM 想要 low-maintenance premium system，而不是最低 BOM。
- 花鼓 CVT/内变会带来后轮维护、后轮质量、结构或诊断上的明显短板。
- 有级 MGU 的档位感、噪音或骑行心智不如目标踏频无级方案。

不满足这些条件时，e-CVT MGU 很容易变成“更贵更复杂的自动换挡”。

## 5. 后续历史追证任务

- 找 Valeo Cyclee 官方归档、OEM 装车案例和当前状态。
- 找 Revonte ONE 官方归档、融资/量产/公司状态和失败原因。
- Owuru / E2Drives / Decathlon 官方城市车资料已补齐，后续重点改为追高功率官方 datasheet、效率 map、热/寿命、诊断服务策略、非 Decathlon OEM 和量产路线。
- 对比 enviolo Automatic 的真实用户/车厂反馈，确认城市和 cargo 中 hub CVT 的强替代程度。
