# 💰 Model Pricing Comparison

> Up-to-date pricing for major AI models (as of February 2026)

## Language Models (LLMs)

### API Pricing per 1M Tokens

| Model | Input | Output | Notes |
|-------|-------|--------|-------|
| **Claude Opus 4** | $15.00 | $75.00 | Most capable Anthropic model |
| **Claude Sonnet 4** | $3.00 | $15.00 | Best value for most tasks |
| **GPT-5.2** | $10.00 | $30.00 | Estimated |
| **GPT-4o** | $2.50 | $10.00 | Multimodal flagship |
| **DeepSeek R1** | $0.55 | $2.19 | Open source, self-host free |
| **DeepSeek V3** | $0.27 | $1.10 | Fast, cheap, great value |
| **Kimi K2** | $0.60 | $2.00 | Chinese API pricing |
| **Grok 4** | $5.00 | $15.00 | X Premium+ included |
| **Qwen 3 (235B)** | $0.40 | $1.60 | Self-host free (Apache 2.0) |
| **Gemini 3 Pro** | $7.50 | $22.50 | 1M+ context |

### Monthly Cost Estimates

For a typical application processing 10M input + 2M output tokens/month:

| Model | Monthly Cost | vs Claude Sonnet |
|-------|--------------|-----------------|
| Claude Opus 4 | $300 | 10x |
| Claude Sonnet 4 | **$60** | baseline |
| GPT-4o | $45 | 0.75x |
| DeepSeek R1 | $10 | 0.17x |
| DeepSeek V3 | $5 | 0.08x |
| Qwen 3 (self-hosted) | $0* | 0x |

*Hardware costs not included

---

## Image Generation

### Per-Image Pricing

| Model | Standard | HD | Notes |
|-------|----------|-----|-------|
| **FLUX 1.1 Pro** | $0.04 | $0.08 | Via Replicate/BFL |
| **DALL-E 4** | $0.04 | $0.08 | 1024x1024 |
| **Midjourney v6** | ~$0.02* | ~$0.05* | Subscription based |
| **Imagen 3** | $0.03 | $0.06 | Via Vertex AI |
| **Stable Diffusion 3** | Free | Free | Self-host |

*Based on $30/month for ~1000 images

### Subscription Plans

| Service | Plan | Price/Month | Images |
|---------|------|-------------|--------|
| Midjourney | Basic | $10 | ~200 |
| Midjourney | Standard | $30 | Unlimited |
| Midjourney | Pro | $60 | Fast + Stealth |
| DALL-E (ChatGPT+) | Plus | $20 | Included |

---

## Video Generation

### Per-Video Pricing

| Model | 5 sec | 10 sec | 1 min | Notes |
|-------|-------|--------|-------|-------|
| **Seedance 2.0** | $0.50 | $1.00 | $5.00 | Est. Chinese pricing |
| **Sora 2** | $0.20 | $0.40 | $2.00 | ChatGPT Pro included |
| **Kling 3.0** | $0.15 | $0.30 | $1.50 | Kuaishou API |
| **Veo 3.1** | $0.30 | $0.60 | $3.00 | Vertex AI |
| **Runway Gen-3** | $0.25 | $0.50 | $2.50 | Standard plan |

### Subscription Plans

| Service | Plan | Price/Month | Credits |
|---------|------|-------------|---------|
| ChatGPT Pro | Pro | $200 | Sora unlimited |
| Runway | Basic | $12 | 125 credits |
| Runway | Standard | $28 | 625 credits |
| Runway | Pro | $76 | 2250 credits |
| Pika | Pro | $8 | 300 credits |

---

## Self-Hosting Cost Estimates

### GPU Requirements for Popular Models

| Model | Min VRAM | Recommended GPU | Rental Cost/hr |
|-------|----------|-----------------|----------------|
| DeepSeek R1 (Full) | 8x80GB | 8x H100 | ~$30/hr |
| DeepSeek R1 (Quant) | 4x48GB | 4x A6000 | ~$8/hr |
| Qwen 3 (72B) | 2x80GB | 2x H100 | ~$8/hr |
| Qwen 3 (7B) | 16GB | 1x RTX 4090 | ~$0.50/hr |
| Llama 3 (70B) | 2x48GB | 2x A6000 | ~$4/hr |
| Llama 3 (8B) | 8GB | 1x RTX 3080 | ~$0.20/hr |
| FLUX.1 Dev | 24GB | 1x RTX 4090 | ~$0.50/hr |

### Cloud Provider Comparison (per H100-hour)

| Provider | On-Demand | Reserved | Spot |
|----------|-----------|----------|------|
| AWS | $4.50 | $2.50 | $1.50 |
| GCP | $4.00 | $2.40 | $1.20 |
| Azure | $4.00 | $2.20 | $1.40 |
| Lambda Labs | $2.50 | $2.00 | - |
| RunPod | $2.00 | - | $1.00 |
| Vast.ai | - | - | $0.80 |

---

## Cost Optimization Tips

### 1. Use the Right Model for the Task

```
Simple Q&A      → DeepSeek V3 ($0.27/M) or Qwen 3
Complex reasoning → Claude Sonnet 4 ($3/M) 
Critical tasks   → Claude Opus 4 ($15/M)

Savings: Up to 50x by matching model to task
```

### 2. Prompt Caching

Most providers offer prompt caching discounts:

| Provider | Cache Discount | Max TTL |
|----------|---------------|---------|
| Anthropic | 90% off | 5 min |
| OpenAI | 50% off | 1 hr |
| DeepSeek | 75% off | 1 hr |

### 3. Batch Processing

| Provider | Batch Discount | Latency |
|----------|----------------|---------|
| OpenAI | 50% | 24h |
| Anthropic | 50% | 24h |

### 4. Self-Host When Volume Justifies

Break-even analysis for Qwen 3 (72B):

```
API cost: $0.40/M input + $1.60/M output
Self-host: ~$4/hr for 2x H100

Break-even: ~50M tokens/month

Below 50M: Use API
Above 50M: Consider self-hosting
```

---

## Free Tiers

| Provider | Free Tier |
|----------|-----------|
| Claude | $5 credits (new users) |
| OpenAI | $5 credits (new users) |
| DeepSeek | $5 credits |
| Groq | 14k tokens/min free |
| Together.ai | $5 credits |
| Google AI Studio | Free (with limits) |
| Hugging Face | Free inference (rate limited) |

---

## Price History & Trends

```
LLM Pricing Trend (per 1M output tokens):
═══════════════════════════════════════════
2023 Q1: GPT-4 →           $60.00 ███████████████████████
2023 Q4: GPT-4 Turbo →     $30.00 ████████████
2024 Q2: Claude 3.5 →      $15.00 ██████
2024 Q4: DeepSeek V3 →     $1.10  █
2025 Q4: DeepSeek R1 →     $2.19  █
2026 Q1: Qwen 3 →          $1.60  █

Trend: 10-50x cheaper every 18 months
```

---

⚠️ **Disclaimer:** Prices change frequently. Check official documentation for current rates.

📚 **Related:**
- [Model Comparison Matrix](comparison-matrix.md)
- [Self-Hosting Guide](self-hosting-guide.md)
