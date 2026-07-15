# MGU 调研文档地图

最后更新：2026-07-16

## 1. 入口和阅读顺序

本目录用于说明 `research-mgu` 里每类文件的用途、证据边界和维护规则。后续读者应先读本文，再按研究问题进入对应材料。

建议顺序：

1. `00_status/PROJECT_STATUS.md`：当前研究状态、核心判断、最高优先级缺口和下一步。
2. `03_analysis/ecvt_mgu_research_focus.md`：研究边界，说明为什么主轴是 e-CVT/连续变速 MGU，而不是广义 MGU。
3. `03_analysis/ecvt_mgu_product_function_definition.md`：e-CVT MGU 整车系统功能定义，整理脚感一致性主线、总功能池、控制方式、变速逻辑、骑行体感、接口和验证方向。
4. `03_analysis/ecvt_competitive_products_web_index.md`：网页索引，记录官方页、媒体页、展会页、测评页和待复核线索。
5. `01_evidence/verified_sources*.csv` 和 `01_evidence/*source_findings.csv`：可引用证据和逐条 finding。
6. `02_matrices/*.csv`：把证据转成竞品、替代方案、场景价值和验证任务。
7. `03_analysis/*.md`：专题分析、场景假设、验证计划和 go/no-go 草案。

新增齿比范围口径时，优先读：

1. `02_matrices/transmission_ratio_range_benchmark.csv`：证据闭合的外变、MGU、内变/CVT/gearbox 齿比范围对比矩阵。
2. `01_evidence/ratio_source_findings.csv`：逐条齿比范围 finding 和计算口径。
3. `03_analysis/transmission_ratio_range_benchmark_note.md`：范围定义、排除项和当前最大外变速结论。

阅读场景和替代方案判断时，优先读：

1. `03_analysis/scenario_entry_priority_note.md`：场景进入优先级阅读版，对应 `02_matrices/ecvt_mgu_scenario_matrix.csv` 和 `02_matrices/scenario_substitutability_matrix.csv`。
2. `03_analysis/substitute_solution_segment_note.md`：替代方案分场景阅读版，对应 `02_matrices/substitute_solution_segment_matrix.csv`。
3. `02_matrices/ecvt_mgu_validation_task_matrix.csv` 和 `03_analysis/ecvt_mgu_validation_plan.md`：把上述场景判断转成验证任务。

阅读产品功能定义时，优先读：

1. `03_analysis/ecvt_mgu_product_function_definition.md`：当前产品定义入口，说明系统可以做哪些功能、如何控制，并定义巡航看踏频、冲刺看意图、爬坡看脚感力矩的控制优先级。
2. `03_analysis/ecvt_mgu_visual_storyboard.md`：图文介绍网页视觉故事板，说明如何把控制策略转成曲线图、图解、页面章节和 AI 生成提示词。
3. `03_analysis/url_key_info_integrated_dedup_summary.md`：从后续 Excel 对比表提取出的整合去重材料，包含红色加粗标注中的个人理解和重点内容。
4. `03_analysis/technical_architecture.md` 和 `03_analysis/ecvt_mgu_validation_plan.md`：用于把功能定义继续拆成技术架构和验证任务。

查看产品方向和骑手体感展示时，优先读：

1. `05_presentation/ecvt_mgu_rider_feel_visualization_20260716.html`：桌面端骑手体感可视化正式展示页，用趋势曲线解释巡航、冲刺、爬坡和曲柄相位换比窗口。
2. `05_presentation/ecvt_mgu_product_direction.html`：产品方向五层逻辑展示页，用于说明 e-CVT MGU 的价值边界和场景判断。
3. `05_presentation/README.md` 和 `05_presentation/PRESENTATION_CHANGELOG.md`：展示页入口、阅读方式和变更记录。

上述 `05_presentation` 文件只作为汇报展示入口，不作为事实源；其中所有确定性判断仍应回查 `01_evidence`、`02_matrices`、`03_analysis` 和内容版本记录。

## 2. 文件类型和证据边界

| 位置 | 用途 | 能否直接当证据 |
| --- | --- | --- |
| `00_status/PROJECT_STATUS.md` | 项目状态和当前判断入口 | 不能单独当证据；其中结论必须回查 source/finding |
| `01_evidence/verified_sources*.csv` | 已核验来源清单 | 可以作为来源索引 |
| `01_evidence/*source_findings.csv` | 从来源抽取的逐条事实 | 可以作为事实引用入口 |
| `01_evidence/source_backlog.csv` | 待查来源和缺口 | 不能当事实 |
| `02_matrices/*.csv` | 结构化判断和对比 | 只能引用其背后的 source/finding |
| `03_analysis/ecvt_competitive_products_web_index.md` | 网页索引和复核状态 | `已核验`可作入口；`待复核/搜索命中`只能作线索 |
| `03_analysis/*deep*` / `*_hypothesis_*` / `*_plan.md` | 专题分析和验证设计 | 结论需追溯 source/finding |
| `04_reports/*.md` | 阶段报告草稿 | 不是最新事实源，引用前先看状态页和证据表 |
| `05_presentation/*` | 汇报展示材料 | 不作为事实源 |
| `99_legacy/*` | 旧资料和历史草稿 | 默认不能作为当前证据 |

## 3. 当前研究主轴

当前主轴是：判断中置电机与 e-CVT/电子控制连续变速系统高度集成的 MGU，在整车场景中是否形成不可替代的 OEM 系统收益。

- Gobao X-system：当前最重要的官方 e-CVT MGU 竞品/参照。
- Avinox MG Concept：量产方向/准量产目标参照，Tech Details 图卡可用于内部对标，机制和最终 datasheet 仍需闭环。
- Owuru / E2Drives / Decathlon：官方城市车技术链已补齐，可证明目标踏频和连续变速 UX；高功率 eMTB/cargo 路线仍主要是媒体首测/原型证据。
- Pinion MGU：量产有级 MGU 参照，不再作为目标技术形态的默认代表。
- Bosch/Shimano/SRAM/enviolo/Rohloff/3X3：关键替代方案，用于判断自动换挡、低维护和系统集成是否足以替代 e-CVT MGU。

## 4. 维护规则

- 所有确定性产品结论必须能追溯到 `source_id` 或 `finding_id`。
- `搜索命中待复核`、`视频待复核`、`待补`、`backlog_only` 只能写成线索，不能写成事实。
- 官方页优先于媒体页；媒体页可用于骑行体验、展会信号、机制解释和风险边界。
- 图片、展台图卡、规格表截图和网页图库可能包含关键事实；抽取时要注明是否来自正文、图片/OCR 或 PDF。
- Markdown 和 CSV 按 UTF-8 读写。PowerShell 查看时建议显式使用 `-Encoding UTF8`。
- 在当前 PowerShell/Codex 桌面环境中，`rg` 全局搜索必须显式给路径，例如 `rg -n -i "owuru|e2drives" .\research-mgu`。不要使用不带路径的 `rg "keyword"` 作为没有命中的依据。
- 补来源时先进入 `verified_sources*.csv`，再进入 `source_findings.csv`，最后再改矩阵和分析结论。
