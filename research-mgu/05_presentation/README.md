# e-CVT MGU 价值认知离线网页

最后更新：2026-07-05

## 如何打开

新增年轮逻辑版：

`research-mgu/05_presentation/ecvt_mgu_product_direction.html`

它按五层年轮组织内容：`e-CVT 是什么 -> 可用场景 -> 已有方案怎么解决 -> 剩余问题与 e-CVT 补法 -> 真正适合场景`。本版用于让读者从内到外顺着逻辑看 e-CVT MGU 的价值边界；页面中的证据 ID 可点击查看真实证据记录。最新内容版本已同步记录在：

`research-mgu/05_presentation/content_versions/ecvt_mgu_ring_layers_v3.md`

直接用浏览器打开：

`research-mgu/05_presentation/ecvt_mgu_stage_sync_dashboard.html`

这是一个单文件离线网页，CSS 已内嵌，不依赖外网资源。

另有一个分页交互原型，用于验证“每页只显示一章、滚轮切换”的汇报方式：

`research-mgu/05_presentation/ecvt_mgu_stage_sync_deck.html`

## 当前页面定位

这个网页面向产品/市场团队，用于阶段性理解 e-CVT MGU 的价值边界。它不是正式立项结论，也不是产品投放路线图。

当前版本重点回答：

- e-CVT MGU 到底解决哪些真实痛点。
- 哪些整车场景中这些痛点最集中。
- 相比电子外变、花鼓 CVT/内变、有级 gearbox MGU、普通中置电机，哪些价值可以被替代，哪些仍可能保留。
- 山地车为什么不是弱场景，而是强痛点、高验证门槛场景。
- 公开证据目前支持到哪里，哪些还必须靠台架、样机或 OEM/用户访谈补齐。

## 阅读方式

建议按以下顺序阅读：

1. `年轮主线`：先看五层逻辑如何从定义推到适合场景。
2. `五层内容`：快速扫一遍定义、场景、已有方案、剩余问题和适合场景。
3. `已有方案`：看电子外变、花鼓 CVT/内变、有级 MGU、普通中置分别怎么解决问题。
4. `剩余问题`：看这些方案还留下什么问题，以及 e-CVT 如何补位。
5. `适合场景`：收束到 eMTB、cargo/family、SUV/trekking 和边界场景。

页面中 `Vxxx` / `Fxxx` 证据标签为可点击证据入口：点击后会显示来源标题、来源方、记录文件、核验范围、支持内容和证据边界；该浮层默认隐藏，不作为新的主线章节展示。

## 证据边界记录

- Gobao X-system 是当前最强官方 e-CVT MGU 证据。
- Avinox MG Concept 按 e-CVT MGU 方向处理，但量产规格和内部机械实现仍缺官方闭环。
- Owuru / Decathlon LD 920 E 用于说明目标踏频和用户不用操心换挡的 UX 价值，不能直接外推到高功率 MGU 量产可靠性。
- Pinion、enviolo、Rohloff、Bosch、Shimano、SRAM 主要作为量产参照或替代方案压力，不是目标技术形态。
- eMTB 的后拨易损、飞轮/链条外露、簧下质量、技术爬坡和负载换挡痛点已经单独补充到 `03_analysis/emtb_pain_points_and_ecvt_mgu_opportunity.md`。

这些证据边界保留在内容版本记录和调研文档中，不再作为年轮网页的可见主章节展示。

## 数据来源

页面内容来自现有调研包，主要包括：

- `00_status/PROJECT_STATUS.md`
- `02_matrices/ecvt_mgu_scenario_matrix.csv`
- `02_matrices/substitute_solution_segment_matrix.csv`
- `03_analysis/gobao_x_system_deep_dive.md`
- `03_analysis/avinox_mg_concept_evidence_pack.md`
- `03_analysis/historical_ecvt_lessons.md`
- `03_analysis/go_no_go_criteria_draft.md`
- `03_analysis/emtb_pain_points_and_ecvt_mgu_opportunity.md`
- `01_evidence/verified_sources*.csv`
- `01_evidence/ecvt_source_findings.csv`

## 变更记录

网页生成、更改和关键口径决策记录在：

`research-mgu/05_presentation/PRESENTATION_CHANGELOG.md`
