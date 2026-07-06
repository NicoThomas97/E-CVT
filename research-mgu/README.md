# MGU 调研包说明

最后更新：2026-07-04

## 当前研究主轴

本项目当前主轴是：

> e-CVT 形式中置电机集成变速在整车使用场景中的不可替代性和 OEM 系统收益。

当前不是泛泛研究所有 MGU，也不是默认 Pinion 式有级 gearbox MGU 是目标形态。Pinion 现在主要是量产集成参照；Gobao X-system 和 Avinox MG Concept 是 e-CVT/连续变速方向的核心信号。

## 优先阅读

- `00_status/PROJECT_STATUS.md`：当前目标、进度、场景排序、证据缺口和下一步。
- `02_matrices/ecvt_mgu_scenario_matrix.csv`：e-CVT MGU 场景价值、系统收益和替代压力判断。
- `02_matrices/substitute_solution_segment_matrix.csv`：各场景下 e-CVT MGU 与电子外变、花鼓 CVT/内变、有级 MGU、普通中置电机的对照。
- `02_matrices/ecvt_mgu_validation_task_matrix.csv`：把场景价值假设转成公开追证、台架、样车、访谈验证任务。
- `03_analysis/go_no_go_criteria_draft.md`：进入下一阶段验证前的 go/no-go 标准草案。
- `03_analysis/ecvt_mgu_validation_plan.md`：台架测试、样车验证、OEM/经销商/用户访谈的证据补齐计划。
- `03_analysis/emtb_pain_points_and_ecvt_mgu_opportunity.md`：eMTB 山地车痛点、簧下质量、后拨易损和 e-CVT MGU 机会说明。
- `03_analysis/scenario_hypothesis_emtb.md`：高端 eMTB 场景的痛点、替代边界和验证问题。
- `03_analysis/scenario_hypothesis_cargo_family.md`：cargo/family 场景的满载停启、低维护、TCO 和替代边界。
- `03_analysis/scenario_hypothesis_suv_trekking.md`：高端 SUV/trekking 场景的综合系统价值和替代边界。
- `03_analysis/gobao_x_system_deep_dive.md`：Gobao X-system 深挖。
- `03_analysis/avinox_mg_concept_evidence_pack.md`：Avinox MG Concept 证据边界。
- `03_analysis/historical_ecvt_lessons.md`：Owuru、Valeo、Revonte、enviolo 等历史和相邻路线启发。

## 当前可作为证据使用的文件

- `01_evidence/verified_sources.csv`：基础已核验来源。
- `01_evidence/verified_sources_v3_addendum.csv`：v3 补充来源。
- `01_evidence/verified_sources_v5_addendum.csv`：v5 Pinion/OEM/媒体补充来源。
- `01_evidence/verified_sources_v6_addendum.csv`：v6 e-CVT/连续变速补充来源。
- `01_evidence/source_findings.csv`：广义 MGU 和替代方案逐条事实。
- `01_evidence/ecvt_source_findings.csv`：e-CVT 专用逐条事实。

## 当前主要矩阵

- `02_matrices/ecvt_mgu_scenario_matrix.csv`
- `02_matrices/substitute_solution_segment_matrix.csv`
- `02_matrices/ecvt_mgu_validation_task_matrix.csv`
- `02_matrices/product_longlist_verified.csv`
- `02_matrices/l1_mgu_comparison_verified.csv`
- `02_matrices/feature_pain_matrix.csv`
- `02_matrices/pinion_mgu_user_evidence.csv`
- `02_matrices/oem_bike_examples.csv`

## `pm-skills` 使用计划

`pm-skills` 后续会使用，但它不是证据来源。

- `competitive-analysis`：证据收敛后整理竞品/替代方案定位。
- `market-sizing`：只对通过场景筛选的目标市场做 TAM/SAM/SOM。
- PRD/产品策略类 skill：在价值场景、替代边界和验证门槛稳定后组织产品定义。

不要用 `pm-skills` 直接发明规格、事实、市场规模、用户付费意愿或产品结论。

## Legacy / 草稿文件

以下文件保留为搜索过程和背景记录，不应直接作为最终证据：

- `99_legacy/sources.csv`
- `99_legacy/product_longlist.csv`
- `99_legacy/competitor_matrix.csv`
- `99_legacy/rnd_preresearch_report.md`
- `03_analysis/market_landscape.md`
- `03_analysis/technical_architecture.md`
- `04_reports/rnd_preresearch_report_v2.md`

## 证据规则

所有确定性产品结论都应追溯到已核验 source ID 或 finding ID。

只出现在 backlog 或旧 sources 表里的候选，只能写成线索、历史候选或未核验路线，不能写成确定事实。
