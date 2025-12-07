# Phi-4-Multimodal-Instruct

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/microsoft/Phi-4-multimodal-instruct)
[![Website](https://img.shields.io/badge/Website-Microsoft-blue)](https://azure.microsoft.com/en-us/products/phi)

**Developer:** Microsoft
**Parameters:** 5.6B
**License:** MIT
**Architecture:** Multimodal Transformer (BF16)
**Released:** February 2025

Microsoft's Phi-4 multimodal variant continues the Phi series' focus on efficient, high-capability small models. Notably the first open-source model with speech summarization capability, achieving #1 ranking on the Hugging Face OpenASR Leaderboard with 6.14% WER.

## Key Features

- Tri-modal: Audio + Vision + Text in single model
- First open-source speech summarization capability
- Strong instruction-following across all modalities
- 128K token context length
- Outperforms Whisper V3 on speech recognition
- Exceeds SeamlessM4T-v2-Large on speech translation

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 5.6B |
| Backbone | Phi-4-Mini-Instruct |
| Tensor Type | BF16 |
| Context Length | 128K tokens |
| Vocabulary Size | 200,064 tokens |
| Max Audio (Standard) | 40 seconds |
| Max Audio (Summarization) | 30 minutes |

**Training Data:**
- Text: 5 trillion tokens
- Audio: 2.3 million speech hours
- Vision: 1.1 trillion image-text tokens
- Training: 28 days on 512 A100-80G GPUs

**Supported Languages:**

| Modality | Languages |
|----------|-----------|
| Text | 23 languages (Arabic, Chinese, Czech, Danish, Dutch, English, Finnish, French, German, Hebrew, Hungarian, Italian, Japanese, Korean, Norwegian, Polish, Portuguese, Russian, Spanish, Swedish, Thai, Turkish, Ukrainian) |
| Audio | 8 languages (English, Chinese, German, French, Italian, Japanese, Spanish, Portuguese) |
| Vision | English |

## Deployment Considerations

**Hardware Requirements:**
- Tested on: NVIDIA A100, A6000, H100
- For V100 or earlier: Use `_attn_implementation="eager"` instead of flash_attention_2
- VRAM: ~12GB minimum (estimate based on parameter count)

**Quantization Availability:**
- 3 quantized variants available on Hugging Face
- Safetensors format

**Deployment Options:**
1. **Transformers** - With flash_attention_2 support
2. **vLLM** - OpenAI-compatible server deployment
3. **Azure AI Studio** - Managed deployment
4. **GitHub Marketplace** - Pre-configured instances

**Required Dependencies:**
```
flash_attn==2.7.4.post1
torch==2.6.0
transformers==4.48.2
accelerate==1.3.0
soundfile==0.13.1
```

**Input Format Examples:**
```
# Audio task
<|user|><|audio_1|>Transcribe the audio clip into text.<|end|><|assistant|>

# Combined vision + audio
<|user|><|image_1|><|audio_1|><|end|><|assistant|>
```

## About Microsoft Phi Team

The Phi series is developed by Microsoft Research, focusing on the principle that smaller, well-trained models can match or exceed larger models on specific tasks. The team has demonstrated that careful data curation and training methodology can produce highly efficient models.

Previous releases include Phi-1 (1.3B), Phi-2 (2.7B), and Phi-3, each pushing the boundaries of what small models can achieve. The Phi-4 multimodal variant represents their first foray into unified multimodal capabilities.

Microsoft's approach emphasizes practical deployment scenarios, with MIT licensing enabling broad commercial adoption and integration into existing Microsoft infrastructure (Azure, GitHub).

## Practical Assessment

**Strengths:**
- Excellent efficiency: 5.6B parameters with tri-modal capability
- MIT license maximizes commercial flexibility
- Strong benchmark performance (#1 OpenASR Leaderboard)
- Long audio summarization support (30 minutes)
- 128K context enables complex multi-turn interactions
- Well-documented with clear deployment guides

**Weaknesses:**
- Vision limited to English only
- Audio limited to 8 languages (vs 23 for text)
- 40-second limit for non-summarization audio tasks
- Requires specific dependency versions
- Less community tooling than Qwen2-Audio

**Best suited for:** Production deployments needing efficient tri-modal capability with commercial-friendly licensing. Particularly strong for speech summarization use cases and integration with Microsoft/Azure infrastructure.

## Links

- [Phi-4-multimodal-instruct (Hugging Face)](https://huggingface.co/microsoft/Phi-4-multimodal-instruct)
- [Microsoft Phi Product Page](https://azure.microsoft.com/en-us/products/phi)
- [Azure AI Studio](https://ai.azure.com/)
