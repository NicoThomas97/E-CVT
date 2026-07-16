# L2/L3/L4 基准与替代路线 v2

调研日期：2026-07-05  
证据口径：使用 `verified_sources.csv` 与 `verified_sources_v6_addendum.csv` 中已检查内容。

## 1. L2 准直接方案：不做 MGU，也能抢用户体验

### Bosch eShift

Bosch eShift 是系统级替代路线的核心样本。官方页面定义它为 electric gear shifting solution，支持手动与自动变体，并列出 Rohloff E-14、Shimano Di2、TRP、Classified、3X3、Gearsensor 和 enviolo AUTOMATiQ 等伙伴（V005）。

关键启发：

- 自动换挡价值不一定需要 motor-internal gearbox。
- Bosch 的优势是生态整合：电机、显示、Flow app、伙伴传动件、OEM 和售后。
- 对自研 MGU 来说，必须证明“把变速放进中置单元”相对 eShift 这种外部化路线有足够价值。

### Shimano AUTO SHIFT

Shimano 官方说明 AUTO SHIFT 使用 cadence、torque、speed 等传感数据自动选档，并允许手动覆盖；兼容性绑定 Di2 和 LINKGLIDE/HYPERGLIDE+ 传动组合（V007）。

关键启发：

- Shimano 的核心价值在控制算法和 drivetrain 协同，不是电机内置 gearbox。
- 这一路线对运动用户更友好，因为外变/Di2 的骑行习惯和服务网络成熟。

### SRAM Eagle Powertrain

SRAM 官方页面把 Eagle Powertrain 描述为 E-MTB 系统，和 Eagle Transmission 集成，提供 Auto Shift、Pedal Speed personalization、Coast Shift、AXS Bridge Display、AXS Pod 和 AXS app（V008）。

关键启发：

- SRAM 路线非常接近“体验一体化”，但机械上仍不是 MGU。
- 高端 eMTB 用户可能先接受这种“电机+电子外变”的自动化，而不是重量更大的 MGU。

### enviolo / Rohloff / 3X3

这些路线主要在城市、货运、trekking、SUV 等低维护场景有强意义：

- enviolo Automatic 提供自动无级体验，强调 preferred pace、低维护、封闭结构和 310-400% 速比范围；Utility hub 达到 400% range 和 120 Nm @300 kg 口径（V009）。
- Rohloff E-14 通过电子内变和中置电机协同，支持 torque reduction、multi-shift、auto-downshift；SPEEDHUB 是 14 档、526% range、130 Nm max input torque 的高可靠内变基准（V010, V011）。
- 3X3 系统强调 maintenance-free、静止或重载下换挡、链条/皮带、电驱/非电驱兼容，并已有 QiO、SUGG、Muli、Victoria、VELLO 等整车示例（V012）。

## 2. L3 高性能中置基准

### Avinox M2S/M2/M1

Avinox 当前官方量产驱动单元是 M2S/M2/M1。M2S 的官方口径是 2.59 kg、130 Nm normal max、150 Nm Boost、250 W rated、条件性 1500 W peak；M2 和 M1 分别低一档（V002）。

这说明 Avinox 已具备高功率密度和系统产品化能力。MG Concept 的 Tech Details 图卡已经可作为量产方向/准量产 MGU 目标输入，但 M2S/M2/M1 的功率、重量和扭矩仍不能直接套用到 MG Concept。

### Bosch Performance Line CX

Bosch CX BDU384Y 官方技术数据可作为口径管理样板：页面列出 max possible 120 Nm、750 W、600% support、2.8 kg，但脚注明确标准供应仍是 85 Nm 和 600 W，高值与 app/OEM/dealer/battery 等条件相关（V006）。

这对我们的报告写作非常重要：所有高性能中置电机参数都必须拆分“标准/可解锁/峰值/条件”。

## 3. L4 替代技术路线

### Pinion 纯 gearbox

Pinion P-line/C-line 不是 MGU，但它们是 sealed gearbox 的核心学习对象。P-line 官方页面列出 P1.18 18 档、636% range、2700 g，P1.12 12 档、600% range、2350 g，并列出 250 Nm max torque 和 10,000 km service interval（V014）。

### Rohloff / enviolo / 3X3 hubs

这些 hub/internal transmission 路线不等于 MGU，但它们会影响用户是否愿意为 MGU 付费：

- Rohloff：高可靠、高范围、高价格、长途/货运/trekking 信任感强。
- enviolo：自动/无级、城市/货运体验友好。
- 3X3：维护少、可电控、整车示例逐步增加。

### 尚待补证

Gates Carbon Drive、Classified、Effigear、Bafang、Yamaha、Brose、TQ、FAZUA、Specialized 暂不写入已验证结论。它们保留在 `source_backlog.csv` 中，后续按优先级补证。
