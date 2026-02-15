# Gemini 3 Pro

> **Organization**: Google DeepMind  
> **Release**: January 2026  
> **Type**: Multimodal Large Language Model

## 🎯 Overview

Gemini 3 Pro is Google's flagship multimodal model, leading benchmarks in vision, video understanding, and multilingual capabilities. It features a **1M token context window** and native multimodal understanding across text, images, audio, and video.

## 📊 Key Specifications

| Attribute | Value |
|-----------|-------|
| **Parameters** | Undisclosed (MoE architecture) |
| **Context Window** | 1,000,000 tokens |
| **Training Data** | Through December 2025 |
| **Architecture** | Sparse MoE with native multimodal |
| **Modalities** | Text, Images, Audio, Video (input/output) |

## 📈 Benchmarks

### Multimodal Understanding

| Benchmark | Gemini 3 Pro | GPT-5.2 | Claude Opus 4 |
|-----------|--------------|---------|---------------|
| MMMU (vision) | **72.3%** | 68.1% | 65.4% |
| Video-MME | **84.2%** | 76.8% | 71.2% |
| DocVQA | **95.1%** | 92.4% | 90.8% |
| ChartQA | **91.8%** | 88.2% | 86.5% |

### Reasoning & Knowledge

| Benchmark | Gemini 3 Pro | GPT-5.2 | Claude Opus 4 |
|-----------|--------------|---------|---------------|
| MMLU | 92.4% | **93.7%** | 90.2% |
| MATH | 91.2% | **94.8%** | 89.2% |
| GSM8K | 98.1% | **99.2%** | 97.8% |
| ARC-Challenge | **98.7%** | 97.2% | 96.8% |

### Multilingual

| Benchmark | Gemini 3 Pro | GPT-5.2 | Claude Opus 4 |
|-----------|--------------|---------|---------------|
| MMMLU (avg) | **88.4%** | 85.2% | 82.1% |
| XL-Sum | **45.2** | 42.1 | 40.8 |
| Flores-200 | **42.8** | 39.4 | 38.2 |

## 💻 API Access

### Basic Usage (Python)

```python
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

model = genai.GenerativeModel("gemini-3-pro")

response = model.generate_content("Explain quantum computing")
print(response.text)
```

### Multimodal Input

```python
import PIL.Image

# Image understanding
image = PIL.Image.open("diagram.png")
response = model.generate_content([
    "Explain this diagram in detail:",
    image
])

# Video understanding
video_file = genai.upload_file("lecture.mp4")
response = model.generate_content([
    "Summarize the key points from this lecture:",
    video_file
])
```

### Extended Context (1M tokens)

```python
# Load multiple documents
documents = [open(f"doc_{i}.txt").read() for i in range(100)]
combined = "\n---\n".join(documents)

response = model.generate_content([
    "Analyze all these documents and find common themes:",
    combined
])
```

### Streaming

```python
response = model.generate_content(
    "Write a detailed analysis...",
    stream=True
)

for chunk in response:
    print(chunk.text, end="")
```

## 💰 Pricing

| Model | Input (per 1M tokens) | Output (per 1M tokens) |
|-------|----------------------|------------------------|
| Gemini 3 Pro | $15.00 | $45.00 |
| Gemini 3 Pro (>200K context) | $30.00 | $90.00 |
| Gemini 3 Flash | $0.15 | $0.60 |

*Pricing as of February 2026. Images/video billed by content.*

## 🔑 Key Features

### 1. Million Token Context
- Process entire codebases
- Analyze hours of video
- Multi-document reasoning
- Maintain coherence at scale

### 2. Native Multimodal
- Images, audio, video input
- Image generation output
- Cross-modal reasoning
- Real-time video understanding

### 3. Multilingual Excellence
- 100+ languages
- Cultural context awareness
- Cross-lingual reasoning
- Translation & localization

### 4. Google Integration
- Search grounding
- Google Workspace integration
- Cloud AI Platform deployment
- Vertex AI features

## ⚠️ Limitations

- **Regional availability**: Some features limited by region
- **Video processing**: Long videos may have delays
- **Factual precision**: Can lag GPT-5.2 on precise facts
- **Cost at scale**: Premium pricing for extended context

## 🆚 When to Choose Gemini 3 Pro

### Choose Gemini 3 Pro When:
- ✅ Multimodal tasks (especially video)
- ✅ Very long context needed (>400K tokens)
- ✅ Multilingual applications
- ✅ Google Cloud/Workspace ecosystem
- ✅ Document/image understanding focus

### Consider Alternatives When:
- ❌ Maximum reasoning accuracy needed (GPT-5.2)
- ❌ Coding-heavy workflows (Claude Opus 4)
- ❌ Privacy-sensitive (consider open-source)
- ❌ Cost-sensitive applications

## 🔧 Available Variants

| Variant | Context | Best For |
|---------|---------|----------|
| Gemini 3 Pro | 1M | Full capability |
| Gemini 3 Flash | 1M | Speed/cost balance |
| Gemini 3 Nano | 32K | On-device |

## 🔗 Resources

- **API Documentation**: [ai.google.dev/docs](https://ai.google.dev/docs)
- **AI Studio**: [aistudio.google.com](https://aistudio.google.com)
- **Vertex AI**: [cloud.google.com/vertex-ai](https://cloud.google.com/vertex-ai)
- **Technical Report**: [deepmind.google/gemini-3](https://deepmind.google/gemini-3)

## 📚 Related Models

- [Gemini 3 Flash](gemini-3-flash.md) - Faster, cheaper variant
- [GPT-5.2](gpt-5.2.md) - OpenAI's competitor
- [Claude Opus 4](claude-opus-4.md) - Anthropic's competitor

---

*Added: February 2026*
