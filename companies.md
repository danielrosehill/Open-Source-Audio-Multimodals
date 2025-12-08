# Companies Developing Audio Multimodal Models

*Last updated: December 8, 2025*

Organizations developing the audio multimodal and omni-modal models cataloged in this repository.

---

## Alibaba (Qwen Team)

Chinese tech giant's AI research division, responsible for the Qwen model family.

**Models:**
- [Qwen Omni](models/omnimodality/qwen-omni.md)  True omni-modal (7B-35B), text+image+audio+video in, text+speech out
- [Qwen2-Audio](models/audio-multimodal/qwen2-audio.md)  Audio-text-to-text (8B), mature ecosystem with GGUF/llama.cpp support

**License:** Apache 2.0
**Website:** [qwenlm.github.io](https://qwenlm.github.io/)

---

## ByteDance

TikTok's parent company, active in audio and multimodal AI research.

**Models:**
- [BuboGPT](models/audio-multimodal/bubogpt.md)  Audio-visual with SAM grounding (7B-13B), sound localization
- [SALMONN](models/audio-multimodal/salmonn.md)  Pioneer audio multimodal (7B-13B), dual encoder (Whisper+BEATs), developed with Tsinghua University

**License:** BSD 3-Clause / Apache 2.0
**Website:** [bytedance.com](https://www.bytedance.com/)

---

## Fixie.ai

Startup focused on real-time voice AI with low-latency audio understanding.

**Models:**
- [Ultravox](models/audio-multimodal/ultravox.md)  Audio-text-to-text (8B-70B), ~150ms TTFT, multiple backbones (Llama, Gemma, Qwen), 42+ languages

**License:** MIT
**Website:** [ultravox.ai](https://ultravox.ai/)

---

## FreedomIntelligence

Research group focused on data-efficient audio multimodal training.

**Models:**
- [Soundwave](models/audio-multimodal/soundwave.md)  Audio-text-to-text (9B), data-efficient (10k hours), outperforms Qwen2-Audio on benchmarks

**License:** Apache 2.0

---

## Google DeepMind

Leading AI research lab, developer of Gemini and Gemma model families.

**Models:**
- [Gemma-3n](models/omnimodality/gemma-3n.md)  On-device omni-modal (2B-4B effective), AudioLM speech, mobile-optimized

**License:** Gemma License
**Website:** [deepmind.google](https://deepmind.google/)

---

## Microsoft

Software giant with significant AI research investments in efficient multimodal models.

**Models:**
- [Phi-4-Multimodal](models/audio-multimodal/phi-4-multimodal.md)  Tri-modal audio+vision+text (5.6B), #1 OpenASR Leaderboard, 30-min summarization

**License:** MIT
**Website:** [microsoft.com/research](https://www.microsoft.com/en-us/research/)

---

## Mistral AI

French AI company known for efficient, high-quality open-weight models.

**Models:**
- [Voxtral](models/audio-multimodal/voxtral.md)  Audio-text-to-text (5B-24B), 30-40 min audio context, function calling, 7 quantized variants

**License:** Apache 2.0
**Website:** [mistral.ai](https://mistral.ai)

---

## Moonshot AI

Chinese AI startup behind the Kimi model family.

**Models:**
- [Kimi-Audio](models/audio-multimodal/kimi-audio.md)  Audio-text-to-text (10B), hybrid architecture with audio generation, 13M+ hours training data

**License:** MIT / Apache 2.0
**Website:** [moonshot.cn](https://www.moonshot.cn/)

---

## NexaAI

Company focused on compact, on-device audio multimodal models.

**Models:**
- [OmniAudio](models/audio-multimodal/omniaudio.md)  Compact audio-text-to-text (2.6B), GGUF quantized, 5-10x faster than Qwen2-Audio

**License:** Apache 2.0

---

## NVIDIA

Graphics and AI computing company with significant audio/multimodal research.

**Models:**
- [Audio Flamingo 3](models/audio-multimodal/audio-flamingo-3.md)  Audio-text-to-text (8B), 10-min audio context, Chain-of-Thought reasoning, voice-to-voice variant

**License:** Non-commercial
**Website:** [nvidia.com/research](https://www.nvidia.com/en-us/research/)

---

## StepFun

Chinese AI company pioneering Chain-of-Thought reasoning in audio models.

**Models:**
- [Step-Audio-Chat](models/audio-multimodal/step-audio-chat.md)  Full speech-to-speech (130B), voice cloning, largest open-source audio LLM
- [Step-Audio-R1](models/audio-multimodal/step-audio-r1.md)  First audio LLM with Chain-of-Thought (33B), surpasses Gemini 2.5 Pro on audio reasoning

**License:** Apache 2.0
**Website:** [stepfun.com](https://www.stepfun.com/)

---

## Academic / Research Groups

### Chenyang Lyu et al.

Research collaboration that developed one of the pioneering omni-modal models.

**Models:**
- [Macaw-LLM](models/omnimodality/macaw-llm.md)  Pioneer omni-modal (7B-13B), CLIP+Whisper+LLaMA, one-stage training

**License:** Apache 2.0

### Tsinghua University

Co-developer with ByteDance on audio multimodal research.

**Models:**
- [SALMONN](models/audio-multimodal/salmonn.md)  (co-developed with ByteDance)

---

## Summary by Model Count

| Company | Models | Focus Area |
|---------|--------|------------|
| Alibaba | 2 | Omni-modal + Audio understanding |
| ByteDance | 2 | Audio-visual, pioneer research |
| StepFun | 2 | Large-scale, CoT reasoning |
| Fixie.ai | 1 | Real-time voice AI |
| FreedomIntelligence | 1 | Data-efficient training |
| Google DeepMind | 1 | On-device omni-modal |
| Microsoft | 1 | Efficient tri-modal |
| Mistral AI | 1 | Long-form audio |
| Moonshot AI | 1 | Hybrid audio understanding/generation |
| NexaAI | 1 | Compact on-device |
| NVIDIA | 1 | Research, reasoning |

---

*See [providers.md](providers.md) for additional context on closed-source providers (Google Gemini, OpenAI GPT-4o, Anthropic Claude, Reka AI) not covered here.*
