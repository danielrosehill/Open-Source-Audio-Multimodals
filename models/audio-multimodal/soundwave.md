# Soundwave

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/FreedomIntelligence/Soundwave)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/FreedomIntelligence/Soundwave)
[![Paper](https://img.shields.io/badge/arXiv-2502.12900-b31b1b)](https://arxiv.org/abs/2502.12900)

**Developer:** FreedomIntelligence (CUHK Shenzhen)
**Parameters:** 9B
**License:** Apache 2.0
**Architecture:** Audio-Text-to-Text (F16)

A data-efficient speech-text alignment model that outperforms Qwen2-Audio on key benchmarks while using only 1/50th of the training data. Demonstrates that careful architectural design can compensate for limited training resources.

## Key Features

- Outperforms Qwen2-Audio on speech translation and AIR-Bench tasks
- Trained on only 10k hours of audio data (vs. 500k+ for comparable models)
- Maintains conversational intelligence during interactive sessions
- Addresses representation space gap and sequence length inconsistency between speech and text

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 9B |
| Tensor Type | Float16 |
| Training Data | 10k hours |
| Primary Language | English |
| VRAM Required | ~21GB minimum |

## Deployment Considerations

**Hardware Requirements:**
- Minimum 21GB VRAM for inference
- CUDA-capable GPU recommended (CPU fallback available but slow)

**Limitations:**
- No GGUF quantizations currently available
- Maximum audio duration not documented
- English-focused (multilingual performance unverified)
- Demo space currently non-functional (GPU allocation issues)

**Inference Settings (from reference implementation):**
- Max tokens: 512
- Temperature: 0.2
- Top-p: 0.9

## About FreedomIntelligence

FreedomIntelligence is a research team from The Chinese University of Hong Kong, Shenzhen (CUHKSZ), focused on democratizing LLM research. Known for:

- **HuatuoGPT series** - Medical-focused LLMs
- **LLMZoo** - Open models, data, and evaluation benchmarks
- **TwinMarket** - Multi-agent socio-economic simulation (NeurIPS 2025 & ICLR 2025 award winner)

Their work emphasizes open-source contributions and data-efficient training approaches.

## Practical Assessment

**Strengths:**
- Strong benchmark performance relative to training data size
- Apache 2.0 license allows commercial use
- Well-documented research paper with clear methodology

**Weaknesses:**
- High VRAM requirements (21GB) limit local deployment options
- No quantized variants for consumer hardware
- Demo unavailable for testing
- Less mature ecosystem compared to Qwen2-Audio

**Best suited for:** Researchers interested in data-efficient training approaches, or production deployments with adequate GPU resources (cloud or dedicated).

## Links

- [Hugging Face Model](https://huggingface.co/FreedomIntelligence/Soundwave)
- [GitHub Repository](https://github.com/FreedomIntelligence/Soundwave)
- [Research Paper (arXiv)](https://arxiv.org/abs/2502.12900)
- [Demo Space](https://huggingface.co/spaces/puccho/Soundwave) (currently offline)
