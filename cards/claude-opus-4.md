# Claude Opus 4

**Organization:** Anthropic  
**Release Date:** 2025  
**Type:** Large Language Model  
**Docs:** [anthropic.com/claude](https://anthropic.com/claude)

---

## Overview

Claude Opus 4 is Anthropic's most capable model, designed for complex reasoning, coding, and long-context tasks. It emphasizes safety, honesty, and helpfulness through Constitutional AI training.

**Key Claims:**
- Top-tier performance on reasoning and coding benchmarks
- 200K token context window (effective use of full context)
- Strong instruction following and safety properties
- Extended thinking mode for complex reasoning

---

## Model Family

| Variant | Context | Speed | Best For |
|---------|---------|-------|----------|
| **Opus 4** | 200K | Slower | Complex reasoning, research |
| **Sonnet 4** | 200K | Fast | Balanced performance |
| **Haiku 4** | 200K | Fastest | High-volume, simple tasks |

---

## Architecture

| Spec | Value |
|------|-------|
| Parameters | Not disclosed |
| Context Window | 200K tokens |
| Modalities | Text, Image, PDF |
| Training | Constitutional AI (CAI) |

### Extended Thinking

Opus 4 supports "extended thinking" mode where it can reason for longer before responding, similar to o1-style chain-of-thought but with Anthropic's approach.

---

## Benchmark Performance

### Reasoning
| Benchmark | Opus 4 | Notes |
|-----------|--------|-------|
| GPQA Diamond | ~78% | PhD-level science |
| MMLU-Pro | ~88% | Graduate knowledge |
| HumanEval | ~92% | Coding |

### Agentic Tasks
| Benchmark | Opus 4 |
|-----------|--------|
| SWE-Bench Verified | ~55% |
| TAU-Bench | Leading |

### Safety
- Strong refusal of harmful requests
- Low hallucination rate
- Calibrated uncertainty

---

## Pricing

| Model | Input (per 1M) | Output (per 1M) |
|-------|----------------|-----------------|
| Opus 4 | $15.00 | $75.00 |
| Sonnet 4 | $3.00 | $15.00 |
| Haiku 4 | $0.25 | $1.25 |

*Prompt caching available for 90% reduction on cached tokens.*

---

## Access

| Method | Status |
|--------|--------|
| Claude.ai | ✅ Available (Pro subscription) |
| API | ✅ Available |
| AWS Bedrock | ✅ Available |
| Google Cloud | ✅ Available |
| Weights | ❌ Closed |

---

## Key Features

### 1. Constitutional AI
Trained to be helpful, harmless, and honest through self-critique and revision, not just RLHF.

### 2. Long Context
200K tokens with strong retrieval across the full context — not just first/last attention.

### 3. Computer Use (Beta)
Can control computer interfaces for agentic tasks (clicking, typing, navigating).

### 4. Tool Use
Native function calling with structured outputs.

### 5. Artifacts
Code execution and visualization in Claude.ai.

---

## Comparison vs GPT-5.2 & Gemini 3 Pro

| Dimension | Claude Opus 4 | GPT-5.2 | Gemini 3 Pro |
|-----------|---------------|---------|--------------|
| Reasoning | Top-tier | Top-tier | Top-tier |
| Coding | Excellent | Excellent | Excellent |
| Context | 200K | 128K | 2M |
| Safety | Strongest | Good | Good |
| Price | High | High | Mid |
| Multimodal | Text+Image | Text+Image+Audio | Text+Image+Audio+Video |

---

## Best For

- **Complex reasoning** requiring extended thinking
- **Coding assistance** and code review
- **Research** and analysis of long documents
- **Safety-critical** applications
- **Agentic** workflows with tool use

---

## Resources

- **Documentation:** [docs.anthropic.com](https://docs.anthropic.com)
- **Claude.ai:** [claude.ai](https://claude.ai)
- **API Console:** [console.anthropic.com](https://console.anthropic.com)
- **Model Card:** [Anthropic Model Card](https://www.anthropic.com/news/claude-model-card)
