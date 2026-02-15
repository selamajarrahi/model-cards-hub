# 🃏 Model Cards Hub

> A curated collection of AI model cards, specs, and comparison guides.

## 📚 Model Index

### Language Models (LLMs)

| Model | Org | Release | Params | Highlights |
|-------|-----|---------|--------|------------|
| [Doubao-Seed-2.0](cards/doubao-seed-2.0.md) | ByteDance | Feb 2026 | Unknown | Competes with GPT-5.2, Gemini 3 Pro |
| [Kimi K2](cards/kimi-k2.md) | Moonshot AI | Jul 2025 | 1T (32B active) | MoE, Muon optimizer, agentic focus |
| [Claude Opus 4](cards/claude-opus-4.md) | Anthropic | 2025 | Unknown | 200K context, Constitutional AI, extended thinking |
| [DeepSeek R1](cards/deepseek-r1.md) | DeepSeek | Jan 2025 | 671B MoE | Open source, matches o1, MIT license |
| [Grok 4](cards/grok-4.md) | xAI | Late 2025 | Unknown | Real-time X data, Aurora image gen |
| [Qwen 3](cards/qwen-3.md) | Alibaba | 2025 | Up to 235B | Apache 2.0, 90% GPT quality at 1/10 cost |
| [GPT-5.2](#) | OpenAI | — | — | *Coming soon* |
| [Gemini 3 Pro](#) | Google | — | — | *Coming soon* |

### Video Generation

| Model | Org | Release | Resolution | Highlights |
|-------|-----|---------|------------|------------|
| [Seedance 2.0](cards/seedance-2.0.md) | ByteDance | Feb 2026 | 2K | 4-modal input, native audio sync |
| [Sora 2](#) | OpenAI | — | 1080p | *Coming soon* |
| [Kling 3.0](#) | Kuaishou | — | 1080p | *Coming soon* |
| [Veo 3.1](#) | Google | — | 1080p | *Coming soon* |

### Image Generation

| Model | Org | Release | Highlights |
|-------|-----|---------|------------|
| [FLUX 1.1 Pro](cards/flux-1.1-pro.md) | Black Forest Labs | Oct 2024 | Best quality, great text rendering, 6x faster |
| [DALL-E 4](#) | OpenAI | — | *Coming soon* |
| [Imagen 3](#) | Google | — | *Coming soon* |
| [Midjourney v6](#) | Midjourney | — | *Coming soon* |

---

## 🗂️ Card Format

Each model card follows a consistent structure:

```markdown
# Model Name

## Overview
- Organization, release date, key claims

## Architecture
- Parameters, layers, context, special features

## Benchmarks
- Performance on standard evals

## Usage
- API access, pricing, integrations

## Comparison
- How it stacks up vs alternatives

## Resources
- Links to papers, docs, demos
```

---

## 📥 Adding New Models

1. Create `cards/<model-name>.md` using the template
2. Update this README's index
3. Add any PDF/raw model cards to `raw/`

---

## 🔗 External Resources

- [Hugging Face Model Hub](https://huggingface.co/models)
- [Papers With Code](https://paperswithcode.com)
- [AI Index Report](https://aiindex.stanford.edu)

---

*Maintained by codmire_'s assistant 🐈‍⬛*
