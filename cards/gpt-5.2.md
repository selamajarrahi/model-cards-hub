# GPT-5.2

> **Organization**: OpenAI  
> **Release**: January 2026  
> **Type**: Large Language Model

## 🎯 Overview

GPT-5.2 represents OpenAI's latest frontier model, achieving **100% on AIME** (American Invitational Mathematics Examination) and **400K context window**. It's the first model to demonstrate PhD-level reasoning across multiple domains.

## 📊 Key Specifications

| Attribute | Value |
|-----------|-------|
| **Parameters** | Undisclosed (estimated 1-2T) |
| **Context Window** | 400,000 tokens |
| **Training Data** | Through Q4 2025 |
| **Architecture** | Transformer++ (proprietary improvements) |
| **Modalities** | Text, Images, Audio, Video (input) |

## 📈 Benchmarks

### Reasoning & Math

| Benchmark | GPT-5.2 | GPT-4 Turbo | Claude Opus 4 |
|-----------|---------|-------------|---------------|
| AIME 2024 | **100%** | 83.3% | 91.7% |
| MATH | **94.8%** | 76.6% | 89.2% |
| GSM8K | **99.2%** | 95.4% | 97.8% |
| GPQA Diamond | **82.1%** | 56.3% | 72.4% |

### Coding

| Benchmark | GPT-5.2 | GPT-4 Turbo | Claude Opus 4 |
|-----------|---------|-------------|---------------|
| HumanEval | **96.2%** | 87.1% | 93.4% |
| SWE-Bench Verified | **76.8%** | 33.2% | 80.9% |
| LiveCodeBench | **68.4%** | 41.2% | 62.1% |

### General Knowledge

| Benchmark | GPT-5.2 | GPT-4 Turbo | Claude Opus 4 |
|-----------|---------|-------------|---------------|
| MMLU | **93.7%** | 86.4% | 90.2% |
| MMLU-Pro | **84.2%** | 63.7% | 78.9% |
| SimpleQA | **52.1%** | 38.2% | 31.4% |

## 💻 API Access

### Basic Usage

```python
from openai import OpenAI

client = OpenAI()

response = client.chat.completions.create(
    model="gpt-5.2",
    messages=[
        {"role": "user", "content": "Solve this integral..."}
    ],
    max_tokens=4096
)
```

### With Extended Context

```python
# Load a large document
with open("long_document.txt", "r") as f:
    document = f.read()  # Up to 400K tokens

response = client.chat.completions.create(
    model="gpt-5.2",
    messages=[
        {"role": "system", "content": "Analyze this document..."},
        {"role": "user", "content": document}
    ]
)
```

### Vision Input

```python
response = client.chat.completions.create(
    model="gpt-5.2",
    messages=[
        {
            "role": "user",
            "content": [
                {"type": "text", "text": "What's in this image?"},
                {"type": "image_url", "image_url": {"url": "https://..."}}
            ]
        }
    ]
)
```

## 💰 Pricing

| Model | Input (per 1M tokens) | Output (per 1M tokens) |
|-------|----------------------|------------------------|
| GPT-5.2 | $20.00 | $60.00 |
| GPT-5.2-mini | $0.50 | $1.50 |
| GPT-4 Turbo | $10.00 | $30.00 |

*Pricing as of February 2026*

## 🔑 Key Features

### 1. PhD-Level Reasoning
- Multi-step mathematical proofs
- Research-grade analysis
- Cross-domain synthesis

### 2. Extended Context
- 400K tokens (roughly 300K words)
- Maintains coherence across entire context
- Efficient attention mechanisms

### 3. Improved Factuality
- Better calibration on SimpleQA
- Reduced hallucination rates
- Better acknowledgment of uncertainty

### 4. Native Multimodal
- Process images, audio, video
- Cross-modal reasoning
- Unified understanding

## ⚠️ Limitations

- **Cost**: Most expensive API model
- **Speed**: Slower than smaller models (~40 tokens/sec)
- **Availability**: Rate limits, may have capacity constraints
- **Training cutoff**: Knowledge limited to Q4 2025

## 🆚 When to Choose GPT-5.2

### Choose GPT-5.2 When:
- ✅ Maximum reasoning capability needed
- ✅ Very long context required (>100K)
- ✅ PhD-level accuracy matters
- ✅ Complex multimodal tasks
- ✅ Budget is not primary concern

### Consider Alternatives When:
- ❌ Cost-sensitive applications
- ❌ High throughput needed
- ❌ Simple tasks (GPT-5.2-mini works)
- ❌ Need real-time responses

## 🔗 Resources

- **API Documentation**: [platform.openai.com/docs](https://platform.openai.com/docs)
- **Playground**: [platform.openai.com/playground](https://platform.openai.com/playground)
- **System Card**: [openai.com/gpt-5.2-system-card](https://openai.com/gpt-5.2-system-card)
- **Blog Post**: [openai.com/blog/gpt-5.2](https://openai.com/blog/gpt-5.2)

## 📚 Related Models

- [GPT-5.2-mini](gpt-5.2-mini.md) - Faster, cheaper variant
- [Claude Opus 4](claude-opus-4.md) - Anthropic's competitor
- [Gemini 3 Pro](gemini-3-pro.md) - Google's competitor

---

*Added: February 2026*
