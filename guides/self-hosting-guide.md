# 🖥️ Self-Hosting Guide for Open Models

> Run AI models on your own hardware or cloud infrastructure

---

## Why Self-Host?

| Benefit | Details |
|---------|---------|
| **Privacy** | Data never leaves your infrastructure |
| **Cost** | Can be cheaper at scale (50M+ tokens/month) |
| **Customization** | Fine-tune, modify, no restrictions |
| **Availability** | No rate limits, no API outages |
| **Compliance** | Meet data residency requirements |

---

## Quick Start: Which Model?

### Best Open Models by Size

| VRAM Available | Recommended Model | Quality vs GPT-4 |
|----------------|-------------------|------------------|
| 4GB | Phi-3 Mini (3.8B) | ~60% |
| 8GB | Llama 3 8B / Qwen 2.5 7B | ~70% |
| 16GB | Mistral 7B / Qwen 2.5 14B | ~75% |
| 24GB | Qwen 2.5 32B | ~85% |
| 48GB | Llama 3 70B (4-bit) | ~90% |
| 80GB | DeepSeek R1 (quantized) | ~95% |
| 160GB+ | DeepSeek R1 / Qwen 235B | ~95%+ |

---

## Method 1: Ollama (Easiest)

**Best for:** Personal use, quick experimentation

### Installation

```bash
# macOS / Linux
curl -fsSL https://ollama.com/install.sh | sh

# Windows
# Download from https://ollama.com/download
```

### Running Models

```bash
# Download and run a model
ollama run llama3:8b

# Other popular models
ollama run mistral
ollama run qwen2.5:14b
ollama run deepseek-r1:32b  # If you have the VRAM
```

### API Access

```python
import requests

response = requests.post(
    "http://localhost:11434/api/generate",
    json={
        "model": "llama3:8b",
        "prompt": "Hello!",
        "stream": False
    }
)
print(response.json()["response"])
```

---

## Method 2: vLLM (Production)

**Best for:** High-throughput production deployments

### Installation

```bash
pip install vllm
```

### Running Server

```bash
# Serve a model
python -m vllm.entrypoints.openai.api_server \
    --model meta-llama/Llama-3-8b-instruct \
    --port 8000

# With quantization for larger models
python -m vllm.entrypoints.openai.api_server \
    --model Qwen/Qwen2.5-72B-Instruct \
    --quantization awq \
    --tensor-parallel-size 2  # For multi-GPU
```

### Using with OpenAI SDK

```python
from openai import OpenAI

client = OpenAI(
    base_url="http://localhost:8000/v1",
    api_key="dummy"
)

response = client.chat.completions.create(
    model="meta-llama/Llama-3-8b-instruct",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

### Performance Tips

```bash
# Enable continuous batching (automatic in vLLM)
# Enable PagedAttention (automatic)
# Set max batch size for throughput
--max-num-batched-tokens 32768
```

---

## Method 3: Text Generation Inference (TGI)

**Best for:** Docker-based deployments, Hugging Face ecosystem

### Running with Docker

```bash
# Pull and run
docker run --gpus all -p 8080:80 \
    -v $PWD/data:/data \
    ghcr.io/huggingface/text-generation-inference:latest \
    --model-id meta-llama/Llama-3-8b-instruct \
    --max-input-length 4096 \
    --max-total-tokens 8192
```

### API Usage

```python
import requests

response = requests.post(
    "http://localhost:8080/generate",
    json={
        "inputs": "Hello!",
        "parameters": {"max_new_tokens": 100}
    }
)
```

---

## Method 4: llama.cpp (CPU/Efficiency)

**Best for:** CPU inference, laptops, edge devices

### Installation

```bash
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp
make -j

# With GPU acceleration
make LLAMA_CUDA=1
```

### Running

```bash
# Download GGUF model from HuggingFace
wget https://huggingface.co/TheBloke/Llama-3-8B-Instruct-GGUF/resolve/main/llama-3-8b-instruct.Q4_K_M.gguf

# Run
./main -m llama-3-8b-instruct.Q4_K_M.gguf \
    -p "Hello!" \
    -n 100
```

### Server Mode

```bash
./server -m llama-3-8b-instruct.Q4_K_M.gguf \
    --port 8080 \
    --ctx-size 4096
```

---

## Quantization Guide

### Understanding Quantization

| Format | Size Reduction | Quality Loss | Speed |
|--------|---------------|--------------|-------|
| FP16 | 2x (baseline) | None | Baseline |
| INT8 | 4x | Minimal | ~Same |
| INT4/GGUF Q4 | 8x | Small | Faster |
| GPTQ | 8x | Small | Needs GPU |
| AWQ | 8x | Minimal | Fast on GPU |
| GGUF Q2 | 16x | Noticeable | Fastest |

### Choosing Quantization

```
For most uses:     Q4_K_M (GGUF) or AWQ
For max quality:   Q6_K or Q8_0 (GGUF) or INT8
For max speed:     Q2_K (GGUF)
```

### Converting Models

```bash
# Using llama.cpp for GGUF
python convert_hf_to_gguf.py model_path --outtype q4_k_m

# Using AutoGPTQ
from transformers import AutoModelForCausalLM
model = AutoModelForCausalLM.from_pretrained(
    "model_path",
    load_in_4bit=True,
    device_map="auto"
)
```

---

## Hardware Requirements

### GPU Memory Guide

| Model | FP16 | INT8 | INT4 |
|-------|------|------|------|
| 7B | 14GB | 7GB | 4GB |
| 13B | 26GB | 13GB | 7GB |
| 34B | 68GB | 34GB | 17GB |
| 70B | 140GB | 70GB | 35GB |
| 235B | 470GB | 235GB | 120GB |
| 671B (MoE) | ~200GB* | ~100GB* | ~50GB* |

*MoE models only load active experts

### Recommended Setups

| Budget | Setup | Models You Can Run |
|--------|-------|-------------------|
| $500 | RTX 3060 12GB | 7B INT4 |
| $1000 | RTX 4070 Ti 16GB | 13B INT4, 7B INT8 |
| $2000 | RTX 4090 24GB | 34B INT4, 13B FP16 |
| $5000 | 2x RTX 4090 | 70B INT4 |
| $15000 | A100 80GB | 70B FP16 |
| $50000 | 4x H100 80GB | 235B, DeepSeek R1 |

---

## Cloud Deployment Options

### GPU Cloud Providers

| Provider | $/hr (H100) | Min Commit | Notes |
|----------|-------------|------------|-------|
| RunPod | $2.00 | None | Easy, community |
| Vast.ai | $0.80-2.00 | None | Marketplace |
| Lambda Labs | $2.50 | None | Simple |
| CoreWeave | $2.50 | Contract | Enterprise |
| AWS | $4.50 | None | Most features |
| GCP | $4.00 | None | Good tooling |

### Quick Deploy: RunPod

```bash
# 1. Create account at runpod.io
# 2. Select GPU (e.g., RTX 4090)
# 3. Use template: "RunPod vLLM"
# 4. Set environment variables:
MODEL_NAME=Qwen/Qwen2.5-72B-Instruct
QUANTIZATION=awq
```

### Quick Deploy: Docker Compose

```yaml
# docker-compose.yml
version: '3.8'
services:
  llm:
    image: ghcr.io/huggingface/text-generation-inference:latest
    deploy:
      resources:
        reservations:
          devices:
            - capabilities: [gpu]
    ports:
      - "8080:80"
    volumes:
      - ./models:/data
    environment:
      - MODEL_ID=meta-llama/Llama-3-8b-instruct
      - MAX_INPUT_LENGTH=4096
      - MAX_TOTAL_TOKENS=8192
```

---

## Specific Model Guides

### DeepSeek R1

```bash
# Requires significant VRAM (8x80GB for full, 4x48GB quantized)

# Using vLLM with tensor parallelism
python -m vllm.entrypoints.openai.api_server \
    --model deepseek-ai/DeepSeek-R1 \
    --tensor-parallel-size 8 \
    --trust-remote-code

# Smaller distilled version
ollama run deepseek-r1:32b
```

### Qwen 2.5 72B

```bash
# Using AWQ quantization (needs ~40GB VRAM)
python -m vllm.entrypoints.openai.api_server \
    --model Qwen/Qwen2.5-72B-Instruct-AWQ \
    --quantization awq \
    --tensor-parallel-size 2
```

### Llama 3 70B

```bash
# With 2x 24GB GPUs
python -m vllm.entrypoints.openai.api_server \
    --model meta-llama/Meta-Llama-3-70B-Instruct \
    --tensor-parallel-size 2 \
    --dtype float16
```

---

## Performance Optimization

### Key Optimizations

```python
# 1. Enable Flash Attention
pip install flash-attn

# 2. Use PagedAttention (vLLM default)

# 3. Continuous batching (vLLM/TGI default)

# 4. KV cache quantization
--kv-cache-dtype fp8

# 5. Speculative decoding (if supported)
--speculative-model small_model
```

### Benchmarking

```bash
# vLLM benchmarking
python benchmarks/benchmark_serving.py \
    --model meta-llama/Llama-3-8b-instruct \
    --num-prompts 100 \
    --request-rate 10
```

---

## Common Issues

### Out of Memory

```bash
# Solutions:
1. Use quantization (AWQ, GPTQ, GGUF)
2. Reduce batch size: --max-num-seqs 64
3. Reduce context: --max-model-len 4096
4. Use tensor parallelism across GPUs
```

### Slow Inference

```bash
# Solutions:
1. Ensure GPU is being used (check nvidia-smi)
2. Enable Flash Attention
3. Use vLLM or TGI (not raw transformers)
4. Consider smaller quantization
```

### Model Won't Load

```bash
# Common fixes:
1. Accept model license on HuggingFace
2. Set HF_TOKEN environment variable
3. Check disk space for model download
4. Verify CUDA version compatibility
```

---

## Security Considerations

1. **Network Isolation:** Don't expose to internet without auth
2. **Input Validation:** Limit prompt length, filter inputs
3. **Rate Limiting:** Prevent abuse
4. **Logging:** Track usage for auditing
5. **Updates:** Keep dependencies patched

### Basic Auth Example

```python
# FastAPI wrapper with auth
from fastapi import FastAPI, Depends, HTTPException
from fastapi.security import HTTPBasic, HTTPBasicCredentials

app = FastAPI()
security = HTTPBasic()

def verify(credentials: HTTPBasicCredentials = Depends(security)):
    if credentials.username != "user" or credentials.password != "pass":
        raise HTTPException(status_code=401)
    return credentials

@app.post("/generate")
def generate(prompt: str, credentials = Depends(verify)):
    # Call your model
    pass
```

---

📚 **Related:**
- [Model Comparison Matrix](comparison-matrix.md)
- [Pricing Comparison](pricing-comparison.md) (break-even analysis)
- [API Code Snippets](api-snippets.md)
