# 中置变速电机研发预研报告 v2

调研日期：2026-07-04  
口径修正：本版把 `sources` 拆成已核验来源、待核验来源和逐条 findings。未核验来源不再支撑确定性结论。

## 1. 可信结论

当前公开资料足以支持一个方向判断：中置变速电机/MGU 值得继续研发预研，但第一阶段应围绕“低维护传动 + 自动/半自动换挡 + 整车系统集成”建立验证闭环，而不是只追求最大扭矩或最大峰值功率。

已核验的市场事实：

- Pinion 已有量产 MGU，E1.9/E1.12 分别为 9/12 档、568%/600% range、约 4.0/4.1 kg、85 Nm competitive torque（V001）。
- Gobao 官方 X-system 已明确 motor+transmission 单元和 automatic continuously variable transmission，两个模型块分别为 120 Nm/1200 W/400% 和 150 Nm/1500 W/500%，重量同为 3.85 kg（V004）。
- Avinox MG Concept 仍只有可信媒体信号，不能把 Avinox M2S 的官方量产参数套给 MG Concept（V002, V003）。
- Bosch、Shimano、SRAM 已用系统级电子/自动换挡路线抢占部分 MGU 用户价值（V005, V007, V008）。

## 2. 研发优先级

### 最高优先级：Pinion vs Gobao 双路线对照

Pinion 代表有级 gearbox MGU，Gobao 代表 eCVT MGU。研发预研应先回答：

- eCVT 在效率、热、寿命、NVH 和控制复杂度上能否接受？
- 有级 gearbox 是否已经足够满足用户体验，且更容易量产？
- 哪种路线在 cargo/SUV/trekking 上更有商业胜率？
- 哪种路线在 eMTB 上更可能被高端用户接受？

### 第二优先级：L2 外部自动换挡路线

Bosch eShift、Shimano AUTO SHIFT、SRAM Eagle Powertrain、enviolo AUTOMATiQ、Rohloff E-14 都证明：用户可能先接受“电机+电子传动协同”，而不是重量和成本更高的 MGU。

自研 MGU 必须证明比 L2 路线多出来的价值：

- 更低维护成本。
- 更少外露易损件。
- 更好的中心化重量分布。
- 更适合 belt drive 和封闭传动。
- 更可控的换挡负载管理。

## 3. 首发场景建议

不建议把第一版产品定义为“eMTB 旗舰复刻 Avinox MG Concept”。更稳的首发假设是：

| 场景 | 推荐度 | 原因 |
| --- | --- | --- |
| SUV / trekking / cargo | 高 | 对低维护、可靠性、自动换挡、满载起步更敏感，重量容忍度更高 |
| 高端 eMTB | 中 | 技术展示价值高，但重量、手动可控性、NVH、冲击和品牌信任门槛高 |
| 城市通勤 | 中 | 自动换挡价值强，但 enviolo/Bosch/Shimano 等 L2/L4 替代方案竞争强 |
| 轻量 eMTB / eGravel | 低 | 对重量和体积极敏感，不适合第一版 MGU |

## 4. 三个月预研动作 v2

第 1 阶段：证据补齐

- 解决 backlog 中的高优先级缺口：Avinox MG Concept 官方资料、BikeBiz Gobao 原文、Valeo、Revonte、Owuru。
- 对 Pinion 和 Gobao 做参数口径表：扭矩、功率、重量、速比、热、维护、OEM、价格带。
- 收集实车评测和用户反馈，尤其是 Pinion MGU 的噪音、换挡、可靠性和售后。

第 2 阶段：架构方案

- 有级 MGU：以 Pinion 为主参照，定义 9-12 档或等效宽速比方案。
- eCVT MGU：以 Gobao/Avinox MG Concept 为趋势参照，重点验证效率、热、寿命和控制。
- 外部自动换挡 MVP：以 Bosch/Shimano/SRAM/enviolo/Rohloff 为参照，用较低成本验证自动换挡用户价值。

第 3 阶段：台架和整车验证

- 台架：效率地图、热稳态、换挡冲击、负载下换挡、密封、泥沙、水洗、执行器寿命。
- 整车：满载起步、城市停启、长坡、低速大扭矩爬坡、eMTB 技术段、清洗后功能。
- 服务：整机返修边界、模块可换性、诊断接口、OEM 装车工时、售后工具。

## 5. 当前文件如何使用

- `verified_sources.csv`：可引用来源。
- `source_backlog.csv`：待核验来源，不支撑结论。
- `source_findings.csv`：事实摘录表，报告结论应从这里推导。
- `product_longlist_verified.csv`：二轮核验后的产品长名单。
- `l1_mgu_deep_dive.md`：直接 MGU 深挖。
- `l2_l3_l4_benchmark.md`：准直接、基准和替代路线。

## 6. 仍需谨慎

本版还不是最终评审报告。它已经修正了来源口径，但还缺三类证据：

- 官方缺口：Avinox MG Concept、Valeo、Revonte、Owuru。
- 用户缺口：Pinion MGU 和相关整车的长期可靠性/噪音/售后。
- 商业缺口：整车价格带、OEM 装车量、供应链成本和售后成本。

