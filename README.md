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

# VLA 算法范式演变（2023.08 – 2026.08）

> 抓大放小：仅收录改变范式走向的里程碑，省略噪音工作。

## 一句话结论（金字塔之顶）

**VLA 三年只做了一件事：把"看"（视觉）与"做"（动作）从两套离散的建模，统一进同一个可规模化学习的连续表达里——范式主线是「离散 token → 连续生成 → 互联网预训练 → 从经验学习 → 世界模型融合」，每一步都朝"用最少的先验、让数据本身教会动作"逼近。**

## 第一性原理：VLA 在解什么？（金字塔之基）

回到本质，一个 agent 决策需要三样东西：

1. **看什么** —— 视觉状态 $s_t$（图像）
2. **怎么做** —— 动作分布 $P(a_t | s_t, \text{指令})$（连续、多模态、与历史强耦合）
3. **从哪学** —— 数据（专家轨迹、互联网视频、自身经验）

VLA 三年所有范式的更迭，都可归结为对上面三件事的**持续"去先验"**：

| 维度 | 早期（RT-1/RT-2） | 后期（π0.x / Gr00t / WorldVLA） | 本质变化 |
|---|---|---|---|
| 动作建模 | 离散 token 分类 | 连续生成（Flow Matching / 扩散） | 从"枚举"到"生成"，天然匹配连续控制 |
| 数据来源 | 机器人轨迹 | 轨迹 + **互联网视频** + **自身经验** | 数据量级与多样性质变 |
| 学习方式 | 监督模仿 | 模仿 + **强化学习（RECAP）** | 从"看演示"到"自己练" |
| 世界认知 | 无（仅感知-行动） | **世界模型 / 动作世界模型** | 从"反应"到"预测/想象" |

**核心逻辑**：每解除一个先验（离散化、轨迹依赖、演示依赖、无世界模型），VLA 就向"通用基础模型"逼近一步。这是理解整条时间线的判据。

## 里程碑时间线（金字塔之身，按第一性原理分层）

### 第一层：奠基与"看得懂"（2023）

- **RT-2**（2023-07，[arXiv:2307.15818](https://arxiv.org/abs/2307.15818)）—— 范式**起点**：把动作作为文本 token 送入大 VLM 的 **Co-Fine-Tuning** 范式，首次让"一个模型同时做推理和动作"，开启 VLA 概念。
- **PaLM-E**（2023-03，[arXiv:2303.03378](https://arxiv.org/abs/2303.03378)）—— 嵌入式具身多模态 LLM，为"感知-行动进同一个大模型"铺路。

### 第二层：让数据决定一切（2023.10 – 2024.10）

- **Open X-Embodiment / RT-X**（2023-10，[arXiv:2310.08864](https://arxiv.org/abs/2310.08864)）—— 首个**跨本体、跨数据集统一预训练**范式（OXE 数据集 + RT-X 系列），证明"数据规模化"比"设计技巧"更有效。
- **Octo**（2024-05，[arXiv:2405.12213](https://arxiv.org/abs/2405.12213)）—— 开源、可组合微调的可扩展 transformer 扩散策略，把"可复现"带给 VLA。
- **OpenVLA**（2024-06，[arXiv:2406.09246](https://arxiv.org/abs/2406.09246)）—— 首个**开放权重 7B VLA**（LLaVA + 扩散动作头），统一了动作解码/微调/量化的工程范式，成为社区事实标准底座。
- **RDT-1B**（2024-10，[arXiv:2410.07864](https://arxiv.org/abs/2410.07864)，清华/智源）—— 1.2B 扩散基础模型，专注**双臂（bimanual）**规模化预训练。

### 第三层：从离散到连续生成（2024.10，范式分水岭）

- **π0**（2024-10，[arXiv:2410.24164](https://arxiv.org/abs/2410.24164)，Physical Intelligence）—— **范式转折点**：用 **Flow Matching 连续动作生成**取代离散 token，叠加"通用预训练 + 任务后训练"，标志 VLA 从"分类"走向"生成"。

### 第四层：无动作标签与跨本体（2024.10 – 2025.04）

- **LAPA**（2024-10，[arXiv:2410.11758](https://arxiv.org/abs/2410.11758)，ICLR 2025）—— 首个**无动作标签的潜动作预训练**，把预训练数据从机器人轨迹扩展到**互联网视频**，极大解锁数据。
- **DexVLA**（2025-02，[arXiv:2502.05855](https://arxiv.org/abs/2502.05855)）—— 可插拔扩散动作专家（1B），聚焦**灵巧操作**的跨本体泛化。
- **Gr00t N1**（2025-03，[arXiv:2503.14734](https://arxiv.org/abs/2503.14734)，NVIDIA）—— 首个**开源人形机器人 VLA 基础模型**（dual-system 架构），把 VLA 带入人形/跨本体赛道。
- **π0.5**（2025-04，[arXiv:2504.16054](https://arxiv.org/abs/2504.16054)）—— π 系**异构多源数据协同训练**，提升开放世界泛化。

### 第五层：世界模型与"从经验学习"（2025.06 – 2026）

- **WorldVLA**（2025-06，[arXiv:2506.21539](https://arxiv.org/abs/2506.21539)）—— 将**世界模型与 VLA 统一**为自回归"动作世界模型"，开启 "VLA ↔ World Model" 融合路线。
- **π0.6**（2025-11，[arXiv:2511.14759](https://arxiv.org/abs/2511.14759)）—— π 系首次引入**强化学习（RECAP）**做经验驱动后训练：从"看演示"走向"从经验学习"。
- **π0.7**（2026-04，Physical Intelligence）—— 组合泛化/技能**涌现**（如零样本组合原子技能），被视为 VLA 基础模型能力的分水岭。

> 备注：Nova、PaSa 等未能核实到对应 VLA 论文，按"去噪音"原则不纳入主线；VLA-Cache（KV 缓存，部署效率）、DreamVLA（世界知识）等为次要方向，未列入主干。

## 鱼骨图（Fishbone：VLA 范式演变的五大驱动因果）

```
                ┌────────────────────── 结果：VLA 向"通用具身基础模型"演进 ──────────────────────┐
                │                                                                                  │
   动作建模       │             数据来源              │        学习方式           │        世界认知
  （如何做）      │            （从哪学）              │       （怎么学）          │     （预测/想象）
                │                                    │                          │
        ┌───────┴───────┐                   ┌────────┴───────┐          ┌────────┴───────┐
        │ 离散token      │                   │ 机器人轨迹     │          │ 纯监督模仿       │
        │ (RT-2 2023)    │                   │ (早期范式)     │          │ (早期范式)       │
        └───────┬───────┘                   └────────┬───────┘          └────────┬───────┘
                │                                    │                          │
        ┌───────┴───────┐                   ┌────────┴───────┐          ┌────────┴───────┐
        │ 连续生成       │                   │ 跨本体/跨数据集 │          │ 从演示到经验     │
        │ Flow Matching │                   │ (RT-X/π0.5)    │          │ RL(RECAP π0.6) │
        │ (π0 2024)     │                   └────────┬───────┘          └────────┬───────┘
        └───────┬───────┘                            │                          │
                │                        ┌───────────┴───────────┐              │
                │                        │ 互联网视频(无动作标签)  │              │
                │                        │ (LAPA 2024)           │              │
                │                        └───────────┬───────────┘              │
                │                                    │                          │
                └──────────┬─────────────────────────┴─────────────┬────────────┘
                           │                                       │
              ┌────────────┴───────────┐                 ┌─────────┴─────────┐
              │  规模/开放（杠杆）       │                 │  世界模型/动作世界   │
              │  开源+人形+双臂         │                 │  模型融合          │
              │  (OpenVLA/Gr00t/RDT)   │                 │  (WorldVLA 2025)  │
              └───────────────────────┘                 └───────────────────┘
```

**读图方式**：主骨是"VLA 泛化能力"，四根大刺分别是四大驱动维度；每个"鱼刺"上的节点，就是推动范式前进一步的代表性里程碑——越是靠近主骨的后续节点，越代表该维度的"去先验"程度加深。
