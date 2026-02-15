# Context Window Comparison Chart

> Compare context lengths across models and understand what they mean in practice.

---

## 📊 Context Window Overview

| Model | Context Window | ~Words | ~Pages |
|-------|---------------|--------|--------|
| Gemini 3 Pro | **1,000,000** | 750,000 | 3,000 |
| GPT-5.2 | 400,000 | 300,000 | 1,200 |
| Claude Opus 4 | 200,000 | 150,000 | 600 |
| Llama 4 400B | 128,000 | 96,000 | 384 |
| DeepSeek R1 | 128,000 | 96,000 | 384 |
| Qwen 3 235B | 128,000 | 96,000 | 384 |
| Mistral Large | 128,000 | 96,000 | 384 |
| Kimi K2 | 128,000 | 96,000 | 384 |
| Grok 4 | 131,072 | 98,304 | 393 |
| GPT-4 Turbo | 128,000 | 96,000 | 384 |
| Claude Sonnet 4 | 200,000 | 150,000 | 600 |

*~750 words per 1,000 tokens; ~250 words per page*

---

## 📈 Visual Comparison

```
Context Length (tokens)

Gemini 3 Pro     ████████████████████████████████████████████████████████████████████ 1M
GPT-5.2          ████████████████████████████████████████ 400K
Claude Opus 4    ████████████████████ 200K
Llama 4          ████████████ 128K
DeepSeek R1      ████████████ 128K
GPT-4 Turbo      ████████████ 128K
Mistral Large    ████████████ 128K
Qwen 3           ████████████ 128K
GPT-4o           ████████████ 128K
Claude Sonnet 3.5 ████████████████████ 200K
Llama 3.1        ████████████ 128K
GPT-3.5 Turbo    ████ 16K
```

---

## 📝 What Fits in Each Context?

### 16K Tokens (~12K words)
- ✅ One academic paper
- ✅ 2-3 short blog posts
- ✅ Small code file (~500 lines)
- ❌ Full codebase
- ❌ Book chapters

### 32K Tokens (~24K words)
- ✅ Long academic paper
- ✅ Small documentation set
- ✅ Medium code file (~1,000 lines)
- ❌ Multiple papers
- ❌ Large documents

### 128K Tokens (~96K words)
- ✅ Multiple academic papers (5-10)
- ✅ Small book (~380 pages)
- ✅ Codebase (~5,000 lines)
- ✅ Full API documentation
- ❌ Large novel
- ❌ Complete codebase

### 200K Tokens (~150K words)
- ✅ Medium book (~600 pages)
- ✅ Multiple codebases
- ✅ Extensive documentation
- ✅ Research literature review
- ❌ Very large documents

### 400K Tokens (~300K words)
- ✅ Large book or multiple books
- ✅ Enterprise codebase
- ✅ Comprehensive analysis of many documents
- ✅ Multi-hour meeting transcripts

### 1M Tokens (~750K words)
- ✅ Multiple large books
- ✅ Entire repository with history
- ✅ Video transcripts (hours)
- ✅ Complete project documentation
- ✅ Extensive research corpus

---

## ⚡ Effective Context vs. Raw Context

**Warning:** Raw context length ≠ useful context length

### The "Lost in the Middle" Problem

Models often struggle with information in the middle of long contexts:

```
Recall Accuracy by Position:
Beginning  ████████████████████ 95%
Middle     ███████████ 60%
End        █████████████████ 85%
```

### Recommendations by Context Length

| Usage | Recommended Approach |
|-------|---------------------|
| < 16K | Fill freely, all positions work well |
| 16-64K | Put important info at start/end |
| 64-128K | Consider chunking + retrieval |
| > 128K | RAG often outperforms raw context |

---

## 💰 Cost Implications

Longer contexts cost more:

| Model | Input Cost/1M | 128K Input Cost |
|-------|---------------|-----------------|
| Gemini 3 Pro | $15 (≤200K), $30 (>200K) | $1.92 |
| GPT-5.2 | $20 | $2.56 |
| Claude Opus 4 | $15 | $1.92 |
| Llama 4 (vLLM) | ~$0* | ~$0* |
| DeepSeek R1 | $0.55 | $0.07 |
| Qwen 3 | $0 (self-host) | $0* |

*Self-hosted models have infrastructure costs instead

### Cost Optimization Strategies

1. **Truncation**: Only include relevant portions
2. **Summarization**: Pre-summarize long documents
3. **RAG**: Retrieve only what's needed
4. **Caching**: Reuse common prefixes

---

## 🧪 Testing Context Utilization

### Needle in a Haystack Test

Insert a specific fact in the middle of a long context and test retrieval:

```python
def needle_test(model, context_length, position_pct):
    """Test if model can retrieve info at specific position."""
    
    needle = "The secret code is 42-ALPHA-7."
    
    # Create context with needle at position
    padding = "Lorem ipsum... " * (context_length // 20)
    insert_pos = int(len(padding) * position_pct)
    
    context = padding[:insert_pos] + needle + padding[insert_pos:]
    
    response = model.generate(
        f"Context: {context}\n\nWhat is the secret code?"
    )
    
    return "42-ALPHA-7" in response
```

### Results (Typical)

| Model | 25% | 50% | 75% | 95% |
|-------|-----|-----|-----|-----|
| GPT-5.2 | 100% | 98% | 99% | 100% |
| Claude Opus 4 | 100% | 97% | 98% | 100% |
| Gemini 3 Pro | 99% | 94% | 96% | 99% |
| Llama 4 | 98% | 88% | 92% | 97% |

---

## 📚 Practical Guidelines

### For Coding Tasks
```
Rule of thumb: Include 3-5x the context you think you need

Good context includes:
- The file being edited
- Related files (imports, interfaces)
- Tests for the module
- Documentation

Avoid:
- Entire codebase (use file selection)
- Generated files (build outputs)
- Binary files (obviously)
```

### For Analysis Tasks
```
Structure your context:

1. System prompt with clear instructions
2. Most relevant documents first
3. Supporting documents next
4. Query/question at the end

Consider: Would RAG give better results for your use case?
```

### For Conversations
```
Multi-turn conversations accumulate context:

Turn 1:  2K tokens
Turn 5:  10K tokens
Turn 20: 40K tokens
Turn 50: 100K tokens

Strategy: Periodically summarize conversation history
```

---

## 🔗 Related Guides

- [Model Selection Guide](model-selection-guide.md)
- [Pricing Comparison](pricing-comparison.md)
- [API Snippets](api-snippets.md)

---

*Updated: February 2026*
