# 变速机构齿比范围证据汇总

调研日期：2026-07-15

## 1. 文件位置

本轮把“变速机构齿比范围”拆成三层文件维护：

- `01_evidence/verified_sources_v7_ratio_addendum.csv`：新增 Shimano / SRAM / Shimano Alfine 官方来源。
- `01_evidence/ratio_source_findings.csv`：逐条记录可引用的齿比范围 finding 和计算口径。
- `02_matrices/transmission_ratio_range_benchmark.csv`：最终对比矩阵，供后续报告和方案判断引用。

## 2. 口径

齿比范围统一按 `最大齿比 / 最小齿比` 计算。

外变速的绝对最小/最大齿比不是后拨或飞轮单独决定，而是由前牙盘和后飞轮共同决定：

```text
最小齿比 = 最小前盘齿数 / 最大飞轮齿数
最大齿比 = 最大前盘齿数 / 最小飞轮齿数
总范围 = 最大齿比 / 最小齿比
```

1x 外变如果只列飞轮，不列牙盘，只能写 cassette range。例如 10-52T 是 520%，但绝对最小/最大齿比仍取决于用户选的前盘。

MGU、内变花鼓、CVT 和 gearbox 的公开资料多数只给总范围，不给真实内部最小/最大齿比。因此矩阵中用 `not_published`，不能把最低档直接写成 1。Avinox MG Concept 是例外：Tech Details 图卡显示的是相对 `100%-520%`，所以矩阵只把它作为相对范围，不写成最终 datasheet。

## 3. 当前结论

在本轮官方资料扫描中，证据闭合的最大外变速组合是：

> Shimano CUES 2x11：`36-22T` + `11-45T`，总范围 `669.4%`。

它超过 Pinion P1.18 的 `636%`、Shimano MTB 2x12 的 `623.1%`、Shimano Trekking 3x9 的 `618.2%`、Pinion E-Drive MGU E1.12 的 `600%`、Avinox MG Concept 图卡的 `520%` 和 SRAM Eagle 10-52T 的 `520%`。

这个结论的边界是“官方组件规格 + 容量闭合 + 不使用超规格混搭”。它不是全市场、历史所有零件和民间魔改方案的绝对上限。

## 4. 修正和排除项

- 早先的 `44/32/22T + 11-36T = 655%` 没有闭合证据，已排除。
- `FC-MT500-3 / 40-30-22T + 11-36T = 595%` 可作为传统 3x 示例，但不是最大外变速范围。
- Bosch eShift、Shimano AUTO SHIFT、SRAM Eagle Powertrain 属于换挡生态或整套系统，齿比范围取决于搭配传动件，不单独列最大/最小齿比。
- 3X3 当前已验证来源证明其生态和静止/负载换挡能力，但项目已有来源没有闭合具体速比表，所以不进入本轮范围矩阵。
- Valeo Cyclee、Revonte ONE 当前仍是历史线索，缺少可引用官方/归档规格，不进入本轮范围矩阵。

## 5. 使用建议

后续报告如要引用“最大外变速范围”，优先引用 `02_matrices/transmission_ratio_range_benchmark.csv` 的 `RR001`，并同时引用 `R001` / `V040`。如要引用 Avinox、Gobao、Pinion、Rohloff、enviolo 或 Owuru 的范围，引用矩阵中的对应 `benchmark_id`，再回查 `evidence_ids`。
