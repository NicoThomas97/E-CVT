# e-CVT MGU 年轮逻辑网页内容版本 v3

生成日期：2026-07-05  
对应网页：`research-mgu/05_presentation/ecvt_mgu_product_direction.html`  
页面定位：内部产品/市场/管理沟通用离线认知页，不是正式立项结论，也不是产品投放路线图。

## 1. 本版修改重点

- 五层主正文沿用 v2，不改变场景判断、Avinox / Gobao 口径和替代方案结论。
- 新增证据 ID 点击详情：页面中所有 `Vxxx` / `Fxxx` 证据标签均可点击。
- 点击后显示该 ID 的来源标题、来源方、等级、记录文件、核验范围、支持内容和证据边界。
- 证据详情默认隐藏，不作为新的可见 section，不改变年轮主线页面外观。

## 2. 本版新增内容来源

- `01_evidence/verified_sources.csv`
- `01_evidence/verified_sources_v5_addendum.csv`
- `01_evidence/verified_sources_v6_addendum.csv`
- `01_evidence/source_findings.csv`
- `01_evidence/ecvt_source_findings.csv`

## 3. 五层完整正文

五层正文与 `ecvt_mgu_ring_layers_v2.md` 保持一致：

1. Layer 01：e-CVT 是什么。
2. Layer 02：e-CVT 可以用到哪些场景。
3. Layer 03：已有方案具体怎么解决。
4. Layer 04：这些方案还剩什么问题，e-CVT 怎么补。
5. Layer 05：e-CVT 真正适合的场景。

本版不新增未核验规格，不改变 v2 的正文判断。

## 4. 新增证据点击详情索引

### 来源条目 V

| ID | 来源/对象 | 记录文件 | 页面显示的支持内容口径 | 边界 |
| --- | --- | --- | --- | --- |
| `V001` | Pinion E-Drive MGU 官方页 | `verified_sources.csv` | Pinion 有级 gearbox MGU 的官方量产参照、档位/范围/Auto.Shift/维护叙事 | 官方营销/规格页，不是独立测试 |
| `V002` | Avinox M2S/M2/M1 官方页 | `verified_sources.csv` | Avinox 当前量产驱动单元基准 | 不验证 MG Concept 规格 |
| `V004` | Gobao X-System 官方页 | `verified_sources.csv` | motor + transmission single unit、automatic CVT、目标踏频、connected/security | 不外推未确认 X1/X1P 命名、OEM 客户和长期可靠性 |
| `V005` | Bosch eShift 官方页 | `verified_sources.csv` | 外部电子/自动换挡生态和伙伴传动系统 | 不是 MGU |
| `V006` | Bosch Performance Line CX 官方页 | `verified_sources.csv` | 普通高性能中置电机基准 | 不是换挡/MGU 产品；最大值和标准值需分开 |
| `V007` | Shimano AUTO SHIFT 官方页 | `verified_sources.csv` | cadence、torque、speed 传感自动换挡与手动覆盖 | 不是 motor-internal gearbox |
| `V008` | SRAM Eagle Powertrain 官方页 | `verified_sources.csv` | eMTB 驱动系统、Eagle Transmission、Auto Shift、Coast Shift、AXS 生态 | 不是电机内部变速 |
| `V009` | enviolo products 官方页 | `verified_sources.csv` | preferred cadence 自动 CVT、封闭低维护 hub/gearbox 路线 | 不是 mid-drive MGU |
| `V010` | Rohloff E-14 官方页 | `verified_sources.csv` | 电子内变花鼓、降扭换挡、起步档、App 设置/诊断 | 不是 MGU |
| `V011` | Rohloff SPEEDHUB 官方规格页 | `verified_sources.csv` | 14 档、526% 范围和 SPEEDHUB 技术基准 | 规格状态需查最新手册 |
| `V012` | 3X3 system 官方页 | `verified_sources.csv` | 低维护 gear hub、静止/负载换挡、链/带兼容 | 抽取页未给扭矩/速比表 |
| `V020` | Simplon KAGU :ePinion High 官方页 | `verified_sources_v5_addendum.csv` | Pinion MGU 装车到高端 SUV/trekking 的 OEM 示例 | 未提取价格和市场表现 |
| `V022` | Radfahren / ElektroRad Simplon Kagu 测试 | `verified_sources_v5_addendum.csv` | 媒体试骑对 Pinion MGU SUV/touring 车的体验评价 | 媒体单篇体验，不是实验室测试 |
| `V032` | Avinox MG Concept Tech Details 图卡 | `verified_sources_v6_addendum.csv` | Avinox 量产方向/准量产产品定义：扭矩平滑、负载/静止换挡、虚拟档、低维护、锁止/倒车/速度传感、六平台覆盖 | 展台图卡/OCR，不是最终 datasheet |

### 事实摘录 F

| ID | 对应来源 | 记录文件 | 页面显示的支持内容口径 | 边界 |
| --- | --- | --- | --- | --- |
| `F001` | `V001` | `source_findings.csv` | Pinion 电机和 gearbox 集成为一体，并电子换挡 | 用于有级 MGU 量产路线 |
| `F004` | `V001` | `source_findings.csv` | Pinion 封闭壳体和 10,000 km 油液维护间隔主张 | 服务/维护主张，不是独立耐久测试 |
| `F005` | `V002` | `source_findings.csv` | Avinox M2S/M2/M1 量产页不验证 MG Concept | 防止参数套用 |
| `F013` | `V005` | `source_findings.csv` | Bosch eShift 是电动换挡生态，不是 motor-internal gearbox | 替代路线证据 |
| `F015` | `V006` | `source_findings.csv` | Bosch CX 最大可能值和标准供货值边界 | 普通中置对照 |
| `F016` | `V007` | `source_findings.csv` | Shimano AUTO SHIFT 使用 cadence/torque/speed 并允许手动覆盖 | 外部自动换挡路线 |
| `F018` | `V008` | `source_findings.csv` | SRAM Eagle Powertrain 与 Eagle Transmission、Auto Shift、Coast Shift、AXS 生态集成 | eMTB 电子外变替代压力 |
| `F020` | `V009` | `source_findings.csv` | enviolo Automatic 目标踏频、自动换挡、低维护和皮带兼容 | hub CVT 路线 |
| `F024` | `V012` | `source_findings.csv` | 3X3 gear hub 可静止/负载换挡、低维护、链/带兼容 | 内变花鼓替代能力 |
| `F026` | `V004` | `ecvt_source_findings.csv` | Gobao preferred cadence 与 AI-based ECVT 连续平滑调节 | 长期效率/热/可靠性仍需验证 |
| `F027` | `V004` | `ecvt_source_findings.csv` | Gobao motor plus transmission、fewer parts、maintenance-free、connected service/security | 官方系统主张，非长期实测 |
| `F034` | `V028` | `ecvt_source_findings.csv` | Velobiz 报道 Avinox 无后拨/多片飞轮、低维护内部 gearbox 和多平台适配 | 行业媒体，不是最终官方规格 |
| `F041` | `V009` | `ecvt_source_findings.csv` | enviolo 自动 CVT 和封闭低维护 hub 已解决许多 city/utility 换挡痛点 | 替代压力，不是 e-CVT 独有优势 |
| `F043` | `V032` | `ecvt_source_findings.csv` | Avinox Tech Details 六图可作为量产方向/准量产定义对标 | 展台图卡/OCR |
| `F044` | `V032` | `ecvt_source_findings.csv` | Avinox torque smoothing、无 overshoot、overrun、>1.1 kg、150 kg、45 dB | 测试基础待闭环 |
| `F045` | `V032` | `ecvt_source_findings.csv` | Avinox assist-off、静止/300 Nm 负载换挡、<0.1 s、constant torque | 测量位置和测试条件未知 |
| `F046` | `V032` | `ecvt_source_findings.csv` | Avinox 100%-520% 连续变比、1-13 虚拟档、自动/手动/多档模式 | 内部机构未确认 |
| `F047` | `V032` | `ecvt_source_findings.csv` | Avinox 单速低维护外传动、3 times more durable、10% less efficient、锁止、倒车、速度传感、charging | 耐久/效率/charging 基础待验证 |
| `F048` | `V032` | `ecvt_source_findings.csv` | Avinox 覆盖 eMTB、eTrekking、eSUV、eGravel、eCity、eCargo | 平台覆盖仍需分场景验证 |

## 5. 证据边界

- 页面点击详情只是把已有证据记录显性化，不新增外部事实。
- `Vxxx` 显示来源条目的核验范围和限制；`Fxxx` 显示从来源条目中抽取的 finding、条件和置信度。
- Avinox MG Concept 仍按量产方向 / 准量产目标参照处理，不写成最终公开 datasheet 或内部机械实现已闭环。
- Gobao X-system 仍按官方 e-CVT MGU 证据处理，不外推未确认 OEM 客户、量产时间、长期可靠性或效率 map。

## 6. 本版相对 v2 的变化

- 新增证据详情浮层和点击交互。
- 将所有页面证据 ID 接入真实证据记录，避免 ID 看起来像按钮但没有实际内容。
- 保持页面默认外观不变：证据详情不作为新 section 展示，只有点击证据 ID 后出现。
