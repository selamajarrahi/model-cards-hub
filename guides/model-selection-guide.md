# 🧭 Model Selection Guide

> A flowchart approach to choosing the right AI model for your needs

## Quick Selection Flowchart

```
START
  │
  ▼
┌─────────────────────────────────────┐
│ What are you trying to do?          │
└─────────────────────────────────────┘
  │
  ├─── Generate TEXT ──────────────────────────────────────────────────┐
  │                                                                     │
  ├─── Generate IMAGES ────────────────────────────────────────┐       │
  │                                                             │       │
  ├─── Generate VIDEO ─────────────────────────────────┐       │       │
  │                                                     │       │       │
  └─── Other ──► See "Specialized Tasks" below         │       │       │
                                                        │       │       │
                                                        ▼       ▼       ▼
                                                    [VIDEO]  [IMAGE]  [TEXT]
```

---

## Text/LLM Selection

```
┌─────────────────────────────────────┐
│ What's your PRIMARY requirement?    │
└─────────────────────────────────────┘
  │
  ├─── Maximum quality/capability
  │     │
  │     └───► Claude Opus 4 or GPT-5.2
  │           Best: Complex reasoning, nuanced writing, coding
  │
  ├─── Best value (quality/cost)
  │     │
  │     └───► Claude Sonnet 4 or DeepSeek R1
  │           Best: Most production workloads
  │
  ├─── Minimum cost
  │     │
  │     ├─── Need API? ───► DeepSeek V3 ($0.27/M)
  │     │
  │     └─── Can self-host? ───► Qwen 3 or Llama 3 (free)
  │
  ├─── Need to self-host / air-gapped
  │     │
  │     ├─── Best open model ───► DeepSeek R1 (MIT)
  │     │
  │     ├─── Smaller/faster ───► Qwen 3 (Apache 2.0)
  │     │
  │     └─── Meta ecosystem ───► Llama 3 (Community)
  │
  ├─── Agentic / Tool Use
  │     │
  │     ├─── Best overall ───► Claude Opus 4
  │     │
  │     └─── Open source ───► Kimi K2
  │
  ├─── Real-time information
  │     │
  │     └───► Grok 4 (live X/web data)
  │
  └─── Long context (>100K tokens)
        │
        └───► Gemini 3 Pro (1M+) or Claude (200K)
```

---

## Image Generation Selection

```
┌─────────────────────────────────────┐
│ What matters most for your images? │
└─────────────────────────────────────┘
  │
  ├─── Photorealism & accuracy
  │     │
  │     └───► FLUX 1.1 Pro
  │           Best: Product photos, realistic scenes
  │
  ├─── Artistic / stylized output
  │     │
  │     └───► Midjourney v6
  │           Best: Concept art, illustrations
  │
  ├─── Text rendering in images
  │     │
  │     └───► FLUX 1.1 Pro or DALL-E 4
  │           Best: Signs, logos, text overlays
  │
  ├─── Speed & iteration
  │     │
  │     └───► FLUX 1.1 Pro (6x faster than v1)
  │           Best: Rapid prototyping
  │
  ├─── Self-hosting / open weights
  │     │
  │     ├─── Best quality ───► FLUX.1 Dev (non-commercial)
  │     │
  │     └─── Commercial OK ───► Stable Diffusion 3
  │
  └─── Integrated with chat
        │
        └───► DALL-E 4 (via ChatGPT) or Grok (Aurora)
```

---

## Video Generation Selection

```
┌─────────────────────────────────────┐
│ What do you need from video?       │
└─────────────────────────────────────┘
  │
  ├─── Highest quality / consistency
  │     │
  │     └───► Seedance 2.0 or Sora 2
  │           Best: Professional content
  │
  ├─── Native audio sync
  │     │
  │     └───► Seedance 2.0 (built-in audio)
  │           Best: Music videos, dialogue
  │
  ├─── Longer clips (>1 min)
  │     │
  │     └───► Seedance 2.0 (up to 5 min)
  │           Best: Extended sequences
  │
  ├─── Image-to-video
  │     │
  │     ├─── Character animation ───► Seedance 2.0
  │     │
  │     └─── General motion ───► Kling 3.0
  │
  ├─── Budget-conscious
  │     │
  │     └───► Kling 3.0 or Pika
  │           Best: Social media content
  │
  └─── Quick access / no API
        │
        └───► Sora (via ChatGPT Pro $200/mo)
```

---

## By Use Case

### Chatbots & Assistants

| Scenario | Recommended | Why |
|----------|-------------|-----|
| Customer support | Claude Sonnet 4 | Safety, accuracy, cost |
| Personal assistant | GPT-4o | Good multimodal, fast |
| Coding assistant | Claude Opus 4 | Best code quality |
| Research assistant | DeepSeek R1 | Great reasoning, cheap |

### Content Creation

| Scenario | Recommended | Why |
|----------|-------------|-----|
| Blog writing | Claude Sonnet 4 | Quality + speed |
| Marketing copy | GPT-4o | Creative, on-brand |
| Technical docs | Claude Opus 4 | Accuracy, depth |
| Social posts | Qwen 3 | Fast, cheap |

### Development & Engineering

| Scenario | Recommended | Why |
|----------|-------------|-----|
| Code review | Claude Opus 4 | Deep understanding |
| Bug fixing | DeepSeek R1 | Reasoning chains |
| Architecture | Claude Opus 4 | Complex planning |
| Quick scripts | DeepSeek V3 | Speed + cost |

### Creative / Media

| Scenario | Recommended | Why |
|----------|-------------|-----|
| Product photos | FLUX 1.1 Pro | Photorealism |
| Concept art | Midjourney v6 | Style |
| Social video | Kling 3.0 | Cost + quality |
| Professional video | Seedance 2.0 | Highest quality |

---

## Decision Matrix

Score your requirements (1-5) and match:

| Requirement | Claude Opus | DeepSeek R1 | GPT-4o | Qwen 3 |
|-------------|-------------|-------------|--------|--------|
| Reasoning | 5 | 5 | 4 | 3 |
| Coding | 5 | 4 | 4 | 3 |
| Speed | 3 | 4 | 5 | 5 |
| Cost | 1 | 4 | 3 | 5 |
| Safety | 5 | 3 | 4 | 3 |
| Open source | 0 | 5 | 0 | 5 |
| Context | 5 | 4 | 4 | 4 |

**Scoring:**
- Total your priorities (weight × score)
- Highest total = best fit

---

## Red Flags / Avoid When...

### Don't use Claude Opus 4 when:
- ❌ Budget is tight (use Sonnet instead)
- ❌ You need real-time web data
- ❌ Latency is critical (slower responses)

### Don't use DeepSeek R1 when:
- ❌ Data privacy is paramount (Chinese company)
- ❌ You need guaranteed uptime (smaller provider)
- ❌ Strict compliance requirements

### Don't use GPT when:
- ❌ Self-hosting is required
- ❌ Maximum reasoning depth needed
- ❌ Cost sensitivity is high

### Don't use Midjourney when:
- ❌ You need text in images
- ❌ Exact prompt adherence required
- ❌ API integration needed (Discord-based)

---

## Still Unsure?

### Quick Default Recommendations

| Category | Default Choice | Runner-up |
|----------|---------------|-----------|
| LLM (general) | Claude Sonnet 4 | DeepSeek R1 |
| LLM (coding) | Claude Opus 4 | DeepSeek R1 |
| LLM (cheap) | DeepSeek V3 | Qwen 3 |
| Image (general) | FLUX 1.1 Pro | DALL-E 4 |
| Video (general) | Seedance 2.0 | Sora 2 |

### Test Before Committing

Most APIs offer free tiers or trials:
- Anthropic: $5 free credit
- OpenAI: $5 free credit  
- DeepSeek: $5 free credit
- BFL/FLUX: Pay-per-image (low minimums)

---

📚 **Next Steps:**
- [Comparison Matrix](comparison-matrix.md) - Detailed specs
- [Pricing Comparison](pricing-comparison.md) - Cost analysis
- [API Code Snippets](api-snippets.md) - Quick start code
