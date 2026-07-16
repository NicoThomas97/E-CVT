# Pinion vs Gobao 架构对照

调研日期：2026-07-04  
证据范围：Pinion 使用官方 MGU 页面；Gobao 使用官方 X-system 页面；Avinox 作为 eCVT/MGU 量产方向参照时，仅使用已核读的 Tech Details 图卡和已分层媒体证据，未使用未核验媒体参数。

## 1. 一句话对比

Pinion 是“有级 gearbox MGU”的量产标杆；Gobao 是“eCVT/连续变速 MGU”的中国高输出信号；Avinox MG Concept 已经把 eCVT/连续变比 MGU 的量产方向功能包公开化。

## 2. 参数对照

| 维度 | Pinion E1.9 | Pinion E1.12 | Gobao Urban & Trekking | Gobao MTB & Cargo |
| --- | ---: | ---: | ---: | ---: |
| 变速形式 | 9-speed gearbox | 12-speed gearbox | automatic CVT | automatic CVT |
| 速比范围 | 568% | 600% | 400% | 500% |
| 重量 | ~4000 g | ~4100 g | 3.85 kg | 3.85 kg |
| 扭矩 | 85 Nm competitive torque | 85 Nm competitive torque | 120 Nm | 150 Nm |
| 功率 | 600/800 W peak | 600/800 W peak | 1200 W | 1500 W |
| 维护 | 10,000 km oil change claimed | 10,000 km oil change claimed | not verified | not verified |
| 证据 | V001 | V001 | V004 | V004 |

## 3. 工程含义

Pinion 路线的优势是机械边界清楚：档位、速比、维护间隔和规格表都比较容易验证。风险集中在重量、成本、NVH、用户换挡感和售后。

Gobao 路线的优势是体验叙事更强：自动连续变速、较高扭矩/功率、同样 3.85 kg 的页面重量，对 eMTB/cargo 很有冲击力。风险集中在效率、热、寿命、控制稳定性、真实工况功率持续能力和量产可信度。

## 4. 对自研路线的建议

第一阶段不要押单一路线。建议用两个技术假设并行：

- `有级 gearbox MGU`：以 Pinion 为硬基准，验证可量产、可维护、可服务。
- `eCVT MGU`：以 Gobao 官方规格块和 Avinox Tech Details 量产方向目标为高风险高收益参照，优先做效率、热、寿命、扭矩平滑、负载换挡和低维护台架。

如果公司资源只能选一条，建议先以有级 gearbox MGU 做工程闭环，同时保留 eCVT 的核心台架预研。理由是 Pinion 已证明量产路径，而 eCVT 虽已有 Gobao 官方规格和 Avinox 准量产图卡压力，但长期可靠性、真实效率和服务边界仍需硬证据。

## 5. 必须补的验证数据

- 同等轮端输出下的传动效率地图。
- 30 分钟长坡热稳态和热衰减。
- 低速大扭矩换挡冲击和成功率。
- 泥水/清洗/低温后的换挡执行稳定性。
- 维护周期、油品/润滑、密封件和整机返修边界。
- OEM 车架接口、Q-factor、链线/皮带线、整机成本。
