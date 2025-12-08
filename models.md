# Featured Audio Multimodal Models

*Last updated: December 7, 2025*

This page highlights the most notable open-source and open-weight multimodal models with native audio support. These models process audio tokens directly alongside text prompts, enabling prompt-guided transcription, analysis, and formatting in a single inference pass.

---

## Open Source Models

| Model | Developer | Parameters | License | Profile |
|-------|-----------|------------|---------|---------|
| Voxtral | Mistral AI | 3B / 24B | Apache 2.0 | [Details](models/audio-multimodal/voxtral.md) |
| Qwen2-Audio | Alibaba | 7B | Qwen License | [Details](models/audio-multimodal/qwen2-audio.md) |
| Kimi-Audio | Moonshot AI | TBD | TBD | [Details](models/audio-multimodal/kimi-audio.md) |
| Phi-4-Multimodal | Microsoft | ~14B | MIT | [Details](models/audio-multimodal/phi-4-multimodal.md) |
| Ultravox | Fixie.ai | 1B - 27B | Open Source | [Details](models/audio-multimodal/ultravox.md) |
| Step-Audio-R1 | StepFun | 33B | Apache 2.0 | [Details](models/audio-multimodal/step-audio-r1.md) |
| SALMONN | ByteDance/Tsinghua | 7B / 13B | Apache 2.0 | [Details](models/audio-multimodal/salmonn.md) |
| BuboGPT | ByteDance | 7B / 13B | BSD 3-Clause | [Details](models/audio-multimodal/bubogpt.md) |

---

## Individual Model Profiles

- [Voxtral](models/audio-multimodal/voxtral.md) - Mistral's frontier speech understanding models
- [Qwen2-Audio](models/audio-multimodal/qwen2-audio.md) - Practical option for local deployment with GGUF
- [Kimi-Audio](models/audio-multimodal/kimi-audio.md) - Moonshot AI's audio multimodal
- [Phi-4-Multimodal](models/audio-multimodal/phi-4-multimodal.md) - Microsoft's efficient multimodal
- [Ultravox](models/audio-multimodal/ultravox.md) - Real-time voice AI optimized for low latency
- [Step-Audio-R1](models/audio-multimodal/step-audio-r1.md) - First audio LLM with Chain-of-Thought reasoning
- [SALMONN](models/audio-multimodal/salmonn.md) - Pioneer audio multimodal from ByteDance/Tsinghua
- [BuboGPT](models/audio-multimodal/bubogpt.md) - Audio-visual multimodal with SAM grounding

---

## Closed Source / API-Only

For completeness, here are the leading proprietary audio multimodal models available via API.

### Google Gemini

**Models:** Gemini 2.0 Flash, Gemini 2.5 Pro, Gemini 3
**Access:** Google AI Studio, Vertex AI

Google's Gemini family has had native audio support since 2.0. Particularly strong for long-form audio processing—tested successfully with 1-hour recordings. Gemini 3 (December 2025) represents the latest iteration.

**Key features:**
- Native audio token processing
- Long-context audio support
- Prompt-guided transcription and analysis
- Integrated with Google Cloud ecosystem

### OpenAI

**Models:** GPT-4o, GPT-4o Audio Preview
**Access:** OpenAI API

GPT-4o introduced native audio understanding with voice mode. The Audio Preview variant provides direct audio token processing for developers.

**Key features:**
- Audio input/output capabilities
- Voice mode for conversational AI
- Integration with OpenAI ecosystem
- Real-time API for voice applications

---

## Selection Considerations

**For local deployment on consumer hardware:**
- Qwen2-Audio-7B-Instruct with GGUF quantization is currently the most practical option
- Voxtral Mini (3B) designed specifically for edge deployment

**For maximum capability:**
- Voxtral (24B) for frontier performance
- Step-Audio-R1 (33B) for advanced reasoning tasks

**For real-time voice agents:**
- Ultravox optimized for low latency (~150ms TTFT)

**For audio reasoning:**
- Step-Audio-R1 with Chain-of-Thought capabilities

**For Mistral ecosystem integration:**
- Voxtral provides native compatibility with Mistral tooling

---

## Other Notable Models

See [ask-ai/outputs/models.md](ask-ai/outputs/models.md) for a comprehensive list including:
- SpeechGPT
- Audio-Flamingo
- And more research/emerging models

---

## Resources

- [Awesome-Audio-LLM](https://github.com/AudioLLMs/Awesome-Audio-LLM) - Curated list of audio LLM research and models
- [Hugging Face audio-text-to-text models](https://huggingface.co/models?pipeline_tag=audio-text-to-text&sort=downloads) - Browse latest models

---

*This list focuses on production-ready or near-production models. The field evolves rapidly.*
