# Step-Audio-R1

**Developer:** StepFun
**Parameters:** 33B
**License:** Apache 2.0

The first audio language model to successfully unlock Chain-of-Thought (CoT) reasoning. Step-Audio-R1 solves the "inverted scaling" problem where performance previously degraded with longer reasoning in audio models.

## Key Features

- First audio LLM with working Chain-of-Thought reasoning
- Modality-Grounded Reasoning Distillation (MGRD) framework
- Surpasses Gemini 2.5 Pro across audio reasoning benchmarks
- Comparable to Gemini 3 on major audio reasoning tasks
- Covers speech, environmental sounds, and music domains
- 16k-64k token context length

## Technical Requirements

- NVIDIA GPUs with CUDA (tested on 4×L40S/H100/H800/H20)
- Docker deployment recommended
- vLLM support via custom branch

## Links

- [Paper](https://arxiv.org/abs/2511.15848)
- [GitHub](https://github.com/stepfun-ai/Step-Audio-R1)
- [Hugging Face](https://huggingface.co/stepfun-ai/Step-Audio-R1)
- [Playground](https://huggingface.co/spaces/stepfun-ai/Step-Audio-R1)
