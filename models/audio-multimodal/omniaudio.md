# OmniAudio-2.6B

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/NexaAI/OmniAudio-2.6B)
[![GitHub](https://img.shields.io/badge/GitHub-Nexa--SDK-black)](https://github.com/NexaAI/nexa-sdk)

**Developer:** NexaAI
**Parameters:** 2.6B
**License:** Apache 2.0
**Architecture:** Gemma2-based multimodal

OmniAudio-2.6B is a compact multimodal audio-language model designed specifically for efficient on-device deployment. It integrates Gemma-2-2b as the language backbone with Whisper Turbo for audio processing, connected via a custom projector module. Unlike traditional ASR+LLM pipelines, OmniAudio unifies both capabilities in a single architecture optimized for minimal latency and resource overhead.

## Key Features

- Compact 2.6B parameter design for edge deployment
- Unified audio-text processing (no separate ASR stage)
- Offline operation without internet connectivity
- GGUF quantization support for consumer hardware
- 5.5x to 10.3x faster than Qwen2-Audio-7B on equivalent hardware
- Voice-in conversational AI with active listening
- Audio summarization and tone modification

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 2.6B |
| LLM Backbone | Gemma-2-2b |
| Audio Encoder | Whisper Turbo |
| Architecture | Gemma2 with custom projector |
| Tensor Types | FP16, Q4_0, Q4_K_M, Q8_0 |

**Model Sizes (GGUF):**
| Format | Size |
|--------|------|
| Q4_0 | 1.63 GB |
| Q4_K_M | 1.71 GB |
| Q8_0 | 2.78 GB |

## Performance Benchmarks

Tested on 2024 Mac Mini M4 Pro:

| Format | Tokens/sec |
|--------|------------|
| FP16 GGUF | 35.23 |
| Q4_K_M | 66.00 |

**Comparison:** 5.5x to 10.3x faster than Qwen2-Audio-7B-Instruct on equivalent hardware.

## Deployment Considerations

**Hardware Requirements:**
- Q4_K_M: 1.30 GB RAM, 1.60 GB storage
- Runs on consumer hardware (Mac, edge devices)
- No GPU required for inference

**Quick Start:**
```bash
# Install Nexa-SDK
pip install nexaai

# Run with streaming
nexa run omniaudio -st
```

**Python Usage:**
```python
from nexa.gguf import NexaOmniAudioModel

model = NexaOmniAudioModel(
    model_path="NexaAI/OmniAudio-2.6B:gguf-q4_K_M"
)

# Process audio with text prompt
response = model.inference(
    audio_path="recording.wav",
    prompt="Summarize this meeting recording"
)
print(response)
```

## Use Cases

- **Offline voice QA** - Process voice queries without internet
- **Voice-in conversations** - Real-time audio chat on device
- **Creative content generation** - Transform voice prompts into written content
- **Meeting summarization** - Convert lengthy recordings to concise summaries
- **Tone modification** - Adjust voice memo formality/professionalism
- **Edge deployment** - IoT devices, mobile apps, embedded systems

## About NexaAI

NexaAI focuses on on-device AI solutions, developing efficient models and inference frameworks optimized for edge deployment. Their Nexa-SDK provides tools for running AI models locally on consumer hardware without cloud dependencies. OmniAudio represents their entry into the audio multimodal space, emphasizing efficiency and accessibility over raw capability.

## Practical Assessment

**Strengths:**
- Smallest audio multimodal model in this collection (2.6B)
- Runs on consumer hardware without GPU
- Apache 2.0 license allows commercial use
- GGUF quantization for flexible deployment
- Significantly faster than larger alternatives
- True offline capability

**Weaknesses:**
- Smaller model may have reduced capability vs 7B+ models
- Less established than major providers (Alibaba, Microsoft, NVIDIA)
- Limited documentation on audio duration limits
- Newer model with less community validation

**Best suited for:** Edge deployment, mobile applications, IoT devices, and scenarios requiring offline audio processing. Ideal when hardware constraints or latency requirements preclude larger models. The Apache 2.0 license and small footprint make this attractive for commercial embedded applications.

## Links

- [Hugging Face Model](https://huggingface.co/NexaAI/OmniAudio-2.6B)
- [Nexa-SDK GitHub](https://github.com/NexaAI/nexa-sdk)
- [NexaAI](https://nexa.ai/)
