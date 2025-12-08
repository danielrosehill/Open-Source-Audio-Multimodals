# BuboGPT

[![Project Page](https://img.shields.io/badge/Project-Page-green)](https://bubo-gpt.github.io/)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/magic-research/bubogpt)
[![Paper](https://img.shields.io/badge/arXiv-2307.08581-b31b1b)](https://arxiv.org/abs/2307.08581)

**Developer:** ByteDance Inc.
**Parameters:** 7B / 13B (Vicuna backbone)
**License:** BSD 3-Clause
**Architecture:** Multi-modal LLM (text + image + audio) with visual grounding
**Released:** July 2023

BuboGPT is a multi-modal LLM that incorporates text, image, and audio inputs with a unique ability to ground its responses to visual objects. Named after Bubo owls (known for strong vision and hearing), the model excels at joint audio-visual understanding and can localize sounds within images.

## Key Features

- Joint understanding of text, vision, and audio in a shared representation space
- Fine-grained visual grounding with SAM-based object localization
- Sound localization from aligned audio-image pairs
- Detailed audio description and acoustic analysis
- Assessment of relevance between arbitrary audio-image combinations
- Cross-modal interaction between all three modalities

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 7B / 13B (depends on Vicuna backbone) |
| Base LLM | Vicuna-7B / Vicuna-13B |
| Vision Encoder | Q-Former |
| Audio Encoder | Q-Former |
| Visual Grounding | SAM-based module |
| License | BSD 3-Clause |

## Architecture

BuboGPT uses a modular architecture:
1. **Modality Q-Formers** - Separate encoders for image and audio
2. **Projection matrices** - Connect Q-Formers to LLM
3. **Vicuna LLM** - Language generation backbone
4. **SAM grounding module** - Extracts entities and finds corresponding image masks

The framework learns a shared representation space across modalities through a two-stage training process.

## Training Approach

**Stage 1: Single-modal pre-training**
- Train on paired modality-text data

**Stage 2: Multi-modal instruction tuning**
- Curated datasets from MiniGPT-4, LLaVA, Clotho, and VGGSS
- Enables joint text-image-audio understanding

## Deployment Considerations

**Hardware Requirements:**
- Python 3.9, CUDA 11.7, PyTorch 2.0.1
- 7B model: ~14GB VRAM
- 13B model: ~26GB VRAM

**Deployment Options:**
- Gradio demo provided in repository
- Direct inference with PyTorch

## About ByteDance

BuboGPT is developed by researchers at ByteDance Inc., including Yang Zhao, Zhijie Lin, Daquan Zhou, Zilong Huang, Jiashi Feng, and Bingyi Kang. ByteDance has been active in multimodal AI research, also producing SALMONN and other audio-visual models.

## Practical Assessment

**Strengths:**
- Unique visual grounding capability—can point to objects in images
- Joint audio-visual understanding (sound localization)
- SAM integration for precise object segmentation
- Works with arbitrary modality combinations (aligned or unaligned)
- BSD 3-Clause license allows commercial use

**Weaknesses:**
- Based on older Vicuna LLM (not latest generation)
- No official quantized versions available
- Less focused on pure audio tasks compared to SALMONN
- Limited community adoption

**Best suited for:** Applications requiring audio-visual understanding with visual grounding—especially use cases where you need to localize sounds in images or relate audio events to visual objects.

## Links

- [Project Page](https://bubo-gpt.github.io/)
- [GitHub Repository](https://github.com/magic-research/bubogpt)
- [Research Paper (arXiv)](https://arxiv.org/abs/2307.08581)
