# Awesome Egocentric Dataset（第一人称视觉数据集精选）

> 精选的 **egocentric（第一人称）视觉数据集**清单 —— 从经典基准到 2023–2026 最新发布。

覆盖日常活动理解、手-物交互、导航、视频-语言、长期记忆等研究方向。

## 目录

- [关于](#关于)
- [常用官方入口与获取指南](#常用官方入口与获取指南)
- [领域核心综述与学术社区活动](#领域核心综述与学术社区活动)
- [近年新数据集（2023–2026）](#近年新数据集20232026)
  - [Ego4D / Ego-Exo4D 与衍生基准](#ego4d--ego-exo4d-与衍生基准)
  - [智能眼镜与 Project Aria 生态](#智能眼镜与-project-aria-生态)
  - [程序性活动理解与失误检测](#程序性活动理解与失误检测)
  - [第一人称视频理解、大模型与视听具身](#第一人称视频理解大模型与视听具身)
  - [手-物交互、3D 姿态与灵巧操作](#手-物交互3d-姿态与灵巧操作)
  - [规模化人类视频与具身预训练](#规模化人类视频与具身预训练20252026)
  - [长期记忆与第一人称视频问答](#长期记忆与第一人称视频问答)
- [经典数据集](#经典数据集)
- [商业受限与门控数据集](#商业受限与门控数据集)
- [参与贡献](#参与贡献)
- [许可](#许可)
- [Egocentric 视角下的 VLA 论文（2023.08 – 2026.08）](#egocentric-视角下的-vla-论文202308--202608)

## 关于

本仓库维护一份持续更新的第一人称视觉数据集清单。它借鉴了广受引用的
[Egocentric-Dataset](https://github.com/EgoAlpha/Egocentric-Dataset) 与 [awesome-egocentric-vision](https://github.com/Sid2697/awesome-egocentric-vision) 等学术资源（早期清单多停更于 2022 年），并做了如下刷新：

- **剔除**官方页面已失效或不再维护的数据集。
- **更新**已迁移到新官方页面的数据集链接。
- **新增**最近三年（2023–2026）发布的重要数据集。

每个条目都附简要描述（机构、任务类型、规模，若已知）。

## 常用官方入口与获取指南

第一人称（egocentric）视觉数据由于包含大量真实人类日常活动与敏感环境信息，大型基准库普遍需要**签署学术许可协议（Data Use Agreement）**方可授权下载。以下整理了目前最核心的官方入口、索引资源与避坑建议：

### 核心官方入口

- **[Ego4D](https://ego4d-data.org/)** — 日常第一人称视觉基准，规模约 **3,670 小时**（涵盖日常活动、工作、社交等），来自全球 9 个国家 74 个地点、855 位佩戴者。部分片段包含眼动注视（Gaze tracking）、立体双目（Stereo）与多机位同步数据。
  - **官方文档**：[https://ego4d-data.org/docs/](https://ego4d-data.org/docs/)
  - **专用下载工具 (CLI)**：[facebookresearch/Ego4d](https://github.com/facebookresearch/Ego4d)
  - **获取流程**：在线签署学术使用协议，审核通过后（通常约 48 小时）官方将通过邮件发放专用的 AWS S3 访问凭证（AWS Access Key / Secret Key）。
- **[Ego-Exo4D](https://ego-exo4d-data.org/)** — 头戴第一人称与外部多机位第三人称同步基准，聚焦熟练技能类活动（烹饪、健康、运动、乐器等），总计约 **1,286 小时**。
  - **官方页面**：[https://ego-exo4d-data.org/](https://ego-exo4d-data.org/)
  - **获取流程**：同样需要签署学术许可协议，通过官方 CLI 工具与数据凭证拉取对应模态与视角的视频。
- **[EPIC-KITCHENS](https://epic-kitchens.github.io/)** — 第一人称厨房场景经典基准（涵盖 EPIC-KITCHENS-55 与 EPIC-KITCHENS-100）。
  - **官方主页**：[https://epic-kitchens.github.io/](https://epic-kitchens.github.io/)
  - **核心特色**：原生非脚本第一人称环境，在精细化动作识别（Action Recognition）和手-物交互（Hand-Object Interaction）研究中引用和使用最为广泛。
- **学术索引资源**：[awesome-egocentric-vision](https://github.com/Sid2697/awesome-egocentric-vision) — 按数据集与下游任务（动作识别、手部姿态估计、视线追踪、多模态问答等）系统梳理了 Ego4D、EPIC-KITCHENS、Ego-Exo4D 以及后续专项小库。
- **核心采集设备**：[Meta Project Aria](https://www.projectaria.com/) — 当前主流第一人称具身数据集的核心硬件平台。Ego-Exo4D 的第一人称头戴视角主要来自这套传感器眼镜（集成眼动仪、双单色 SLAM 相机、RGB 相机、双 IMU 及空间麦克风阵列），亦是 AEA、ADT、Nymeria、HOT3D、LookOut 等前沿基准的官方采集设备。

### 数据下载与存储避坑建议

> [!TIP]
> **全量视频达 TB 乃至 PB 级，切忌盲目拉取全量原始高清视频！**
> 
> 1. **先看字段与模式**：优先下载体积极小的 **标注文件（Annotations / Metadata）** 或 **可视化样例（Visualizations / Sample Clips）**，在本地先期检查 JSON schema、时间戳对齐与标注字段定义。
> 2. **按任务拉取子集**：根据具体研究任务（例如 FHO 手物交互、MQ 矩查询、AV 音视频同步、3D 手部估计），使用官方 CLI 工具附带的 `--datasets` 或 `--parts` 过滤选项，仅拉取当前任务所需的特征（Features）、低分辨率代理（Downscaled Clips）或指定视频片段，大幅节省带宽与存储空间。

## 领域核心综述与学术社区活动

### 权威综述路线图

- **[An Outlook into the Future of Egocentric Vision](https://arxiv.org/abs/2308.07123)**（IJCV 2024）— 由第一人称视觉领域多位领头学者联合撰写的全景综述与技术路线图，系统梳理了从穿戴式硬件生态、任务定义（动作识别、注视预测、手物交互、三维感知与重构、长期记忆）到主流基准与开放挑战。

### 核心学术研讨会（Recurring Workshops）

- **[EgoVis Workshop (Joint Egocentric Vision Workshop)](https://egovis.github.io/)** — 当前第一人称视觉领域最核心的学术交流阵地，整合了历史悠久的 EPIC Workshop、Ego4D Workshop 与 Project Aria 社区，常设于 CVPR（CVPR 2024、2025、2026），持续主办年度基准挑战赛与杰出论文评选。
- **[EgoMotion Workshop](https://egomotion-workshop.github.io/)** — 聚焦基于第一人称穿戴式多模态传感器的人体动作追踪、动作合成与行为理解的专题研讨会（CVPR 2024、ICCV 2025）。

## 近年新数据集（2023–2026）

### Ego4D / Ego-Exo4D 与衍生基准

- [Ego-Exo4D](https://ego-exo4d-data.org/) — Meta AI / UIUC 等多机构（2023，NeurIPS）。大规模多模态多视角数据集，包含同步的第一人称（主要来自 Project Aria 眼镜）+ 多路外部第三人称视频，覆盖熟练技能类活动，总计约 **1,286 小时**，提供 3D 手/身体/注视标注与基准。需签署学术许可。[[论文]](https://arxiv.org/abs/2311.18259) [[代码]](https://github.com/facebookresearch/Ego4d)
- [EgoSchema](https://egoschema.github.io/) — 加州大学伯克利分校 BAIR（CVPR 2024）。超长视频理解诊断基准；约 5,000 段 180 秒 Ego4D 片段 + 人工标注选择题。[[论文]](https://arxiv.org/abs/2308.09126)
- [HourVideo](https://hourvideo.stanford.edu/) — 斯坦福大学等（NeurIPS 2024）。超长第一人称视频语言理解诊断基准；精选 500 段时长在 20 至 120 分钟的未修剪 Ego4D 视频，包含 12,976 道人工多选问答，全面评测长视频摘要、感知定位、时空/因果推理与导航能力。[[论文]](https://arxiv.org/abs/2411.04998)
- [EgoTracks](https://ego4d-data.org/docs/data/egotracks/) — Meta AI（2023）。基于 Ego4D 的长期目标跟踪基准，5.9k 视频中约 22.42k 条轨迹。
- [Ego4D Goal-Step](https://arxiv.org/abs/2311.18259) — 层次化目标-步骤-子步骤任务规划基准；包含 2,807 小时目标标签视频与 430 小时细粒度步骤标注（4.8 万步骤段）。
- [Ego4D-HCap](https://arxiv.org/abs/2307.16854) — 分层长程视频总结与描述基准；基于小时级 Ego4D 视频构建 8,267 条人工密集长视频摘要。
- [LongEgoRefer](https://arxiv.org/abs/2403.15382) — 长视频时空目标 Grounding 基准；在平均 45 分钟的未修剪第一人称视频中定位 1,498 条指称表达。
- [EgoSAT](https://arxiv.org/abs/2406.18898) — 面向流式具身交互理解的第一人称视频基准；165 小时第一人称视频配约 4,800 对问答。
- [EgoPet](https://www.amirbar.net/egopet/) — Technion（ECCV 2024）。动物第一人称视频数据集（自我运动 + 交互），含三个行为基准任务。[[论文]](https://arxiv.org/abs/2404.09991)
- [EgoHumans](https://rawalkhirodkar.github.io/egohumans/) — 卡内基梅隆大学（ICCV 2023）。首个野外多人体 3D 理解第一人称基准；12.5 万+ 图像，含 SMPL / SMPL-X 标注。[[论文]](https://arxiv.org/abs/2305.16487)

### 智能眼镜与 Project Aria 生态

> [Meta Project Aria](https://www.projectaria.com/) 是 Meta 为第一人称具身 AI 与多模态感知研发的专用传感器眼镜平台（集成双 SLAM 相机、眼动追踪仪、RGB 传感器、双 IMU 及空间麦克风阵列）。Ego-Exo4D 的第一人称视角以及以下 AEA、ADT、Nymeria、HOT3D 等基准均主要由该设备采集。

- [Aria Everyday Activities (AEA)](https://www.projectaria.com/datasets/aea/) — Meta Reality Labs（CVPR 2024）。来自 Aria 智能眼镜的开放多模态日常活动数据集；143 段（约 18 小时），含 IMU / 眼动。[[论文]](https://arxiv.org/abs/2402.13349)
- [Aria Digital Twin (ADT)](https://www.projectaria.com/datasets/adt/) — Meta Reality Labs（2023）。用 Aria 采集的第一人称 3D 基准，配大规模仿真真值（设备/物体/场景 3D）。[[论文]](https://arxiv.org/abs/2306.06362)
- [Oxford Day-and-Night (OxDaN)](https://oxdan.active.vision/) — 牛津大学（NeurIPS 2025）。基于 Project Aria 智能眼镜在日间与夜间极端光照下采集的超大规模第一人称 3D 视觉基准；覆盖 30+ 公里轨迹、约 4 万平方米室内外场景，提供多会话 SLAM 毫米级位姿与 3D 点云真值，面向新视角合成（3DGS/NeRF）与视觉重定位评测。[[论文]](https://arxiv.org/abs/2506.04224) [[数据]](https://huggingface.co/datasets/active-vision-lab/oxford-day-and-night)
- [LaMAria](https://lamaria.ethz.ch/) — 苏黎世联邦理工 ETH Zurich / Meta（2025）。城市级第一人称视觉惯性 SLAM 基准；Aria 眼镜采集数小时与数公里城市轨迹，配备大地测量级控制点厘米精度真值。[[代码]](https://github.com/cvg/lamaria) [[论文]](https://arxiv.org/abs/2408.08332)
- [Nymeria](https://arxiv.org/abs/2406.09905) — Meta Reality Labs（ECCV 2024）。最大规模野外全身运动数据集；264 名参与者、300 小时，用 Aria 眼镜采集。
- [HOT3D](https://facebookresearch.github.io/hot3d/) — Meta（2024）。第一人称 3D 手-物交互跟踪；833 段序列，由 Aria + Quest 3 采集，是官方 BOP 数据集之一。[[论文]](https://arxiv.org/abs/2406.09598) [[代码]](https://github.com/facebookresearch/hot3d)
- [HD-EPIC](https://hd-epic.github.io/) — 多机构联合（CVPR 2025）。高细节第一人称视频数据集；41 小时非脚本厨房视频，逐帧 3D / 手 / 语音密集标注。[[论文]](https://arxiv.org/abs/2502.04144)
- [EgoXtreme](https://arxiv.org/abs/2410.07639) — 极端环境第一人称 6D 物体姿态估计基准；由 15 位参与者佩戴 Aria 眼镜在极端低照、剧烈运动模糊和烟雾场景（工业检修、运动、应急救援）下采集 130 万帧（775 分钟）。
- [LookOut / AND](https://arxiv.org/abs/2508.14466) —（ICCV 2025）。真实人形第一人称导航数据集；约 4 小时 Aria 导航录制，面向基于 VLM 的导航。

### 程序性活动理解与失误检测

- [CaptainCook4D](https://captaincook4d.github.io/captain-cook/) — 佛罗里达大学（CVPR 2024）。首个第一人称 4D 复杂烹饪操作与失误检测基准；384 段录制（94.5 小时），标注 5.3K 步骤与 10K 细粒度动作，显式构建按规执行（Correct）与步骤偏离/诱发失误（Erroneous）对照组。[[代码]](https://github.com/CaptainCook4D/CaptainCook4D) [[论文]](https://arxiv.org/abs/2312.14441)
- [IndEgo](https://indego-dataset.github.io/) — Fraunhofer IPK 等（NeurIPS 2025）。大规模工业作业与人机协同多模态数据集；3,460 段第一人称（~197 小时）+ 1,092 段外部多视角（~97 小时），覆盖工业装配、物流检修，集成眼动、双手姿态、失误检测与推理 VQA 基准。[[数据]](https://huggingface.co/datasets/FraunhoferIPK/IndEgo) [[论文]](https://arxiv.org/abs/2511.19684)
- [EPFL-Smart-Kitchen-30](https://cnai.epfl.ch/EPFL-Smart-Kitchen) — 洛桑联邦理工 EPFL / 微软（NeurIPS 2025）。多模态多视角厨房动作与人体运动学基准；16 名受试者烹饪 4 种食谱（29.7 小时），同步 9 路第三人称 RGB-D + 第一人称 HoloLens 2，含深度、IMU、眼动与高精度 3D 骨骼关节学真值。[[代码]](https://github.com/amathislab/EPFL-Smart-Kitchen) [[论文]](https://arxiv.org/abs/2506.01608)
- [EgoProceL](https://github.com/Sid2697/EgoProceL-egocentric-procedure-learning) — IIIT Hyderabad（ECCV 2022）。第一人称程序性学习基准；130 名受试者 16 项日常与制作任务（62 小时），专注于跨视频非监督关键步骤发现与对齐。[[论文]](https://arxiv.org/abs/2207.10883)
- [EgoExoLearn](https://egoexolearn.github.io/) — 上海人工智能实验室 / OpenGVLab（CVPR 2024）。大规模异步 ego-exo 程序性活动数据集，1000+ 小时分层程序标注。[[论文]](https://arxiv.org/abs/2403.16182) [[代码]](https://github.com/OpenGVLab/EgoExoLearn)

### 第一人称视频理解、大模型与视听具身

- [EgoBlind](https://github.com/doc-doc/EgoBlind) — 华盛顿大学 / 腾讯等（NeurIPS 2025）。首个面向视障人群真实需求的第一人称 VideoQA 基准；1,392 段真实盲人生活视频，5,311 个由视障者直接提出或验证的真实问答，评估多模态大模型在弱视力辅助中的认知与可靠回答能力。[[论文]](https://arxiv.org/abs/2503.08221)
- [EgoAVU](https://arxiv.org/abs/2410.11623) —（2024）。第一人称视听具身理解评测套件；含 300 万条指令微调数据（EgoAVU-Instruct）与高精度评测基准（EgoAVU-Bench），覆盖视听定位、时序推理与防幻觉。
- [EgoThink](https://adacheng.github.io/EgoThink/) —（CVPR 2024 Highlight）。评估 VLM 第一人称"思考"的基准，六类任务，选自 Ego4D。[[论文]](https://arxiv.org/abs/2311.15596) [[代码]](https://github.com/AdaCheng/EgoThink)
- [VidEgoThink](https://adacheng.github.io/VidEgoThink/) —（2024）。第一人称视频理解评测；约 400 个视频问答样本。[[论文]](https://arxiv.org/abs/2410.11623)
- [EgoVideo](https://arxiv.org/abs/2406.18070) — 上海人工智能实验室 / OpenGVLab（2024）。在大型预训练数据上训练的第一人称视频基础模型。[[代码]](https://github.com/OpenGVLab/EgoVideo)
- [EgoTempo](https://arxiv.org/abs/2503.13646) — Google Research 等（CVPR 2025）。评测多模态大模型在第一人称视频中的时序理解。[[代码]](https://github.com/google-research-datasets/egotempo)
- [EgoLife](https://egolife-ai.github.io/blog/) — 南洋理工大学（CVPR 2025）。超长（周级）AI 生活助手数据集；6 名参与者、300 小时，含 EgoLifeQA 基准。[[论文]](https://arxiv.org/abs/2503.03803) [[代码]](https://github.com/EvolvingLMMs-Lab/EgoLife)
- [EgoThinker / EgoRe-5M](https://arxiv.org/abs/2510.23569) —（NeurIPS 2025）。第一人称推理数据集，500 万因果 CoT 问答样本 + 手物标注。
- [EgoCVR](https://arxiv.org/abs/2407.16658) —（ECCV 2024）。第一人称细粒度组合式视频检索基准。
- [OpenMMEgo (OME10M)](https://proceedings.neurips.cc/paper_files/paper/2025/file/24b9e3da4b01ec1e8a41144cfe8dc929-Paper-Conference.pdf) —（NeurIPS 2025）。千万级第一人称时空视频知识数据集，用于增强多模态大模型。
- [EVUD](https://github.com/alanaai/EVUD) — alanaai（2026）。面向视频大模型的 第一人称视频指令微调数据集。
- [EgoVid-5M](https://egovid.github.io/) — 阿里巴巴 / 中科院自动化所等（NeurIPS 2025 Datasets & Benchmarks）。首个面向第一人称视频生成的大规模数据集；**500 万段** 1080p 片段，含 500 万条高层文本描述与 6.5 万条细粒度运动学控制标注，并配套专用清洗流水线。[[论文]](https://arxiv.org/abs/2411.08380) [[代码]](https://github.com/JeffWang987/EgoVid)
- [EgoObjects](https://github.com/facebookresearch/EgoObjects) — Meta AI（ICCV 2023）。第一人称细粒度物体理解数据集；**9,000+ 段视频 / 250 名采集者 / 11.4 万标注帧 / 1.44 万个物体实例 / 368 类**，支持类别级与实例级物体检测。MIT 许可。[[论文]](https://arxiv.org/abs/2309.08816)
- [EgoExo-Fitness](https://github.com/iSEE-Laboratory/EgoExo-Fitness) — 中山大学（ECCV 2024）。同步第一人称 + 第三人称全身动作理解数据集；两级时序边界，并提供技术关键点校验、自然语言点评与**动作质量评分**。[[下载]](https://huggingface.co/datasets/Lymann/EgoExo-Fitness)
- [Ego-1K](https://huggingface.co/datasets/facebook/ego-1k) —（CVPR 2026）。大规模时间同步第一人称**多视角**视频数据集；近 1,000 段短视频，由 12 台同步相机环绕佩戴 VR 头显的用户采集，聚焦手部运动与手-物交互，面向 3D/4D 新视角合成与具身感知。
- [RekaDaily-10k](https://huggingface.co/datasets/RekaAI/RekaDaily-10k-raw) — Reka AI（2026）。增量发布的超大规模无脚本第一人称日常生活视频；当前含 **7,834 小时 / 397,171 段视频**，Apache-2.0 开放许可。

### 手-物交互、3D 姿态与灵巧操作

- [EgoDex](https://github.com/apple/ml-egodex) — Apple（2025）。最大规模第一人称灵巧操作数据集；829+ 小时，用 Vision Pro 采集并含 3D 手部姿态。[[论文]](https://arxiv.org/abs/2505.11709)
- [EPIC-Contact](https://sid2697.github.io/epic-contact) — 布里斯托大学（ECCV 2026）。真实厨房双手与物体接触 3D 姿态基准；从 EPIC-KITCHENS 标注 2.3K 片段（6.23 万帧），提供密集双向 3D 手-物接触对应与网格，配套 HOPformer 模型。[[代码]](https://github.com/Sid2697/HOPformer) [[论文]](https://arxiv.org/abs/2606.30598) [[数据]](https://huggingface.co/datasets/Sid2697/epic-contact)
- [EgoBody](https://egobody.ethz.ch/) — 苏黎世联邦理工 ETH Zurich（ECCV 2022）。大规模第一人称社交交互与 3D 人体运动捕捉基准；头戴设备同步采集复杂真实 3D 场景下多人的全身姿态与交互网格。[[论文]](https://arxiv.org/abs/2112.07642)
- [UnrealEgo / UnrealEgo2](https://unrealego.mpi-inf.mpg.de/) — 马克斯·普朗克研究所 MPI-INF（ECCV 2022 / CVPR 2024）。立体双目鱼眼第一人称 3D 人体姿态估计开山基准与挑战赛平台；含逼真合成与真实世界测试集，配套 EgoPoseFormer 基线。[[代码]](https://github.com/hiroyasuakada/UnrealEgo) [[论文]](https://arxiv.org/abs/2208.01633)
- [OpenEgo](https://arxiv.org/abs/2509.05513) —（2025）。大规模多模态第一人称灵巧操作数据集。
- [EgoSim / MultiEgoView](https://arxiv.org/abs/2502.18373) —（NeurIPS 2024）。第一人称多视角模拟器 + 真实数据集。
- [EMHI](https://arxiv.org/abs/2408.17168) —（2024）。多模态第一人称人体运动数据集。

### 规模化人类视频与具身预训练（2025–2026）

> 这一子类对应文末 VLA 章节的核心主线：把规模化第一人称人类视频转化为可用的动作信号，用于具身预训练。其中 Assembly-101、HOI4D、HoloAssist、RH20T-Human 是 Gr00T N1 明确列出的 egocentric 训练来源。

- [EgoScale](https://arxiv.org/abs/2602.16710) — UT Austin / NVIDIA 等（2026）。规模化人类到灵巧操作迁移框架；在 **20,854 小时**动作标注第一人称人类视频上训练 VLA，首次揭示人类数据规模与验证损失之间的 **log-linear scaling law**，并证明该损失与真机成功率强相关，最终策略较无预训练基线成功率 **+54%**。
- [EgoVerse](https://egoverse.ai/) — UC Berkeley / Stanford / Meta 等多机构（RSS 2026）。跨机构协作的人类数据驱动机器人学习平台；当前发布 **1,362 小时 / 8 万 episodes / 1,965 个任务 / 240 个场景 / 2,087 名演示者**，含标准化格式与多实验室 human-to-robot 迁移复现研究。[[论文]](https://arxiv.org/abs/2604.07607)
- [EgoLive](https://arxiv.org/abs/2604.23570) —（2026）。面向机器人操作学习的大规模第一人称数据集；**1,680 小时** 2160×2160 立体 60fps 视频、**65,866 个 episode / 346 个真实任务**，全部采集于家政、零售、药房等无约束真实工作场景。
- [Egocentric-10K](https://huggingface.co/datasets/builddotai/Egocentric-10K) — Build AI（2025）。迄今规模最大的第一人称数据集；**10,000 小时 / 10.8 亿帧 / 192,900 段**，全部采集于真实工厂，手部可见度与主动操作密度领先同类。⚠️ **门控数据集**，详见[商业受限与门控数据集](#商业受限与门控数据集)。[[评估集]](https://huggingface.co/datasets/builddotai/Egocentric-10K-Evaluation)
- [HumanNet](https://dagroup-pku.github.io/HumanNet/) — 北京大学等（2026）。**百万小时**人类中心视频语料，覆盖第一人称与第三人称视角，提供以交互为中心的标注；受控实验表明 **1,000 小时 egocentric 视频优于 100 小时真机数据**。[[论文]](https://arxiv.org/abs/2605.06747) [[代码]](https://github.com/DAGroup-PKU/HumanNet)
- [EgoMimic](https://egomimic.github.io/) — 佐治亚理工学院（2024）。以第一人称视频 + 手部追踪进行模仿学习的早期代表，约 4 小时数据、3 个任务，是 EgoDex 的直接方法学前驱。[[论文]](https://arxiv.org/abs/2410.24221)
- [Assembly-101](https://assembly-101.github.io/) — Meta Reality Labs / 新加坡国立大学（CVPR 2022）。大规模多视角程序性活动数据集；参与者组装 101 款儿童玩具，提供手-物交互的无标记动作捕捉与多级动作标注。**Gr00T N1 的 egocentric 训练来源之一**。[[论文]](https://arxiv.org/abs/2212.04501) [[下载]](https://huggingface.co/datasets/cvml-nus/assembly101)
- [HOI4D](https://hoi4d.github.io/) — 清华大学 / 北京大学（CVPR 2022）。类别级第一人称 4D 人-物交互数据集；**240 万 RGB-D 帧 / 4,000 段序列 / 9 名参与者 / 800 个物体实例 / 16 类 / 610 个室内场景**，含全景分割、运动分割、3D 手部姿态与类别级物体姿态标注。**Gr00T N1 的 egocentric 训练来源之一**。[[论文]](https://arxiv.org/abs/2203.01577)
- [HoloAssist](https://holoassist.github.io/) — 微软（ICCV 2023）。真实世界第一人称人类交互数据集；**169 小时 / 350 对**指导者-执行者，每位执行者佩戴 MR 头显采集 7 路同步数据流（含深度、手部姿态、眼动、IMU），面向交互式 AI 助手。**Gr00T N1 的 egocentric 训练来源之一**。[[论文]](https://arxiv.org/abs/2309.17024)
- [RH20T / RH20T-Human](https://rh20t.github.io/) — 上海交通大学（2023）。**11 万+** 接触密集型机器人操作序列，每条均配对应的人类演示视频；RH20T-Human 为其人类演示子集，是 Gr00T N1 的 egocentric 训练来源之一。[[论文]](https://arxiv.org/abs/2307.00595)

### 长期记忆与第一人称视频问答

- [HourVideo](https://hourvideo.stanford.edu/) — 斯坦福大学等（NeurIPS 2024）。超长第一人称视频语言理解基准；500 段 20–120 分钟未修剪长视频，12,976 道人工多选问答，评测长时程记忆、时序/因果推理与导航。[[论文]](https://arxiv.org/abs/2411.04998)
- [SuperMemory-VQA](https://arxiv.org/abs/2606.00825) —（2026）。第一人称 VQA 数据集，52.9 小时 AI 眼镜日常录制，用于长期记忆推理。
- [EgoMemReason](https://egomemreason.github.io/) —（2026）。记忆驱动的长期第一人称视频推理基准（周级）。
- [MyEgo](https://github.com/Ryougetsu3606/MyEgo) —（CVPR 2026）。个性化第一人称 VideoQA 基准；541 段长视频、5,000 个围绕佩戴者私人物品、日常活动与个人历史轨迹的个性化问答，评测 MLLM 的自我中心意图与 Ego-Grounding 能力。

## 经典数据集

以下为经典的第一人称数据集（2023 年之前），链接已更新到其当前官方页面。

- [Ego4D](https://ego4d-data.org/) — 约 **3,670 小时**日常活动第一人称视频（v1 为 3,025 小时），来自全球 9 个国家的 74 个地点、855 位佩戴者，部分含注视、立体双目与多机位同步。需签署学术许可，通过后约 48 小时提供 AWS 凭证。[[文档](https://ego4d-data.org/docs/)] [[代码与下载工具](https://github.com/facebookresearch/Ego4d)]
- [EgoHands](http://vision.soic.indiana.edu/projects/egohands/) — 印第安纳大学（CVPR 2015）。经典第一人称手部检测与交互基准；48 段高分辨率双手交互视频，涵盖下棋、拼图等桌上协同，包含 1.5 万+ 帧逐像素精细手部分割与交互标注。[[论文]](https://ieeexplore.ieee.org/document/7298642)
- [EgoCom](https://github.com/facebookresearch/EgoCom-Dataset) — 自然对话数据集，多模态人机沟通数据，从参与者第一人称视角同步采集。
- [EPIC-Kitchens](https://epic-kitchens.github.io/) — 第一人称厨房场景经典基准，参与者在原生环境中进行非脚本动作（含 EPIC-KITCHENS-55、EPIC-KITCHENS-100 及 2018/2020 版本），在动作识别和手-物交互研究中应用最为广泛。
- [EPIC-Tent](https://data.bris.ac.uk/data/dataset/2ite3tu1u53n42hjfh3886sa86) — 29 名参与者佩戴两个头戴相机搭建帐篷。[[论文]](https://ieeexplore.ieee.org/document/9022634)
- [MECCANO](https://iplab.dmi.unict.it/MECCANO/) — 20 名受试者组装玩具摩托车。[[代码]](https://github.com/fpv-iplab/MECCANO)
- [EGO-CH](https://iplab.dmi.unict.it/EGO-CH/) — 70 名受试者参观意大利西西里两处文化遗址。
- [EGTEA Gaze+](http://cbs.ic.gatech.edu/fpv/) — 32 名受试者、86 次烹饪、28 小时带注视信息的第一人称烹饪视频。[[镜像](https://ai.stanford.edu/~alireza/GTEA_Gaze_Website/)]
- [ADL](https://web.cs.ucdavis.edu/~hpirsiav/papers/ADLdataset/) — 20 名受试者在原生环境中进行日常活动。
- [CMU Kitchen](http://kitchen.cs.cmu.edu/) — 多模态，18 名受试者烹饪 5 种食谱（布朗尼、鸡蛋、披萨、沙拉、三明治）。
- [EgoSeg](http://www.vision.huji.ac.il/egoseg/) — 长期动作分割（行走、跑步、驾驶等）。
- [First-Person Social Interactions](http://ai.stanford.edu/~alireza/Disney/) — 8 名受试者在迪士尼乐园的第一人称社交交互。
- [UEC Dataset](http://www.cs.cmu.edu/~kkitani/datasets/) — 两个编排的第一人称动作数据集（走、跳、攀爬等）+ 6 段 YouTube 运动视频。
- [JPL](http://michaelryoo.com/jpl-interaction.html) — 与机器人的第一人称交互。
- [FPPA](http://tamaraberg.com/prediction/Prediction.html) — 5 名受试者执行 5 种日常动作，用于动作预测。
- [UT Egocentric](https://vision.cs.utexas.edu/projects/egocentric_data/UT_Egocentric_Dataset.html) — 3–5 小时长视频，记录一个人的一天。
- [VINST / Visual Diaries](http://www.csc.kth.se/cvap/vinst/NovEgoMotion.html) — 31 段视频，记录受试者从地铁站步行到工作地点的视觉体验。
- [BEOID (Bristol Egocentric Object Interaction)](https://www.cs.bris.ac.uk/~damen/BEOID/) — 8 名受试者、六个地点；与物体和环境的交互。
- [Object Search Dataset](https://github.com/Mengmi/deepfuturegaze_gan) — 55 名受试者的 57 段序列，用于搜索与检索任务。
- [UNICT-VEDI](http://iplab.dmi.unict.it/VEDI/) — 受试者参观博物馆。
- [EgoGesture](http://www.nlpr.ia.ac.cn/iva/yfzhang/datasets/egogesture.html) — 50 名受试者执行 83 种手势的 2k 段视频。
- [DoMSEV](http://www.verlab.dcc.ufmg.br/semantic-hyperlapse/cvpr2018-dataset/) — 不同活动共 80 小时的第一人称视频。
- [DR(eye)VE](https://aimagelab-legacy.ing.unimore.it/imagelab/page.asp?IdPage=8) — 74 段带注视信息的人驾驶视频。
- [EgoDexter](https://handtracker.mpi-inf.mpg.de/projects/OccludedHands/EgoDexter.htm) — 4 段序列、4 名演员，在杂乱背景中进行多样手-物交互。[[论文]](https://handtracker.mpi-inf.mpg.de/projects/OccludedHands/index.htm)
- [First-Person Hand Action (FPHA)](https://guiggh.github.io/publications/first-person-hands/) — 3D 手-物交互；6 名演员、45 个活动类别、1175 段视频。[[论文]](https://arxiv.org/pdf/1704.02463.pdf)
- [UTokyo PEV / Ego-Surf](https://www.ut-vision.org/resources/) — 面对面交谈中同步录制的成对第一人称片段（PEV）与群组第一人称视频（Ego-Surf）。
- [TEgO](https://iamlabumd.github.io/tego/) — 可教学第一人称物体；19 个不同物体的图像，用于训练可教学物体识别器。
- [Multimodal Focused Interaction](https://discovery.dundee.ac.uk/en/datasets/multimodal-focused-interaction-dataset/) — 19 段会话、17 位对话伙伴、377 分钟的连续多模态录制。
- [TREK-100](https://opendatalab.com/OpenDataLab/TREK-100) — 第一人称视觉中的目标跟踪（100 段视频）。
- [Charade-Ego](https://prior.allenai.org/projects/charades-ego) — 成对的第一人称与第三人称日常活动视频。

## 商业受限与门控数据集

以下数据集规模可观，但**需要申请访问（gated）或存在商业使用限制**。收录时请务必先确认其许可条款，**切勿直接用于商业用途**：

- [Egocentric-10K](https://huggingface.co/datasets/builddotai/Egocentric-10K) — 10,000 小时 / 10.8 亿帧，真实工厂场景。**门控**：需同意条款并提交联系方式。同系列 [Egocentric-100K](https://huggingface.co/datasets/builddotai/Egocentric-100K) 规模约 100,405 小时 / 108 亿帧。
- [Xperience-10M](https://huggingface.co/datasets/ropedia-ai/xperience-10m) — 约 1 万小时 / 近 1 PB，多传感器同步采集。**门控，自定义许可（other）**。
- [EgoSuite-Open100K](https://huggingface.co/collections/LightwheelAI/egosuite-open100k) — 规划 10 万小时第一人称人类活动数据（首期 1 万小时已开放）。**商用训练受限**。
- [Ego500](https://huggingface.co/datasets/humanarchive/ego500) — 500 小时第一人称工作视频 / 31 万+ 结构化动作标注。**门控，CC-BY-NC-4.0（非商用）**。
- [Nexdata 10,000-Hour Egocentric Video](https://huggingface.co/datasets/Nexdata-AI/10000-Hour-Egocentric-Video-Dataset) — 10,000 小时，PICO 4 Ultra 4K 立体视频。**商用门控**。
- [Datoric Industrial Egocentric Video](https://huggingface.co/datasets/Datoric/industrial-egocentric-video-50000h) — 50,000 小时工业场景。**商用门控**。
- [Datoric Residential Egocentric Video](https://huggingface.co/datasets/Datoric/egocentric-residential-video-100000h) — 100,000 小时住宅场景。**商用门控**。
- [EgoBrain](https://huggingface.co/datasets/ut-vision/EgoBrain) — 1.6 TB / 40 名参与者。**门控，CC-BY-NC-4.0（非商用）**。

> **许可提醒**：本清单中另有多条数据集的原始许可本身即限制商用，例如 [EgoDex](https://github.com/apple/ml-egodex) 为 **CC-BY-NC-ND**（署名-非商用-禁演绎）、[HOT3D](https://facebookresearch.github.io/hot3d/) 与 [Ego-Exo4D](https://ego-exo4d-data.org/) 亦为非商用研究许可。引用前请逐一核对官方许可页。

## 参与贡献

欢迎贡献。要新增或修正数据集条目，请发起 Pull Request 或 Issue。请确保：

- 数据集与 egocentric / 第一人称视觉相关。
- 官方链接可访问。
- 附带一行描述（机构、任务、规模）。

## 许可

本清单以 [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) 提供。各数据集的许可证以各自链接为准。

---

# Egocentric 视角下的 VLA 论文（2023.08 – 2026.08）

> 抓大放小，只保留与 **egocentric（第一人称）数据** 直接相关的论文。收录标准：
> **① 以 egocentric 数据作为训练来源**（egocentric 人类视频 / 可穿戴视角作为 VLA 预训练或微调输入）；
> **② 针对 egocentric 数据做加工改进**（质检、清洗、标注、伪标签、训练方法）。
> 与 egocentric 无关的通用 VLA 里程碑（RT-2、OpenVLA、π0 系列、Octo、DexVLA、WorldVLA 等）不在本清单。

## 一句话结论（金字塔之顶）

**egocentric 人类视频之于 VLA，是一条"取之不尽、尚未充分开采"的训练水源；这三年的范式主线是「如何把第一人称视频变成可用的动作信号」——先直接用人手/手腕动作作标签，再发展为"伪标签 + 互联网预训练"，再到"一套流水线同时解决质检、标注与训练"，最终证明经过良好加工的第一人称数据可以匹敌甚至超过真实机器人数据。**

## 第一性原理：egocentric 数据在 VLA 里卡在哪？（金字塔之基）

要拿第一人称视频训练 VLA，本质要打通三件事：

1. **动作从哪来** —— 第一人称视频**没有动作标签**，只有人眼看到的人手/手腕运动，如何得到 $P(a_t)$？
2. **数据如何干净** —— 原始第一人称视频含噪声、不完整轨迹、视角/本体差异，如何质检、清洗、标注？
3. **学完怎么用** —— 人类视频学到的"人怎么做"，如何迁移到机器人/不同本体？

三年所有与 egocentric 相关的 VLA 工作，都落在**打通这三件事**上：

| 维度 | 直接做人手标签 | 伪标签 / 互联网预训练 | 流水线加工 + 训练 |
|---|---|---|---|
| 动作来源 | 人手/手腕动作直接预测（EgoVLA、Ego-Pi） | latent action 伪标注，egocentric 视频入预训练（Gr00T N1、LAPA） | 自动轨迹提取 + 可靠性加权（EgoScaler、ACE-Ego-0） |
| 数据加工 | 依赖手部标注 | 少量依赖、伪标签化 | **质检/清洗/标注一体化流水线**（EgoScaler、HumanScale） |
| 下游迁移 | 逆运动学重定向到机器人 | 统一进基础模型 | 与机器人数据联合训练 |

**核心逻辑**：egocentric 数据的价值上限，取决于"加工成本"与"动作信号质量"的比值。每一篇论文都是在降低加工成本、或提升动作信号质量——这条判据可解释整个时间线。

## 里程碑时间线（金字塔之身，按第一性原理分层）

### 第一层：egocentric 视频直接入 VLA（2025）

- **Gr00T N1**（2025-03，[arXiv:2503.14734](https://arxiv.org/abs/2503.14734)，NVIDIA）—— **①类（训练来源，最强相关）**：数据金字塔底部明确纳入 **7 个 egocentric 人类视频数据集**（Ego4D、Ego-Exo4D、EPIC-KITCHENS、Assembly-101、HOI4D、HoloAssist、RH20T-Human），用 **VQ-VAE latent action / IDM 伪标注**统一训练，首次把"第一人称人类视频"大规模搬进人形 VLA 基础模型。
- **EgoVLA**（2025-07，[arXiv:2507.12440](https://arxiv.org/abs/2507.12440)）—— **①类（训练来源）**：直接用 egocentric 人类视频训练 VLA，**预测人手/手腕动作**，再经逆运动学/重定向转成机器人动作；自建 Ego Humanoid Manipulation Benchmark 双机械臂任务评测，证明第一人称视频可训出可迁移的 VLA。

### 第二层：把加工做成流水线（2025）

- **EgoScaler**（2025-09，[arXiv:2509.21986](https://arxiv.org/abs/2509.21986)）—— **②类（数据标注/清洗）**：从**原始 egocentric 视频自动提取 6DoF 物体操作轨迹**（无需额外手部标注），自动修正噪声/不完整轨迹，构建大规模 VLA 预训练数据集；基于 π0 架构验证预训练提升 20%+。解决"动作从哪来 + 数据如何干净"。

### 第三层：egocentric 与机器人数据联合、并证明其价值（2026）

- **Ego-Pi**（2026-06，[arXiv:2606.08107](https://arxiv.org/abs/2606.08107)）—— **①类（训练来源）**：以 π0.5 为基座，在带五指的类人机器人上**联合学习 egocentric 人类数据与机器人数据**，证明第一人称数据能让机器人学到"无对应机器人数据"的任务语义并组合技能。
- **ACE-Ego-0**（2026-06，[arXiv:2606.17200](https://arxiv.org/abs/2606.17200)）—— **②类（标注流水线 + 训练）**：构建**可扩展的 egocentric 视频→动作标注流水线**，将原始人类视频转成机器人格式伪动作轨迹，并用**可靠性加权训练**抑制伪标签噪声；联合 1.48K 小时 egocentric 人类数据 + 机器人数据预训练。
- **HumanScale**（2026-06，[arXiv:2606.20521](https://arxiv.org/abs/2606.20521)）—— **① + ② 类**：系统对比 egocentric 人类视频 vs 遥操作机器人轨迹作为具身预训练来源，发现经**精心设计的过滤 + 标注流水线**后，egocentric 数据可**超越真实机器人数据**（验证损失 −24%，成功率显著提升）。这是"egocentric 数据加工价值"最强论据。

### 附：混合预训练来源中的 egocentric 成分

- **LAPA**（2024-10，[arXiv:2410.11758](https://arxiv.org/abs/2410.11758)，ICLR 2025）—— **①类（部分）**：以"无动作标签的互联网视频学 latent action"为核心；其混合预训练数据含 **Something-Something V2**（论文标注为第一人称人类操作视频），egocentric 是其预训练来源之一（非主线，但属 egocentric 数据入 VLA 的早期代表）。

> 去噪音说明：π0/π0.5/π0.6/π0.7、OpenVLA、RDT-1B、DexVLA、Octo、RT-X 等虽属 VLA 主线，但其预训练/微调数据**不含 egocentric 人类数据**（多为机器人轨迹/通用互联网图文），与 egocentric 无关，故不收录。Nova、PaSa 无法核实，亦不收录。

## 鱼骨图（Fishbone：egocentric 数据如何驱动 VLA 训练）

```
                ┌──────────── 结果：用第一人称人类视频驱动 VLA 训练 ─────────────┐
                │                                                              │
   动作来源      │             数据加工（质检/标注）      │       下游迁移 / 训练
  （动作从哪来） │              （数据如何干净）          │     （学完怎么用）
                │                                        │
        ┌───────┴────────┐                     ┌─────────┴─────────┐
        │ 直接预测人手/    │                     │ 迁移到机器人       │
        │ 手腕动作         │                     │ (IK 重定向)        │
        │ (EgoVLA 25)     │                     │ (EgoVLA 25)       │
        └───────┬────────┘                     └─────────┬─────────┘
                │                                        │
        ┌───────┴────────┐                     ┌─────────┴─────────┐
        │ 伪标签 latent  │                     │ 联合机器人数据     │
        │ action (VQ-VAE)│                     │ co-training       │
        │ (Gr00T N1 25)  │                     │ (Ego-Pi 26)       │
        └───────┬────────┘                     └─────────┬─────────┘
                │                                        │
                └───────────┬────────────────────────────┘
                            │
            ┌───────────────┴───────────────┐
            │  自动轨迹提取 / 伪标签         │
            │  (EgoScaler 25)               │
            └───────────────┬───────────────┘
                            │
            ┌───────────────┴───────────────┐
            │  标注流水线 + 可靠性加权       │
            │  过滤/质检 (ACE-Ego-0,         │
            │  HumanScale 26)               │
            └───────────────┬───────────────┘
                            │
            ┌───────────────┴───────────────┐
            │  egocentric > 机器人数据       │
            │  (HumanScale 26 结论)          │
            └───────────────────────────────┘
```

**读图方式**：主骨是"用第一人称数据驱动 VLA 训练"；三根大刺分别为"动作来源 / 数据加工 / 下游迁移"。鱼骨中部自左向右，代表"加工流水线"越做越完整（自动提取 → 标注流水线 → 过滤质检 → 超越机器人数据），即该维度不断"去人工、去噪声"的演进方向。
