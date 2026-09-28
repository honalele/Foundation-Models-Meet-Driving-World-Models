# Foundation Models for Driving World Models

### Encoders, Simulators, Reasoners, and Data Engines

<p align="center">
  <a href="https://arxiv.org/abs/xxxx.xxxxx"><img src="https://img.shields.io/badge/arXiv-xxxx.xxxxx-b31b1b.svg" alt="arXiv"></a>
  <a href="#citation"><img src="https://img.shields.io/badge/Citation-BibTeX-blue.svg" alt="Citation"></a>
  <img src="https://img.shields.io/badge/Works-200%2B-brightgreen.svg" alt="Works">
  <img src="https://img.shields.io/badge/Coverage-2023--2026-orange.svg" alt="Coverage">
  <img src="https://img.shields.io/badge/Manuscript-Submitted%3A%20IEEE%20OJ--ITS-lightgrey.svg" alt="Manuscript: submitted to IEEE OJ-ITS">
  <img src="https://img.shields.io/badge/PRs-Welcome-success.svg" alt="PRs Welcome">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/github/stars/honalele/Foundation-Models-Meet-Driving-World-Models?style=social" alt="Stars">
</p>

<p align="center">
  <b>A role-based review of how Foundation Models (LLMs / VLMs / WFMs / VLAs) reshape Driving World Models</b><br/>
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

> **Manuscript status.** This survey is **submitted to the *IEEE Open Journal of Intelligent Transportation Systems* (OJ-ITS) and under revision; it is not yet accepted or published.** This repository may describe work in advance of the journal version; we will update badges, links, and the [citation](#citation) block once the official venue and DOI are fixed.

---

> If you find this repository helpful, please consider giving it a **star** — it helps the community discover this resource and motivates us to keep it up to date with the fast-moving FM × DWM literature.

---

## Abstract

Foundation models (FMs) are reshaping every stage of driving world models (DWMs)—from how scenes are encoded, to how futures are simulated, to how agents reason about and learn from the resulting rollouts. These FMs—encompassing large language models (LLMs), vision-language models (VLMs), video foundation models, and vision-language-action models (VLAs)—have brought new capabilities in semantic understanding, physical world reasoning, high-fidelity generation, and sequential decision-making. In this survey, we review this rapidly growing intersection, covering **more than 200 works, 173 of them published between 2023 and 2026**, encompassing both academic advances (**GAIA-2, Epona, LAW, OpenDriveVLA**) and industry platforms (**Cosmos, Sora, Wayve GAIA**). We organize the literature around four functional paradigms:

- **FM as World Encoder** — leveraging FMs for generalizable, semantically rich scene representation;
- **FM as World Simulator** — using world foundation models (WFMs) for physics-aware, controllable future state simulation;
- **FM as World Reasoner** — employing LLMs/VLMs for decision-making, planning, and safety assessment within simulated worlds; and
- **FM as Data Engine** — harnessing FM-powered WFMs to build scalable closed-loop data flywheels for autonomous driving (AD).

We state our literature-collection protocol explicitly, construct detailed comparison tables across all four dimensions, critically analyze the genuine technical contributions versus industry hype, clarify the core gaps between general video generation models and AD-specific WFMs, and chart a structured research roadmap covering **scaling laws, physical grounding, real-time edge deployment, and safety verification** for safety-critical scenarios. A companion repository with bibliography updates and auxiliary materials is maintained at [**github.com/honalele/Foundation-Models-Meet-Driving-World-Models**](https://github.com/honalele/Foundation-Models-Meet-Driving-World-Models).

---

## Why This Survey

Driving World Models (DWMs) have emerged as the cornerstone of next-generation safety-critical autonomous driving (AD), while Foundation Models (FMs) — including LLMs, VLMs, video World Foundation Models (WFMs), and Vision-Language-Action models (VLAs) — have brought new capabilities in semantic understanding, physical reasoning, high-fidelity generation, and sequential decision-making. **Their convergence is reshaping every stage of the AD pipeline**, from perception and prediction to planning and closed-loop control.

Existing reviews overlap this space with different organizing lenses: some make the driving world model the object of study, others organize FM work by driving task or testing stage. This survey treats **the driving world model as the object of study** and **the foundation model's role as the organizing variable**. The contribution is a connected, role-based synthesis of overlapping literatures — not a claim that prior reviews omit every component.

| Survey | Venue | Organizing Axis | Industry Platforms | VLA & Data Flywheel | Coverage | Refs. |
|--------|-------|-----------------|--------------------|---------------------|----------|-------|
| Feng et al. | arXiv | Generation / planning / prediction–planning interaction | Partial (no Cosmos) | Not covered | up to 2025 | — |
| Tu et al. | arXiv | Representation space × application | Partial | Not covered | up to 2026 | 178 |
| Ding et al. | ACM CSUR | Understanding present / predicting future, then domain | — | Not covered | up to 2025 | — |
| Cui et al. | WACV Workshops | MLLM/VLM by driving task | Partial | — | up to 2024 | — |
| Gao et al. | IEEE OJ-ITS | FM type × scenario generation / analysis | Partial | — | up to 2025 | 345† |
| Zhao et al. | IEEE T-ITS | LLMs by testing-pipeline stage | Partial | — | up to 2025 | 250 |
| Stefanidou et al. | IEEE OJ-ITS | FMs by driving task | — | — | up to 2025 | — |
| Zeng & Dong | arXiv (under review, T-ITS) | Latent WMs: simulation / planning / synthesis / reasoning | — | Partial | up to 2026 | 91 |
| **Ours** | **Submitted** | **By FM role: Encoder / Simulator / Reasoner / Data Engine** | **In depth** | **In depth** | **2023–2026** | **207** |

“—” means not established from the accessible material, not narrow coverage. Reference counts are for the explicitly identified source versions; † Gao et al. report 345 *reviewed papers*. These are transparent proxies, not a ranking of review quality.

### Our Three Contributions

1. **Role-based taxonomy** — *Encoder / Simulator / Reasoner / Data Engine* — that captures how FMs are integrated into and reshape the full DWM pipeline, with formalized definitions of each paradigm.
2. **Up-to-date review of 200+ works (173 from 2023–2026)** — extending coverage to the 2025–2026 wave of FM-native driving WFMs (Cosmos 2.5, GAIA-2, Epona) and unified VLA-based driving stacks. The reference list has 207 entries, 156 of which are cited in the four role sections.
3. **Critical technical analysis** — of FMs' genuine contributions versus limitations in the safety-critical context, clarifying the gaps between general video models and AD-specific WFMs, and treating **explainability and trustworthiness as a first-class concern** (§VII).

### What Kind of Review This Is

This is a **curated narrative review**, not a PRISMA-style systematic review; “comprehensive” should be read in that sense.

- **Window:** January 2023 – August 2026. Foundational earlier work is included when it is load-bearing (about one reference in six).
- **Sources:** arXiv (cs.CV / cs.RO / cs.LG / cs.AI), IEEE Xplore, open-access proceedings of CVPR / ICCV / ECCV / NeurIPS / ICLR / ICML / CoRL / ICRA / IROS / RSS, Crossref / OpenAlex, plus official technical reports, model cards and keynotes for NVIDIA, Wayve, Tesla and major Chinese OEMs. Industry material is labelled as **vendor claims**.
- **Inclusion:** (i) targets driving or is evaluated on driving data; (ii) an FM, or an FM-built / conditioned / evaluated world model, is central; (iii) reports an evaluation, released artifact, or comparable architecture.
- **Verification:** mechanisms and selected numbers were checked against primary sources. We did not re-run methods; tables keep source-reported values and flag protocol differences instead of forming a leaderboard.
- **Known biases:** English-language venues dominate; industry systems appear through what their owners disclose; the cut-off moves while the field is this active.

---

## What's New

- **2026-09** — README synced to the revised manuscript: DriveLaW renamed to its paper name **LAW**; survey-positioning table and reference counts refreshed; planning and FVD tables re-grouped with explicit protocol exceptions; population-share and cross-era improvement claims removed; policy–WM coupling modes restated without production attributions; Cosmos 3 tiers corrected (Nano / Super available, Edge announced); challenge milestones restated as evidence requirements.
- **2026-08** — Manuscript revised against the IEEE OJ-ITS draft: 200+ works; new §VII on explainability and trustworthiness; Cosmos 3, GAIA-3 / GAIA-4, EponaV2, OmniDreams, Alpamayo-R1, WA-JEPA / Auto-JEPA, Cosmos-Drive-Dreams; explicit literature-collection protocol.
- **2026-04** — Initial public release of this **manuscript** and repository companion (4-role taxonomy, benchmark / industry-platform notes).
- **2025-12** — Inclusion of NVIDIA Cosmos Predict 2.5 (flow-based WFM), GAIA-2 (Wayve), Epona (autoregressive diffusion), LAW (latent WM + planning), OpenDriveVLA, EvoDriveVLA, AutoVLA.
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
│ • Language      │ • WFM platforms │ • Policy + WM     │   flywheel  │
│   interfaces    │   (Cosmos, GAIA)│   coupling modes  │             │
└─────────────────┴─────────────────┴───────────────────┴─────────────┘
```

The roles are **non-exclusive**: NVIDIA Cosmos, for example, simultaneously realizes the Simulator (Predict), Reasoner (Reason), and Data Engine (Curator) roles.

**What counts as a world model here.** A model is a world model if it does **action-conditioned counterfactual prediction**: supplying a different ego action yields a different predicted future. Motion forecasting, occupancy used purely as perception, and multi-task E2E stacks such as UniAD / VAD are included only as baselines. A **foundation model** is defined by breadth of pre-training and multi-task adaptability, not parameter count — which is why Think2Drive and LAW are treated as non-FM controls.

### The Four Foundation Model Families We Cover

| FM Family | Input → Output | Representative Models | Training-data Unit | Core Role in DWM Pipeline |
|-----------|----------------|----------------------|--------------------|---------------------------|
| **LLM** | Text → Text | GPT-4o, LLaMA-3.1, Qwen-2.5 | Text tokens | Intent generation, decision reasoning, reward design, prompt engineering for scene generation |
| **VLM** | Image/Video + Text → Text | GPT-4V, LLaVA-1.5, InternVL3, Cosmos Reason 2 | Image–text pairs / video / tokens | Scene understanding, captioning, synthetic data annotation, trajectory evaluation, safety assessment |
| **Video WFM** | Text/Image/Video (± action) → Video | Cosmos Predict 2.5, Cosmos Transfer 2.5, Sora, GAIA-2, Epona | Video clips / hours | World simulation, future prediction, action-conditioned generation, synthetic data, sim-to-real |
| **VLA** | Image + Text → Action | RT-2, OpenVLA, OpenDriveVLA | Action-labelled trajectories | End-to-end perception-to-action, closed-loop control, action-conditioned rollout |

Training-data units differ between families and training stages; no cross-family scale ranking is intended.

### Three Eras of Driving World Models

```
   2018 ─────── 2021 ─── 2023 ─── 2024 ─── 2025 ─── 2026 ──────
   │                    │                          │
   │   Pre-FM Era       │   FM Integration Era     │   FM-Native Physical AI Era
   │   (VAE/GAN/RNN)    │   (Diffusion + LLM)      │   (Purpose-built WFMs)
   │                    │                          │
   World Models         GAIA-1, DriveDreamer       Cosmos, GAIA-2, OpenDriveVLA, Epona
   DriveGAN             GPT-Driver, MagicDrive     V-JEPA 2, Cosmos-Drive-Dreams
                        OccWorld, Vista, LAW       Cosmos Predict 2.5, Alpamayo-R1
                                                   OmniDreams, Cosmos 3 / WA-JEPA
```

The current era is defined by purpose-built world foundation models designed natively for physical AI and autonomous driving. Two recent features are easy to miss: platform releases have begun to **tier explicitly for edge deployment** (Cosmos 3), and the joint-embedding line from LeCun has produced driving-specific descendants (**V-JEPA 2 → WA-JEPA / Auto-JEPA**). The core question has shifted from “can we generate realistic driving videos?” to “can we build a faithful, physically grounded, actionable simulator that enables safe closed-loop driving?”

**Two independent simulator design choices.** Generation mechanism (how a future is predicted) and predictive representation (where it is predicted) are separate axes:

| Example | Mechanism | Predictive representation |
|---------|-----------|---------------------------|
| GAIA-1 | Autoregressive | Discrete latent tokens |
| DriveDreamer | Diffusion | Continuous latents |
| Epona | AR + diffusion | Continuous latents |
| Cosmos Predict 2.5 | Flow matching | Continuous latents |
| LAW | Feature prediction | Continuous features; no video decoder |

These rows illustrate combinations, not prevalence. Pixel-space output does not imply pixel-space prediction.

---

## Paper Structure

| Section | Title | Highlights |
|---------|-------|------------|
| §I | **Introduction** | Motivation, scope vs. existing surveys, three contributions |
| §II | **Preliminaries** | Literature-collection protocol; definitions (DWM, WFM, FM-Empowered DWM); four FM families; three-era timeline; unified problem formulation incl. shared-backbone case |
| §III | **FM as World Encoder** | VLM-driven scene understanding, pre-trained visual FM backbones, multi-modal encoding, language interfaces |
| §IV | **FM as World Simulator** | Pixel-space generative WMs (AR / Diffusion / Flow), WFM platforms (Cosmos, GAIA-2), LLM-assisted scene generation, latent-space / JEPA WMs, online vs. offline deployment |
| §V | **FM as World Reasoner** | LLM decision making, Imagine-then-Plan, FM as reward/critic, VLA for E2E driving, policy–WM coupling paradigms |
| §VI | **FM as Data Engine** | Three-level synthetic data generation, VLM auto-annotation, sim-to-real, closed-loop data flywheel |
| §VII | **Explainability and Trustworthiness** | Fluency ≠ faithfulness; what each role makes inspectable; toward auditable driving models |
| §VIII | **Benchmarks and Evaluation** | Four metric families, evaluation capability matrix, CARLA monoculture, call for a Physical AI benchmark suite |
| §IX | **Open Challenges and Future Directions** | Six challenges with evidence requirements and milestones |
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
| DriveGPT4 | 2024 | LLaMA-2 + Valley tokenizer | Text + Action / QA + Planning | BDD-X | [paper](https://arxiv.org/abs/2310.01412) |
| DriveMLM | 2023 | LLaMA-7B + ViT-g/14 | Text + Action / Behavioral Planning | CARLA Town05 Long | [paper](https://arxiv.org/abs/2312.09245) |
| DriveLM ★ | 2024 | BLIP-2 | Graph QA / Perception–Planning | nuScenes | [paper](https://arxiv.org/abs/2312.14150) · [code](https://github.com/OpenDriveLab/DriveLM) |
| DriveVLM | 2024 | Qwen-VL | Text + Trajectory / Planning | nuScenes | [paper](https://arxiv.org/abs/2402.12289) |
| Cosmos Reason 2 ★ | 2025 | Custom Physical VLM | Video QA + Caption | Multi-domain | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Dolphins | 2023 | OpenFlamingo | Grounded CoT QA | BDD-X | [paper](https://arxiv.org/abs/2312.00438) |
| RAG-Driver | 2024 | LLM + RAG | Retrieval-Augmented Explanation | BDD-X / Spoken-SAX | [paper](https://arxiv.org/abs/2402.10828) |
| DriveCoT | 2024 | Video Swin Transformer (no LLM) | Structured CoT + Action | CARLA | [paper](https://arxiv.org/abs/2403.16996) |

What the numbers show: on BDD-X, DriveGPT4 improves explanation quality over ADAPT (CIDEr 99.1 vs. 85.4) and more than halves speed RMSE (1.30 vs. 3.02 m/s); DriveMLM reports 76.1 driving score on CARLA Town05 Long, 4.7 points above an Apollo baseline. These task-specific gains use different units and cannot be pooled into a general measure of FM benefit.

**B. Pre-trained Visual FM Backbones** — CLIP, SigLIP, DINOv2, InternViT, VideoMAE integrated into BEV frameworks (BEVFormer, BEVDet, TPVFormer). Two patterns dominate: pre-trained tokenizers (GAIA-1 discrete DINO-distilled; Cosmos Predict 2.5 continuous VAE) and conditional feature injection. Driving with DINO (ACM MM 2026) uses DINO features as a sim-to-real bridge; 3D FM priors add robustness to camera-viewpoint shift (CVPR-W 2026).

**C. Multi-modal FM Encoding** — PointCLIP, DriveLM, Cosmos shared video tokenization, and GAIA-2's separate conditioning signals (ego dynamics, agents, road semantics, CLIP embeddings); cooperative infrastructure LiDAR extends the observable state in occluded scenes.

**D. Language Interfaces to World Representations**

| Method | Year | FM Used | Output / Task | Dataset | Links |
|--------|------|---------|---------------|---------|-------|
| LMDrive | 2024 | LLaMA-2 | Waypoints / Language-guided E2E driving | CARLA | [paper](https://arxiv.org/abs/2312.07488) · [code](https://github.com/opendilab/LMDrive) |
| Talk2BEV | 2023 | BLIP-2 / MiniGPT-4 + GPT-4 | BEV Language Query | nuScenes | [paper](https://arxiv.org/abs/2310.02251) |

Language provides a readable interface without replacing the continuous internal state; LMDrive does not establish natural language as the primary world-state representation.

> **Critical takeaway (§III):** The four paradigms trade off along a single **fidelity–efficiency–generalization** axis. Readable language descriptions need not faithfully explain the policy. A matched comparison — controlling downstream task and training budget — is still missing.

---

### §IV FM as World Simulator (the most active area)

The dominant paradigm is **pixel-space generative world models**, with three architectural families — autoregressive transformers, diffusion models, and flow-based models — plus latent-space / JEPA WMs and purpose-built WFM platforms.

#### 4.1 Representative Video Generators and Related Components

| Method | Year | Architecture | Conditioning | Output | Open | Links |
|--------|------|--------------|--------------|--------|------|-------|
| DriveGAN | 2021 | GAN | Action | Single-view | Yes | [paper](https://arxiv.org/abs/2104.15060) |
| GAIA-1 ★ | 2023 | AR Transformer (6.5B WM) | Video + Text + Action | Single-view | No | [paper](https://arxiv.org/abs/2309.17080) · [page](https://wayve.ai/thinking/scaling-gaia-1/) |
| DriveDreamer ★ | 2023 | Stable Diffusion UNet | Layout + HDMap | Single-view | Yes | [paper](https://arxiv.org/abs/2309.09777) · [code](https://github.com/JeffWang987/DriveDreamer) |
| WoVoGen | 2023 | Diffusion | BEV Layout + Text | Multi-view | Yes | [paper](https://arxiv.org/abs/2312.02934) |
| ADriver-I | 2024 | Multimodal LLM | Vision + Action | Single-view | Yes | [paper](https://arxiv.org/abs/2311.13549) |
| MagicDrive ★ | 2024 | Stable Diffusion UNet | 3D BBox + BEV | Multi-view | Yes | [paper](https://arxiv.org/abs/2310.02601) · [code](https://github.com/cure-lab/MagicDrive) |
| DrivingDiffusion | 2024 | Latent Diffusion UNet | Layout + 3D BBox | Multi-view | Yes | [paper](https://arxiv.org/abs/2310.07771) |
| Panacea | 2024 | Stable Diffusion 2.1 | BEV + Text | Panoramic | Yes | [paper](https://arxiv.org/abs/2311.16813) |
| GenAD | 2024 | Diffusion UNet | Trajectory + Action | Single-view | Yes | [paper](https://arxiv.org/abs/2403.09630) |
| Drive-WM | 2024 | Diffusion | Trajectory + Map | Multi-view | Yes | [paper](https://arxiv.org/abs/2311.17918) |
| Vista ★ | 2024 | Diffusion | Action + Text | Single-view | Yes | [paper](https://arxiv.org/abs/2405.17398) · [code](https://github.com/OpenDriveLab/Vista) |
| DriveDreamer-2 | 2024 | Diffusion + LLM | Text + Layout | Multi-view | Yes | [paper](https://arxiv.org/abs/2403.06845) |
| DriveWorld | 2024 | Memory state-space pre-training | Spatial-Temporal | Occupancy + Action | Yes | [paper](https://arxiv.org/abs/2405.04390) |
| Epona ★ | 2025 | AR Diffusion | Trajectory + Action | Single-view | — | [paper](https://arxiv.org/abs/2506.24113) (ICCV 2025) · [code](https://github.com/Kevin-thu/Epona) |
| LAW ★ | 2025 | Self-supervised latent WM | Features + Ego traj. | Latent features | Yes | [paper](https://arxiv.org/abs/2406.08481) (ICLR 2025) |
| Cosmos Predict | 2025 | DiT | Text + Image + Action | Multi-view | Yes | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Cosmos Transfer | 2025 | Multi-Control Diffusion | 3D Sim + Text | Photorealistic | Yes | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| Cosmos Predict 2.5 ★ | 2025 | Flow-Based Model | Text + Image/Video‡ | Multi-view | Yes | [code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| GAIA-2 ★ | 2025 | Latent Diffusion (ST-factorized DiT) | Ego + Agents + Layout + CLIP | Multi-view | No | [paper](https://arxiv.org/abs/2503.20523) · [page](https://wayve.ai/thinking/gaia-2/) |

Not every row is a world model in the sense above: **Cosmos Transfer** is a sim-to-real translator, and **DriveWorld / LAW** are non-video predictive representations included for contrast. “Open” records the source-listed artifact status, not a guarantee that code, weights and training data are all available; “—” means the status at the cut-off was not established.  
‡ The action-conditioned Cosmos Predict 2.5 variant is documented as robot-only.

**Also notable:** MaskGWM (CVPR 2025, [paper](https://arxiv.org/abs/2502.11663)), Orbis (NeurIPS 2025, [paper](https://arxiv.org/abs/2507.13162)), DriveDreamer4D (CVPR 2025, [paper](https://arxiv.org/abs/2410.13571)), DriveScape ([paper](https://arxiv.org/abs/2409.05463)), EponaV2 (2026, [paper](https://arxiv.org/abs/2605.14696)), DriveDreamer-Policy (2026, [paper](https://arxiv.org/abs/2604.01765)), RAYNOVA (CVPR 2026, [paper](https://arxiv.org/abs/2602.20685)), GeoFlow (ECCV 2026, [paper](https://arxiv.org/abs/2608.12203)), InfiniVerse (ECCV-W 2026, [paper](https://arxiv.org/abs/2606.31109)).

#### 4.2 Reported Generation Results (nuScenes FID / FVD)

Rows are grouped by source collation. **Neither within-group nor across-group values establish a matched ranking** — conditioning, sample length, resolution and evaluation implementations differ. No results are bolded.

| Method | Architecture | Resolution | Views | Frames | FID ↓ | FVD ↓ |
|--------|--------------|------------|-------|--------|-------|-------|
| *(a) Predominantly single-view prediction (collated by Vista)* ||||||
| DriveGAN | GAN | 256×256 | 1 | 16 | 73.4 | 502.3 |
| DriveDreamer | Diffusion UNet | 128×192 | 1 | 16 | 52.6 | 452.0 |
| WoVoGen | Diffusion | 256×448 | 1 | 16 | 27.6 | 417.7 |
| GenAD | Diffusion UNet | 256×448 | 1 | 16 | 15.4 | 184.0 |
| Drive-WM | Diffusion | 192×384 | 3 | 16 | 15.8 | 122.7 |
| ADriver-I | Multimodal LLM | — | 1 | 16 | 5.5 | 97.0 |
| Vista | Diffusion | 576×1024 | 1 | 25 | 6.9 | 89.4 |
| Epona | AR Diffusion | — | 1 | — | 7.5 | 82.8 |
| *(b) Multi-view, first-frame conditioning (collated by DriveDreamer-2)* ||||||
| DriveDreamer | Diffusion UNet | — | 6 | 16 | 14.9 | 340.8 |
| DrivingDiffusion | Latent Diffusion | 512×512 | 6 | 16 | 15.8 | 332.0 |
| MagicDrive | Stable Diffusion | 224×400 | 6 | 16 | 16.2 | 218.1 |
| DriveDreamer-2 | Diffusion + LLM | — | 6 | 16 | 11.2 | 55.7 |
| *(c) Panacea original report, arXiv v1 (separate protocol)* ||||||
| Panacea | Stable Diffusion | 256×512 | 6 | 8 | 16.96 | 139.0 |

These values cannot establish a cross-era improvement factor or isolate the effect of foundation-model scale; FVD measures distributional similarity to real video, not physical correctness. LAW generates no pixels, so generation metrics do not apply to it.

#### 4.3 Latent-Space and JEPA World Models

| Method | Year | Architecture | Output / Capability | Dataset | Links |
|--------|------|--------------|---------------------|---------|-------|
| OccWorld | 2024 | 3D Occupancy Latent | Future Occupancy Grids | nuScenes | [paper](https://arxiv.org/abs/2311.16038) |
| MILE | 2022 | Latent Imitation | Latent Future + Control | CARLA | [paper](https://arxiv.org/abs/2210.07729) |
| Think2Drive ★ | 2024 | Latent WM + learned planner (no FM) | Model-based RL; DS 56.8 / RC 98.6% | CARLA v2 | [paper](https://arxiv.org/abs/2402.16720) |
| World4Drive | 2025 | Intention-aware Latent WM | Imagine-then-Plan | nuScenes / NAVSIM | [paper](https://arxiv.org/abs/2507.00603) (ICCV 2025) |
| LAW ★ | 2025 | Self-supervised latent WM | Latent future-feature prediction + planning | nuScenes / NAVSIM | [paper](https://arxiv.org/abs/2406.08481) (ICLR 2025) |
| V-JEPA 2 | 2025 | Joint-embedding predictive | Video prior → planner with little interaction data | Multi-domain | [paper](https://arxiv.org/abs/2506.09985) |
| OmniNWM | 2025 | Omniscient navigation WM | RGB + semantics + depth + intrinsic policy eval | — | [paper](https://arxiv.org/abs/2510.18313) |
| WA-JEPA | 2026 | World-Action JEPA | Future-directed, action-coupled JEPA for driving | — | [paper](https://arxiv.org/abs/2608.20974) |
| Auto-JEPA | 2026 | Latent intent WM | Predicts action-relevant features, not the scene | — | [paper](https://arxiv.org/abs/2607.29031) |
| DeepSight | 2026 | Latent-state WM | Long-horizon latent rollouts | — | [paper](https://arxiv.org/abs/2605.10564) (ICML 2026) |
| DLWM | 2026 | Dual latent WMs | Gaussian-centric pre-training | — | [paper](https://arxiv.org/abs/2604.00969) (CVPR 2026) |

The field's real trend is a **progressive narrowing of what is predicted** — from pixels, to scene features, to the action-relevant subspace — with each step trading inspectability for tractability. Latent models are the natural candidates for online deployment, but **none reports inference latency**, so this remains an argument from architecture rather than measurement.

> **Critical takeaway (§IV):** A generative training objective alone does not establish causal or physical validity, whether prediction occurs in pixels or latents. “Flow-based” ≠ “single-step”: few-step Cosmos inference comes from a separately distilled checkpoint, and no matched flow-vs-diffusion comparison exists. Future architectures must incorporate explicit physical inductive biases, not just scaling.

---

### §V FM as World Reasoner

Four reasoning paradigms that let driving agents make decisions based on world-model rollouts. Rows whose FM type is **None** are non-FM controls, retained deliberately. “Implicit” marks a model that predicts future states internally without exposing a rollout that can be queried under alternative actions.

#### 5.1 LLM as High-Level Decision Maker

| Method | Year | FM Type | WM Integrated | Paradigm | Benchmark | Links |
|--------|------|---------|---------------|----------|-----------|-------|
| GPT-Driver | 2023 | GPT-3.5 | No | Direct Trajectory Generation | nuScenes | [paper](https://arxiv.org/abs/2310.01415) |
| LanguageMPC | 2023 | GPT-4 | No | LLM + MPC | HighwayEnv | [paper](https://arxiv.org/abs/2310.03026) |
| Agent-Driver | 2023 | GPT-4 | No | LLM Agent with Tools | nuScenes | [paper](https://arxiv.org/abs/2311.10813) |
| DiLu | 2024 | LLaMA | No | Reflective Memory Learning | HighwayEnv | [paper](https://arxiv.org/abs/2309.16292) (ICLR 2024) |
| Dolphins | 2023 | OpenFlamingo | No | Grounded CoT | BDD-X | [paper](https://arxiv.org/abs/2312.00438) |
| RAG-Driver | 2024 | LLM + RAG | No | Retrieved Explanation | BDD-X / Spoken-SAX | [paper](https://arxiv.org/abs/2402.10828) |
| DriveCoT | 2024 | None (Video Swin) | No | Structured CoT Prediction | CARLA | [paper](https://arxiv.org/abs/2403.16996) |
| LMDrive | 2024 | LLaMA-2 | No | Language-Guided E2E | CARLA | [paper](https://arxiv.org/abs/2312.07488) |

Without a world model, the LLM can reason about what *should* happen but cannot verify what *would* happen.

#### 5.2 Imagine-then-Plan (LLM / WM Joint Reasoning) ★

LLM proposes intents → WM rolls out futures → VLM critic evaluates → optimal trajectory selected.

| Method | Year | FM Type | WM Integrated | Paradigm | Benchmark | Links |
|--------|------|---------|---------------|----------|-----------|-------|
| World4Drive | 2025 | Vision FM encoder | Yes | Intention-aware latent rollout | nuScenes | [paper](https://arxiv.org/abs/2507.00603) |
| Think2Drive | 2024 | None (model-based RL) | Yes | Latent WM + learned planner | CARLA v2 | [paper](https://arxiv.org/abs/2402.16720) |
| LAW | 2025 | None (self-sup. latent WM) | Yes | Latent future-feature prediction | nuScenes / NAVSIM | [paper](https://arxiv.org/abs/2406.08481) |
| Epona | 2025 | AR Diffusion WFM | Yes (Shared) | Joint Generation + Planning | NAVSIM | [paper](https://arxiv.org/abs/2506.24113) |
| Cosmos Reason | 2025 | Physical VLM | Offline only | Physical-plausibility rollout critic | Multi-domain | [page](https://www.nvidia.com/en-us/ai/cosmos/) |

Also in this line: Reason–Imagine–Act (ITSC 2026, [paper](https://arxiv.org/abs/2605.24004)), OWMDrive causality-aware 4D occupancy WM (IROS 2026, [paper](https://arxiv.org/abs/2606.30421)), See Tomorrow, Act Today (CVPR 2026, [paper](https://arxiv.org/abs/2605.07195)), and VLA world models (2026, [paper](https://arxiv.org/abs/2604.09059)).

Think2Drive and LAW use **no LLM**; any claim that FM-based reasoning is necessary for long-tail competence has to outperform these controls, not merely match them. Cosmos Reason scores Predict rollouts **offline** to filter synthetic data; the official materials document no runtime imagine-then-plan loop. GAIA-2 contains no reasoning module.

**A VLM critic is not safety verification.** Three failure modes follow from selecting the action whose *imagined* outcome scores best: **correlated error** (simulator and critic share FM priors), **model exploitation** (the arg max favors actions the model is wrong-but-optimistic about, and gets worse as the candidate set grows), and **distribution shift**. The literature has shown improved average-case planning, not safety verification; admissibility checks on rollouts ([Oefinger et al., RSS 2026](https://arxiv.org/abs/2607.07196)) are a first step.

#### 5.3 FM as Reward Function and Critic

This is a **proposed integration pattern**, distinct from established planning and reflection methods:

| Method | Year | FM Type | What it actually does | Benchmark | Links |
|--------|------|---------|-----------------------|-----------|-------|
| DriveVLM | 2024 | Qwen-VL | Scene description / analysis + hierarchical planning — not RL reward learning | nuScenes | [paper](https://arxiv.org/abs/2402.12289) |
| DiLu | 2024 | LLaMA | Reflection and memory — not a learned scalar reward | HighwayEnv | [paper](https://arxiv.org/abs/2309.16292) |
| Cosmos Reason | 2025 | Physical VLM | Physical-plausibility assessment and data filtering | Multi-domain | [page](https://www.nvidia.com/en-us/ai/cosmos/) |

Hand-engineered rewards are auditable statements of domain knowledge; FM critics trade that auditability for expressiveness, move fragility from reward to prompt, are expensive per candidate, and may share failure modes with the policy. A convincing evaluation should compare learned and hand-engineered critics under matched compute, against a strong non-FM critic.

#### 5.4 Vision-Language-Action (VLA) for End-to-End Driving

| Method | Year | FM Type | WM Integration | Paradigm | Benchmark | Links |
|--------|------|---------|----------------|----------|-----------|-------|
| OpenDriveVLA ★ | 2025 | VLA | Implicit | E2E VLA | nuScenes | [paper](https://arxiv.org/abs/2503.23463) |
| SimLingo ★ | 2025 | VLA (VLM-based) | No | Language–Action Alignment | Bench2Drive / CARLA | [paper](https://arxiv.org/abs/2503.09594) (CVPR 2025) · [code](https://github.com/RenzKa/simlingo) |
| AutoVLA | 2025 | VLA | — | Adaptive Reasoning + RL Fine-tune | — | [paper](https://arxiv.org/abs/2506.13757) (NeurIPS 2025) |
| Alpamayo-R1 | 2025 | Cosmos-Reason + diffusion decoder | Modular VLA | Long-tail driving VLA | — | [paper](https://arxiv.org/abs/2511.00088) |
| EvoDriveVLA | 2026 | VLA | — | Collaborative Distillation | — | [paper](https://arxiv.org/abs/2603.09465) |
| PixelPilot | 2026 | VLA | — | Scaling driving VLAs | — | [paper](https://arxiv.org/abs/2607.04637) (ECCV 2026) |
| ExploreVLA | 2026 | VLA | Dense WM | World modelling + exploration | — | [paper](https://arxiv.org/abs/2604.02714) (ECCV 2026) |
| MindVLA-U1 | 2026 | VLA | — | Unified streaming; reports VLA > VA | — | [paper](https://arxiv.org/abs/2605.12624) |

SimLingo's Action Dreaming aligns language with the action space; it does **not** perform video-level world simulation. An emerging production trend (especially among Chinese OEMs) simplifies VLA to **VA (Vision-Action)** for edge latency; MindVLA-U1 contests this from the VLA side, but it is a single work and the latency argument stands regardless.

#### 5.5 Reported Planning Results

nuScenes L2 (m) and collision (%) at 1 / 2 / 3 s, frame-averaged L2 convention. Protocol exceptions are separated. **No cross-protocol ranking or significance is implied.**

| Method | Paradigm | L2 1s | L2 2s | L2 3s | Col 1s | Col 2s | Col 3s | WM |
|--------|----------|-------|-------|-------|--------|--------|--------|----|
| *End-to-end / modular (no explicit WM)* |||||||||
| ST-P3 | Multi-task E2E | 1.33 | 2.11 | 2.90 | 0.23 | 0.62 | 1.27 | No |
| VAD-Base | Vectorized E2E | 0.41 | 0.70 | 1.05 | 0.07 | 0.17 | 0.41 | No |
| GenAD | Generative E2E | 0.28 | 0.49 | 0.78 | 0.08 | 0.14 | 0.34 | No |
| *World-model-integrated* |||||||||
| OccWorld-D | 3D Occ WM | 0.39 | 0.73 | 1.18 | 0.11 | 0.19 | 0.67 | Yes |
| Drive-WM | Multiview WM | 0.43 | 0.77 | 1.20 | 0.10 | 0.21 | 0.48 | Yes |
| World4Drive | Latent Imagine | 0.23 | 0.47 | 0.81 | 0.02 | 0.12 | 0.33 | Yes |
| LAW (perception) | Latent WM | 0.24 | 0.46 | 0.76 | 0.08 | 0.10 | 0.39 | Yes |
| *Protocol exceptions (not directly comparable)* |||||||||
| UniAD§ | Multi-task E2E | 0.48 | 0.96 | 1.65 | 0.05 | 0.17 | 0.71 | No |
| GPT-Driver‡ | LLM Planner | 0.20 | 0.40 | 0.70 | 0.04 | 0.12 | 0.36 | No |
| SparseDrive-S¶ | Sparse E2E | 0.29 | 0.58 | 0.96 | 0.01 | 0.05 | 0.18 | No |

§ per-horizon L2 · ‡ ego-state input · ¶ distinct collision implementation. CARLA closed-loop rows (each on its own, incompatible suite): InterFuser DS 68.3 (Town05 Long), TCP-Ens DS 75.1 (LB 1.0), LMDrive DS 36.2 / RC 46.5% (LangAuto), MILE DS 61.1 / RC 97.4% (Town05), Think2Drive DS 56.8 / RC 98.6% (LB 2.0 / CARLA v2).

LAW (0.76 m) and GenAD (0.78 m) at L2@3s are numerically close, but that proximity does not establish equivalence or significance; LAW's result supports evaluating latent future-feature prediction, not attributing a gain to language-model reasoning.

#### 5.6 Policy and World Model Coupling Paradigms

| Mode | Architecture | Trade-off | Status |
|------|--------------|-----------|--------|
| **Mode 1** | WM as front-end predictor (upstream of the policy) | Independent training; sequential inference latency | Occupancy-based production stacks motivate the separation, but public material does not establish that they implement this exact counterfactual-rollout interface |
| **Mode 2** | WM as post-hoc safety screen (downstream of the policy) | Rollout latency on every screened decision; needs a validated trigger and fallback | Design proposal — **latency and safety properties require empirical validation** |
| **Mode 3** | Shared backbone joint training | Shared supervision and parameters; possible task interference | Epona (decoded video), LAW (feature prediction) |

These are coupling patterns, not a performance ranking. Neither shared features nor an action head alone makes a system a VLA.

> **Critical takeaway (§V – the latency–safety paradox):** The methods with the most thorough safety assessment are also the slowest. VAD reports 59.5–628.3 ms across E2E baselines (non-automotive GPUs), so the latency problem predates FMs — but **none of the WM-integrated planners reports latency, parameter count and accuracy together**, so we cannot say whether FM-based reasoning costs 2× or 100×. The field needs **hierarchical System 1 / System 2 reasoning** — fast policies for routine driving, slower imagine-then-plan for safety-critical situations.

---

### §VI FM as Data Engine

A scalable, closed-loop data flywheel: **collect real data → fine-tune WFM → generate synthetic data → VLM auto-annotate → train policy → deploy → collect more real data**.

Safety-critical driving data is **not a different kind of data**; a near-collision is a merge with a smaller gap. Two properties survive that objection: **sampling economics** (n examples of a rate-p event need ~n/p miles) and **inductive-bias dominance** (in the tail, the model's prior does most of the work, so more common-case data does not constrain it).

#### 6.1 Three-Level Synthetic Data Generation

| Method | FM Type | Output | Sim2Real | Auto-Label | Links |
|--------|---------|--------|----------|------------|-------|
| Cosmos Predict 2.5 | Flow-Based WFM | Multi-view Video | Yes | Yes (via Reason 2) | [code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| Cosmos Transfer 2.5 | Multi-Control WFM | Photorealistic Video | Yes | Yes (via Reason 2) | [page](https://www.nvidia.com/en-us/ai/cosmos/) |
| MagicDrive | Diffusion WFM | Multi-view Image | No | No | [code](https://github.com/cure-lab/MagicDrive) |
| DriveDreamer-2 | Diffusion + LLM | Video | No | No | [paper](https://arxiv.org/abs/2403.06845) |
| ChatSim | LLM Agent + NeRF | Editable Scene | No | No | [paper](https://arxiv.org/abs/2402.05746) |
| MARS | NeRF (modular backbones) | Reconstructed Scenes | Yes | No | [paper](https://arxiv.org/abs/2307.15058) |
| DriveScape | Diffusion WFM | Multi-view Video | No | No | [paper](https://arxiv.org/abs/2409.05463) |
| CTG++ | LLM + Diffusion | Traffic Scenarios | Yes | No | [paper](https://arxiv.org/abs/2305.13242) |
| Waymax | Behavior Model | Traffic Simulation | No | No | [paper](https://arxiv.org/abs/2310.08710) |
| UniSim ★ | Neural feature fields | Interactive Simulation | Yes | No | [paper](https://arxiv.org/abs/2308.01898) (CVPR 2023 Highlight) |

The three levels: **Scenario-level** (full driving scenarios from text) → **Sensor-level** (matching real hardware: multi-camera + LiDAR + radar) → **Event-level** (long-tail safety-critical events). At platform scale, **Cosmos-Drive-Dreams** ([paper](https://arxiv.org/abs/2506.09042)) wraps a driving-specialized Cosmos suite in a rare-edge-case SDG pipeline.

2026 safety-critical synthesis makes risk an explicit control variable: CCFM collision-constrained flow matching ([paper](https://arxiv.org/abs/2607.04451)), risk-controllable multi-view diffusion ([paper](https://arxiv.org/abs/2603.11534)), ECoSim data-efficient traffic-sim fine-tuning ([paper](https://arxiv.org/abs/2607.00545)), and zero-label JEPA scenario-complexity detection ([paper](https://arxiv.org/abs/2606.28383)).

#### 6.2 VLM-Driven Auto-Annotation and Data Filtering

DriveLM (graph QA labels), LISA (reasoning segmentation; demonstrated on general-domain imagery, not driving), Dolphins (event-level behavioural descriptions; qualitative), Cosmos Reason / InternVL3 (physical-AI VLM filtering).

**The price is partial loss of control over the dataset:** composition becomes a property of the generator's prior, label semantics drift with annotator versions, and provenance is hard to reconstruct after several flywheel turns. **None of the surveyed platforms publishes a lineage record.**

#### 6.3 Sim-to-Real Adaptation with World Foundation Models

Multi-Control Style Transfer (Cosmos Transfer) · Domain Randomization · Fine-tuning with real data · Neural reconstruction (MARS, Street Gaussians, EmerNeRF, S3Gaussian, NeuRAD) · Asymmetric style transfer (ASTAD) · Domain-invariant representations (Driving with DINO). Most reported transfer still stops at closed-loop simulation.

> **Critical takeaway (§VI):** Synthetic data **complements rather than replaces** real data. The most-cited evidence is narrow: MagicDrive's augmentation gains shrink as the perception model trains longer (+3.08 → +2.52 → +0.25 mAP at 0.5× / 1× / 2× epochs). We know of no published sweep of the synthetic-to-real *ratio* on a driving perception task. The best-supported direction is **targeted synthesis** of scenarios identified as underrepresented.

---

## Industry Platforms

### Open & Industry-Scale WFM Platforms

| Platform | Owner | Modalities | Open Weights | Notes |
|----------|-------|------------|--------------|-------|
| **NVIDIA Cosmos** ★ | NVIDIA | Predict + Transfer + Reason | Yes (most) | Three-pillar platform; flow-based Predict 2.5 (2B / 14B); Curator / CDS / Evaluator stack. Data pipeline: ~20M hours of raw video *across Physical AI domains* (not driving only) → ~100M curated clips. [page](https://www.nvidia.com/en-us/ai/cosmos/) · [Predict 2.5 code](https://github.com/nvidia-cosmos/cosmos-predict2.5) |
| **Cosmos 3** | NVIDIA | Next-generation WFM family | Yes | June 2026 launch: **Nano / Super available, Edge tier announced**. An edge tier motivates deployment study but does not by itself establish on-vehicle latency. [announcement](https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Launches-Cosmos-3-the-Open-Frontier-Foundation-Model-for-Physical-AI/default.aspx) |
| **OmniDreams** | NVIDIA | Real-time AR, action-conditioned | — | Mid-/post-trains a Cosmos diffusion model into a real-time closed-loop generator. [paper](https://arxiv.org/abs/2606.03159) |
| **Alpamayo-R1** | NVIDIA | Cosmos-Reason + diffusion decoder | — | Modular VLA that moves Reason *inside* a driving policy; now a common driving-VLA baseline. [paper](https://arxiv.org/abs/2511.00088) |
| **Wayve GAIA-2** ★ | Wayve | Controllable multi-view from fleet | No (proprietary) | Latent diffusion, ST-factorized DiT; CLIP text conditioning without a VLM in the loop. [paper](https://arxiv.org/abs/2503.20523) · [page](https://wayve.ai/thinking/gaia-2/) |
| **Wayve GAIA-3 / GAIA-4** | Wayve | AV evaluation / Simulation 2.0 | No | Corporate blog posts (Dec 2025 / Aug 2026) **without technical reports** — recorded as vendor claims. [GAIA-3](https://wayve.ai/thinking/gaia-3/) · [GAIA-4](https://wayve.ai/thinking/gaia-4/) |
| **OpenAI Sora** | OpenAI | Text-to-video (general) | No | Not driving-specific; raises the question of whether purpose-built driving WFMs keep an advantage. |
| **Tesla Occupancy Networks** | Tesla | 8-cam → volumetric occupancy | No | Public talks (AI Day / CVPR 2022 WAD); occupancy as world-state input to an MCTS planner. |

Industry platforms emphasize scale and broad generation capability; that does not establish superiority under matched evaluation. Academic work competes by isolating a single design variable — e.g. LAW delivers competitive planning without pixel generation, MaskGWM improves generalization without platform-scale resources.

### Production-Scale Driving Stacks (publicly announced)

> Compiled from public presentations, corporate materials and media reports — **not peer-reviewed evidence**. Huawei WEWA could not be traced to a stable primary source and is retained only as a publicly claimed direction.

| Company | Stack Name | Paradigm | Generative WM? | Reasoning Layer | Year |
|---------|------------|----------|----------------|-----------------|------|
| **Huawei** | WEWA (ADS 4.0) | E2E + WM | Partial (untraced vendor claim) | World Action module | 2025 |
| **NIO** | NWM (NAD Architecture 2.0) | WM-centric | Yes (AR generative, 216 futures / 100 ms) | Trajectory selection over rollouts | 2024 |
| **XPeng** | XNet + XPlanner + XBrain (XNGP) | E2E + Occupancy WM | Partial (2K occupancy, short-horizon) | XBrain large model | 2024 |
| **Horizon Robotics** | SuperDrive (Journey 6) | VA-style E2E | No | No explicit VLM in safety path | 2024 |
| **Li Auto** | E2E + VLM (OTA 6.4) | Dual System 1/2 | No | Explicit VLM as System 2 critic | 2024 |
| **Momenta** | R6 Flywheel | RL-based E2E | No (data-flywheel-centric) | VA-style, no VLM critic | 2024 |

Three patterns recur across these stacks, mirroring academic directions: **(i)** occupancy-centric latent spaces (Tesla FSD, XPeng XNet, Horizon SuperDrive), **(ii)** dual fast/slow controllers (Li Auto), **(iii)** RL-based closed-loop data flywheels (Momenta).

---

## Explainability & Trustworthiness

Foundation models entered driving partly on the promise that a model which can *talk about* a scene is easier to trust. That promise deserves scrutiny, and explainability is a regulatory requirement in several deployment jurisdictions.

**Fluency is not faithfulness.** A rationale is generated by the same forward pass that produced the action, under an objective that rewards plausibility rather than causal accuracy. Driving-VLA chains of causation are not reliably faithful ([Mayumu et al.](https://arxiv.org/abs/2605.17268)), and instruction-conditioned models are not robust to counterfactual instructions ([ICR-Drive](https://arxiv.org/abs/2604.05378)). An unfaithful explanation is worse than none, because it manufactures unearned confidence.

| Role | What is inspectable | Catch |
|------|---------------------|-------|
| **Encoder** | Language interfaces expose readable descriptions | They need not be the policy's internal state or a faithful explanation |
| **Simulator** | Pixel-space rollouts — a human can *watch* the phantom vehicle | Latent WMs such as LAW buy speed by giving this up |
| **Reasoner** | Highest *apparent* transparency | Lowest *verified* transparency (see §V) |
| **Data Engine** | Largely invisible | Silent VLM filters bias the training set with no reviewable artifact — the least-examined risk of the four |

Three directions look substantive: **counterfactual explanation** ([DRIV-EX](https://arxiv.org/abs/2603.00696)), **architectural interpretability** (the explanation is a load-bearing intermediate), and **evidential / calibrated uncertainty**. Judged by whether an explanation changes what a safety argument can claim, the field does not yet have a method it can put in front of a regulator.

---

## Benchmarks & Datasets

### Evaluation Metric Families

| Family | Core Metrics | Critical Limitation |
|--------|--------------|---------------------|
| **Visual Fidelity** | FID, FVD, LPIPS, SSIM | Ignores physics, action alignment and downstream utility |
| **Prediction Accuracy** | ADE/FDE, L2 (pixel/latent), multi-view consistency | Almost exclusively open-loop |
| **Physical Checks** | Track persistence (proposed), kinematic violations (proposed), collision events, traffic-rule infractions | Proposed checks need explicit visibility, threshold and denominator conventions; not yet standardized |
| **Downstream Task** | Closed-loop collision, perception mAP gain, planning success | Depends on policy, dataset and scenario suite |

Each family tests one link in a chain of claims (*looks right* → *happens next* → *physically possible* → *helps driving*). The cheapest and most-reported metric tests the weakest link; the one that decides deployment is reported least.

### Evaluation Capabilities and Boundaries

| Resource | Protocol / capability | Interpretation limit |
|----------|-----------------------|----------------------|
| **nuScenes** | Recorded sensor data (1000 × 20 s, 6-cam + LiDAR + radar + HD maps) | Logged agents cannot react to a changed ego action |
| **Waymo Open** | Recorded sensor data (1150 × 20 s, ~6 h), geographic diversity | Dataset access alone is not reactive simulation |
| **CARLA** | Interactive simulator with selectable agents, routes, infractions | Outcomes depend on traffic policy and scenario configuration |
| **NAVSIM** | Non-reactive policy evaluation with planning metrics | Does not measure agent reactions to ego interventions |

Other resources: **BDD100K** (weather / lighting diversity), **nuPlan** (own 1500 h corpus from four cities — not a re-annotation of nuScenes), **Waymo Sim Agents** (separate multi-agent protocol), **KITTI / Argoverse**, **SHIFT**, **ScenarioNet / MetaDrive**, **Waymax**, **SUMO**. New 2026 benchmarks — **DrivingGen** (ICLR 2026, [paper](https://arxiv.org/abs/2601.01528)), “all-around player” evaluation ([paper](https://arxiv.org/abs/2605.10858)), and environmental-illusion robustness ([paper](https://arxiv.org/abs/2607.05783)) — have begun to close the gap, but none is yet a shared yardstick.

**A note on the CARLA monoculture.** A field that validates almost exclusively on one open simulator risks mistaking properties of that simulator for properties of driving; our benchmark proposal is therefore stated in terms of *capabilities to be measured*, not a platform.

### Call for a Standardized Physical AI Benchmark Suite (§VIII.C)

1. **Physical consistency** evaluation (object permanence, kinematic validity, collision realism, traffic-rule compliance)
2. **Action controllability** benchmark — different ego actions should yield correspondingly different futures
3. **Long-tail scenario** suite
4. **Downstream task** evaluation protocol (perception training, closed-loop planning, sim-to-real)
5. **Efficiency** benchmark — latency, memory, and compute reported together

---

## Open Challenges

We identify **six core open challenges**. Milestones are stated as evidence requirements, not maturity scores or predicted dates.

| # | Challenge | Current Status | Evidence Needed / Milestone |
|---|-----------|----------------|-----------------------------|
| **1** | **Scaling Laws for WFMs** | Visual fidelity scales, physical understanding does not; Cosmos Predict 2.5 ships 2B and 14B, but no public study relates scale to physics-violation rate | A controlled study varying model size, data diversity and mixture separately, reporting physical-error measures alongside generation fidelity |
| **2** | **Physical Grounding & Causal Reasoning** | Geometric, dynamic and causal failure classes recur in public demo reels (informal, non-systematic observation) | A reproducible kinematic-violation benchmark with explicit thresholds, denominators and confidence intervals, evaluated across domains |
| **3** | **Real-Time Edge Deployment** | NVIDIA reports 31.0 s (4B) – 109.2 s (13B) on one H100 for 32 frames at 640×1024; eight GPUs do not close the gap. Real-time is reported only at 320×512 on the smallest model with speculative decoding | Sub-50 ms world-model rollout for a 3 s horizon on Jetson AGX Orin (or an equivalent automotive SoC), with end-to-end latency and memory on named hardware |
| **4** | **Unified World Agent Architecture** | Many stacks compose separate encoder → WM → VLM critic → planner | A single-model VLA + WM with competitive CARLA LB 2.0 performance *and* explicit ≥5 s rollouts, with ablations separating shared training from capacity gains |
| **5** | **Safety Verification & Trustworthy AI** | Phantom objects, obstacle erasure, temporal hallucination; calibration must be tested under intended domain shifts | An explicitly scoped safety case with measured failure exposure, confidence bounds and calibrated uncertainty — no universal acceptable failure rate is asserted |
| **6** | **Multi-Agent Interaction & Game-Theoretic Modeling** | Models evaluated only against logged futures can miss how agents react to ego interventions | A Waymo Sim Agents-style benchmark explicitly scoring ego-conditional reactive behavior, with a published baseline |

### Future Technology Roadmap

```
Short-Term (2026–2027)              Mid-Term (2028–2030)               Long-Term (2030+)
──────────────────────              ──────────────────────             ──────────────────
• Latent-space WM real-time         • Unified world agent              • Fully self-improving
  inference on edge                   architecture                       data flywheel
• Standardized physical             • Physics-informed WFMs            • Provably safe world
  consistency benchmark               with causal reasoning              model verification
• Synthetic data reliably           • Synthetic-to-real ratio          • Generalizable world
  improves long-tail perception       no longer the binding              agent for all scenarios
                                      constraint
```

Milestones are **capabilities rather than quantitative targets**, and phase boundaries are indicative. We deliberately avoid predicting a synthetic-to-real data ratio.

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

- **Recent works** from CVPR/ICCV/ECCV/NeurIPS/ICLR 2025–2026 we may have missed
- **Industry technical reports** with publicly available material
- **Benchmark proposals** addressing the gaps identified in §VIII
- **Negative results / failure analyses** of FM × DWM systems
- **Latency and compute reports** for world-model-integrated planners

---

## Citation

If you find this manuscript or repository helpful for your research, please cite the version you used (e.g. arXiv, project PDF, or the final journal article once available):

```bibtex
@misc{bao2026fm_dwm_survey,
  title        = {Foundation Models for Driving World Models: Encoders, Simulators, Reasoners, and Data Engines},
  author       = {Bao, Naren and Carballo, Alexander and Javanmardi, Ehsan and Tsukada, Manabu and Takeda, Kazuya},
  year         = {2026},
  url          = {https://github.com/honalele/Foundation-Models-Meet-Driving-World-Models},
  note         = {Manuscript submitted to IEEE Open Journal of Intelligent Transportation Systems (OJ-ITS); not yet peer-reviewed. Prefer the official journal or arXiv BibTeX after publication.}
}
```

When the paper is on arXiv or IEEE Xplore, switch to the venue's recommended `@article` entry (with DOI).

---

## Related Surveys

- Feng et al., *A Survey of World Models for Autonomous Driving*, arXiv:2501.11260, 2025.
- Tu et al., *The Role of World Models in Shaping Autonomous Driving: A Comprehensive Survey*, arXiv:2502.10498, 2025.
- Ding et al., *Understanding World or Predicting Future? A Comprehensive Survey of World Models*, ACM CSUR, 2025.
- Zidan et al., *World Models: A Comprehensive Survey of Architectures, Methodologies, Reasoning Paradigms, and Applications*, arXiv:2606.00133, 2026.
- Gao et al., *Foundation Models in Autonomous Driving: A Survey on Scenario Generation and Scenario Analysis*, IEEE OJ-ITS, 2026.
- Zhao et al., *A Survey on the Application of Large Language Models in Scenario-Based Testing of Automated Driving Systems*, IEEE T-ITS, 2026.
- Stefanidou et al., *Foundation Models in Autonomous Driving: A Review of Current Tasks and Applications*, IEEE OJ-ITS, 2025.
- Zeng & Dong, *Latent World Models for Automated Driving: A Unified Taxonomy, Evaluation Framework, and Open Challenges*, arXiv:2603.09086, 2026 (under review, T-ITS).
- Xu et al., *A Survey on End-to-End Autonomous Driving Training from the Perspectives of Data, Strategy, and Platform*, IEEE T-ITS, 2026.
- Cui et al., *A Survey on Multimodal Large Language Models for Autonomous Driving*, WACV Workshops, 2024.
- Yang et al., *A Survey of Large Language Models for Autonomous Driving*, arXiv:2311.01043, 2023.
- Zhou et al., *Vision Language Models in Autonomous Driving: A Survey and Outlook*, IEEE TIV, 2024.

Our survey **complements** these by treating the driving world model as the object of study and the foundation model's role as the organizing variable, with coverage through August 2026.

---

## Data and Code Availability

No new experimental data were generated. The manuscript's section-citation counts are reproducible from the bibliography via `survey_stats.py` and `survey_corpus.csv`, which accompany the manuscript source. These materials do not reproduce the surveyed models' training or evaluation.

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
  <i>Last Updated: September 2026</i>
</p>
