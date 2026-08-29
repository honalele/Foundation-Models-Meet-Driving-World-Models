# Foundation Models for Driving World Models

### Encoders, Simulators, Reasoners, and Data Engines

<p align="center">
  <a href="https://arxiv.org/abs/xxxx.xxxxx"><img src="https://img.shields.io/badge/arXiv-xxxx.xxxxx-b31b1b.svg" alt="arXiv"></a>
  <a href="#citation"><img src="https://img.shields.io/badge/Citation-BibTeX-blue.svg" alt="Citation"></a>
  <img src="https://img.shields.io/badge/Papers-200%2B-brightgreen.svg" alt="Papers">
  <img src="https://img.shields.io/badge/Coverage-2023--2026-orange.svg" alt="Coverage">
  <img src="https://img.shields.io/badge/Manuscript-Planned%3A%20IEEE%20OJ--ITS-lightgrey.svg" alt="Manuscript: planned submission to IEEE OJ-ITS">
  <img src="https://img.shields.io/badge/PRs-Welcome-success.svg" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/github/stars/xxxxx/Foundation-Models-Meet-Driving-World-Models?style=social" alt="Stars">
</p>

<p align="center">
  <b>The first systematic survey on the intersection of Foundation Models (LLMs / VLMs / WFMs / VLAs) and Driving World Models</b><br/>
  <i>covering 200+ works, 173 of them published between 2023 and 2026.</i>
</p>

<p align="center">
  <a href="#abstract">Abstract</a> •
  <a href="#why-this-survey">Why This Survey</a> •
  <a href="#whats-new">What's New</a> •
  <a href="#taxonomy-at-a-glance">Taxonomy</a> •
  <a href="#paper-list">Paper List</a> •
  <a href="#industry-platforms">Industry</a> •
  <a href="#explainability--trustworthiness">Explainability</a> •
  <a href="#benchmarks--datasets">Benchmarks</a> •
  <a href="#open-challenges">Open Challenges</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#citation">Citation</a>
</p>

> **Manuscript status.** This survey is **not yet peer-reviewed or published**. We **plan to submit** it to the *IEEE Open Journal of Intelligent Transportation Systems* (OJ-ITS). This repository may describe work in advance of the journal version; we will update badges, links, and the [citation](#citation) block once the official venue and DOI are fixed.

---

> If you find this repository helpful, please consider giving it a **star** — it helps the community discover this resource and motivates us to keep it up to date with the fast-moving FM × DWM literature.

---

## Abstract

Foundation models (FMs) are reshaping every stage of driving world models (DWMs)—from how scenes are encoded, to how futures are simulated, to how agents reason about and learn from the resulting rollouts. These FMs—encompassing large language models (LLMs), vision-language models (VLMs), video foundation models, and vision-language-action models (VLAs)—have brought new capabilities in semantic understanding, physical world reasoning, high-fidelity generation, and sequential decision-making. In this survey, we review this rapidly growing intersection, covering **more than 200 works, 173 of them published between 2023 and 2026**, encompassing both academic advances (**GAIA-2, Epona, DriveLaW, OpenDriveVLA**) and industry platforms (**Cosmos, Sora, Waymo**). We organize the literature around four functional paradigms:

- **FM as World Encoder** — leveraging FMs for generalizable, semantically rich scene representation;
- **FM as World Simulator** — using world foundation models (WFMs) for physics-aware, controllable future state simulation;
- **FM as World Reasoner** — employing LLMs/VLMs for decision-making, planning, and safety assessment within simulated worlds; and
- **FM as Data Engine** — harnessing FM-powered WFMs to build scalable closed-loop data flywheels for AD.

We state our literature-collection protocol explicitly, construct detailed comparison tables across all four dimensions, critically analyze the genuine technical contributions versus industry hype, clarify the core gaps between general video generation models and AD-specific WFMs, and chart a structured research roadmap covering **scaling laws, physical grounding, real-time edge deployment, and safety verification** for safety-critical scenarios. A companion repository with bibliography updates and auxiliary materials is maintained at [**github.com/honalele/Foundation-Models-Meet-Driving-World-Models**](https://github.com/honalele/Foundation-Models-Meet-Driving-World-Models).

---

## Why This Survey

Driving World Models (DWMs) have emerged as the cornerstone of next-generation safety-critical autonomous driving (AD), while Foundation Models (FMs) — including LLMs, VLMs, video World Foundation Models (WFMs), and Vision-Language-Action models (VLAs) — have unlocked new capabilities in semantic understanding, physical reasoning, high-fidelity generation, and sequential decision-making. **Their convergence is reshaping every stage of the AD pipeline**, from perception and prediction to planning and closed-loop control.

Existing reviews typically answer one of two questions—*what do FMs do for driving?* or *how do DWMs work?*—but not both at once. Placing them on these two axes leaves the upper-right quadrant essentially unoccupied: a review in which **the driving world model is the object of study** and **the foundation model is the organizing variable**. That is the gap this survey fills.

| Survey | Organizing Axis | Industry Platforms | VLA & Data Flywheel | Coverage |
|--------|-----------------|--------------------|---------------------|----------|
| Feng et al. 2025 | Driving WMs by output modality | Partial (no Cosmos) | Not covered | up to 2025 |
| Tu et al. 2025 | Driving WMs by representation / application | Partial | Not covered | up to 2026 |
| Ding et al. 2024 | General WMs by application domain | Not covered | Not covered | up to 2025 |
| Cui et al. 2024 | MLLM/VLM by driving task | Not covered | Not covered | up to 2024 |
| Gao et al. 2025 | FMs for scenario generation / analysis | Partial | Flywheel only | up to 2025 |
| Zhao et al. 2025 | LLMs for scenario-based ADS testing | Not covered | Not covered | up to 2025 |
| Stefanidou et al. 2025 | FMs for AD by driving task | Not covered | Not covered | up to 2025 |
| Zeng & Dong 2026 | Latent WMs for driving | Not covered | VLA only | up to 2026 |
| **Ours** | **By FM role: Encoder / Simulator / Reasoner / Data Engine** | **In depth** | **In depth** | **2023–2026** |

### Our Three Core Contributions

1. **Role-based taxonomy** — *Encoder / Simulator / Reasoner / Data Engine* — that captures how FMs are integrated into and reshape the full DWM pipeline, with formalized definitions of each paradigm.
2. **Comprehensive review of 200+ works (173 from 2023–2026)** — extending prior surveys by covering the 2025–2026 wave of FM-native driving WFMs (Cosmos 2.5 / 3, GAIA-2, Epona) and unified VLA-based driving stacks. The reference list contains 207 entries, of which 157 appear in the four role sections.
3. **Critical technical analysis** — clarifying the core gaps between general video generation models and AD-specific WFMs in the safety-critical context, and treating **explainability and trustworthiness as a first-class concern** (§VII) rather than a closing remark.

### Literature Collection

The primary window is **January 2023 to August 2026**. We searched arXiv, IEEE Xplore, and the open-access proceedings of CVPR / ICCV / ECCV / NeurIPS / ICLR / ICML / CoRL / ICRA / IROS / RSS, plus official technical reports and public keynotes for industry platforms. A work is included if it (i) targets driving or is evaluated on driving data, (ii) places an FM or an FM-conditioned world model at the center rather than as an incidental module, and (iii) reports an evaluation, a released artifact, or an architecture specific enough to compare. Industry systems are labelled as **vendor claims** wherever they appear.

---

## What's New

- **2026-08** — Manuscript revised against the IEEE OJ-ITS draft: 200+ works (173 from 2023–2026); new §VII on explainability and trustworthiness; Cosmos 3 (Nano / Edge / Super), GAIA-3 / GAIA-4, EponaV2, OmniDreams, Alpamayo-R1, WA-JEPA / Auto-JEPA, Cosmos-Drive-Dreams; explicit literature-collection protocol.
- **2026-04** — Initial public release of this **manuscript** and repository companion (4-role taxonomy, benchmark / industry-platform notes). Target journal: IEEE OJ-ITS (submission planned; not yet accepted).
- **2025-12** — Inclusion of NVIDIA Cosmos Predict 2.5 (flow-based WFM), GAIA-2 (Wayve), Epona (autoregressive diffusion), DriveLaW (latent WM + planning), OpenDriveVLA, EvoDriveVLA, AutoVLA.
- **2025-09** — Coverage extended to production-scale Chinese OEM stacks: Huawei WEWA, NIO NWM, XPeng XNGP, Horizon SuperDrive, Li Auto OTA 6.4 (E2E + VLM), Momenta R6 Flywheel.

> Tracking the latest FM × DWM works? [**Watch this repo**](../../subscription) and [**open a PR**](../../pulls) — see [Contributing](#contributing).

---

## Authors

**[Naren Bao](mailto:naren@g.ecc.u-tokyo.ac.jp)<sup>1,3</sup>, Alexander Carballo<sup>2</sup>, Ehsan Javanmardi<sup>1</sup>, Manabu Tsukada<sup>1</sup>, Kazuya Takeda<sup>3,4</sup>**

<sup>1</sup> Graduate School of Information Science and Technology, The University of Tokyo, Japan  
<sup>2</sup> Graduate School of Engineering, Gifu University, Japan  
<sup>3</sup> Graduate School of Informatics, Nagoya University, Japan  
<sup>4</sup> Special adviser of the university and affiliated to the university headquarters, Nagoya University, Japan

Corresponding author: Naren Bao (`naren@g.ecc.u-tokyo.ac.jp`).

---

## Taxonomy at a Glance

We propose a **role-based taxonomy** organized around the four core roles foundation models play in the driving world model pipeline:

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
│   FM encoding   │   WMs / JEPA    │   driving         │   loop data │
│ • Language as   │ • WFM platforms │ • VLA + WM fusion │   flywheel  │
│   world state   │   (Cosmos, GAIA)│   (3 paradigms)   │             │
└─────────────────┴─────────────────┴───────────────────┴─────────────┘
```

A work is a **world model** here if it does **action-conditioned counterfactual prediction**: supplying a different ego action yields a different predicted future. Motion forecasting, occupancy used purely as perception, and multi-task E2E stacks such as UniAD / VAD are baselines, not world models.

### The Four Foundation Model Families We Cover

| FM Family | Input → Output | Representative Models | Pre-training Scale | Core Role in DWM Pipeline |
|-----------|----------------|----------------------|--------------------|---------------------------|
| **LLM** | Text → Text | GPT-4o, LLaMA-3.1, Qwen-2.5 | 15–18T tokens | Intent generation, decision reasoning, reward design |
| **VLM** | Image/Video + Text → Text | GPT-4V, LLaVA-1.5, InternVL3, Cosmos Reason 2 | mixed units (1.2M–200B) | Scene understanding, auto-annotation, trajectory critic |
| **Video WFM** | Text/Image/Video (± action) → Video | Cosmos Predict 2.5, Cosmos Transfer 2.5, GAIA-2, Epona, Sora | 25–200M clips | World simulation, future prediction, synthetic data engine |
| **VLA** | Image + Text → Action | RT-2, OpenVLA, OpenDriveVLA | 130K–970K demos | End-to-end perception-to-action, closed-loop control |

Pre-training scales are ranges over the named models and use different units per family; they are not comparable across rows. GPT-4o, GPT-4V and Sora disclose none.

### Three Eras of Driving World Models

```
   2018 ─────── 2022 ─── 2023 ─── 2024 ─── 2025 ─── 2026 ──────
   │                    │                          │
   │   Pre-FM Era       │   FM Integration Era     │   FM-Native Physical AI Era
   │   (VAE/GAN/RNN)    │   (Diffusion + LLM)      │   (Purpose-built WFMs)
   │                    │                          │
   World Models  →  GAIA-1, DriveDreamer  →  Cosmos, GAIA-2, Epona, DriveLaW
   DriveGAN             GPT-Driver,                OpenDriveVLA, Cosmos Predict 2.5
                        MagicDrive, OccWorld       Cosmos 3, OmniDreams, Alpamayo-R1
                                                   WA-JEPA, V-JEPA 2
```

The current era is defined by purpose-built world foundation models designed natively for physical AI and autonomous driving — rather than adapting general FMs to driving tasks. Two recent features are easy to miss: platforms have begun to **tier explicitly for edge deployment** (Cosmos 3 Nano / Edge / Super), and the joint-embedding line from LeCun has produced driving-specific descendants (**V-JEPA 2 → WA-JEPA / Auto-JEPA**).

Simulator work grew fastest through 2024 and remains the largest category, but the composition has since shifted: Reasoner and Data Engine citations both rise into 2026 while Encoder work declines — the open problems have moved from *how to represent the scene* to *what to do with the predicted future*.

---

## Paper Structure

| Section | Title | Highlights |
|---------|-------|------------|
| §I | **Introduction** | Motivation, scope vs. existing surveys, three contributions |
| §II | **Preliminaries** | Literature-collection protocol; definitions (DWM, WFM, FM-Empowered DWM); four FM families; three-era timeline; unified problem formulation |
| §III | **FM as World Encoder** | VLM-driven scene understanding, pre-trained visual FM backbones, multi-modal encoding, language-as-state |
| §IV | **FM as World Simulator** | Pixel-space generative WMs (AR / Diffusion / Flow), purpose-built WFM platforms (Cosmos, GAIA-2), LLM-assisted scene generation, latent-space / JEPA WMs, online vs. offline deployment |
| §V | **FM as World Reasoner** | LLM decision making, Imagine-then-Plan, FM as reward/critic, VLA for E2E driving, three VLA + WM fusion modes |
| §VI | **FM as Data Engine** | Three-level synthetic data generation, VLM auto-annotation, sim-to-real, closed-loop data flywheel |
| §VII | **Explainability and Trustworthiness** | Fluency ≠ faithfulness; what each of the four roles actually makes inspectable; toward auditable driving models |
| §VIII | **Benchmarks and Evaluation** | Four metric families, existing datasets/benchmarks, CARLA monoculture, call for a Physical AI benchmark suite |
| §IX | **Open Challenges and Future Directions** | Six core challenges with concrete milestones |
| §X | **Conclusion** | Summary and outlook |
| App. A | **Detailed Architecture Case Studies** | DriveDreamer (two-stage diffusion), NVIDIA Cosmos (three-pillar platform) |

Each role section closes with a **Critical Analysis** subsection stating what the evidence does and does not support.

---

## Paper List

> **Legend:**
> *Year* · *Architecture / FM Family* · *Output / Capability*
> [`paper`] linked to arXiv / venue page · [`code`] linked to public repo · [`page`] linked to project / blog page when available · ★ flagged works are particularly recommended starting points.

### §III FM as World Encoder

Foundation models provide DWMs with richer, semantically meaningful scene representations. We split this into four paradigms.

**A. VLM-Driven Structured Scene Understanding**

| Method | Year | FM Used | Output / Task | Dataset | Links |
|--------|------|---------|---------------|---------|-------|
| GPT-4V on Road ★ | 2023 | GPT-4V | Scene Description / Understanding | Custom | [paper](https://arxiv.org/abs/2311.05332) |
| DriveGPT4 | 2024 | LLaMA-2 + Valley tokenizer | Text + Action QA + Planning | BDD-X | [paper](https://arxiv.org/abs/2310.01412) |
| DriveMLM | 2023 | LLaMA-7B + ViT-g/14 | Text + Action / Behavioral Plan | CARLA Town05 Long | [paper](https://arxiv.org/abs/2312.09245) |
| DriveLM ★ | 2024 | BLIP-2 | Graph QA / Perception–Planning | nuScenes | [paper](https://arxiv.org/abs/2312.14150) · [code](https://github.com/OpenDriveLab/DriveLM) |
| DriveVLM | 2024 | Qwen-VL | Text + Trajectory / Planning | nuScenes | [paper](https://arxiv.org/abs/2402.12289) |
| Cosmos Reason 2 ★ | 2025 | Custom Physical VLM | Video QA + Caption | Multi-domain | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Dolphins | 2023 | OpenFlamingo | Grounded CoT QA | DriveLM | [paper](https://arxiv.org/abs/2312.00438) |
| RAG-Driver | 2024 | LLM + RAG | Retrieval-Augmented Reasoning | nuScenes | [paper](https://arxiv.org/abs/2402.10828) |
| DriveCoT | 2024 | VLM | CoT Rationale + Action | nuScenes | [paper](https://arxiv.org/abs/2403.16996) |

**B. Pre-trained Visual FM Backbones** — CLIP, SigLIP, DINOv2, InternViT, VideoMAE V2 integrated into BEV frameworks (BEVFormer, BEVDet, TPVFormer, MAE). Driving with DINO (ACM MM 2026) uses DINO features as a unified sim-to-real bridge.

**C. Multi-modal FM Encoding** — PointCLIP, DriveLM, Cosmos / GAIA-2 multi-modal tokenizers across camera, LiDAR, radar, and CAN.

**D. Language as Unified World State**

| Method | Year | FM Used | Output / Task | Dataset | Links |
|--------|------|---------|---------------|---------|-------|
| LMDrive | 2024 | LLaMA-2 | Closed-loop E2E driving | CARLA | [paper](https://arxiv.org/abs/2312.07488) · [code](https://github.com/opendilab/LMDrive) |
| Talk2BEV | 2023 | BLIP-2 / MiniGPT-4 + GPT-4 | BEV Language Query | nuScenes | [paper](https://arxiv.org/abs/2310.02251) |

> **Critical takeaway (§III):** The four paradigms trade off along a single **fidelity–efficiency–generalization** axis. Language-as-state is the most inspectable representation in the pipeline — and also the least spatially precise. No existing work benchmarks them head-to-head on a unified task.

---

### §IV FM as World Simulator (the most active area)

The dominant paradigm is **pixel-space generative world models**, with three architectural families: autoregressive transformers, diffusion models, and flow-based models — plus latent-space / JEPA WMs and purpose-built WFM platforms.

**Architecture distribution (simulator-category papers):** Diffusion ~72% once latent diffusion is counted as diffusion. Flow-based models remain a small 2025+ cohort, but they are the architecture the largest purpose-built driving WFM platforms have converged on.

#### 4.1 Representative Video-Generation Methods

| Method | Year | Architecture | Conditioning | Output | Open | Links |
|--------|------|--------------|--------------|--------|------|-------|
| DriveGAN | 2021 | GAN | Action | Single-view | Yes | [paper](https://arxiv.org/abs/2101.03737) |
| GAIA-1 ★ | 2023 | AR Transformer (6.5B WM) | Video + Text + Action | Single-view | No | [paper](https://arxiv.org/abs/2309.17080) · [page](https://wayve.ai/thinking/scaling-gaia-1/) |
| DriveDreamer ★ | 2023 | Stable Diffusion UNet | Layout + HDMap | Single-view | Yes | [paper](https://arxiv.org/abs/2309.09777) · [code](https://github.com/JeffWang987/DriveDreamer) |
| WoVoGen | 2023 | Diffusion | BEV Layout + Text | Multi-view | Yes | [paper](https://arxiv.org/abs/2312.02934) |
| ADriver-I | 2024 | Multimodal LLM | Vision + Action | Single-view | Yes | [paper](https://arxiv.org/abs/2311.13549) |
| MagicDrive ★ | 2024 | Stable Diffusion UNet | 3D BBox + BEV | Multi-view | Yes | [paper](https://arxiv.org/abs/2310.02601) · [code](https://github.com/cure-lab/MagicDrive) |
| DrivingDiffusion | 2024 | Latent Diffusion UNet | Layout + 3D BBox | Multi-view | Yes | [paper](https://arxiv.org/abs/2310.07771) |
| Panacea | 2024 | SVD | BEV + Text | Panoramic | Yes | [paper](https://arxiv.org/abs/2311.16813) |
| GenAD | 2024 | Diffusion UNet | Trajectory + Action | Single-view | Yes | [paper](https://arxiv.org/abs/2403.09630) |
| Drive-WM | 2024 | Diffusion | Trajectory + Map | Multi-view | Yes | [paper](https://arxiv.org/abs/2311.17918) |
| Vista ★ | 2024 | Diffusion | Action + Text | Single-view | Yes | [paper](https://arxiv.org/abs/2405.17398) · [code](https://github.com/OpenDriveLab/Vista) |
| DriveDreamer-2 | 2024 | Diffusion + LLM | Text + Layout | Multi-view | Yes | [paper](https://arxiv.org/abs/2403.06845) |
| DriveWorld | 2024 | 4D Pre-train + Diffusion | Spatial-Temporal | Multi-view | Yes | [paper](https://arxiv.org/abs/2405.04390) |
| Epona ★ | 2025 | AR Diffusion | Trajectory + Action | Single-view | No† | [paper](https://arxiv.org/abs/2506.24113) (ICCV 2025) · [code](https://github.com/Kevin-thu/Epona) |
| DriveLaW ★ | 2025 | Self-supervised latent WM | Features + Ego traj. | Latent features | Yes | [paper](https://arxiv.org/abs/2406.08481) (ICLR 2025) |
| Cosmos Predict | 2025 | DiT | Text + Image + Action | Multi-view | Yes | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Cosmos Transfer | 2025 | Multi-Control Diffusion | 3D Sim + Text | Photorealistic | Yes | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Cosmos Predict 2.5 ★ | 2025 | Flow-Based DiT | Text + Image/Video‡ | Multi-view | Yes | [code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| GAIA-2 ★ | 2025 | Latent Diffusion (ST-factorized DiT) | Ego + Agents + Layout + CLIP | Multi-view | No | [paper](https://arxiv.org/abs/2503.20523) · [page](https://wayve.ai/thinking/gaia-2/) |

† Official weights were not open at the time of the table; community code is now public.  
‡ The action-conditioned Cosmos Predict 2.5 variant is documented as robot-only. Cosmos Transfer is a sim-to-real translator rather than an action-conditioned predictor.

**Also notable (not all are video generators):** MaskGWM (CVPR 2025, [paper](https://arxiv.org/abs/2502.11663)), Orbis (NeurIPS 2025, [paper](https://arxiv.org/abs/2507.13162)), DriveDreamer4D (CVPR 2025, [paper](https://arxiv.org/abs/2410.13571)), DriveScape ([paper](https://arxiv.org/abs/2409.05463)), EponaV2 (2026, [paper](https://arxiv.org/abs/2605.14696)), DriveDreamer-Policy (2026, [paper](https://arxiv.org/abs/2604.01765)).

#### 4.2 Quantitative Comparison (nuScenes FID / FVD)

Rows are grouped by source collation. Protocols are only approximately matched; **direct comparison across groups is not meaningful**.

| Method | Architecture | Views | FID ↓ | FVD ↓ |
|--------|--------------|-------|-------|-------|
| *(a) Predominantly single-view (collated by Vista)* ||||
| DriveGAN | GAN | 1 | 73.4 | 502.3 |
| DriveDreamer | Diffusion UNet | 1 | 52.6 | 452.0 |
| WoVoGen | Diffusion | 1 | 27.6 | 417.7 |
| GenAD | Diffusion UNet | 1 | 15.4 | 184.0 |
| Drive-WM | Diffusion | 3 | 15.8 | 122.7 |
| ADriver-I | Multimodal LLM | 1 | 5.5 | 97.0 |
| Vista | Diffusion | 1 | 6.9 | 89.4 |
| Epona | AR Diffusion | 1 | 7.5 | 82.8 |
| *(b) Multi-view, first-frame conditioning (collated by DriveDreamer-2)* ||||
| DriveDreamer | Diffusion UNet | 6 | 14.9 | 340.8 |
| DrivingDiffusion | Latent Diffusion | 6 | 15.8 | 332.0 |
| MagicDrive | Stable Diffusion | 6 | 16.2 | 218.1 |
| Panacea | SVD | 6 | 16.9 | 139.0 |
| DriveDreamer-2 | Diffusion + LLM | 6 | 11.2 | **55.7** |

Reported single-view FVD fell from 502.3 (GAN) / 452.0 (first diffusion DWM) to 82.8 (Epona) in a few years — a trend, not a measured ratio. DriveLaW is **not** in this table: it generates no pixels, so generation metrics do not apply.

#### 4.3 Latent-Space and JEPA World Models (the path to real-time)

| Method | Year | Architecture | Output / Capability | Dataset | Links |
|--------|------|--------------|---------------------|---------|-------|
| OccWorld | 2024 | 3D Occupancy Latent | Future Occupancy Grids | nuScenes | [paper](https://arxiv.org/abs/2311.16038) |
| MILE | 2022 | Latent Imitation | Latent Future + Control | CARLA | [paper](https://arxiv.org/abs/2210.07729) |
| Think2Drive ★ | 2024 | Latent + learned planner (no FM) | Model-based RL in latent space | CARLA v2 | [paper](https://arxiv.org/abs/2402.16720) |
| World4Drive | 2025 | Intention-aware Latent WM | Imagine-then-Plan | nuScenes / NAVSIM | [paper](https://arxiv.org/abs/2507.00603) (ICCV 2025) |
| DriveLaW ★ | 2025 | Self-supervised latent WM | Unified latent WM + planning | nuScenes / NAVSIM | [paper](https://arxiv.org/abs/2406.08481) (ICLR 2025) |
| V-JEPA 2 | 2025 | Joint-embedding predictive | Video prior → planner with little interaction data | Multi-domain | [paper](https://arxiv.org/abs/2506.09985) |
| WA-JEPA | 2026 | World-Action JEPA | Future-directed, action-coupled JEPA for driving | — | [paper](https://arxiv.org/abs/2608.20974) |
| Auto-JEPA | 2026 | Latent intent WM | Predicts action-relevant features, not the scene | — | [paper](https://arxiv.org/abs/2607.29031) |
| OmniNWM | 2025 | Omniscient navigation WM | RGB + semantics + depth + intrinsic policy eval | — | [paper](https://arxiv.org/abs/2510.18313) |

The field's real trend is a **progressive narrowing of what is predicted** — from pixels, to scene features, to the action-relevant subspace — with each step trading inspectability for tractability.

> **Critical takeaway (§IV):** All three generative architectures learn statistical correlations in pixel space, **not physical causality**. A visually convincing video of a car braking does not imply the model understands friction or inertia. Flow-based ≠ single-step: few-step inference comes from a separately distilled checkpoint. Future architectures must incorporate explicit physical inductive biases, not just scaling.

---

### §V FM as World Reasoner

Four reasoning paradigms that let driving agents make decisions based on world-model rollouts. Rows whose FM type is **None** are non-FM controls, retained deliberately.

#### 5.1 LLM as High-Level Decision Maker

| Method | Year | FM Type | WM Integrated | Paradigm | Benchmark | Links |
|--------|------|---------|---------------|----------|-----------|-------|
| GPT-Driver | 2023 | GPT-3.5 | No | Direct Trajectory Generation | nuScenes | [paper](https://arxiv.org/abs/2310.01415) |
| LanguageMPC | 2023 | GPT-4 | No | LLM + MPC | HighwayEnv | [paper](https://arxiv.org/abs/2310.03026) |
| Agent-Driver | 2023 | GPT-4 | No | LLM Agent with Tools | nuScenes | [paper](https://arxiv.org/abs/2311.10813) |
| DiLu | 2024 | LLaMA | No | Reflective Memory Learning | HighwayEnv | [paper](https://arxiv.org/abs/2309.16292) (ICLR 2024) |
| Dolphins | 2023 | OpenFlamingo | No | Grounded CoT | DriveLM | [paper](https://arxiv.org/abs/2312.00438) |
| RAG-Driver | 2024 | LLM + RAG | No | Retrieval-Augmented Planning | nuScenes | [paper](https://arxiv.org/abs/2402.10828) |
| DriveCoT | 2024 | VLM | No | Chain-of-Thought Reasoning | nuScenes | [paper](https://arxiv.org/abs/2403.16996) |
| LMDrive | 2024 | LLaMA-2 | No | Language-Guided E2E | CARLA | [paper](https://arxiv.org/abs/2312.07488) |

Without a world model, the LLM is flying blind: it can reason about what *should* happen but cannot verify what *would* happen.

#### 5.2 Imagine-then-Plan (LLM / WM Joint Reasoning) ★

LLM proposes intents → WM rolls out futures → VLM critic evaluates → optimal trajectory selected.

| Method | Year | FM Type | WM Integrated | Paradigm | Benchmark | Links |
|--------|------|---------|---------------|----------|-----------|-------|
| World4Drive | 2025 | Vision FM encoder | Yes | Intention-aware latent rollout | nuScenes | [paper](https://arxiv.org/abs/2507.00603) |
| Think2Drive | 2024 | None (model-based RL) | Yes | Latent WM + learned planner | CARLA v2 | [paper](https://arxiv.org/abs/2402.16720) |
| DriveLaW | 2025 | None (self-sup. latent WM) | Yes | Latent future-feature prediction | nuScenes / NAVSIM | [paper](https://arxiv.org/abs/2406.08481) |
| Cosmos Reason | 2025 | Physical VLM | Offline critic | Physical-plausibility rollout critic | Multi-domain | [page](https://www.nvidia.com/en-us/ai/cosmos/) |

Think2Drive and DriveLaW use **no LLM**. Any claim that FM-based reasoning is necessary for long-tail competence has to outperform these controls, not merely match them. Cosmos Reason scores Predict rollouts offline to filter synthetic data; the official materials document **no runtime imagine-then-plan loop**.

A VLM critic is **not safety verification**. Simulator and critic are typically built from related FMs, so their errors are correlated; a natural-language score of “this looks safe” certifies agreement between two correlated estimators, not compliance with a safety property.

#### 5.3 FM as Reward Function and Critic

| Method | Year | FM Type | Paradigm | Benchmark | Links |
|--------|------|---------|----------|-----------|-------|
| DriveVLM | 2024 | Qwen-VL | VLM Critic + RL | nuScenes | [paper](https://arxiv.org/abs/2402.12289) |
| DiLu (Reflection) | 2024 | LLaMA | Self-critique Reward Refinement | HighwayEnv | [paper](https://arxiv.org/abs/2309.16292) |
| Cosmos Reason | 2025 | Physical VLM | Trajectory critic + Data filter | Multi-domain | [page](https://www.nvidia.com/en-us/ai/cosmos/) |

Reported gains are, to our knowledge, always measured against hand-engineered baselines and never against a strong non-FM critic under matched compute.

#### 5.4 Vision-Language-Action (VLA) for End-to-End Driving

| Method | Year | FM Type | WM Integration | Paradigm | Benchmark | Links |
|--------|------|---------|----------------|----------|-----------|-------|
| OpenDriveVLA ★ | 2025 | VLA | Implicit | E2E VLA | nuScenes | [paper](https://arxiv.org/abs/2503.23463) |
| SimLingo ★ | 2025 | VLA (VLM-based) | No | Language–Action Alignment | Bench2Drive / CARLA | [paper](https://arxiv.org/abs/2503.09594) (CVPR 2025) · [code](https://github.com/RenzKa/simlingo) |
| Epona | 2025 | AR Diffusion WFM | Shared | Joint Generation + Planning | NAVSIM | [paper](https://arxiv.org/abs/2506.24113) |
| EvoDriveVLA | 2026 | VLA | — | Collaborative Distillation | — | [paper](https://arxiv.org/abs/2603.09465) |
| AutoVLA | 2025 | VLA | — | Adaptive Reasoning + RL Fine-tune | — | [paper](https://arxiv.org/abs/2506.13757) (NeurIPS 2025) |
| Alpamayo-R1 | 2025 | Cosmos-Reason + diffusion decoder | Modular VLA | Long-tail driving VLA | — | [paper](https://arxiv.org/abs/2511.00088) |

SimLingo's Action Dreaming task aligns language with the action space; it does **not** perform video-level world simulation. An emerging production trend (especially among Chinese OEMs) is simplifying VLA to **VA (Vision-Action)** for edge latency, retaining language mainly for debugging.

#### 5.5 Three Paradigms of VLA + WM Fusion

| Mode | Architecture | Latency | Trainability | Status / Adoption |
|------|--------------|---------|--------------|-------------------|
| **Mode 1** | WM as Front-End Predictor | High (sequential) | Independent | Tesla FSD, XPeng XNGP, NIO NWM |
| **Mode 2** | WM as Post-hoc Safety Screen | Medium (projected) | Independent | Design proposal — **no published implementation** |
| **Mode 3** | Shared Backbone Joint Training | Low | Joint (complex) | Epona, DriveLaW (research) |

**Open-loop nuScenes planning (averaged L2 convention, ego-status-free):** once the reporting convention is unified, the best WM-integrated planner (DriveLaW, L2@3s = 0.76 m) leads the best planner without one (GenAD, 0.78 m) by **two centimetres** — a margin this benchmark does not resolve. Neither DriveLaW nor World4Drive contains a language model, so even that margin is evidence for latent future-state prediction, not for FM-based reasoning.

> **Critical takeaway (§V – the latency–safety paradox):** The methods with the strongest safety assessment are also the slowest, and **none of the WM-integrated planners in the comparison table reports inference latency**. Imagine-then-plan has not demonstrated safety verification in any sense a certification authority would accept. The field needs **hierarchical System 1 / System 2 reasoning** — fast VLA for routine driving, slower imagine-then-plan for safety-critical situations.

---

### §VI FM as Data Engine (the most impactful practical role)

A scalable, closed-loop data flywheel: **collect real data → fine-tune WFM → generate synthetic data → VLM auto-annotate → train policy → deploy → collect more real data**.

Safety-critical driving data is **not a different kind of data**; a near-collision is a merge with a smaller gap. Two properties do survive that objection: **sampling economics** (the tail is expensive) and **inductive-bias dominance** (in the tail the model's prior does most of the work).

#### 6.1 Three-Level Synthetic Data Generation

| Method | FM Type | Output | Sim2Real | Auto-Label | Links |
|--------|---------|--------|----------|------------|-------|
| Cosmos Predict 2.5 | Flow-Based WFM | Multi-view Video | Yes | Yes (via Reason 2) | [code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| Cosmos Transfer 2.5 | Multi-Control WFM | Photorealistic Video | Yes | Yes (via Reason 2) | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Cosmos-Drive-Dreams | Cosmos WFM suite | Rare-edge-case SDG | Yes | Yes | [paper](https://arxiv.org/abs/2506.09042) |
| MagicDrive | Diffusion WFM | Multi-view Image | No | No | [code](https://github.com/cure-lab/MagicDrive) |
| DriveDreamer-2 | Diffusion + LLM | Video | No | No | [paper](https://arxiv.org/abs/2403.06845) |
| DriveScape | Diffusion WFM | Multi-view Video | No | No | [paper](https://arxiv.org/abs/2409.05463) |
| ChatSim | LLM Agent + NeRF | Editable Scene | No | No | [paper](https://arxiv.org/abs/2402.05746) |
| MARS | NeRF (modular backbones) | Reconstructed Scenes | Yes | No | [paper](https://arxiv.org/abs/2307.15058) |
| CTG++ | LLM + Diffusion | Traffic Scenarios | Yes | No | [paper](https://arxiv.org/abs/2305.13242) |
| Waymax | Behavior Model | Traffic Simulation | No | No | [paper](https://arxiv.org/abs/2310.08710) |
| UniSim ★ | Neural feature fields | Interactive Simulation | Yes | No | [paper](https://arxiv.org/abs/2308.01898) (CVPR 2023 Highlight) |

The three levels: **Scenario-level** (full driving scenarios from text) → **Sensor-level** (matching real hardware: multi-camera + LiDAR + radar) → **Event-level** (long-tail safety-critical events).

#### 6.2 VLM-Driven Auto-Annotation and Active Learning

DriveLM (graph QA labels), LISA (open-vocabulary / reasoning segmentation; demonstrated on general-domain imagery, not driving), Dolphins (event-level behavioural descriptions; qualitative), Cosmos Reason / InternVL3 (physical-AI VLM filtering). After several flywheel turns, models train on data generated by earlier models — and **none of the surveyed platforms publishes a lineage record**.

#### 6.3 Sim-to-Real Adaptation with World Foundation Models

Multi-Control Style Transfer (Cosmos Transfer) · Domain Randomization · Fine-tuning with real data · Neural reconstruction (MARS, Street Gaussians, EmerNeRF, S3Gaussian, NeuRAD). Most reported transfer still stops at closed-loop simulation.

> **Critical takeaway (§VI):** Synthetic data **complements rather than replaces** real data. We deliberately avoid predicting a synthetic-to-real ratio: the useful ratio is task-, domain-, and validation-purpose-dependent, and we could not locate a published sweep of that ratio on a driving perception task. The most promising direction is **targeted synthesis** — generating specific scenarios identified as underrepresented via active learning or failure analysis.

---

## Industry Platforms

### Open & Industry-Scale WFM Platforms

| Platform | Owner | Modalities | Open Weights | Notes |
|----------|-------|------------|--------------|-------|
| **NVIDIA Cosmos** ★ | NVIDIA | Predict + Transfer + Reason | Yes (most) | Three-pillar platform; flow-based Predict 2.5; Curator / CDS / Evaluator stack. Cosmos 3 (Aug 2026) ships **Nano / Edge / Super** tiers plus few-step distilled variants. [page](https://www.nvidia.com/en-us/ai/cosmos/) · [Predict 2.5 code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| **OmniDreams** | NVIDIA | Real-time AR, action-conditioned | — | Mid-/post-trains a Cosmos diffusion model into a real-time closed-loop generator. [paper](https://arxiv.org/abs/2606.03159) |
| **Alpamayo-R1** | NVIDIA | Cosmos-Reason + diffusion decoder | — | Modular VLA that puts Reason *inside* a driving policy. [paper](https://arxiv.org/abs/2511.00088) |
| **Wayve GAIA-2** ★ | Wayve | Controllable multi-view from fleet | No (proprietary) | Latent diffusion, ST-factorized DiT. [paper](https://arxiv.org/abs/2503.20523) · [page](https://wayve.ai/thinking/gaia-2/) |
| **Wayve GAIA-3 / GAIA-4** | Wayve | AV evaluation / Simulation 2.0 | No | Corporate blog posts (Dec 2025 / Aug 2026) **without technical reports** — recorded as vendor claims. [GAIA-3](https://wayve.ai/thinking/gaia-3/) · [GAIA-4](https://wayve.ai/thinking/gaia-4/) |
| **OpenAI Sora** | OpenAI | Text-to-video (general) | No | Not driving-specific, but raises the bar for what general WFMs can do. |
| **Tesla Occupancy Networks** | Tesla | 8-cam → volumetric occupancy | No | Public talks (AI Day / CVPR 2022 WAD); occupancy as world-state input to an MCTS planner. |

Industry platforms win on compute, data, and visual fidelity. Academic work competes on a different axis: it isolates a single design variable and shows that the variable, not the scale, produced the effect — an experiment platform releases are structurally unable to run.

### Production-Scale Driving Stacks (publicly announced)

> Compiled from official keynotes, developer-conference announcements, and corporate technical blogs — **not peer-reviewed evidence**, but evidence that the WM and E2E paradigms are being validated at production scale. Huawei WEWA could not be traced to a stable primary source and is retained only as a publicly claimed direction.

| Company | Stack Name | Paradigm | Generative WM? | Reasoning Layer | Year |
|---------|------------|----------|----------------|-----------------|------|
| **Tesla** | FSD + Occupancy Network | E2E + Occupancy WM | Partial (occupancy) | MCTS-based planner | 2022+ |
| **Huawei** | WEWA (ADS 4.0) | E2E + WM | Yes (World Engine) — unverified | World Action module | 2025 |
| **NIO** | NWM (NAD Architecture 2.0) | WM-centric | Yes (AR generative, 216 futures / 100 ms) | Trajectory selection over rollouts | 2024 |
| **XPeng** | XNet + XPlanner + XBrain (XNGP) | E2E + Occupancy WM | Partial (2K occupancy, short-horizon) | XBrain large model | 2024 |
| **Horizon Robotics** | SuperDrive (Journey 6) | VA-style E2E | No | No explicit VLM in safety path | 2024 |
| **Li Auto** | E2E + VLM (OTA 6.4) | Dual System 1/2 | No | Explicit VLM as System 2 critic | 2024 |
| **Momenta** | R6 Flywheel | RL-based E2E | No (data-flywheel-centric) | VA-style, no VLM critic | 2024 |

Three architectural patterns recur across these stacks, mirroring academic directions: **(i)** occupancy-centric latent spaces, **(ii)** dual fast/slow controllers (System 1 / System 2), **(iii)** RL-based closed-loop data flywheels. Current industry practice favors **Mode 1** for production; **Mode 3** leads on research benchmarks.

---

## Explainability & Trustworthiness

Foundation models entered driving partly on the promise that a model which can *talk about* a scene is easier to trust than one which cannot. That promise deserves scrutiny.

**Fluency is not faithfulness.** A natural-language rationale is generated by the same forward pass that produced the action, under an objective that rewards plausibility rather than causal accuracy. An unfaithful explanation is worse than no explanation, because it manufactures unearned confidence.

The four roles differ sharply in what they make inspectable:

| Role | What is inspectable | Catch |
|------|---------------------|-------|
| **Encoder** | Language-as-state is human-readable | Spatial imprecision; transparency and precision trade off |
| **Simulator** | Pixel-space rollouts — a human can *watch* the phantom vehicle | Latent WMs buy speed by giving this up |
| **Reasoner** | Highest *apparent* transparency | Lowest *verified* transparency (see §V) |
| **Data Engine** | Largely invisible | Silent VLM filters bias the training distribution with no artifact a reviewer could examine — the least-examined trustworthiness risk of the four |

Three directions look substantive rather than cosmetic: **counterfactual explanation** (what change to the scene would have changed the decision), **architectural interpretability** (the explanation is a load-bearing intermediate), and **evidential / calibrated uncertainty**. By the standard of whether an explanation changes what a safety argument can claim, the field does not yet have a method it can put in front of a regulator.

---

## Benchmarks & Datasets

### Evaluation Metric Families

| Family | Core Metrics | Critical Limitation |
|--------|--------------|---------------------|
| **Visual Fidelity** | FID, FVD, LPIPS, SSIM | Ignores physics, action alignment, and downstream utility |
| **Prediction Accuracy** | ADE/FDE, L2, multi-view consistency | Almost exclusively open-loop |
| **Physical Consistency** | Object permanence, kinematic violation, collision realism, traffic-rule compliance | **No standardized protocol** |
| **Downstream Task** | Closed-loop collision, perception mAP gain, planning success | Hard to standardize across policies / datasets |

The metric that is cheapest to compute and most often reported (visual fidelity) tests the weakest link; the one that determines whether the model is worth deploying (downstream, closed-loop) is reported least.

### Datasets

| Dataset | Scale | Modalities | Use Cases |
|---------|-------|------------|-----------|
| **nuScenes** | 1000 × 20 s scenes | 6-cam + LiDAR + radar + HD maps | Most widely used DWM benchmark |
| **Waymo Open** | 1150 × 20 s scenes (~6 h) | High-res cam + LiDAR | Geographic diversity, not raw duration |
| **BDD100K** | 100K videos | Diverse weather / lighting | Video generation training |
| **KITTI** | — | Cam + LiDAR | Earlier-gen perception baseline |
| **Argoverse** | — | Cam + LiDAR + maps | Motion forecasting |

### Closed-Loop Benchmarks

| Benchmark | Mode | Use Case |
|-----------|------|----------|
| **CARLA** | Simulator | Closed-loop driving policy / WM eval — and a **monoculture** in this literature |
| **CARLA Leaderboard 2.0** | Hard routes | SOTA closed-loop benchmark |
| **NAVSIM** | Data-driven, non-reactive | Open-loop metrics that align better with closed-loop than displacement error |
| **nuPlan** | Closed-loop from its own 1500 h corpus (4 cities) | Planning benchmark — **not** a re-annotation of nuScenes |
| **Waymo Sim Agents Challenge** | Multi-agent | Reactive agent simulation |
| **SHIFT** | Synthetic | Domain adaptation |
| **ScenarioNet** / **MetaDrive** | Open-source / procedural | Large-scale scenario simulation, RL throughput |
| **Waymax** | Data-driven, accelerator-native | Large-scale agent simulation, not photorealism |
| **DrivingGen** (ICLR 2026) | Generative video WM benchmark | Emerging shared yardstick — not yet community-standard |

### Why We Call for New Benchmarks

All current benchmarks are **insufficient for FM-empowered driving WMs**:

1. They are designed for perception/prediction, not generative WMs.
2. They lack standardized protocols for **physical consistency** and **action controllability**.
3. They do not include comprehensive **long-tail safety-critical scenarios**.
4. They do not evaluate the full **data flywheel** capabilities.

A field that validates almost exclusively on one open simulator (CARLA) risks mistaking properties of that simulator for properties of driving.

We propose five components for a new standardized Physical AI benchmark suite (§VIII.C):

1. Standardized **physical consistency** evaluation (object permanence, kinematics, collision realism, traffic rule compliance)
2. **Action controllability** benchmark
3. **Long-tail scenario** suite
4. **Downstream task** evaluation protocol
5. **Efficiency** benchmark (latency, memory, deployable on edge) — including **compute reporting** (latency + parameter count + accuracy together), which the FM-based planners currently omit

---

## Open Challenges

We identify **six core open challenges** with concrete milestones for the field:

| # | Challenge | Current Status | Concrete Milestone |
|---|-----------|----------------|--------------------|
| **1** | **Scaling Laws for WFMs** | Visual fidelity scales, physical understanding does not. Cosmos Predict 2.5 ships 2B and 14B variants; no public study relates scale to physics-violation rate. | A public scaling-law study reporting compute-vs.-physics-violation rates at ≥3 model scales |
| **2** | **Physical Grounding & Causal Reasoning** | Geometric / dynamic / causal violations persist (vehicles through guardrails, red-light run-throughs, braking without visible cause) | Sub-1% kinematic-violation rate on a standardized physical consistency benchmark |
| **3** | **Real-Time Edge Deployment** | NVIDIA reports 31.0 s (4B) – 109.2 s (13B) on a single H100 for 32 frames at 640×1024; eight GPUs do not close the gap. Real-time is reported only at 320×512 on the smallest model with speculative decoding. | Sub-50 ms world-model rollout for 3 s horizon on Jetson AGX Orin (or an equivalent automotive SoC) |
| **4** | **Unified World Agent Architecture** | Frankenstein systems: separate encoder → WM → VLM critic → planner | A single-model VLA + WM achieving competitive CARLA LB 2.0 with explicit ≥5 s rollouts |
| **5** | **Safety Verification & Trustworthy AI** | Phantom objects, obstacle erasure, temporal hallucination; no calibrated uncertainty | Published safety case: <10⁻⁶/hour false-prediction rate with calibrated uncertainty |
| **6** | **Multi-Agent Interaction & Game-Theoretic Modeling** | Agents treated as passive background — "frozen world" | A Waymo Sim Agents-style benchmark scoring ego-conditional reactive behavior |

### Future Technology Roadmap

```
Short-Term (2026–2027)              Mid-Term (2028–2030)               Long-Term (2030+)
──────────────────────              ──────────────────────             ──────────────────
• Latent-space WM real-time         • Unified world agent              • Fully self-improving
  inference on edge                   architecture                       data flywheel
• Standardized physical             • Physics-informed WFMs            • Provably safe world
  consistency benchmarks              with causal reasoning              model verification
• Synthetic data reliably           • Synthetic-to-real ratio          • Generalizable world
  improves long-tail perception       no longer the binding              agent for all scenarios
                                      constraint
```

Milestones are stated as **capabilities rather than quantitative targets**. We deliberately avoid predicting a synthetic-to-real data ratio.

---

## Contributing

This repository is a **living resource**. The FM × DWM space is moving fast — we welcome contributions from the community.

**To suggest a paper, fix an error, or add resources:**

1. Open an [issue](../../issues/new) describing the change, **or**
2. Submit a [pull request](../../pulls) with the addition.

When proposing a paper, please include:

- Title, authors, year, venue (arXiv ID if applicable)
- Which §III/§IV/§V/§VI paradigm it fits (or propose a new one)
- A 1–2 sentence summary of the core contribution
- Links to: paper, code, project page (when available)

We particularly welcome:

- **Recent works** from CVPR/ICCV/NeurIPS/ICLR 2025–2026 we may have missed
- **Industry technical reports** with publicly available material
- **Benchmark proposals** addressing the gaps identified in §VIII
- **Negative results / failure analyses** of FM × DWM systems

---

## Citation

If you find this manuscript or repository helpful for your research, please cite the version you used (e.g. arXiv, project PDF, or the final journal article once available):

```bibtex
@misc{bao2026fm_dwm_survey,
  title        = {Foundation Models for Driving World Models: Encoders, Simulators, Reasoners, and Data Engines},
  author       = {Bao, Naren and Carballo, Alexander and Javanmardi, Ehsan and Tsukada, Manabu and Takeda, Kazuya},
  year         = {2026},
  url          = {https://github.com/honalele/Foundation-Models-Meet-Driving-World-Models},
  note         = {Manuscript; planned submission to IEEE Open Journal of Intelligent Transportation Systems (OJ-ITS); not yet peer-reviewed. Prefer the official journal or arXiv BibTeX after publication.}
}
```

When the paper is on arXiv or IEEE Xplore, switch to the venue's recommended `@article` entry (with DOI).

---

## Related Surveys

- Feng et al., *A Survey of World Models for Autonomous Driving*, arXiv:2501.11260, 2025.
- Tu et al., *The Role of World Models in Shaping Autonomous Driving*, arXiv:2502.10498, 2025.
- Ding et al., *Understanding World or Predicting Future? A Comprehensive Survey of World Models*, ACM CSUR, 2025.
- Zidan et al., *World Models: A Comprehensive Survey of Architectures, Methodologies, Reasoning Paradigms, and Applications*, arXiv:2606.00133, 2026.
- Gao et al., *Foundation Models for Scenario Generation and Analysis*, IEEE OJ-ITS, 2025.
- Zhao et al., *Large Language Models in Scenario-Based Testing of Automated Driving Systems*, IEEE T-ITS, 2026.
- Stefanidou et al., *Foundation Models in Autonomous Driving: A Review of Current Tasks and Applications*, IEEE OJ-ITS, 2025.
- Zeng & Dong, *Latent World Models for Automated Driving*, arXiv:2603.09086, 2026 (under review, T-ITS).
- Xu et al., *A Survey on End-to-End Autonomous Driving Training*, IEEE T-ITS, 2026.
- Cui et al., *A Survey on Multimodal Large Language Models for Autonomous Driving*, WACV 2024.
- Yang et al., *A Survey of Large Language Models for Autonomous Driving*, arXiv:2311.01043, 2023.
- Zhou et al., *Vision Language Models in Autonomous Driving: A Survey and Outlook*, IEEE TIV, 2024.

Our survey **complements** these by treating the driving world model as the object of study and the foundation model as the organizing variable, with extended coverage through August 2026.

---

## Contact

For questions, suggestions, corrections, or collaboration:

- **Naren Bao** — [naren@g.ecc.u-tokyo.ac.jp](mailto:naren@g.ecc.u-tokyo.ac.jp)
- Open an [issue](../../issues) or [pull request](../../pulls) on this repo.

---

## Acknowledgments

This work was supported by JST, CRONOS, Japan Grant Number JPMJCS24K8. We thank all authors of the surveyed papers for their contributions to the field, and the open-source community whose code and datasets make this research possible.

---

## License

This repository is released under the [MIT License](LICENSE). The survey manuscript itself is intended for publication under a Creative Commons Attribution 4.0 License.

---

<p align="center">
  <b>If this survey or paper list helps your research, please consider giving it a star!</b><br/>
  <i>Last Updated: August 2026</i>
</p>
