# Seedance 2.0

**Organization:** ByteDance  
**Release Date:** February 2026  
**Type:** Multimodal Video Generation  
**Status:** Beta (select users)

---

## Overview

Seedance 2.0 is ByteDance's next-generation AI video model featuring true multimodal input (text + image + video + audio) and native audio-visual synchronization.

**Key Innovations:**
- **4-modal input:** Accept text, images, videos, AND audio references
- **Native audio sync:** Audio-visual generated simultaneously (not cascaded)
- **@ mention system:** Tag each input with its role (@face_photo, @dance_video, etc.)
- **2K resolution:** Pro mode supports 2048×1152

---

## Specifications

| Spec | Value |
|------|-------|
| Input Modalities | 4 (Text + Image + Video + Audio) |
| Max Files | 12 total (9 images + 3 videos + 3 audio) |
| Resolution | 1080p native, 2K (2048×1152) in Pro |
| Duration | 4-15 seconds |
| Frame Rate | 24fps |
| Audio | Native audio-visual sync |
| Lip Sync | 8+ languages |
| Generation Speed | ~60s for 5s video (30% faster than 1.5) |

---

## Input System

### The @ Mention System

Seedance 2.0 uses an innovative tagging system to specify how each input is used:

| Tag | Purpose |
|-----|---------|
| `@face_photo` | Character's face reference |
| `@outfit_ref` | Clothing and style reference |
| `@dance_video` | Motion/choreography reference |
| `@bg_music` | Background music to sync with |
| `@voiceover` | Narration audio for lip-sync |

### Input Limits

| Modality | Max Files | Formats |
|----------|-----------|---------|
| Images | 9 | JPG, PNG, WebP |
| Videos | 3 | MP4, MOV |
| Audio | 3 | MP3, WAV, M4A |
| Text | Unlimited | Natural language |

---

## Native Audio-Visual Synchronization

Unlike cascaded approaches (generate video → add audio), Seedance 2.0 generates both **simultaneously**:

| Approach | Method | Result |
|----------|--------|--------|
| Cascaded (most models) | Video first, then audio | Audio drift, mismatched lips |
| **Joint Generation (Seedance 2.0)** | Video + audio in one pass | Perfect frame-level sync |

This enables:
- Footsteps landing exactly when feet touch ground
- Lip movements matching specific phonemes with ms precision
- Sound effects at exact frame of visual event

---

## Multi-Language Lip Sync

Supports phoneme-level lip synchronization in 8+ languages:

- English, Mandarin, Cantonese
- Japanese, Korean
- Spanish, French, German
- More being added

---

## Camera Control

| Movement | Description |
|----------|-------------|
| Push in / Pull out | Dolly zoom toward/away from subject |
| Tracking shot | Camera follows subject |
| Pan left/right | Horizontal rotation |
| Tilt up/down | Vertical rotation |
| Crane shot | Vertical camera movement |
| Hitchcock zoom | Dolly zoom (push + zoom out) |
| Orbit | Camera circles around subject |
| Static | Locked-off shot |

---

## Comparison vs Competitors

| Model | Duration | Resolution | Input Modes | Native Audio | Best For |
|-------|----------|------------|-------------|--------------|----------|
| **Seedance 2.0** | 4-15s | 2K | 4 | ✅ | Multimodal control |
| Sora 2 | 5-20s | 1080p | 2 | ✅ | Physics, narratives |
| Kling 3.0 | Up to 10s | 1080p | 2 | ✅ | Motion quality |
| Veo 3.1 | Up to 8s | 1080p | 2 | ✅ | Cinematic quality |

**Wavespeed.ai scores:** Seedance 2.0: 65/80 | Sora 2: 63/80

---

## Use Cases

| Use Case | Input Combo |
|----------|-------------|
| **E-Commerce** | Product images + brand guide + voiceover |
| **Music Videos** | Artist face + choreography + music track |
| **Social Media** | Face photo + trending audio |
| **Advertising** | Brand assets + spokesperson + script audio |
| **Education** | Presenter photo + voiceover + visual refs |

---

## Access

| Platform | Status | Notes |
|----------|--------|-------|
| Jimeng AI (Dreamina) | ✅ Available | China |
| Doubao App | ✅ Available | China |
| RecCloud (Global) | 🔜 Feb 24, 2026 | International |
| API | 🔜 Coming | Not yet launched |

---

## Resources

- **CNBC Coverage:** [Article](https://www.cnbc.com/2026/02/14/new-china-ai-models-alibaba-bytedance-seedance-kuaishou-kling.html)
- **Vibess Guide:** [Complete Guide](https://www.vibess.app/blog/seedance-2-0-complete-guide)
- **Reddit Discussion:** [r/singularity](https://www.reddit.com/r/singularity/comments/1r3g435/bytedance_releases_seedance_20_video_model_with/)
