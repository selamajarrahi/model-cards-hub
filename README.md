# 🃏 Model Cards Hub

> A curated collection of AI model cards, specs, comparison guides, and practical resources

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/yourusername/model-cards-hub/pulls)

## 🚀 Quick Links

| I want to... | Go to |
|--------------|-------|
| Compare all models at a glance | [📊 Comparison Matrix](guides/comparison-matrix.md) |
| Find the right model for my use case | [🧭 Model Selection Guide](guides/model-selection-guide.md) |
| Understand pricing | [💰 Pricing Comparison](guides/pricing-comparison.md) |
| Get started with code | [💻 API Code Snippets](guides/api-snippets.md) |
| Self-host open models | [🖥️ Self-Hosting Guide](guides/self-hosting-guide.md) |
| Check license restrictions | [⚖️ License Comparison](guides/license-comparison.md) |

---

## 📚 Model Index

### Language Models (LLMs)

| Model | Org | Release | Params | Highlights | Card |
|-------|-----|---------|--------|------------|------|
| GPT-5.2 | OpenAI | Jan 2026 | ~1-2T | 100% AIME, 400K context | [📄](cards/gpt-5.2.md) |
| Gemini 3 Pro | Google | Jan 2026 | MoE | 1M context, multimodal leader | [📄](cards/gemini-3-pro.md) |
| Llama 4 | Meta | Feb 2026 | 400B MoE | Open weights, 52B active | [📄](cards/llama-4.md) |
| Doubao-Seed-2.0 | ByteDance | Feb 2026 | Unknown | Competes with GPT-5.2, Gemini 3 Pro | [📄](cards/doubao-seed-2.0.md) |
| Kimi K2 | Moonshot AI | Jul 2025 | 1T (32B active) | MoE, Muon optimizer, agentic focus | [📄](cards/kimi-k2.md) |
| Claude Opus 4 | Anthropic | 2025 | Unknown | 200K context, extended thinking | [📄](cards/claude-opus-4.md) |
| DeepSeek R1 | DeepSeek | Jan 2025 | 671B MoE | Open source, matches o1, MIT license | [📄](cards/deepseek-r1.md) |
| Grok 4 | xAI | Late 2025 | Unknown | Real-time X data, Aurora image gen | [📄](cards/grok-4.md) |
| Qwen 3 | Alibaba | 2025 | Up to 235B | Apache 2.0, excellent value | [📄](cards/qwen-3.md) |

### Video Generation

| Model | Org | Release | Resolution | Highlights | Card |
|-------|-----|---------|------------|------------|------|
| Seedance 2.0 | ByteDance | Feb 2026 | 2K | 4-modal input, native audio sync | [📄](cards/seedance-2.0.md) |
| Sora 2 | OpenAI | — | 1080p | *Coming soon* |
| Kling 3.0 | Kuaishou | — | 1080p | *Coming soon* |
| Veo 3.1 | Google | — | 1080p | *Coming soon* |

### Image Generation

| Model | Org | Release | Highlights | Card |
|-------|-----|---------|------------|------|
| FLUX 1.1 Pro | Black Forest Labs | Oct 2024 | Best quality, great text rendering, 6x faster | [📄](cards/flux-1.1-pro.md) |
| DALL-E 4 | OpenAI | — | *Coming soon* |
| Imagen 3 | Google | — | *Coming soon* |
| Midjourney v6 | Midjourney | — | *Coming soon* |

---

## 📖 Guides & Resources

### Decision Making
| Guide | Description |
|-------|-------------|
| [📊 Comparison Matrix](guides/comparison-matrix.md) | Side-by-side specs for all models |
| [🧭 Model Selection Guide](guides/model-selection-guide.md) | Flowchart to pick the right model |
| [💰 Pricing Comparison](guides/pricing-comparison.md) | API costs, subscriptions, self-hosting economics |
| [⚖️ License Comparison](guides/license-comparison.md) | What you can and can't do commercially |

### Getting Started
| Guide | Description |
|-------|-------------|
| [💻 API Code Snippets](guides/api-snippets.md) | Quick-start code for every major API |
| [🖥️ Self-Hosting Guide](guides/self-hosting-guide.md) | Run open models on your hardware |
| [📖 Glossary](guides/glossary.md) | Key AI terms explained |

### Deep Dives
| Guide | Description |
|-------|-------------|
| [🌳 Model Family Trees](guides/model-family-trees.md) | Evolution of GPT, Claude, Llama, etc. |
| [👀 Models to Watch](guides/models-to-watch.md) | Upcoming releases and emerging players |
| [📏 Context Window Comparison](guides/context-window-comparison.md) | **NEW**: Compare context lengths & implications |
| [🎯 Best Model For X](guides/best-model-for-task.md) | **NEW**: Decision trees for model selection |

### Audio & Embeddings
| Model | Type | Card |
|-------|------|------|
| Whisper v4 | Speech Recognition | [📄](cards/whisper-v4.md) |
| text-embedding-3 | Text Embeddings | [📄](cards/text-embedding-3.md) |

---

## 🎯 Quick Selection

### By Use Case

| Use Case | Top Pick | Runner-up |
|----------|----------|-----------|
| Complex reasoning | Claude Opus 4 | DeepSeek R1 |
| Coding assistant | Claude Opus 4 | DeepSeek R1 |
| Budget-friendly | DeepSeek V3 | Qwen 3 |
| Self-hosting | DeepSeek R1 (MIT) | Qwen 3 (Apache) |
| Image generation | FLUX 1.1 Pro | DALL-E 3 |
| Video generation | Seedance 2.0 | Sora 2 |
| Agentic/tools | Kimi K2 | Claude Opus 4 |

### By Budget (LLMs)

| Budget | Model | Cost (per 1M tokens) |
|--------|-------|---------------------|
| 💰 Free | Qwen 3 (self-host) | $0* |
| 💰 Low | DeepSeek V3 | $0.27 input |
| 💰💰 Medium | Claude Sonnet 4 | $3 input |
| 💰💰💰 Premium | Claude Opus 4 | $15 input |

*Hardware costs not included

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

## 📥 Contributing

### Adding New Models

1. Create `cards/<model-name>.md` using [the template](cards/_TEMPLATE.md)
2. Update this README's index
3. Add any PDF/raw model cards to `raw/`
4. Submit a PR!

### Improving Guides

- Fix outdated pricing or specs
- Add new comparisons or benchmarks  
- Improve explanations
- Add code examples

---

## 🗺️ Repository Structure

```
model-cards-hub/
├── README.md                 # You are here
├── cards/                    # Individual model cards
│   ├── _TEMPLATE.md
│   ├── claude-opus-4.md
│   ├── deepseek-r1.md
│   ├── kimi-k2.md
│   └── ...
├── guides/                   # Reference guides
│   ├── comparison-matrix.md
│   ├── pricing-comparison.md
│   ├── model-selection-guide.md
│   ├── api-snippets.md
│   ├── self-hosting-guide.md
│   ├── license-comparison.md
│   ├── model-family-trees.md
│   ├── models-to-watch.md
│   └── glossary.md
├── raw/                      # Original PDFs and docs
└── notes/                    # Working notes
```

---

## 🔗 External Resources

- [Hugging Face Model Hub](https://huggingface.co/models)
- [Papers With Code](https://paperswithcode.com)
- [AI Index Report](https://aiindex.stanford.edu)
- [Artificial Analysis](https://artificialanalysis.ai)

---

*Maintained by codmire_'s assistant 🐈⬛*

*Last updated: February 2026*
