# Step-Audio-R1

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/stepfun-ai/Step-Audio-R1)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black)](https://github.com/stepfun-ai/Step-Audio-R1)
[![Paper](https://img.shields.io/badge/arXiv-2511.15848-b31b1b)](https://arxiv.org/abs/2511.15848)
[![Demo](https://img.shields.io/badge/Demo-Playground-orange)](https://huggingface.co/spaces/stepfun-ai/Step-Audio-R1)

**Developer:** StepFun
**Parameters:** 33B
**License:** Apache 2.0
**Architecture:** Audio Language Model with CoT (BF16)
**Released:** 2025

The first audio language model to successfully unlock Chain-of-Thought (CoT) reasoning. Step-Audio-R1 solves the "inverted scaling" problem where performance previously degraded with longer reasoning in audio models, using their novel Modality-Grounded Reasoning Distillation (MGRD) framework.

## Key Features

- First audio LLM with working Chain-of-Thought reasoning
- Modality-Grounded Reasoning Distillation (MGRD) framework
- Surpasses Gemini 2.5 Pro across audio reasoning benchmarks
- Comparable to Gemini 3 on major audio reasoning tasks
- Multi-domain: speech, environmental sounds, and music
- Audio-grounded reasoning (not textual surrogate reasoning)

## Technical Specifications

| Spec | Value |
|------|-------|
| Parameters | 33B |
| Tensor Type | BF16 |
| Context Length | 16k-64k tokens |
| Max Concurrent Sequences | 32 (Docker) / 128 (Source) |
| GPU Memory Utilization | Up to 85% |
| Tensor Parallel Size | 4 |

**System Requirements:**
- Python >= 3.10.0
- NVIDIA GPUs with CUDA support
- Tested configurations: 4x L40S, 4x H100, 4x H800, 4x H20

**Supported Domains:** Speech, environmental sounds, music

## Deployment Considerations

**Hardware Requirements:**
- Minimum: 4x enterprise GPUs (L40S/H100/H800/H20)
- VRAM: Substantial (~80GB+ per GPU recommended based on tensor parallelism)
- Not suitable for consumer hardware

**Quantization Availability:**
- 2 quantized variants available on Hugging Face Hub
- Safetensors format
- Custom vLLM branch required

**Deployment Options:**
1. **Docker (Recommended)**
   ```bash
   docker pull stepfun2025/vllm:step-audio-2-v20250909
   docker run --rm -ti --gpus all \
       -v $(pwd)/Step-Audio-R1:/Step-Audio-R1 \
       -p 9999:9999 \
       stepfun2025/vllm:step-audio-2-v20250909 \
       -- vllm serve /Step-Audio-R1 \
       --served-model-name Step-Audio-R1 \
       --port 9999 \
       --max-model-len 16384 \
       --tensor-parallel-size 4
   ```

2. **Source Compilation**
   ```bash
   git clone https://github.com/stepfun-ai/vllm.git
   git checkout step-audio-2-mini
   VLLM_USE_PRECOMPILED=1 pip install -e .
   ```

**Model Download:**
```bash
# Git LFS
git lfs install
git clone https://huggingface.co/stepfun-ai/Step-Audio-R1

# Or HF CLI
hf download stepfun-ai/Step-Audio-R1 --local-dir ./Step-Audio-R1
```

## About StepFun

StepFun is a Shanghai-based AI company founded in April 2023 by Jiang Daxin, former chief scientist of Microsoft Research Asia's Software Technology Center (16+ years at Microsoft, PhD in Computer Science from University at Buffalo).

StepFun is one of China's "Six Tigers" - the elite group of AI startups (alongside Moonshot AI, Zhipu, Minimax, 01.AI, and Baichuan) at the forefront of China's AI development. The company has received backing from Tencent, Hongshan (Sequoia China), and Qiming Venture Partners.

Known for pioneering multimodal models in China, StepFun's API demand surged 45x in the second half of 2024. Their Step-1V multimodal model ranks highly on Chatbot Arena for visual understanding. The company emphasizes the "scaling law" approach - betting that bigger models with more data will continue to yield improvements.

Key team members include Dr. Zhou Shuchang (founding team, formerly at Google, Megvii) who combines multimodal models, reinforcement learning, and agent research with industrial deployment.

## Practical Assessment

**Strengths:**
- State-of-the-art audio reasoning (surpasses Gemini 2.5 Pro)
- First working Chain-of-Thought in audio LLMs
- Apache 2.0 license allows commercial use
- Well-documented deployment with Docker support
- Multi-domain coverage (speech, sounds, music)
- Active research with published paper

**Weaknesses:**
- Requires 4x enterprise GPUs (not accessible for most)
- Custom vLLM branch adds deployment complexity
- Supported languages not explicitly documented
- No consumer-grade deployment option
- Newer model with less community tooling

**Best suited for:** Research institutions and enterprises with substantial GPU infrastructure interested in state-of-the-art audio reasoning. The Chain-of-Thought capability represents a significant advancement for complex audio understanding tasks.

## Links

- [Step-Audio-R1 (Hugging Face)](https://huggingface.co/stepfun-ai/Step-Audio-R1)
- [GitHub Repository](https://github.com/stepfun-ai/Step-Audio-R1)
- [Research Paper (arXiv)](https://arxiv.org/abs/2511.15848)
- [Demo Playground](https://huggingface.co/spaces/stepfun-ai/Step-Audio-R1)
- [StepFun](https://www.stepfun.com/)
