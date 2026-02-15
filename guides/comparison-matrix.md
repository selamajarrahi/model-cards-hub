# 📊 Model Comparison Matrix

> Side-by-side comparison of all models in the hub

## Language Models (LLMs)

| Model | Params | Context | Open Source | API | Best For |
|-------|--------|---------|-------------|-----|----------|
| **Claude Opus 4** | Unknown | 200K | ❌ | ✅ | Complex reasoning, coding, safety |
| **DeepSeek R1** | 671B MoE | 128K | ✅ MIT | ✅ | Open research, cost-effective |
| **Kimi K2** | 1T (32B active) | 128K | ✅ | ✅ | Agentic tasks, tool use |
| **Grok 4** | Unknown | 200K+ | ❌ | ✅ | Real-time info, humor |
| **Qwen 3** | Up to 235B | 128K | ✅ Apache 2.0 | ✅ | Cost-effective, multilingual |
| **Doubao-Seed-2.0** | Unknown | Unknown | ❌ | ✅ | Chinese market, general |
| **GPT-5.2** | Unknown | Unknown | ❌ | ✅ | General flagship |
| **Gemini 3 Pro** | Unknown | 1M+ | ❌ | ✅ | Multimodal, long context |

### Benchmark Comparison

| Model | MMLU | HumanEval | MATH | Reasoning |
|-------|------|-----------|------|-----------|
| Claude Opus 4 | ~92% | ~95% | ~85% | ⭐⭐⭐⭐⭐ |
| DeepSeek R1 | ~91% | ~92% | ~90% | ⭐⭐⭐⭐⭐ |
| Kimi K2 | ~89% | ~88% | ~82% | ⭐⭐⭐⭐ |
| Grok 4 | ~88% | ~85% | ~80% | ⭐⭐⭐⭐ |
| Qwen 3 | ~86% | ~82% | ~78% | ⭐⭐⭐⭐ |

---

## Video Generation Models

| Model | Max Resolution | Max Duration | Audio | Speed | Open Weights |
|-------|---------------|--------------|-------|-------|--------------|
| **Seedance 2.0** | 2K | 5 min | ✅ Native | ⭐⭐⭐ | ❌ |
| **Sora 2** | 1080p | 1 min | ❌ | ⭐⭐ | ❌ |
| **Kling 3.0** | 1080p | 3 min | ✅ | ⭐⭐⭐ | ❌ |
| **Veo 3.1** | 1080p | 2 min | ✅ | ⭐⭐ | ❌ |

### Quality Comparison

| Model | Motion | Consistency | Physics | Text Handling |
|-------|--------|-------------|---------|---------------|
| Seedance 2.0 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| Sora 2 | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| Veo 3.1 | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| Kling 3.0 | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |

---

## Image Generation Models

| Model | Best Resolution | Speed | Text Rendering | Style Control |
|-------|----------------|-------|----------------|---------------|
| **FLUX 1.1 Pro** | 2K+ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| **DALL-E 4** | 1024x1024 | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Imagen 3** | 2K | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Midjourney v6** | 2K | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ |

---

## Quick Selection Guide

### By Use Case

| If you need... | Best Choice |
|---------------|-------------|
| Complex reasoning | Claude Opus 4, DeepSeek R1 |
| Code generation | Claude Opus 4, DeepSeek R1 |
| Agentic/tool use | Kimi K2, Claude Opus 4 |
| Cost efficiency | Qwen 3, DeepSeek R1 |
| Real-time info | Grok 4 |
| Self-hosting | DeepSeek R1, Qwen 3 |
| Video with audio | Seedance 2.0, Veo 3.1 |
| Best image quality | FLUX 1.1 Pro |
| Artistic images | Midjourney v6 |

### By Budget

| Budget Level | LLM | Image | Video |
|--------------|-----|-------|-------|
| 💰 Free/Low | Qwen 3 (self-host) | FLUX.1 Dev | - |
| 💰💰 Medium | DeepSeek R1 API | FLUX 1.1 Pro | Kling |
| 💰💰💰 Premium | Claude Opus 4 | DALL-E 4 | Sora 2 |

---

## Feature Matrix

### LLM Capabilities

| Feature | Claude | DeepSeek | Kimi | Grok | Qwen |
|---------|--------|----------|------|------|------|
| Function Calling | ✅ | ✅ | ✅ | ✅ | ✅ |
| Vision | ✅ | ✅ | ✅ | ✅ | ✅ |
| Code Execution | ✅ | ✅ | ✅ | ✅ | ✅ |
| Extended Thinking | ✅ | ✅ | ❌ | ❌ | ❌ |
| Web Search | ❌ | ❌ | ✅ | ✅ | ❌ |
| File Analysis | ✅ | ✅ | ✅ | ✅ | ✅ |
| Streaming | ✅ | ✅ | ✅ | ✅ | ✅ |

### Multimodal Inputs

| Input Type | Claude | DeepSeek | Kimi | FLUX | Seedance |
|------------|--------|----------|------|------|----------|
| Text | ✅ | ✅ | ✅ | ✅ | ✅ |
| Images | ✅ | ✅ | ✅ | ✅ | ✅ |
| Documents | ✅ | ✅ | ✅ | ❌ | ❌ |
| Video | ❌ | ❌ | ✅ | ❌ | ✅ |
| Audio | ❌ | ❌ | ❌ | ❌ | ✅ |

---

📚 **See individual model cards for detailed specs:**
- [Language Models](../cards/) 
- [Pricing Comparison](pricing-comparison.md)
- [Model Selection Guide](model-selection-guide.md)
