# 🌳 AI Model Family Trees

> Understanding the lineages and evolution of major AI models

---

## OpenAI / GPT Family

```
GPT-1 (2018)
    │ 117M parameters
    │ Introduced transformer decoder for generation
    │
    └─► GPT-2 (2019)
        │ 1.5B parameters
        │ "Too dangerous to release" (later released)
        │
        └─► GPT-3 (2020)
            │ 175B parameters
            │ Few-shot learning breakthrough
            │
            ├─► GPT-3.5 (2022)
            │   │ ChatGPT's original model
            │   │ RLHF introduction
            │   │
            │   └─► GPT-3.5-Turbo
            │       Faster, cheaper API
            │
            └─► GPT-4 (2023)
                │ Multimodal (vision)
                │ Significant reasoning improvement
                │
                ├─► GPT-4-Turbo (2023)
                │   │ 128K context, cheaper
                │   │
                │   └─► GPT-4o (2024)
                │       │ Omni model, native multimodal
                │       │ Audio, image, video understanding
                │       │
                │       └─► GPT-4o-mini
                │           Smaller, faster, cheaper
                │
                └─► o1 / o3 (2024-2025)
                    │ Reasoning models
                    │ "Thinking" tokens
                    │
                    └─► GPT-5 / GPT-5.2 (2025-2026)
                        Next generation flagship
```

---

## Anthropic / Claude Family

```
Constitutional AI Research (2022)
    │ RLHF + Constitutional approach
    │
    └─► Claude 1.0 (2023)
        │ First public model
        │
        └─► Claude 1.3 / Claude Instant
            │ Improved speed and quality
            │
            └─► Claude 2.0 (2023)
                │ 100K context
                │
                └─► Claude 2.1
                    │ 200K context
                    │
                    └─► Claude 3 Family (2024)
                        │
                        ├─► Claude 3 Haiku
                        │   Fast, cheap, good
                        │
                        ├─► Claude 3 Sonnet
                        │   Best value
                        │
                        └─► Claude 3 Opus
                            │ Most capable
                            │
                            └─► Claude 3.5 Sonnet (2024)
                                │ Opus-level at Sonnet price
                                │
                                └─► Claude 4 Family (2025)
                                    │
                                    ├─► Claude Sonnet 4
                                    │   Production workhorse
                                    │
                                    └─► Claude Opus 4
                                        Extended thinking
                                        Best coding/reasoning
```

---

## Meta / Llama Family

```
OPT (2022)
    │ Open Pre-trained Transformer
    │ Research release, various sizes
    │
    └─► LLaMA 1 (2023)
        │ "Leaked" then open-sourced
        │ 7B, 13B, 33B, 65B
        │ Spawned entire ecosystem
        │
        ├─► Alpaca (Stanford)
        │   Fine-tuned on instructions
        │
        ├─► Vicuna
        │   ShareGPT conversations
        │
        ├─► Koala, WizardLM, etc.
        │   Various community fine-tunes
        │
        └─► Llama 2 (2023)
            │ Official Meta release
            │ 7B, 13B, 70B + Chat variants
            │ Commercial license
            │
            ├─► Code Llama
            │   Code-specialized
            │
            └─► Llama 3 (2024)
                │ 8B, 70B (later 405B)
                │ Much improved quality
                │
                ├─► Llama 3.1
                │   128K context
                │
                ├─► Llama 3.2
                │   │ Multimodal (vision)
                │   │ Smaller sizes (1B, 3B)
                │   │
                │   └─► Llama 3.3
                │       70B quality at lower cost
                │
                └─► Llama 4 (Expected 2026)
                    MoE architecture?
```

---

## Chinese AI Labs

### Alibaba / Qwen

```
Qwen (2023)
    │ First release, 7B-72B
    │
    └─► Qwen 1.5 (2024)
        │ Improved multilingual
        │
        └─► Qwen 2 (2024)
            │ Better reasoning
            │ Code & Math focus
            │
            └─► Qwen 2.5 (2024)
                │ Up to 72B
                │ Strong benchmarks
                │
                └─► Qwen 3 (2025)
                    Up to 235B
                    Apache 2.0
                    Near-GPT-4 quality
```

### DeepSeek

```
DeepSeek LLM (2023)
    │ Initial 7B-67B models
    │
    └─► DeepSeek-Coder (2024)
        │ Code-specialized
        │
        └─► DeepSeek V2 (2024)
            │ MoE architecture
            │ Very cost-efficient
            │
            └─► DeepSeek V3 (2024)
                │ 671B MoE
                │ $0.27/M tokens
                │
                └─► DeepSeek R1 (2025)
                    │ Reasoning model
                    │ Matches o1
                    │ MIT license
                    │
                    └─► DeepSeek R1 Distilled
                        Various sizes (7B-70B)
```

### Moonshot / Kimi

```
Kimi (2024)
    │ 128K context pioneer
    │
    └─► Kimi K1 (2024)
        │ Improved reasoning
        │
        └─► Kimi K2 (2025)
            1T parameters (32B active)
            MoE architecture
            Muon optimizer
            Agentic focus
```

---

## Google / DeepMind

```
BERT (2018) ─────────────────────────────────────────┐
    │ Encoder-only, revolutionized NLU              │
    │                                                │
T5 (2020) ───────────────────────────────┐          │
    │ Encoder-decoder                    │          │
    │                                    │          │
PaLM (2022) ◄────────────────────────────┴──────────┘
    │ 540B parameters
    │
    └─► PaLM 2 (2023)
        │ Powering Bard (then Gemini)
        │
        └─► Gemini 1.0 (2023)
            │ Nano, Pro, Ultra
            │ Native multimodal
            │
            ├─► Gemini 1.5 Pro (2024)
            │   │ 1M context
            │   │
            │   └─► Gemini 1.5 Flash
            │       Fast & cheap
            │
            └─► Gemini 2.0 Flash (2024)
                │ Improved speed & quality
                │
                └─► Gemini 3 (2025-2026)
                    Pro, Ultra
                    Next generation
```

---

## Image Generation

### Stability AI / Stable Diffusion

```
Stable Diffusion 1.x (2022)
    │ Open source revolution
    │ Latent diffusion
    │
    └─► Stable Diffusion 2.x (2022)
        │ Improved quality, controversies
        │
        └─► SDXL (2023)
            │ 1024x1024 native
            │
            ├─► SDXL-Turbo
            │   Few-step generation
            │
            └─► Stable Diffusion 3 (2024)
                │ MMDiT architecture
                │
                └─► SD 3.5 (2024)
                    Improved quality
```

### Black Forest Labs / FLUX

```
(Stable Diffusion creators left)
    │
    └─► FLUX.1 (2024)
        │ Pro, Dev, Schnell variants
        │ Best-in-class quality
        │
        └─► FLUX 1.1 Pro (2024)
            │ 6x faster
            │ Better quality
            │
            └─► FLUX 2.0 (Expected 2026)
                Video support?
```

### OpenAI / DALL-E

```
DALL-E 1 (2021)
    │ First text-to-image transformer
    │
    └─► DALL-E 2 (2022)
        │ Diffusion-based
        │ Much improved
        │
        └─► DALL-E 3 (2023)
            │ Native ChatGPT integration
            │ Better text rendering
            │
            └─► DALL-E 4 (Expected)
```

---

## Video Generation

```
Make-A-Video (Meta, 2022) ────────────────────────┐
    │ Early research                              │
    │                                             │
Imagen Video (Google, 2022) ──────────────────────┤
    │ Research milestone                          │
    │                                             │
Gen-2 (Runway, 2023) ◄────────────────────────────┤
    │ First practical tool                        │
    │                                             │
Sora (OpenAI, 2024) ◄─────────────────────────────┘
    │ Transformer-based
    │ 60s+ videos
    │
├─► Kling (Kuaishou)
│   Chinese competitor
│
├─► Veo (Google)
│   Gemini-powered
│
└─► Seedance (ByteDance)
    Multi-modal input
    Native audio
```

---

## Key Takeaways

### Trends Across Families

1. **Scaling:** Models get bigger, then efficient (MoE)
2. **Multimodal:** Vision → Audio → Video
3. **Context:** 4K → 128K → 1M+
4. **Reasoning:** RLHF → Chain-of-thought → Thinking tokens
5. **Open Source:** Catching up to closed models

### Who's Winning?

| Category | Current Leader | Rising Challenger |
|----------|---------------|-------------------|
| Flagship LLM | Claude Opus 4 | GPT-5 |
| Value LLM | DeepSeek R1 | Qwen 3 |
| Open Source | DeepSeek R1 | Llama 4 |
| Image | FLUX 1.1 Pro | - |
| Video | Sora 2 | Seedance 2.0 |

---

📚 **Related:**
- [Model Comparison Matrix](comparison-matrix.md)
- [Models to Watch](models-to-watch.md)
