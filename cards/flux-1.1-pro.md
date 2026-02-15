# FLUX 1.1 Pro

**Organization:** Black Forest Labs  
**Release Date:** October 2024 (1.1 Pro update)  
**Type:** Image Generation (Text-to-Image)  
**Access:** [blackforestlabs.ai](https://blackforestlabs.ai)

---

## Overview

FLUX is Black Forest Labs' flagship image generation model, created by former Stability AI researchers (including the original Stable Diffusion team). FLUX 1.1 Pro offers state-of-the-art image quality with exceptional prompt adherence.

**Key Claims:**
- Best-in-class prompt following
- Exceptional detail and realism
- 6x faster than FLUX 1.0 Pro
- Strong text rendering in images

---

## Model Family

| Variant | Speed | Quality | Access |
|---------|-------|---------|--------|
| **FLUX 1.1 Pro** | Fast | Highest | API only |
| **FLUX 1.0 Pro** | Medium | Very High | API only |
| **FLUX 1.0 Dev** | Medium | High | Open (non-commercial) |
| **FLUX 1.0 Schnell** | Very Fast | Good | Open (Apache 2.0) |

---

## Specifications

| Spec | Value |
|------|-------|
| Architecture | Rectified Flow Transformer |
| Max Resolution | Up to 2048×2048 |
| Aspect Ratios | Flexible (1:1, 16:9, 9:16, etc.) |
| Output Formats | PNG, JPEG, WebP |
| Text Rendering | Strong (unlike most diffusion models) |

---

## Performance

### Quality Benchmarks (ELO ratings)

| Model | ELO | Notes |
|-------|-----|-------|
| **FLUX 1.1 Pro** | ~1150 | Current leader |
| Midjourney v6.1 | ~1140 | Close second |
| DALL-E 3 | ~1100 | OpenAI's best |
| Stable Diffusion 3 | ~1050 | Open source |
| Ideogram 2.0 | ~1130 | Strong text |

### Speed (FLUX 1.1 Pro)
- ~10 seconds per image at 1024×1024
- 6x faster than FLUX 1.0 Pro

---

## Pricing

### API (Black Forest Labs)

| Resolution | Cost per Image |
|------------|----------------|
| 1024×1024 | ~$0.04 |
| 1536×1536 | ~$0.06 |
| 2048×2048 | ~$0.08 |

### Third-Party Providers

| Provider | ~Cost per Image |
|----------|-----------------|
| Replicate | $0.03-0.05 |
| Together AI | $0.03-0.04 |
| fal.ai | $0.02-0.04 |

---

## Access

| Method | Status |
|--------|--------|
| BFL API | ✅ Available |
| Replicate | ✅ Available |
| fal.ai | ✅ Available |
| Together AI | ✅ Available |
| Self-host (Pro) | ❌ API only |
| Self-host (Dev/Schnell) | ✅ Weights available |

---

## Key Features

### 1. Prompt Adherence
FLUX excels at following complex, detailed prompts — including specific object placement, counting, and relationships.

### 2. Text Rendering
Unlike most image models, FLUX can reliably render text within images (signs, labels, etc.).

### 3. Photorealism
Exceptional at generating photorealistic images with natural lighting and detail.

### 4. Consistency
Low variance between generations — prompts produce predictable results.

### 5. LoRA Support
FLUX Dev/Schnell support custom LoRA fine-tuning for style and subject consistency.

---

## Comparison vs Alternatives

| Model | Quality | Speed | Price | Text | Open |
|-------|---------|-------|-------|------|------|
| **FLUX 1.1 Pro** | Best | Fast | Low | Great | ❌ |
| Midjourney v6.1 | Excellent | Medium | Mid | Good | ❌ |
| DALL-E 3 | Very Good | Fast | High | OK | ❌ |
| Ideogram 2.0 | Excellent | Medium | Mid | Best | ❌ |
| SD3 / SDXL | Good | Fast | Free | Poor | ✅ |
| FLUX Schnell | Good | Very Fast | Free | OK | ✅ |

---

## Best For

- **Production image generation** at scale
- **Marketing/advertising** content
- **Product visualization**
- Applications requiring **text in images**
- **Photorealistic** renders
- **Rapid iteration** (fast generation)

---

## Open Source Options

If you need self-hosting:

| Model | License | Quality |
|-------|---------|---------|
| FLUX Schnell | Apache 2.0 | Good |
| FLUX Dev | Non-commercial | High |
| Stable Diffusion 3 | Stability License | Good |

---

## Resources

- **Official:** [blackforestlabs.ai](https://blackforestlabs.ai)
- **API Docs:** [docs.bfl.ml](https://docs.bfl.ml)
- **HuggingFace:** [black-forest-labs](https://huggingface.co/black-forest-labs)
- **Replicate:** [replicate.com/black-forest-labs](https://replicate.com/black-forest-labs)

---

## Team Background

Black Forest Labs was founded by former Stability AI researchers, including key contributors to the original Stable Diffusion. FLUX represents their vision for next-generation image synthesis.
