# Gemma 3n

[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-Hugging%20Face-yellow)](https://huggingface.co/google/gemma-3n-E2B)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97-E4B%20Variant-yellow)](https://huggingface.co/google/gemma-3n-E4B)
[![Any-to-Any](https://img.shields.io/badge/%F0%9F%A4%97%20Task-any--to--any-purple)](https://huggingface.co/models?pipeline_tag=any-to-any)

**Developer:** Google DeepMind
**Parameters:** 6B raw / 2B effective (E2B) or 8B raw / 4B effective (E4B)
**License:** Gemma
**Architecture:** MatFormer with selective parameter activation
**Knowledge Cutoff:** June 2024

Gemma 3n is Google's efficient multimodal model series designed for on-device deployment. Using the innovative MatFormer architecture with selective parameter activation, Gemma 3n achieves the memory footprint of a 2B model while maintaining 6B raw parameters. It supports text, images, audio, and video inputs with a 32K context window.

## Model Variants

| Model | Raw Params | Effective Params | Memory Footprint |
|-------|------------|------------------|------------------|
| **Gemma-3n-E2B** | 6B | ~2B | ~2B equivalent |
| **Gemma-3n-E4B** | 8B | ~4B | ~4B equivalent |

## Key Features

- **MatFormer Architecture**: Nested sub-models enable selective parameter activation
- **Efficient deployment**: 6B model runs with 2B memory footprint
- **Full multimodal**: Text, images, audio, and video support
- **Audio processing**: Single channel at 6.25 tokens per second
- **140+ language support** for spoken languages
- **32K context window** for input and output
- **On-device optimized**: Designed for low-resource execution

## Technical Specifications

| Spec | Value |
|------|-------|
| Raw Parameters | 6B (E2B) / 8B (E4B) |
| Effective Parameters | ~2B (E2B) / ~4B (E4B) |
| Tensor Type | BF16 |
| Context Window | 32K tokens |
| Audio Encoding | 6.25 tokens/second (mono) |
| Image Resolution | 256×256, 512×512, or 768×768 |
| Image Tokens | 256 per image |
| Training Data | ~11 trillion tokens |
| Language Support | 140+ languages |

## Benchmark Performance (E2B Instruction-Tuned)

| Benchmark | Score |
|-----------|-------|
| MMLU | 60.1% |
| HumanEval | 66.5% (pass@1) |
| MBPP | 56.6% (pass@1) |
| HellaSwag (10-shot) | 72.2% |

## Deployment Considerations

**Hardware Requirements:**
- Designed for edge/mobile deployment
- E2B runs with ~2B model memory footprint
- CPU inference possible for lighter workloads
- GPU recommended for audio/video processing

**Software Requirements:**
- Transformers >= 4.53.0

**Basic Usage:**
```python
from transformers import pipeline
import torch

pipe = pipeline(
    "image-text-to-text",
    model="google/gemma-3n-e2b",
    device="cuda",
    torch_dtype=torch.bfloat16,
)

output = pipe(
    "https://example.com/image.jpg",
    text="<image_soft_token> Describe this image"
)
print(output)
```

**Direct Model Loading:**
```python
from transformers import AutoProcessor, Gemma3nForConditionalGeneration
import torch

model = Gemma3nForConditionalGeneration.from_pretrained(
    "google/gemma-3n-e2b",
    device="cuda",
    torch_dtype=torch.bfloat16
).eval()

processor = AutoProcessor.from_pretrained("google/gemma-3n-e2b")

# Process multimodal input
model_inputs = processor(
    text="Transcribe this audio",
    audio=audio_array,
    return_tensors="pt"
).to(model.device)

with torch.inference_mode():
    generation = model.generate(**model_inputs, max_new_tokens=256)
    decoded = processor.decode(generation[0], skip_special_tokens=True)
```

## About Google DeepMind

Google DeepMind is the AI research laboratory formed from the merger of Google Brain and DeepMind in 2023. The Gemma model family represents Google's open-weights initiative, providing efficient models for researchers and developers. Gemma 3n specifically targets the growing need for capable multimodal models that can run on resource-constrained devices.

## Practical Assessment

**Strengths:**
- Innovative MatFormer architecture enables efficient inference
- True multimodal (text, image, audio, video) in compact form factor
- 140+ language support exceeds most competitors
- On-device deployment viable for mobile/edge
- Large 32K context window
- Well-documented with HuggingFace Transformers integration

**Weaknesses:**
- Gemma license (not Apache 2.0) has some restrictions
- Audio capabilities less documented than image/text
- Effective parameter reduction may impact complex reasoning
- Newer architecture with less community tooling
- Knowledge cutoff (June 2024) older than some competitors

**Best suited for:** Edge deployment scenarios requiring multimodal understanding across text, images, and audio. The efficient architecture makes this ideal for mobile applications, embedded systems, and scenarios where compute is limited but multimodal capability is needed. The 140+ language support is particularly valuable for global deployment.

## Links

- [Gemma-3n-E2B (Hugging Face)](https://huggingface.co/google/gemma-3n-E2B)
- [Gemma-3n-E4B (Hugging Face)](https://huggingface.co/google/gemma-3n-E4B)
- [Google DeepMind](https://deepmind.google/)
- [Gemma Documentation](https://ai.google.dev/gemma)
