# e-CVT MGU 研究重点说明

最后更新：2026-07-05

## 1. 技术边界

本项目后续主轴不是广义 MGU，也不是以 Pinion 为代表的有级机械 gearbox MGU，而是：

> 中置电机与 e-CVT/电子控制连续变速系统高度集成的中置驱动单元。

目标形态更接近 Gobao X-system 和 Avinox MG Concept 的量产方向/准量产产品定义：电机、变速机构、控制策略、传感器和整车系统协同，让整车可以自动维持合适踏频、传动比、电机工作区间和扭矩响应。

## 2. 与其他路线的区别

| 路线 | 后续定位 |
| --- | --- |
| e-CVT MGU | 主研究对象，重点判断使用场景、不可替代性、效率/热/寿命风险 |
| 有级 gearbox MGU，如 Pinion MGU | 量产集成 MGU 参照，用于学习封装、OEM 装车、低维护、售后，不作为目标技术形态 |
| 电子外变，如 SRAM/Shimano | 关键替代方案，比较自动换挡和运动场景体验 |
| 花鼓内变/CVT，如 enviolo/Rohloff/3X3 | 关键替代方案，比较低维护、停启、货运和通勤场景 |
| 普通高性能中置电机 | 性能、重量、成本和生态基准 |

## 3. e-CVT MGU 真正要解决的问题

e-CVT MGU 的价值不应定义为“能变速”，而应定义为：

- 用户不需要主动管理档位。
- 在满载起步、低速爬坡、频繁停启、坡度变化时自动保持合适踏频。
- 减少外露传动系统复杂度。
- 将电机控制、变速控制、传感器和诊断合成一个整车系统。
- 相比花鼓 CVT，把复杂度从后轮移回中置单元，改善后轮维护和整车布置。
- 相比电子外变，减少后拨、飞轮、链条等外露易损件依赖。
- 参考 Avinox Tech Details，把扭矩平滑、<0.1 s 负载换挡、100%-520% 可配置虚拟档、低维护单速外传动、mechanical lock、reverse assist、built-in speed sensor 和 charging 纳入系统级价值判断。

## 4. 最重要的风险

e-CVT MGU 需要重点验证：

- 传动效率是否可接受。
- 高扭矩/高功率下热管理是否可接受。
- 连续变速机构寿命是否可接受。
- 控制策略是否稳定、可预测、可手动覆盖。
- 用户是否接受无级感、虚拟档位或目标踏频控制。
- 售后是否可诊断、可维修、可更换模块。
- 与有级 gearbox MGU、花鼓 CVT、电子外变相比，系统收益是否真的更高。

## 5. 后续优先级变化

- Gobao X-system：第一核心官方竞品/参照。
- Avinox MG Concept：第一量产方向/准量产目标参照；Tech Details 图卡可作为内部对标输入，继续追 press kit、专利、OEM prototype 页面、测试基准和最终公开 datasheet。
- Owuru / E2Drives / Decathlon：官方城市车技术链和 LD 920 E 装车已补齐，可证明目标踏频/连续变速 UX 与 Decathlon OEM fit；高功率 eMTB/cargo 仍停留在媒体首看/原型证据，需要继续追官方 datasheet、效率、热、寿命和服务策略。
- Valeo Cyclee、Revonte ONE：继续作为历史 e-CVT/自动变速方案线索，用于追溯技术卡点、商业状态和失败原因。
- Pinion MGU：降为量产 MGU 参照，不再作为主目标路线。
- `scenario_substitutability_matrix.csv` 后续应改成 e-CVT MGU 的场景不可替代性矩阵。
