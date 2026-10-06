# 功能更新履历 (Feature Log)

## [2026-10-06 20:50] 补全第一人称视觉核心官方入口、索引资源与避坑下载指南

- **上线/引入日期**: 2026-10-06
- **涉及模块**: `README.md`（目录、核心入口、Ego-Exo4D、Ego4D、Aria 背景说明）

### 1. 变更动机
第一人称（Egocentric）视觉由于包含大量真实人类日常活动与敏感环境信息，全量视频文件往往达数十 TB 乃至 PB 级别，且核心大库（Ego4D、Ego-Exo4D 等）均有严格的数据使用许可协议（DUA）及多日审核流程。为了降低研究者与开发者的检索门槛，避免盲目拉取全量视频导致带宽与存储耗尽，需在 README 开篇显著位置补充核心官方入口、权限获取流程与分步下载避坑指南。

### 2. 变更详情
1. **新增常用官方入口与获取指南专栏**：
   - **Ego4D**：补充约 3,670 小时规模、注视/双目/多机位同步特征、官方文档链接、CLI 工具链接及 48 小时 AWS 凭证下发流程。
   - **Ego-Exo4D**：补充约 1,286 小时完整规模、头戴（Project Aria）+ 外部多机位同步特性与学术许可要求。
   - **EPIC-KITCHENS**：补充厨房场景手-物交互与细粒度动作识别的黄金基准地位。
   - **awesome-egocentric-vision**：补充该学术索引资源，方便按任务和数据集结构化导航。
   - **Meta Project Aria**：补充该核心传感器硬件平台介绍及其在 Ego-Exo4D、AEA、ADT、Nymeria、HOT3D 等基准中的主力采集角色。
2. **下载与存储避坑最佳实践**：
   - 明确指出“先下标注元数据（Annotations）与可视化切片（Visualizations）熟悉 Schema，再按具体 Benchmark 任务按需拉取子集/降采样片段”的分步获取策略。
3. **纠正与更新旧版本条目**：
   - 更新目录索引（TOC），接入新增章节锚点。
   - 修正经典数据集章节中 Ego4D 与 EPIC-Kitchens 的描述与配套链接。

## [2026-10-06 21:08] 扩充领域综述路线图、顶级 Workshop 与高权威学术基准矩阵

- **上线/引入日期**: 2026-10-06
- **涉及模块**: `README.md`（全景综述与研讨会、Ego4D 衍生基准、Aria 生态、程序性活动与失误检测、3D 姿态与手物接触、无障碍与视听具身、经典数据集）

### 1. 变更动机
参照领域权威综述与学术脉络（IJCV 2024 与 awesome-egocentric-vision），剔除水刊与广告营销站点，精选具有高学术公信力、被各大顶会（CVPR、ECCV、NeurIPS）录用并有真实代码与数据托管的旗舰基准，进一步充实程序学习、工业失误检测、极端工况三维感知、双目姿态估计与视障辅助问答等核心方向。

### 2. 变更详情
1. **领域核心综述与学术社区活动**：
   - 补充首篇全景技术路线图：*An Outlook into the Future of Egocentric Vision* (IJCV 2024)。
   - 补充核心研讨会：EgoVis Workshop（CVPR 常设，合并 EPIC + Ego4D + Aria）与 EgoMotion Workshop（CVPR 2024/ICCV 2025）。
2. **Ego4D / Ego-Exo4D 衍生基准**：
   - 补充斯坦福超长视频基准 **HourVideo**（NeurIPS 2024）、分层规划 **Ego4D Goal-Step**、长摘要 **Ego4D-HCap**、长视频定位 **LongEgoRefer** 及流式交互 **EgoSAT**。
3. **Project Aria 智能眼镜生态拓展**：
   - 补充牛津大学日夜极端光照 3D 视觉基准 **Oxford Day-and-Night (OxDaN)**、苏黎世联邦理工城市级 SLAM 基准 **LaMAria** 与极端工况 6D 物体姿态基准 **EgoXtreme**。
4. **新增「程序性活动理解与失误检测」专栏**：
   - 补充烹饪失误检测基准 **CaptainCook4D**（CVPR 2024）、工业协同操作与检修基准 **IndEgo**（NeurIPS 2025）、多模态动作与人体运动学基准 **EPFL-Smart-Kitchen-30**（NeurIPS 2025）、无监督步骤发现 **EgoProceL**（ECCV 2022）及异步学习 **EgoExoLearn**。
5. **手-物交互、3D 姿态与灵巧操作**：
   - 补充密集手-物接触姿态基准 **EPIC-Contact**（ECCV 2026）、社交互动 3D 动捕基准 **EgoBody**（ECCV 2022）、双目鱼眼 3D 姿态基准 **UnrealEgo / UnrealEgo2**（ECCV 2022/CVPR 2024）。
6. **视障无障碍辅助与视听具身**：
   - 补充首个视障人群真实需求基准 **EgoBlind**（NeurIPS 2025）、视听指令理解套件 **EgoAVU** 及个性化自我意图基准 **MyEgo**（CVPR 2026）。
7. **经典数据集补全**：
   - 补入印第安纳大学经典手部像素级分割基准 **EgoHands**（CVPR 2015）。
