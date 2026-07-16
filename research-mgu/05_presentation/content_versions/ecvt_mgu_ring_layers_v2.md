# e-CVT MGU 年轮逻辑网页内容版本 v2

生成日期：2026-07-05  
对应网页：`research-mgu/05_presentation/ecvt_mgu_ring_layers.html`  
页面定位：内部产品/市场/管理沟通用离线认知页，不是正式立项结论，也不是产品投放路线图。

## 1. 本版修改重点

- 根据 2026-07-05 更新后的调研包重写网页正文。
- 将 Avinox MG Concept 从“战略信号”更新为“量产方向 / 准量产目标参照”，但保留 booth/OCR、最终 datasheet 和内部机械实现未闭环的证据边界。
- 明确第 3 层只讲“已有解决方案有哪些、具体怎么解决问题”。
- 明确第 4 层只讲“这些解决方案还剩什么问题、e-CVT 如何补位”。
- 将 `TCO 价值` 统一改为“全生命周期使用成本价值”或“全生命周期使用成本”。
- 将 `premium integrated drive` 统一改为“高端一体化驱动体验”。

## 2. 主要来源文件

- `00_status/PROJECT_STATUS.md`
- `02_matrices/ecvt_mgu_scenario_matrix.csv`
- `02_matrices/substitute_solution_segment_matrix.csv`
- `02_matrices/feature_pain_matrix.csv`
- `03_analysis/20_architecture_and_benchmarks/avinox_mg_concept_deep_research.md`
- `03_analysis/20_architecture_and_benchmarks/avinox_mg_concept_evidence_pack.md`
- `03_analysis/10_market_and_scenarios/emtb_pain_points_and_ecvt_mgu_opportunity.md`
- `03_analysis/10_market_and_scenarios/scenario_hypothesis_emtb.md`
- `03_analysis/10_market_and_scenarios/scenario_hypothesis_cargo_family.md`
- `03_analysis/10_market_and_scenarios/scenario_hypothesis_suv_trekking.md`
- `03_analysis/20_architecture_and_benchmarks/l2_l3_l4_benchmark.md`
- `03_analysis/40_feasibility_and_validation/go_no_go_criteria_draft.md`

## 3. 五层完整正文

### Layer 01：e-CVT 是什么

在本调研口径中，e-CVT MGU 指中置电机与连续变比机构集成为单一驱动单元，通过目标踏频、扭矩平滑、连续变比和虚拟档位降低用户换挡负担，并把单速链条/皮带外传动和整车系统功能纳入同一架构。

本层核心判断：

- 它不是“普通中置电机 + 自动换挡”的同义词，而是把电机、传动、控制和整车诊断放进同一系统边界。
- Gobao X-system 是当前最强官方证据：页面支持 motor + transmission single unit、automatic continuously variable transmission、目标踏频和 connected service/security。
- Avinox MG Concept 已升级为量产方向/准量产目标参照：Tech Details 图卡可用于内部对标，但最终 datasheet、内部机械实现和测试基准仍需闭环。

证据 ID：`V004`、`V032`、`F026`、`F027`、`F043`、`F048`

来源口径：

- `PROJECT_STATUS.md`：e-CVT MGU 的价值不是“会自动变速”，而是在同一个中置单元里同时处理传动耐久、目标踏频、扭矩平滑、低速高扭矩、后轮结构和整车控制。
- `gobao_x_system_deep_dive.md`：Gobao 官方页面可支持电机 + 传动系统单一单元、自动连续可变传动、目标踏频、手动控制选项和 connected service/security。
- `avinox_mg_concept_deep_research.md` 与 `avinox_mg_concept_evidence_pack.md`：Avinox Tech Details 六图支持扭矩平滑、无缝换挡、重载/静止换挡、连续变比 + 虚拟档位、低维护单速外传动和系统功能叙事。

### Layer 02：e-CVT 可以用到哪些场景

e-CVT MGU 理论上可以进入多种高端 e-bike 场景；Avinox Tech Details 明确覆盖 eMTB、eTrekking、eSUV、eGravel、eCity、eCargo，但可用不等于适合。

本层列出的可用场景：

- High-end eMTB / gravity / technical climbing：后拨/飞轮/链条外露、非簧载质量、扭矩平滑、负载换挡和技术爬坡是强痛点，但重量、效率、NVH 和骑手信任门槛最高。
- Cargo / family utility / heavy-load daily use：满载起步、坡道、频繁停启、低技能用户误操作、低维护/全生命周期使用成本、倒车助力和机械锁止是核心痛点。
- 高端 SUV / trekking / all-road commuter：低维护、目标踏频、长距离混合路况、轻越野、载物、内置速度传感和整车系统集成可以形成综合价值。
- Premium urban commuter / connected city bike：目标踏频和不用操心换挡的 UX 价值成立，但 hub CVT/enviolo/Owuru 替代压力很大。
- High-end touring / adventure / expedition：长距离、偏远维护、宽范围、可靠和低维护需求真实，但 Rohloff、Pinion 和 gearbox 路线强。
- Fleet / delivery / shared premium utility：有潜在全生命周期使用成本价值，但必须用运营维护数据证明。
- Lightweight eMTB / eGravel / sporty commuter：轻、自然、低阻和运动控制优先，e-CVT MGU 的重量、效率、体积成本很难被价值覆盖；Avinox 将 eGravel 列为覆盖平台，后续需要验证它是营销覆盖还是实际产品机会。

证据 ID：`V004`、`V032`、`F026`、`F041`、`F044`、`F048`

### Layer 03：已有方案具体怎么解决

现有方案已经用不同方式解决了自动换挡、低维护、宽范围、封闭传动和量产风险。第三层只讲它们怎么解决问题，不急着评价 e-CVT。

主要替代路线：

- 电子外变 + 中置：Bosch、Shimano、SRAM 用 cadence、torque、speed 等传感数据、电机卸力、Auto Shift、Coast Shift、手动覆盖、App/显示生态解决换挡时机和运动用户熟悉度。
- 花鼓 CVT/内变 + 中置：enviolo、Rohloff、3X3 用 preferred cadence、自动无级、起步档、静止/负载换挡、封闭低维护和链/带兼容，解决城市、trekking、cargo 的停启、省心和维护问题。
- 有级 gearbox MGU / gearbox：Pinion 用封闭 gearbox、9/12 档、568%/600% 范围、Auto.Shift / Start.Select 和长维护周期叙事，把外露传动和宽范围低维护问题变成可量产方案。
- 普通中置 + 机械传动：用成熟中置电机、传统外变或机械传动，解决成本、重量、维修网络、开发风险和用户熟悉度问题。

证据 ID：`V001`、`V005`、`V007`、`V008`、`V009`、`V010`、`V012`、`F041`

来源口径：

- `l2_l3_l4_benchmark.md`：整理 Bosch eShift、Shimano AUTO SHIFT、SRAM Eagle Powertrain、enviolo、Rohloff、3X3、Pinion 等路线如何解决部分用户体验和维护问题。
- `feature_pain_matrix.csv`：逐项列出各路线的 interesting_feature、pain_point_addressed 和 existing_alternatives。
- `substitute_solution_segment_matrix.csv`：逐场景比较 solved_pains 和 unsolved_pains。

### Layer 04：这些方案还剩什么问题，e-CVT 怎么补

第四层才进入 e-CVT：逐项回答已有方案还留下什么问题，e-CVT 如何用中置集成、连续变比、单速外传动和系统功能补位。

一一对应关系：

- 电子外变的剩余问题：后拨、飞轮、链条仍外露。电子外变改善换挡时机和电机协同，但 eMTB 的泥沙、石击、摔车、跳跃落地和高扭矩磨损仍会打在后端传动件上。
  e-CVT 补法：内部变比 + 单速链条/皮带外传动，减少后端易损件，并形成非簧载质量降低和后轮/悬架自由度收益。

- 花鼓 CVT/内变的剩余问题：复杂度和质量仍在后轮侧。花鼓 CVT/内变能做低维护和自动踏频，但会带来后轮质量、轮组维修、诊断分散和激进 eMTB 骑感压力。
  e-CVT 补法：把复杂机构放回车架中部，让后轮更简单，利于悬架、轮组、货架、挡泥板、售后和整车诊断。

- 有级 MGU 的剩余问题：有级换挡不等于目标踏频。有级 MGU 已经把低维护和宽范围讲清楚，但连续自然感、扭矩平滑、噪声和运动控制体验仍需要比较。
  e-CVT 补法：连续变比、100%-520% 可配置虚拟档、目标踏频、恒定扭矩输出和 `<0.1 s` 换挡窗口可作为准量产目标。

- 普通中置的剩余问题：不改变外部传动架构。普通中置成熟、轻、便宜，但仍依赖外部传动，难以系统性解决低维护、误换挡、后端约束和整车功能统一。
  e-CVT 补法：把机械锁止、电动倒车助力、内置速度传感、connected service/security 放入中置系统，形成整车级功能组合。

仍需验证的共同门槛：

- e-CVT 效率 map、热衰减和持续工况表现。
- 扭矩平滑、overrun、虚拟档位和目标踏频控制质量。
- 满载起步、长坡、低速高扭矩和冲击寿命。
- 断电、低电、故障降级、诊断和模块化售后。
- charging 传动路径、制动协同、单向离合限制和法规边界。

证据 ID：`V032`、`F018`、`F020`、`F026`、`F027`、`F044`、`F047`

### Layer 05：e-CVT 真正适合的场景

真正适合的场景，不是“能装上 e-CVT”的场景，而是替代方案难以同时做到低维护、目标踏频、后端简化、低速高扭矩和整车系统收益的场景。

主场景判断：

1. High-end eMTB / gravity / technical climbing
   - 判断：强痛点、高战略价值、高验证门槛。
   - 价值来源：后拨/飞轮/链条外露易损、泥沙/石击/摔车/跳跃落地风险、非簧载质量、扭矩平滑、负载换挡、虚拟档位和技术爬坡。
   - e-CVT 机会：后端简化、中心化传动、非簧载质量降低、技术爬坡能力和旗舰差异化。
   - 边界：必须证明重量、效率、45 dB 口径、扭矩平滑、`<0.1 s` 换挡、300 Nm 负载换挡、手动/虚拟档可信度、冲击耐久和骑手控制信任。

2. Cargo / family utility / heavy-load
   - 判断：强痛点，但 hub CVT/内变替代压力强。
   - 价值来源：满载起步、坡道、频繁停启、家庭用户误操作、低维护、倒车助力、机械锁止和全生命周期使用成本。
   - e-CVT 机会：让载货/载娃场景像自动挡车一样易用，减少传动误用和售后维护，并把倒车/锁止/诊断纳入整车系统。
   - 边界：必须证明高载热、长坡效率、寿命、故障降级、charging 边界和全生命周期使用成本。

3. 高端 SUV / trekking / all-road commuter
   - 判断：综合价值最均衡，最容易让产品/市场团队和 OEM 理解。
   - 价值来源：低维护、目标踏频、长距离混合路况、轻越野、载物、皮带友好、内置速度传感、低噪声和 connected/security。
   - e-CVT 机会：形成高端一体化驱动体验，不只是单个电机参数。
   - 边界：hub CVT/内变和有级 MGU 替代压力明显，必须证明后轮维护、效率、NVH、系统功能边界和成本溢价。

补充和边界场景：

- Premium urban commuter：UX 价值成立，但 hub CVT/enviolo/Owuru 替代压力很大。
- Touring / adventure：低维护和可靠性需求真实，但 Rohloff/Pinion/gearbox 的可靠性和宽范围叙事强。
- Lightweight eMTB / eGravel：轻、自然、低阻和运动控制优先，e-CVT MGU 的重量、效率和体积成本很难被价值覆盖；Avinox 覆盖 eGravel 后仍需验证是否是真实机会。
- Fleet / delivery / shared utility：有潜在全生命周期使用成本场景，但必须量化维护频次、停工时间、远程诊断和模块更换效率。

证据 ID：`V004`、`V009`、`V020`、`V022`、`V032`、`F026`、`F027`、`F041`、`F044`、`F048`

## 4. 证据边界

- Gobao X-system 是当前最强官方 e-CVT MGU 证据。可以支持 e-CVT MGU、目标踏频、自动连续变比、手动控制选项和 connected service/security；不能外推未确认 OEM 客户、量产时间、真实量产状态、长期可靠性和效率 map。
- Avinox MG Concept 已从“战略信号”升级为“量产方向 / 准量产目标参照”。Tech Details 六图可作为内部对标和验证目标，但内部机制、最终公开 datasheet、测试基准、量产规格、功率、效率、寿命和上市节奏仍不能写成官方闭环事实。
- `520%`、`<0.1 s`、`300 Nm`、`45 dB`、`>1.1 kg`、`3 times more durable`、`10% less efficient`、mechanical motor lock、electric reverse assist、built-in speed sensor、downhill charging 等内容可写成 Tech Details 图卡值或准量产目标，不写成最终工程结论。
- Owuru / Decathlon LD 920 E 可用于说明目标踏频和用户不用操心换挡的 UX 价值，不能直接外推到高功率 MGU 的量产可靠性。
- Pinion、enviolo、Rohloff、3X3、Bosch、Shimano、SRAM 主要作为量产参照或替代方案压力，不是目标技术形态。

## 5. 本版相对 v1 的变化

- 更新 Avinox MG Concept 证据口径：从战略信号改为量产方向 / 准量产目标参照。
- 第 3 层从“已有方案概览”改为“已有方案具体怎么解决问题”。
- 第 4 层从“e-CVT 独特痛点”改为“已有方案剩余问题 -> e-CVT 补法”。
- 场景内容补入 Avinox Tech Details 新证据：非簧载质量、扭矩平滑、45 dB、300 Nm、`<0.1 s`、100%-520% 虚拟档、低维护单速外传动、机械锁止、倒车助力、内置速度传感、charging 和六平台覆盖。
- 将 `TCO 价值` 改为“全生命周期使用成本价值”或“全生命周期使用成本”。
- 将 `premium integrated drive` 改为“高端一体化驱动体验”。

## 6. 后续修改要求

- 后续若只改网页显示，应只调整 CSS、布局、交互和响应式，不改本文件中的结论口径。
- 后续若改正文，应新建 `ecvt_mgu_ring_layers_v3.md`，并说明改动内容、来源文件和证据 ID。
- 不得新增未核验参数、量产时间、OEM 客户、内部机械结构或官方规格。
