# MGU 调研项目状态

最后更新：2026-07-05，v6.5

## 1. 当前目标

本阶段目标已经收敛为：

> 系统补齐 e-CVT 形式中置电机集成变速用于立项判断所需的证据，重点判断在什么整车使用场景下，e-CVT MGU 相比电子外变、花鼓内变/CVT、有级 gearbox MGU、普通中置电机具备不可替代或明显更优的 OEM 系统收益。

第一阶段不是直接给最终立项结论，而是完成证据补齐、场景价值判断模型、替代方案边界和 go/no-go 草案。

## 2. 北极星问题

最终研究要回答：

- 哪些整车使用场景下，e-CVT MGU 的收益不是“也能变速”，而是替代方案难以同时做到？
- 整车厂为什么选择中置电机集成变速，而不是电子外变、花鼓内变/CVT、有级 gearbox MGU 或普通中置电机？
- 哪些场景的痛点最适合用 e-CVT MGU 解决，哪些场景只是“也能用但可替代性强”？
- 哪些技术指标必须先证明，才值得进入正式立项？
- 哪些证据仍然不够，不能支撑管理层决策？

## 3. 当前工作假设

当前最重要的判断不是先决定产品路线图，而是看清每个场景中 e-CVT MGU 的价值来源：

> e-CVT MGU 的价值不是“会自动变速”，而是在同一个中置单元里同时处理传动耐久、目标踏频、扭矩平滑、低速高扭矩、后轮结构和整车控制。

高端 eMTB 不应被理解为痛点弱或次要场景。更准确的判断是：eMTB 是痛点强度和战略价值都很高的场景，后拨/飞轮/链条外露易损、簧下质量、技术爬坡和负载换挡都是真痛点；只是它对重量、效率、NVH、冲击耐久、手动控制和骑手信任的验证门槛最高。

高端 SUV / trekking 和 cargo / family utility 也仍然重要，因为它们对低维护、频繁停启、载重、目标踏频和整车系统集成的需求集中，且更容易让产品/市场团队理解 e-CVT 的省心价值。但这不代表 eMTB 价值更弱。

## 4. 本轮新增文件

证据文件：

- `01_evidence/verified_sources_v6_addendum.csv`：新增 Gobao、Avinox、Owuru、LD 920 E 等 e-CVT/连续变速相关证据。
- `01_evidence/ecvt_source_findings.csv`：e-CVT 专用逐条 finding，避免把旧广义 MGU 证据和本轮结论混在一起。

矩阵文件：

- `02_matrices/ecvt_mgu_scenario_matrix.csv`：按整车场景判断 e-CVT MGU 的系统收益、替代压力和场景角色。
- `02_matrices/substitute_solution_segment_matrix.csv`：按场景比较 e-CVT MGU、电子外变、花鼓 CVT/内变、有级 MGU、普通中置方案。
- `02_matrices/ecvt_mgu_validation_task_matrix.csv`：把场景价值假设转成公开追证、台架、样车、访谈验证任务。

分析文件：

- `03_analysis/gobao_x_system_deep_dive.md`
- `03_analysis/avinox_mg_concept_evidence_pack.md`
- `03_analysis/avinox_mg_concept_deep_research.md`：基于 Bikerumor 文章、Tech Details 六张高清图、The Verge / Transition Velo / Velobiz 等报道，对 Avinox MG Concept 做深度研究；重点补入扭矩平滑、<0.1 s 换挡、300 Nm 负载换挡、100%-520% 可配置虚拟档位、maintenance-free 图卡、mechanical motor lock、electric reverse assist、built-in speed sensor、下坡 charging 图示和六平台覆盖。当前口径：作为 Avinox 量产方向/准量产产品定义和内部对标目标使用。
- `03_analysis/historical_ecvt_lessons.md`
- `03_analysis/go_no_go_criteria_draft.md`
- `03_analysis/ecvt_mgu_validation_plan.md`
- `03_analysis/emtb_pain_points_and_ecvt_mgu_opportunity.md`
- `03_analysis/scenario_hypothesis_emtb.md`
- `03_analysis/scenario_hypothesis_cargo_family.md`
- `03_analysis/scenario_hypothesis_suv_trekking.md`

## 5. 当前证据状态

最高可信的 e-CVT MGU 证据现在分成两类：Gobao 官方 X-system 页面给出 motor + transmission single unit、automatic continuously variable transmission、目标踏频、可选手动、两组功率/扭矩/范围配置；Avinox MG Concept Tech Details 六图给出高可信量产方向/准量产产品定义，可用于内部对标和验证任务。

Avinox MG Concept 已从“战略强信号”推进为“量产方向/准量产产品定义清晰的核心 MGU 对象”。Bikerumor Tech Details 六图已经本地保存并逐图核读，能支持以下判断：Avinox 的核心叙事不只是内置变速，而是扭矩平滑、无缝换挡、重载/静止换挡、连续变比 + 虚拟档位、低维护单速外传动、整车锁止/倒车/速度传感/charging 功能和 eMTB/eTrekking/eSUV/eGravel/eCity/eCargo 六平台覆盖。当前研发口径：这些图卡值可以当作 Avinox 量产方向/准量产目标来做对标和验证；证据口径上仍标注为 booth/OCR，内部机制、测试基准和最终公开 datasheet 是后续闭环项，不应降低 Tech Details 图卡的产品权重。

Owuru / Decathlon LD 920 E 证明“目标踏频 + 用户不用操心换挡”在城市车上有 UX 价值，但它不是同一类高功率 e-CVT MGU 竞品。它更适合作为历史启发和替代压力证据。

Valeo Cyclee 和 Revonte ONE 仍是历史线索，不能作为当前活跃竞品结论。

## 6. 场景价值与替代性草案

当前不再用单一“首发排序”理解场景，而是按痛点结构、系统收益和替代压力阅读：

1. High-end eMTB / gravity / technical climbing：强痛点、高战略价值、高验证门槛；不是弱场景。Avinox 图卡补强了非簧载质量、扭矩平滑、<0.1 s 换挡、300 Nm 负载换挡等价值点，关键仍是证明重量、效率、NVH、冲击耐久和骑手信任。
2. Cargo / family utility：强痛点、强替代压力；价值在满载起步、坡道、频繁停启、家庭用户误操作、低维护、倒车助力和锁止防盗，但必须证明高载热、寿命和 TCO。
3. 高端 SUV / trekking / all-road commuter：综合价值强；目标踏频、低维护、轻越野、载物、长距离混合路况、静止换挡和内置速度传感可以形成 premium integrated drive 体验，但 hub CVT/内变和有级 MGU 替代压力明显。
4. Premium urban commuter：UX 价值成立，但 hub CVT/enviolo/Owuru 替代压力很大，e-CVT MGU 需要证明整车安全、诊断、后轮维护和高级感增量。
5. Touring / adventure：需求存在，但 Rohloff/Pinion/gearbox 的可靠性和宽范围叙事强。
6. Lightweight eMTB / eGravel：轻、自然、低阻和运动控制优先，e-CVT MGU 的重量/效率/体积成本很难被价值覆盖；但 Avinox 将 eGravel 列为覆盖平台，后续需要验证它是营销覆盖还是实际产品机会。

## 7. 仍缺的关键证据

最高优先级：

- Gobao X1/X1P 官方命名、量产时间、OEM 客户、持续功率、效率 map、热衰减、寿命和服务策略。
- Avinox MG Concept 官方资料、完整 press kit、专利、prototype bike 页面，以及 e-CVT 内部实现、断电降级和最终公开 datasheet 确认；这些是闭环项，不影响 Tech Details 图卡作为量产方向/准量产目标使用。
- Avinox Tech Details 图卡中的关键值和功能边界：`>1.1 kg` reduced unsprung mass、150 kg heavier riders、45 dB、300 Nm shift under load、<0.1 s shifting window、100%-520% gear ratio、3 times more durable、10% less efficient、mechanical motor lock、electric reverse assist、built-in speed sensor、下坡 charging。
- Owuru / E2Drives / Decathlon 官方城市车技术链已初步补齐：E2Drives Technology、E2Drives Company、OWURU official page 和 Decathlon LD 920 E 官方商品页可证明 Gen 1 城市车/OEM fit；仍缺高功率 eMTB/cargo 官方 datasheet、非 Decathlon OEM、效率 map、热衰减、寿命、诊断和服务策略。
- Valeo Cyclee 和 Revonte ONE 的官方归档、装车历史和商业结果。

下一阶段必须由测试或访谈补齐：

- e-CVT 效率 map。
- 满载起步、长坡、低速高扭矩热循环。
- 目标踏频、扭矩平滑、overrun 和虚拟档位控制质量及用户接受度。
- 断电/低电/故障降级可骑性。
- 售后模块化、故障码、远程诊断和换件成本。
- 回充/charging 传动路径、飞轮/单向离合限制、制动协同和法规边界。
- OEM 对 BOM、供应风险和系统锁定的接受边界。

## 8. `pm-skills` 使用计划

`pm-skills` 后续会用，但只在证据已经收敛后作为结构化工具，不作为事实来源。

- `competitive-analysis`：用于整理已核验竞品和替代方案定位。
- `market-sizing`：只对价值场景和替代边界已经收敛的目标市场做 TAM/SAM/SOM 估算。
- PRD/产品策略类 skill：在价值场景、替代边界、验证门槛和 go/no-go 标准稳定后用于组织产品定义。

当前阶段还不适合让 `pm-skills` 主导，因为事实、场景和替代压力仍在补证。

## 9. 防跑偏规则

- 不把 URL 收集当成证据。
- 不用 Avinox M2S/M2/M1 参数代表 MG Concept。
- 不把概念机、prototype、量产产品、历史项目和替代技术当成同一成熟度比较。
- 不把“自动换挡”直接说成 e-CVT MGU 独有优势；必须说明外部自动换挡或花鼓 CVT 为什么不足。
- 不让 Pinion 有级 MGU 继续主导目标定义；Pinion 只作为量产集成参照和替代路线。
- 每个确定性结论必须能追溯到已核验 source ID 或 finding ID。
- 如果公司约束会影响场景排序，必须先问用户，不要猜。

## 10. 下一步

下一步建议进入“价值假设转验证任务”。已新增三份场景假设页作为下一步测试和访谈抓手：

- `scenario_hypothesis_emtb.md`：验证后拨取消、后轮/悬架自由度、技术爬坡和骑手控制是否形成可感知收益。
- `scenario_hypothesis_cargo_family.md`：验证满载停启、低技能用户、低维护和 TCO 价值。
- `scenario_hypothesis_suv_trekking.md`：验证 premium integrated low-maintenance、目标踏频和后轮简化价值。

后续具体动作：

- 基于 `ecvt_mgu_validation_task_matrix.csv` 给 `VT001-VT012` 标注优先级、责任人、目标证据和状态。
- 将 `ecvt_mgu_validation_plan.md` 第 3 节转成台架测试需求，将第 4 节转成 OEM / 经销商 / 用户访谈提纲。
- 已用 `avinox_mg_concept_deep_research.md` 更新验证矩阵：新增 Avinox Tech Details 对应验证项，特别是扭矩平滑、非簧载质量、负载换挡、maintenance-free、mechanical lock、reverse assist、built-in speed sensor 和 charging。
- 补查 Gobao/Avinox/Owuru 的官方或准官方闭环资料：Gobao 重点是量产、客户和服务策略；Avinox 重点是 press kit、专利、OEM prototype 页面、测试基准和最终公开 datasheet；Owuru/E2Drives 重点转为高功率 datasheet、效率/热/寿命、服务策略和非 Decathlon OEM。
- 使用 `pm-skills` 的 competitive-analysis 对已核验方案做结构化定位，但不让它生成事实。
