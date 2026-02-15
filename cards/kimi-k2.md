# Kimi K2

**Organization:** Moonshot AI  
**Release Date:** July 2025  
**Type:** Large Language Model (MoE)  
**Paper:** [arXiv:2507.20534](https://arxiv.org/abs/2507.20534)

---

## Overview

Kimi K2 is Moonshot AI's flagship 1 trillion parameter mixture-of-experts (MoE) model. Notable for being the first production model at this scale to use the **Muon optimizer**.

**Key Claims:**
- 1T total parameters (32B active per token)
- SOTA or near-SOTA on coding, reasoning, general benchmarks
- "Open Agentic Intelligence" — optimized for tool use and autonomous tasks

---

## Architecture

| Spec | Value |
|------|-------|
| Total Parameters | 1 trillion |
| Active Parameters | 32B per token |
| Experts | 384 per layer |
| Layers | 61 |
| Hidden Dimension | 7168 |
| Context Window | 128K tokens |
| Architecture | Mixture of Experts (MoE) |

---

## Training

### Optimizer: Muon

Kimi K2 is the **largest known model trained with Muon** — a 700x scale increase over previous Muon experiments (~1.5B params).

| Muon Setting | Value |
|--------------|-------|
| Learning Rate | ~0.02 (for Linear layers) |
| Momentum | 0.95 |
| Newton-Schulz Steps | 5 |
| Precision | bfloat16 |

AdamW is used for embeddings, LayerNorm, and 1D parameters.

### Data

- **Training Tokens:** 15.5 trillion
- **Focus Areas:** Code, reasoning, agentic trajectories, tool use

---

## Benchmark Performance

### Coding
- **SWE-Bench:** SOTA
- **HumanEval:** Near-SOTA

### Reasoning
- **MATH:** SOTA
- **GSM8K:** SOTA

### General
- **MMLU:** Near-SOTA
- **ARC:** Near-SOTA

### Agentic/Tool Use
- Strong performance on tool use benchmarks
- Optimized for multi-step autonomous tasks

---

## Muon at Scale: Key Findings

1. **Learning rate transfer works** — Same η effective across model sizes
2. **Stability** — No special stabilization needed
3. **Efficiency** — <1% FLOP overhead maintained at scale
4. **Memory** — Same as AdamW (momentum buffer only)

---

## Access

| Method | Status |
|--------|--------|
| Kimi Chat | ✅ Available |
| API | ✅ Available |
| Weights | ❓ "Open" but licensing unclear |

---

## Resources

- **arXiv Paper:** [2507.20534](https://arxiv.org/abs/2507.20534)
- **Project Page:** [moonshotai.github.io/Kimi-K2](https://moonshotai.github.io/Kimi-K2/)
- **Muon Learning Hub:** [Local](/home/kb/.openclaw/workspace/muon-learning-hub)

---

## Historical Context

Kimi K2 validates that Muon can scale to frontier model sizes. Before K2, the largest Muon training was ~1.5B parameters in NanoGPT speedruns.

This opens the door for other labs to adopt Muon for large-scale training.
