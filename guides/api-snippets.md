# 💻 API Code Snippets

> Quick-start code for calling major AI model APIs

---

## Language Models

### Claude (Anthropic)

```python
# pip install anthropic
from anthropic import Anthropic

client = Anthropic(api_key="your-api-key")

message = client.messages.create(
    model="claude-sonnet-4-20250514",  # or "claude-opus-4-20250514"
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "Explain quantum computing in simple terms."}
    ]
)
print(message.content[0].text)
```

**With Vision:**
```python
import base64

with open("image.png", "rb") as f:
    image_data = base64.standard_b64encode(f.read()).decode("utf-8")

message = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=1024,
    messages=[{
        "role": "user",
        "content": [
            {"type": "image", "source": {"type": "base64", "media_type": "image/png", "data": image_data}},
            {"type": "text", "text": "What's in this image?"}
        ]
    }]
)
```

**With Extended Thinking:**
```python
message = client.messages.create(
    model="claude-opus-4-20250514",
    max_tokens=8000,
    thinking={
        "type": "enabled",
        "budget_tokens": 5000
    },
    messages=[{"role": "user", "content": "Solve this complex problem..."}]
)
```

---

### OpenAI (GPT)

```python
# pip install openai
from openai import OpenAI

client = OpenAI(api_key="your-api-key")

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain quantum computing in simple terms."}
    ]
)
print(response.choices[0].message.content)
```

**With Vision:**
```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{
        "role": "user",
        "content": [
            {"type": "text", "text": "What's in this image?"},
            {"type": "image_url", "image_url": {"url": "https://example.com/image.png"}}
        ]
    }]
)
```

**With Function Calling:**
```python
tools = [{
    "type": "function",
    "function": {
        "name": "get_weather",
        "description": "Get current weather for a location",
        "parameters": {
            "type": "object",
            "properties": {
                "location": {"type": "string", "description": "City name"}
            },
            "required": ["location"]
        }
    }
}]

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "What's the weather in Tokyo?"}],
    tools=tools
)
```

---

### DeepSeek

```python
# pip install openai (uses OpenAI-compatible API)
from openai import OpenAI

client = OpenAI(
    api_key="your-deepseek-api-key",
    base_url="https://api.deepseek.com/v1"
)

response = client.chat.completions.create(
    model="deepseek-reasoner",  # R1 model
    messages=[
        {"role": "user", "content": "Solve this step by step: What is 15% of 847?"}
    ]
)
print(response.choices[0].message.content)
```

---

### Google Gemini

```python
# pip install google-generativeai
import google.generativeai as genai

genai.configure(api_key="your-api-key")
model = genai.GenerativeModel("gemini-2.0-flash")

response = model.generate_content("Explain quantum computing in simple terms.")
print(response.text)
```

**With Vision:**
```python
import PIL.Image

image = PIL.Image.open("image.png")
response = model.generate_content(["What's in this image?", image])
```

---

### Qwen (via Together.ai or Self-Hosted)

```python
# Via Together.ai
from openai import OpenAI

client = OpenAI(
    api_key="your-together-api-key",
    base_url="https://api.together.xyz/v1"
)

response = client.chat.completions.create(
    model="Qwen/Qwen2.5-72B-Instruct-Turbo",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

---

## Image Generation

### FLUX (via Replicate)

```python
# pip install replicate
import replicate

output = replicate.run(
    "black-forest-labs/flux-1.1-pro",
    input={
        "prompt": "A serene Japanese garden with cherry blossoms, photorealistic",
        "aspect_ratio": "16:9",
        "output_format": "webp"
    }
)
print(output)  # Returns image URL
```

### FLUX (via BFL API)

```python
import requests

response = requests.post(
    "https://api.bfl.ml/v1/flux-pro-1.1",
    headers={"x-key": "your-bfl-api-key"},
    json={
        "prompt": "A serene Japanese garden with cherry blossoms",
        "width": 1024,
        "height": 768
    }
)
result = response.json()
print(result["sample"])  # Image URL
```

### DALL-E

```python
from openai import OpenAI

client = OpenAI(api_key="your-api-key")

response = client.images.generate(
    model="dall-e-3",
    prompt="A serene Japanese garden with cherry blossoms",
    size="1024x1024",
    quality="hd",
    n=1
)
print(response.data[0].url)
```

### Stable Diffusion (via Stability AI)

```python
import requests

response = requests.post(
    "https://api.stability.ai/v1/generation/stable-diffusion-xl-1024-v1-0/text-to-image",
    headers={
        "Authorization": f"Bearer your-api-key",
        "Content-Type": "application/json",
    },
    json={
        "text_prompts": [{"text": "A serene Japanese garden"}],
        "cfg_scale": 7,
        "height": 1024,
        "width": 1024,
        "samples": 1,
    }
)
```

---

## Video Generation

### Runway Gen-3

```python
import requests

# Create generation
response = requests.post(
    "https://api.runwayml.com/v1/generations",
    headers={"Authorization": f"Bearer your-api-key"},
    json={
        "model": "gen-3-alpha",
        "prompt": "A cat playing piano, cinematic lighting",
        "duration": 5
    }
)
task_id = response.json()["id"]

# Poll for result
# ... (check status endpoint until complete)
```

### Replicate (Various Video Models)

```python
import replicate

output = replicate.run(
    "minimax/video-01",
    input={
        "prompt": "A cat playing piano",
        "prompt_optimizer": True
    }
)
```

---

## Embeddings

### OpenAI

```python
from openai import OpenAI

client = OpenAI(api_key="your-api-key")

response = client.embeddings.create(
    model="text-embedding-3-large",
    input="Your text to embed"
)
embedding = response.data[0].embedding
```

### Cohere

```python
import cohere

co = cohere.Client("your-api-key")

response = co.embed(
    texts=["Hello world"],
    model="embed-english-v3.0"
)
print(response.embeddings)
```

---

## Streaming Responses

### Claude Streaming

```python
with client.messages.stream(
    model="claude-sonnet-4-20250514",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Tell me a story"}]
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
```

### OpenAI Streaming

```python
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Tell me a story"}],
    stream=True
)
for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

---

## Error Handling Best Practices

```python
import time
from anthropic import APIError, RateLimitError

def call_with_retry(func, max_retries=3):
    for attempt in range(max_retries):
        try:
            return func()
        except RateLimitError:
            wait = 2 ** attempt
            print(f"Rate limited, waiting {wait}s...")
            time.sleep(wait)
        except APIError as e:
            print(f"API error: {e}")
            raise
    raise Exception("Max retries exceeded")
```

---

## Environment Setup

### Recommended .env file
```bash
# .env
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...
DEEPSEEK_API_KEY=sk-...
GOOGLE_API_KEY=AIza...
REPLICATE_API_TOKEN=r8_...
TOGETHER_API_KEY=...
```

### Loading in Python
```python
from dotenv import load_dotenv
import os

load_dotenv()
api_key = os.getenv("ANTHROPIC_API_KEY")
```

---

📚 **Related:**
- [Model Comparison Matrix](comparison-matrix.md)
- [Pricing Comparison](pricing-comparison.md)
- [Model Selection Guide](model-selection-guide.md)
