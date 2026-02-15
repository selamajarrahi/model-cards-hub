# Mistral Large 2

> **Organization**: Mistral AI  
> **Release**: July 2024 (updated 2025)  
> **Type**: Large Language Model  
> **License**: Mistral Research License / Commercial Available

## 🎯 Overview

Mistral Large 2 is Mistral AI's flagship model, offering frontier-level performance with European AI sovereignty. Notable for its **128K context window**, strong multilingual capabilities, and native function calling.

## 📊 Key Specifications

| Attribute | Value |
|-----------|-------|
| **Parameters** | 123B |
| **Context Window** | 128,000 tokens |
| **Training Data** | Through 2024 |
| **Languages** | English, French, German, Spanish, Italian, Portuguese, Dutch, Russian, Chinese, Japanese, Korean |
| **License** | Mistral Research License (free for research) |

## 📈 Benchmarks

| Benchmark | Mistral Large 2 | GPT-4 Turbo | Claude Opus 4 |
|-----------|-----------------|-------------|---------------|
| MMLU | 84.0% | 86.4% | 90.2% |
| HumanEval | 92.1% | 87.1% | 93.4% |
| MATH | 71.2% | 68.2% | 89.2% |
| MT-Bench | 8.63 | 8.96 | 8.85 |

## 💻 Usage

### Via API (La Plateforme)

```python
from mistralai.client import MistralClient
from mistralai.models.chat_completion import ChatMessage

client = MistralClient(api_key="your-api-key")

response = client.chat(
    model="mistral-large-latest",
    messages=[ChatMessage(role="user", content="Explain quantum computing")]
)
print(response.choices[0].message.content)
```

### Function Calling

```python
tools = [
    {
        "type": "function",
        "function": {
            "name": "get_weather",
            "description": "Get weather for a city",
            "parameters": {
                "type": "object",
                "properties": {
                    "city": {"type": "string"}
                },
                "required": ["city"]
            }
        }
    }
]

response = client.chat(
    model="mistral-large-latest",
    messages=[ChatMessage(role="user", content="What's the weather in Paris?")],
    tools=tools
)
```

## 💰 Pricing

| Model | Input (per 1M tokens) | Output (per 1M tokens) |
|-------|----------------------|------------------------|
| mistral-large-latest | $3.00 | $9.00 |
| mistral-medium | $2.70 | $8.10 |
| mistral-small | $1.00 | $3.00 |

## 🔑 Key Features

1. **European AI**: GDPR-compliant, EU data residency options
2. **128K Context**: Process large documents efficiently
3. **Multilingual**: Strong on European and Asian languages
4. **Function Calling**: Native tool use support
5. **Code Generation**: Competitive with specialized models

## 🔗 Resources

- **API Docs**: [docs.mistral.ai](https://docs.mistral.ai)
- **La Plateforme**: [console.mistral.ai](https://console.mistral.ai)
- **GitHub**: [github.com/mistralai](https://github.com/mistralai)

---

*Added: February 2026*
