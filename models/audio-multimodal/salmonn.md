# SALMONN

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/collections/tsinghua-ee/salmonn-66752469e7e54c6580a3c65f)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/bytedance/SALMONN)
[![Paper](https://img.shields.io/badge/arXiv-2310.13289-b31b1b)](https://arxiv.org/abs/2310.13289)

**Developer:** ByteDance & Tsinghua University
**Parameters:** 7B / 13B
**License:** Apache 2.0
**Architecture:** Audio-Text-to-Text (dual audio encoders + LLM)
**Released:** October 2023 (ICLR 2024)

SALMONN (Speech Audio Language Music Open Neural Network) was one of the pioneering open-source audio multimodal models, enabling LLMs to perceive and understand general audio inputs including speech, audio events, and music. The project has evolved into a family of models covering audio-visual understanding and speech quality assessment.

## Key Features

- Generic hearing abilities for LLMs—speech, sound, and music comprehension
- Dual audio encoder architecture (Whisper + BEATs)
- Audio-based storytelling and captioning
- Cross-modal emergent abilities through multi-task training
- Extensive training data released (600k+ QA samples, 50k storytelling annotations)
- Multiple specialized variants for different tasks

## Model Family

| Variant | Focus | Publication |
|---------|-------|-------------|
| SALMONN | Core audio-text understanding | ICLR 2024 |
| video-SALMONN | Audio-visual integration | ICML 2024 |
| video-SALMONN-o1 | Reasoning-enhanced audio-visual | ICML 2025 |
| video-SALMONN 2 | High-quality AV captioning | July 2025 |
| SALMONN-SQA | Speech quality assessment | ICASSP/ACL 2025 |

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 7B / 13B |
| Base LLM | Vicuna-7B / Vicuna-13B |
| Audio Encoder | Whisper-large-v2 + BEATs |
| Training Data | 600k+ QA samples |
| Context Length | Standard LLM context |
| License | Apache 2.0 |

## Architecture

SALMONN uses a dual-encoder design:
1. **Whisper encoder** - Speech recognition capabilities
2. **BEATs encoder** - Non-speech audio event understanding
3. **Q-Former bridge** - Connects audio representations to LLM
4. **Vicuna LLM** - Language generation backbone

This dual-encoder approach provides complementary coverage of speech and general audio understanding.

## Deployment Considerations

**Hardware Requirements:**
- 7B model: ~14GB VRAM recommended
- 13B model: ~26GB VRAM recommended

**Deployment Options:**
1. **Transformers** - Direct inference with HuggingFace
2. **Gradio demo** - Provided in repository

**Model Variants:**
- `SALMONN-7B` - Lighter weight option
- `SALMONN-13B` - Enhanced capability

## About ByteDance & Tsinghua

SALMONN is a collaborative effort between ByteDance and Tsinghua University's Department of Electronic Engineering. The project represents academic-industry collaboration in advancing audio-language models.

ByteDance brings industry-scale engineering and deployment expertise, while Tsinghua contributes fundamental research capabilities. The team has been prolific in publishing at top venues (ICLR, ICML, ICASSP, ACL) and releasing models under permissive licenses.

## Practical Assessment

**Strengths:**
- Pioneer in open-source audio multimodals—mature and well-researched
- Dual encoder design handles both speech and general audio
- Extensive training data publicly released
- Strong academic backing with peer-reviewed publications
- Apache 2.0 license allows commercial use
- Active development with multiple specialized variants

**Weaknesses:**
- Based on older Vicuna LLM (not latest generation)
- Larger VRAM requirements than some newer models
- No official GGUF quantizations available
- Less active community compared to Qwen2-Audio

**Best suited for:** Researchers and developers wanting a well-documented, academically rigorous audio multimodal with extensive released training data. The video-SALMONN variants are particularly valuable for audio-visual applications.

## Links

- [SALMONN Collection (Hugging Face)](https://huggingface.co/collections/tsinghua-ee/salmonn-66752469e7e54c6580a3c65f)
- [GitHub Repository](https://github.com/bytedance/SALMONN)
- [Research Paper (arXiv)](https://arxiv.org/abs/2310.13289)
- [video-SALMONN Paper](https://arxiv.org/abs/2404.00612)
