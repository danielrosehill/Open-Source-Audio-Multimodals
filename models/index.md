# Audio Multimodal Models Index

Open-source models that process audio tokens natively alongside text prompts, enabling unified inference for transcription, analysis, and understanding.

## Any-to-Any Models (Omni-Modal)

[![Any-to-Any](https://img.shields.io/badge/%F0%9F%A4%97%20Task-any--to--any-purple)](https://huggingface.co/models?pipeline_tag=any-to-any)

Models classified under Hugging Face's "any-to-any" task naturally include audio as part of their broader multimodal capabilities. These accept multiple input modalities (text, image, audio, video) and can generate multiple output types including speech.

| Model | Developer | Parameters | License | Notes |
|-------|-----------|------------|---------|-------|
| [Gemma-3n](omnimodality/gemma-3n.md) | Google DeepMind | 2B-4B | Gemma License | On-device multimodal, AudioLM speech, mobile-optimized |
| [Macaw-LLM](omnimodality/macaw-llm.md) | Chenyang Lyu et al. | 7B-13B | Apache 2.0 | Pioneer omni-modal (2023), CLIP+Whisper+LLaMA, one-stage training |
| [Qwen Omni](omnimodality/qwen-omni.md) | Alibaba | 7B-35B | Apache 2.0 | True omni-modal (text+image+audio+video in, text+speech out), Gemini 2.5 Pro parity |

## Audio-Text-to-Text Models

[![Audio-Text-to-Text](https://img.shields.io/badge/%F0%9F%A4%97%20Task-audio--text--to--text-blue)](https://huggingface.co/models?pipeline_tag=audio-text-to-text)

Models focused specifically on audio understanding with text output—the core "audio multimodal" category.

| Model | Developer | Parameters | License | Notes |
|-------|-----------|------------|---------|-------|
| [Audio Flamingo 3](audio-multimodal/audio-flamingo-3.md) | NVIDIA | 8B | Non-commercial | 10-min audio, Chain-of-Thought reasoning, voice-to-voice variant |
| [BuboGPT](audio-multimodal/bubogpt.md) | ByteDance | 7B-13B | BSD 3-Clause | Audio-visual with SAM grounding, sound localization |
| [Kimi-Audio](audio-multimodal/kimi-audio.md) | Moonshot AI | 10B | MIT/Apache 2.0 | Hybrid architecture with audio generation, 13M+ hours training data |
| [OmniAudio](audio-multimodal/omniaudio.md) | NexaAI | 2.6B | Apache 2.0 | Compact on-device, GGUF quantized, 5-10x faster than Qwen2-Audio |
| [Phi-4-Multimodal](audio-multimodal/phi-4-multimodal.md) | Microsoft | 5.6B | MIT | Tri-modal (audio+vision+text), #1 OpenASR Leaderboard, 30-min summarization |
| [Qwen2-Audio](audio-multimodal/qwen2-audio.md) | Alibaba | 8B | Apache 2.0 | Most mature ecosystem, GGUF available, llama.cpp support |
| [SALMONN](audio-multimodal/salmonn.md) | ByteDance/Tsinghua | 7B-13B | Apache 2.0 | Pioneer audio multimodal, dual encoder (Whisper+BEATs), video variants |
| [Soundwave](audio-multimodal/soundwave.md) | FreedomIntelligence | 9B | Apache 2.0 | Data-efficient (10k hours), outperforms Qwen2-Audio on benchmarks |
| [Step-Audio-Chat](audio-multimodal/step-audio-chat.md) | StepFun | 130B | Apache 2.0 | Full speech-to-speech, voice cloning, largest open-source audio LLM |
| [Step-Audio-R1](audio-multimodal/step-audio-r1.md) | StepFun | 33B | Apache 2.0 | First audio LLM with Chain-of-Thought, surpasses Gemini 2.5 Pro |
| [Ultravox](audio-multimodal/ultravox.md) | Fixie.ai | 8B-70B | MIT | ~150ms TTFT, multiple backbones (Llama, Gemma, Qwen), 42+ languages |
| [Voxtral](audio-multimodal/voxtral.md) | Mistral AI | 5B-24B | Apache 2.0 | 30-40 min audio, function calling, 7 quantized variants |
