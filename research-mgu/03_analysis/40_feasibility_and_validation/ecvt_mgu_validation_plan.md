# e-CVT MGU 立项证据补齐验证计划

最后更新：2026-07-05

## 1. 目的

本文件把三份场景价值假设转成可执行的证据补齐任务。它不是测试规范终版，而是用于研发预研、产品访谈和竞品追证对齐。

核心判断标准：

> 只有当 e-CVT MGU 在某个场景中同时解决多个痛点，并且相比电子外变、花鼓 CVT/内变、有级 gearbox MGU、普通中置电机形成明显系统收益，才值得进入下一阶段立项讨论。

任务明细见 `02_matrices/ecvt_mgu_validation_task_matrix.csv`。

## 2. 验证对象

当前优先把验证拆成三个价值场景，而不是单一产品路线图：

| 场景 | 要验证的核心价值 | 最大替代压力 |
| --- | --- | --- |
| High-end eMTB / gravity / technical climbing | 后拨/飞轮/链条外露易损、后轮/悬架自由度、技术爬坡和骑手控制 | 电子外变 + 高性能中置、有级 MGU |
| Cargo / family utility | 满载起步、坡道停启、低技能用户、低维护和 TCO | 花鼓 CVT/内变、有级 MGU |
| 高端 SUV / trekking / all-road commuter | 目标踏频、低维护、后轮简化、长距离混合路况和 premium integrated drive | 花鼓 CVT/内变、有级 MGU、外部电子换挡 |

Avinox MG Concept Tech Details 已作为量产方向/准量产目标输入加入上述三类场景：eMTB 对标非簧载质量、扭矩平滑和负载换挡；cargo/family 对标静止换挡、倒车助力和锁止；SUV/trekking 对标低维护、内置速度传感、低噪声和系统集成。

## 3. 证据类型

### 3.1 公开追证

目的：把公开事实边界钉牢。Avinox Tech Details 图卡可以作为量产方向/准量产产品定义使用，但仍要追清测试基准、内部机制、最终公开 datasheet 和法规/安全边界。

重点：

- Gobao X-system：官方命名、量产时间、OEM 客户、服务策略、持续性能。
- Avinox MG Concept：Tech Details 图卡值的测试基准、内部机制、量产边界、合作车型、press kit、专利和 charging 传动路径。
- Owuru / Decathlon：目标踏频 UX 与量产可靠性的边界。
- Pinion / enviolo / Rohloff / Bosch / Shimano / SRAM：替代方案成熟度和系统能力。

对应任务：`VT010`、`VT011`。

### 3.2 台架测试

目的：验证 e-CVT MGU 是否能在真实负载下成立，而不是只看峰值扭矩或宣传参数。

优先台架项：

| 测试 | 覆盖场景 | 关键输出 |
| --- | --- | --- |
| 效率 map | eMTB、cargo、SUV/trekking | 踏频、扭矩、车速、坡度下的效率区间 |
| 热循环 | cargo、eMTB | 满载起步、低速高扭矩、长坡、高温下热衰减 |
| NVH | eMTB、SUV/trekking | 电机声、变比调整声、链/带路径噪声和主观感知 |
| 寿命/污染/冲击 | eMTB、cargo | 泥水、粉尘、冲击、清洗、密封和执行器可靠性 |
| 故障降级 | 全场景 | 低电、断电、传感器故障、执行器故障时的可骑/可推/可修策略 |
| 扭矩响应/换挡窗口 | eMTB、SUV/trekking | fast response with no overshoot、assist remain/overrun、<0.1 s shifting window、300 Nm load shift 的可测定义 |
| 系统功能安全 | cargo、SUV/trekking、urban | mechanical motor lock、electric reverse assist、built-in speed sensor、charging 的功能边界和失效策略 |

对应任务：`VT003`、`VT006`、`VT009`、`VT012`。

### 3.3 样车验证

目的：验证用户能否感知 e-CVT MGU 的系统收益。

高端 eMTB 样车重点：

- 技术爬坡时目标踏频是否自然。
- 扭矩平滑是否接近 Avinox 图卡的 fast response with no overshoot，而不是迟钝或拖拽。
- 站姿重踩、突然变坡、湿滑路面下是否可预测。
- 虚拟档/手动覆盖是否可信。
- <0.1 s 级变比/换挡窗口是否能在真实负载下被感知为 constant torque output。
- 跳跃落地、摔车、泥水清洗后的可靠性。

Cargo/family 样车重点：

- 满载起步和坡道起步是否更轻松。
- electric reverse assist 是否能解决满载倒车/挪车。
- mechanical motor lock 是否能安全地服务驻车、防盗、断电和维修。
- 频繁停启时用户是否不用操心档位。
- 家庭/低技能用户是否减少误操作。
- 整车推行、低电和故障状态是否可接受。

SUV/trekking 样车重点：

- 长距离混合路况下目标踏频是否舒适。
- 自动连续变比是否比有级自动换挡更自然。
- 后轮简化、皮带路径、货架/挡泥板/轮组维护、built-in speed sensor 和低噪声是否有真实收益。

对应任务：`VT001`、`VT004`、`VT007`、`VT008`。

## 4. OEM / 经销商 / 用户访谈

访谈不是问“你想不想要 e-CVT MGU”，而是问替代方案的痛点。

### 4.1 OEM 访谈问题

- 当前车型最不满意的是外露传动、换挡体验、低维护、后轮布置、售后成本，还是品牌差异化？
- 电子外变、hub CVT/内变、有级 MGU、普通中置电机分别有哪些不能接受的问题？
- 如果 e-CVT MGU 更贵更重，必须带来哪些系统收益才值得上车？
- OEM 是否愿意接受单一中置总成带来的供应商锁定和售后风险？
- 目标车型中，哪些价格带和用户人群能承载这个系统？

### 4.2 经销商 / 售后访谈问题

- 当前高端 e-bike 最常见传动故障是什么？
- 后拨、飞轮、链条、花鼓内变、电子换挡、MGU 各自维修难点是什么？
- 如果一体化 MGU 需要模块更换，经销商能接受什么诊断工具、备件成本和维修时间？
- 用户更愿意接受“定期小维护”还是“低频但高价总成维修”？

### 4.3 用户访谈问题

- 用户真正讨厌的是换挡本身、维护、坏车、噪声、重量，还是续航？
- 目标踏频和用户不用操心换挡是否能被感知为高级体验？
- 高端 eMTB 用户是否愿意用虚拟档/手动覆盖替代传统外变控制感？
- cargo/family 用户是否愿意为“像自动挡一样好骑”支付溢价？

对应任务：`VT001`、`VT004`、`VT005`、`VT007`、`VT012`。

## 5. 场景级 Go / No-Go 判断方式

### 5.1 eMTB

Go 倾向：

- 后拨取消、后轮/悬架自由度和技术爬坡收益被用户明确感知。
- 重量、效率、NVH 和手动控制可信度接近或优于替代路线。
- 冲击、泥水、清洗和摔车后的可靠性可证明。

No-Go 倾向：

- 用户认为电子外变已经足够，外露传动不是强痛点。
- e-CVT 带来明显重量、噪声、效率或控制不可预测问题。
- 售后从便宜易损件变成高价总成风险。

### 5.2 Cargo / family

Go 倾向：

- 满载起步、坡道和频繁停启体验明显优于传统外变。
- 相比 hub CVT/内变，后轮维护、诊断、TCO 或用户误操作有可量化收益。
- 高载热、寿命和故障降级可接受。

No-Go 倾向：

- enviolo/Rohloff/3X3 已经以更低成本解决大部分痛点。
- e-CVT 高载效率或热表现差。
- TCO 被总成维修成本抵消。

### 5.3 高端 SUV / trekking

Go 倾向：

- 目标踏频、连续变比、低维护和 connected/security 能组成清晰 premium integrated drive 体验。
- 后轮简化和中置诊断相比 hub CVT/内变有实际 OEM 收益。
- 效率、NVH、售后和价格带可接受。

No-Go 倾向：

- 用户只感知到“自动换挡”，无法感知中置集成增量。
- hub CVT/内变或有级 MGU 能以更低风险满足需求。
- 长距离效率或噪声不符合高端预期。

## 6. 当前最大证据缺口

1. e-CVT 效率 map 和热衰减曲线。
2. 高载低速寿命、润滑、密封、执行器失效模式。
3. eMTB 用户对自动目标踏频、虚拟档和手动覆盖的接受度。
4. hub CVT/内变在 eMTB 和 cargo 中的后轮质量、维修和骑感真实评价。
5. Gobao X-system 的量产、OEM 客户、服务模型和持续性能。
6. Avinox MG Concept 官方机制闭环。
7. Avinox Tech Details 图卡值的测试口径：>1.1 kg、150 kg、45 dB、300 Nm、<0.1 s、100%-520%、3x durability、10% efficiency、charging。
8. 售后模块化、故障码、断电降级和保修成本。

## 7. 下一步产出建议

- 将 `ecvt_mgu_validation_task_matrix.csv` 转成测试需求表。
- 将本文件第 4 节转成 OEM / 经销商 / 用户访谈提纲。
- 对 `VT001-VT012` 标注责任人、优先级、预计证据来源和完成状态。
- 继续补查 Gobao、Avinox、Owuru 的官方或准官方闭环资料：Gobao 追量产、客户和服务策略；Avinox Tech Details 先按量产方向/准量产目标使用，同时追 press kit、专利、OEM prototype 页面、测试基准和最终公开 datasheet；Owuru/E2Drives 追高功率 datasheet、效率/热/寿命、服务策略和非 Decathlon OEM。
