# Step-Audio-Chat

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/stepfun-ai/Step-Audio-Chat)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/stepfun-ai/Step-Audio)
[![Dataset](https://img.shields.io/badge/Dataset-StepEval--Audio--360-blue)](https://huggingface.co/datasets/stepfun-ai/StepEval-Audio-360)

**Developer:** StepFun
**Parameters:** 130B
**License:** Apache 2.0
**Architecture:** Multimodal LLM (BF16)

Step-Audio-Chat is the flagship conversational component of StepFun's Step-Audio system, a 130B parameter multimodal LLM designed for comprehensive speech understanding and generation. It integrates speech recognition, semantic understanding, dialogue management, voice cloning, and speech generation into a single unified model.

## Key Features

- Full speech-to-speech conversation capability
- Voice cloning and speaker characteristic replication
- Multi-turn dialogue management
- Audio instruction following
- Role-playing and persona adoption
- Singing and RAP generation
- Strong multilingual instruction following

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 130B (132B) |
| Tensor Type | BF16 |
| Task Type | Audio-Text-to-Text |
| Format | Safetensors |

**Capabilities:**
- Speech recognition (audio → text)
- Semantic understanding
- Dialogue management
- Voice cloning
- Speech generation (text → speech)
- Audio instruction following

## Benchmark Performance

Results on StepEval-Audio-360:

| Metric | Score |
|--------|-------|
| Factuality | 66.4% |
| Relevance | 75.2% |
| Chat Score | 4.11 |
| Instruction Following | 3.8 |
| Voice Control | 4.4 |
| Audio Quality | 4.1 |

Outperforms GLM4-Voice, Qwen2-Audio, and Moshi across various benchmarks.

## Step-Audio Model Family

Step-Audio-Chat is part of StepFun's broader Step-Audio ecosystem:

| Model | Parameters | Focus |
|-------|------------|-------|
| **Step-Audio-Chat** | 130B | Conversational AI, voice cloning, speech generation |
| **Step-Audio-R1** | 33B | Chain-of-Thought reasoning, audio understanding |

## Deployment Considerations

**Hardware Requirements:**
- Enterprise-grade GPU cluster required
- 130B parameters requires substantial VRAM (likely 8x H100 or equivalent)
- Not suitable for consumer hardware

**Deployment:**
- Refer to [Step-Audio GitHub](https://github.com/stepfun-ai/Step-Audio) for deployment instructions
- Custom inference setup likely required for full speech-to-speech pipeline

## About StepFun

StepFun is a Shanghai-based AI company founded in April 2023 by Jiang Daxin, former chief scientist of Microsoft Research Asia's Software Technology Center. One of China's "Six Tigers" elite AI startups, StepFun has received backing from Tencent, Hongshan (Sequoia China), and Qiming Venture Partners.

The company is known for pioneering multimodal models in China, with API demand surging 45x in the second half of 2024. Their emphasis on the "scaling law" approach is evident in the 130B parameter Step-Audio-Chat model.

## Practical Assessment

**Strengths:**
- Largest open-source audio multimodal model (130B parameters)
- Full speech-to-speech capability in single model
- Voice cloning and speaker replication
- Apache 2.0 license allows commercial use
- Strong benchmark performance vs competitors
- Comprehensive audio pipeline (recognition → understanding → generation)

**Weaknesses:**
- Massive hardware requirements (enterprise GPU cluster)
- 130B size limits accessibility significantly
- Complex deployment for full speech pipeline
- Less documentation than smaller models
- Primarily focused on Chinese language optimization

**Best suited for:** Enterprises and research institutions with substantial compute resources seeking comprehensive speech-to-speech conversational AI. The voice cloning and speech generation capabilities make this ideal for advanced voice assistant applications, but the 130B size restricts deployment to well-resourced organizations.

## Links

- [Step-Audio-Chat (Hugging Face)](https://huggingface.co/stepfun-ai/Step-Audio-Chat)
- [Step-Audio GitHub](https://github.com/stepfun-ai/Step-Audio)
- [StepEval-Audio-360 Dataset](https://huggingface.co/datasets/stepfun-ai/StepEval-Audio-360)
- [Step-Audio Collection](https://huggingface.co/collections/stepfun-ai/step-audio)
- [StepFun](https://www.stepfun.com/)
