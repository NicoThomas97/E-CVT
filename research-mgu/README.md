# MGU 调研包入口

最后更新：2026-07-15

## 先读什么

先读 `DOCUMENT_MAP.md`。它是本调研包的目录注释，说明每个文件夹和核心文件的用途、证据边界、维护规则和当前研究主轴。

随后先读 `03_analysis/README.md`，再按以下顺序阅读：

- `00_status/PROJECT_STATUS.md`：当前目标、状态、优先缺口和下一步。
- `03_analysis/00_entry_and_index/ecvt_mgu_research_focus.md`：研究边界，说明为什么主轴是 e-CVT/连续变速 MGU。
- `03_analysis/40_feasibility_and_validation/ecvt_mgu_rider_feel_feasibility_deep_research.md`：体感逻辑可实现性深度研究，回答真实 e-CVT MGU 是否能实现巡航、冲刺、爬坡和曲柄相位控制逻辑。
- `03_analysis/40_feasibility_and_validation/ecvt_mgu_simulation_model_spec.md`：真实模型仿真规范，用于后续把公开证据、台架参数和样车数据转成参数窗口。
- `03_analysis/00_entry_and_index/ecvt_competitive_products_web_index.md`：网页索引和复核状态。
- `01_evidence/verified_sources*.csv` 与 `01_evidence/*source_findings.csv`：可引用来源和逐条事实。
- `02_matrices/*.csv`：竞品、替代方案、场景价值和验证任务矩阵。

齿比范围相关结论优先读 `02_matrices/transmission_ratio_range_benchmark.csv`，并回查 `01_evidence/ratio_source_findings.csv`。

体感可实现性相关结论优先读：

- `03_analysis/40_feasibility_and_validation/ecvt_mgu_rider_feel_feasibility_deep_research.md`：主报告。
- `02_matrices/ecvt_mgu_technical_evidence_database.csv`：技术证据库。
- `02_matrices/ecvt_mgu_transmission_architecture_matrix.csv`：传动原理矩阵。
- `02_matrices/ecvt_mgu_rider_feel_feasibility_matrix.csv`：体感逻辑可实现性矩阵。
- `03_analysis/40_feasibility_and_validation/ecvt_mgu_simulation_model_spec.md`：证据参数化仿真规范。

场景和替代方案判断优先读：

- `03_analysis/10_market_and_scenarios/scenario_entry_priority_note.md`：场景进入优先级阅读版，对应 `02_matrices/ecvt_mgu_scenario_matrix.csv` 和 `02_matrices/scenario_substitutability_matrix.csv`。
- `03_analysis/10_market_and_scenarios/substitute_solution_segment_note.md`：替代方案分场景阅读版，对应 `02_matrices/substitute_solution_segment_matrix.csv`。

## 当前研究主轴

本项目当前主轴是：

> e-CVT 形式中置电机集成变速在整车使用场景中的不可替代性和 OEM 系统收益。

当前不是泛泛研究所有 MGU，也不是默认 Pinion 式有级 gearbox MGU 是目标形态。Pinion 主要是量产集成参照；Gobao X-system、Avinox MG Concept、Owuru / E2Drives / Decathlon 构成 e-CVT/连续变速方向的关键证据链。

## 证据规则

- 本 README 只是入口，不是证据库。
- 所有确定性产品结论都应追溯到已核验 `source_id` 或 `finding_id`。
- `backlog`、legacy、搜索命中、视频待复核和旧报告里的内容只能作为线索，不能直接写成事实。
- PowerShell 查看 Markdown/CSV 时建议显式使用 `-Encoding UTF8`。
