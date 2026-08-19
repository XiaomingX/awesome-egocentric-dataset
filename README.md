# Awesome Egocentric Dataset

> A curated list of **egocentric (first-person) vision datasets** — from classic benchmarks to the latest 2023–2026 releases.

第一人称视觉（Egocentric / First-Person Vision）数据集精选清单，覆盖日常活动理解、手-物交互、导航、视频语言、长期记忆等研究方向。

## Table of Contents

- [About](#about)
- [Recent Datasets (2023–2026)](#recent-datasets-20232026)
  - [Ego4D / Ego-Exo4D & Benchmarks](#ego4d--ego-exo4d--benchmarks)
  - [Smart Glasses & Project Aria](#smart-glasses--project-aria)
  - [Egocentric Video Understanding & Video-LLMs](#egocentric-video-understanding--video-llms)
  - [Hand-Object Interaction & Dexterous Manipulation](#hand-object-interaction--dexterous-manipulation)
  - [Long-Term Memory & Egocentric Video QA](#long-term-memory--egocentric-video-qa)
- [Classic Datasets](#classic-datasets)
- [Removed Samples](#removed-samples)
- [Contributing](#contributing)

## About

This repository maintains an up-to-date list of egocentric vision datasets. It is inspired by the widely-referenced
[Egocentric-Dataset](https://github.com/EgoAlpha/Egocentric-Dataset) list (last updated 2022), refreshed to:

- **Remove** datasets whose official pages are no longer accessible or that are no longer maintained.
- **Update** links for datasets that have migrated to new official pages.
- **Add** the most important datasets released in the last three years (2023–2026).

Each entry includes a brief description covering the institution, task type, and scale where known.

## Recent Datasets (2023–2026)

### Ego4D / Ego-Exo4D & Benchmarks

- [Ego-Exo4D](https://ego-exo4d-data.org/) — Meta AI / UIUC (2023, NeurIPS). Large-scale multi-view multimodal dataset with synchronized egocentric + multi-view exocentric video of skilled human activities (~116h), with 3D hand/body/gaze annotations and benchmarks. [[paper]](https://arxiv.org/abs/2311.18259) [[code]](https://github.com/facebookresearch/Ego4d)
- [EgoSchema](https://egoschema.github.io/) — UC Berkeley BAIR (CVPR 2024). A diagnostic benchmark for very-long-form video understanding; ~5,000 180-second Ego4D clips with human-annotated multiple-choice questions. [[paper]](https://arxiv.org/abs/2308.09126)
- [EgoTracks](https://ego4d-data.org/docs/data/egotracks/) — Meta AI (2023). Long-term object tracking benchmark on Ego4D, with 22.42k tracks across 5.9k videos.
- [EgoPet](https://www.amirbar.net/egopet/) — Technion (ECCV 2024). Animal egocentric video dataset (egomotion + interaction) with three behavioral benchmark tasks. [[paper]](https://arxiv.org/abs/2404.09991)
- [EgoHumans](https://rawalkhirodkar.github.io/egohumans/) — CMU (ICCV 2023). First egocentric benchmark for multi-person 3D understanding in the wild; 125k+ images with SMPL / SMPL-X annotations. [[paper]](https://arxiv.org/abs/2305.16487)

### Smart Glasses & Project Aria

- [Aria Everyday Activities (AEA)](https://www.projectaria.com/datasets/aea/) — Meta Reality Labs (CVPR 2024). Open multimodal egocentric dataset from Aria smart glasses covering everyday activities; 143 sequences (~18h) with IMU / eye-gaze. [[paper]](https://arxiv.org/abs/2402.13349)
- [Aria Digital Twin (ADT)](https://www.projectaria.com/datasets/adt/) — Meta Reality Labs (2023). Egocentric 3D benchmark captured with Aria plus large-scale simulated ground truth (device / object / scene 3D). [[paper]](https://arxiv.org/abs/2306.06362)
- [Nymeria](https://arxiv.org/abs/2406.09905) — Meta Reality Labs (ECCV 2024). Largest in-the-wild full-body motion dataset; 300h from 264 participants captured with Aria glasses.
- [HOT3D](https://facebookresearch.github.io/hot3d/) — Meta (2024). Egocentric 3D hand-object interaction tracking; 833 sequences captured with Aria + Quest 3, an official BOP dataset. [[paper]](https://arxiv.org/abs/2406.09598) [[code]](https://github.com/facebookresearch/hot3d)
- [HD-EPIC](https://hd-epic.github.io/) — Multi-institution (CVPR 2025). Highly-detailed egocentric video dataset; 41h of unscripted kitchen video with per-frame 3D / hand / speech dense annotations. [[paper]](https://arxiv.org/abs/2502.04144)
- [LookOut / AND](https://arxiv.org/abs/2508.14466) — (ICCV 2025). Real humanoid egocentric navigation dataset; ~4h of Aria navigation recordings for VLM-based navigation.

### Egocentric Video Understanding & Video-LLMs

- [EgoExoLearn](https://egoexolearn.github.io/) — Shanghai AI Lab / OpenGVLab (CVPR 2024). Large-scale asynchronous ego-exo procedural activity dataset with 1,000+ hours of hierarchical procedure annotation. [[paper]](https://arxiv.org/abs/2403.16182) [[code]](https://github.com/OpenGVLab/EgoExoLearn)
- [EgoThink](https://adacheng.github.io/EgoThink/) — (CVPR 2024 Highlight). Benchmark evaluating VLMs' first-person "thinking" across six task categories, derived from Ego4D. [[paper]](https://arxiv.org/abs/2311.15596) [[code]](https://github.com/AdaCheng/EgoThink)
- [VidEgoThink](https://adacheng.github.io/VidEgoThink/) — (2024). First-person video understanding evaluation; ~400 video question-answering samples. [[paper]](https://arxiv.org/abs/2410.11623)
- [EgoVideo](https://arxiv.org/abs/2406.18070) — Shanghai AI Lab / OpenGVLab (2024). Egocentric video foundation model trained on large-scale pretraining data. [[code]](https://github.com/OpenGVLab/EgoVideo)
- [EgoTempo](https://arxiv.org/abs/2503.13646) — Google Research et al. (CVPR 2025). Benchmark evaluating MLLMs' temporal understanding in egocentric video. [[code]](https://github.com/google-research-datasets/egotempo)
- [EgoLife](https://egolife-ai.github.io/blog/) — NTU (CVPR 2025). Ultra-long (week-scale) AI life-assistant dataset; 300h from 6 participants, including the EgoLifeQA benchmark. [[paper]](https://arxiv.org/abs/2503.03803) [[code]](https://github.com/EvolvingLMMs-Lab/EgoLife)
- [EgoThinker / EgoRe-5M](https://arxiv.org/abs/2510.23569) — (NeurIPS 2025). First-person reasoning dataset with 5M samples of causal CoT question-answering and hand-object annotations.
- [EgoCVR](https://arxiv.org/abs/2407.16658) — (ECCV 2024). Egocentric fine-grained compositional video retrieval benchmark.
- [OpenMMEgo (OME10M)](https://proceedings.neurips.cc/paper_files/paper/2025/file/24b9e3da4b01ec1e8a41144cfe8dc929-Paper-Conference.pdf) — (NeurIPS 2025). Ten-million-scale egocentric spatio-temporal video knowledge dataset to enhance MLLMs.
- [EVUD](https://github.com/alanaai/EVUD) — alanaai (2026). Egocentric video instruction-tuning dataset for video LLMs.

### Hand-Object Interaction & Dexterous Manipulation

- [EgoDex](https://github.com/apple/ml-egodex) — Apple (2025). Largest egocentric dexterous manipulation dataset; 829+ hours captured with Vision Pro plus 3D hand pose. [[paper]](https://arxiv.org/abs/2505.11709)
- [OpenEgo](https://arxiv.org/abs/2509.05513) — (2025). Large-scale multimodal egocentric dexterous manipulation dataset.
- [EgoSim / MultiEgoView](https://arxiv.org/abs/2502.18373) — (NeurIPS 2024). Egocentric multi-view simulator plus a real-world dataset.
- [EMHI](https://arxiv.org/abs/2408.17168) — (2024). Multimodal egocentric human motion dataset.

### Long-Term Memory & Egocentric Video QA

- [SuperMemory-VQA](https://arxiv.org/abs/2606.00825) — (2026). Egocentric VQA dataset with 52.9h of AI-glasses daily recordings for long-term memory reasoning.
- [EgoMemReason](https://egomemreason.github.io/) — (2026). Memory-driven long-term egocentric video reasoning benchmark (week-scale).

## Classic Datasets

Well-established egocentric datasets (pre-2023), with links updated to their current official pages.

- [Ego4D](https://ego4d-data.org/) — 3,025 hours of daily-life activity video from 855 unique camera wearers across 74 worldwide locations and 9 countries. [[download](https://ego4d.dev/)]
- [EgoCom](https://github.com/facebookresearch/EgoCom-Dataset) — Natural conversations dataset with multi-modal human communication captured simultaneously from egocentric perspectives.
- [EPIC-Kitchens](https://epic-kitchens.github.io/) — Subjects performing unscripted actions in native environments (EPIC-Kitchens 55, EPIC-KITCHENS-100, and 2018/2020 editions).
- [EPIC-Tent](https://data.bris.ac.uk/data/dataset/2ite3tu1u53n42hjfh3886sa86) — 29 participants assembling a tent while wearing two head-mounted cameras. [[paper]](https://ieeexplore.ieee.org/document/9022634)
- [MECCANO](https://iplab.dmi.unict.it/MECCANO/) — 20 subjects assembling a toy motorbike. [[code]](https://github.com/fpv-iplab/MECCANO)
- [EGO-CH](https://iplab.dmi.unict.it/EGO-CH/) — 70 subjects visiting two cultural sites in Sicily, Italy.
- [EGTEA Gaze+](http://cbs.ic.gatech.edu/fpv/) — 32 subjects, 86 cooking sessions, 28 hours of first-person cooking with gaze. [[mirror](https://ai.stanford.edu/~alireza/GTEA_Gaze_Website/)]
- [ADL](https://web.cs.ucdavis.edu/~hpirsiav/papers/ADLdataset/) — 20 subjects performing daily activities in their native environments.
- [CMU Kitchen](http://kitchen.cs.cmu.edu/) — Multimodal, 18 subjects cooking 5 different recipes: brownies, eggs, pizza, salad, sandwich.
- [EgoSeg](http://www.vision.huji.ac.il/egoseg/) — Long-term action segmentation (walking, running, driving, etc.).
- [First-Person Social Interactions](http://ai.stanford.edu/~alireza/Disney/) — 8 subjects at Disneyworld for egocentric social interaction.
- [UEC Dataset](http://www.cs.cmu.edu/~kkitani/datasets/) — Two choreographed egocentric-action datasets (walk, jump, climb, etc.) + 6 YouTube sports videos.
- [JPL](http://michaelryoo.com/jpl-interaction.html) — Egocentric interaction with a robot.
- [FPPA](http://tamaraberg.com/prediction/Prediction.html) — Five subjects performing 5 daily actions for action prediction.
- [UT Egocentric](https://vision.cs.utexas.edu/projects/egocentric_data/UT_Egocentric_Dataset.html) — 3–5 hour long videos capturing a person's day.
- [VINST / Visual Diaries](http://www.csc.kth.se/cvap/vinst/NovEgoMotion.html) — 31 videos capturing the visual experience of a subject walking from metro station to work.
- [BEOID (Bristol Egocentric Object Interaction)](https://www.cs.bris.ac.uk/~damen/BEOID/) — 8 subjects, six locations; interaction with objects and environment.
- [Object Search Dataset](https://github.com/Mengmi/deepfuturegaze_gan) — 57 sequences of 55 subjects on search and retrieval tasks.
- [UNICT-VEDI](http://iplab.dmi.unict.it/VEDI/) — Subjects visiting a museum.
- [EgoGesture](http://www.nlpr.ia.ac.cn/iva/yfzhang/datasets/egogesture.html) — 2k videos from 50 subjects performing 83 hand gestures.
- [DoMSEV](http://www.verlab.dcc.ufmg.br/semantic-hyperlapse/cvpr2018-dataset/) — 80 hours of egocentric video across different activities.
- [DR(eye)VE](https://aimagelab-legacy.ing.unimore.it/imagelab/page.asp?IdPage=8) — 74 videos of people driving with gaze.
- [EgoDexter](https://handtracker.mpi-inf.mpg.de/projects/OccludedHands/EgoDexter.htm) — 4 sequences with 4 actors and varying hand-object interactions in cluttered backgrounds. [[paper]](https://handtracker.mpi-inf.mpg.de/projects/OccludedHands/index.htm)
- [First-Person Hand Action (FPHA)](https://guiggh.github.io/publications/first-person-hands/) — 3D hand-object interaction; 1,175 videos across 45 activity categories from 6 actors. [[paper]](https://arxiv.org/pdf/1704.02463.pdf)
- [UTokyo PEV / Ego-Surf](https://www.ut-vision.org/resources/) — Paired first-person clips (PEV) and group first-person videos (Ego-Surf) recorded synchronously during face-to-face conversations.
- [TEgO](https://iamlabumd.github.io/tego/) — Teachable egocentric objects; images of 19 distinct objects for training a teachable object recognizer.
- [Multimodal Focused Interaction](https://discovery.dundee.ac.uk/en/datasets/multimodal-focused-interaction-dataset/) — 377 minutes of continuous multimodal recording across 19 sessions with 17 conversational partners.
- [TREK-100](https://opendatalab.com/OpenDataLab/TREK-100) — Object tracking in first-person vision (100 videos).
- [Charade-Ego](https://prior.allenai.org/projects/charades-ego) — Paired first- and third-person videos of daily activities.

## Removed Samples

The following datasets from the original [Egocentric-Dataset](https://github.com/EgoAlpha/Egocentric-Dataset) list were **removed** because their official pages are no longer accessible and no reliable official mirror exists:

- **EgoHands** — Official Indiana University page is no longer available; only unofficial third-party mirrors remain.
- **THU-READ** — Original Tsinghua page is unreachable; no reliable official backup exists.

## Contributing

Contributions are welcome. To add or fix a dataset entry, open a pull request or issue. Please ensure:

- The dataset is egocentric / first-person vision related.
- The official link is accessible.
- Include a one-line description (institution, task, scale).

## License

The list itself is provided under [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/). Dataset-specific terms apply to each linked dataset.

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
