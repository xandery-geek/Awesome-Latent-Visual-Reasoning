# 🧠 Awesome Latent Visual Reasoning

<div align="center">

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Stars](https://img.shields.io/github/stars/xandery-geek/Awesome-Latent-Visual-Reasoning?style=social)](https://github.com/xandery-geek/Awesome-Latent-Visual-Reasoning) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

A curated collection of papers on **Latent Visual Reasoning** — enabling Multimodal Large Language Models (MLLMs) to reason in continuous latent/visual space rather than discrete text token space.

**Last updated:** October 2026 | **Papers:** 75

</div>

---

## 📖 Background

Traditional MLLMs rely on text-space Chain-of-Thought (CoT) for visual reasoning, which suffers from:
- **Modality bottleneck:** Compressing continuous visual information into discrete text tokens loses fine-grained spatial and geometric details
- **External tool dependency:** Cropping, annotation, and drawing tools limit flexibility
- **Inefficiency:** Text CoT generates redundant tokens with high inference latency

This repository collects works that explore **reasoning in latent/visual space** — a paradigm where models perform multi-step reasoning using continuous visual embeddings or latent tokens instead of (or interleaved with) explicit text.

---

## 📂 Taxonomy

### 🔹 1. Core Latent Visual Reasoning for MLLMs

Papers that enable MLLMs to use hidden visual states or internalized visual operations during reasoning trajectories without decoding into explicit images.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2025-01 | [Efficient Reasoning with Hidden Thinking](https://arxiv.org/abs/2501.19201) | Heima | ICML 2026 | Encode each CoT step into a single thinking token; token count reduced to 6% |
| 2025-09 | [Multimodal Chain of Continuous Thought](https://arxiv.org/abs/2508.12587) | MCOUT | NeurIPS 2025 Workshop | Iterative continuous latent thought with multimodal attention for VLMs |
| 2025-10 | [Latent Visual Reasoning](https://arxiv.org/abs/2509.24251) | LVR | ICLR 2026 | Auto-regressive visual token reconstruction interleaved with text generation |
| 2025-10 | [Reasoning in the Dark: Interleaved Vision-Text Reasoning in Latent Space](https://arxiv.org/abs/2510.12603) | IVT-LR | — | Unified latent text + latent vision tokens per reasoning step |
| 2025-10 | [Latent Chain-of-Thought for Visual Reasoning](https://arxiv.org/abs/2510.23925) | LaCoT | NeurIPS 2025 | Bayesian formulation via amortized variational inference and GFlowNet |
| 2025-11 | [Chain-of-Visual-Thought](https://arxiv.org/abs/2511.19418) | CoVT | — | ~20 continuous visual tokens distilled from segmentation, depth, edge experts |
| 2025-11 | [Monet: Reasoning in Latent Visual Space Beyond Images and Language](https://arxiv.org/abs/2511.21395) | Monet | CVPR 2026 | 3-stage distillation + VLPO for latent visual reasoning |
| 2025-12 | [Sketch-in-Latents](https://arxiv.org/abs/2512.16584) | SkiLa | — | Multi-step interleaved text + visual sketch tokens |
| 2025-12 | [Latent Implicit Visual Reasoning](https://arxiv.org/abs/2512.21218) | LIVR | — | Task-agnostic: no explicit supervision via visual bottlenecking |
| 2026-01 | [LaViT: Aligning Latent Visual Thoughts for Multi-modal Reasoning](https://arxiv.org/abs/2601.10129) | LaViT | — | Reconstruct teacher visual semantics and attention trajectories before text decoding |
| 2026-02 | [Vision-aligned Latent Reasoning](https://arxiv.org/abs/2602.04476) | VaLR | ICML 2026 | Dynamic vision-aligned latents per CoT step with REPA |
| 2026-02 | [Multimodal Latent Reasoning via Hierarchical Visual Cues Injection](https://arxiv.org/abs/2602.05359) | HIVE | — | Loop Transformer with coarse-to-fine hierarchical visual injection |
| 2026-02 | [SwimBird: Switchable Reasoning Mode](https://arxiv.org/abs/2602.06040) | SwimBird | — | Adaptive mode switching: text / visual / interleaved |
| 2026-03 | [LanteRn: Latent Visual Structured Reasoning](https://arxiv.org/abs/2603.25629) | LanteRn | — | Interleave continuous visual thoughts and text; align latents with SFT and RL |
| 2026-04 | [LatentUM: Unleashing the Potential of Interleaved Cross-Modal Reasoning via a Latent-Space Unified Model](https://arxiv.org/abs/2604.02097) | LatentUM | NeurIPS 2026 | Shared semantic latents connect visual understanding, generation, and planning without pixel decoding |
| 2026-04 | [Visual Enhanced Depth Scaling for Multimodal Latent Reasoning](https://arxiv.org/abs/2604.10500) | — | NeurIPS 2026 | Visual replay strengthens grounding; routed depth refines difficult latent tokens |
| 2026-04 | [Xiaomi OneVL: One-Step Latent Reasoning and Planning with Vision-Language Explanation](https://arxiv.org/abs/2604.18486) | OneVL | NeurIPS 2026 | One-step latent reasoning with dual language/world-model supervision for VLA |
| 2026-04 | [HyLaR: Hybrid Latent Reasoning with Decoupled Policy Optimization](https://arxiv.org/abs/2604.20328) | HyLaR | ECCV 2026 | Hybrid text + visual latent reasoning optimized with DePO |
| 2026-05 | [Visual Latents Know More Than They Say: Unsilencing Latent Reasoning in MLLMs](https://arxiv.org/abs/2605.02735) | Unsilencing | NeurIPS 2026 | Inference-time latent optimization with contrastive alignment and confidence reward |
| 2026-05 | [Retrieve, Integrate, and Synthesize: Spatial-Semantic Grounded Latent Visual Reasoning](https://arxiv.org/abs/2605.07106) | RIS | — | Ground latent steps in boxes and region descriptions through an attention bottleneck |
| 2026-05 | [CoLVR: Enhancing Exploratory Latent Visual Reasoning via Contrastive Optimization](https://arxiv.org/abs/2605.08802) | CoLVR | NeurIPS 2026 | Angle-perturbed latent contrastive learning plus trajectory contrastive RL encourage exploratory reasoning |
| 2026-05 | [Self-Consistent Latent Reasoning: Long Latent Sequence Reasoning for Vision-Language Model](https://arxiv.org/abs/2605.12163) | SCOLAR | — | Single-shot visual latents from full-sequence hidden states counter information-gain collapse |
| 2026-05 | [ATLAS: Agentic or Latent Visual Reasoning? One Word is Enough for Both](https://arxiv.org/abs/2605.15198) | ATLAS | NeurIPS 2026 | A discrete functional token internalizes visual operations; latent-anchored GRPO stabilizes training |
| 2026-05 | [Semantic-Enriched Latent Visual Reasoning](https://arxiv.org/abs/2605.19342) | SLVR | ICML 2026 | Attribute-supervised region latents aligned via multi-query GRPO |
| 2026-05 | [LatentOmni: Rethinking Omni-Modal Understanding via Unified Audio-Visual Latent Reasoning](https://arxiv.org/abs/2605.22012) | LatentOmni | NeurIPS 2026 | Feature-aligned audio-visual latents with synchronized temporal positions |
| 2026-05 | [DeepLatent: Think with Images via Parallel Latent Visual Reasoning](https://arxiv.org/abs/2606.00562) | DeepLatent | — | Parallel 2D visual latents anchored to source image features with continuous-space RL |
| 2026-08 | [LUT: Latent Utility Training for Visual Reasoning](https://arxiv.org/abs/2608.00743) | LUT | — | VQA-only training selects useful latent trajectories and rewards answer-relevant steps |
| 2026-08 | [Scaffolding Minds: Optimizing Latent Visual Target Representations for Multimodal Reasoning](https://arxiv.org/abs/2608.19669) | Scaffolding Minds | — | Learned scaffolding encoder and stochastic latent policy improve visual reasoning |
| 2026-10 | [Latent Reasoning in Continuous Space for Unified Multimodal Models](https://rootyjeon.github.io/latent-reasoning-umm/assets/larc.pdf) | LARC | NeurIPS 2026 | Interleave text and continuous hidden-state steps; information-gain RL improves visual generation and reasoning |

For LARC, the date is the catalogue verification month; its [project page](https://rootyjeon.github.io/latent-reasoning-umm/) has no public arXiv submission date yet.

### 🔹 2. Rendered CoT → Visual Latent Reasoning

A growing paradigm: render text CoT as images, then use visual features as supervision for latent reasoning. Bridges text-space and visual-space reasoning.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2026-01 | [Render-of-Thought](https://arxiv.org/abs/2601.14750) | RoT | ACL 2026 | Render textual CoT as images for visual latent reasoning |
| 2026-01 | [ImgCoT: Compressing Long CoT into Compact Visual Tokens](https://arxiv.org/abs/2601.22730) | ImgCoT | ICML 2026 | Visual CoT compression via TiTok; 8 tokens replace full CoT |
| 2026-01 | [ReGuLaR: Variational Latent Reasoning](https://arxiv.org/abs/2601.23184) | ReGuLaR | — | VAE framework for latent reasoning with rendered CoT as prior |
| 2026-02 | [OneLatent: Single-Token Compression](https://arxiv.org/abs/2602.13738) | OneLatent | — | Extreme compression to 1 token with DeepSeek-OCR supervision |
| 2026-05 | [UniVLR: Unifying Text and Vision in Visual Latent Reasoning for Multimodal LLMs](https://arxiv.org/abs/2605.11856) | UniVLR | NeurIPS 2026 | Render text traces with auxiliary images, then compress both into visual latents |
| 2026-06 | [Why Struggle with Continuous Latents? Interpretable Discrete Latent Reasoning via Rendered Compression](https://arxiv.org/abs/2606.29712) | DLR | NeurIPS 2026 | Render text CoT as images and cluster visual features into interpretable discrete latent tokens |

### 🔹 3. Imagination & Mental Imagery

Models generate internal visual representations (mental imagery) to aid reasoning, inspired by human cognition.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2025-06 | [Machine Mental Imagery](https://arxiv.org/abs/2506.17218) | Mirage | — | Interleave latent visual tokens mimicking human mental imagery |
| 2025-10 | [Latent Sketchpad](https://arxiv.org/abs/2510.24514) | Sketchpad | — | Internal visual sketchpad with Vision Head and Sketch Decoder |

### 🔹 4. Domain-Specific Latent Reasoning

Papers applying latent reasoning to specific domains.

| Date | Paper | Abbreviation | Venue | Domain | Key Idea |
|------|-------|:---:|:---:|:---:|----------|
| 2025-06 | [MINT-CoT: Mathematical Interleaved Tokens](https://arxiv.org/abs/2506.05331) | MINT-CoT | NeurIPS 2025 | Math | Interleave fine-grained visual tokens for mathematical reasoning |
| 2026-01 | [Fast-ThinkAct: Efficient Vision-Language-Action Reasoning via Verbalizable Latent Planning](https://arxiv.org/abs/2601.09708) | Fast-ThinkAct | CVPR 2026 | Robotics / VLA | Compress action plans into verbalizable latents for low-latency control |
| 2026-02 | [Latent Reasoning VLA: Latent Thinking and Prediction for Vision-Language-Action Models](https://arxiv.org/abs/2602.01166) | LaRA-VLA | ICML 2026 | Robotics / VLA | Internalize multimodal CoT into continuous latents for embodied action |
| 2026-02 | [Towards Explainable Industrial Anomaly Detection via Knowledge-Guided Latent Reasoning](https://arxiv.org/abs/2602.09850) | Reason-IAD | NeurIPS 2026 | Industrial Anomaly Detection | Entropy-guided latent tokens and selective visual patch injection locate defects |
| 2026-03 | [LaST-VLA: Thinking in Latent Spatio-Temporal Space for Vision-Language-Action in Autonomous Driving](https://arxiv.org/abs/2603.01928) | LaST-VLA | NeurIPS 2026 | Autonomous Driving | Align latent thoughts with 3D geometry and world-model dynamics |
| 2026-03 | [LatentGeo: Learnable Auxiliary Constructions](https://arxiv.org/abs/2603.12166) | LatentGeo | — | Geometry | Latent auxiliary line construction for geometric reasoning |
| 2026-04 | [MedLVR: Latent Visual Reasoning for Reliable Medical Visual Question Answering](https://arxiv.org/abs/2604.09757) | MedLVR | — | Medical VQA | Interleave latent visual evidence states with ROI supervision and VLPO |
| 2026-04 | [LaST-R1: Reinforcing Robotic Manipulation via Adaptive Physical Latent Reasoning](https://arxiv.org/abs/2604.28192) | LaST-R1 | NeurIPS 2026 | Robotics / VLA | Jointly optimize latent reasoning and actions with adaptive reasoning length |
| 2026-05 | [SSR3D-LLM: Structured Spatial Reasoning via Latent Steps for Fine-Grained Grounding in Unified 3D-LLMs](https://arxiv.org/abs/2605.28490) | SSR3D-LLM | NeurIPS 2026 | 3D Grounding | Latent spatial steps and memory tokens iteratively refine geometry-aware object ranking |
| 2026-05 | [VITAL: Visual-Semantic Dual Supervision for Enhanced and Interpretable Latent Reasoning in Medical MLLMs](https://arxiv.org/abs/2605.28422) | VITAL | — | Medical VQA | Dual text reconstruction + ROI feature regression for interpretable latent reasoning |
| 2026-06 | [Continuous Reasoning for Vision-Language-Action](https://arxiv.org/abs/2606.00229) | Continuous Reasoning | — | Robotics / VLA | Shared Gaussian latent thoughts trained by self-verification for action generation |
| 2026-06 | [Imagine Before You Predict: Interleaved Latent Visual Reasoning for Video Event Prediction](https://arxiv.org/abs/2606.05769) | Future-L1 | — | Video Prediction | Align latent visual spans to future frames, then optimize with temporal rewards |
| 2026-06 | [Think Less, Act Early: Reinforced Latent Reasoning with Early Exit in Vision-Language-Action Models](https://arxiv.org/abs/2606.15099) | AVA-VLA | ICML 2026 | Robotics / VLA | Denoise latent reasoning trajectories with RL and exit by state confidence |
| 2026-06 | [Latent Visual Diffusion Reasoning with Monte Carlo Tree Search](https://arxiv.org/abs/2606.27988) | LVDR | ECCV 2026 | Skill Assessment | Keypoint-guided MCTS reveals latent reasoning paths in sports and surgery videos |
| 2026-07 | [LEEVLA: Seeing What Matters in Latent Environment Evolution for Vision-Language-Action](https://arxiv.org/abs/2607.08182) | LEEVLA | — | Robotics / VLA | Prioritize task-relevant regions and predict structured latent feature evolution |

### 🔹 5. Related: Latent Reasoning for LLMs (Text-only)

Foundational and closely related works on latent reasoning in the text-only setting.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2023-10 | [Think Before You Speak: Training LLMs With Pause Tokens](https://arxiv.org/abs/2310.02226) | Pause Tokens | ICLR 2024 | Pause tokens as initial form of implicit reasoning |
| 2023-11 | [Implicit CoT via Knowledge Distillation](https://arxiv.org/abs/2311.01460) | ICoT-KD | — | KD for implicit CoT |
| 2024-05 | [From Explicit to Implicit CoT](https://arxiv.org/abs/2405.14838) | ICoT-SI | — | Step-by-step internalization of explicit CoT |
| 2024-12 | [Coconut: Reasoning in Continuous Latent Space](https://arxiv.org/abs/2412.06769) | Coconut | COLM 2025 | Foundational work on continuous latent reasoning |
| 2024-12 | [Compressed Chain of Thought](https://arxiv.org/abs/2412.13171) | CCoT | — | Dense representations for CoT compression |
| 2025-02 | [SoftCoT: Soft Chain-of-Thought](https://arxiv.org/abs/2502.12134) | SoftCoT | ACL 2025 | Soft thinking in continuous concept space |
| 2025-05 | [SoftCoT++: Test-Time Scaling](https://arxiv.org/abs/2505.11484) | SoftCoT++ | — | Diverse exploration via perturbed latent thoughts |
| 2025-05 | [Think Silently: Dynamic Latent Compression](https://arxiv.org/abs/2505.16552) | CoLaR | NeurIPS 2025 | Dynamic CoT compression into latent tokens |
| 2025-10 | [Latent Reasoning as Vocabulary-Space Superposition](https://arxiv.org/abs/2510.15522) | — | — | Vocabulary-space superposition for latent reasoning |
| 2026-01 | [Depth-Recurrent Attention Mixtures: Giving Latent Reasoning the Attention it Deserves](https://arxiv.org/abs/2601.21582) | Dreamer | NeurIPS 2026 | Sequence, depth, and expert attention scale recurrent latent reasoning efficiently |
| 2026-06 | [Geometric Latent Reasoning Induces Shorter Generations in LLMs](https://arxiv.org/abs/2606.02248) | GLR | NeurIPS 2026 | Transition head follows CoT-anchored paths in embedding space with fewer output tokens |

### 🔹 6. Causal Analysis & Critique

Works that critically examine whether latent tokens genuinely contribute to reasoning.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2026-02 | [CrystaL: Spontaneous Emergence of Visual Latents](https://arxiv.org/abs/2602.20980) | CrystaL | — | Dual-path alignment for crystallizing visual latents |
| 2026-02 | [Imagination Helps Visual Reasoning, But Not Yet in Latent Space](https://arxiv.org/abs/2602.22766) | CapImagine | ICML 2026 | Causal mediation analysis reveals latent tokens may be "placeholders" |
| 2026-05 | [What's Holding Back Latent Visual Reasoning?](https://arxiv.org/abs/2605.18445) | — | NeurIPS 2026 | Dummy-token and oracle-token analysis identifies weak intermediate supervision and latent collapse |
| 2026-05 | [Leveraging Latent Visual Reasoning in Silence](https://arxiv.org/abs/2605.18641) | — | NeurIPS 2026 | Noise/removal tests and attention rewards probe whether latent tokens guide learning |
| 2026-06 | [Beyond Visual Memory: Mechanistic Diagnostics of Latent Visual Reasoning](https://arxiv.org/abs/2606.01287) | — | — | Decomposes latent slots, boundary markers, and format to test causal mechanisms |
| 2026-09 | [Reason Through the Latent! Making Latent Visual Reasoning Necessary](https://arxiv.org/abs/2609.06746) | CVRR | — | Remove visual cache before decoding so answers must depend on recurrent latent states |

### 🔹 7. Latent Reasoning for Retrieval & Embedding

Applying latent reasoning or latent-space generation to retrieval, universal embeddings, and document representation.

| Date | Paper | Abbreviation | Venue | Task | Key Idea |
|------|-------|:---:|:---:|:---:|----------|
| 2026-01 | [CausalEmbed: Multi-Vector Generation in Latent Space](https://arxiv.org/abs/2601.21262) | CausalEmbed | — | Document Retrieval | Auto-regressive latent generation for document retrieval (30–155× compression) |
| 2026-04 | [PLUME: Latent Reasoning Based Universal Multimodal Embedding](https://arxiv.org/abs/2604.02073) | PLUME | — | Multimodal Retrieval | Implicit CoT reasoning before extracting universal multimodal embeddings |
| 2026-04 | [Latent Abstraction for Retrieval-Augmented Generation](https://arxiv.org/abs/2604.17866) | LAnR | NeurIPS 2026 | Text RAG | LLM hidden states form dense subqueries and decide when retrieval is sufficient |
| 2026-05 | [LatentRAG: Latent Reasoning and Retrieval for Efficient Agentic RAG](https://arxiv.org/abs/2605.06285) | LatentRAG | NeurIPS 2026 | Text RAG | Single-pass latent thoughts and subqueries align with dense retriever embeddings |
| 2026-08 | [Retrieval Grounding Latent Reasoning for Dense Retrieval](https://arxiv.org/abs/2608.14107) | RGLT | — | Text Retrieval | Credit intermediate silent-token transitions for retrieval improvements |
| 2026-09 | [Latent-Aligned Reasoning for Multimodal Recommendation](https://arxiv.org/abs/2609.04645) | LARK | — | Multimodal Recommendation | Align visual checkpoint latents and contrastive item embeddings with CoT states |

### NeurIPS 2026 titles awaiting public paper details

The [official NeurIPS 2026 list](https://neurips.cc/Downloads/2026) also includes the following closely related titles. They are listed here without method summaries or dated taxonomy rows until a public paper or abstract can be verified. The paper count above covers the dated taxonomy rows only:

- [GeLVR: Geometry-Consistent Latent Visual Reasoning in Multimodal LLMs](https://neurips.cc/virtual/2026/poster/150448)
- [SLVR: Structured Latent Visual Reasoning via Human-like Reasoning Flows](https://neurips.cc/virtual/2026/poster/154074) — distinct from the ICML 2026 paper *Semantic-Enriched Latent Visual Reasoning* above
- [Look Before You Reason: Implicit Visual Thinking for Efficient Multimodal Reasoning](https://neurips.cc/virtual/2026/poster/149054)
- [Latent Spatial Reasoning: Building Innate 3D Awareness via Latent-Space Distillation](https://neurips.cc/virtual/2026/poster/154054)
- [Think Densely, Act Sparsely: Latent Expert Cognitive Chains for Vision-Language-Action Autonomous Driving](https://neurips.cc/virtual/2026/poster/149058)

---

## 📊 Comparison Table

| Paper | Token Count | Supervision | Training | Base Model | Best Result |
|-------|:-----------:|:-----------:|:--------:|:----------:|-------------|
| Heima | ~N (1/step) | CoT annotations | Encoder-Decoder distill | Qwen MLLM | 6% tokens |
| MCOUT | N iterations | None | SFT | SilVar 1B | MMMU +8.23% |
| LVR | Variable | Crop regions | SFT + GRPO_latent | Qwen2.5-VL | MMVP +5% |
| IVT-LR | N steps | CoT annotations | Progressive SFT | — | 5× speedup |
| LaCoT | Variable | QA pairs | GFlowNet | Qwen2.5-VL | 3B > 11B |
| CoVT | ~20 | Depth/segmentation | Expert distillation | Qwen2.5-VL | +3~16% |
| Monet | Variable | Auxiliary images | 3-stage SFT + VLPO | Qwen2.5-VL | Multi-task ↑ |
| SkiLa | Variable | Sketch images | Visual semantic reconstruct | Qwen2.5-VL | > GPT-4o |
| LIVR | K learnable | **None** | Visual bottlenecking | Qwen2.5-VL | BLINK SOTA |
| VaLR | K/step | Visual encoders | Curriculum + REPA | Qwen2.5-VL | VSI +19.9% |
| SwimBird | Adaptive | Multi-mode | 3-mode SFT | Qwen2.5-VL | HR-Bench 79.0 |
| HIVE | Adaptive | Multi-modal | Loop Transformer SFT | Huginn 3.5B | ScienceQA 91.6% |
| LatentUM | Variable | Shared visual semantic space | Unified latent modeling | Unified multimodal model | Visual spatial planning ↑ |
| OneVL | One-step | Language + world-model | 3-stage alignment | VLA / World Model | Explicit-CoT accuracy at answer-only latency |
| HyLaR | Hybrid | Text + visual latents | SFT + DePO | — | Fine-grained perception ↑ |
| Unsilencing | Variable | Query-guided latent alignment | Inference-time optimization | MLLMs | Unblocks suppressed visual latents |
| RIS | Variable | Box + region descriptions | Grounded SFT + attention bottleneck | MLLM | Fine-grained perception ↑ |
| CoLVR | Variable | Perturbed latent contrasts | Contrastive learning + trajectory RL | MLLM | VSP +5.83%, Jigsaw +8.00% |
| SCOLAR | Long sequence | Visual feature anchoring | 3-stage SFT + ALPO | Vision-language model | >30× longer usable latent CoT |
| SLVR | Region-centric | Attribute + multi-query QA | 2-stage + M-GRPO | — | Semantic consistency ↑ |
| DeepLatent | Parallel 2D | Image features | Distillation + latent-space RL | Vision-language model | Parallel visual reasoning ↑ |
| LUT | Variable | VQA pairs | Utility distillation + attribution RL | MLLM | Perception-intensive reasoning ↑ |
| Scaffolding Minds | Variable | Learned visual targets | Scaffolding SFT + stochastic RL | MLLM | +5.2% avg on 9 visual benchmarks |
| LARC | Variable | CoT curriculum + image information gain | SFT + self-evolving RL | BAGEL | GenEval 0.88 vs 0.81 base |
| LaRA-VLA | Latent | Textual + visual CoT | Curriculum learning | VLA | Up to 90% latency reduction |
| MedLVR | Short segment | ROI evidence | ROI-SFT + VLPO | Qwen2.5-VL | Medical VQA avg 48.3→53.4 |
| VITAL | Latent | Text + ROI features | Dual supervision | Medical MLLM | SOTA on 7 medical VQA benchmarks |
| Continuous Reasoning | Structured Gaussian | Action verification | EMA self-verification | VLA | Real-robot success ↑ |
| Future-L1 | Interleaved spans | Future-frame features | SFT + LA-DAPO | Qwen3-VL-8B | FutureBench 61.0→85.4 |
| AVA-VLA | Adaptive | Task-level reward | RL denoising + early exit | VLA | 6× faster than explicit CoT |
| ImgCoT | **8** | Rendered CoT | TiTok + LLM SFT | Qwen2.5 | ≈ Full-CoT |
| ReGuLaR | ~3 steps | Rendered CoT | VAE (ELBO + KL) | LLaMA 3.2 | Avg 45.6% |
| OneLatent | **1** | Rendered CoT | 3-stage curriculum | DeepSeek-OCR | 11× compress, -2.21% |
| UniVLR | Compact | Rendered text + images | Visual latent compression | MLLM | Fewer reasoning tokens than prior LVR |
| DLR | Discrete latent vocabulary | Rendered CoT features | Codebook alignment + SFT + RL | Qwen3-VL / LLaMA-3 | Up to 20× CoT compression |

---

## 🔑 Key Trends

1. **From Text CoT → Visual CoT → Latent Space Reasoning** — Progressive transition to implicit reasoning
2. **Rendered CoT as Visual Supervision** — ImgCoT, ReGuLaR, OneLatent, and DLR use rendered traces for latent compression
3. **Hybrid Auto-regressive Generation & Decoupled Optimization** — Unified discrete text + continuous latent prediction with adaptive policies
4. **Multi-stage Training** — Progressive SFT + RL is the standard recipe
5. **Adaptive Mode Switching** — Models learn to choose text/visual/mixed reasoning per query
6. **Causal & Mechanistic Scrutiny** — CapImagine, Leveraging Latent Visual Reasoning in Silence, Beyond Visual Memory, SCOLAR, and CVRR test information collapse, boundary effects, and whether answers depend on latent states
7. **From Multi-token to Single-token** — Extreme compression (OneLatent: 1 token) with minimal accuracy loss
8. **Domain Specialization** — Geometry and 3D grounding, math, medical VQA, industrial anomaly detection, robotics/VLA, video prediction, skill assessment, and retrieval-specific latent reasoning
9. **Training for Latent Utility** — SCOLAR, LUT, Scaffolding Minds, CoLVR, and LARC optimize information gain, answer relevance, contrastive diversity, or task-specific visual targets

---

## 📝 Surveys

| Date | Title | arXiv |
|------|-------|:-----:|
| 2025-05 | [Reasoning Beyond Language: Survey on Latent CoT](https://arxiv.org/abs/2505.16782) | 2505.16782 |
| 2025-07 | [A Survey on Latent Reasoning](https://arxiv.org/abs/2507.06203) | 2507.06203 |
| 2025-09 | [Implicit Reasoning in LLMs: Comprehensive Survey](https://arxiv.org/abs/2509.02350) | 2509.02350 |

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a PR if you find a relevant paper missing or want to add corrections.

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=xandery-geek/Awesome-Latent-Visual-Reasoning&type=Date)](https://star-history.com/#xandery-geek/Awesome-Latent-Visual-Reasoning&Date)

---

*This repository is maintained by [Xander Yuan](https://github.com/xandery-geek). Licensed under [MIT](https://opensource.org/licenses/MIT).*
