# 中置变速电机研发预研报告 v3

调研日期：2026-07-04  
定位：第三轮补证后的 L1 直接竞品重点版。

## 1. 本轮新增结论

第三轮把 L1 的事实硬度进一步拉开：

- `Pinion MGU`：已量产、官方规格清楚，是有级 gearbox MGU 的主基准（V001）。
- `Gobao X-system`：官方页面已验证 motor+transmission 单元和 automatic continuously variable transmission，且给出 120/150 Nm、1200/1500 W、3.85 kg、400/500% range 两个模型块（V004）。
- `Avinox MG Concept`：仍是媒体信号，没有官方规格闭环；不能用 Avinox M2S 参数代替（V002, V003, V017）。
- `Valeo Cyclee`：从“无证据 backlog”升级为“历史媒体线索”，但还不是可比较的当前量产竞品（V015）。
- `Revonte/Owuru`：仍不够硬，不能进入规格对比。

## 2. 研发判断

当前最值得投入的直接对标不是“列更多品牌”，而是把 Pinion 与 Gobao 拆穿：

- Pinion 代表更稳的工程路线：有级 gearbox、明确维护、明确规格、已量产。
- Gobao 代表更激进的路线：eCVT、较高扭矩/功率、较低页面重量、量产状态仍需追踪。
- Avinox 代表战略威胁：即使规格未公开，DJI/Avinox 的系统集成和品牌能力值得最高关注。

## 3. 推荐下一阶段技术路线

建议立两个样机方向，但资源优先级不同：

1. `P0 有级 gearbox MGU`
   - 目标：跑通量产工程闭环。
   - 对标：Pinion E1.9/E1.12。
   - 关键指标：速比范围、换挡冲击、负载换挡、密封、油品/润滑、服务间隔、NVH。

2. `P1 eCVT MGU`
   - 目标：验证是否能在效率、热、寿命上成立。
   - 对标：Gobao X-system 和 Avinox MG Concept 趋势。
   - 关键指标：效率地图、热稳态、连续功率、控制稳定性、长寿命磨损。

3. `P2 外部自动换挡 MVP`
   - 目标：用较低成本验证用户是否真的为自动换挡付费。
   - 对标：Bosch eShift、Shimano AUTO SHIFT、SRAM Eagle Powertrain、enviolo、Rohloff。

## 4. 立项门槛

进入正式开发前，需要至少完成：

- Pinion 实车用户证据：噪音、换挡、售后、可靠性、价格带。
- Gobao 生产证据：X1/X1P 命名、OEM 客户、真实交付时间、热/效率/持续功率。
- Avinox 官方资料：官方图片/视频/展台资料/专利线索。
- 自研方案边界：首发是 cargo/SUV/trekking 还是 eMTB。
- 供应链边界：gearbox、执行器、控制器、传感器、密封润滑、售后工具是否自研或合作。

## 5. 下一轮最该查什么

下一轮不建议继续扩散长名单，而要补“用户证据 + 商业证据”：

- Pinion MGU 整车评测和长期使用反馈。
- 已装 Pinion MGU 的整车品牌、价格、车型类别。
- Gobao X-system 的 OEM 合作和样车证据。
- Avinox MG Concept 的官方或准官方视觉资料。
- 欧洲/中国高端 cargo、SUV、eMTB 的价格带和目标客户。

