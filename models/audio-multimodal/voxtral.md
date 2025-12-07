# Voxtral

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/mistralai)
[![Website](https://img.shields.io/badge/Website-Mistral%20AI-orange)](https://mistral.ai/news/voxtral)
[![Paper](https://img.shields.io/badge/arXiv-2507.13264-b31b1b)](https://arxiv.org/abs/2507.13264)

**Developer:** Mistral AI
**Parameters:** 5B (Mini), 24B (Full)
**License:** Apache 2.0
**Architecture:** Audio-Text-to-Text (BF16)
**Released:** July 2025

Mistral's frontier open-source speech understanding models. Goes beyond traditional ASR by incorporating semantic understanding and language comprehension directly into the model. The Mini variant (built on Ministral 3B backbone) is specifically designed for local and edge deployments, while the full Voxtral leverages Mistral Small 3.1.

## Key Features

- Native multilingual support with automatic language detection (8+ languages)
- Built-in Q&A and summarization without separate model chaining
- Direct function-calling triggered by spoken intent
- Retains text understanding from language model backbone
- Multi-audio processing per message and multi-turn conversations

## Technical Specifications

| Spec | Voxtral Mini | Voxtral |
|------|--------------|---------|
| Parameters | 5B | 24B |
| Backbone | Ministral 3B | Mistral Small 3.1 |
| Context Length | 32k tokens | 32k tokens |
| Max Audio (Transcription) | 30 minutes | 30 minutes |
| Max Audio (Understanding) | 40 minutes | 40 minutes |
| VRAM Required | ~9.5GB (BF16) | ~48GB (BF16 est.) |
| Tensor Type | BF16 | BF16 |

**Supported Languages:** English, Spanish, French, Portuguese, Hindi, German, Dutch, Italian (with automatic detection)

## Deployment Considerations

**Hardware Requirements:**
- Voxtral Mini: Consumer GPU viable (~10GB VRAM)
- Full Voxtral: Enterprise GPU required (~48GB+ VRAM)

**Quantization Availability:**
- 7 quantized variants available for Voxtral Mini
- Enables deployment on consumer hardware

**Deployment Options:**
1. **vLLM (recommended)** - OpenAI-compatible API server
2. **Transformers** (v4.54.0+) - Direct inference
3. **Mistral API** - Starting at $0.001/minute

**Inference Settings:**
- Chat/Understanding: temperature=0.2, top_p=0.95
- Transcription: temperature=0.0

## About Mistral AI

Mistral AI is a Paris-based AI research company founded in 2023 by former Google DeepMind and Meta researchers, including Arthur Mensch (CEO), Guillaume Lample, and Timothee Lacroix. Known for their commitment to open-source AI, they've released a series of competitive open-weight models including Mistral 7B, Mixtral, and now Voxtral.

The company has raised over $1 billion and is valued at approximately $6 billion, making it one of Europe's most valuable AI startups. Their philosophy emphasizes democratizing AI through open, accessible models while building enterprise-grade infrastructure.

## Practical Assessment

**Strengths:**
- Excellent local deployment option with Mini variant
- Long audio support (30-40 minutes) exceeds most competitors
- Apache 2.0 license allows commercial use
- Strong benchmark performance (surpasses Whisper Large-v3, matches GPT-4o mini)
- Built-in function calling for voice-triggered actions

**Weaknesses:**
- Full 24B model requires significant hardware
- Newer model with less community tooling than Qwen2-Audio
- Limited to 8 languages (fewer than some competitors)

**Best suited for:** Developers wanting a balance of capability and local deployability. The Mini variant is particularly attractive for edge deployment and voice agent applications.

## Links

- [Voxtral Mini (Hugging Face)](https://huggingface.co/mistralai/Voxtral-Mini-3B-2507)
- [Voxtral (Hugging Face)](https://huggingface.co/mistralai/Voxtral-24B-2507)
- [Announcement Blog](https://mistral.ai/news/voxtral)
- [Research Paper (arXiv)](https://arxiv.org/abs/2507.13264)
