# Text Embedding 3 (Large & Small)

> **Organization**: OpenAI  
> **Release**: January 2024 (updated 2025)  
> **Type**: Text Embedding Model  
> **Use Case**: Semantic search, RAG, clustering, classification

## 🎯 Overview

Text Embedding 3 is OpenAI's latest embedding model family, offering state-of-the-art performance for semantic similarity tasks. Available in two sizes: **Large** (best quality) and **Small** (cost-optimized).

## 📊 Key Specifications

| Attribute | text-embedding-3-large | text-embedding-3-small |
|-----------|------------------------|------------------------|
| **Dimensions** | 3,072 (or 256-3072) | 1,536 (or 256-1536) |
| **Max Tokens** | 8,191 | 8,191 |
| **Price/1M tokens** | $0.13 | $0.02 |
| **MTEB Score** | 64.6 | 62.3 |

## 📈 Benchmarks

### MTEB (Massive Text Embedding Benchmark)

| Model | Average Score | Retrieval | Clustering | Classification |
|-------|---------------|-----------|------------|----------------|
| text-embedding-3-large | **64.6** | 59.2 | 48.7 | 75.5 |
| text-embedding-3-small | 62.3 | 56.1 | 44.8 | 73.2 |
| text-embedding-ada-002 | 61.0 | 53.2 | 41.3 | 70.1 |
| Cohere embed-v3 | 64.4 | 58.8 | 47.1 | 74.8 |
| Voyage-2 | 63.8 | 57.9 | 46.2 | 73.9 |

### Retrieval Quality (NDCG@10)

| Model | MS MARCO | NQ | HotpotQA |
|-------|----------|-----|----------|
| text-embedding-3-large | **42.1** | 52.3 | 66.8 |
| text-embedding-3-small | 39.4 | 49.1 | 63.2 |
| ada-002 | 35.7 | 45.8 | 58.4 |

## 💻 Usage

### Basic Embedding

```python
from openai import OpenAI

client = OpenAI()

response = client.embeddings.create(
    model="text-embedding-3-large",
    input="The quick brown fox jumps over the lazy dog"
)

embedding = response.data[0].embedding
print(f"Dimensions: {len(embedding)}")  # 3072
```

### With Dimension Reduction

```python
# Native dimension reduction (no quality loss for smaller dims)
response = client.embeddings.create(
    model="text-embedding-3-large",
    input="Your text here",
    dimensions=1024  # Reduced from 3072
)

# Still high quality, smaller vectors
embedding = response.data[0].embedding  # length 1024
```

### Batch Processing

```python
# Embed multiple texts at once
texts = [
    "First document about AI",
    "Second document about ML",
    "Third document about NLP"
]

response = client.embeddings.create(
    model="text-embedding-3-small",
    input=texts
)

embeddings = [item.embedding for item in response.data]
```

### Similarity Search

```python
import numpy as np

def cosine_similarity(a, b):
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))

# Embed query and documents
query_embedding = get_embedding("What is machine learning?")
doc_embeddings = [get_embedding(doc) for doc in documents]

# Find most similar
similarities = [cosine_similarity(query_embedding, doc_emb) 
                for doc_emb in doc_embeddings]
most_similar_idx = np.argmax(similarities)
```

## 🔧 Integration Examples

### With Pinecone

```python
import pinecone

# Initialize
pinecone.init(api_key="YOUR_KEY")
index = pinecone.Index("my-index")

# Upsert embeddings
vectors = [
    (f"doc_{i}", embedding, {"text": text})
    for i, (text, embedding) in enumerate(zip(texts, embeddings))
]
index.upsert(vectors=vectors)

# Query
query_embedding = get_embedding("search query")
results = index.query(vector=query_embedding, top_k=5)
```

### With LangChain

```python
from langchain_openai import OpenAIEmbeddings
from langchain_community.vectorstores import Chroma

embeddings = OpenAIEmbeddings(model="text-embedding-3-large")

# Create vector store
vectorstore = Chroma.from_documents(
    documents=docs,
    embedding=embeddings
)

# Similarity search
results = vectorstore.similarity_search("query", k=5)
```

### With pgvector (PostgreSQL)

```sql
-- Create table with vector column
CREATE TABLE documents (
    id SERIAL PRIMARY KEY,
    content TEXT,
    embedding vector(3072)
);

-- Insert
INSERT INTO documents (content, embedding) 
VALUES ('Your text', '[0.1, 0.2, ...]');

-- Search
SELECT content, 1 - (embedding <=> query_embedding) AS similarity
FROM documents
ORDER BY embedding <=> query_embedding
LIMIT 5;
```

## 💡 Best Practices

### Choosing Dimensions

```
Use Case               Recommended Dimensions
──────────────────────────────────────────────
Maximum quality        3072 (full)
Balanced              1536
Cost-sensitive        1024
Very large scale      512 or 256
```

### Preprocessing

```python
def preprocess_for_embedding(text):
    # Remove extra whitespace
    text = " ".join(text.split())
    
    # Truncate if needed (8191 tokens ≈ 32K chars)
    if len(text) > 30000:
        text = text[:30000]
    
    return text
```

### Chunking Strategy

```python
from langchain.text_splitter import RecursiveCharacterTextSplitter

splitter = RecursiveCharacterTextSplitter(
    chunk_size=500,      # ~125 tokens
    chunk_overlap=50,    # Some overlap for context
    separators=["\n\n", "\n", ". ", " "]
)

chunks = splitter.split_text(long_document)
embeddings = [get_embedding(chunk) for chunk in chunks]
```

## 💰 Pricing Optimization

| Strategy | Savings |
|----------|---------|
| Use text-embedding-3-small | 6.5x cheaper |
| Reduce dimensions (1024) | ~Same cost, smaller storage |
| Cache embeddings | 100% for repeated texts |
| Batch requests | Reduce overhead |

## ⚠️ Limitations

- **Max tokens**: 8,191 (~32K characters)
- **Not multilingual-optimized**: Works but specialized models may be better
- **No fine-tuning**: Can't customize for domain
- **Rate limits**: Standard OpenAI limits apply

## 🆚 When to Choose

### text-embedding-3-large
- ✅ Maximum retrieval quality needed
- ✅ Production RAG systems
- ✅ Fine-grained similarity
- ✅ Small/medium dataset

### text-embedding-3-small
- ✅ Cost-sensitive applications
- ✅ Large-scale indexing
- ✅ Less critical similarity
- ✅ Prototyping

### Consider Alternatives
- **Multilingual**: Cohere multilingual-v3
- **Open source**: BGE, E5-mistral
- **Self-hosted**: sentence-transformers

## 🔗 Resources

- **API Docs**: [platform.openai.com/docs/guides/embeddings](https://platform.openai.com/docs/guides/embeddings)
- **Cookbook**: [github.com/openai/openai-cookbook](https://github.com/openai/openai-cookbook)
- **MTEB Leaderboard**: [huggingface.co/spaces/mteb/leaderboard](https://huggingface.co/spaces/mteb/leaderboard)

## 📚 Related Models

- [Cohere embed-v3](cohere-embed.md) - Alternative embedding
- [Voyage-2](voyage-2.md) - Specialized embeddings
- [BGE-M3](bge-m3.md) - Open-source option

---

*Added: February 2026*
