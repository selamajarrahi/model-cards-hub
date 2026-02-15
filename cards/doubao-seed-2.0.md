# Doubao-Seed-2.0

**Organization:** ByteDance  
**Release Date:** February 14, 2026  
**Type:** Large Language Model (LLM)  
**Model Card PDF:** [Official](https://lf3-static.bytednsdoc.com/obj/eden-cn/lapzild-tss/ljhwZthlaukjlkulzlp/seed2/0214/Seed2.0%20Model%20Card.pdf)

---

## Overview

Doubao-Seed-2.0 is ByteDance's flagship LLM, positioned as a competitor to GPT-5.2 and Gemini 3 Pro. The model is optimized for long-chain reasoning, agent-based tasks, and multimodal understanding.

**Key Claims:**
- Leading results on multimodal, math, and coding benchmarks
- Performance comparable to GPT-5.2 and Gemini 3 Pro
- Token pricing ~10x lower than competitors

---

## Model Family

| Variant | Focus | Availability |
|---------|-------|--------------|
| **Seed-2.0 Pro** | Flagship, long-chain reasoning | Doubao app, Volcano Engine API |
| **Seed-2.0 Lite** | Fast inference, cost-optimized | TBD |

---

## Architecture

| Spec | Value |
|------|-------|
| Parameters | Not disclosed |
| Context Window | Not disclosed (likely 128K+) |
| Modalities | Text, Image, potentially more |
| Training | Likely includes code, math, agent trajectories |

*ByteDance has not released full architectural details.*

---

## Benchmark Performance

From the model card (Feb 2026):

### Multimodal Reasoning
- **SimpleVQA:** Leading
- **HallusionBench:** Leading
- **MMMU:** Leading
- **OmniDocBench:** Leading
- **CharXiv:** Leading

### Mathematical Reasoning
- **MathArena:** Leading
- **Beyond-AIME:** Leading
- **Humanity's Last Exam:** Leading
- **GPQA Diamond:** Leading

### Agent/Tool Use
- **TAU Bench:** Leading
- **VitaBench:** Leading
- **GAIA:** Leading
- **FinSearchComp:** Leading

---

## Pricing

ByteDance claims pricing is **~1 order of magnitude lower** than competing models (GPT-5.2, Gemini 3 Pro).

| Tier | Input | Output |
|------|-------|--------|
| Volcano Engine API | TBD | TBD |

---

## Access

| Method | Status |
|--------|--------|
| Doubao App | ✅ Available |
| Volcano Engine API | ✅ Available |
| International API | ❓ Unknown |

---

## Related Models

### Seedance 2.0 (Video)
ByteDance also released **Seedance 2.0** — a multimodal video generation model — on the same day. See [Seedance 2.0](seedance-2.0.md).

### Seed Series History
- **Seed 1.5 VL** — Vision-language model (2025)
- **Seed 1.6** — Predecessor LLM
- **Seed 1.8** — Previous flagship
- **SeedProver 1.5** — Formal math reasoning

---

## Resources

- **Model Card PDF:** [ByteDance Static](https://lf3-static.bytednsdoc.com/obj/eden-cn/lapzild-tss/ljhwZthlaukjlkulzlp/seed2/0214/Seed2.0%20Model%20Card.pdf)
- **WeChat Announcement:** [Link](https://mp.weixin.qq.com/s/1dlAeBOu1FPkCabQ_UIMEA)
- **TechNode Coverage:** [Article](https://technode.com/2026/02/14/bytedance-releases-doubao-seed-2-0-positions-pro-model-against-gpt-5-2-and-gemini-3-pro/)

---

## Notes

- Released same day as Seedance 2.0 video model
- Part of ByteDance's aggressive push into AI
- Benchmarks suggest strong performance but independent verification pending
