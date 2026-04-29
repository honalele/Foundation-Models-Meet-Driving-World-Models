# Foundation Models Meet Driving World Models

### A Comprehensive Survey on the Convergence of FMs and DWMs for Autonomous Driving

<p align="center">
  <a href="https://arxiv.org/abs/xxxx.xxxxx"><img src="https://img.shields.io/badge/arXiv-xxxx.xxxxx-b31b1b.svg" alt="arXiv"></a>
  <a href="#citation"><img src="https://img.shields.io/badge/Citation-BibTeX-blue.svg" alt="Citation"></a>
  <img src="https://img.shields.io/badge/Papers-110%2B-brightgreen.svg" alt="Papers">
  <img src="https://img.shields.io/badge/Coverage-2023--2026-orange.svg" alt="Coverage">
  <img src="https://img.shields.io/badge/Manuscript-Planned%3A%20IEEE%20OJ--ITS-lightgrey.svg" alt="Manuscript: planned submission to IEEE OJ-ITS">
  <img src="https://img.shields.io/badge/PRs-Welcome-success.svg" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/github/stars/xxxxx/Foundation-Models-Meet-Driving-World-Models?style=social" alt="Stars">
</p>

<p align="center">
  <b>The first systematic survey on the intersection of Foundation Models (LLMs / VLMs / WFMs / VLAs) and Driving World Models</b><br/>
  <i>covering 110+ academic and industry works from 2023 to 2026.</i>
</p>

<p align="center">
  <a href="#why-this-survey">Why This Survey</a> •
  <a href="#whats-new">What's New</a> •
  <a href="#taxonomy-at-a-glance">Taxonomy</a> •
  <a href="#paper-list">Paper List</a> •
  <a href="#industry-platforms">Industry</a> •
  <a href="#benchmarks--datasets">Benchmarks</a> •
  <a href="#open-challenges">Open Challenges</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#citation">Citation</a>
</p>

> **Manuscript status.** This survey is **not yet peer-reviewed or published**. We **plan to submit** it to the *IEEE Open Journal of Intelligent Transportation Systems* (OJ-ITS). This repository may describe work in advance of the journal version; we will update badges, links, and the [citation](#citation) block once the official venue and DOI are fixed.

---

> If you find this repository helpful, please consider giving it a **star** — it helps the community discover this resource and motivates us to keep it up to date with the fast-moving FM × DWM literature.

---

## Why This Survey

Driving World Models (DWMs) have emerged as the cornerstone of next-generation safety-critical autonomous driving (AD), while Foundation Models (FMs) — including LLMs, VLMs, video World Foundation Models (WFMs), and Vision-Language-Action models (VLAs) — have unlocked unprecedented capabilities in semantic understanding, physical reasoning, high-fidelity generation, and sequential decision-making. **Their convergence is reshaping every stage of the AD pipeline**, from perception and prediction to planning and closed-loop control.

Yet the existing surveys leave clear gaps:

| Survey                | Organizing Axis                          | FM × DWM Integration | Industry Platforms | VLA & Data Flywheel | Coverage  |
|-----------------------|------------------------------------------|----------------------|--------------------|---------------------|-----------|
| Feng et al. 2025      | Driving WMs by output modality           | Not covered          | Partial (no Cosmos)| Not covered         | up to 2024|
| Tu et al. 2025        | Driving WMs by downstream role           | Not covered          | Partial            | Not covered         | up to 2024|
| Ding et al. 2024      | General WMs by application domain        | Not covered          | Not covered        | Not covered         | up to 2024|
| Cui et al. 2024       | MLLM/VLM by driving task                 | No WM coverage       | Not covered        | Not covered         | up to 2024|
| **Ours**              | **By FM Role: Encoder / Simulator / Reasoner / Data Engine** | **In depth**         | **In depth**       | **In depth**        | **2023–2026** |

**This survey is the first to systematically examine how foundation models reshape every stage of the driving world model pipeline**, with critical analysis of genuine technical contributions vs. industry hype, and a structured roadmap toward Physical AI for autonomous driving.

### Our Four Core Contributions

1. **Role-based taxonomy** — *Encoder / Simulator / Reasoner / Data Engine* — that captures how FMs are integrated into and reshape the full DWM pipeline, with formalized definitions of each paradigm.
2. **Comprehensive 110+ paper review (2023–2026)** — extending prior surveys (which primarily index up to 2024) to cover the 2025–2026 wave of FM-native driving WFMs (Cosmos 2.5, GAIA-2, Epona) and unified VLA-based driving stacks.
3. **Critical technical analysis** — clarifying the core gaps between general video generation models and AD-specific WFMs in the safety-critical context.
4. **Structured research roadmap** — six key open challenges with actionable future directions aligned with the latest advances in Physical AI, hardware acceleration, and safety-critical deployment.

---

## What's New

- **2026-04** — Initial public release of this **manuscript** and repository companion (110+ papers, 4-role taxonomy, benchmark / industry-platform notes). Target journal: IEEE OJ-ITS (submission planned; not yet accepted).
- **2025-12** — Inclusion of NVIDIA Cosmos Predict 2.5 (flow-based WFM), GAIA-2 (Wayve), Epona (autoregressive diffusion), DriveLaW (latent WM + planning), OpenDriveVLA, EvoDriveVLA, AutoVLA.
- **2025-09** — Coverage extended to production-scale Chinese OEM stacks: Huawei WEWA, NIO NWM, XPeng XNGP, Horizon SuperDrive, Li Auto OTA 6.4 (E2E + VLM), Momenta R6 Flywheel.

> Tracking the latest FM × DWM works? [**Watch this repo**](../../subscription) and [**open a PR**](../../pulls) — see [Contributing](#contributing).

---

## Authors

**[Naren Bao](mailto:naren@g.ecc.u-tokyo.ac.jp)<sup>1,3</sup>, Alexander Carballo<sup>2,5</sup>, Ehsan Javanmardi<sup>1</sup>, Manabu Tsukada<sup>1</sup>, Kazuya Takeda<sup>3,4,5</sup>**

<sup>1</sup> Graduate School of Information Science and Technology, The University of Tokyo, Japan
<sup>2</sup> Graduate School of Engineering, Gifu University, Japan
<sup>3</sup> Graduate School of Informatics, Nagoya University, Japan
<sup>4</sup> Institutes of Innovation for Future Society, Nagoya University, Japan
<sup>5</sup> Nagoya University Open Innovation Center, Japan

---

## Taxonomy at a Glance

We propose a novel **role-based taxonomy** organized around the four core roles foundation models play in the driving world model pipeline:

```
┌─────────────────────────────────────────────────────────────────────┐
│                  FM-Empowered Driving World Models                   │
├─────────────────┬─────────────────┬───────────────────┬─────────────┤
│  FM as          │  FM as          │  FM as            │ FM as       │
│  World Encoder  │  World Simulator│  World Reasoner   │ Data Engine │
├─────────────────┼─────────────────┼───────────────────┼─────────────┤
│ • VLM-driven    │ • Autoregressive│ • LLM decision    │ • Synthetic │
│   structured    │   transformer   │   making          │   data gen  │
│   scene encoding│ • Diffusion-    │ • Imagine-then-   │ • VLM auto- │
│ • Pre-trained   │   based WMs     │   Plan paradigm   │   annotation│
│   visual FMs    │ • Flow-based    │ • FM as reward /  │ • Sim-to-   │
│   (CLIP, DINOv2)│   WFMs          │   critic for RL   │   real      │
│ • Multi-modal   │ • Latent-space  │ • VLA for E2E     │ • Closed-   │
│   FM encoding   │   WMs           │   driving         │   loop data │
│ • Language as   │ • WFM platforms │ • VLA + WM fusion │   flywheel  │
│   world state   │   (Cosmos, GAIA)│   (3 paradigms)   │             │
└─────────────────┴─────────────────┴───────────────────┴─────────────┘
```

### The Four Foundation Model Families We Cover

| FM Family       | Input → Output                        | Representative Models                                | Pre-training Scale     | Core Role in DWM Pipeline                                    |
|-----------------|---------------------------------------|------------------------------------------------------|------------------------|--------------------------------------------------------------|
| **LLM**         | Text → Text                           | GPT-4o, LLaMA-3.1, Qwen-2.5                          | >1T tokens             | Intent generation, decision reasoning, reward design         |
| **VLM**         | Image/Video + Text → Text             | GPT-4V, LLaVA-1.5, InternVL-2.5, Cosmos Reason 2     | >1B image-text pairs   | Scene understanding, auto-annotation, safety verification    |
| **Video WFM**   | Text/Image/Video + Action → Video     | Cosmos Predict 2.5, GAIA-2, Epona, Sora              | >100M video clips      | World simulation, future prediction, synthetic data engine   |
| **VLA**         | Image + Text → Action                 | RT-2, OpenVLA, OpenDriveVLA                          | >100K trajectories     | End-to-end perception-to-action, closed-loop control         |

### Three Eras of Driving World Models

```
   2018 ─────── 2022 ─── 2023 ─── 2024 ─── 2025 ─── 2026 ──────
   │                    │                          │
   │   Pre-FM Era       │   FM Integration Era     │   FM-Native Physical AI Era
   │   (VAE/GAN/RNN)    │   (Diffusion + LLM)      │   (Purpose-built WFMs)
   │                    │                          │
   World Models  →  GAIA-1, DriveDreamer  →  Cosmos, GAIA-2, Epona, DriveLaW
                    GPT-Driver,                OpenDriveVLA, Cosmos Predict 2.5
                    MagicDrive, OccWorld
```

The current "FM-Native Physical AI Era" is defined by purpose-built world foundation models designed natively for physical AI and autonomous driving — rather than adapting general FMs to driving tasks.

---

## Paper Structure

| Section | Title                                          | Highlights                                                                                          |
|---------|------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| §1      | **Introduction**                               | Motivation, scope, positioning vs. existing surveys                                                 |
| §2      | **Preliminaries**                              | Core definitions (DWM, WFM, FM-Empowered DWM), four FM families, evolution timeline, unified problem formulation |
| §3      | **FM as World Encoder**                        | VLM-driven scene understanding, pre-trained visual FM backbones, multi-modal encoding, language-as-state |
| §4      | **FM as World Simulator**                      | Pixel-space generative WMs (AR / Diffusion / Flow), purpose-built WFM platforms (Cosmos, GAIA-2), LLM-assisted scene generation, latent-space WMs, online vs. offline deployment |
| §5      | **FM as World Reasoner**                       | LLM decision making, Imagine-then-Plan paradigm, FM as reward/critic, VLA for E2E driving, three VLA + WM fusion paradigms |
| §6      | **FM as Data Engine**                          | Three-level synthetic data generation, VLM auto-annotation, sim-to-real adaptation, closed-loop data flywheel |
| §7      | **Benchmarks and Evaluation**                  | Four metric families (visual fidelity / prediction accuracy / physical consistency / downstream task), existing benchmarks, call for standardized Physical AI benchmarks |
| §8      | **Open Challenges and Future Directions**      | Six core challenges with concrete milestones                                                         |
| §9      | **Conclusion**                                 | Summary and outlook                                                                                  |
| App. A  | **Detailed Architecture Case Studies**         | DriveDreamer (two-stage diffusion), NVIDIA Cosmos (three-pillar platform)                            |

---

## Paper List

> **Legend:**
> *Year* · *Architecture / FM Family* · *Output / Capability*
> [`paper`] linked to arXiv / venue page · [`code`] linked to public repo · [`page`] linked to project / blog page when available · ★ flagged works are particularly recommended starting points.

### §3 FM as World Encoder

Foundation models provide DWMs with richer, semantically meaningful scene representations. We split this into four paradigms:

**A. VLM-Driven Structured Scene Understanding**

| Method                | Year | FM Used                  | Output / Task                    | Dataset       | Links                                                            |
|-----------------------|------|--------------------------|----------------------------------|---------------|------------------------------------------------------------------|
| GPT-4V on Road ★      | 2023 | GPT-4V                   | Scene Description / Understanding| Custom        | [paper](https://arxiv.org/abs/2311.05332)                         |
| DriveGPT4             | 2024 | LLaVA-1.5                | Text + Action QA + Planning      | BDD-X         | [paper](https://arxiv.org/abs/2310.01412)                         |
| DriveMLM              | 2023 | LLaMA-2 + ViT            | Text + Action / Behavioral Plan  | nuScenes      | [paper](https://arxiv.org/abs/2312.09245)                         |
| DriveLM ★             | 2024 | BLIP-2                   | Graph QA / Perception–Planning   | nuScenes      | [paper](https://arxiv.org/abs/2312.14150) · [code](https://github.com/OpenDriveLab/DriveLM)|
| DriveVLM              | 2024 | InternVL-2               | Text + Trajectory / Planning     | nuScenes      | [paper](https://arxiv.org/abs/2402.12289)                         |
| Cosmos Reason 2 ★     | 2025 | Custom Physical VLM      | Video QA + Caption               | Multi-domain  | [page](https://www.nvidia.com/en-us/ai/cosmos/)                   |
| Dolphins              | 2023 | Driving VLM              | Grounded CoT QA                  | BDD-X         | [paper](https://arxiv.org/abs/2312.00438)                         |
| RAG-Driver            | 2024 | LLM + RAG                | Retrieval-Augmented Reasoning    | nuScenes      | [paper](https://arxiv.org/abs/2402.10828)                         |
| DriveCoT              | 2024 | VLM                      | CoT Rationale + Action           | nuScenes      | [paper](https://arxiv.org/abs/2403.16996)                         |

**B. Pre-trained Visual FM Backbones** — CLIP, SigLIP, DINOv2, InternViT, VideoMAE V2 integrated into BEV frameworks (BEVFormer, BEVDet, TPVFormer, MAE).

**C. Multi-modal FM Encoding** — PointCLIP, DriveLM, Cosmos / GAIA-2 multi-modal tokenizers across camera, LiDAR, radar, and CAN.

**D. Language as Unified World State**

| Method                | Year | FM Used         | Output / Task              | Dataset    | Links                                  |
|-----------------------|------|-----------------|----------------------------|------------|----------------------------------------|
| LMDrive               | 2024 | LLaMA-2         | Closed-loop E2E driving    | CARLA      | [paper](https://arxiv.org/abs/2312.07488) · [code](https://github.com/opendilab/LMDrive)|
| Talk2BEV              | 2023 | LLaMA-2 + CLIP  | BEV Language Query         | nuScenes   | [paper](https://arxiv.org/abs/2310.02251)|

> **Critical takeaway (§III.E):** The four paradigms trade off along a single **fidelity–efficiency–generalization** axis. No existing work benchmarks them head-to-head on a unified task — a critical community gap.

---

### §4 FM as World Simulator (the most active area)

The dominant paradigm is **pixel-space generative world models**, with three architectural families: autoregressive transformers, diffusion models, and flow-based models. Plus latent-space WMs and purpose-built WFM platforms.

**Architecture Distribution (across §IV simulator works):** Diffusion 48% · AR Transformer 22% · Latent 18% · Flow 12%.

#### 4.1 Autoregressive Transformer World Models

| Method        | Year | Backbone            | Conditioning            | Output       | Open  | Links                                                     |
|---------------|------|---------------------|-------------------------|--------------|-------|-----------------------------------------------------------|
| GAIA-1 ★      | 2023 | AR Transformer (9B) | Video + Text + Action   | Single-view  | No    | [paper](https://arxiv.org/abs/2309.17080) · [page](https://wayve.ai/thinking/scaling-gaia-1/)|
| ADriver-I     | 2024 | Multimodal LLM      | Vision + Action         | Single-view  | Yes   | [paper](https://arxiv.org/abs/2311.13549)                  |
| Epona ★       | 2025 | AR Diffusion        | Trajectory + Action     | Single-view  | No    | [paper](https://arxiv.org/abs/2502.xxxxx) (ICCV 2025)      |

#### 4.2 Diffusion-Based Driving World Models

| Method                | Year | Backbone                      | Conditioning             | Output         | Open  | Links                                                                 |
|-----------------------|------|-------------------------------|--------------------------|----------------|-------|-----------------------------------------------------------------------|
| DriveDreamer ★        | 2023 | Stable Diffusion UNet         | Layout + HDMap           | Single-view    | Yes   | [paper](https://arxiv.org/abs/2309.09777) · [code](https://github.com/JeffWang987/DriveDreamer)|
| WoVoGen                | 2023 | Diffusion                     | BEV Layout + Text        | Multi-view     | Yes   | [paper](https://arxiv.org/abs/2312.02934)                              |
| MagicDrive ★          | 2024 | Stable Diffusion UNet         | 3D BBox + BEV            | Multi-view     | Yes   | [paper](https://arxiv.org/abs/2310.02601) · [code](https://github.com/cure-lab/MagicDrive)|
| DrivingDiffusion      | 2024 | Latent Diffusion UNet         | Layout + 3D BBox         | Multi-view     | Yes   | [paper](https://arxiv.org/abs/2310.07771)                              |
| Panacea               | 2024 | Stable Video Diffusion        | BEV + Text               | Panoramic      | Yes   | [paper](https://arxiv.org/abs/2311.16813)                              |
| GenAD                 | 2024 | Diffusion UNet                | Trajectory + Action      | Single-view    | Yes   | [paper](https://arxiv.org/abs/2403.09630)                              |
| Drive-WM              | 2024 | Diffusion                     | Trajectory + Map         | Multi-view     | Yes   | [paper](https://arxiv.org/abs/2311.17918)                              |
| Vista ★               | 2024 | Diffusion                     | Action + Text            | Single-view    | Yes   | [paper](https://arxiv.org/abs/2405.17398) · [code](https://github.com/OpenDriveLab/Vista)|
| DriveDreamer-2        | 2024 | Diffusion + LLM               | Text + Layout            | Multi-view     | Yes   | [paper](https://arxiv.org/abs/2403.06845)                              |
| DriveWorld            | 2024 | 4D Pre-train + Diffusion      | Spatial-Temporal         | Multi-view     | Yes   | [paper](https://arxiv.org/abs/2405.04390)                              |
| DriveScape            | 2024 | Diffusion WFM                 | Layout + Text            | Multi-view     | -     | [paper](https://arxiv.org/abs/2409.05463)                              |
| MaskGWM               | 2025 | Generalizable Diffusion       | Video Mask Reconstruction| Multi-view     | -     | [paper](https://arxiv.org/abs/2502.xxxxx) (CVPR 2025)                  |
| Orbis                 | 2025 | Long-horizon Diffusion        | Trajectory               | Multi-view     | -     | [paper](https://arxiv.org/abs/2505.xxxxx) (NeurIPS 2025)               |
| DriveDreamer4D        | 2025 | 4D GS + Diffusion             | Spatial-Temporal         | 3D Scene       | -     | [paper](https://arxiv.org/abs/2410.13571) (CVPR 2025)                  |

#### 4.3 Flow-Based World Foundation Models

| Method               | Year | Backbone                | Conditioning                       | Output         | Open  | Links                                                                |
|----------------------|------|-------------------------|------------------------------------|----------------|-------|----------------------------------------------------------------------|
| Cosmos Predict 2.5 ★ | 2025 | Flow-Based DiT          | Text + Image + Video + Action      | Multi-view     | Yes   | [code](https://github.com/nvidia-cosmos/cosmos-predict2.5) · [page](https://www.nvidia.com/en-us/ai/cosmos/)|
| GAIA-2 ★             | 2025 | Controllable Transformer| Ego + Agents + Layout + Weather    | Multi-view     | No    | [paper](https://arxiv.org/abs/2503.20523) · [page](https://wayve.ai/thinking/gaia-2/)|

#### 4.4 Latent-Space World Models (the path to real-time)

| Method               | Year | Architecture                    | Output / Capability                       | Dataset       | Links                                                                 |
|----------------------|------|---------------------------------|-------------------------------------------|---------------|-----------------------------------------------------------------------|
| OccWorld             | 2024 | 3D Occupancy Latent             | Future Occupancy Grids                    | nuScenes      | [paper](https://arxiv.org/abs/2311.16038)                              |
| MILE                 | 2022 | Latent Imitation                | Latent Future + Control                   | CARLA         | [paper](https://arxiv.org/abs/2210.07729)                              |
| Think2Drive ★        | 2024 | Latent + MCTS                   | Efficient RL in Latent Space              | CARLA LB 2.0  | [paper](https://arxiv.org/abs/2402.16720)                              |
| World4Drive          | 2025 | Intention-aware Latent WM       | Imagine-then-Plan                         | nuScenes      | [paper](https://arxiv.org/abs/2502.xxxxx) (ICCV 2025)                  |
| DriveLaW ★           | 2025 | Latent Diffusion                | Unified Latent WM + Planning (100× cheaper)| nuScenes      | [paper](https://arxiv.org/abs/2406.08481) (ICLR 2025)                  |

**Quantitative highlights (FVD↓ on nuScenes):** DriveDreamer 452.0 → Vista 89.4 → Epona 82.8 → DriveLaW 81.3 — a ~6× FVD improvement in just two years for single-view generation.

> **Critical takeaway (§IV.E):** All three architectures learn statistical correlations in pixel space, **not physical causality**. A visually convincing video of a car braking does not imply the model understands friction or inertia. Future architectures must incorporate explicit physical inductive biases, not just scaling.

---

### §5 FM as World Reasoner

Four reasoning paradigms that let driving agents make safe, rational decisions based on world model rollouts.

#### 5.1 LLM as High-Level Decision Maker

| Method            | Year | FM Type        | Paradigm                          | Benchmark    | Links                                                       |
|-------------------|------|----------------|-----------------------------------|--------------|-------------------------------------------------------------|
| GPT-Driver        | 2023 | GPT-3.5        | Direct Trajectory Generation      | nuScenes     | [paper](https://arxiv.org/abs/2310.01415)                    |
| LanguageMPC       | 2023 | GPT-4          | LLM + MPC                         | HighwayEnv   | [paper](https://arxiv.org/abs/2310.03026)                    |
| Agent-Driver      | 2023 | GPT-4          | LLM Agent with Tools              | nuScenes     | [paper](https://arxiv.org/abs/2311.10813)                    |
| DiLu              | 2024 | LLaMA          | Reflective Memory Learning        | HighwayEnv   | [paper](https://arxiv.org/abs/2309.16292) (ICLR 2024)        |

#### 5.2 Imagine-then-Plan Paradigm (LLM + WM Joint Reasoning) ★

This is **the current state-of-the-art reasoning paradigm** — LLM proposes intents → WM rolls out futures → VLM critic evaluates → optimal trajectory selected.

| Method            | Year | FM Type           | WM Integrated   | Paradigm                          | Benchmark        | Links                                                       |
|-------------------|------|-------------------|-----------------|-----------------------------------|------------------|-------------------------------------------------------------|
| World4Drive       | 2025 | Custom VLM        | Yes             | Imagine-then-Plan                 | nuScenes         | (ICCV 2025)                                                  |
| Think2Drive       | 2024 | LLM               | Yes (Latent)    | MCTS + Latent WM                  | CARLA            | [paper](https://arxiv.org/abs/2402.16720)                    |
| DriveLaW          | 2025 | LLM               | Yes (Latent)    | Unified Latent WM + Planning      | nuScenes         | [paper](https://arxiv.org/abs/2406.08481)                    |
| Cosmos Reason 2   | 2025 | Physical VLM      | Yes (Cosmos)    | Full Imagine-then-Plan Pipeline   | Multi-domain     | [page](https://www.nvidia.com/en-us/ai/cosmos/)              |

#### 5.3 FM as Reward Function and Critic

| Method            | Year | FM Type           | Paradigm                          | Benchmark        | Links                                                       |
|-------------------|------|-------------------|-----------------------------------|------------------|-------------------------------------------------------------|
| DriveVLM          | 2024 | InternVL-2        | VLM Critic + RL                   | nuScenes         | [paper](https://arxiv.org/abs/2402.12289)                    |
| DiLu (Reflection) | 2024 | LLaMA             | Self-critique Reward Refinement   | HighwayEnv       | [paper](https://arxiv.org/abs/2309.16292)                    |
| Cosmos Reason     | 2025 | Physical VLM      | Trajectory critic + Data filter   | Multi-domain     | [page](https://www.nvidia.com/en-us/ai/cosmos/)              |

#### 5.4 Vision-Language-Action (VLA) for End-to-End Driving

| Method            | Year | FM Type        | WM Integration   | Paradigm                          | Benchmark        | Links                                                       |
|-------------------|------|----------------|------------------|-----------------------------------|------------------|-------------------------------------------------------------|
| OpenDriveVLA ★    | 2025 | VLA            | Implicit         | E2E VLA                           | nuScenes         | [paper](https://arxiv.org/abs/2503.23463)                    |
| SimLingo ★        | 2025 | VLA (Custom)   | Yes (Shared)     | Joint Driving + Dreaming (Mode 3) | CARLA LB 2.0     | [paper](https://arxiv.org/abs/2503.xxxxx) (CVPR 2025)        |
| EvoDriveVLA       | 2026 | VLA            | -                | Collaborative Distillation        | -                | [paper](https://arxiv.org/abs/2603.09465)                    |
| AutoVLA           | 2025 | VLA            | -                | Adaptive Reasoning + RL Fine-tune | -                | [paper](https://arxiv.org/abs/2506.13757) (NeurIPS 2025)     |

#### 5.5 Three Paradigms of VLA + WM Fusion

| Mode  | Architecture                            | Latency  | Trainability      | Industry Adoption                          |
|-------|-----------------------------------------|----------|-------------------|--------------------------------------------|
| **Mode 1** | WM as Front-End Predictor          | High     | Independent       | Tesla FSD, XPeng XNGP, NIO NWM             |
| **Mode 2** | WM as Post-Validation Safety Cage  | Medium   | Independent       | (research)                                 |
| **Mode 3** | Shared Backbone Joint Training     | Low      | Joint (complex)   | SimLingo, emerging research                |

**Quantitative highlights (open-loop nuScenes L2@3s↓):** UniAD 1.65 → World4Drive 1.31 → DriveLaW 1.22 → VAD-Base 0.60 → SparseDrive 0.50 — WM-integrated planners consistently beat non-WM baselines, but the gap is narrower than expected.

> **Critical takeaway (§V.E – the latency–safety paradox):** The methods with the strongest safety guarantees are also the slowest. Imagine-then-Plan needs 5–30 s per decision; VLAs run real-time but lack explicit safety verification. The field needs **hierarchical System 1 / System 2 reasoning** — fast VLA for routine driving, slow imagine-then-plan for safety-critical situations.

---

### §6 FM as Data Engine (the most impactful practical role)

A scalable, closed-loop data flywheel: **collect real data → fine-tune WFM → generate synthetic data → VLM auto-annotate → train policy → deploy → collect more real data**.

#### 6.1 Three-Level Synthetic Data Generation

| Method               | FM Type                   | Output                  | Sim2Real | Auto-Label    | Links                                                                  |
|----------------------|---------------------------|-------------------------|----------|---------------|------------------------------------------------------------------------|
| Cosmos Predict 2.5   | Flow-Based WFM            | Multi-view Video        | Yes      | Yes (Reason 2)| [code](https://github.com/nvidia-cosmos/cosmos-predict2.5)              |
| Cosmos Transfer 2.5  | Multi-Control WFM         | Photorealistic Video    | Yes      | Yes (Reason 2)| [page](https://www.nvidia.com/en-us/ai/cosmos/)                         |
| MagicDrive           | Diffusion WFM             | Multi-view Image        | No       | No            | [code](https://github.com/cure-lab/MagicDrive)                          |
| DriveDreamer-2       | Diffusion + LLM           | Video                   | No       | No            | [paper](https://arxiv.org/abs/2403.06845)                                |
| ChatSim              | LLM Agent + NeRF          | Editable Scene          | No       | No            | [paper](https://arxiv.org/abs/2402.05746)                                |
| MARS                 | NeRF + GAN                | Reconstructed Scenes    | Yes      | No            | [paper](https://arxiv.org/abs/2307.15058)                                |
| CTG++                | LLM + Diffusion           | Traffic Scenarios       | Yes      | No            | [paper](https://arxiv.org/abs/2305.13242)                                |
| Waymax               | Behavior Model            | Traffic Simulation      | Yes      | Partial       | [paper](https://arxiv.org/abs/2310.08710)                                |
| UniSim ★             | Diffusion WFM             | Interactive Simulation  | Yes      | Yes           | [paper](https://arxiv.org/abs/2308.01898) (CVPR 2023 Highlight)          |

The three levels: **Scenario-level** (full driving scenarios from text) → **Sensor-level** (matching real hardware: multi-camera + LiDAR + radar) → **Event-level** (long-tail safety-critical events).

#### 6.2 VLM-Driven Auto-Annotation and Active Learning

DriveLM (graph QA labels), LISA (open-vocabulary segmentation), Dolphins (event-level behavioral annotations), Cosmos Reason / InternVL-2 (physical-AI VLM filtering).

#### 6.3 Sim-to-Real Adaptation with World Foundation Models

Multi-Control Style Transfer (Cosmos Transfer) · Domain Randomization · Fine-tuning with real data · Neural reconstruction (MARS, Street Gaussians, EmerNeRF, S3Gaussian, NeuRAD).

> **Critical takeaway (§VI.E):** Synthetic data **complements rather than replaces** real data. Diminishing returns appear above ~30% synthetic-to-real ratio for perception. The most promising direction is **targeted synthesis** — generating specific scenarios identified as underrepresented via active learning or failure analysis.

---

## Industry Platforms

### Open & Industry-Scale WFM Platforms

| Platform              | Owner    | Modalities                              | Open Weights | Notes                                                                       |
|-----------------------|----------|-----------------------------------------|--------------|-----------------------------------------------------------------------------|
| **NVIDIA Cosmos** ★   | NVIDIA   | Predict + Transfer + Reason             | Yes (most)   | Three-pillar platform; flow-based Predict 2.5; full Curator/CDS/Evaluator stack. [page](https://www.nvidia.com/en-us/ai/cosmos/) · [Predict 2.5 code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| **Wayve GAIA-2** ★    | Wayve    | Controllable multi-view from fleet      | No (proprietary) | Fleet-scale data + integrated reasoning. [paper](https://arxiv.org/abs/2503.20523) · [page](https://wayve.ai/thinking/gaia-2/) |
| **OpenAI Sora**       | OpenAI   | Text-to-video (general)                 | No           | Not driving-specific, but raises the bar for what general WFMs can do.       |

### Production-Scale Driving Stacks (publicly announced)

> Compiled from official keynotes, developer-conference announcements, and corporate technical blogs — **not peer-reviewed evidence**, but evidence that the WM and E2E paradigms are being validated at production scale.

| Company        | Stack Name                              | Paradigm                | Generative WM?                  | Reasoning Layer                     | Year   |
|----------------|-----------------------------------------|-------------------------|---------------------------------|-------------------------------------|--------|
| **Tesla**      | FSD + Occupancy Network                 | E2E + Occupancy WM      | Partial (occupancy)             | MCTS-based planner                  | 2022+  |
| **Huawei**     | WEWA (ADS 4.0)                          | E2E + WM                | Yes (World Engine)              | World Action module                 | 2025   |
| **NIO**        | NWM (NAD Architecture 2.0)              | WM-centric              | Yes (AR generative, 216 futures / 100 ms) | Trajectory selection over rollouts | 2024   |
| **XPeng**      | XNet + XPlanner + XBrain (XNGP)         | E2E + Occupancy WM      | Partial (2K occupancy)          | XBrain large model                  | 2024   |
| **Horizon Robotics** | SuperDrive (Journey 6)            | VA-style E2E            | No                              | (no explicit VLM in safety path)    | 2024   |
| **Li Auto**    | E2E + VLM (OTA 6.4)                     | Dual System 1/2         | No                              | Explicit VLM as System 2 critic     | 2024   |
| **Momenta**    | R6 Flywheel                             | RL-based E2E            | No (data-flywheel-centric)      | VA-style                            | 2024   |

Three architectural patterns recur across these stacks, mirroring academic directions: **(i)** occupancy-centric latent spaces, **(ii)** dual fast/slow controllers (System 1 / System 2), **(iii)** RL-based closed-loop data flywheels.

---

## Benchmarks & Datasets

### Datasets

| Dataset             | Scale                         | Modalities                              | Use Cases                            |
|---------------------|-------------------------------|-----------------------------------------|--------------------------------------|
| **nuScenes**        | 1000 × 20 s scenes            | 6-cam + LiDAR + radar + HD maps         | Most widely used DWM benchmark       |
| **Waymo Open**      | 1000+ hours                   | High-res cam + LiDAR                    | Large-scale perception / forecasting |
| **BDD100K**         | 100K videos                   | Diverse weather / lighting              | Video generation training            |
| **KITTI**           | -                             | Cam + LiDAR                             | Earlier-gen perception baseline      |
| **Argoverse**       | -                             | Cam + LiDAR + maps                      | Motion forecasting                   |

### Closed-Loop Benchmarks

| Benchmark                        | Mode                  | Use Case                                  |
|----------------------------------|-----------------------|-------------------------------------------|
| **CARLA**                        | Simulator             | Closed-loop driving policy / WM eval      |
| **CARLA Leaderboard 2.0**        | Hard routes           | SOTA closed-loop benchmark                |
| **NAVSIM**                       | Data-driven, non-reactive | Standardized WM closed-loop eval      |
| **nuPlan**                       | Closed-loop from nuScenes | Planning benchmark                    |
| **Waymo Sim Agents Challenge**   | Multi-agent           | Reactive agent simulation                 |
| **SHIFT**                        | Synthetic             | Domain adaptation                         |
| **ScenarioNet**                  | Open-source           | Large-scale scenario simulation           |

### Why We Call for New Benchmarks

All current benchmarks are **insufficient for FM-empowered driving WMs**:

1. They are designed for perception/prediction, not generative WMs.
2. They lack standardized protocols for **physical consistency** and **action controllability**.
3. They do not include comprehensive **long-tail safety-critical scenarios**.
4. They do not evaluate the full **data flywheel** capabilities.

We propose five components for a new standardized Physical AI benchmark suite (§VII.C):

1. Standardized **physical consistency** evaluation (object permanence, kinematics, collision realism, traffic rule compliance)
2. **Action controllability** benchmark
3. **Long-tail scenario** suite
4. **Downstream task** evaluation protocol
5. **Efficiency** benchmark (latency, memory, deployable on edge)

---

## Open Challenges

We identify **six core open challenges** with concrete milestones for the field:

| #     | Challenge                                       | Current Status                                                     | Concrete Milestone                                                                        |
|-------|-------------------------------------------------|--------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| **1** | **Scaling Laws for WFMs**                       | Visual fidelity scales, physical understanding does not             | A public scaling-law study reporting compute-vs.-physics-violation rates at ≥3 model scales |
| **2** | **Physical Grounding & Causal Reasoning**       | Geometric / dynamic / causal violations persist                    | Sub-1% kinematic-violation rate on a standardized physical consistency benchmark           |
| **3** | **Real-Time Edge Deployment**                   | Cosmos Predict 2.0 ≈ 4 s for 2 s video on A100 (200× too slow)     | Sub-50 ms world-model rollout for 3 s horizon on Jetson AGX Orin                           |
| **4** | **Unified World Agent Architecture**            | Frankenstein systems: separate encoder → WM → VLM critic → planner | A single-model VLA + WM achieving competitive CARLA LB 2.0 with explicit ≥5 s rollouts     |
| **5** | **Safety Verification & Trustworthy AI**        | Phantom objects, obstacle erasure, temporal hallucination          | Published safety case: <10⁻⁶/hour false-prediction rate with calibrated uncertainty        |
| **6** | **Multi-Agent Interaction & Game-Theoretic Modeling** | Agents treated as passive background — "frozen world"        | A Waymo Sim Agents-style benchmark scoring ego-conditional reactive behavior               |

### Future Technology Roadmap

```
Short-Term (2026–2027)              Mid-Term (2028–2030)               Long-Term (2030+)
──────────────────────              ──────────────────────             ──────────────────
• Latent-space WM real-time         • Unified world agent              • Fully self-improving
  inference on edge                   architecture                       data flywheel
• Standardized physical             • Physics-informed WFMs            • Provably safe world
  consistency benchmarks              with causal reasoning              model verification
• Synthetic data replaces           • Synthetic data replaces          • Generalizable world
  ~30% of real data                   ~70% of real data                  agent for all scenarios
```

---

## Contributing

This repository is a **living resource**. The FM × DWM space is moving fast — we welcome contributions from the community.

**To suggest a paper, fix an error, or add resources:**

1. Open an [issue](../../issues/new) describing the change, **or**
2. Submit a [pull request](../../pulls) with the addition.

When proposing a paper, please include:

- Title, authors, year, venue (arXiv ID if applicable)
- Which §3/§4/§5/§6 paradigm it fits (or propose a new one)
- A 1–2 sentence summary of the core contribution
- Links to: paper, code, project page (when available)

We particularly welcome:

- **Recent works** from CVPR/ICCV/NeurIPS/ICLR 2025–2026 we may have missed
- **Industry technical reports** with publicly available material
- **Benchmark proposals** addressing the gaps identified in §VII
- **Negative results / failure analyses** of FM × DWM systems

---

## Citation

If you find this manuscript or repository helpful for your research, please cite the version you used (e.g. arXiv, project PDF, or the final journal article once available):

```bibtex
@misc{bao2026fm_dwm_survey,
  title        = {Foundation Models Meet Driving World Models: A Comprehensive Survey},
  author       = {Bao, Naren and Carballo, Alexander and Javanmardi, Ehsan and Tsukada, Manabu and Takeda, Kazuya},
  year         = {2026},
  url          = {https://github.com/REPO_OWNER/Foundation-Models-Meet-Driving-World-Models},
  note         = {Manuscript; planned submission to IEEE Open Journal of Intelligent Transportation Systems (OJ-ITS); not yet peer-reviewed. Prefer the official journal or arXiv BibTeX after publication.}
}
```

Replace `REPO_OWNER` with your GitHub organization or username. When the paper is on arXiv or IEEE Xplore, switch to the venue's recommended `@article` entry (with DOI).

---

## Related Surveys

- Feng et al., *A Survey of World Models for Autonomous Driving*, arXiv:2501.11260, 2025.
- Tu et al., *The Role of World Models in Shaping Autonomous Driving*, arXiv:2502.10498, 2025.
- Ding et al., *Understanding World or Predicting Future? A Comprehensive Survey of World Models*, arXiv:2411.14499, 2024.
- Cui et al., *A Survey on Multimodal Large Language Models for Autonomous Driving*, WACV 2024.
- Yang et al., *A Survey of Large Language Models for Autonomous Driving*, arXiv:2311.01043, 2023.
- Zhou et al., *Vision Language Models in Autonomous Driving: A Survey and Outlook*, IEEE TIV, 2024.

Our survey **complements** these by being the first to systematically examine the **intersection of FMs and DWMs** through a role-based taxonomy, with extended coverage to 2026.

---

## Contact

For questions, suggestions, corrections, or collaboration:

- **Naren Bao** — [naren@g.ecc.u-tokyo.ac.jp](mailto:naren@g.ecc.u-tokyo.ac.jp)
- Open an [issue](../../issues) or [pull request](../../pulls) on this repo.

---

## Acknowledgments

This work was supported by the University of Tokyo and Nagoya University. We thank all authors of the surveyed papers for their contributions to the field, and the open-source community whose code and datasets make this research possible.

---

## License

This repository is released under the [MIT License](LICENSE).

---

<p align="center">
  <b>If this survey or paper list helps your research, please consider giving it a star!</b><br/>
  <i>Last Updated: April 2026</i>
</p>
