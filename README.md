# Foundation Models Meet Driving World Models: A Comprehensive Survey

<p align="center">
  <a href="https://arxiv.org/abs/xxxx.xxxxx"><img src="https://img.shields.io/badge/arXiv-xxxx.xxxxx-b31b1b.svg" alt="arXiv"></a>
  <a href="#citation"><img src="https://img.shields.io/badge/Citation-BibTeX-blue.svg" alt="Citation"></a>
  <img src="https://img.shields.io/badge/Papers-110%2B-brightgreen.svg" alt="Papers">
  <img src="https://img.shields.io/badge/Coverage-2023--2026-orange.svg" alt="Coverage">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
</p>

<p align="center">
  <b>The first systematic survey on the intersection of Foundation Models and Driving World Models for Autonomous Driving</b>
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#taxonomy">Taxonomy</a> •
  <a href="#paper-structure">Paper Structure</a> •
  <a href="#covered-topics">Covered Topics</a> •
  <a href="#open-challenges">Open Challenges</a> •
  <a href="#citation">Citation</a>
</p>

---

## Authors

**[Naren Bao](mailto:naren@g.ecc.u-tokyo.ac.jp)<sup>1,2</sup>, Alexander Carballo<sup>3,5</sup>, Ehsan Javanmardi<sup>1</sup>, Manabu Tsukada<sup>1</sup>, Kazuya Takeda<sup>2,4,5</sup>**

<sup>1</sup> Graduate School of Information Science and Technology, The University of Tokyo, Japan  
<sup>2</sup> Graduate School of Informatics, Nagoya University, Japan  
<sup>3</sup> Graduate School of Engineering, Gifu University, Japan  
<sup>4</sup> Institutes of Innovation for Future Society, Nagoya University, Japan  
<sup>5</sup> Nagoya University Open Innovation Center, Japan

---

## Overview

Driving world models (DWMs) — computational engines that simulate, predict, and model the evolution of dynamic driving environments — have emerged as a cornerstone of next-generation autonomous driving systems. Concurrently, foundation models (FMs), including LLMs, VLMs, video foundation models, and VLAs, have demonstrated unprecedented capabilities in semantic understanding, physical reasoning, high-fidelity generation, and sequential decision-making.

**This survey provides the first systematic and up-to-date review of this rapidly growing intersection**, covering over **110 papers from 2023 to 2026**, encompassing both academic advances (GAIA-2, Epona, DriveLaW, OpenDriveVLA) and industry platforms (Cosmos, Sora, Waymo).

### Key Contributions

- **Novel Role-Based Taxonomy**: We propose a taxonomy organized around how FMs reshape every stage of the DWM pipeline — Encoder, Simulator, Reasoner, and Data Engine
- **Comprehensive Coverage**: 110+ papers systematically reviewed with detailed comparison tables across all four dimensions
- **Critical Analysis**: Genuine technical contributions versus industry hype; core gaps between general video generation models and AD-specific WFMs
- **Research Roadmap**: Structured future directions covering scaling laws, physical grounding, real-time edge deployment, and safety verification

---

## Taxonomy

We propose a novel **role-based taxonomy** organized around four core roles that foundation models play in the driving world model pipeline:

```
┌─────────────────────────────────────────────────────────────────┐
│                  FM-Empowered Driving World Models              │
├─────────────────┬─────────────────┬───────────────┬─────────────┤
│  FM as World    │  FM as World    │ FM as World   │ FM as Data  │
│  Encoder        │  Simulator      │ Reasoner      │ Engine      │
├─────────────────┼─────────────────┼───────────────┼─────────────┤
│ • VLM-driven    │ • Autoregressive│ • LLM decision│ • Synthetic │
│   scene         │   Transformer   │   making      │   data gen  │
│   understanding │ • Diffusion     │ • Imagine-    │ • VLM auto- │
│ • Pre-trained   │   models        │   then-Plan   │   annotation│
│   visual FMs    │ • Flow-based    │ • FM as reward│ • Sim-to-   │
│ • Multi-modal   │   WFMs          │   / critic    │   real      │
│   FM encoding   │ • WFM platforms │ • VLA for E2E │ • Closed-   │
│ • Language as   │   (Cosmos,      │   driving     │   loop data │
│   world state   │    GAIA-2)      │               │   flywheel  │
└─────────────────┴─────────────────┴───────────────┴─────────────┘
```

### Foundation Model Families

| FM Family | Input / Output | Representative Models | Core Role in DWM Pipeline |
|-----------|---------------|----------------------|--------------------------|
| **LLM** | Text → Text | GPT-4o, LLaMA-3.1, Qwen-2.5 | Intent generation, decision reasoning, reward design |
| **VLM** | Image/Video+Text → Text | GPT-4V, LLaVA-1.5, InternVL-2.5, Cosmos Reason 2 | Scene understanding, auto-annotation, safety verification |
| **Video WFM** | Text/Image/Video+Action → Video | Cosmos Predict 2.5, GAIA-2, Epona, Sora | World simulation, future prediction, synthetic data |
| **VLA** | Image+Text → Action | RT-2, OpenVLA, OpenDriveVLA | End-to-end perception-to-action, closed-loop control |

---

## Paper Structure

| Section | Title | Description |
|---------|-------|-------------|
| §1 | **Introduction** | Motivation, scope, and positioning relative to existing surveys |
| §2 | **Preliminaries** | Core definitions (DWM, WFM), FM taxonomy, DWM evolution timeline, unified problem formulation |
| §3 | **FM as World Encoder** | VLM-driven scene understanding, pre-trained visual FM backbones, multi-modal encoding, language-as-state |
| §4 | **FM as World Simulator** | Pixel-space generative WMs (autoregressive / diffusion / flow), purpose-built WFM platforms (Cosmos, GAIA-2), LLM-assisted scene generation, latent-space WMs |
| §5 | **FM as World Reasoner** | LLM decision making, Imagine-then-Plan paradigm, FM as reward/critic, VLA for end-to-end driving, VLA+WM fusion paradigms |
| §6 | **FM as Data Engine** | Controllable synthetic data generation, VLM auto-annotation, sim-to-real adaptation, closed-loop data flywheel |
| §7 | **Benchmarks and Evaluation** | Evaluation metrics (visual fidelity, prediction accuracy, physical consistency), existing benchmarks, call for standardized Physical AI benchmarks |
| §8 | **Open Challenges & Future Directions** | Six core challenges with actionable research roadmap |
| §9 | **Conclusion** | Summary and outlook |

---

## Covered Topics

### §3 FM as World Encoder

Foundation models provide driving world models with richer, more semantically meaningful scene representations:

- **VLM-Driven Scene Understanding** — GPT-4V on Road, DriveGPT4, DriveLM, DriveVLM, Cosmos Reason 2
- **Pre-trained Visual FM Backbones** — CLIP, SigLIP, DINOv2, InternViT integrated with BEV frameworks (BEVFormer, BEVDet, TPVFormer)
- **Multi-modal FM Encoding** — Unified latent spaces across camera, LiDAR, radar, and CAN bus data
- **Language as World State** — LMDrive, Talk2BEV

### §4 FM as World Simulator

The most active area — using foundation models as the core simulation engine:

- **Autoregressive Transformer WMs** — GAIA-1/2, ADriver-I, DriveGPT
- **Diffusion-Based WMs** — DriveDreamer, MagicDrive, Panacea, Vista
- **Flow-Based WFMs** — Cosmos Predict 2.5 (single-step generation)
- **Purpose-Built WFM Platforms** — NVIDIA Cosmos (Predict + Transfer + Reason), Wayve GAIA-2, Epona
- **LLM-Assisted Scene Generation** — DriveDreamer-2, ChatSim
- **Latent-Space World Models** — Think2Drive, MILE, OccWorld, DriveLaW

### §5 FM as World Reasoner

Foundation models enable safe, rational decision-making based on world model rollouts:

- **LLM as Decision Maker** — GPT-Driver, LanguageMPC, Agent-Driver, RAG-Driver, DriveCoT
- **Imagine-then-Plan Paradigm** — World4Drive, Think2Drive + MCTS, DriveLaW
- **FM as Reward/Critic** — DriveVLM rewards, DiLu self-reflection, Cosmos Reason as critic
- **VLA for End-to-End Driving** — OpenDriveVLA, SimLingo, EvoDriveVLA, AutoVLA
- **VLA + WM Fusion** — Three paradigms: WM as front-end predictor, WM as safety cage, shared backbone joint training

### §6 FM as Data Engine

The most impactful practical role — scalable synthetic data generation:

- **Three-Level Generation Pipeline**: Scenario-level → Sensor-level → Event-level
- **VLM Auto-Annotation & Filtering** — Replacing manual annotation with VLM-based pipelines
- **Sim-to-Real Adaptation** — Cosmos Transfer for domain gap bridging
- **Closed-Loop Data Flywheel** — Continuous self-improvement cycle: collect → train WFM → generate → annotate → train policy → deploy → collect

---

## Open Challenges

We identify **six core open challenges** for the field:

| Challenge | Current Status | Key Gap |
|-----------|---------------|---------|
| **Scaling Laws for WFMs** | Visual fidelity scales, but physical understanding does not | "Fidelity-physics gap" — no rigorous scaling law characterization |
| **Physical Grounding** | Geometric / dynamic / causal violations persist | Pixel-level losses are blind to physics |
| **Real-Time Edge Deployment** | ~4s for 2s video on A100; need 50ms at 20Hz | 200× latency gap for safety-critical control |
| **Unified World Agent** | Separate encoder → WM → VLM critic → planner | Information loss at every handoff |
| **Safety Verification** | Phantom objects, obstacle erasure, temporal hallucination | No confidence estimates or uncertainty quantification |
| **Multi-Agent Interaction** | Agents treated as passive background | "Frozen world" — no reactive, game-theoretic modeling |

### Future Technology Roadmap

- **Short-Term (2026–2027)**: Latent-space WM real-time inference on edge; standardized physical consistency benchmarks; synthetic data replaces 30% real data
- **Mid-Term (2028–2030)**: Unified world agent architecture; physics-informed WFMs with causal reasoning; synthetic data replaces 70% real data
- **Long-Term (2030+)**: Fully self-improving data flywheel; provably safe world model verification; generalizable world agent for all driving scenarios

---

## Citation

If you find this survey helpful for your research, please cite our paper:

```bibtex
@article{bao2026fm_dwm_survey,
  title     = {Foundation Models Meet Driving World Models: A Comprehensive Survey},
  author    = {Bao, Naren and Carballo, Alexander and Javanmardi, Ehsan and Tsukada, Manabu and Takeda, Kazuya},
  journal   = {arXiv preprint arXiv:xxxx.xxxxx},
  year      = {2026}
}
```

---

## Contact

For questions, suggestions, or corrections, please open an [issue](../../issues) or contact:

- **Naren Bao** — [naren@g.ecc.u-tokyo.ac.jp](mailto:naren@g.ecc.u-tokyo.ac.jp)

---

## Acknowledgments

This work was supported by the University of Tokyo and Nagoya University. We thank all authors of the surveyed papers for their contributions to the field.

---

<p align="center">
  <i>Last Updated: April 2026</i>
</p>
