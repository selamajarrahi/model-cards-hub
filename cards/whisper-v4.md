# Whisper v4

> **Organization**: OpenAI  
> **Release**: December 2025  
> **Type**: Speech Recognition / Audio Understanding  
> **License**: MIT (Open Source)

## 🎯 Overview

Whisper v4 is OpenAI's latest automatic speech recognition (ASR) model, achieving **near-human accuracy** across 100+ languages. It features improved noise robustness, speaker diarization, and real-time streaming capabilities.

## 📊 Key Specifications

| Attribute | Value |
|-----------|-------|
| **Parameters** | 1.5B (large-v4) |
| **Languages** | 100+ |
| **Audio Input** | Up to 30 minutes per chunk |
| **Sample Rate** | 16kHz (resampled internally) |
| **Output** | Text, timestamps, language detection |

## 📈 Benchmarks

### Word Error Rate (WER) - English

| Model | LibriSpeech Clean | LibriSpeech Other | Earnings Calls |
|-------|-------------------|-------------------|----------------|
| Whisper v4 | **1.8%** | **3.2%** | **5.1%** |
| Whisper v3 | 2.7% | 5.1% | 8.2% |
| Google USM | 2.1% | 4.3% | 6.8% |
| Azure Speech | 2.4% | 4.8% | 7.1% |

### Multilingual Performance (Average WER)

| Model | Top 10 Languages | 50+ Languages | Long-tail |
|-------|------------------|---------------|-----------|
| Whisper v4 | **4.2%** | **7.8%** | **15.2%** |
| Whisper v3 | 5.8% | 10.1% | 22.4% |
| Google USM | 4.8% | 8.9% | 18.1% |

## 💻 Usage

### With OpenAI API

```python
from openai import OpenAI

client = OpenAI()

# Transcribe audio file
with open("audio.mp3", "rb") as f:
    transcript = client.audio.transcriptions.create(
        model="whisper-v4",
        file=f,
        response_format="verbose_json"
    )

print(transcript.text)
print(transcript.segments)  # With timestamps
```

### With Hugging Face Transformers

```python
from transformers import WhisperProcessor, WhisperForConditionalGeneration
import torch

processor = WhisperProcessor.from_pretrained("openai/whisper-large-v4")
model = WhisperForConditionalGeneration.from_pretrained("openai/whisper-large-v4")

# Load audio
audio, sr = librosa.load("audio.mp3", sr=16000)

# Process
input_features = processor(audio, return_tensors="pt").input_features
generated_ids = model.generate(input_features)
transcription = processor.batch_decode(generated_ids, skip_special_tokens=True)
```

### Streaming (Real-time)

```python
import whisper_streaming

# Real-time transcription
async for segment in whisper_streaming.transcribe_stream(audio_stream):
    print(f"[{segment.start:.2f}s] {segment.text}")
```

### With Speaker Diarization

```python
# Using pyannote for diarization + Whisper
from pyannote.audio import Pipeline
import whisper

# Get speaker segments
diarization = Pipeline.from_pretrained("pyannote/speaker-diarization")
speakers = diarization("audio.wav")

# Transcribe and align
result = whisper.transcribe("audio.wav")

for segment, speaker in align(result.segments, speakers):
    print(f"[{speaker}] {segment.text}")
```

## 📦 Model Variants

| Variant | Parameters | Speed | Quality | Use Case |
|---------|------------|-------|---------|----------|
| whisper-tiny | 39M | ⚡⚡⚡⚡ | ⭐ | Edge devices |
| whisper-base | 74M | ⚡⚡⚡ | ⭐⭐ | Real-time, mobile |
| whisper-small | 244M | ⚡⚡ | ⭐⭐⭐ | Balanced |
| whisper-medium | 769M | ⚡ | ⭐⭐⭐⭐ | Accuracy focus |
| whisper-large-v4 | 1.5B | ⚡ | ⭐⭐⭐⭐⭐ | Maximum quality |
| whisper-turbo | 809M | ⚡⚡⚡ | ⭐⭐⭐⭐ | Speed + quality |

## 🔑 Key Features

### 1. Near-Human Accuracy
- 1.8% WER on clean English
- Robust to accents and dialects
- Strong on technical vocabulary

### 2. Speaker Diarization
- Native multi-speaker support
- "Who said what" timestamps
- Integration with pyannote

### 3. Noise Robustness
- Background music handling
- Environmental noise rejection
- Overlapping speech

### 4. Streaming Support
- Real-time transcription
- Low-latency mode
- Partial results

### 5. Language Detection
- Automatic language identification
- Code-switching support
- 100+ languages

## 💰 Pricing

### OpenAI API
| Model | Price per Minute |
|-------|------------------|
| whisper-v4 | $0.006 |
| whisper-turbo | $0.004 |

### Self-Hosted (Approximate)
| Setup | Cost per Hour |
|-------|---------------|
| GPU (A100) | ~$0.50-1.00 |
| CPU only | ~$0.10-0.20 |

## ⚠️ Limitations

- **Hallucinations**: Can generate plausible but incorrect text
- **Numbers/Names**: Struggles with proper nouns, phone numbers
- **Music**: Lyrics transcription is inconsistent
- **30-minute chunks**: Needs chunking for longer audio

## 🔧 Best Practices

### Pre-processing
```python
# Optimal audio format
# - 16kHz sample rate
# - Mono channel
# - Normalized volume
# - Remove silence (optional)

import librosa
import soundfile as sf

audio, sr = librosa.load("input.mp3", sr=16000, mono=True)
audio = librosa.util.normalize(audio)
sf.write("processed.wav", audio, 16000)
```

### Prompting for Domain Adaptation
```python
# Use initial_prompt for domain terms
result = client.audio.transcriptions.create(
    model="whisper-v4",
    file=audio_file,
    prompt="Meeting about AI, featuring CEO John Smith and CTO Jane Doe."
)
```

### Handling Long Audio
```python
from pydub import AudioSegment

# Split into 25-minute chunks with 5-second overlap
audio = AudioSegment.from_file("long_audio.mp3")
chunk_length = 25 * 60 * 1000  # 25 min in ms
overlap = 5 * 1000  # 5 sec overlap

chunks = []
for i in range(0, len(audio), chunk_length - overlap):
    chunks.append(audio[i:i + chunk_length])
```

## 🔗 Resources

- **API Documentation**: [platform.openai.com/docs/guides/speech-to-text](https://platform.openai.com/docs/guides/speech-to-text)
- **GitHub (Original)**: [github.com/openai/whisper](https://github.com/openai/whisper)
- **Hugging Face**: [huggingface.co/openai/whisper-large-v4](https://huggingface.co/openai/whisper-large-v4)
- **Paper**: [arXiv:2212.04356](https://arxiv.org/abs/2212.04356) (v1)

## 📚 Related Models

- [AssemblyAI Universal-2](assembly-ai.md) - Commercial alternative
- [Azure Speech](azure-speech.md) - Microsoft's offering
- [Google USM](google-usm.md) - Google's ASR

---

*Added: February 2026*
