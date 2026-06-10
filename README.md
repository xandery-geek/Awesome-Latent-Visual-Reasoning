# 🧠 Awesome Latent Visual Reasoning

<div align="center">

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Stars](https://img.shields.io/github/stars/xandery-geek/Awesome-Latent-Visual-Reasoning?style=social)](https://github.com/xandery-geek/Awesome-Latent-Visual-Reasoning) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

A curated collection of papers on **Latent Visual Reasoning** — enabling Multimodal Large Language Models (MLLMs) to reason in continuous latent/visual space rather than discrete text token space.

**Last updated:** June 2026 | **Papers:** 43

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

Papers that enable MLLMs to generate or manipulate visual embeddings/latents during reasoning trajectories without decoding into explicit images.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2025-01 | [Efficient Reasoning with Hidden Thinking](https://arxiv.org/abs/2501.19201) | Heima | — | Encode each CoT step into a single thinking token; token count reduced to 6% |
| 2025-09 | [Multimodal Chain of Continuous Thought](https://arxiv.org/abs/2508.12587) | MCOUT | NeurIPS 2025 Workshop | Iterative continuous latent thought with multimodal attention for VLMs |
| 2025-10 | [Latent Visual Reasoning](https://arxiv.org/abs/2509.24251) | LVR | ICLR 2026 | Auto-regressive visual token reconstruction interleaved with text generation |
| 2025-10 | [Reasoning in the Dark: Interleaved Vision-Text Reasoning in Latent Space](https://arxiv.org/abs/2510.12603) | IVT-LR | — | Unified latent text + latent vision tokens per reasoning step |
| 2025-10 | [Latent Chain-of-Thought for Visual Reasoning](https://arxiv.org/abs/2510.23925) | LaCoT | NeurIPS 2025 | Bayesian formulation via amortized variational inference and GFlowNet |
| 2025-11 | [Chain-of-Visual-Thought](https://arxiv.org/abs/2511.19418) | CoVT | — | ~20 continuous visual tokens distilled from segmentation, depth, edge experts |
| 2025-11 | [Monet: Reasoning in Latent Visual Space](https://arxiv.org/abs/2511.21395) | Monet | CVPR 2026 | 3-stage distillation + VLPO for latent visual reasoning |
| 2025-12 | [Sketch-in-Latents](https://arxiv.org/abs/2512.16584) | SkiLa | — | Multi-step interleaved text + visual sketch tokens |
| 2025-12 | [Latent Implicit Visual Reasoning](https://arxiv.org/abs/2512.21218) | LIVR | — | Task-agnostic: no explicit supervision via visual bottlenecking |
| 2026-02 | [Vision-aligned Latent Reasoning](https://arxiv.org/abs/2602.04476) | VaLR | — | Dynamic vision-aligned latents per CoT step with REPA |
| 2026-02 | [SwimBird: Switchable Reasoning Mode](https://arxiv.org/abs/2602.06040) | SwimBird | — | Adaptive mode switching: text / visual / interleaved |
| 2026-02 | [HIVE: Multimodal Latent Reasoning via Hierarchical Visual Cues](https://arxiv.org/abs/2602.05359) | HIVE | — | Loop Transformer with coarse-to-fine hierarchical visual injection |
| 2026-04 | [OneVL: One-Step Latent Reasoning and Planning with Vision-Language Explanation](https://arxiv.org/abs/2604.18486) | OneVL | — | One-step latent reasoning with dual language/world-model supervision for VLA |
| 2026-04 | [Hybrid Latent Reasoning with Decoupled Policy Optimization](https://arxiv.org/abs/2604.20328) | HyLaR | — | Hybrid text + visual latent reasoning optimized with DePO |
| 2026-05 | [Visual Latents Know More Than They Say: Unsilencing Latent Reasoning in MLLMs](https://arxiv.org/abs/2605.02735) | Unsilencing | — | Inference-time latent optimization with contrastive alignment and confidence reward |
| 2026-05 | [Semantic-Enriched Latent Visual Reasoning](https://arxiv.org/abs/2605.19342) | SLVR | — | Attribute-supervised region latents aligned via multi-query GRPO |

### 🔹 2. Rendered CoT → Visual Latent Reasoning

A growing paradigm: render text CoT as images, then use visual features as supervision for latent reasoning. Bridges text-space and visual-space reasoning.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2026-01 | [Render-of-Thought](https://arxiv.org/abs/2601.14750) | RoT | — | Render textual CoT as images for visual latent reasoning |
| 2026-01 | [ImgCoT: Compressing Long CoT into Compact Visual Tokens](https://arxiv.org/abs/2601.22730) | ImgCoT | — | Visual CoT compression via TiTok; 8 tokens replace full CoT |
| 2026-01 | [ReGuLaR: Variational Latent Reasoning](https://arxiv.org/abs/2601.23184) | ReGuLaR | — | VAE framework for latent reasoning with rendered CoT as prior |
| 2026-02 | [OneLatent: Single-Token Compression](https://arxiv.org/abs/2602.13738) | OneLatent | — | Extreme compression to 1 token with DeepSeek-OCR supervision |

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
| 2026-02 | [Latent Reasoning VLA: Latent Thinking and Prediction for Vision-Language-Action Models](https://arxiv.org/abs/2602.01166) | LaRA-VLA | ICML 2026 | Robotics / VLA | Internalize multimodal CoT into continuous latents for embodied action |
| 2026-03 | [LatentGeo: Learnable Auxiliary Constructions](https://arxiv.org/abs/2603.12166) | LatentGeo | — | Geometry | Latent auxiliary line construction for geometric reasoning |
| 2026-04 | [MedLVR: Latent Visual Reasoning for Reliable Medical Visual Question Answering](https://arxiv.org/abs/2604.09757) | MedLVR | — | Medical VQA | Interleave latent visual evidence states with ROI supervision and VLPO |
| 2026-05 | [VITAL: Visual-Semantic Dual Supervision for Enhanced and Interpretable Latent Reasoning in Medical MLLMs](https://arxiv.org/abs/2605.28422) | VITAL | — | Medical VQA | Dual text reconstruction + ROI feature regression for interpretable latent reasoning |
| 2026-06 | [Continuous Reasoning for Vision-Language-Action](https://arxiv.org/abs/2606.00229) | Continuous Reasoning | — | Robotics / VLA | Shared Gaussian latent thoughts trained by self-verification for action generation |

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

### 🔹 6. Causal Analysis & Critique

Works that critically examine whether latent tokens genuinely contribute to reasoning.

| Date | Paper | Abbreviation | Venue | Key Idea |
|------|-------|:---:|:---:|----------|
| 2026-02 | [Imagination Helps, But Not Yet in Latent Space](https://arxiv.org/abs/2602.22766) | CapImagine | — | Causal mediation analysis reveals latent tokens may be "placeholders" |
| 2026-02 | [CrystaL: Spontaneous Emergence of Visual Latents](https://arxiv.org/abs/2602.20980) | CrystaL | — | Dual-path alignment for crystallizing visual latents |
| 2026-05 | [What's Holding Back Latent Visual Reasoning?](https://arxiv.org/abs/2605.18445) | — | — | Dummy-token and oracle-token analysis identifies weak intermediate supervision and latent collapse |
| 2026-06 | [Beyond Visual Memory: Mechanistic Diagnostics of Latent Visual Reasoning](https://arxiv.org/abs/2606.01287) | — | — | Decomposes latent slots, boundary markers, and format to test causal mechanisms |

### 🔹 7. Latent Reasoning for Retrieval & Embedding

Applying latent reasoning or latent-space generation to retrieval, universal embeddings, and document representation.

| Date | Paper | Abbreviation | Venue | Task | Key Idea |
|------|-------|:---:|:---:|:---:|----------|
| 2026-01 | [CausalEmbed: Multi-Vector Generation in Latent Space](https://arxiv.org/abs/2601.21262) | CausalEmbed | — | Document Retrieval | Auto-regressive latent generation for document retrieval (30–155× compression) |
| 2026-04 | [PLUME: Latent Reasoning Based Universal Multimodal Embedding](https://arxiv.org/abs/2604.02073) | PLUME | — | Multimodal Retrieval | Implicit CoT reasoning before extracting universal multimodal embeddings |

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
| OneVL | One-step | Language + world-model | 3-stage alignment | VLA / World Model | Explicit-CoT accuracy at answer-only latency |
| HyLaR | Hybrid | Text + visual latents | SFT + DePO | — | Fine-grained perception ↑ |
| Unsilencing | Variable | Query-guided latent alignment | Inference-time optimization | MLLMs | Unblocks suppressed visual latents |
| SLVR | Region-centric | Attribute + multi-query QA | 2-stage + M-GRPO | — | Semantic consistency ↑ |
| LaRA-VLA | Latent | Textual + visual CoT | Curriculum learning | VLA | Up to 90% latency reduction |
| MedLVR | Short segment | ROI evidence | ROI-SFT + VLPO | Qwen2.5-VL | Medical VQA avg 48.3→53.4 |
| VITAL | Latent | Text + ROI features | Dual supervision | Medical MLLM | SOTA on 7 medical VQA benchmarks |
| Continuous Reasoning | Structured Gaussian | Action verification | EMA self-verification | VLA | Real-robot success ↑ |
| ImgCoT | **8** | Rendered CoT | TiTok + LLM SFT | Qwen2.5 | ≈ Full-CoT |
| ReGuLaR | ~3 steps | Rendered CoT | VAE (ELBO + KL) | LLaMA 3.2 | Avg 45.6% |
| OneLatent | **1** | Rendered CoT | 3-stage curriculum | DeepSeek-OCR | 11× compress, -2.21% |

---

## 🔑 Key Trends

1. **From Text CoT → Visual CoT → Latent Space Reasoning** — Progressive transition to implicit reasoning
2. **Rendered CoT as Visual Supervision** — ImgCoT, ReGuLaR, OneLatent share this emerging paradigm
3. **Hybrid Auto-regressive Generation & Decoupled Optimization** — Unified discrete text + continuous latent prediction with adaptive policies
4. **Multi-stage Training** — Progressive SFT + RL is the standard recipe
5. **Adaptive Mode Switching** — Models learn to choose text/visual/mixed reasoning per query
6. **Causal & Mechanistic Scrutiny** — CapImagine, What's Holding Back, and Beyond Visual Memory test whether latent slots causally contribute or act as format/boundary markers
7. **From Multi-token to Single-token** — Extreme compression (OneLatent: 1 token) with minimal accuracy loss
8. **Domain Specialization** — Geometry, math, medical VQA, robotics/VLA, and retrieval-specific latent reasoning

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
