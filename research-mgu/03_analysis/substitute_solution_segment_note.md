# 替代方案分场景阅读版

调研日期：2026-07-15

## 1. 文件定位

本文件是 `02_matrices/substitute_solution_segment_matrix.csv` 的阅读版。它不替代矩阵，也不单独作为证据；所有确定性判断都必须回查矩阵行里的 `evidence_ids`，再继续追溯到 `01_evidence/verified_sources*.csv` 或 `01_evidence/*source_findings.csv`。

阅读口径：

- `e-CVT MGU` 指中置电机与连续变速机构集成的方案。
- `电子外变 + 中置电机` 指 Bosch / Shimano / SRAM 等外部自动或电子换挡生态。
- `花鼓 CVT/内变 + 中置电机` 指 enviolo、Rohloff、Owuru/Decathlon 等后轮或轮端传动路线。
- `有级 gearbox MGU` 指 Pinion E-Drive MGU 等电机 + 有级 gearbox 集成方案。
- `普通中置电机 + 机械传动` 指不把传动系统作为核心差异化的成熟低风险路线。

## 2. 跨场景结论

1. e-CVT MGU 不能只靠“自动换挡”建立不可替代性。电子外变、花鼓 CVT/内变和有级 MGU 都已经能覆盖部分自动或低维护价值；e-CVT MGU 必须把目标踏频、封闭/低维护传动、后轮简化、中心化质量和整车诊断组合成一个系统收益。证据入口：`高端 SUV / trekking`、`Cargo / family utility`、`Premium urban commuter` 的 e-CVT MGU、电子外变、花鼓 CVT/内变和有级 MGU 行；`V004;V005;V007;V008;V009;V010;V011;V012;V020;V022;V025;V031;V032;F013;F016;F018;F020;F021;F022;F023;F026;F027;F039;F040;F041;F042;F044;F045;F046;F047;F048;F049;F050;F052;F053;F054`。

2. 花鼓 CVT/内变是城市、cargo、trekking 场景里最强的体验替代路线之一。e-CVT MGU 的机会不是重复“自动/低维护”，而是证明后轮维护、中心质量、整车诊断、高载起步或高扭矩效率更好。证据入口：`高端 SUV / trekking`、`Cargo / family utility`、`Premium urban commuter`、`Touring / adventure` 的花鼓 CVT/内变行；`V009;V010;V011;V012;V013;V014;V031;F020;F021;F022;F023;F024;F025;F039;F041`。

3. 电子外变 + 高性能中置仍是高端 eMTB 和轻量运动车的强基线。它保留外露后拨、飞轮和链条痛点，但在重量、运动接受度、手动信任和生态成熟度上压力很大。证据入口：`High-end eMTB`、`Lightweight eMTB/eGravel` 的电子外变行；`V007;V008;F016;F018`。

4. 有级 gearbox MGU 是最直接的量产集成替代路线。e-CVT MGU 要胜出，必须证明连续变比、目标踏频、低技能用户友好性、噪声和控制自然度比有级方案更有价值。证据入口：`高端 SUV / trekking`、`Cargo / family utility`、`Premium urban commuter`、`High-end eMTB`、`Touring / adventure` 的有级 gearbox MGU 行；`V001;V018;V020;V021;V022;V025;F001;F004`。

5. 轻量 eMTB / eGravel 不适合作为早期主攻场景，除非重量、低阻和体积出现突破。该细分的主价值排序是轻、自然、运动控制和成熟生态，而不是最大化低维护自动传动。证据入口：`Lightweight eMTB/eGravel` 的 e-CVT MGU、电子外变、普通轻量中置行；`V001;V002;V004;V008;V009;F001;F005;F018;F020;F026`。

## 3. 分场景速读

| 场景 | 最强替代压力 | e-CVT MGU 能胜出的条件 | 不能提前宣称 | 证据入口 |
| --- | --- | --- | --- | --- |
| 高端 SUV / trekking | 花鼓 CVT/内变、有级 gearbox MGU、电子外变 | 把目标踏频、低维护、后轮简化、内置速度传感、低噪声和整车诊断做成高级整车体验，并证明比后轮 CVT/内变更利于维护和高扭矩效率 | 不能只说“自动换挡更高级”；也不能在未证明效率、热、寿命、成本前宣称全面优于成熟替代 | `高端 SUV / trekking` 全部方案行；`V001;V002;V004;V005;V006;V007;V008;V009;V010;V011;V012;V020;V022;V025;V032;F001;F004;F005;F013;F015;F016;F018;F020;F021;F022;F023;F026;F027;F041;F042;F044;F046;F047;F048` |
| Cargo / family utility | 花鼓 CVT/内变、有级 gearbox MGU | 证明满载起步、频繁停启、后轮维护、诊断、倒车/锁止和 TCO 优于成熟内变/CVT方案 | 不能在未验证高载热、耐久和故障降级前宣称量产可靠性 | `Cargo / family utility` 全部方案行；`V001;V004;V005;V006;V007;V008;V009;V010;V011;V012;V020;V025;V032;F001;F004;F013;F015;F016;F018;F020;F021;F022;F023;F026;F027;F029;F041;F045;F047;F048` |
| Premium urban commuter | 花鼓 CVT/内变、Owuru/Decathlon 城市车链条、普通中置/轮毂方案 | 在防盗、远程诊断、后轮维护、高级感和目标踏频体验上覆盖更高成本 | 不能把城市自动低维护说成 e-CVT MGU 独有，因为 hub CVT/Automatic 已经很强 | `Premium urban commuter` 全部方案行；`V001;V004;V005;V006;V007;V009;V025;V031;V033;V034;V035;V036;F001;F004;F013;F015;F016;F020;F026;F027;F039;F040;F041;F042;F049;F050;F052;F053;F054` |
| High-end eMTB | 电子外变 + 高性能中置、有级 gearbox MGU、普通高性能中置 | 证明后拨取消、后轮/悬架设计自由、非簧载质量改善、负载/静止变比、扭矩平滑和虚拟档位被骑手真实感知 | 不能在未验证重量、效率、NVH、冲击耐久和手动信任前宣称是最稳妥首发市场 | `High-end eMTB` 全部方案行；`V001;V002;V003;V004;V006;V007;V008;V009;V012;V018;V021;V022;V027;V028;V029;V032;F001;F004;F006;F015;F016;F018;F020;F024;F031;F032;F035;F036;F043;F044;F045;F046;F047;F048` |
| Touring / adventure | Rohloff/Pinion/gearbox 内变、有级 MGU、可维修电子外变 | 在自动踏频、整车诊断和故障降级策略上超过可靠宽范围传统路线 | 不能在未验证断电可骑、长途效率、全球维修和软件故障降级前宣称适合远征 | `Touring / adventure` 全部方案行；`V001;V004;V005;V006;V007;V010;V011;V013;V014;V025;F001;F004;F013;F015;F016;F022;F023;F025;F026;F027` |
| Lightweight eMTB/eGravel | 电子外变 + 轻量中置、普通轻量中置 + 机械传动 | 重量、低阻、体积和运动手动控制接近轻量中置基线 | 不能把低维护自动传动价值放在轻量/运动控制之前 | `Lightweight eMTB/eGravel` 全部方案行；`V001;V002;V004;V008;V009;F001;F005;F018;F020;F026` |

## 4. 使用建议

后续写报告时，不建议直接引用本文件作为事实来源。推荐引用链条是：

1. 先引用 `02_matrices/substitute_solution_segment_matrix.csv` 中对应 `segment + solution` 行。
2. 再引用该行的 `evidence_ids`。
3. 数值、官方功能、量产状态和具体规格必须继续回查 `01_evidence/verified_sources*.csv` 或 `01_evidence/*source_findings.csv`。

本文件适合回答“哪个替代方案最危险”“e-CVT MGU 在什么条件下有机会赢”“哪些话现在还不能说”。
