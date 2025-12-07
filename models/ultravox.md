# Ultravox

**Developer:** Fixie.ai
**Variants:** Multiple backbones (Llama 3.3, Gemma 3, Qwen 3)
**Parameters:** 1B - 27B (depending on backbone)
**License:** Open source

A multimodal Speech LLM that understands speech directly without a separate ASR stage. Uses a multimodal projector to convert audio directly into LLM embedding space, enabling significantly faster response times than traditional ASR+LLM pipelines.

## Key Features

- ~150ms time-to-first-token on A100 GPU
- Multiple backbone options (Llama, Gemma, Qwen)
- Built on Whisper Large V3 Turbo audio encoder (fine-tuned)
- Real-time voice agent capabilities
- Speech-to-speech translation support

## Latest (v0.6)

- Improved Hindi language understanding
- Better background noise and audio quality robustness
- New Gemma 3 and Qwen 3 variants

## Links

- [Website](https://ultravox.ai/)
- [GitHub](https://github.com/fixie-ai/ultravox)
- [Hugging Face](https://huggingface.co/fixie-ai)
