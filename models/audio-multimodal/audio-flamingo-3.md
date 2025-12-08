# NVIDIA Audio Flamingo 3

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/nvidia/audio-flamingo-3-hf)
[![Paper](https://img.shields.io/badge/arXiv-Paper-red)](https://arxiv.org/abs/2507.00540)

**Developer:** NVIDIA
**Parameters:** 8B
**License:** NVIDIA OneWay Noncommercial License
**Architecture:** Transformer Decoder-only (Qwen2.5-7B backbone)
**Release Date:** July 2025

Audio Flamingo 3 (AF3) is a state-of-the-art audio-language model that provides unified understanding across speech, sound, and music. It features a custom AF-Whisper audio encoder, MLP-based audio adaptor, and Qwen2.5-7B language model backbone. AF3 supports long-context audio comprehension up to 10 minutes and multi-turn conversational dialogue with audio context.

## Key Features

- Unified audio representation for speech, sound, and music
- Long-context audio processing (up to 10 minutes)
- Multi-turn conversational dialogue with audio context
- Chain-of-thought reasoning via AF-Think PEFT adapter
- Voice-to-voice interaction (AF3-Chat variant with streaming TTS)
- Emotion and tone analysis in speech
- Detailed audio captioning and question answering
- Flash Attention 2 and torch compile support

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 8B |
| Audio Encoder | AF-Whisper (unified) |
| Adapter | MLP-based audio adaptor |
| LLM Backbone | Qwen2.5-7B |
| Tensor Type | BF16 |
| Max Audio Length | 10 minutes |
| Audio Window | 30 seconds |
| Max Input Tokens | 16,000 |
| Max Output Tokens | 1,024 |

**Supported Input Formats:**
- Audio: WAV, MP3, FLAC
- Text: UTF-8 (up to 16K tokens)

**Model Variants:**
- **AF3** - Base audio understanding model
- **AF3-Chat** - Voice-to-voice with streaming TTS
- **AF-Think** - Chain-of-thought reasoning PEFT adapter

## Deployment Considerations

**Hardware Requirements:**
- Recommended: NVIDIA Ampere (A100) or Hopper (H100)
- Supported OS: Linux
- Runtime: PyTorch / HuggingFace Transformers

**Performance Optimizations:**
- Flash Attention 2 support
- Torch compile compatibility
- PyTorch SDPA fallback

**Usage Example:**
```python
from transformers import AutoProcessor, AutoModelForCausalLM
import torch

model = AutoModelForCausalLM.from_pretrained(
    "nvidia/audio-flamingo-3-hf",
    torch_dtype=torch.bfloat16,
    trust_remote_code=True
)
processor = AutoProcessor.from_pretrained(
    "nvidia/audio-flamingo-3-hf",
    trust_remote_code=True
)

# Process audio and text
inputs = processor(
    audio=audio_array,
    text="Describe what you hear in this audio.",
    return_tensors="pt"
)
outputs = model.generate(**inputs, max_new_tokens=256)
response = processor.decode(outputs[0], skip_special_tokens=True)
```

## About NVIDIA

NVIDIA is a leading AI computing company that has expanded from GPUs into comprehensive AI platforms. Their research division has produced numerous influential models and frameworks across computer vision, natural language processing, and now audio-language understanding. Audio Flamingo 3 represents their entry into the audio multimodal space, building on their expertise in efficient inference and large-scale model training.

## Practical Assessment

**Strengths:**
- Long-context audio support (10 minutes) exceeds many competitors
- Unified handling of speech, sound, and music domains
- Chain-of-thought reasoning capability via AF-Think adapter
- Voice-to-voice interaction option (AF3-Chat)
- Strong hardware optimization (Flash Attention 2, torch compile)
- Built on proven Qwen2.5-7B backbone

**Weaknesses:**
- Non-commercial license limits deployment options
- Requires high-end NVIDIA hardware (A100/H100 recommended)
- Linux-only support
- Subject to additional Qwen Research License terms

**Best suited for:** Research applications requiring long-form audio understanding, multi-turn audio dialogue systems, and projects that need unified speech/sound/music comprehension. The non-commercial license makes this ideal for academic research rather than production deployments.

## Links

- [Hugging Face Model](https://huggingface.co/nvidia/audio-flamingo-3-hf)
- [NVIDIA AI](https://www.nvidia.com/en-us/ai/)
