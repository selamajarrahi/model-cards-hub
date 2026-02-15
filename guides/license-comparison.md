# ⚖️ AI Model License Comparison

> Understanding what you can and can't do with different AI models

---

## Quick Reference Table

| Model | License | Commercial Use | Modify | Self-Host | Derivatives |
|-------|---------|----------------|--------|-----------|-------------|
| **DeepSeek R1** | MIT | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes |
| **Qwen 3** | Apache 2.0 | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes |
| **Llama 3** | Meta Community | ✅ Yes* | ✅ Yes | ✅ Yes | ⚠️ Restrictions |
| **Mistral** | Apache 2.0 | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes |
| **FLUX.1 Dev** | Non-commercial | ❌ No | ✅ Yes | ✅ Yes | ⚠️ NC only |
| **FLUX.1 Pro** | Proprietary | ✅ API only | ❌ No | ❌ No | ❌ No |
| **Claude** | Proprietary | ✅ API only | ❌ No | ❌ No | ❌ No |
| **GPT-4** | Proprietary | ✅ API only | ❌ No | ❌ No | ❌ No |
| **Stable Diffusion 3** | Community | ✅ Yes* | ✅ Yes | ✅ Yes | ⚠️ Restrictions |

*With conditions - see details below

---

## License Types Explained

### MIT License (Most Permissive)
**Examples:** DeepSeek R1, DeepSeek V3

✅ **You CAN:**
- Use commercially without restrictions
- Modify the code/weights
- Distribute modified versions
- Use for any purpose
- Sublicense

✅ **You MUST:**
- Include original copyright notice
- Include the license text

❌ **You CANNOT:**
- Hold authors liable

**Best for:** Maximum freedom, commercial products

---

### Apache 2.0 License
**Examples:** Qwen, Mistral, Gemma

✅ **You CAN:**
- Use commercially
- Modify and distribute
- Patent use (explicit grant)
- Sublicense

✅ **You MUST:**
- Include original copyright
- State changes made
- Include NOTICE file if present
- Include license text

❌ **You CANNOT:**
- Use trademarks
- Hold authors liable

**Best for:** Commercial use with clear patent protection

---

### Meta Llama Community License
**Examples:** Llama 3, Llama 2

✅ **You CAN:**
- Use commercially (if <700M monthly users)
- Modify weights
- Create derivatives
- Self-host

⚠️ **You MUST:**
- Accept Meta's terms
- Include "Built with Llama" attribution
- Request license if >700M users
- Follow acceptable use policy

❌ **You CANNOT:**
- Use for >700M users without permission
- Train other LLMs with outputs (in some versions)
- Violate acceptable use policy

**Best for:** Most commercial applications, with scale limits

---

### Non-Commercial Licenses
**Examples:** FLUX.1 Dev, some Stable Diffusion variants

✅ **You CAN:**
- Use for research
- Use for personal projects
- Modify and experiment
- Share non-commercially

❌ **You CANNOT:**
- Use in commercial products
- Sell access to the model
- Use for commercial services

**Best for:** Research, hobbyists, testing before buying commercial

---

### Proprietary (API-Only)
**Examples:** Claude, GPT-4, DALL-E, Midjourney

✅ **You CAN:**
- Use via API commercially
- Use outputs commercially (usually)
- Build products using API

❌ **You CANNOT:**
- Access weights
- Self-host
- Modify the model
- Reverse engineer

✅ **You OWN:**
- Usually your outputs (check ToS)
- Your prompts/data (usually, check ToS)

**Best for:** When you need best quality and don't need self-hosting

---

## Commercial Use Checklist

### Launching a Commercial Product?

```
□ Identify which model(s) you're using
□ Read the full license text
□ Check monthly user limits (Llama)
□ Verify commercial use is allowed
□ Check attribution requirements
□ Review acceptable use policies
□ Consider: Do you need to self-host?
□ Consider: Do you need to modify weights?
□ Consult legal if significant revenue expected
```

### Safe Choices for Commercial

| Use Case | Safest Choice | Why |
|----------|--------------|-----|
| Startup MVP | Qwen (Apache) | No restrictions |
| Enterprise | DeepSeek (MIT) | Maximum freedom |
| API product | Claude/GPT | Clear commercial terms |
| High-scale | Llama + license | Best quality open |
| Research | Any open model | Most have research clause |

---

## Output Ownership

### Who Owns Model Outputs?

| Provider | Output Ownership | Can Train On? |
|----------|-----------------|---------------|
| OpenAI | User owns | Yes (with terms) |
| Anthropic | User owns | Yes (with terms) |
| Google | User owns | Check current ToS |
| DeepSeek | User owns | Yes |
| Llama | User owns | Model-dependent |
| FLUX | Depends on license | Research only (Dev) |

### Important Considerations

1. **Outputs may still be subject to:**
   - Copyright of training data
   - Local laws
   - Provider's acceptable use policy

2. **You generally cannot:**
   - Claim copyright on purely AI-generated content (US)
   - Use outputs that violate usage policies
   - Generate content that infringes others' IP

---

## Fine-Tuning & Derivatives

### Can You Fine-Tune and Distribute?

| Model | Fine-Tune | Distribute FT Model | Sell FT Model |
|-------|-----------|--------------------|--------------| 
| DeepSeek | ✅ | ✅ | ✅ |
| Qwen | ✅ | ✅ | ✅ |
| Llama 3 | ✅ | ✅ (with attribution) | ✅* |
| Mistral | ✅ | ✅ | ✅ |
| FLUX Dev | ✅ | ✅ (NC only) | ❌ |

*Subject to 700M user limit and terms

---

## Red Flags to Watch For

### 🚩 Vague Commercial Terms
Some licenses use unclear language. When in doubt:
- Contact the provider
- Consult a lawyer
- Choose a clearer license (MIT/Apache)

### 🚩 Retroactive Changes
Some providers reserve right to change terms. Mitigations:
- Snapshot specific version
- Document license at time of download
- Consider irrevocable licenses (MIT, Apache)

### 🚩 Output Restrictions
Some models restrict:
- Generating competing AI training data
- Certain content types
- Specific use cases

**Always read the acceptable use policy!**

---

## Quick Decision Tree

```
Do you need to self-host?
├── Yes → Is commercial use required?
│   ├── Yes → Qwen (Apache) or DeepSeek (MIT)
│   └── No → Any open model (check license)
│
└── No → Is the API model acceptable?
    ├── Yes → Use Claude/GPT/etc. (check ToS)
    └── No → You need open weights
            → See self-host branch above
```

---

## License Text Links

| Model | License Link |
|-------|-------------|
| DeepSeek | [MIT License](https://github.com/deepseek-ai/DeepSeek-R1/blob/main/LICENSE) |
| Qwen | [Apache 2.0](https://github.com/QwenLM/Qwen/blob/main/LICENSE) |
| Llama 3 | [Meta License](https://llama.meta.com/llama3/license/) |
| Mistral | [Apache 2.0](https://mistral.ai/licenses/) |
| FLUX | [BFL Licenses](https://github.com/black-forest-labs/flux) |
| Claude | [Anthropic ToS](https://www.anthropic.com/legal/terms) |
| OpenAI | [OpenAI ToS](https://openai.com/policies/terms-of-use) |

---

⚠️ **Disclaimer:** This is not legal advice. Always read the actual license text and consult a lawyer for commercial use.

📚 **Related:**
- [Model Comparison Matrix](comparison-matrix.md)
- [Self-Hosting Guide](self-hosting-guide.md)
