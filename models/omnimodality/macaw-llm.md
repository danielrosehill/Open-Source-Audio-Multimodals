# Macaw-LLM

[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/lyuchenyang/Macaw-LLM)
[![Paper](https://img.shields.io/badge/arXiv-2306.09093-b31b1b)](https://arxiv.org/abs/2306.09093)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Papers-yellow)](https://huggingface.co/papers/2306.09093)

**Developer:** Chenyang Lyu et al.
**Parameters:** 7B / 13B (based on LLaMA/Vicuna/Bloom)
**License:** Apache 2.0
**Architecture:** CLIP + Whisper + LLM (Multi-Modal Alignment)
**Released:** June 2023

Macaw-LLM is a pioneering multi-modal language model that seamlessly integrates visual, audio, and textual information. It was one of the early research efforts to combine image, video, audio, and text modalities into a single LLM framework using a novel one-stage instruction fine-tuning approach.

## Key Features

- **Multi-modal input processing**: Handles images, video frames, audio, and text simultaneously
- **One-stage training**: Simplified alignment process compared to traditional two-stage approaches
- **Audio understanding**: Uses Whisper to encode and process audio data
- **Efficient alignment**: Attention-based mechanism with minimal additional parameters
- **Open dataset**: 69K image + 50K video instruction examples publicly released

## Architecture

Macaw-LLM consists of three main components:

1. **Modality Module**
   - **CLIP** - Encodes images and video frames
   - **Whisper** - Processes audio inputs

2. **Cognitive Module**
   - **LLaMA/Vicuna/Bloom** - Language generation backbone

3. **Alignment Module**
   - Novel attention-based mechanism where multi-modal features serve as queries against the LLM's embedding matrix
   - Enables efficient feature integration with minimal additional parameters
   - Single-stage training (vs. traditional two-stage approaches)

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 7B / 13B |
| Base LLMs | LLaMA, Vicuna, Bloom |
| Visual Encoder | CLIP |
| Audio Encoder | Whisper |
| Training Data | 69K image + 50K video instruction samples |
| Data Sources | MS COCO (images), Charades & AVSD (video) |
| License | Apache 2.0 |

## Training Data

The researchers constructed a multi-modal instruction dataset for single-turn dialogues:
- **69K image-based instances** - Generated from MS COCO captions using GPT-3.5-Turbo
- **50K video-based instances** - From Charades and Audio-Visual Scene-aware Dialogue (AVSD) datasets

## Model Variants

| Variant | Base LLM | Parameters |
|---------|----------|------------|
| Macaw-LLM-7B | LLaMA-7B | 7B |
| Macaw-LLM-13B | LLaMA-13B | 13B |

## Deployment Considerations

**Hardware Requirements:**
- 7B model: ~16GB VRAM recommended
- 13B model: ~32GB VRAM recommended

**Dependencies:**
- PyTorch
- Transformers
- CLIP
- Whisper

## About the Developers

Macaw-LLM was developed by Chenyang Lyu and collaborators. The project represents early academic research into unifying multiple modalities within a single LLM framework, predating many of the larger commercial omni-modal efforts.

## Practical Assessment

**Strengths:**
- Pioneer in open-source omni-modal LLMs (June 2023)
- Simple one-stage training paradigm
- Comprehensive modality coverage (image, video, audio, text)
- Apache 2.0 license for commercial use
- Training data and code fully released

**Weaknesses:**
- Based on older LLaMA 1 generation
- Less active development compared to newer models
- No official quantizations (GGUF) available
- Superseded by more recent omni-modal models (Qwen-Omni, etc.)

**Best suited for:** Researchers interested in multi-modal LLM architectures and the evolution of omni-modal approaches. The one-stage alignment strategy is of particular academic interest. For production use cases, newer models like Qwen-Omni or Gemini offer more refined implementations.

## Historical Significance

Macaw-LLM was published in June 2023, making it one of the earliest open-source efforts to combine all four major modalities (image, video, audio, text) in a single LLM. While newer models have since surpassed it in capability, it represents an important milestone in the development of omni-modal AI systems.

## Links

- [GitHub Repository](https://github.com/lyuchenyang/Macaw-LLM)
- [Research Paper (arXiv)](https://arxiv.org/abs/2306.09093)
- [Hugging Face Paper Page](https://huggingface.co/papers/2306.09093)
