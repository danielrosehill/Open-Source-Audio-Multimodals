# Audio Multimodal Providers

*Last updated: December 7, 2025*

This page catalogs organizations developing multimodal models with audio capabilities—both open-source and proprietary. The audio multimodal space spans research labs, cloud providers, and startups.

---

## Open Source / Open Weight

### Mistral AI

**Models:** Voxtral (24B), Voxtral Mini (3B)
**License:** Apache 2.0
**Website:** [mistral.ai](https://mistral.ai)

French AI company known for efficient, high-quality models. Voxtral (July 2025) extends their language model capabilities to native audio understanding with up to 30 minutes of audio context.

### Alibaba (Qwen Team)

**Models:** Qwen2-Audio (7B)
**License:** Qwen License
**Website:** [qwenlm.github.io](https://qwenlm.github.io/)

Chinese tech giant's AI research division. Qwen2-Audio is currently one of the most practical options for local deployment with GGUF quantizations available.

### Microsoft

**Models:** Phi-4-Multimodal-Instruct (~14B)
**License:** MIT
**Website:** [microsoft.com/research](https://www.microsoft.com/en-us/research/)

Phi series focuses on efficient, high-capability small models. Phi-4 multimodal includes audio + vision + text understanding.

### Moonshot AI (Kimi)

**Models:** Kimi-Audio
**License:** TBD
**Website:** [moonshot.cn](https://www.moonshot.cn/)

Chinese AI startup behind the Kimi model family. Kimi-Audio extends their language model with native audio modality support.

### Fixie.ai

**Models:** Ultravox (1B - 27B, multiple backbones)
**License:** Open Source
**Website:** [ultravox.ai](https://ultravox.ai/)

Startup focused on real-time voice AI. Ultravox uses a multimodal projector to convert audio directly into LLM embedding space, optimized for low latency (~150ms TTFT).

### ByteDance

**Models:** SALMONN (7B/13B)
**License:** Research
**Website:** [bytedance.com](https://www.bytedance.com/)

TikTok's parent company. SALMONN (Speech Audio Language Music Open Neural Network) handles diverse audio types.

### StepFun

**Models:** Step-Audio-R1 (33B)
**License:** Apache 2.0
**Website:** [stepfun.com](https://www.stepfun.com/)

Chinese AI company behind Step-Audio-R1, the first audio language model to successfully unlock Chain-of-Thought (CoT) reasoning. Developed the Modality-Grounded Reasoning Distillation (MGRD) framework to solve the "inverted scaling" problem in audio reasoning.

**Key features:**
- First audio LLM with working CoT reasoning
- Surpasses Gemini 2.5 Pro on audio reasoning benchmarks
- Covers speech, environmental sounds, and music
- Docker deployment with vLLM support

**Links:**
- [GitHub](https://github.com/stepfun-ai/Step-Audio-R1)
- [Hugging Face](https://huggingface.co/stepfun-ai/Step-Audio-R1)
- [Paper](https://arxiv.org/abs/2511.15848)

---

## Closed Source / API-Only

### Google

**Models:** Gemini 2.0 Flash, Gemini 2.5 Pro, Gemini 3
**Access:** Google AI Studio, Vertex AI
**Website:** [ai.google.dev](https://ai.google.dev/)

Gemini family has had native audio support since 2.0. Particularly strong for long-form audio (tested with 1-hour recordings). Leading capability in the audio multimodal space.

### OpenAI

**Models:** GPT-4o, GPT-4o Audio Preview
**Access:** OpenAI API
**Website:** [openai.com](https://openai.com/)

GPT-4o introduced native audio understanding with voice mode. Real-time API available for voice applications.

### Anthropic

**Models:** Claude 3.5 Sonnet, Claude 3.5 Opus
**Access:** Anthropic API, Claude.ai
**Website:** [anthropic.com](https://www.anthropic.com/)

Audio support via document/file upload. Strong reasoning capabilities applied to audio content.

### Reka AI

**Models:** Reka Core (67B), Reka Flash (21B), Reka Edge (7B), Reka Spark (2B)
**Access:** API, Enterprise (Nexus, Guardian)
**Website:** [reka.ai](https://reka.ai/)

Multimodal-first AI company. All models trained from scratch on text, code, images, video, and audio with a novel architecture. Full multimodal input support across all model sizes.

**Key features:**
- Native audio, video, and image understanding
- Enterprise platforms (Nexus, Guardian)
- Models range from 2B to 67B parameters
- Core approaches frontier model performance

**Links:**
- [Technical Report](https://publications.reka.ai/reka-core-tech-report.pdf)
- [arXiv Paper](https://arxiv.org/abs/2404.12387)

---

## Research / Emerging

| Organization | Model | Status |
|--------------|-------|--------|
| Fudan University | SpeechGPT | Research |
| CMU | LTU-AS | Research |
| Various | Audio-Flamingo | Research |

---

## Provider Comparison

| Provider | Open Source | Audio Native | Enterprise | Edge Deploy |
|----------|-------------|--------------|------------|-------------|
| Mistral AI | Yes | Yes | Yes | Yes (Mini) |
| Alibaba | Yes | Yes | Yes | Yes (GGUF) |
| Microsoft | Yes | Yes | Yes | Yes |
| Fixie.ai | Yes | Yes | Yes | Yes |
| StepFun | Yes | Yes | Yes | No |
| Google | No | Yes | Yes | No |
| OpenAI | No | Yes | Yes | No |
| Reka AI | No | Yes | Yes | Yes (Edge) |

---

*This list covers major providers as of December 2025. The space is evolving rapidly with new entrants and model releases.*
