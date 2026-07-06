# L1 直接 MGU 深挖 v2

调研日期：2026-07-05  
证据口径：使用 `verified_sources.csv`、`verified_sources_v6_addendum.csv` 和 `ecvt_source_findings.csv` 中已检查内容。Avinox Tech Details 图卡作为 Avinox 量产方向/准量产产品定义信息使用，可进入功能和参数目标对标；内部机制、测试基准和最终公开 datasheet 仍需官方闭环。

## 1. 已核验直接对象

### Pinion E-Drive MGU

Pinion 是当前最强的量产参照。官方页面明确把产品定义为 Motor.Gearbox.Unit，即电机和 gearbox 在一个单元内（V001）。

已核验规格：

| 型号 | 档位 | 速比范围 | 重量 | Q-factor | 峰值功率 | 扭矩口径 |
| --- | ---: | ---: | ---: | ---: | ---: | --- |
| E1.9 | 9 | 568% | ~4000 g | 174 mm | 600/800 W | 85 Nm competitive torque |
| E1.12 | 12 | 600% | ~4100 g | 174 mm | 600/800 W | 85 Nm competitive torque |

Pinion 还强调 10,000 km oil-change 维护间隔、封闭壳体、Auto.Shift、Start.Select/Pre.Select、FIT app/display 生态和负载下换挡（V001）。

研发含义：

- Pinion 给出了“有级 MGU”可量产的完整参照。
- 它的核心壁垒不是单个参数，而是 gearbox、电子换挡、系统集成、维护模型和 OEM 落地。
- 自研方案如果走有级 gearbox 路线，Pinion 是必须逐项拆解的主参照。

### Gobao X-system

Gobao 官方 X-system 页面已能支撑直接 MGU 判断：页面写明 motor and transmission are combined into a single unit，并使用 automatic continuously variable transmission，支持自动换挡与手动控制（V004）。

已核验规格：

| 官方页面模型块 | 目标 | 扭矩 | 功率 | 重量 | 速比范围 | 速度 | 壳体 |
| --- | --- | ---: | ---: | ---: | ---: | --- | --- |
| Urban & Trekking | 城市/旅行 | 120 Nm | 1200 W | 3.85 kg | 400% | 25/45 km/h | Mg |
| MTB & Cargo | 山地/货运 | 150 Nm | 1500 W | 3.85 kg | 500% | 25/45 km/h | Mg |

研发含义：

- Gobao 是最接近“我们要做什么”的中国供应链压力源。
- 与 Pinion 不同，Gobao 展示的是 eCVT/连续变速叙事，而不是固定档位 gearbox。
- 当前仍需把官方模型块和媒体所称 X1/X1P 命名一一对应，不能凭猜测合并。

### Avinox MG Concept

Avinox MG Concept 已经从“需要补证的媒体/规格缺口状态”升级为“量产方向/准量产产品定义清晰、官方机制仍待闭环”的核心 L1 对象。The Verge 报道其是 MGU/eCVT 方向，目标 2027，并报道 Canyon、Commencal、Forbidden、Mondraker 展示了 prototype eMTB（V003）；Bikerumor / Avinox booth Tech Details 六图进一步给出可直接用于对标的产品目标（V032, F043-F048）。

已核验边界：

- Avinox 官方当前 Drive Unit 页面只验证 M2S/M2/M1，不验证 MG Concept（V002）。
- M2S 的 130/150 Nm、2.59 kg 和条件性 1500 W 只能作为 Avinox 当前生产电机 benchmark，不能套到 MG Concept（V002）。
- Tech Details 图卡可作为 MG Concept 量产方向/准量产目标信息：`>1.1 kg` reduced unsprung mass、150 kg heavier riders、45 dB、300 Nm shift under load、<0.1 s shifting window、100%-520% ratio、1-13 virtual gears、3 times more durable、traditional drivetrain 10% less efficient、mechanical motor lock、electric reverse assist、built-in speed sensor、downhill charging graphic 和 eMTB/eTrekking/eSUV/eGravel/eCity/eCargo 六平台覆盖（V032, F043-F048）。
- 仍未闭环的是内部变比机构、扭矩测量位置、效率/热/寿命测试口径、charging 传动路径、断电降级和最终上市 datasheet。

研发含义：

- Avinox MG Concept 已经可以作为 eCVT/连续变比 MGU 的量产方向信息、准量产规格目标和系统功能目标使用。
- 后续必须找官方展会资料、press kit、专利和合作整车页面，用来解释机制、测试基准和量产边界，而不是继续等待“是否值得关注”的确认。

## 2. 仍未核验的 L1 候选

| 候选 | 当前状态 | 处理 |
| --- | --- | --- |
| Valeo Cyclee / Smart e-Bike System | 未拿到可用官方内容 | 保留为历史候选，不进入规格对比 |
| Revonte ONE | 未拿到官方/归档内容 | 保留为历史 eCVT/integrated-drive 线索 |
| Owuru | 未验证物理边界 | 暂列 L1/L2 边界候选 |

## 3. L1 技术路线判断

当前 L1 分成两条清晰路线：

- 有级 MGU：Pinion 已量产，参数和维护模型清晰，优先做深度拆解。
- eCVT MGU：Gobao 已有官方页面，Avinox 已有量产方向/准量产 Tech Details 图卡；体验和系统功能潜力很大，但效率、热、寿命、内部机制和服务策略需要验证。

下一步最值得做的是 Pinion vs Gobao 的架构对照：有级 gearbox 与 eCVT 分别在效率、重量、换挡体验、控制复杂度、可靠性、售后成本上的系统取舍。
