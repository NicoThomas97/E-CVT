# 网页重点内容提取：两列完整汇总

- 来源文件： `网页重点内容提取_后续与AI对比.xlsx`
- 来源工作表：`Sheet1`（`Sheet2` 和 `Sheet3` 为空表）
- 抽取范围：从第 3 行开始的数据区；保留原始段落和换行。
- 处理规则：空单元格和 `/` 占位符不作为正文信息汇总。

## 抽取统计

- F 列「我从URL中获取我认为重要的信息」：非空 28 个，其中 `/` 占位 16 个，实际正文 12 个。
- I 列「我从URL中获取我认为重要的信息」（位于「我在人工审核时的相关发现」分组下）：非空 25 个，其中 `/` 占位 24 个，实际正文 1 个。
- 实际正文条目合计：13 个。

## 完整汇总

### 1. 3.1-001 | This motor could be the future of e-bikes

- Excel 行号： 4
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 发布/展会/市场信号
- 原始 URL： https://www.theverge.com/news/959382/avinox-mg-concept-gobao-mgu-ecvt
- 用途： Avinox MG Concept 与 Gobao X-series 同场作为 eCVT MGU 市场信号；记录 Eurobike 2026、Canyon/Commencal/Forbidden/Mondraker 等合作原型、2027 方向、早期试骑转述

提取内容：

你可以设定自己偏好的踩踏踏频，无论爬坡坡度多陡，系统都会自动调节档位，让腿部始终保持固定踩踏转速；整套结构无需易损的后拨变速器，也不用笨重的多片飞轮维护。如果想要手动操控也完全可行，你能自定义任意多档位，搭配贴合路况的传动比，骑行时与路面反馈感更强。

新兴品牌 Gobao 同步发布了原理高度相似的 X 系列 MGU 产品，同样搭载电子无级变速 eCVT 技术。

### 2. 3.1-002 | Avinox MG Concept : un prototype de moteur a transmission integree qui promet la fin des vitesses

- Excel 行号： 5
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 功能/发布报道
- 原始 URL： https://www.transitionvelo.com/composants/moteurs-batteries/moteurs/avinox-mg-concept-un-prototype-de-moteur-a-transmission-integree-qui-promet-la-fin-des-vitesses/
- 用途： 介绍 MG Concept 的 motor + gearbox 集成、<0.1 s 换挡、静止/负载换挡、基于踏频自动模式、AI+ 模式、约 520% 变比范围、300 Nm 负载换挡线索

提取内容：

结果是：无需传统的多速变速箱。该系统通过简单的单速链条或皮带工作，去除多个暴露于冲击、磨损和污垢的部件。

收益有两个方面。一方面，维护工作大幅减少，因为内部单元在其使用寿命内无需维护。另一方面，自行车设计师在车架和悬挂设计上重新获得了显著的自由。

Avinox宣布换档时间不到0.1秒，实现持续动力传输和实时适应地形变化的开发。

与大多数现有系统不同，换挡可以在重载下、爬坡时进行，也可以在静止时进行。这对于技术型电动山地车骑手或需要频繁重启的城市用户来说尤其有趣。

传动齿比的控制逻辑完全可自定义配置。骑手可以单次切换一个档位，也能一次性同步调整多组齿比。
系统同时提供多种自动模式：一种基于踩踏踏频控制，另一种为「AI 智能增强模式」，可根据车速与路面行驶工况自动优化动力表现。
换句话说，Avinox 将推出一款简易无级变速（CVT）模式，类似 Owuru 电机搭载的同款方案：骑行者只需设定自己想要的踩踏踏频，变速系统会自动完成其余所有调节工作。
除此之外，系统还支持模拟多档位变速，且模拟出的传动齿比可自定义调校；这项功能对于各类竞技骑行场景而言极具实用价值。

可以把它想象成一个“行星式”齿轮箱，中轴内有两个电机协同工作：第一个电机调节齿轮比，调节踏板舒适度，第二个电机控制踏板辅助。通过这种方式，开发和马达动力不断优化，以满足骑手的需求。

品牌同时着重强调整车动态骑行表现：即便整车总负重超过 150 公斤，这套系统依旧能保持自然顺滑的踩踏手感，不会出现部分重载电机传动套件常见的形变拖沓、动力响应疲软的问题。
MG Concept 还搭载全新安全防护设计：内置防盗功能，可实时锁止电机。更亮眼的是，该防盗保护在断电状态下依旧生效（类似 Vefaa 旗下 eBikeOS 系统的现有方案）。
这套研发方向也印证了 Avinox 的产品规划：不局限于单一电机硬件，而是依托这款原型产品打造一套完整的互联智能生态系统。

如今尚存一个疑问：这套全新架构能否站稳市场，既要对抗市场沿用多年的飞轮 + 外拨链器传统组合，也要直面内置无级变速电机的先行者 Owuru，同时还要应对蓄势待发的新晋厂商（比如搭载 X1、X1P 电子无级变速系统的国宝 Gobao）。此外也不能忽视自带内置变速箱的电机阵营，包括 Pinion MGU、法雷奥 Cyclee、Intradrive、Effigear 等品牌。

可惜目前暂无更多详细技术参数（重量、额定功率、扭矩等）对外披露。现阶段仅能获取以下信息：该电机运行噪音水平与 M2S 电机持平；最大 300 牛米扭矩下，可无需松脚持续踩踏完成变速；车辆静止时也能够切换传动齿比。

### 3. 3.1-004 | Avinox MG Concept: Lightweight, Full-Power Combined eBike Motor & Gearbox Project

- Excel 行号： 7
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 展会图卡/功能图卡
- 原始 URL： https://bikerumor.com/avinox-mg-concept-combined-ebike-motor-and-gearbox-at-eurobike-2026/
- 用途： 展台图卡与图片证据；本地已保存并 OCR，作为准量产方向/功能目标，不等于最终规格表

提取内容：

自然柔顺的踩踏手感，是市面上高端、精致电助力驱动系统的标志性特质。

从 Avinox MG Concept 的资料示意图可以看出，相比竞品，它能更好地平顺处理骑手的踩踏输入扭矩。

MG Concept 拥有更快的变速速度，换挡手感比传统拨链器传动系统更顺滑、无割裂感。

官方说明骑手可自定义想要的档位数量，例如 4 档、13 档等方案，这些档位可均匀划分覆盖 520% 的超大变速区间。

品牌同时表示，该电机变速箱无需配备易损耗的专用内置传动皮带，由此判断它采用了区别于传统 CVT 的全新结构方案。

将变速机构与踩踏助力系统集成于单一总成，可实现多项高阶智能功能：机械式安全锁止机构、电助力倒车档（方便倒车推行），以及内置智能转速与扭矩传感器。

Avinox 表示这套系统可在下坡工况下实现能量回收，以此延长电池续航，该能量回收功能大概率依托再生制动实现。

运行噪音同为 45 分贝，表现与 Avinox M2S、M2 两款电机持平，由此推断其动力输出水平相近。

即便电机不输出助力，变速箱依旧可以完成换挡操作

最大 300 牛米负载踩踏状态下可直接换挡；车辆静止、未踩踏时也能切换齿比

额定承重适配总重最高 150 千克（330 磅）的骑行载荷

### 4. 3.1-005 | New Avinox MG gearbox motor prototype: is this the end of the classic drivetrain?

- Excel 行号： 8
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 展会/首骑/媒体深度
- 原始 URL： https://ebike-mtb.com/en/avinox-mg-gearbox-motor/
- 用途： E-MOUNTAINBIKE 对 Eurobike 2026 Avinox MG Concept 的深度报道与试骑线索；可用于补充 motor + gearbox、continuously variable transmission、seamless gear changes、maintenance 与 ride-feel 叙事，但仍应按概念/原型证据处理

提取内容：

E-CVT传动系统（电子无级变速器）将电动自行车电机与电子控制的无级变速器结合在一起。与传统的变速器或变速箱系统不同，它没有固定齿轮。相反，系统会根据速度、坡度和节奏持续调整齿轮比。

对E-CVT系统的批评通常更多关注电子调校、潜在的效率损失以及系统在启动和加速时的响应性，而非机械部件本身。

据Avinox介绍，该概念的核心目标是提供最自然的乘坐感受。该系统在整个档位范围内保持一致的踏频，并持续调整变速箱传动比以适应骑行条件。
无论你正在攻克陡坡、在平缓林道匀速骑行，或是高速长途转场，系统都会尽量维持你预先设定好的目标踏频基本不变。
Avinox 表示，这套机制能带来极其顺滑、贴合原生骑行感的体验：助力输出大小与传动齿比会根据实时行驶工况持续同步自适应调节。

展台展示的图形中，Aminox直接将MG概念车与传统传动系统进行了比较，声称耐用性提升了多达三倍，效率提升了10%。然而，公司尚未解释这些数字是如何确定的，以及适用的条件是什么。

### 5. 3.2-005 | Revolutionary Gobao X1P Gearbox Motor Review: Is This the Future of eMTB Drive Systems?

- Excel 行号： 17
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 展会/首看/媒体深度
- 原始 URL： https://ebike-mtb.com/en/gobao-x1p-review/
- 用途： E-MOUNTAINBIKE 对 Gobao X1P 的 Eurobike 2026 深度报道；补充 X1P E-CVT gearbox motor、150 Nm 级高输出、无后拨/飞轮思路、eMTB 场景和媒体试骑/评估语境

提取内容：

我们已经在全新Hepha Urban X上测试了另一个令人兴奋的功能。电机实现可控再生，停止踩踏后会轻柔减速。通过倒退，制动效果可以进一步增强。实际上，它已经出乎意料地表现良好，尤其是在较长的下坡上带来了明显的好处。不过，为了实现真正自然的骑行体验，系统在某些情况下仍需进一步打磨，比如过弯时。

最引人注目的是即时且清晰的动力传输。即使在低踏频下，扭矩依然充足，加速极快且可控，最高可达25公里/小时的辅助限制。由于没有换挡，动力输出始终稳定且异常平稳。起始也非常简单且明确。

更令人印象深刻的是噪音水平。虽然许多变速箱系统在负载下能清晰听到声音，但Gobao的传动依然出奇地安静。只有在约100转以上的节奏时，才会有轻微的电声嗡嗡声。尤其是直接与现有变速箱系统相比，X1P已经非常接近量产准备状态。

### 6. 3.3-002 | NOW AVAILABLE: Auto.Shift for the Pinion MGU / Smart.Shift Functions

- Excel 行号： 20
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 官方功能页
- 原始 URL： https://pinion.eu/en/e-drive/smartshift-functions/
- 用途： Auto.Shift、Auto.Shift.Pro、Pre.Select、Start.Select、传感器、目标踏频、手动覆盖、停车起步档、滑行预选档逻辑

提取内容：

Pinion E-Drive系统提供四个支持等级：“Eco”设计为最大续航，而“Fly”则允许骑手随时充分发挥系统强大的动力。然而，“流”和“灵活”两个等级是自适应骑行模式，设计得动态，能根据各种骑行情境和地形完美调整支撑量。精心调校的启动辅助装置帮助防止松散爬坡时的车轮打滑，车把上的增压按钮进一步完善了整体配置。此外，所有支持模式都可通过FIT电动自行车控制应用根据骑手个人偏好进行定制。

除了提供调整和微调功率输出、启动、动力传输及所有Smart.Shift功能外，应用还提供简单明了的调校说明，指导用户完成调校过程。

例如，结合FIT电动自行车控制应用，这些显示屏可以用来规划或显示通过Komoot的路线和方向。

### 7. 3.3-003 | Pinion E-MTB

- Excel 行号： 21
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 官方 OEM 场景页
- 原始 URL： https://pinion.eu/en/e-bikes/e-mtb/
- 用途： Pinion MGU 在 eMTB 的场景叙事与 OEM 示例

提取内容：

Auto.Shift 是进一步简化电动自行车的先进方式。整个换挡过程都是自动化的，始终保持你偏好的步频。你设定一个想要的踏频，系统会根据地形或速度调整档位来保持这个踏频。Auto.Shift 对于长途旅行以及不断变化的城市交通状况来说都非常宝贵。
自动换挡按钮在显示屏上以“A”表示，可随时开关，甚至在骑行中，只需长按E扳机即可。

Auto.Shift.Pro，我们为您提供自动换挡与手动控制的完美结合。该模式专为动态骑行设计，允许你随时用TE1 E-Trigger覆盖自动换挡。一旦你手动介入并换挡，系统会记录随之而来的节奏变化，并相应调整换挡策略。Auto.Shift.Pro 非常适合注重自动换挡舒适性和手动自由的运动骑手。

在多条路线上，你常常需要主动换挡并调整步频以应对即将到来的情况。自动变速箱对情况做出反应，但无法预见。Auto.Shift.Pro 就是解决办法。例如，接近陡坡时，你可能想在爬坡前提高踏频，以获得最佳动量。在 Auto.Shift.Pro 模式下，只需按TE1 E扳机上的按钮手动降一到两个档位。Auto.Shift.Pro 会自动接管较轻档的新踏频作为目标值，并根据爬坡时最佳调整换挡逻辑。如果新的踏频不再适合当前情况，你可以通过长按后部E-Trigger手柄迅速将其重置到预设值。 [我认为Auto.Shift.Pro的问题是不能自动识别骑行者的意图。其实通过轮速、目标踏频、踩踏力矩和坡度可以理解此时骑行者的意图，系统自己做出判断]

Pre.Select是一种半自动换挡功能，用于在滑行时选择最佳档位以恢复踩踏。系统会持续监控你的速度，并自动调整档位，让你能平稳地开始踩踏。此功能特别适用于电动山地车的下坡骑行，确保你在下坡时始终处于正确的档位。 [我认为这都是默认必要的，不应该单独设置为一个模式]

Start.Select是MGU内部半自动换挡的入门级变速器。你的电动自行车在停车时会自动换到预设的起步档位——例如在红绿灯处。这确保了开局轻松高效的过程。尤其是在频繁停停的情况下，Start.Select大大简化了重新起步，让你无需手动换挡就能专注于道路。 [我认为这可以是通过大量的实验给一个默认的速比，来达到起步时踩下去的力矩值达到多大是一个舒适/时候的速比。可以做成每个品牌的初始默认值，也可以让客户自己试验选择一个起步的速比]

选用 Pinion 系统，换挡逻辑完全由你自定义：升档、降档，左右按键布局均可随心设置，TE1 电子变速指拨支持个性化调校。

MGU配备了多种传感器，可监测踏板踩踏力度、曲柄位置、踏频、速度等。

### 8. 3.5-001 | Bosch eShift official page

- Excel 行号： 32
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 官方功能/伙伴页
- 原始 URL： https://www.bosch-ebike.com/en/products/eshift
- 用途： 外部电子/自动换挡生态；列出 3X3 Electric、Classified Powershift、enviolo AUTOMATiQ、Gearsensor GS、Rohloff E-14、Shimano Di2、TRP E.A.S.I. 等伙伴；含 M+、RollShift、Auto-downshift、适配车型与驱动单元边界

提取内容：

eShift 可适配 Classified 双速花鼓变速系统，它会根据脚踏曲柄所处位置，在最优时机完成换挡操作，城市电助力自行车是典型适配场景。

针对运动骑行模式，你可将目标踏频设置为 75 转 / 分钟及以上；若想要更休闲省力的骑行节奏，则可设定 60 转 / 分钟以下的踏频。

### 9. 3.5-002 | Bosch eShift in Test - Automatic Gear Shifting for everyone?

- Excel 行号： 33
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 骑行体验/测评
- 原始 URL： https://ebike-mtb.com/en/bosch-eshift-review-2024/
- 用途： E-MOUNTAINBIKE 对 Bosch eShift + TRP E.A.S.I. A12 的测试；用于评估外部自动换挡在 eMTB 场景中对 e-CVT MGU 的替代压力，以及与 Shimano/SRAM 自动换挡生态的竞争关系

提取内容：

按住博世Mini遥控器中键，可以将踏频设置在40到120转之间，每分钟5个增量。

Roll-Shift 滑行换挡功能（无需踩踏即可完成变速）在三款变速系统上均可稳定运行，通过复杂越野路况时这项功能优势十分突出。
但若在高难度林道开启自动变速进行运动骑行，博世、禧玛诺、速联三套系统都会很快达到性能上限，这类自动变速功能更适配平缓路况的长途休闲骑行。

### 10. 3.16-001 | What Is an eCVT? Could It Replace Derailleurs and Gearboxes?

- Excel 行号： 77
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 媒体技术解释/风险边界
- 原始 URL： https://www.pinkbike.com/news/why-ecvts-could-be-the-future-of-e-bike-drivetrains.html
- 用途： 横向解释 Avinox、Gobao、Owuru 等 eCVT 逻辑；用于机制框架、虚拟档/目标踏频、效率、低电/断电、法规和轻助力适配风险边界；不是单一产品规格源

提取内容：

我在Eurobike试驾Gabao eCVT时，把它调到最大助力模式（1500瓦），然后用后刹拉硬力冲刺。我强制它在手动模式下换挡（它有十二个“虚拟档位”），它毫无问题地换挡了。一旦你了解了电动CVT换挡的工作原理，这就不足为奇了——它只是调节传到电机的电信号。

### 11. 6.1-001 | New Avinox MG gearbox motor prototype

- Excel 行号： 79
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 媒体深度/首骑
- 原始 URL： https://ebike-mtb.com/en/avinox-mg-gearbox-motor/
- 用途： 已写入正文；E-MOUNTAINBIKE 可补试骑/功能叙事

提取内容：

无论你是在攀爬陡坡、沿着流畅的小径巡航，还是快速换乘区段，你偏好的预设节奏都应保持基本不变。据Avinox介绍，这带来了极为平顺自然的骑行体验，因为辅助水平和传动比都会根据具体情况不断调整。

### 12. 6.2-001 | Revolutionary Gobao X1P Gearbox Motor Review

- Excel 行号： 89
- 来源列：F 列「我从URL中获取我认为重要的信息」
- 网页类型： 媒体深度/展会
- 原始 URL： https://ebike-mtb.com/en/gobao-x1p-review/
- 用途： 已写入正文；补 Eurobike 2026 与 X1P 试骑/评价语境

提取内容：

最引人注目的是即时且清晰的动力传输。即使在低踏频下，扭矩依然充足，加速极快且可控，最高可达25公里/小时的辅助限制。由于没有换挡，动力输出始终稳定且异常平稳。起始也非常简单且明确。

### 13. 3.1-002 | Avinox MG Concept : un prototype de moteur a transmission integree qui promet la fin des vitesses

- Excel 行号： 5
- 来源列：I 列「我从URL中获取我认为重要的信息」（位于「我在人工审核时的相关发现」分组下）
- 网页类型： 功能/发布报道
- 原始 URL： https://www.transitionvelo.com/composants/moteurs-batteries/moteurs/avinox-mg-concept-un-prototype-de-moteur-a-transmission-integree-qui-promet-la-fin-des-vitesses/
- 审核发现 URL： https://www.transitionvelo.com/composants/moteurs-batteries/moteurs/owuru-ride-150-nm-de-couple-et-1000-w-de-puissance-pour-le-moteur-a-variation-continue/
- 用途： 介绍 MG Concept 的 motor + gearbox 集成、<0.1 s 换挡、静止/负载换挡、基于踏频自动模式、AI+ 模式、约 520% 变比范围、300 Nm 负载换挡线索

提取内容：

迪卡侬旗下子品牌 Owuru 厂商，刚刚发布了全新一代 Owuru Ride 电机。
相比迪卡侬现有车型搭载的旧款 Owuru 电机，这款新品功率更高、扭矩更强、重量更轻；产品瞄准电动山地车与货运电助力车市场，并且核心亮点在于 —— 它不再仅限装配迪卡侬自有品牌车辆。

Owuru 推出 Owuru Ride 一体化电机，该产品集成无级变速传动系统（CVT），峰值扭矩可达 150 牛米，峰值功率 1000 瓦。
现款 Owuru 电机重量为 4.7 千克，新款 Owuru Ride 仅重 3.9 千克，整机体积也更加小巧紧凑。
Owuru 目前正在寻找合作整车厂商配套搭载这款全新电机，产品计划 2026 年末正式上市，首款装车车型大概率是 Rockrider 系列电动山地车。

我们再来回顾一下无级变速传动系统的工作逻辑：它可以连续改变车辆传动齿比，全程无需手动换挡，动力输出平顺无顿挫。骑手仅需设定自己理想的踩踏踏频，剩余变速调节工作全部交由系统自动完成。
这款集成在电机内部的无级变速机构，变速范围可达 500%，等效于一套 12 速外拨变速套件的齿比跨度。
