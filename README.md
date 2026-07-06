# E-CVT

本仓库用于保存 e-CVT 形式中置电机集成变速（MGU）的前期研究资料。当前内容集中在
[`research-mgu/`](research-mgu/)，目标是支持立项前判断：在哪些整车使用场景中，e-CVT
MGU 相比电子外变、花鼓 CVT/内变、有级 gearbox MGU、普通中置电机，能够形成更强的
OEM 系统收益和更清晰的不可替代性。

## 当前资料包

- [`research-mgu/00_status/`](research-mgu/00_status/)：项目状态、当前目标、证据缺口和下一步。
- [`research-mgu/01_evidence/`](research-mgu/01_evidence/)：已核验来源、逐条事实和待补证据。
- [`research-mgu/02_matrices/`](research-mgu/02_matrices/)：场景价值、替代方案、产品长名单和验证任务矩阵。
- [`research-mgu/03_analysis/`](research-mgu/03_analysis/)：竞品、技术路线、场景假设、痛点和 go/no-go 分析。
- [`research-mgu/04_reports/`](research-mgu/04_reports/)：阶段性预研报告草稿。
- [`research-mgu/05_presentation/`](research-mgu/05_presentation/)：汇报用页面、内容版本和变更记录。
- [`research-mgu/99_legacy/`](research-mgu/99_legacy/)：历史资料和早期草稿，仅作背景参考。

## 建议阅读顺序

1. [`research-mgu/README.md`](research-mgu/README.md)
2. [`research-mgu/00_status/PROJECT_STATUS.md`](research-mgu/00_status/PROJECT_STATUS.md)
3. [`research-mgu/02_matrices/ecvt_mgu_scenario_matrix.csv`](research-mgu/02_matrices/ecvt_mgu_scenario_matrix.csv)
4. [`research-mgu/02_matrices/substitute_solution_segment_matrix.csv`](research-mgu/02_matrices/substitute_solution_segment_matrix.csv)
5. [`research-mgu/02_matrices/ecvt_mgu_validation_task_matrix.csv`](research-mgu/02_matrices/ecvt_mgu_validation_task_matrix.csv)
6. [`research-mgu/03_analysis/go_no_go_criteria_draft.md`](research-mgu/03_analysis/go_no_go_criteria_draft.md)
7. [`research-mgu/03_analysis/ecvt_mgu_validation_plan.md`](research-mgu/03_analysis/ecvt_mgu_validation_plan.md)

## 研究边界

本仓库当前阶段不直接给最终立项结论，而是沉淀证据、场景价值判断模型、替代方案边界和验证任务。
确定性结论应能追溯到已核验 source ID 或 finding ID；仅出现在 backlog、legacy 或未核验材料中的信息，
应作为线索或候选假设处理。

## 维护说明

- 新增证据优先放入 `01_evidence/`，并补充来源、事实描述和可信度边界。
- 新增场景或竞品判断时，同步更新 `02_matrices/` 中相关矩阵。
- 面向汇报的内容放在 `05_presentation/`，并在 changelog 中记录关键变化。
- `99_legacy/` 中的资料不建议直接作为结论依据。
