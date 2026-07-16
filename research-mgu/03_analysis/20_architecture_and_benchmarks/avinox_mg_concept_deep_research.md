# Avinox MG Concept 深度研究

研究日期：2026-07-05  
对象边界：Avinox MG Concept / Eurobike 2026 展示的准量产产品定义；不是 Avinox M1/M2/M2S 量产 Drive Unit。  
证据口径：优先使用 Bikerumor 文章及其 Tech Details 图片；辅以 The Verge、Transition Velo、Velobiz 等线上报道；Avinox、Gobao、Pinion 官方页仅作为边界和参照，不把量产电机参数套用到 MG Concept。Tech Details 图卡值按 Avinox 量产方向/准量产目标使用，可进入对标和验证；证据上仍标注为 booth/OCR，最终公开 datasheet、测试基准和内部机制待闭环。
修订说明：2026-07-05 补入用户提供的 Bikerumor `Tech Details` 六张高清截图，并按 01-06 逐图核读；上一版对这些图卡读取不足，本版以高清图为准。

## 0. 结论先行

Avinox MG Concept 不是普通的“新电机壳体”，而是 Avinox 对下一代 MGU 路线给出的准量产产品定义：中置电机、内部变比机构、自动/手动/虚拟档位控制、单速链条或皮带外传动，以及围绕踏频目标、扭矩平滑和整车场景的软件控制。它真正重要的地方，不是某个单项数字，而是把 e-bike 高端传动架构从“电机 + 后拨/飞轮/花鼓变速”推向“电机 + 内置变比 + 软件定义传动”的供应链竞争。

当前最稳妥的技术定义应是：

> Avinox MG Concept 是一个公开展示且产品定义已相当完整的 motor + gearbox / continuously-variable-ratio 准量产 MGU。Tech Details 图卡值应作为 Avinox 量产方向和内部对标目标处理；证据上仍保留 booth/OCR 边界，Avinox 尚未用完整官方技术资料确认其内部机械拓扑，因此不能把它写成已经定型的某一种 CVT 机构。

这条路线对我们的 MGU 预研有三层意义：

1. 市场层面：Avinox 已经把 eMTB、eSUV、trekking、gravel、urban 等多品类纳入 MGU 叙事，并通过 Canyon、Commencal、Forbidden、Mondraker、Megamo 等高端/运动品牌形成 OEM 心理锚点。
2. 技术层面：核心体验不再是“换挡更快”，而是“用户不必管理档位，系统用踏频目标、扭矩平滑、虚拟档位和内部变比管理传动，同时减少外露传动维护”。
3. 竞争层面：Gobao X-system 已经有官方规格页，Pinion MGU 已经量产。Avinox 的威胁在于它可能把高功率密度电机、软件、显示/电池生态和 OEM 号召力打包进入 MGU，而不是单独靠机械变速取胜。

## 1. 证据分层

| ID | 类型 | 来源 | 本文使用方式 |
| --- | --- | --- | --- |
| S1 | 媒体 + 现场图片 | Bikerumor: Avinox MG Concept at Eurobike 2026 | 主证据。正文给出 Avinox 未提供完整 press kit、未完全回答技术问题的边界；图片提供展台图卡和样机外观证据。 |
| S1-I | 图片证据 | 本地下载的 Bikerumor 图片与用户补充的 Tech Details 高清截图：`research-mgu/03_analysis/90_source_materials/avinox_mg_concept_source_images/` | 读取展台文字、Tech Details 六图、虚拟齿比条、样机接口、整车样机形态。 |
| S2 | 媒体 | The Verge: Avinox MG Concept and Gobao MGU/eCVT | 用于判断 2027 市场信号、合作 OEM、Gobao 对照和“MGU/eCVT 正在成为 Eurobike 热点”的外部叙事。 |
| S3 | 媒体 | Transition Velo: Avinox MG Concept | 用于补充 0.1 s 换挡、重载/静止换挡、目标踏频、AI+、虚拟档位、约 520% 范围、合作品牌等描述。媒体也明确指出重量/功率/扭矩等深层规格缺失。 |
| S4 | 行业媒体 | Velobiz: Avinox stellt neuen MG Concept Motor vor | 用于补充单速链条/皮带、无后拨/多级飞轮、150 kg 以上总移动质量自然骑感、防盗锁止等发布叙事。 |
| O1 | 官方 | Avinox Drive Unit 页面 | 只作为 Avinox 当前量产 M1/M2/M2S 能力参照；不能推导 MG Concept 最终重量、功率或扭矩。 |
| O2 | 官方 | Gobao X-system 页面 | 作为 eCVT MGU 量产化压力参照：官方确认 motor + transmission integrated，自动连续变速，120/150 Nm、1200/1500 W、3.85 kg、400/500% 范围等。 |
| O3 | 官方 | Pinion E-Drive MGU 页面 | 作为已量产有级 MGU 参照：E1.9/E1.12、568/600% 范围、约 4.0/4.1 kg、10,000 km 维护周期等。 |

## 2. Bikerumor 文章和图片的关键内容

### 2.1 正文边界和 Tech Details 图卡要一起读

Bikerumor 的价值在于：虽然它不是正式公开 datasheet，但它把 Tech Details 产品定义和证据边界同时写出来，使这些图卡值可以被当作 Avinox 量产方向信息使用。文章明确表达了几个约束：

- Avinox 当时没有给出完整 press kit，记者也没有拿到全部技术问题答案。
- 文章把 MG Concept 描述成“combined motor and gearbox drivetrain”，但也提醒 Avinox 没有完全确认内部是否就是 CVT。
- 现场给出的 520% 范围、0.1 s 换挡、重载换挡、约 45 dB 等，应直接视为 Avinox 量产方向/准量产目标和内部对标输入；测试基准、测量位置和最终公开 datasheet 仍需官方闭环。

这意味着本文后续会把 MG Concept 写成“量产方向/准量产 eCVT/连续变比 MGU 产品定义”，而不是远期概念展示；只是不会把它写成“已经确认某种内部机械结构的最终上市产品”。

### 2.2 图片证据 1：样机不是普通中置电机

本地图片 `01_*driveside-mystery-all-in-one-box.jpg`、`02_*teaser.jpg`、`04_IMG_5130-scaled.jpeg` 能看出：

- 外壳上有清晰的 `AVINOX MG Concept` 标识。
- 样机有一个较大的圆形电机/盖板区域，同时右侧/后侧有独立凸出的壳体体积，外观上明显比普通中置电机更像“电机 + 传动机构”的组合体。
- 顶部有外露线束和插头，说明展品更接近工程样件/展示样件，而不是完整封闭的量产外观。
- 图片只能支持“集成式 MGU 样机外观”判断，不能由外观反推内部是行星齿轮、摩擦 CVT、双电机功率分流或其他具体机构。

对研发的启发：MGU 的外形不是附属问题。即使 Avinox 的量产版本会重做壳体，当前样机已经显示出 BB 区域、下管、摇臂、链线、线束出口、散热面和服务入口会被重新定义。

### 2.3 Tech Details 01：Natural Ride Feel 不是泛泛骑感，而是扭矩响应控制

用户补充高清图 `tech_details_user_full/01_natural_ride_feel.png` 是本文必须补充的关键证据。图中可读信息包括：

- `Reduced Unsprung Mass`，并标注 `>1.1 kg`。
- `Support Heavier Riders`，并标注 `150 kg`。
- `Ultra-Quiet Motor Operation`，并标注 `45 dB`。
- 曲线纵轴为 `TORQUE`，横轴为 `TIME`。
- 三条曲线分别是 `RIDER'S TORQUE`、`ASSIST TORQUE COMPETITOR`、`ASSIST TORQUE AVINOX`。
- Avinox 曲线旁标注 `FAST RESPONSE WITH NO OVERSHOOT`。
- 图上有两段 `ASSIST REMAIN`，以及 `PEDAL STOPS` 到 `ASSIST STOPS` 之间的 `OVERRUN` 区间。

这张图把 “natural ride feel” 具体化为控制问题：Avinox 想表达的是电机助力扭矩对骑手输入扭矩的平滑、快速且不过冲的响应，而不是单纯“功率大”或“声音小”。图中 Avinox 蓝线比竞争对手虚线更平顺，且在骑手扭矩波动时保持更连续的助力输出；踏停后还显示可控的 overrun 助力尾段。

研发含义：

- 该系统价值不只是内置变速，而是电机扭矩控制、变比控制和骑手踏频/扭矩意图识别的联合控制。
- `>1.1 kg` unsprung mass reduction 暗示去掉后拨/多级飞轮等后轮外露传动件后，后轮非簧载质量下降。这对 eMTB 后悬架响应是非常强的卖点，但必须追问对比基准和是否包含飞轮、后拨、线管、张紧器等。
- `150 kg` 更重骑手支持与 `45 dB` 噪声是 Tech Details 图卡值，可作为量产方向/准量产目标处理；后续需要追问测试口径和量产认证边界。

### 2.4 Tech Details 02：Seamless Shifting 明确给出三类换挡能力

用户补充高清图 `tech_details_user_full/02_seamless_shifting.png` 可读信息包括：

- `Assist-off Gear Shift`
- `Stationary shifting`
- `Shift Under Load`，并标注 `300 Nm`
- 传统传动图中，每次换挡都有明显扭矩下陷，且标注 `>1 s SHIFTING WINDOW`。
- Avinox MG 图中标注 `CONSTANT TORQUE OUTPUT`，换挡窗口标注 `<0.1 s SHIFTING WINDOW`。

这张图比原文摘要更重要，因为它明确把 MG Concept 的无缝换挡拆成三项场景能力：

1. 助力关闭或低助力状态下仍可换挡。
2. 静止状态可换挡，解决坡道停车、满载起步、技术路段重新起步的痛点。
3. 负载下换挡，图卡用 `300 Nm` 做传播值。

研发含义：

- 传统 derailleur 路线的痛点被 Avinox 定义为“换挡窗口长、扭矩中断明显”；MG Concept 的目标是用电机和内部变比协同把换挡窗口压到 `<0.1 s`，并维持输出扭矩连续。
- `300 Nm` 必须追问测量位置：曲柄输入、MGU 输出轴、链轮、后轮等效扭矩还是内部机构承载。这个数字不能直接与中置电机额定扭矩混用。
- 静止换挡和负载换挡是 cargo/family/SUV 场景比 eMTB 更容易商业化的功能证据。

### 2.5 Tech Details 03：Fully Customizable 证明“连续变比 + 虚拟档位”叙事

用户补充高清图 `tech_details_user_full/03_fully_customizable.png` 可读信息包括：

- `Automatic Shifting`
- `Manual shifting`
- `Multi-Gear shifting`
- `AVINOX MG DRIVETRAIN`
- `INFINITELY VARIABLE GEAR RATIO`
- `Configurable Gear Profiles`
- 齿比条从 `100% GEAR RATIO` 到 `520% GEAR RATIO`
- 下方显示 1-13 的虚拟档位刻度。

这张图说明 Avinox 想表达的不是传统“13 速实体齿轮箱”，而是连续变比底层能力叠加可配置虚拟档位。换句话说，Avinox 同时想解决两类用户：

- 不想换挡的用户：系统按目标踏频或自动策略连续调整。
- 仍想要档位感的用户：通过 configurable gear profiles 获得类似 4、13 或其他档位数的手感。

这对 MGU 产品定义很关键。真正的差异化不只是“内部有无级变速”，而是要提供一个可解释、可训练、可调校的传动行为层。用户买到的不是机构本身，而是“我踩什么踏频、车如何自动选比、在技术路段是否可预测”的体验。

### 2.6 Tech Details 04：Maintenance-Free 图卡包含耐久、效率与工具链替代叙事

用户补充高清图 `tech_details_user_full/04_maintenance_free.png` 可读信息包括：

- 左侧 `LEGACY TOOLKIT`：传统后拨、飞轮、线管和工具被红叉否定。
- 右侧 `AVINOX MG DRIVETRAIN`：单速外传动示意，标注 `3 times more durable`。
- 右侧 `TRADITIONAL DRIVETRAIN`：多级飞轮与偏斜链线示意，标注 `10% less efficient`。
- 底部标题 `04 MAINTENANCE-FREE`。

这张图的技术含义非常具体：Avinox 不是只说“少维护”，而是在把传统 derailleur/cassette 工具链、斜链线效率损失、传动件寿命一起打包为痛点。MG Concept 的答案是单速外传动 + 内部变比。

但这里必须保留边界：

- `maintenance-free` 是 Tech Details 产品叙事，可作为 Avinox 量产方向处理，但不能等同于整车无需维护。内部变比机构、轴承、密封、油脂/油液、皮带/链条、张紧机构仍需量产说明。
- `3 times more durable` 和 `10% less efficient` 必须追问基准对象、测试工况、链条/飞轮规格、污染条件、载荷、里程、功率、效率定义。
- 如果 Avinox 不能解释这些数字，专业媒体和 OEM 会把它们视为营销数字，而非工程证据。

对我们而言，这恰好是机会：如果自研方案能拿出透明的效率地图、链线磨耗测试、泥水耐久、冲击载荷、换挡扭矩谱和可维护策略，就能在 Avinox 还未公开数据前建立可信度。

### 2.7 Tech Details 05：Next-Gen Functions 暴露出系统级功能野心

用户补充高清图 `tech_details_user_full/05_next_gen_functions.png` 可读信息包括：

- `Mechanical Motor Lock`
- `Electric Reverse Assist`
- `Built-in Speed Sensor`
- 下坡图示中有 `CHARGING`、闪电符号和电池电量增加图标。

这张图是此前最容易漏掉、但对系统定义非常关键的一张。它说明 Avinox MG Concept 不只想替代变速器，还想把防盗、倒车/推车、速度传感、下坡能量回收或充电叙事纳入 MGU 系统。

需要特别谨慎的是 `CHARGING`。如果它暗示下坡回充/再生制动，那么中置 MGU 必须解释动力如何从后轮经链条/皮带反拖到电机，普通自行车飞轮/单向离合会不会阻断回充，制动控制如何实现，以及法规和安全边界如何处理。该图可作为 Avinox 量产方向/准量产功能方向处理，但不能直接等同于最终量产系统一定具备可用再生制动。

研发含义：

- `Mechanical Motor Lock` 可能是防盗/驻车锁止卖点，也可能与内部机构锁止有关，必须追问断电锁止、拖车、维修、失效解锁策略。
- `Electric Reverse Assist` 对 eCargo、family utility、重载 SUV 很有价值，但对 eMTB 价值有限；这进一步说明 MG Concept 不是只为 eMTB halo，而是想做全平台系统。
- `Built-in Speed Sensor` 如果成立，可减少外部磁铁/线束/传感器安装复杂度，是 OEM 装配和售后友好点。

### 2.8 Tech Details 06：Made For All Bike Platforms 明确六类目标平台

用户补充高清图 `tech_details_user_full/06_made_for_all_bike_platforms.png` 明确列出：

- `eMTB`
- `eTREKKING`
- `eSUV`
- `eGRAVEL`
- `eCITY`
- `eCARGO`

这张图的价值是纠正“Avinox MG Concept 只是 eMTB 技术秀”的误读。Avinox 的展台叙事已经把 MG Concept 定义为跨平台 MGU，而不是单一山地车零件。eMTB 负责制造技术势能，eCargo/eCity/eSUV/trekking 才可能承担规模化和低维护商业逻辑。

### 2.9 图片证据：整车样机说明 OEM 适配已经开始

图片 `06_*Commencal-Meta-Power-SX-eMTB_teaser.jpg` 与 `07_IMG_5129-scaled.jpeg` 显示 Commencal Meta Power SX prototype 装配了 MG Concept。结合线上报道，Avinox 不是单独展示一个台架零件，而是在多家整车品牌的样车语境下展示。

这里的判断边界是：

- 可以确认 MG Concept 已进入整车样车展示层面。
- 可以把 Canyon、Commencal、Forbidden、Mondraker、Megamo 视为媒体报道中的合作/展示信号。
- 不能确认这些品牌都会量产采用，也不能确认 2027 首发名单。

## 3. 外部报道补充出的产品叙事

### 3.1 The Verge：MGU/eCVT 正在从概念变成赛道

The Verge 把 Avinox MG Concept 和 Gobao X-series 放在同一篇文章中讨论，核心信号是：Eurobike 2026 上，motor gearbox unit 与 eCVT 不再是孤立的工程兴趣点，而是供应链进入“下一代电助力传动”的公开赛道。

The Verge 报道的重点包括：

- Avinox MG Concept 面向 2027 发布/量产窗口，但细节更少。
- Canyon、Commencal、Forbidden、Mondraker 等展示了搭载 Avinox MG Concept 的原型车。
- Gobao X1/X1P 被描述为更接近量产的 eCVT MGU，报道引用了 120 Nm/1200 W 与 150 Nm/1500 W 级别。
- 文章把 Avinox、Gobao 与 Pinion MGU 放在同一竞争语境下，说明固定齿轮 MGU 与 eCVT MGU 正在被媒体和行业共同比较。

这给我们的判断是：Avinox MG Concept 的价值不在于它是否最先量产，而在于它把“高端整车厂是否要押注 MGU/eCVT”这个问题提前摆到台面上。

### 3.2 Transition Velo：强调目标踏频、AI+ 和虚拟档位

Transition Velo 的报道与 Bikerumor 图卡互相印证了几个体验点：

- 0.1 s 以内换挡。
- 重踩负载下换挡和静止换挡。
- 目标踏频自动模式。
- AI+ 自动模式。
- 模拟/虚拟档位。
- 约 520% 传动范围。
- 与 Canyon、Commencal、Forbidden、Mondraker、Megamo 等品牌联动。

但它也很重要地指出，功率、扭矩、重量等关键规格没有公开。这说明当前应把 MG Concept 做功能目标和系统架构对标，并按 Avinox 量产方向信息处理；完整 datasheet 对标仍需等官方公开资料闭环。

Transition Velo 还提到对内部结构的媒体推测，例如可能是行星齿轮与多个电机/执行机构组合。本文不把这类推测作为事实，只把它列入后续专利和拆解追证方向。

### 3.3 Velobiz：强化低维护、无后拨和重载自然骑感

Velobiz 的行业报道强化了 Avinox 对整车厂最有吸引力的几个叙事：

- 使用单速链条或皮带时，不再需要后拨和多级飞轮。
- 内部变速系统降低维护压力。
- 可覆盖 eMTB、eTrekking、eSUV、gravel 等多个平台。
- 面对超过 150 kg 的总移动质量时仍要保持自然骑感。
- 即使无电，也可通过电机锁止提供防盗能力。

这些点从研发角度看不是“附加功能”，而是 MGU 商业化成败的真实战场。MGU 如果只解决变速，未必比外置传动有足够价值；如果同时解决重载起步、低维护、整车防盗、链线、售后和软件体验，才有可能让 OEM 愿意改变整车架构。

## 4. 技术架构判断

### 4.1 可以确定的架构方向

基于 S1-S4，可以较高置信度判断：

- MG Concept 是中置区域的 motor + gearbox / motor + variable-ratio drivetrain 集成方案。
- 外部传动目标是简化为单速链条或皮带，减少后拨和多级飞轮。
- 底层变比能力至少被 Avinox 展台表达为 100%-520% 的连续/可配置范围。
- 用户界面会同时保留自动模式、手动模式和多档虚拟模式。
- 系统卖点围绕扭矩平滑、无缝换挡、重载/静止变比、目标踏频、低维护、机械锁止、倒车助力、内置速度传感和跨车型平台。

### 4.2 不能确定的内部实现

当前不能确认：

- 是真正机械 CVT、功率分流 eCVT、行星齿轮 + 电机调速、电子离合多速 gearbox，还是其他组合。
- 是否存在锁止直驱档、效率最高档、断电默认档位或机械降级模式。
- 传动效率地图、热限制、连续爬坡能力和低温/泥水环境表现。
- 最终重量、尺寸、Q-factor、链线、安装接口、线束接口、控制器集成程度。
- 最终量产噪声、寿命、保养周期和售后更换策略。
- 下坡 `CHARGING` 是否代表真实再生制动/回充，还是展示层面的能量管理叙事。
- 机械锁止、电动倒车助力、内置速度传感的具体硬件实现和法规边界。

### 4.3 最值得追问的工程问题

1. 效率：520% 范围内各变比效率如何？目标踏频模式是否牺牲续航？传统传动“10% less efficient”的对比基准是什么？
2. 热：重载低速爬坡时，电机热和变比机构热如何叠加？是否会出现降额后变比体验变差？
3. 寿命：展台的“3 times more durable”对应哪个零件寿命？链条、皮带、内部齿轮、轴承、离合器还是整车传动系统？
4. 断电：无电时是否可踩？固定在哪个传动比？能否牵车、倒车、维修支架转动？
5. 控制：目标踏频、AI+、虚拟档位之间如何切换？技术爬坡时系统是否会在不合适的瞬间变比？
6. 安全：300 Nm 级负载换挡如果成立，扭矩估算点在哪里？是曲柄输入、输出轴、链轮还是后轮等效？
7. 服务：内部变速机构损坏时是整机更换还是模块更换？OEM/经销商能拿到什么诊断能力？
8. 回充：下坡 `CHARGING` 如何穿过单向飞轮/链条/皮带实现？是否需要特定后轮结构或制动协同？
9. 锁止：`Mechanical Motor Lock` 是锁电机、锁输出轴、锁曲柄还是锁整车传动？断电和故障时如何解锁？
10. 传感：`Built-in Speed Sensor` 是否取消外置磁铁？速度测量来自电机、输出轴、后轮还是融合估算？

## 5. 与 Gobao、Pinion 的位置关系

### 5.1 Avinox MG Concept vs Gobao X-system

Gobao X-system 官方页已经确认 motor and transmission combined into one unit，并给出两个明确规格块：

- Urban & Trekking：120 Nm、1200 W、3.85 kg、400% 最大齿比范围。
- MTB & Cargo：150 Nm、1500 W、3.85 kg、500% 最大齿比范围。

相较之下，Avinox MG Concept 的 Tech Details 已经给出强产品定义，即使完整 datasheet 尚未公开，也足以作为量产方向信息使用。Avinox 的潜在优势不是“先有规格表”，而是：

- 已有 Avinox M 系列量产电机、显示、控制、App、电池生态。
- 在高端 eMTB 品牌中的可见度更强。
- DJI/Avinox 的软件、传感和系统整合能力容易被 OEM 想象成差异化来源。

Gobao 的压力在于官方规格更具体，且参数上非常接近高功率 eMTB/cargo 场景；Avinox 的压力在于必须解释 Tech Details 图卡值的测试基准、内部机制和最终量产边界。

### 5.2 Avinox MG Concept vs Pinion MGU

Pinion E-Drive MGU 已经量产，是当前最强的“有级 MGU”参照。它的优势是齿轮箱工程成熟、维护周期清晰、600% 范围和 Auto.Shift/Start.Select 等功能已经商品化。Avinox MG Concept 则更像“连续变比 + 软件定义传动”的下一代方向。

这两条路线的本质差异：

- Pinion：机械齿轮档位明确，效率和手感更容易解释，用户能理解“9/12 速 gearbox”。
- Avinox/Gobao：连续变比和目标踏频体验更强，但效率、热、控制可预测性和失效策略更难解释。

我们的预研不能只问“做有级还是无级”，而要问：目标用户愿意用多少效率和复杂度，换取多少不换挡、低维护和整车集成收益？

## 6. 场景价值排序

### 6.1 eMTB：最强展示场，不一定是最容易首发量产场

eMTB 是 Avinox 选择曝光的核心舞台，因为它最能展示高扭矩、重载换挡、无后拨、悬架空间、品牌技术力。但 eMTB 用户对重量、噪声、效率、瞬态可预测性非常敏感，任何自动变比在技术路段的“多管闲事”都会被放大。

适合的产品切入：

- 高端 halo 车型。
- 强调低速技术爬坡、静止起步、后拨损伤风险降低。
- 需要提供强手动覆盖、可锁定虚拟档位和清晰的 sport/technical 模式。

### 6.2 SUV / trekking：商业化确定性可能更高

SUV/trekking 用户更看重低维护、舒适、自动踏频、长途稳定和整车高级感。对重量与极限响应的敏感度低于 eMTB，对“无需理解变速”的接受度更高。

这是 eCVT MGU 最自然的量产扩张场景之一。

### 6.3 Cargo / family utility：重载起步价值很强

Cargo/family 用户常见痛点是满载停车再起步、坡道、低技能用户、维护成本和安全感。MGU 的静止变比、低维护、单速外传动、防盗锁止等卖点在此非常直接。

Tech Details 05 的 `Electric Reverse Assist` 对 cargo/family utility 尤其关键，因为重载车辆倒车、挪车和坡道掉头是高频痛点。`Mechanical Motor Lock` 也更接近 cargo/urban 的防盗与驻车需求，而不是单纯的 eMTB 性能卖点。

但 cargo 也会严苛考验热、连续扭矩、低速效率和维修成本。如果不能给出可验证的热稳定性，宣传价值会很快变成售后风险。

### 6.4 Urban / gravel：需要谨慎

Urban 已经有 enviolo、内变花鼓、皮带、电子换挡等大量替代路线。MGU 只有在高端通勤、车队运维、防盗、联网服务或品牌溢价足够强时才有优势。

Gravel 则受重量、Q-factor、踩踏自然感和续航影响明显，MGU 需要更轻、更安静、更低阻，才可能从概念进入真实购买。

## 7. 对我们 MGU 预研的直接启发

### 7.1 不要只跟 Avinox 比参数，要比“证据”

Avinox 目前最强的是信号和叙事，硬数据还不完整。我们的预研如果要建立可信度，应优先产出 Avinox 当前没有公开的证据：

- 效率地图：输入功率、输出功率、变比、踏频、温度。
- 热地图：低速高扭、长坡、满载、环境温度。
- NVH：不同变比、不同负载、不同外传动。
- 失效模式：断电、进水、传感器失效、执行器卡滞。
- 维护模型：链条/皮带寿命、内部油脂/油液周期、模块更换工时。
- 控制体验：扭矩平滑、目标踏频、虚拟档位、手动覆盖、技术路段锁档。
- 系统功能：机械锁止、电动倒车助力、内置速度传感、下坡回充/充电边界。

### 7.2 产品定义应从“变速器”升级为“传动行为系统”

MG Concept 的图卡提醒我们：用户感知到的是行为，不是机构。

建议把自研 MGU 的产品定义拆成四层：

1. 机械变比层：传动范围、承载、效率、寿命。
2. 电机协同层：扭矩补偿、换挡/变比瞬态、热管理。
3. 用户意图层：目标踏频、虚拟档位、运动/舒适/载重模式。
4. 服务与生态层：诊断、锁止、防盗、倒车助力、速度传感、OTA、OEM 标定、售后换件。

如果只完成第 1 层，会很容易被 Pinion/Gobao/Avinox 的成熟生态压制。

### 7.3 可差异化方向

Avinox 的潜在弱点也很清晰：

- 生态可能封闭，OEM 标定自由度有限。
- 内部结构不透明，维修可能偏整机更换。
- 真实效率、热、重量还未公开。
- 自动控制如果不可预测，会被高端 eMTB 用户抵触。

因此我们的差异化可以围绕：

- 开放 OEM 标定和诊断接口。
- 透明效率/热数据。
- 可机械降级或固定比骑行的失效策略。
- 模块化维修，而非整机报废。
- 对 cargo/family/SUV 的重载可靠性优先，而非只追 eMTB halo。

## 8. 研发验证清单

最高优先级追证：

- Avinox 官方 press kit、Eurobike 展台 PDF、白皮书或后续产品页。
- Canyon、Commencal、Forbidden、Mondraker、Megamo 的样车页面或新闻稿。
- Avinox/DJI 相关专利：连续变比、双电机功率分流、行星机构、锁止、防盗、断电降级、扭矩估计。
- 样机整车的近距离链线、张紧器、后轮齿盘、皮带适配图片。
- 真实骑行测试：踏频保持、换挡瞬态、噪声、爬坡热降额、续航影响。
- Tech Details 05 的 `CHARGING` 功能边界：是否真实回充、是否需要制动协同、是否受飞轮/单向离合限制。
- `Mechanical Motor Lock`、`Electric Reverse Assist`、`Built-in Speed Sensor` 的硬件和软件实现说明。
- `Reduced Unsprung Mass >1.1 kg`、`Support Heavier Riders 150 kg`、`Ultra-Quiet Motor Operation 45 dB` 的测试口径。

需要避免写成 final datasheet 的内容：

- MG Concept 最终重量、功率、扭矩、尺寸、Q-factor。
- 2027 必然量产或某品牌必然首发。
- 内部一定是某一种 eCVT 结构。
- 520%、0.1 s、300 Nm、45 dB 等已经是最终公开 datasheet 值。正确口径是：量产方向/准量产目标，可用于对标和验证。
- “3 times more durable”和“10% less efficient”的工程结论，除非拿到测试基准。
- `CHARGING` 一定等同于量产可用再生制动，除非 Avinox 说明传动路径和法规/安全边界。

## 9. 阶段性判断

Avinox MG Concept 是一个强烈的战略警报：高端电助力车的下一轮竞争，很可能不再只围绕“谁的中置电机更轻更猛”，而是围绕“谁能把电机、变比、外传动、软件、显示、电池和售后打成一个可被 OEM 信任的系统”。

当前最合理的研发态度是：把 Avinox MG Concept 作为 eCVT/连续变比 MGU 的量产方向参照和准量产目标参照，而不是远期概念展示。真正值得学习的是它的体验叙事、功能组合和生态打法；真正必须追证的是它还没公开的效率、热、寿命、失效、服务边界、测试基准和最终公开 datasheet。

## 10. 来源索引

- S1: Bikerumor, `Avinox MG Concept: Lightweight, Full-Power Combined eBike Motor & Gearbox Project`, https://bikerumor.com/avinox-mg-concept-combined-ebike-motor-and-gearbox-at-eurobike-2026/
- S2: The Verge, `This motor could be the future of e-bikes`, https://www.theverge.com/news/959382/avinox-mg-concept-gobao-mgu-ecvt
- S3: Transition Velo, `Avinox MG Concept: un prototype de moteur à transmission intégrée...`, https://www.transitionvelo.com/composants/moteurs-batteries/moteurs/avinox-mg-concept-un-prototype-de-moteur-a-transmission-integree-qui-promet-la-fin-des-vitesses/
- S4: Velobiz, `Avinox stellt neuen MG Concept Motor vor`, https://www.velobiz.de/news/avinox-stellt-neuen-mg-concept-motor-vor-veloQXJ0aWNsZS8zNDk2MQbiz
- O1: Avinox Drive Unit official page, https://www.avinox-ebike.com/drive-unit?from=nav&site=avinox-ebike
- O2: Gobao X-system official page, https://gobao-ebike.com/x-system-new/
- O3: Pinion E-Drive official page, https://pinion.eu/en/e-drive/

## 11. 本地图片证据

原始图片目录：`research-mgu/03_analysis/90_source_materials/avinox_mg_concept_source_images/`

重点裁剪：

- `tech_details_user_full/01_natural_ride_feel.png`：Reduced unsprung mass >1.1 kg、150 kg heavier riders、45 dB、扭矩平滑、fast response with no overshoot、assist remain/overrun。
- `tech_details_user_full/02_seamless_shifting.png`：Assist-off gear shift、stationary shifting、300 Nm shift under load、传统 >1 s shifting window、Avinox <0.1 s shifting window、constant torque output。
- `tech_details_user_full/03_fully_customizable.png`：100%-520%、1-13 虚拟档位、automatic/manual/multi-gear shifting、configurable gear profiles。
- `tech_details_user_full/04_maintenance_free.png`：Legacy toolkit、3 times more durable、traditional drivetrain 10% less efficient、单速外传动对比多级飞轮。
- `tech_details_user_full/05_next_gen_functions.png`：Mechanical motor lock、electric reverse assist、built-in speed sensor、下坡 charging 图示。
- `tech_details_user_full/06_made_for_all_bike_platforms.png`：eMTB、eTrekking、eSUV、eGravel、eCity、eCargo 六平台。
- `crops/03_bottom_ratio_panel.jpg`：100%-520% 齿比条、1-13 虚拟档位、Automatic/Manual/Multi-Gear Shifting、Configurable Gear Profiles。
- `crops/03_right_seamless_panel.jpg`：Seamless shifting 图卡。
- `crops/05_toolkit_bottom_more.jpg`：Legacy toolkit、Avinox MG drivetrain、3 times more durable、Traditional drivetrain、10% less efficient。
- `06_Avinox-MG-Concept-light-full-power-eBike-motor-and-gearbox-drivetrain-combined_inside-prototype-alloy-Commencal-Meta-Power-SX-eMTB_teaser.jpg`：Commencal Meta Power SX Prototype 展示。
- `07_IMG_5129-scaled.jpeg`：Commencal 整车样机现场图。

