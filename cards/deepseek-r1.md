# DeepSeek R1

**Organization:** DeepSeek AI  
**Release Date:** January 2025  
**Type:** Large Language Model (Reasoning-focused)  
**Paper:** [arXiv:2501.12948](https://arxiv.org/abs/2501.12948)  
**License:** MIT (Open Source)

---

## Overview

DeepSeek R1 is an open-source reasoning model that matches or exceeds OpenAI o1's performance on math and coding benchmarks. It pioneered transparent chain-of-thought reasoning in open models.

**Key Claims:**
- Matches OpenAI o1 on AIME, MATH, and coding benchmarks
- Fully open source under MIT license
- Novel reinforcement learning approach without supervised fine-tuning
- Distilled versions available (1.5B to 70B)

---

## Model Family

| Variant | Parameters | Context | Best For |
|---------|------------|---------|----------|
| **R1** | 671B (MoE) | 128K | Maximum reasoning |
| **R1-Distill-Qwen-32B** | 32B | 128K | Balanced performance |
| **R1-Distill-Llama-70B** | 70B | 128K | Llama ecosystem |
| **R1-Distill-Qwen-7B** | 7B | 128K | Resource-constrained |
| **R1-Distill-Qwen-1.5B** | 1.5B | 128K | Edge deployment |

---

## Architecture

| Spec | Value |
|------|-------|
| Total Parameters | 671B |
| Active Parameters | ~37B (MoE) |
| Architecture | Mixture of Experts |
| Context Window | 128K tokens |
| Training | RL without SFT (cold-start) |

### Training Innovation

DeepSeek R1 was trained using **pure reinforcement learning** from a base model — no supervised fine-tuning on reasoning traces. This "cold-start" approach allows the model to develop its own reasoning patterns.

---

## Benchmark Performance

### Math Reasoning
| Benchmark | R1 | o1 | Notes |
|-----------|----|----|-------|
| AIME 2024 | 79.8% | 79.2% | Competition math |
| MATH-500 | 97.3% | 96.4% | Graduate math |

### Coding
| Benchmark | R1 | o1 |
|-----------|----|----|
| Codeforces | 2029 Elo | 1891 Elo |
| LiveCodeBench | 65.9% | 63.4% |

### General
| Benchmark | R1 | o1 |
|-----------|----|----|
| GPQA Diamond | 71.5% | 75.7% |
| MMLU | 90.8% | 91.8% |

---

## Pricing

### API (DeepSeek Platform)

| Model | Input (per 1M) | Output (per 1M) |
|-------|----------------|-----------------|
| R1 | $0.55 | $2.19 |
| R1 (cache hit) | $0.14 | $2.19 |

**~90% cheaper than OpenAI o1**

### Self-Hosting
- Weights available on HuggingFace
- Distilled versions run on consumer GPUs

---

## Access

| Method | Status |
|--------|--------|
| DeepSeek API | ✅ Available |
| HuggingFace | ✅ Weights available |
| Ollama | ✅ Distilled versions |
| vLLM | ✅ Supported |

---

## Key Innovation: RL Without SFT

Traditional reasoning models (like o1) use supervised fine-tuning on human-written reasoning chains. DeepSeek R1 skips this entirely:

1. Start with base model
2. Apply RL with verifiable rewards (math correctness, code execution)
3. Let model develop its own reasoning style

This produces more diverse reasoning patterns and avoids "teaching to the test."

---

## Comparison vs OpenAI o1

| Dimension | DeepSeek R1 | OpenAI o1 |
|-----------|-------------|-----------|
| Performance | ~Equal | ~Equal |
| Cost | ~90% cheaper | Expensive |
| Open Source | ✅ MIT License | ❌ Closed |
| Self-Host | ✅ Yes | ❌ No |
| Reasoning Visible | ✅ Full chain | ⚠️ Summarized |

---

## Resources

- **Paper:** [arXiv:2501.12948](https://arxiv.org/abs/2501.12948)
- **HuggingFace:** [deepseek-ai/DeepSeek-R1](https://huggingface.co/deepseek-ai/DeepSeek-R1)
- **API Docs:** [platform.deepseek.com](https://platform.deepseek.com)
- **GitHub:** [deepseek-ai/DeepSeek-R1](https://github.com/deepseek-ai/DeepSeek-R1)

---

## Impact

DeepSeek R1 proved that frontier reasoning capabilities can be achieved with open models. Its release accelerated open-source AI development and forced pricing competition across the industry.
