# Best Model For X: Decision Trees

> Quick decision guides for choosing the right model for your task.

---

## 🧠 Complex Reasoning

```
Do you need PhD-level accuracy?
│
├── YES: GPT-5.2 (100% AIME, best GPQA)
│
└── NO
    │
    Is cost a major concern?
    │
    ├── YES: DeepSeek R1 (open, strong reasoning)
    │
    └── NO
        │
        Do you need very long context (>200K)?
        │
        ├── YES: Gemini 3 Pro (1M context)
        │
        └── NO: Claude Opus 4 (great balance)
```

**Winner by scenario:**
| Scenario | Best Model |
|----------|------------|
| Math competition problems | GPT-5.2 |
| Legal document analysis | Claude Opus 4 |
| Scientific reasoning | GPT-5.2 |
| Budget reasoning tasks | DeepSeek R1 |

---

## 💻 Coding & Software Development

```
What type of coding task?
│
├── Full codebase understanding/refactoring
│   │
│   ├── Need to self-host? → Llama 4 + Augment Code
│   └── API is fine → Claude Opus 4 (best SWE-bench)
│
├── Quick completions/autocomplete
│   │
│   ├── Free tier → Codeium, Continue
│   └── Paid → GitHub Copilot, Cursor
│
├── Code review
│   └── Claude Opus 4 or GPT-5.2
│
└── Learning/explanation
    └── Any top model works; Claude is known for clear explanations
```

**Winner by scenario:**
| Scenario | Best Model |
|----------|------------|
| SWE-bench tasks | Claude Opus 4 (80.9%) |
| Competition programming | GPT-5.2 |
| Open-source contribution | DeepSeek R1 + Llama 4 |
| IDE integration | Cursor (Claude/GPT) |
| Code explanation | Claude (any tier) |

---

## 🎨 Image Generation

```
What's your priority?
│
├── Photorealism
│   │
│   ├── Free → SDXL, Stable Diffusion 3
│   └── Paid → Midjourney v6, FLUX 1.1 Pro
│
├── Text rendering
│   └── FLUX 1.1 Pro (best text accuracy)
│
├── Speed
│   └── FLUX Schnell, SDXL Turbo
│
├── Artistic/stylized
│   └── Midjourney v6
│
└── Enterprise/compliance
    └── DALL-E 3 (OpenAI's content policy)
```

**Winner by scenario:**
| Scenario | Best Model |
|----------|------------|
| Marketing images | Midjourney v6 |
| Product mockups | FLUX 1.1 Pro |
| Text-heavy graphics | FLUX 1.1 Pro |
| Rapid prototyping | FLUX Schnell |
| Self-hosted | Stable Diffusion 3 |

---

## 🎬 Video Generation

```
What type of video?
│
├── Cinematic/high quality
│   └── Seedance 2.0 (2K, native audio)
│
├── Quick clips
│   │
│   ├── API available → Runway Gen-3
│   └── Self-hosted → Open-Sora
│
├── Lip sync/talking heads
│   └── HeyGen, Synthesia
│
└── Animation/motion
    └── Pika, Runway
```

**Winner by scenario:**
| Scenario | Best Model |
|----------|------------|
| Film production | Seedance 2.0 |
| Marketing videos | Runway Gen-3 |
| Training videos | HeyGen |
| Experimental | Sora 2 (when available) |

---

## 🌐 Multilingual Tasks

```
How many languages?
│
├── Chinese + English
│   └── Qwen 3, DeepSeek, Doubao
│
├── European languages
│   └── Mistral Large, Gemini 3 Pro
│
├── 50+ languages
│   └── Gemini 3 Pro (best multilingual)
│
└── Low-resource languages
    └── GPT-5.2 or Gemini 3 Pro
```

**Winner by scenario:**
| Scenario | Best Model |
|----------|------------|
| Chinese NLP | Qwen 3, Doubao |
| European content | Mistral Large |
| Global deployment | Gemini 3 Pro |
| Translation | Google Translate API + Gemini |

---

## 💼 Enterprise Deployment

```
What's your primary constraint?
│
├── Data privacy/on-prem required
│   │
│   ├── Maximum capability → Llama 4 400B
│   ├── Balanced → Llama 4 70B
│   └── Edge deployment → Llama 4 8B
│
├── Compliance/audit trail
│   │
│   ├── SOC 2 needed → Claude (Anthropic), GPT (OpenAI)
│   └── HIPAA → Azure OpenAI, AWS Bedrock
│
├── Cost optimization
│   │
│   ├── High volume → Self-host Llama 4, DeepSeek
│   └── Variable volume → Pay-per-token APIs
│
└── SLA/reliability
    └── Azure OpenAI, AWS Bedrock, GCP Vertex
```

**Winner by scenario:**
| Scenario | Best Solution |
|----------|---------------|
| Air-gapped environment | Llama 4 (on-prem) |
| Financial services | Azure OpenAI (compliance) |
| Healthcare | AWS Bedrock (HIPAA) |
| Startup/scale-up | Direct API (Claude/OpenAI) |
| High-volume inference | Self-hosted vLLM |

---

## 📚 Research & Analysis

```
What type of research?
│
├── Literature review
│   │
│   ├── Many papers → Gemini 3 Pro (1M context)
│   └── Deep analysis → Claude Opus 4
│
├── Data analysis
│   │
│   ├── Code generation → Claude Opus 4
│   └── Statistical reasoning → GPT-5.2
│
├── Scientific writing
│   └── Claude Opus 4 (clear writing)
│
└── Fact verification
    └── GPT-5.2 (best SimpleQA)
```

---

## ⚡ Speed vs. Quality Trade-offs

| Priority | Best Choice |
|----------|-------------|
| Maximum quality | GPT-5.2, Claude Opus 4 |
| Balance (recommended) | Claude Sonnet 4, GPT-4o |
| Maximum speed | Claude Haiku 3, GPT-5.2-mini |
| Self-hosted speed | vLLM + Llama 4 |

---

## 💡 Quick Reference Table

| Task | Best Model | Runner-up |
|------|------------|-----------|
| Complex math | GPT-5.2 | DeepSeek R1 |
| Coding (SWE) | Claude Opus 4 | GPT-5.2 |
| Long context | Gemini 3 Pro | GPT-5.2 |
| Image gen | FLUX 1.1 Pro | Midjourney v6 |
| Video gen | Seedance 2.0 | Runway Gen-3 |
| Multilingual | Gemini 3 Pro | Qwen 3 |
| Budget | DeepSeek R1 | Qwen 3 |
| Self-host | Llama 4 | DeepSeek R1 |
| Privacy | Llama 4 (local) | Claude (Anthropic) |

---

*Updated: February 2026*
