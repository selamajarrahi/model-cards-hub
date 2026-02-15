# Claude Sonnet 4

> **Organization**: Anthropic  
> **Release**: May 2025  
> **Type**: Large Language Model  
> **Tier**: Mid-range (best value)

## 🎯 Overview

Claude Sonnet 4 is Anthropic's balanced model offering, providing **near-Opus performance at 1/5th the cost**. It's the most popular Claude model for production deployments.

## 📊 Key Specifications

| Attribute | Value |
|-----------|-------|
| **Context Window** | 200,000 tokens |
| **Training Data** | Through Q2 2025 |
| **Modalities** | Text, Images (input) |
| **Thinking Mode** | Standard (no extended thinking) |

## 📈 Benchmarks

| Benchmark | Sonnet 4 | Opus 4 | GPT-4o |
|-----------|----------|--------|--------|
| MMLU | 87.4% | 90.2% | 88.7% |
| HumanEval | 88.2% | 93.4% | 90.2% |
| MATH | 78.1% | 89.2% | 76.6% |
| SWE-Bench | 65.1% | 80.9% | 52.3% |

## 💰 Pricing

| Metric | Sonnet 4 | Opus 4 |
|--------|----------|--------|
| Input (per 1M) | $3.00 | $15.00 |
| Output (per 1M) | $15.00 | $75.00 |
| Relative Cost | 1x | 5x |

## 💻 Usage

```python
from anthropic import Anthropic

client = Anthropic()

message = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "Explain the CAP theorem"}
    ]
)
```

## 🔑 When to Choose Sonnet 4

✅ Production APIs (cost-sensitive)
✅ High-volume applications
✅ General assistance tasks
✅ Code review and generation
✅ Document analysis

### Consider Opus 4 Instead For:
- Complex reasoning tasks
- Research-level analysis
- Tasks requiring extended thinking
- Maximum accuracy requirements

## 🔗 Resources

- **API Docs**: [docs.anthropic.com](https://docs.anthropic.com)
- **Console**: [console.anthropic.com](https://console.anthropic.com)

---

*Added: February 2026*
