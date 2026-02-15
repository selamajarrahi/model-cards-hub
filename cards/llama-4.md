# Llama 4

> **Organization**: Meta AI  
> **Release**: February 2026  
> **Type**: Open-Weight Large Language Model  
> **License**: Llama 4 Community License (permissive)

## 🎯 Overview

Llama 4 is Meta's latest open-weight foundation model, featuring a **400B MoE architecture** with 52B active parameters. It matches or exceeds many proprietary models while remaining freely available for commercial use (with some restrictions).

## 📊 Key Specifications

| Attribute | Value |
|-----------|-------|
| **Total Parameters** | 400B (MoE) |
| **Active Parameters** | 52B per forward pass |
| **Context Window** | 128K tokens (256K with RoPE scaling) |
| **Training Data** | 20T tokens, through October 2025 |
| **Architecture** | Mixture of Experts (64 experts, top-8 routing) |
| **License** | Llama 4 Community License |

## 📈 Benchmarks

### Language Understanding

| Benchmark | Llama 4 | Claude Opus 4 | GPT-5.2 |
|-----------|---------|---------------|---------|
| MMLU | 88.2% | 90.2% | **93.7%** |
| MMLU-Pro | 74.1% | 78.9% | **84.2%** |
| HellaSwag | **96.8%** | 95.2% | 96.4% |

### Coding

| Benchmark | Llama 4 | Claude Opus 4 | GPT-5.2 |
|-----------|---------|---------------|---------|
| HumanEval | 88.4% | **93.4%** | 96.2% |
| MBPP+ | 82.1% | 86.7% | **89.2%** |
| SWE-Bench Verified | 48.2% | **80.9%** | 76.8% |

### Math & Reasoning

| Benchmark | Llama 4 | Claude Opus 4 | GPT-5.2 |
|-----------|---------|---------------|---------|
| MATH | 76.4% | 89.2% | **94.8%** |
| GSM8K | 94.2% | 97.8% | **99.2%** |
| ARC-Challenge | 95.1% | 96.8% | **98.7%** |

## 💻 Usage

### With Hugging Face Transformers

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
import torch

model_id = "meta-llama/Llama-4-400B-MoE"

tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(
    model_id,
    torch_dtype=torch.bfloat16,
    device_map="auto",
    load_in_4bit=True  # For consumer GPUs
)

inputs = tokenizer("The meaning of life is", return_tensors="pt")
outputs = model.generate(**inputs, max_new_tokens=100)
print(tokenizer.decode(outputs[0]))
```

### With vLLM (Production)

```python
from vllm import LLM, SamplingParams

llm = LLM(
    model="meta-llama/Llama-4-400B-MoE",
    tensor_parallel_size=4,  # 4x A100 or H100
    max_model_len=128000
)

prompts = ["Explain quantum entanglement"]
sampling_params = SamplingParams(temperature=0.7, max_tokens=500)

outputs = llm.generate(prompts, sampling_params)
```

### With Ollama (Local)

```bash
# Download and run
ollama run llama4

# In another terminal
curl http://localhost:11434/api/generate -d '{
  "model": "llama4",
  "prompt": "Why is the sky blue?"
}'
```

## 🖥️ Hardware Requirements

### Full Precision (BF16)

| Model | VRAM Required | Recommended Setup |
|-------|---------------|-------------------|
| Llama 4 400B | ~800GB | 10x H100 80GB |
| Llama 4 70B | ~140GB | 2x H100 80GB |
| Llama 4 8B | ~16GB | 1x RTX 4090 |

### Quantized

| Quantization | VRAM (400B) | Quality Loss |
|--------------|-------------|--------------|
| 4-bit (GPTQ/AWQ) | ~200GB | ~1-2% |
| 8-bit (bitsandbytes) | ~400GB | <1% |
| GGUF Q4_K_M | ~220GB | ~2-3% |

## 🔑 Key Features

### 1. Mixture of Experts
- 64 experts, top-8 active per token
- Efficient inference (only 52B params active)
- Better scaling than dense models

### 2. Extended Context
- 128K native, 256K with scaling
- Efficient attention (grouped-query)
- Maintains quality across context

### 3. Open Weights
- Full model weights available
- Fine-tuning friendly
- Active community

### 4. Multilingual
- 50+ languages
- Strong non-English performance
- Code in multiple languages

## 📦 Model Variants

| Variant | Parameters | Active | Use Case |
|---------|------------|--------|----------|
| Llama 4 8B | 8B | 8B | Local/edge deployment |
| Llama 4 70B | 70B | 70B | Single-node inference |
| Llama 4 400B MoE | 400B | 52B | Maximum capability |

## 📜 License

**Llama 4 Community License**:
- ✅ Commercial use
- ✅ Fine-tuning
- ✅ Derivative works
- ⚠️ Must include attribution
- ⚠️ Monthly active users > 700M need separate license
- ❌ Cannot use to train competing foundation models

## ⚠️ Limitations

- **Hardware**: Large models need significant GPU resources
- **Knowledge cutoff**: October 2025
- **No official API**: Must self-host or use third-party providers
- **Reasoning**: Trails proprietary models on complex reasoning

## 🆚 When to Choose Llama 4

### Choose Llama 4 When:
- ✅ Need open-weight / self-hosted
- ✅ Fine-tuning is critical
- ✅ Privacy/compliance requirements
- ✅ Cost optimization at scale
- ✅ Research and experimentation

### Consider Alternatives When:
- ❌ Maximum reasoning needed (GPT-5.2)
- ❌ Best coding accuracy (Claude Opus 4)
- ❌ No infrastructure for hosting
- ❌ Need fully managed solution

## 🔗 Resources

- **Model Hub**: [huggingface.co/meta-llama](https://huggingface.co/meta-llama)
- **GitHub**: [github.com/meta-llama/llama](https://github.com/meta-llama/llama)
- **Documentation**: [llama.meta.com](https://llama.meta.com)
- **Paper**: [arXiv:2602.xxxxx](https://arxiv.org/abs/2602.xxxxx)
- **Community**: [Discord](https://discord.gg/llama)

## 📚 Related Models

- [Qwen 3](qwen-3.md) - Alibaba's open model
- [DeepSeek R1](deepseek-r1.md) - Open reasoning model
- [Mistral Large](mistral-large.md) - European open model

---

*Added: February 2026*
