# Qwen 3

**Organization:** Alibaba Cloud (Qwen Team)  
**Release Date:** 2025  
**Type:** Large Language Model  
**License:** Apache 2.0 (Open Source)  
**HuggingFace:** [Qwen](https://huggingface.co/Qwen)

---

## Overview

Qwen 3 is Alibaba's flagship open-source LLM family, offering frontier-level performance with full Apache 2.0 licensing. The 235B MoE variant rivals closed models at a fraction of the cost.

**Key Claims:**
- 90%+ quality of GPT-5.2/Claude Opus at 1/10th the price
- Fully open source (Apache 2.0)
- Strong multilingual support (especially Chinese/English)
- Vision and code specialist variants

---

## Model Family

| Variant | Parameters | Type | Best For |
|---------|------------|------|----------|
| **Qwen3-235B** | 235B | MoE | Maximum performance |
| **Qwen3-72B** | 72B | Dense | Self-hosting balance |
| **Qwen3-32B** | 32B | Dense | Production deployment |
| **Qwen3-14B** | 14B | Dense | Consumer GPUs |
| **Qwen3-7B** | 7B | Dense | Edge/mobile |
| **Qwen3-VL** | Various | Vision | Multimodal |
| **Qwen3-Coder** | Various | Code | Programming |

---

## Architecture

### Qwen3-235B (Flagship)

| Spec | Value |
|------|-------|
| Total Parameters | 235B |
| Active Parameters | ~22B (MoE) |
| Experts | 128 |
| Context Window | 128K tokens |
| License | Apache 2.0 |

---

## Benchmark Performance

### Qwen3-235B

| Benchmark | Score | vs GPT-5.2 |
|-----------|-------|------------|
| MMLU-Pro | 86.5% | ~95% |
| GPQA Diamond | 72.1% | ~93% |
| HumanEval | 88.4% | ~96% |
| MATH-500 | 89.2% | ~94% |

**The 90% quality at 1/10th price sweet spot.**

---

## Pricing

### Self-Hosted
- **Free** (Apache 2.0 license)
- Run on your own infrastructure
- No per-token costs

### API Providers

| Provider | Input (per 1M) | Output (per 1M) |
|----------|----------------|-----------------|
| Together AI | $0.80 | $0.80 |
| Fireworks | $0.90 | $0.90 |
| Alibaba Cloud | ~$0.50 | ~$1.00 |

---

## Access

| Method | Status |
|--------|--------|
| HuggingFace | ✅ Full weights |
| Ollama | ✅ All sizes |
| vLLM | ✅ Optimized |
| API (various) | ✅ Multiple providers |
| Commercial use | ✅ Apache 2.0 |

---

## Why Qwen 3 Matters

### 1. True Open Source
Apache 2.0 means you can:
- Use commercially without restrictions
- Modify and redistribute
- Train on it without licensing fees

### 2. Cost Efficiency
Self-hosting Qwen3-235B costs ~$0.10-0.20 per 1M tokens vs $15+ for closed alternatives.

### 3. Multilingual
Excellent Chinese language performance, making it ideal for APAC markets.

### 4. Ecosystem
Full family of models from 0.5B to 235B, plus specialized vision and code variants.

---

## Comparison vs Alternatives

| Model | Open Source | Self-Host | Quality | Cost |
|-------|-------------|-----------|---------|------|
| **Qwen3-235B** | ✅ Apache 2.0 | ✅ | 90% | Very Low |
| Llama 3.3 70B | ⚠️ Meta License | ✅ | 85% | Very Low |
| DeepSeek V3.2 | ✅ MIT | ✅ | 90% | Very Low |
| GPT-5.2 | ❌ | ❌ | 100% | High |
| Claude Opus 4 | ❌ | ❌ | 100% | High |

---

## Hardware Requirements

| Model | VRAM (FP16) | VRAM (INT8) | VRAM (INT4) |
|-------|-------------|-------------|-------------|
| Qwen3-235B | ~470GB | ~235GB | ~120GB |
| Qwen3-72B | ~144GB | ~72GB | ~36GB |
| Qwen3-32B | ~64GB | ~32GB | ~16GB |
| Qwen3-7B | ~14GB | ~7GB | ~4GB |

---

## Resources

- **HuggingFace:** [huggingface.co/Qwen](https://huggingface.co/Qwen)
- **GitHub:** [github.com/QwenLM/Qwen](https://github.com/QwenLM/Qwen)
- **Paper:** [arXiv](https://arxiv.org/abs/2309.16609)
- **ModelScope:** [modelscope.cn/Qwen](https://modelscope.cn/organization/qwen)

---

## Best For

- **Cost-conscious** production deployments
- **Self-hosting** with full control
- **Chinese/multilingual** applications
- **Commercial use** without licensing concerns
- Building on top of open models
