# 中置变速电机全球市场与竞品图谱

调研日期：2026-07-03  
服务对象：研发预研  
输出边界：公开资料桌面研究，第一轮目标是找全候选、分层、标记证据状态。Avinox MG Concept 的 Tech Details 图卡作为 Avinox 量产方向/准量产产品定义信息处理，可进入功能和参数目标对标；同时仍区分 booth/OCR 证据、官方页面和最终公开 datasheet。

## 1. 如何阅读

证据标签沿用 `sources.csv`：

- `O`：官方页面、官方手册、官方规格或官方站点。
- `S`：媒体、用户提供文章、展会报道或其他非官方资料。
- `official_text_verified`：本轮已从官方页面读到关键文本。
- `source_url_collected_needs_text_pass`：已收集官方 URL，但本轮未完成规格抽取，不能用于数值结论。
- `media_verified_official_gap`：媒体信号较强，但缺官方规格闭环。
- `booth_image_quasi_production`：展台图卡/OCR 证据足够完整，可作为量产方向信息、准量产产品定义和内部对标目标；最终公开 datasheet、测试基准和内部机制仍需官方闭环。

本报告把市场分为四层，避免把“电机+变速一体机”“电机+外部电子变速”“普通高性能中置电机”和“纯传动件”混为同一类。

## 2. 分层地图

### L1 直接 MGU：电机+变速机构集成

这一层才是中置变速电机最直接的参照。第一轮应全部深挖。

| 候选 | 状态 | 当前判断 | 证据 |
| --- | --- | --- | --- |
| Pinion E-Drive MGU E1.9/E1.12 | 量产/OEM | 目前最重要的量产对标；官方明确 Motor.Gearbox.Unit、9/12 档、568%/600% 速比、85 Nm 级别。 | O001 |
| Avinox MG Concept | 准量产产品定义信号 | Tech Details 图卡已给出 100%-520% 连续变比、<0.1 s、300 Nm、扭矩平滑、低维护、锁止/倒车/速度传感/charging 和六平台覆盖；可作为 eCVT MGU 量产方向和功能/参数目标参照，但不能套用 Avinox M2/M2S 参数，也不能替代最终公开 datasheet。 | V027, V028, V029, V032 |
| Gobao X1/X1P MGU | 计划量产信号 | 与 Avinox MG Concept 同期成为 eCVT/MGU 市场信号；需补官方 X-series 规格。 | O003, S001 |
| Valeo Cyclee | 历史/当前状态待核实 | 是“电机+自动变速箱”路线的关键历史样本，但本轮未完成官方规格抽取。 | O020 |
| Revonte ONE | 历史/当前状态待核实 | 与 MGU 方向高度相关，但当前商业状态、量产交付和官方资料需要二轮确认。 | O021 |
| Owuru | 边界待定 | 可能是自动无级/类 CVT 传动路线，需确认是否 motor-internal、bottom-bracket、hub 或外部 transmission。 | O022 |

### L2 准直接方案：中置电机+自动/电子变速深度集成

这一层不把变速做进电机，但能在用户体验上抢走 MGU 的一部分价值：自动换挡、低维护、换挡不打断踩踏、系统级控制。

| 候选 | 当前判断 | 证据 |
| --- | --- | --- |
| Bosch eShift | 最强的系统集成参照之一，靠 Bosch 生态和合作传动件完成电子/自动换挡体验。 | O004 |
| Shimano EP801 + Di2 AUTO SHIFT / FREE SHIFT | 通过电机、曲柄运动和 Di2 传动协同实现自动/空转换挡体验，是 MGU 外部化替代路线。 | O006, O007 |
| SRAM Eagle Powertrain | 以电机控制和 AXS Transmission 绑定为核心的高端 eMTB 生态，需要二轮抽取官方细节。 | O008 |
| enviolo AUTOMATiQ | 城市、货运、通勤场景的自动无级/类 CVT 用户体验强参照。 | O009 |
| Rohloff E-14 | 高可靠内变+电子换挡路线，对长途、货运、高端 trekking 有参考价值。 | O010 |
| 3X3 NINE / electronic options | 高扭矩内变路线候选，需确认 OEM 规模和电子化程度。 | O011 |

### L3 高性能中置基准：无内置变速，但定义市场预期

这一层不应被当成直接 MGU 竞品，但会定义用户和 OEM 对功率、扭矩、重量、噪音、软件、服务网络的预期。

重点基准：Avinox M2S/M2/M1（O002）、Bosch Performance Line CX/CX Race（O005）、Shimano EP801（O007）、Brose（O018）、Yamaha PW 系列（O017）、Bafang M-series（O016）、TQ HPR 系列（O014）、FAZUA Ride 60（O015）、Specialized Turbo 系统（O019）。

第一轮结论：如果只在扭矩/峰值功率上与这些平台硬拼，很容易进入高成本、强生态、强品牌的红海。MGU 的差异化必须来自“低维护传动、整车布置、自动换挡体验、可靠性、服务成本和系统控制”，而不是单纯更大扭矩。

### L4 替代技术路线：不当同类竞品，但影响设计取舍

| 路线 | 对 MGU 的意义 | 证据 |
| --- | --- | --- |
| Pinion C/P-line + Smart.Shift | 机械 gearbox、密封、速比范围和服务模型的关键学习对象。 | O024 |
| Effigear gearbox | gearbox 结构和 Valeo 背景线索。 | O023 |
| enviolo manual/CVT hubs | 自动/无级体验与城市货运用户需求参照。 | O009 |
| Rohloff SPEEDHUB | 高可靠、高价、高服务周期内变参照。 | O010 |
| Gates Carbon Drive | 低维护、无油污、密封 gearbox/MGU 常见搭档，影响链线、张紧、车架接口。 | O013 |
| Shimano LINKGLIDE/CUES | 低成本高耐久外变路线，可能在中低端市场削弱 MGU 必要性。 | O025 |

## 3. 市场趋势信号

1. 一体化正在从“电机+电池+显示”推进到“电机+换挡+传动”  
   Avinox、Bosch、Shimano、SRAM 都在强化系统体验；Pinion 已把电机和 gearbox 打包为 MGU（O001, O002, O004, O006, O008）。

2. 直接 MGU 正从量产参照进入准量产产品定义竞争  
   Pinion 是最清晰的有级量产参考；Gobao X-system 给出官方 eCVT MGU 规格块；Avinox MG Concept 即使尚未发布最终公开 datasheet，Tech Details 图卡也已经足够作为量产方向和准量产功能/参数目标使用，需要把 booth/OCR 证据、官方页面和正式量产规格分层管理（O001, V004, V032）。

3. 自动换挡价值并不只靠 MGU 实现  
   Bosch eShift、Shimano AUTO/FREE SHIFT、SRAM Eagle Powertrain、enviolo AUTOMATiQ、Rohloff E-14 都能从外部传动侧提供自动/电子换挡体验（O004, O006, O008, O009, O010）。

4. 高端 eMTB 是品牌展示场，SUV/cargo/trekking 可能是 MGU 更稳定的商业入口  
   高端 eMTB 需要轻量、高功率密度和强操控；cargo/SUV/trekking 更看重低维护、可靠性、传动寿命和用户无感换挡。这个判断需要后续用整车装车量和价格带验证。

## 4. 研究队列

优先二轮深挖：

- Pinion E1.9/E1.12：完整 datasheet、OEM 车型、用户评价、服务成本、噪音、失效案例。
- Avinox MG Concept：press kit、专利、量产时间、与 M1/M2/M2S 的边界；Tech Details 图卡值的测试口径，包括 >1.1 kg、150 kg、45 dB、300 Nm、<0.1 s、100%-520%、3 times more durable、10% less efficient、charging。
- Gobao X1/X1P：官方 X-series 资料、规格页、量产节奏、OEM 合作。
- Valeo Cyclee / Revonte ONE / Owuru：确认当前商业状态，避免把停止或未量产项目当成活跃竞品。
- Bosch/Shimano/SRAM/enviolo/Rohloff：提取“自动换挡体验”的用户价值与系统边界，而不是只抄参数。

## 5. 如何接入 pm-skills

`pm-skills` 可在证据库完成后使用：

- 用 `competitive-analysis` 生成竞品矩阵、定位图、差异化建议。
- 用 `market-sizing` 生成 TAM/SAM/SOM 假设框架。
- 不允许让 PM 模板直接发明规格、量产时间、OEM 客户或技术壁垒。
