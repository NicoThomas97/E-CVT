# e-CVT MGU 年轮逻辑网页内容版本 v1

生成日期：2026-07-05  
对应网页：`research-mgu/05_presentation/ecvt_mgu_ring_layers.html`  
页面定位：内部产品/市场/管理沟通用离线认知页，不是正式立项结论，也不是产品投放路线图。

## 1. 本版内容原则

- 使用五层年轮结构组织内容：定义 -> 场景 -> 已有解决方案 -> 剩余痛点 -> 真正适合场景。
- 只基于现有调研成果重组表达，不新增未追溯事实。
- 保留证据 ID，但让它服务于追溯，不抢正文主线。
- 第五层采用证据中立口径：High-end eMTB、Cargo/family、高端 SUV/trekking 都是主场景，但验证门槛和替代压力不同。

## 2. 主要来源文件

- `00_status/PROJECT_STATUS.md`
- `02_matrices/ecvt_mgu_scenario_matrix.csv`
- `02_matrices/substitute_solution_segment_matrix.csv`
- `03_analysis/10_market_and_scenarios/scenario_hypothesis_emtb.md`
- `03_analysis/10_market_and_scenarios/scenario_hypothesis_cargo_family.md`
- `03_analysis/10_market_and_scenarios/scenario_hypothesis_suv_trekking.md`
- `03_analysis/20_architecture_and_benchmarks/gobao_x_system_deep_dive.md`
- `03_analysis/10_market_and_scenarios/pain_point_opportunity_map.md`

## 3. 五层完整正文

### Layer 01：e-CVT 是什么

在本调研口径中，e-CVT MGU 指中置电机与连续变速机构集成为单一驱动单元，通过目标踏频和连续变比降低用户换挡负担，并保留必要的手动/虚拟档控制入口。

本层核心判断：

- 它不是“普通中置电机 + 自动换挡”的同义词，而是把电机、传动、控制和整车诊断放进同一系统边界。
- Gobao X-system 是当前最强官方证据：页面支持 motor + transmission single unit、automatic continuously variable transmission、目标踏频和 connected service/security。
- Avinox MG Concept 只能作为战略信号处理，不能写成已确认量产规格或内部机械实现。

证据 ID：`V004`、`F026`、`F027`

来源口径：

- `PROJECT_STATUS.md`：e-CVT MGU 的价值不是“会自动变速”，而是在同一个中置单元里同时处理传动耐久、目标踏频、低速高扭矩、后轮结构和整车控制。
- `gobao_x_system_deep_dive.md`：Gobao 官方页面可支持电机 + 传动系统单一单元、自动连续可变传动、目标踏频、手动控制选项和 connected service/security。

### Layer 02：e-CVT 可以用到哪些场景

e-CVT MGU 理论上可以进入多种高端 e-bike 场景，但每个场景的痛点结构、替代压力和验证门槛不同。可用不等于适合，适合也不等于首发风险低。

本层列出的可用场景：

- High-end eMTB / gravity / technical climbing：后拨/飞轮/链条外露、后轮动态和技术爬坡是强痛点，但重量、效率、NVH 和骑手信任门槛最高。
- Cargo / family utility / heavy-load daily use：满载起步、坡道、频繁停启、低技能用户误操作和低维护/TCO 是核心痛点。
- 高端 SUV / trekking / all-road commuter：低维护、目标踏频、长距离混合路况、轻越野、载物和整车系统集成可以形成综合价值。
- Premium urban commuter / connected city bike：目标踏频和不用操心换挡的 UX 价值成立，但替代压力大。
- High-end touring / adventure / expedition：长距离、偏远维护、宽范围、可靠和低维护需求真实，但已有强替代。
- Fleet / delivery / shared premium utility：有潜在 TCO 价值，但必须用运营维护数据证明。
- Lightweight eMTB / eGravel / sporty commuter：轻、自然、低阻和运动控制优先，e-CVT MGU 的重量、效率、体积成本很难被价值覆盖。

证据 ID：`V004`、`F026`、`F041`

来源口径：

- `ecvt_mgu_scenario_matrix.csv`：按整车场景整理 pain_profile、ecvt_mgu_value_hypothesis、替代压力和 scenario_role。
- 三份 `scenario_hypothesis_*.md`：分别解释 eMTB、Cargo/family、SUV/trekking 的痛点结构和验证问题。

### Layer 03：这些场景已有的解决方案

现有方案已经覆盖了自动换挡、低维护、宽范围、封闭传动和成本成熟度中的一部分，所以 e-CVT 不能只讲“能变速”。

主要替代路线：

- 电子外变 + 中置电机：能做自动/半自动换挡，运动生态成熟，开发风险低；但后拨、飞轮和链条仍外露，低维护故事不足。
- 花鼓 CVT/内变 + 中置电机：在城市、trekking、cargo 的低维护、目标踏频和停启体验上很强；但后轮复杂、后轮维修、系统诊断分散和后轮质量问题仍存在。
- 有级 gearbox MGU：已证明封闭、宽范围、低维护和量产装车路径；但连续变比和目标踏频体验不一定同等自然。
- 普通中置电机 + 机械传动：成熟、轻、便宜、供应链广；但无法系统性解决外露传动维护、误换挡、后端传动件约束和整车诊断统一。

证据 ID：`V001`、`V005`、`V009`、`V010`、`V012`、`F041`

来源口径：

- `substitute_solution_segment_matrix.csv`：逐场景比较 e-CVT MGU、电子外变、花鼓 CVT/内变、有级 MGU、普通中置方案的 solved_pains 与 unsolved_pains。
- `pain_point_opportunity_map.md`：强调自动换挡不是 MGU 独占卖点，Bosch/Shimano/SRAM 可提供电子/自动换挡体验；enviolo/Rohloff/3X3 已覆盖不少低维护和停启痛点。

### Layer 04：e-CVT 能解决的其他方案未同时解决的痛点

e-CVT 真正的机会不是单个痛点，而是把其他方案分散处理的痛点放进同一个中置系统里同时解决。

本层提炼的组合痛点：

- 外露传动和后端易损件：电子外变改善换挡逻辑，但不能根除后拨、飞轮、链条外露风险。
- 目标踏频和连续变比：相比有级换挡，e-CVT 有机会让普通用户不用操心档位，同时保留手动覆盖。
- 高载起步、坡道、低速高扭矩：Cargo/family 和技术爬坡场景需要系统在负载下给出合适变比，降低误操作和传动冲击。
- 中置集成与后轮简化：相比 hub CVT/内变，e-CVT 的潜在收益在后轮简化、质量集中、诊断统一和高扭矩控制协同。
- OEM 整车系统收益：把电机、变速、显示、APP、诊断、防盗、灯光和远程服务统一起来，而不是卖一个单独电机参数。

证据 ID：`F018`、`F020`、`F026`、`F027`、`F041`

来源口径：

- `gobao_x_system_deep_dive.md`：Gobao 的价值不只是能变速，而是目标踏频、连续变比、手动覆盖、去后拨/多级飞轮、中置集成和系统化连接的组合。
- `scenario_hypothesis_emtb.md`：eMTB 的独特收益假设包括去掉或减少后拨/多片飞轮依赖、把变速复杂度从后轮侧移到中置、支持低速高扭矩技术爬坡和手动覆盖。
- `scenario_hypothesis_cargo_family.md`：cargo/family 的价值必须转化为更少维护、更少误用、更稳定高载起步、更可诊断的故障处理和 TCO。

### Layer 05：e-CVT 真正适合的场景

真正适合的场景，不是“能装上 e-CVT”的场景，而是替代方案难以同时做到低维护、目标踏频、后端简化、低速高扭矩和整车系统收益的场景。

主场景判断：

1. High-end eMTB / gravity / technical climbing
   - 判断：强痛点、高战略价值、高验证门槛。
   - 价值来源：后拨/飞轮/链条外露易损、泥沙/石击/摔车/跳跃落地风险、后轮动态和技术爬坡。
   - e-CVT 机会：后端简化、中心化传动、技术爬坡能力和旗舰差异化。
   - 边界：必须证明重量、效率、NVH、手动/虚拟档可信度、冲击耐久和骑手控制信任。

2. Cargo / family utility / heavy-load
   - 判断：强痛点，但 hub CVT/内变替代压力强。
   - 价值来源：满载起步、坡道、频繁停启、家庭用户误操作、低维护和 TCO。
   - e-CVT 机会：让载货/载娃场景像自动挡车一样易用，减少传动误用和售后维护。
   - 边界：必须证明高载热、长坡效率、寿命、故障降级和 TCO。

3. 高端 SUV / trekking / all-road commuter
   - 判断：综合价值最均衡，最容易让产品/市场团队和 OEM 理解。
   - 价值来源：低维护、目标踏频、长距离混合路况、轻越野、载物、皮带友好和 connected/security。
   - e-CVT 机会：形成 premium integrated drive，不只是单个电机参数。
   - 边界：hub CVT/内变和有级 MGU 替代压力明显，必须证明后轮维护、效率、NVH 和成本溢价。

补充和边界场景：

- Premium urban commuter：UX 价值成立，但 hub CVT/enviolo/Owuru 替代压力很大。
- Touring / adventure：低维护和可靠性需求真实，但 Rohloff/Pinion/gearbox 的可靠性和宽范围叙事强。
- Lightweight eMTB / eGravel：轻、自然、低阻和运动控制优先，e-CVT MGU 的重量、效率和体积成本很难被价值覆盖。
- Fleet / delivery / shared utility：有潜在 TCO 价值，但必须量化维护频次、停工时间、远程诊断和模块更换效率。

证据 ID：`V004`、`V009`、`V020`、`V022`、`F026`、`F027`、`F041`

来源口径：

- `PROJECT_STATUS.md`：当前不再用单一“首发排序”理解场景，而是按痛点结构、系统收益和替代压力阅读。
- `scenario_hypothesis_emtb.md`：eMTB 是强痛点、高战略价值、高验证门槛场景。
- `scenario_hypothesis_cargo_family.md`：Cargo/family 是强痛点场景，但不是无替代场景。
- `scenario_hypothesis_suv_trekking.md`：高端 SUV/trekking 是综合价值场景。

## 4. 证据边界

- Gobao X-system 是当前最强官方 e-CVT MGU 证据。可以支持 e-CVT MGU、目标踏频、自动连续变比、手动控制选项和 connected service/security；不能外推未确认 OEM 客户、量产时间、真实量产状态、长期可靠性和效率 map。
- Avinox MG Concept 按 e-CVT MGU 方向作为研究分类处理，但内部机制、量产规格、功率、效率、寿命和上市节奏不能写成官方闭环事实。
- Owuru / Decathlon LD 920 E 可用于说明目标踏频和用户不用操心换挡的 UX 价值，不能直接外推到高功率 MGU 的量产可靠性。
- Pinion、enviolo、Rohloff、3X3、Bosch、Shimano、SRAM 主要作为量产参照或替代方案压力，不是目标技术形态。

## 5. 本版相对现有网页的变化

- 新增独立年轮版网页 `ecvt_mgu_ring_layers.html`，不覆盖原 dashboard/deck。
- 将原先分页/长页的价值叙事改成五层年轮：定义、场景、已有方案、剩余痛点、适合场景。
- 将第五层按证据中立口径收束，不把 eMTB 降级，也不把 SUV/Cargo 写成唯一答案。
- 新增本内容版本归档文件，作为后续 `v2/v3` 的正文追踪基线。

## 6. 后续修改要求

- 后续若只改网页显示，应只调整 CSS、布局、交互和响应式，不改本文件中的结论口径。
- 后续若改正文，应新建 `ecvt_mgu_ring_layers_v2.md`，并说明改动内容、来源文件和证据 ID。
- 不得新增未核验参数、量产时间、OEM 客户、内部机械结构或官方规格。
