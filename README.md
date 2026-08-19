# Awesome Egocentric Dataset（第一人称视觉数据集精选）

> 精选的 **egocentric（第一人称）视觉数据集**清单 —— 从经典基准到 2023–2026 最新发布。

覆盖日常活动理解、手-物交互、导航、视频-语言、长期记忆等研究方向。

## 目录

- [关于](#关于)
- [近年新数据集（2023–2026）](#近年新数据集20232026)
  - [Ego4D / Ego-Exo4D 与基准](#ego4d--ego-exo4d-与基准)
  - [智能眼镜与 Project Aria](#智能眼镜与-project-aria)
  - [第一人称视频理解与视频大模型](#第一人称视频理解与视频大模型)
  - [手-物交互与灵巧操作](#手-物交互与灵巧操作)
  - [长期记忆与第一人称视频问答](#长期记忆与第一人称视频问答)
- [经典数据集](#经典数据集)
- [已剔除样本](#已剔除样本)
- [参与贡献](#参与贡献)
- [许可](#许可)
- [Egocentric 视角下的 VLA 论文（2023.08 – 2026.08）](#egocentric-视角下的-vla-论文202308--202608)

## 关于

本仓库维护一份持续更新的第一人称视觉数据集清单。它借鉴了广受引用的
[Egocentric-Dataset](https://github.com/EgoAlpha/Egocentric-Dataset) 清单（该清单停更于 2022 年），并做了如下刷新：

- **剔除**官方页面已失效或不再维护的数据集。
- **更新**已迁移到新官方页面的数据集链接。
- **新增**最近三年（2023–2026）发布的重要数据集。

每个条目都附简要描述（机构、任务类型、规模，若已知）。

## 近年新数据集（2023–2026）

### Ego4D / Ego-Exo4D 与基准

- [Ego-Exo4D](https://ego-exo4d-data.org/) — Meta AI / UIUC（2023，NeurIPS）。大规模多模态多视角数据集，包含同步的第一人称 + 多路第三人称视频，覆盖熟练人类活动（约 116 小时），含 3D 手/身体/注视标注与基准。[[论文]](https://arxiv.org/abs/2311.18259) [[代码]](https://github.com/facebookresearch/Ego4d)
- [EgoSchema](https://egoschema.github.io/) — 加州大学伯克利分校 BAIR（CVPR 2024）。超长视频理解诊断基准；约 5,000 段 180 秒 Ego4D 片段 + 人工标注选择题。[[论文]](https://arxiv.org/abs/2308.09126)
- [EgoTracks](https://ego4d-data.org/docs/data/egotracks/) — Meta AI（2023）。基于 Ego4D 的长期目标跟踪基准，5.9k 视频中约 22.42k 条轨迹。
- [EgoPet](https://www.amirbar.net/egopet/) — Technion（ECCV 2024）。动物第一人称视频数据集（自我运动 + 交互），含三个行为基准任务。[[论文]](https://arxiv.org/abs/2404.09991)
- [EgoHumans](https://rawalkhirodkar.github.io/egohumans/) — 卡内基梅隆大学（ICCV 2023）。首个野外多人体 3D 理解第一人称基准；12.5 万+ 图像，含 SMPL / SMPL-X 标注。[[论文]](https://arxiv.org/abs/2305.16487)

### 智能眼镜与 Project Aria

- [Aria Everyday Activities (AEA)](https://www.projectaria.com/datasets/aea/) — Meta Reality Labs（CVPR 2024）。来自 Aria 智能眼镜的开放多模态日常活动数据集；143 段（约 18 小时），含 IMU / 眼动。[[论文]](https://arxiv.org/abs/2402.13349)
- [Aria Digital Twin (ADT)](https://www.projectaria.com/datasets/adt/) — Meta Reality Labs（2023）。用 Aria 采集的第一人称 3D 基准，配大规模仿真真值（设备/物体/场景 3D）。[[论文]](https://arxiv.org/abs/2306.06362)
- [Nymeria](https://arxiv.org/abs/2406.09905) — Meta Reality Labs（ECCV 2024）。最大规模野外全身运动数据集；264 名参与者、300 小时，用 Aria 眼镜采集。
- [HOT3D](https://facebookresearch.github.io/hot3d/) — Meta（2024）。第一人称 3D 手-物交互跟踪；833 段序列，由 Aria + Quest 3 采集，是官方 BOP 数据集之一。[[论文]](https://arxiv.org/abs/2406.09598) [[代码]](https://github.com/facebookresearch/hot3d)
- [HD-EPIC](https://hd-epic.github.io/) — 多机构联合（CVPR 2025）。高细节第一人称视频数据集；41 小时非脚本厨房视频，逐帧 3D / 手 / 语音密集标注。[[论文]](https://arxiv.org/abs/2502.04144)
- [LookOut / AND](https://arxiv.org/abs/2508.14466) —（ICCV 2025）。真实人形第一人称导航数据集；约 4 小时 Aria 导航录制，面向基于 VLM 的导航。

### 第一人称视频理解与视频大模型

- [EgoExoLearn](https://egoexolearn.github.io/) — 上海人工智能实验室 / OpenGVLab（CVPR 2024）。大规模异步 ego-exo 程序性活动数据集，1000+ 小时分层程序标注。[[论文]](https://arxiv.org/abs/2403.16182) [[代码]](https://github.com/OpenGVLab/EgoExoLearn)
- [EgoThink](https://adacheng.github.io/EgoThink/) —（CVPR 2024 Highlight）。评估 VLM 第一人称"思考"的基准，六类任务，选自 Ego4D。[[论文]](https://arxiv.org/abs/2311.15596) [[代码]](https://github.com/AdaCheng/EgoThink)
- [VidEgoThink](https://adacheng.github.io/VidEgoThink/) —（2024）。第一人称视频理解评测；约 400 个视频问答样本。[[论文]](https://arxiv.org/abs/2410.11623)
- [EgoVideo](https://arxiv.org/abs/2406.18070) — 上海人工智能实验室 / OpenGVLab（2024）。在大型预训练数据上训练的第一人称视频基础模型。[[代码]](https://github.com/OpenGVLab/EgoVideo)
- [EgoTempo](https://arxiv.org/abs/2503.13646) — Google Research 等（CVPR 2025）。评测多模态大模型在第一人称视频中的时序理解。[[代码]](https://github.com/google-research-datasets/egotempo)
- [EgoLife](https://egolife-ai.github.io/blog/) — 南洋理工大学（CVPR 2025）。超长（周级）AI 生活助手数据集；6 名参与者、300 小时，含 EgoLifeQA 基准。[[论文]](https://arxiv.org/abs/2503.03803) [[代码]](https://github.com/EvolvingLMMs-Lab/EgoLife)
- [EgoThinker / EgoRe-5M](https://arxiv.org/abs/2510.23569) —（NeurIPS 2025）。第一人称推理数据集，500 万因果 CoT 问答样本 + 手物标注。
- [EgoCVR](https://arxiv.org/abs/2407.16658) —（ECCV 2024）。第一人称细粒度组合式视频检索基准。
- [OpenMMEgo (OME10M)](https://proceedings.neurips.cc/paper_files/paper/2025/file/24b9e3da4b01ec1e8a41144cfe8dc929-Paper-Conference.pdf) —（NeurIPS 2025）。千万级第一人称时空视频知识数据集，用于增强多模态大模型。
- [EVUD](https://github.com/alanaai/EVUD) — alanaai（2026）。面向视频大模型的 第一人称视频指令微调数据集。

### 手-物交互与灵巧操作

- [EgoDex](https://github.com/apple/ml-egodex) — Apple（2025）。最大规模第一人称灵巧操作数据集；829+ 小时，用 Vision Pro 采集并含 3D 手部姿态。[[论文]](https://arxiv.org/abs/2505.11709)
- [OpenEgo](https://arxiv.org/abs/2509.05513) —（2025）。大规模多模态第一人称灵巧操作数据集。
- [EgoSim / MultiEgoView](https://arxiv.org/abs/2502.18373) —（NeurIPS 2024）。第一人称多视角模拟器 + 真实数据集。
- [EMHI](https://arxiv.org/abs/2408.17168) —（2024）。多模态第一人称人体运动数据集。

### 长期记忆与第一人称视频问答

- [SuperMemory-VQA](https://arxiv.org/abs/2606.00825) —（2026）。第一人称 VQA 数据集，52.9 小时 AI 眼镜日常录制，用于长期记忆推理。
- [EgoMemReason](https://egomemreason.github.io/) —（2026）。记忆驱动的长期第一人称视频推理基准（周级）。

## 经典数据集

以下为经典的第一人称数据集（2023 年之前），链接已更新到其当前官方页面。

- [Ego4D](https://ego4d-data.org/) — 3025 小时日常活动视频，来自 9 个国家的 74 个地点、855 位佩戴者。[[下载](https://ego4d.dev/)]
- [EgoCom](https://github.com/facebookresearch/EgoCom-Dataset) — 自然对话数据集，多模态人机沟通数据，从参与者第一人称视角同步采集。
- [EPIC-Kitchens](https://epic-kitchens.github.io/) — 参与者在原生环境中进行非脚本动作（含 EPIC-Kitchens 55、EPIC-KITCHENS-100 及 2018/2020 版本）。
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

## 已剔除样本

以下来自原 [Egocentric-Dataset](https://github.com/EgoAlpha/Egocentric-Dataset) 清单的数据集被**剔除**，因为其官方页面已无法访问、且无可靠官方镜像：

- **EgoHands** — 印第安纳大学官方页面已失效；仅剩非官方第三方镜像。
- **THU-READ** — 清华大学原页面无法访问；无可靠官方备份。

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
