# 场景进入优先级阅读版

调研日期：2026-07-15

## 1. 文件定位

本文件是 `02_matrices/ecvt_mgu_scenario_matrix.csv` 和 `02_matrices/scenario_substitutability_matrix.csv` 的阅读版。它用于把场景价值、替代压力和进入优先级讲清楚，但不替代矩阵；所有确定性判断必须回查矩阵行里的 `evidence_ids`。

这不是最终产品路线图，也不是首发市场承诺。当前阶段的正确用途是：决定哪些场景最值得优先验证，哪些场景只能作为对照或后续机会。

## 2. 当前分层判断

| 分层 | 场景 | 当前角色 | 为什么 | 必须先证明 | 证据入口 |
| --- | --- | --- | --- | --- | --- |
| 第一优先验证 | 高端 SUV / trekking / all-road commuter | 综合价值强，适合验证 premium integrated low-maintenance 价值 | 低维护、目标踏频、长距离混合路况、轻越野、载物、后轮简化、内置速度传感和整车诊断能形成完整高级体验 | 效率、热、寿命、噪声口径、目标踏频接受度、售后模块化和成本溢价 | `ecvt_mgu_scenario_matrix.csv` 高端 SUV / trekking 行；`scenario_substitutability_matrix.csv` Premium SUV / trekking 行；`V001;V004;V009;V020;V022;V025;V032;F001;F004;F020;F022;F026;F027;F041;F044;F046;F047;F048` |
| 第一优先验证 | Cargo / family utility / heavy-load daily use | 强痛点场景，适合验证重载停启、低技能用户、倒车助力和 TCO 价值 | 满载起步、坡道、频繁停启、家庭用户误操作、低维护和安全功能都集中在同一场景 | 高载低速效率、连续爬坡热衰减、冲击寿命、倒车/驻车协同、故障降级和换件成本 | `ecvt_mgu_scenario_matrix.csv` Cargo / family utility 行；`scenario_substitutability_matrix.csv` Cargo / family utility 行；`V001;V004;V009;V010;V011;V012;V032;F020;F021;F022;F023;F026;F029;F041;F045;F047;F048` |
| 战略验证场 | High-end eMTB / gravity / technical climbing | 强痛点、高战略价值、高验证门槛 | 后拨/飞轮/链条外露、后轮结构自由、簧下质量、技术爬坡、负载换挡和旗舰技术展示都是真价值点 | 重量、效率、NVH、冲击耐久、泥水清洗可靠性、手动/虚拟档可信度和骑手信任 | `ecvt_mgu_scenario_matrix.csv` High-end eMTB 行；`scenario_substitutability_matrix.csv` High-end eMTB 行；`V001;V003;V004;V008;V018;V021;V027;V028;V029;V032;F016;F018;F026;F031;F032;F035;F036;F043;F044;F045;F046;F047;F048` |
| 强利基 / 可靠性对照 | High-end touring / adventure / expedition | 需求真实，但 Rohloff/Pinion/gearbox 替代强 | 长距离、偏远维护、宽范围、可靠和低维护诉求真实；e-CVT MGU 需要增加自动踏频和整车诊断价值 | 长途效率、断电/低电可骑、现场维修、软件故障降级和全球售后 | `ecvt_mgu_scenario_matrix.csv` High-end touring / adventure 行；`scenario_substitutability_matrix.csv` High-end touring / adventure 行；`V001;V010;V011;V013;V014;V025;F004;F022;F023;F025;F035` |
| 高端小众 / 体验参考 | Premium urban commuter / connected city bike | UX 价值强，但可替代性很高 | 目标踏频、自动连续变比、防盗连接和低维护有价值；但 enviolo、Owuru/Decathlon、hub CVT/Automatic 已经覆盖很多城市需求 | 整车成本、低速顺滑、停车搬运重量、雨污耐久、用户是否愿意支付显著溢价 | `ecvt_mgu_scenario_matrix.csv` Premium urban commuter 行；`scenario_substitutability_matrix.csv` Urban commuter 行；`V004;V005;V007;V009;V031;F013;F016;F020;F026;F039;F040;F041;F042` |
| 潜在 TCO 场景 | Fleet / delivery / shared premium utility | 只有维护和停工时间能量化降低时才成立 | 运营方关注停工、误用、被盗、诊断和维护频次，e-CVT MGU 可能把传动维护与远程诊断打包 | TCO 数据、模块更换时间、远程诊断接口、滥用耐久、低成本维修网络和批量采购价格 | `ecvt_mgu_scenario_matrix.csv` Fleet / delivery 行；`V004;V005;V009;V012;F027;F041;F042` |
| 高端小众 UX 场景 | Accessible mobility / older riders / low-skill riders | 目标踏频价值明确，但 hub CVT/Automatic 替代很强 | 用户不想学换挡，重视起步、稳定踏频、安全和少维护；成本可能超过多数整车价格带 | 低速控制可预测、安全锁止、防误操作、推行重量和价格接受度 | `ecvt_mgu_scenario_matrix.csv` Accessible mobility 行；`V004;V007;V009;V031;F016;F020;F026;F039;F041` |
| 不建议早期主攻 | Lightweight eMTB / eGravel / sporty commuter | 价值成立条件弱 | 该细分优先轻、自然、低阻、运动控制和简洁，e-CVT MGU 的重量、效率、体积和复杂度成本很难被覆盖 | 接近轻量中置系统的整机重量、低无电阻力、窄 Q-factor、运动手动控制和紧凑外观 | `ecvt_mgu_scenario_matrix.csv` Lightweight eMTB / eGravel 行；`scenario_substitutability_matrix.csv` Lightweight eMTB / eGravel 行；`V002;V006;V008;F015;F018` |

## 3. 推荐阅读顺序

1. 先读本文件，快速理解场景分层。
2. 再读 `03_analysis/substitute_solution_segment_note.md`，确认每个场景里谁是最强替代。
3. 需要做测试或访谈时，读 `03_analysis/ecvt_mgu_validation_plan.md` 和 `02_matrices/ecvt_mgu_validation_task_matrix.csv`。
4. 针对单场景展开时，再读 `03_analysis/scenario_hypothesis_emtb.md`、`03_analysis/scenario_hypothesis_cargo_family.md` 和 `03_analysis/scenario_hypothesis_suv_trekking.md`。

## 4. 使用边界

- 不能把“第一优先验证”写成“确定首发市场”；它只代表当前最值得补证。
- 不能把 High-end eMTB 写成弱场景；它是高战略价值、高验证门槛场景。
- 不能把 Premium urban commuter 写成无价值；它的 UX 价值存在，但替代方案成熟，商业增量必须单独证明。
- 不能把 Lightweight eMTB/eGravel 完全排除；当前判断只是“不适合早期主攻”，除非重量和低阻有突破。

## 5. 下一步衔接

本文件对应的下一步不是继续写更多摘要，而是把场景判断转成证据任务：

- 高端 SUV / trekking：验证 premium integrated low-maintenance 是否能形成真实溢价。
- Cargo / family utility：验证高载低速、频繁停启、倒车/锁止和 TCO。
- High-end eMTB：验证重量、效率、NVH、冲击耐久和骑手控制信任。
- Urban / accessible / fleet：用用户访谈和运营数据判断是否存在足够高的支付意愿或 TCO 改善。

上述任务应回到 `02_matrices/ecvt_mgu_validation_task_matrix.csv` 维护，不在本文扩写成新的事实。
