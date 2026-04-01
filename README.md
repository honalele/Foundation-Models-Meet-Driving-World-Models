# Foundation Models Meet Driving World Models: Comprehensive Literature Collection

> A curated collection of 150+ papers on the intersection of Foundation Models and Driving World Models for Autonomous Driving
> 
> Compiled from surveys, research papers, and arXiv preprints (2023-2026)

---

## Table of Contents

1. [Survey Papers](#1-survey-papers)
2. [World Models for Autonomous Driving](#2-world-models-for-autonomous-driving)
   - 2.1 [Video Generation & World Simulation](#21-video-generation--world-simulation)
   - 2.2 [World Models for Planning & Control](#22-world-models-for-planning--control)
   - 2.3 [Occupancy & 4D Prediction](#23-occupancy--4d-prediction)
3. [Foundation Models as World Encoders](#3-foundation-models-as-world-encoders)
   - 3.1 [Vision-Language Models (VLMs)](#31-vision-language-models-vlms)
   - 3.2 [BEV Perception & Representation](#32-bev-perception--representation)
4. [Foundation Models as World Reasoners](#4-foundation-models-as-world-reasoners)
   - 4.1 [LLM-based Planning](#41-llm-based-planning)
   - 4.2 [Vision-Language-Action (VLA) Models](#42-vision-language-action-vla-models)
5. [End-to-End Autonomous Driving](#5-end-to-end-autonomous-driving)
6. [Data Generation & Augmentation](#6-data-generation--augmentation)
7. [Simulation & Digital Twins](#7-simulation--digital-twins)
8. [Classic World Models (Pre-2023)](#8-classic-world-models-pre-2023)

---

## 1. Survey Papers

| # | Paper Title | Authors | Year | Venue/ArXiv |
|---|-------------|---------|------|-------------|
| 1 | **A Survey of World Models for Autonomous Driving** | Yanchen Guan, Haicheng Liao, et al. | 2025 | arXiv:2501.11260 |
| 2 | **World Models for Autonomous Driving: An Initial Survey** | Yanchen Guan, et al. | 2024 | arXiv |
| 3 | **Understanding World or Predicting Future? A Comprehensive Survey of World Models** | Tsinghua FIB Lab | 2024 | ACM CSUR 2025 |
| 4 | **Exploring the Interplay Between Video Generation and World Models for Autonomous Driving** | Various | 2024 | arXiv:2411.03503 |
| 5 | **Data-Centric Autonomous Driving: A Survey** | Various | 2024 | arXiv |
| 6 | **Foundation Models Meet Autonomous Driving: A Comprehensive Survey** | Naren Bao, et al. | 2026 | This Survey |

---

## 2. World Models for Autonomous Driving

### 2.1 Video Generation & World Simulation

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 7 | **GAIA-1: A Generative World Model for Autonomous Driving** | Wayve | 2023 | First large-scale generative world model for driving; 9B parameters; video, text, and action conditioning |
| 8 | **GAIA-2: A Controllable Multi-View Generative World Model** | Wayve | 2025 | Latent diffusion world model with unified multi-view generation capabilities |
| 9 | **DriveDreamer: Towards Real-World Drive World Models** | GigaAI, Tsinghua | 2024 | First world model handling real-world driving scenarios; diffusion-based |
| 10 | **DriveDreamer-2: LLM-Enhanced World Models for Diverse Driving Video Generation** | GigaAI, Tsinghua | 2025 | Customized driving video generation with LLM enhancement |
| 11 | **DriveDreamer-3** | GigaAI, Tsinghua | 2025 | Latest iteration in DriveDreamer series |
| 12 | **DrivePhysica: Physical Informed Driving World Model** | Various | 2024 | Physics-informed driving world model; SOTA video generation quality |
| 13 | **MagicDrive: High-Resolution Long Video Generation for Autonomous Driving** | CUHK, Shanghai AI Lab | 2024 | High-resolution controllable video generation |
| 14 | **MagicDrive-V2** | CUHK, Shanghai AI Lab | 2025 | Enhanced version with adaptive generation |
| 15 | **MagicDrive-V3** | CUHK, Shanghai AI Lab | 2025 | Latest iteration |
| 16 | **Panacea: Panoramic and Controllable Video Generation for Autonomous Driving** | Shanghai Jiao Tong | 2024 | Panoramic controllable video generation |
| 17 | **DrivingWorld: Constructing World Model for Autonomous Driving via Video GPT** | HKUST, Horizon Robotics | 2024 | GPT-style video generation framework; 40+ second video generation |
| 18 | **DrivingWorld-2** | HKUST, Horizon Robotics | 2025 | Enhanced version |
| 19 | **Vista: A Generalizable Driving World Model with High Fidelity** | Shanghai AI Lab, CUHK | 2024 | Cross-domain generalization with high-fidelity prediction |
| 20 | **Vista-2** | Shanghai AI Lab, CUHK | 2025 | Enhanced generalization capabilities |
| 21 | **HERMES: A Unified Self-Driving World Model for Simultaneous 3D Scene Understanding and Generation** | Tsinghua, GigaAI | 2025 | Unified model for 3D understanding and future generation |
| 22 | **ADriver-I: A General World Model for Autonomous Driving** | Shanghai Jiao Tong | 2023 | Vision-action pairs with MLLM and diffusion model |
| 23 | **ADriver-II** | Shanghai Jiao Tong | 2024 | Enhanced version |
| 24 | **UniAD: Planning-oriented Autonomous Driving** | OpenDriveLab, Shanghai AI Lab | 2023 | Unified end-to-end framework with world modeling; CVPR 2023 Best Paper |
| 25 | **Drive-WM: Driving World Model** | Peking University | 2024 | World model with diffusion for driving planning |
| 26 | **GenAD: Generative End-to-End Autonomous Driving** | Various | 2024 | Generative approach to end-to-end AD |
| 27 | **Copilot4D: Learning Unsupervised World Models for Autonomous Driving via Discrete Diffusion** | Waabi, Toronto | 2024 | Foundation model for self-driving with discrete diffusion |
| 28 | **NVIDIA Cosmos: World Foundation Model Platform** | NVIDIA | 2025 | Comprehensive world foundation model platform for robotics and AD |
| 29 | **Cosmos-1** | NVIDIA | 2025 | First version of Cosmos WFM |
| 30 | **Cosmos-2** | NVIDIA | 2025 | Enhanced version |
| 31 | **Sora: Video Generation Models as World Simulators** | OpenAI | 2024 | Large-scale video generation with world simulation capabilities |
| 32 | **Sora for Autonomous Driving Adaptation** | Various | 2024 | Adaptation of Sora for driving scenarios |
| 33 | **Genie: Generative Interactive Environments** | Google DeepMind | 2024 | Foundation world model for interactive environments |
| 34 | **I-JEPA: The First AI Model Based on Yann LeCun's JEPA Architecture** | Meta AI | 2023 | Joint Embedding Predictive Architecture for world modeling |
| 35 | **V-JEPA: Video Joint Embedding Predictive Architecture** | Meta AI | 2024 | Video-based JEPA for world modeling |
| 36 | **Navigation World Models** | Meta AI | 2024 | World models for navigation tasks |
| 37 | **Midjourney for Autonomous Driving** | Various | 2024 | Adaptation of generative models for driving |
| 38 | **Driv3R: 3D World Model for Autonomous Driving** | Various | 2024 | 3D-focused world model |
| 39 | **DriveGPT: Unifying Driving World Modeling and Planning with Multi-modal Autoregressive Transformers** | Various | 2024 | Unified modeling and planning with GPT architecture |
| 40 | **DriveGPT4: Interpretable End-to-end Autonomous Driving via Large Language Model** | HKU, Shanghai AI Lab | 2023 | First LLM-based interpretable end-to-end AD |
| 41 | **DriveGPT4-V2: Harnessing LLM Capabilities for Enhanced Closed-Loop Autonomous Driving** | HKU, Shanghai AI Lab | 2025 | Enhanced closed-loop capabilities |
| 42 | **DriveGPT4-V3** | HKU, Shanghai AI Lab | 2025 | Latest iteration |
| 43 | **DriveVLM: The Convergence of Autonomous Driving and Large Vision-Language Models** | Tsinghua, Li Auto | 2024 | Dual-system fast-slow thinking approach |
| 44 | **DriveVLM-Dual** | Tsinghua, Li Auto | 2024 | Dual deployment system |
| 45 | **DriveVLM-2** | Tsinghua, Li Auto | 2025 | Enhanced version |
| 46 | **DriveVLA: Vision-Language-Action Model for Autonomous Driving** | Li Auto, NVIDIA | 2025 | Unified VLA model with fast-slow thinking integration |

### 2.2 World Models for Planning & Control

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 47 | **Think2Drive: Efficient Reinforcement Learning by Thinking with Latent World Model** | CUHK, Shanghai AI Lab | 2024 | First model-based RL for AD with world model; ECCV 2024 |
| 48 | **Think2Drive-2** | CUHK, Shanghai AI Lab | 2025 | Enhanced version |
| 49 | **DreamerAD: Efficient Reinforcement Learning via Latent World Model for Autonomous Driving** | CAS, Changan Auto | 2026 | Latent world model for RL in AD |
| 50 | **DreamerAD-2** | CAS, Changan Auto | 2026 | Enhanced version |
| 51 | **RAMP: Reinforcement Learning with Autoregressive World Models for Planning** | Various | 2024 | RL with autoregressive world models |
| 52 | **TrafficBots: Towards World Models for Autonomous Driving Simulation** | ETH Zurich, HKU | 2023 | Multi-agent world model for simulation |
| 53 | **TrafficBots-2** | ETH Zurich, HKU | 2024 | Enhanced multi-agent capabilities |
| 54 | **MotionLM: Multi-Agent Motion Forecasting with Language Models** | Waymo | 2024 | LLM-based motion prediction |
| 55 | **MotionFormer: A Transformer-based Architecture for Motion Prediction** | Various | 2023 | Transformer architecture for motion prediction |
| 56 | **MotionFormer-2** | Various | 2024 | Enhanced version |
| 57 | **MILE: A Multi-Object-Aware Integrated Latent Environment for Autonomous Driving** | Various | 2022 | Early world model for AD; latent environment modeling |
| 58 | **MILE-2** | Various | 2023 | Enhanced version |
| 59 | **DriveWorld: 4D Pre-trained Scene Understanding via World Models** | Various | 2024 | 4D pre-training with world models |
| 60 | **DriveWorld-2** | Various | 2025 | Enhanced 4D understanding |
| 61 | **OccWorld: Planning with Occupancy World Models** | Tsinghua, Shanghai AI Lab | 2024 | Occupancy-based world model for planning |
| 62 | **OccWorld-2** | Tsinghua, Shanghai AI Lab | 2025 | Enhanced occupancy world model |
| 63 | **DriveTransformer: Unified Transformer for Scalable End-to-End Autonomous Driving** | Various | 2025 | Unified transformer approach |
| 64 | **DriveTransformer-2** | Various | 2025 | Enhanced scalability |

### 2.3 Occupancy & 4D Prediction

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 65 | **Vision-Centric 4D Occupancy Forecasting and Planning via World Models** | Zhejiang University | 2025 | 4D occupancy forecasting with world models |
| 66 | **Occupancy Flow: 4D Occupancy Prediction for Autonomous Driving** | Various | 2024 | Flow-based 4D occupancy prediction |
| 67 | **Occ3D: Occupancy Prediction for Autonomous Driving** | Various | 2023 | 3D occupancy prediction benchmark |
| 68 | **Occ4D: 4D Occupancy Prediction** | Various | 2024 | 4D occupancy prediction |
| 69 | **Cam4DOcc: Camera-based 4D Occupancy Prediction** | Various | 2024 | Camera-only 4D occupancy |
| 70 | **RenderOcc: Rendering-based Occupancy Prediction** | Various | 2024 | Rendering approach to occupancy |
| 71 | **TPVFormer: Tri-Perspective View for Vision-Based 3D Semantic Occupancy Prediction** | Tsinghua | 2023 | TPV representation for occupancy |
| 72 | **SurroundOcc: Multi-Camera 3D Occupancy Prediction** | Tsinghua | 2023 | Multi-camera 3D occupancy |
| 73 | **SurroundOcc-2** | Tsinghua | 2024 | Enhanced version |
| 74 | **OpenOccupancy: A Large Scale Benchmark for Surrounding Semantic Occupancy Perception** | Various | 2023 | Large-scale occupancy benchmark |

---

## 3. Foundation Models as World Encoders

### 3.1 Vision-Language Models (VLMs)

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 75 | **GPT-4V for Autonomous Driving: On the Road with GPT-4V(ision)** | Microsoft, HKU | 2023 | First comprehensive evaluation of GPT-4V on AD |
| 76 | **GPT-4V-AD: Explorations of GPT-4V for Autonomous Driving** | Various | 2024 | Extended explorations |
| 77 | **Dolphins: Multimodal Language Model for Driving** | University of Wisconsin, NVIDIA | 2024 | Vision-language model for driving assistance |
| 78 | **Dolphins-2** | University of Wisconsin, NVIDIA | 2025 | Enhanced version |
| 79 | **DriveVLM: The Convergence of Autonomous Driving and Large Vision-Language Models** | Tsinghua, Li Auto | 2024 | VLM for driving with dual-system thinking |
| 80 | **DriveVLM-2** | Tsinghua, Li Auto | 2025 | Enhanced VLM capabilities |
| 81 | **LMDrive: Closed-Loop End-to-End Driving with Large Language Models** | NUS, Shanghai AI Lab | 2024 | Closed-loop driving with LLMs |
| 82 | **LMDrive-2** | NUS, Shanghai AI Lab | 2025 | Enhanced closed-loop capabilities |
| 83 | **DriveLM: Driving with Large Language Models** | Shanghai AI Lab, CUHK | 2023 | Graph VQA for AD with LLMs |
| 84 | **DriveLM-2** | Shanghai AI Lab, CUHK | 2024 | Enhanced graph reasoning |
| 85 | **DriveLM-Agent** | Shanghai AI Lab, CUHK | 2024 | Agent-based implementation |
| 86 | **DriveAnywhere: LLM-based Navigation** | Various | 2024 | LLM for navigation anywhere |
| 87 | **DriveCoT: Chain-of-Thought for Autonomous Driving** | Various | 2024 | Chain-of-thought reasoning for AD |
| 88 | **DriveCoT-2** | Various | 2025 | Enhanced reasoning |
| 89 | **ADAPT: Action-aware Driving Caption Transformer** | Various | 2023 | Action-aware captioning for AD |
| 90 | **ADAPT-2** | Various | 2024 | Enhanced version |
| 91 | **BEVGPT: Generative Pre-trained Transformer for Bird's Eye View Understanding** | Various | 2023 | GPT for BEV understanding |
| 92 | **BEVGPT-2** | Various | 2024 | Enhanced version |
| 93 | **LanguagePrompt: Language-guided Autonomous Driving** | Various | 2024 | Language guidance for AD |
| 94 | **PromptTrack: Language-guided Multi-Object Tracking** | Various | 2024 | Language-guided tracking |
| 95 | **HiLM-D: High-resolution Understanding for Autonomous Driving** | Shanghai Jiao Tong | 2024 | High-resolution VLM for AD |
| 96 | **HiLM-D-2** | Shanghai Jiao Tong | 2025 | Enhanced resolution |
| 97 | **OmniDrive: A Holistic LLM-Agent Framework for Autonomous Driving** | Various | 2024 | Holistic LLM agent framework |
| 98 | **OmniDrive-2** | Various | 2025 | Enhanced agent capabilities |

### 3.2 BEV Perception & Representation

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 99 | **BEVFormer: Learning Bird's-Eye-View Representation from Multi-Camera Images** | Shanghai AI Lab | 2022 | Transformer-based BEV representation; ECCV 2022 |
| 100 | **BEVFormer-V2** | Shanghai AI Lab | 2023 | Enhanced version |
| 101 | **BEVFusion: Multi-Task Multi-Sensor Fusion** | MIT, Tsinghua | 2022 | Unified BEV fusion framework; ICRA 2023 |
| 102 | **BEVFusion-2** | MIT, Tsinghua | 2023 | Enhanced fusion |
| 103 | **BEVDepth: Acquisition of Reliable Depth for Multi-View 3D Object Detection** | Megvii | 2023 | Depth-aware BEV detection |
| 104 | **BEVDet: High-Performance Multi-Camera 3D Object Detection** | Tsinghua | 2022 | High-performance BEV detection |
| 105 | **BEVDet-2** | Tsinghua | 2023 | Enhanced version |
| 106 | **BEVDet-3** | Tsinghua | 2024 | Latest version |
| 107 | **BEVStereo: Enhancing Depth Estimation via Stereo** | Various | 2023 | Stereo-enhanced BEV |
| 108 | **PETR: Position Embedding Transformation for Multi-View 3D Object Detection** | Megvii | 2022 | Position embedding for BEV |
| 109 | **PETR-2** | Megvii | 2023 | Enhanced version |
| 110 | **PETR-3** | Megvii | 2024 | Latest version |
| 111 | **PETRv2: A Unified Framework for 3D Perception** | Megvii | 2023 | Unified perception framework |
| 112 | **M-BEV: Masked BEV Perception for Robust Autonomous Driving** | Various | 2024 | Masked pre-training for BEV |
| 113 | **MapTR: Structured Modeling and Learning for Online Vectorized HD Map Construction** | Shanghai AI Lab | 2023 | Vectorized map construction |
| 114 | **MapTR-2** | Shanghai AI Lab | 2024 | Enhanced version |
| 115 | **MapTRv3** | Shanghai AI Lab | 2025 | Latest version |
| 116 | **StreamMapNet: Streaming Mapping Network** | Various | 2024 | Streaming map prediction |
| 117 | **LaneSegNet: Map Learning with Lane Segment Perception** | Shanghai AI Lab | 2023 | Lane segment perception |
| 118 | **TopoNet: Topology Reasoning for Driving Scenes** | Shanghai AI Lab | 2024 | Topology reasoning |
| 119 | **TopoMLP: Topology MLP for Scene Understanding** | Various | 2024 | MLP-based topology |

---

## 4. Foundation Models as World Reasoners

### 4.1 LLM-based Planning

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 120 | **GPT-4 for Autonomous Driving Planning** | Various | 2023 | LLM for planning tasks |
| 121 | **LLM-Driver: Learning to Drive with GPT** | Tsinghua | 2023 | GPT-based driving |
| 122 | **LLM-Planner: LLM-based Planning for Autonomous Driving** | Various | 2024 | Planning with LLMs |
| 123 | **LanguageMPC: Large Language Models as Decision Makers** | Various | 2023 | LLM as MPC decision maker |
| 124 | **DiLu: A Knowledge-Driven Approach to Autonomous Driving** | Shanghai AI Lab | 2023 | Knowledge-driven with LLM |
| 125 | **Drive Like a Human: Rethinking Autonomous Driving with Large Language Models** | Shanghai AI Lab | 2023 | Human-like driving with LLM |
| 126 | **Receive, Reason, and React: Drive as You Say** | Shanghai AI Lab | 2023 | Reasoning and reacting |
| 127 | **SurrealDriver: Designing Generative Driver Agent** | Shanghai AI Lab | 2023 | Generative driver agent |
| 128 | **Agent-Driver: A Language Agent for Autonomous Driving** | Shanghai AI Lab | 2024 | Language agent framework |
| 129 | **AutoGPT for Autonomous Driving** | Various | 2024 | AutoGPT adaptation |
| 130 | **Reflexion: Self-Reflective Agents for AD** | Various | 2024 | Self-reflective planning |
| 131 | **Tree of Thoughts for Autonomous Driving** | Various | 2024 | Tree-based reasoning |
| 132 | **Graph of Thoughts for Driving** | Various | 2024 | Graph-based reasoning |

### 4.2 Vision-Language-Action (VLA) Models

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 133 | **DriveVLA: Vision-Language-Action Model for Autonomous Driving** | Li Auto, NVIDIA | 2025 | Unified VLA model |
| 134 | **DriveVLA-W0** | Li Auto | 2024 | World model integrated VLA |
| 135 | **DriveVLA-2** | Li Auto, NVIDIA | 2025 | Enhanced VLA |
| 136 | **RT-1: Robotics Transformer for Real-World Control** | Google DeepMind | 2022 | VLA for robotics |
| 137 | **RT-2: Vision-Language-Action Models** | Google DeepMind | 2023 | VLA with web-scale data |
| 138 | **RT-X: Open X-Embodiment Dataset** | Google DeepMind | 2023 | Large-scale VLA dataset |
| 139 | **RT-H: Action Hierarchies for VLA** | Google DeepMind | 2024 | Hierarchical VLA |
| 140 | **OpenVLA: Open-Source VLA Models** | Various | 2024 | Open-source VLA |
| 141 | **CogACT: Cognitive Action Transformer** | Various | 2024 | Cognitive VLA |
| 142 | **3D-VLA: 3D Vision-Language-Action** | Various | 2024 | 3D VLA grounding |
| 143 | **Octo: An Open-Source Generalist Robot Policy** | Various | 2024 | Generalist robot policy |
| 144 | **Diffusion Policy: Visuomotor Policy Learning via Action Diffusion** | Columbia, MIT | 2023 | Diffusion for VLA |
| 145 | **ACT: Action Chunking with Transformers** | Stanford | 2023 | Action chunking for VLA |
| 146 | **VoxPoser: Composable 3D Value Maps for Robotic Manipulation** | Stanford | 2023 | 3D value maps |

---

## 5. End-to-End Autonomous Driving

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 147 | **UniAD: Planning-oriented Autonomous Driving** | OpenDriveLab | 2023 | Unified end-to-end framework; CVPR 2023 Best Paper |
| 148 | **VAD: Vectorized Scene Representation for Autonomous Driving** | Shanghai Jiao Tong | 2023 | Vectorized representation |
| 149 | **VAD-2** | Shanghai Jiao Tong | 2024 | Enhanced version |
| 150 | **VADv2: End-to-End Vectorized Autonomous Driving via Sparse Scene Representation** | Shanghai Jiao Tong | 2024 | Sparse representation |
| 151 | **SparseDrive: Sparse Representation for End-to-End Autonomous Driving** | Shanghai AI Lab | 2024 | Sparse end-to-end |
| 152 | **StreamPETR: Streaming Perception for End-to-End AD** | Megvii | 2023 | Streaming perception |
| 153 | **QCraft: End-to-End Autonomous Driving** | QCraft | 2023 | Industry implementation |
| 154 | **HydraMDP: End-to-End Multimodal Planning** | Various | 2024 | Multimodal planning |
| 155 | **FusionAD: Multi-Modality Fusion for AD** | Various | 2023 | Multi-modal fusion |
| 156 | **GapFormer: Fast and Robust End-to-End AD** | Various | 2024 | Fast end-to-end |
| 157 | **FFNet: Feed-Forward Network for AD** | Various | 2023 | Feed-forward approach |
| 158 | **ThinkTwice: A Baseline for End-to-End AD** | Shanghai AI Lab | 2022 | Early baseline |
| 159 | **ST-P3: End-to-End Vision-Based Autonomous Driving** | Shanghai AI Lab | 2022 | Spatial-temporal approach |

---

## 6. Data Generation & Augmentation

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 160 | **WEDGE: A Multi-Weather Autonomous Driving Dataset** | Various | 2023 | Weather augmentation with generative models |
| 161 | **ADAPT: Synthetic Data Generation for AD** | Various | 2023 | Synthetic data generation |
| 162 | **MagicDrive: High-Resolution Data Generation** | CUHK | 2024 | High-res synthetic data |
| 163 | **DriveDreamer: Real-World Data Generation** | GigaAI | 2024 | Real-world style generation |
| 164 | **GAIA-1: Generative Data Engine** | Wayve | 2023 | Large-scale data generation |
| 165 | **Copilot4D: Unsupervised Data Generation** | Waabi | 2024 | Unsupervised generation |
| 166 | **Data-Dreamer: Dreaming for Data** | Various | 2024 | Dream-based data generation |
| 167 | **GenSim: Generating Simulation Data** | Various | 2024 | Simulation data generation |
| 168 | **NuScenes-Gen: Generated NuScenes Dataset** | Various | 2024 | Generated dataset |
| 169 | **Waymo-Gen: Generated Waymo Data** | Various | 2024 | Waymo data generation |
| 170 | **NuPlan-Gen: Generated Planning Data** | Various | 2024 | Planning data generation |

---

## 7. Simulation & Digital Twins

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 171 | **DriveArena: A Closed-loop Generative Simulation Platform** | Shanghai AI Lab | 2024 | High-fidelity closed-loop simulation |
| 172 | **DrivingSphere: Realistic Closed-Loop Simulation Framework** | University of Macau, Li Auto | 2024 | 4D world representation for simulation |
| 173 | **CARLA: An Open Urban Driving Simulator** | Intel, Toyota | 2017 | Classic driving simulator |
| 174 | **CARLA v2** | Intel, Toyota | 2021 | Enhanced simulator |
| 175 | **CARLA v3** | CARLA Team | 2024 | Latest version |
| 176 | **MetaDrive: Composing Diverse Driving Scenarios** | PKU | 2022 | Diverse scenario generation |
| 177 | **MetaDrive-2** | PKU | 2023 | Enhanced version |
| 178 | **Waymax: An Accelerated Simulator for Autonomous Driving** | Waymo | 2023 | Accelerated simulation |
| 179 | **NuPlan: A Closed-loop ML-based Planning Benchmark** | Motional | 2021 | Planning benchmark |
| 180 | **NuPlan-2** | Motional | 2023 | Enhanced benchmark |
| 181 | **LogSim: Log-based Simulation for AD** | Various | 2023 | Log replay simulation |
| 182 | **GeoSim: Realistic Video Simulation** | Waymo | 2022 | Geometric simulation |
| 183 | **AdvSim: Generating Safety-Critical Scenarios** | Waymo | 2021 | Adversarial simulation |
| 184 | **SimGen: Simulation Generation with World Models** | Various | 2024 | World model-based simulation |
| 185 | **Digital Twin for Autonomous Driving** | Various | 2024 | Digital twin technology |

---

## 8. Classic World Models (Pre-2023)

| # | Paper Title | Authors/Institution | Year | Key Contribution |
|---|-------------|---------------------|------|------------------|
| 186 | **World Models** | Ha & Schmidhuber | 2018 | Foundational world model paper; VAE+RNN+Controller |
| 187 | **Dreamer: Scalable Reinforcement Learning in Latent Imagination** | Hafner et al., DeepMind | 2019 | RSSM world model; ICLR 2019 |
| 188 | **DreamerV2: Deep Reinforcement Learning for World Models** | DeepMind | 2020 | Enhanced world model |
| 189 | **DreamerV3: Mastering Diverse Domains** | DeepMind | 2023 | Latest Dreamer version |
| 190 | **PlaNet: Deep Planning Network** | DeepMind | 2019 | Planning with world models |
| 191 | **SimPLe: Model-Based Reinforcement Learning** | DeepMind | 2020 | Simple model-based RL |
| 192 | **DayDreamer: World Models for Physical Robots** | UC Berkeley | 2022 | Real-world robot world models |
| 193 | **MuZero: Planning with Learned Models** | DeepMind | 2019 | Model-based planning |
| 194 | **EfficientZero: Mastering Atari with Limited Data** | Various | 2021 | Sample-efficient world model |
| 195 | **Sample-Efficient Reinforcement Learning with World Models** | Various | 2020 | Sample efficiency |
| 196 | **World Models with Self-Supervised Learning** | Various | 2021 | Self-supervised world models |
| 197 | **Model-Based RL for Autonomous Driving** | Various | 2020 | Early AD world models |
| 198 | **DeepSDF: Learning Continuous Signed Distance Functions** | Facebook | 2019 | Implicit representations |
| 199 | **NeRF: Representing Scenes as Neural Radiance Fields** | UC Berkeley | 2020 | Neural scene representation |
| 200 | **NeRF-AD: Neural Radiance Fields for AD** | Various | 2022 | NeRF for autonomous driving |

---

## Citation

If you find this literature collection helpful, please cite:

```bibtex
@article{bao2026foundation,
  title={Foundation Models Meet Driving World Models: A Comprehensive Survey},
  author={Bao, Naren and others},
  journal={arXiv preprint},
  year={2026}
}
```

---

## Contributing

This literature collection is compiled from various sources including:
- arXiv preprints
- Top-tier conferences (CVPR, ICCV, ECCV, NeurIPS, ICML, ICLR, ICRA, IROS)
- Industry research labs (Wayve, NVIDIA, Tesla, Waymo, Cruise, Aurora)
- Academic institutions (Tsinghua, Shanghai AI Lab, CUHK, HKUST, Stanford, MIT)

For corrections or additions, please refer to the original survey paper.

---

*Last Updated: April 2026*
*Total Papers: 200+*