# Ultravox

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/fixie-ai)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/fixie-ai/ultravox)
[![Website](https://img.shields.io/badge/Website-Ultravox-purple)](https://ultravox.ai/)
[![Docs](https://img.shields.io/badge/Docs-API-green)](https://docs.ultravox.ai/)

**Developer:** Fixie.ai
**Parameters:** 8B - 70B (depending on backbone)
**License:** MIT
**Architecture:** Multimodal Speech LLM (BF16)
**Current Version:** v0.6 (August 2025)

A multimodal Speech LLM that processes audio directly without a separate ASR stage. Uses a multimodal projector to convert audio directly into LLM embedding space, enabling significantly faster response times (~150ms time-to-first-token) than traditional ASR+LLM pipelines.

## Key Features

- Direct audio-to-LLM processing without ASR intermediary
- Multiple backbone options: Llama 3.3, Gemma 3, Qwen 3
- ~150ms time-to-first-token on A100 GPU
- Real-time voice agent capabilities
- Speech-to-speech translation support
- 42+ language support
- Noise robustness with special `((noise))` token detection

## Technical Specifications

| Spec | 8B Variant | 70B Variant |
|------|------------|-------------|
| Parameters | 8B | 70B |
| Backbone | Llama 3.3-8B | Llama 3.3-70B |
| Audio Encoder | Whisper-large-v3-turbo | Whisper-large-v3-turbo |
| Tensor Type | BF16 | BF16 |
| Recommended Sample Rate | 16kHz | 16kHz |
| VRAM Required | ~16GB | ~140GB+ |

**Training Specifications:**
- Hardware: 8x H100 GPUs
- Duration: 2-3 hours for v0.4 (14K steps)
- Method: Supervised speech instruction finetuning via knowledge-distillation
- Only adapter is trained; LLM and encoder remain frozen

**Supported Languages:** 42+ languages including improved Hindi support in v0.6

## Deployment Considerations

**Hardware Requirements:**
- 8B variant: Consumer/prosumer GPU (~16GB VRAM)
- 70B variant: Enterprise GPU cluster (~140GB+ VRAM)
- Training: 8x H100 GPUs

**Quantization Availability:**
- 1 quantized variant available for 70B model
- Safetensors format

**Deployment Options:**
1. **Managed API** - docs.ultravox.ai (easiest)
2. **BaseTen** - On-demand inference partnership
3. **Local** - Poetry/PyTorch with Hugging Face weights
4. **vLLM** - Community-supported server deployment

**Available Backbones:**
- `ultravox-v0_6-llama-3_3-70b` - Flagship model
- `ultravox-v0_6-llama-3_3-8b` - Efficient variant
- `ultravox-v0_6-gemma-3-4b` - Small model option
- `ultravox-v0_6-qwen-3-8b` - Qwen backbone variant

**Usage Example:**
```python
import transformers
import librosa

pipe = transformers.pipeline(
    model='fixie-ai/ultravox-v0_6-llama-3_3-70b',
    trust_remote_code=True
)

audio, sr = librosa.load("<path-to-audio>", sr=16000)
turns = [{"role": "system", "content": "You are a friendly assistant."}]
result = pipe({'audio': audio, 'turns': turns, 'sampling_rate': sr}, max_new_tokens=30)
```

## About Fixie.ai

Fixie.ai is a Seattle-based AI startup founded in 2022 by former Google, Apple, and OctoML engineering leaders:

- **Matt Welsh (CEO)** - Former engineering leader at OctoML, principal engineer at Google, and briefly at Apple (via Xnor.ai acquisition)
- **Justin Uberti (CTO)** - 14+ years at Google (Duo, Stadia), original architect of AOL Instant Messenger
- **Zach Koch (CPO)** - Former director of product at Shopify, led Chrome and Pixel teams at Google
- **Hessam Bagherinezhad (Chief AI Officer)** - Head of ML at Xnor.ai, ML engineer at Apple

The company raised $17M in seed funding (March 2023) led by Redpoint Ventures with participation from Madrona, Zetta, SignalFire, and Bloomberg Beta. Featured in Business Insider's "Top 44 Generative AI startups."

Their initial focus was on LLM infrastructure and natural language agents, with Ultravox representing their move into multimodal voice AI.

## Practical Assessment

**Strengths:**
- Fastest time-to-first-token (~150ms) among open models
- Multiple backbone options for different resource constraints
- MIT license maximizes flexibility
- Active development with regular releases
- Strong team pedigree (Google, Apple veterans)
- Managed API available for quick prototyping

**Weaknesses:**
- 70B model requires significant hardware
- Audio duration limits not documented
- Training requires substantial GPU resources (8x H100)
- Less mature ecosystem than Qwen2-Audio
- Primarily focused on real-time applications

**Best suited for:** Real-time voice agent applications where latency is critical. The ~150ms TTFT makes this ideal for conversational AI, voice assistants, and interactive applications. The 8B variant offers a good balance of capability and deployability.

## Links

- [Ultravox Collection (Hugging Face)](https://huggingface.co/fixie-ai)
- [GitHub Repository](https://github.com/fixie-ai/ultravox)
- [Website](https://ultravox.ai/)
- [API Documentation](https://docs.ultravox.ai/)
