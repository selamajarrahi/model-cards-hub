# 📖 AI Glossary

> Key terms and concepts for understanding AI models

---

## A

### Attention
The mechanism that allows transformers to focus on relevant parts of the input when generating each output token. "Attention is all you need" (2017 paper) introduced this revolutionary concept.

### Alignment
The process of ensuring AI models behave according to human values and intentions. Techniques include RLHF, Constitutional AI, and fine-tuning.

### AWQ (Activation-aware Weight Quantization)
A quantization method that preserves model quality by analyzing which weights are most important during actual inference.

---

## B

### Batch Size
The number of examples processed together during training. Larger batches can be more efficient but require more memory.

### BERT
Bidirectional Encoder Representations from Transformers. An encoder-only model great for understanding tasks, but not generation.

### BF16 (bfloat16)
A 16-bit floating-point format optimized for deep learning, offering good range with reduced precision.

---

## C

### Chain-of-Thought (CoT)
A prompting technique where models "show their work" by reasoning through steps before giving a final answer.

### Constitutional AI
Anthropic's approach to alignment where the model is trained to follow a set of principles (a "constitution") that guide its behavior.

### Context Length / Context Window
The maximum number of tokens a model can process at once. Modern models range from 4K to 1M+ tokens.

### CUDA
NVIDIA's parallel computing platform that enables GPU-accelerated AI training and inference.

---

## D

### Diffusion Models
A type of generative model that learns to gradually remove noise from random inputs to produce images/video. Used by DALL-E 3, Stable Diffusion, FLUX.

### Distillation
Training a smaller "student" model to mimic a larger "teacher" model, often preserving most capabilities at lower cost.

---

## E

### Embedding
A numerical vector representation of text, images, or other data that captures semantic meaning. Similar items have similar embeddings.

### Emergent Abilities
Capabilities that appear suddenly as models scale, rather than improving gradually. Examples: few-shot learning, arithmetic.

### Extended Thinking
A technique where models use extra "thinking tokens" to reason through complex problems before responding (see Claude Opus 4, o1).

---

## F

### Few-Shot Learning
A model's ability to learn new tasks from just a few examples provided in the prompt.

### Fine-Tuning
Additional training on a specific dataset to specialize a pre-trained model for particular tasks or domains.

### Flash Attention
An optimized attention implementation that reduces memory usage and increases speed.

### FP16 (Float16)
16-bit floating-point precision, commonly used for efficient inference while maintaining good quality.

### FLOPS
Floating-Point Operations Per Second. A measure of computational power (e.g., H100 = 2 petaFLOPS).

---

## G

### GGUF
A file format for quantized models, optimized for llama.cpp and efficient CPU/GPU inference.

### GPTQ
A quantization method that reduces model size while maintaining quality, popular for self-hosting.

### Grounding
Connecting model outputs to real-world information or retrieved documents to reduce hallucinations.

---

## H

### Hallucination
When a model generates plausible-sounding but factually incorrect information.

### Hidden Dimension
The size of the internal representation in a transformer layer (e.g., 4096 in many models).

---

## I

### Inference
Using a trained model to generate outputs, as opposed to training. "Running" the model.

### In-Context Learning
A model's ability to learn from examples provided in the prompt without updating weights.

### INT8/INT4
8-bit or 4-bit integer quantization, dramatically reducing model size at some quality cost.

---

## K

### KV Cache
Key-Value cache storing attention computations to avoid recalculating for previous tokens. Critical for fast generation.

---

## L

### LoRA (Low-Rank Adaptation)
An efficient fine-tuning method that adds small trainable layers instead of updating all weights.

### Loss
The numerical measure of how wrong a model's predictions are during training. Training minimizes this.

---

## M

### Mixture of Experts (MoE)
An architecture where only a subset of model parameters are active for each input, enabling larger total models with reasonable compute (e.g., Kimi K2: 1T params, 32B active).

### Multimodal
Models that process multiple types of input (text, images, audio, video) and/or produce multiple output types.

---

## N

### Next-Token Prediction
The fundamental training objective for language models: predicting what comes next given previous context.

---

## O

### Overfitting
When a model memorizes training data too specifically and fails to generalize to new inputs.

---

## P

### Parameter
A single learnable value in a neural network. Modern LLMs have billions to trillions of parameters.

### Perplexity
A metric for language model quality - lower is better. Measures how "surprised" the model is by the test data.

### Pre-Training
The initial training phase where a model learns from massive amounts of data before task-specific fine-tuning.

### Prompt Engineering
The art of crafting inputs to get desired outputs from AI models.

---

## Q

### Quantization
Reducing the numerical precision of model weights to save memory and speed up inference (e.g., FP16 → INT4).

---

## R

### RAG (Retrieval-Augmented Generation)
Combining a language model with a retrieval system to ground responses in external documents.

### RLHF (Reinforcement Learning from Human Feedback)
A technique for aligning models by training them to produce outputs that humans prefer.

---

## S

### Scaling Laws
Empirical relationships showing how model performance improves with more compute, data, and parameters.

### Self-Attention
The specific attention mechanism where a sequence attends to itself (as opposed to cross-attention).

### Supervised Fine-Tuning (SFT)
Training on labeled examples (input-output pairs) to teach specific behaviors.

### System Prompt
Instructions given to a model that define its behavior, persona, or constraints for a conversation.

---

## T

### Temperature
A parameter controlling randomness in generation. Lower = more deterministic, higher = more creative.

### Tensor Parallelism
Splitting a model across multiple GPUs by dividing individual layers/tensors.

### Tokens
The basic units of text that models process. Roughly 1 token ≈ 4 characters or ¾ of a word in English.

### Top-K / Top-P
Sampling strategies that limit generation to the most likely tokens. Top-P (nucleus sampling) is most common.

### Transformer
The neural network architecture (2017) that powers modern LLMs. Based on self-attention.

---

## V

### Vector Database
A database optimized for storing and searching embeddings, used for RAG and semantic search.

### VRAM
Video RAM - the memory on GPUs. Critical constraint for running large models locally.

---

## W

### Weight
A parameter in a neural network, specifically the values in matrix multiplications.

### Window / Sliding Window Attention
Attention that only looks at a limited window of recent tokens, enabling longer sequences.

---

## Z

### Zero-Shot
A model's ability to perform tasks without any examples, just from instructions.

---

## Common Abbreviations

| Abbreviation | Meaning |
|--------------|---------|
| API | Application Programming Interface |
| CPU | Central Processing Unit |
| GPU | Graphics Processing Unit |
| LLM | Large Language Model |
| ML | Machine Learning |
| NLP | Natural Language Processing |
| OCR | Optical Character Recognition |
| TPU | Tensor Processing Unit (Google) |
| VLM | Vision Language Model |

---

## Benchmark Glossary

| Benchmark | What It Tests |
|-----------|--------------|
| MMLU | Multitask Language Understanding (broad knowledge) |
| HumanEval | Code generation |
| MATH | Mathematical problem solving |
| GSM8K | Grade school math word problems |
| HellaSwag | Commonsense reasoning |
| ARC | Scientific reasoning |
| TruthfulQA | Factual accuracy |
| MT-Bench | Multi-turn conversation quality |
| SWE-Bench | Real-world software engineering |

---

📚 **Related:**
- [Model Comparison Matrix](comparison-matrix.md)
- [Model Selection Guide](model-selection-guide.md)
