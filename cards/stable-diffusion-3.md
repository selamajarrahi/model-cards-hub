# Stable Diffusion 3

> **Organization**: Stability AI  
> **Release**: February 2024 (updated 2025)  
> **Type**: Text-to-Image Generation  
> **License**: Stability AI Community License (open weights available)

## 🎯 Overview

Stable Diffusion 3 (SD3) is Stability AI's latest text-to-image model, featuring a **Multimodal Diffusion Transformer (MMDiT)** architecture that significantly improves text rendering and prompt following.

## 📊 Key Specifications

| Attribute | SD3 Medium | SD3 Large |
|-----------|------------|-----------|
| **Parameters** | 2B | 8B |
| **Resolution** | Up to 1024x1024 | Up to 1536x1536 |
| **Text Encoder** | CLIP + T5-XXL | CLIP + T5-XXL |
| **License** | Community | Community |

## 📈 Capabilities

### Text Rendering
SD3's major improvement: accurate text in images.

| Model | Text Accuracy |
|-------|---------------|
| SD3 | ~85% |
| SDXL | ~40% |
| Midjourney v5 | ~60% |

### Prompt Following

| Model | DrawBench Score |
|-------|-----------------|
| SD3 | 0.82 |
| SDXL | 0.71 |
| DALL-E 3 | 0.79 |

## 💻 Usage

### With diffusers

```python
from diffusers import StableDiffusion3Pipeline
import torch

pipe = StableDiffusion3Pipeline.from_pretrained(
    "stabilityai/stable-diffusion-3-medium",
    torch_dtype=torch.float16
)
pipe = pipe.to("cuda")

image = pipe(
    prompt="A photorealistic cat wearing a tiny wizard hat, holding a sign that says 'Magic!'",
    num_inference_steps=28,
    guidance_scale=7.0
).images[0]

image.save("wizard_cat.png")
```

### With ComfyUI

SD3 nodes are available in ComfyUI for workflow-based generation.

### API Access

```python
import requests

response = requests.post(
    "https://api.stability.ai/v2beta/stable-image/generate/sd3",
    headers={"Authorization": "Bearer YOUR_KEY"},
    files={"none": ""},
    data={
        "prompt": "A beautiful sunset over mountains",
        "output_format": "png"
    }
)

with open("output.png", "wb") as f:
    f.write(response.content)
```

## 💰 Pricing

### API (Stability AI)

| Resolution | Credits/Image |
|------------|---------------|
| 1024x1024 | 6.5 credits |
| 1536x1536 | 13 credits |

~$0.03-0.07 per image depending on plan.

### Self-Hosted

Free with your own GPU (8B model needs ~24GB VRAM).

## 🔑 Key Features

1. **Text Rendering**: Best-in-class text accuracy
2. **Prompt Following**: Excellent instruction adherence
3. **Open Weights**: Self-host for free
4. **Multiple Sizes**: 2B for speed, 8B for quality
5. **ControlNet**: Full ecosystem support

## ⚠️ Limitations

- Slower than SDXL (Turbo variants available)
- 8B model requires significant VRAM
- Some artistic styles less developed than SDXL

## 🆚 vs Alternatives

| Model | Text | Quality | Speed | Open |
|-------|------|---------|-------|------|
| SD3 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ✅ |
| FLUX | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ✅ |
| DALL-E 3 | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ❌ |
| Midjourney | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ❌ |

## 🔗 Resources

- **Model Hub**: [huggingface.co/stabilityai](https://huggingface.co/stabilityai/stable-diffusion-3-medium)
- **API Docs**: [platform.stability.ai](https://platform.stability.ai/docs)
- **ComfyUI**: [github.com/comfyanonymous/ComfyUI](https://github.com/comfyanonymous/ComfyUI)

---

*Added: February 2026*
