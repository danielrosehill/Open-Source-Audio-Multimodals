# Kimi-Audio

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/moonshotai/Kimi-Audio-7B-Instruct)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/MoonshotAI/Kimi-Audio)

**Developer:** Moonshot AI
**Parameters:** 10B
**License:** MIT / Apache 2.0 (dual)
**Architecture:** Hybrid Audio LLM (BF16)
**Base Model:** Modified Qwen 2.5-7B
**Released:** 2024

Kimi-Audio extends Moonshot AI's Kimi model family with native audio modality support. Features a unique hybrid architecture combining continuous acoustic features with discrete semantic tokens, enabling both audio understanding and generation in a single model.

## Key Features

- Hybrid audio input: continuous acoustic vectors + discrete semantic tokens
- End-to-end speech conversation capability
- Audio generation with streaming output (chunk-wise detokenizer)
- Multi-domain audio understanding: speech, music, and sounds
- Speech emotion recognition
- Audio captioning and question answering

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 10B |
| Base Model | Qwen 2.5-7B (modified) |
| Tensor Type | BF16 |
| Training Data | 13+ million hours |
| Output Sample Rate | 24kHz |
| Audio Duration Limits | Not documented |
| VRAM Required | Not documented (estimate ~20GB+) |

**Supported Languages:** English, Chinese

## Deployment Considerations

**Hardware Requirements:**
- CUDA-capable GPU recommended
- Docker deployment recommended for optimal environment setup
- Exact VRAM requirements not documented

**Quantization Availability:**
- No quantized variants currently available
- Full precision deployment only

**Deployment Options:**
1. **Docker** - `moonshotai/kimi-audio:v0.1` (recommended)
2. **pip install** - Direct from GitHub repository
3. **Manual** - Requirements file installation

**Model Variants:**
- `Kimi-Audio-7B` - Base model
- `Kimi-Audio-7B-Instruct` - Instruction-tuned variant

**Usage Example:**
```python
from kimia_infer.api.kimia import KimiAudio

model = KimiAudio(
    model_path="moonshotai/Kimi-Audio-7B-Instruct",
    load_detokenizer=True
)
messages = [{"role": "user", "message_type": "audio", "content": "audio.wav"}]
wav_output, text_output = model.generate(messages, output_type="both")
```

## About Moonshot AI

Moonshot AI (Kimi) is a Beijing-based AI company founded in 2023 by Yang Zhilin, previously a researcher at Google Brain and co-founder of Recurrent AI. The company is known for its Kimi chatbot, which gained significant traction in China for its long-context capabilities.

Moonshot AI is considered one of China's "Six Tigers" - the elite group of AI startups (alongside StepFun, Zhipu, Minimax, 01.AI, and Baichuan) leading the country's AI development. The company has raised substantial funding and is valued at several billion dollars.

Their Kimi-Audio release represents an expansion of the Kimi ecosystem from text-focused models into multimodal audio capabilities.

## Practical Assessment

**Strengths:**
- Unique hybrid architecture (continuous + discrete audio representation)
- Audio generation capability (not just understanding)
- Large training dataset (13M+ hours)
- MIT license option for maximum flexibility
- Docker deployment simplifies environment setup

**Weaknesses:**
- Limited documentation on deployment requirements
- No quantized variants for consumer hardware
- Only English/Chinese language support
- Less community tooling than Qwen2-Audio
- Audio duration limits not documented

**Best suited for:** Researchers interested in hybrid audio architectures and developers needing both audio understanding and generation. The audio output capability differentiates it from understanding-only models.

## Links

- [Kimi-Audio-7B-Instruct (Hugging Face)](https://huggingface.co/moonshotai/Kimi-Audio-7B-Instruct)
- [GitHub Repository](https://github.com/MoonshotAI/Kimi-Audio)
- [Moonshot AI](https://www.moonshot.cn/)
