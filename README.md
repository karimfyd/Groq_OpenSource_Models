

# ⚡ Groq API (2026) — Complete Guide

> Open-Source Models · Pricing · Free Tier · Use Cases

Groq has redefined AI inference with its revolutionary **Language Processing Unit (LPU)** architecture, delivering unprecedented speed for open-source models. With token generation rates exceeding **1,000 tokens/second** on certain models and a generous free tier, Groq is the go-to platform for developers who need real-time AI performance without breaking the bank.

---

## Table of Contents

- [What Makes Groq Different?](#-what-makes-groq-different)
- [Free Tier](#-groq-api-free-tier)
- [Available Models](#-available-models)
  - [Production Models](#production-models)
  - [Preview Models](#preview-models)
  - [Audio Models](#audio-models)
  - [Batch API](#batch-api)
- [Which Model Should You Use?](#-which-model-should-you-use)
- [Performance Benchmarks](#-performance-benchmarks)
- [Pricing & Optimization](#-pricing--optimization)
- [Production Recommendations](#-production-recommendations)
- [Getting Started](#-getting-started-in-under-5-minutes)

---

## ⚡ What Makes Groq Different?

Groq's custom **LPU (Language Processing Unit)** Inference Engine is purpose-built for running LLMs at extremely high speed with deterministic, predictable performance.

| Feature | Detail |
|---|---|
| Latency | Millisecond response times for real-time apps |
| Speed advantage | Up to **3–4x faster** than traditional GPU-based models |
| Token generation | **500–1,000+ tokens/sec** on supported models |
| Consistency | Deterministic performance ideal for production SLAs |

---

## 🆓 Groq API Free Tier

GroqCloud offers a generous **free tier** — no credit card required.

### What's Included

- Access to most production models (Llama 3, Mixtral, Gemma families)
- Community Tier with daily quotas for all registered users
- Commercial use ✅ (with attribution on free tier)

### Developer Plan Rate Limits

| Limit Type | Free Tier / Developer Plan |
|---|---|
| Tokens per minute | 150K–300K TPM (varies by model) |
| Requests per minute | 250–1,000 RPM |
| Context window | Up to 131,072 tokens |
| Commercial use | ✅ Yes (with attribution) |
| Production SLA | ❌ Requires paid plan |

> ⚠️ Rate limits vary by model. Check the [GroqCloud Console](https://console.groq.com) for your account's current quotas.

### When to Enable Billing

Enable billing (pay-as-you-go) when you need:

- Higher throughput and rate limits
- Production-grade reliability
- Batch API access (50% discount)
- Removal of attribution requirements

---

## 🧠 Available Models

### Production Models

> Ready for production use — meet Groq's standards for speed, quality, and reliability.

| Model ID | Display Name | Speed (tok/s) | Context | Input / Output (per 1M) | Best For |
|---|---|---|---|---|---|
| `llama-3.3-70b-versatile` | Llama 3.3 70B | 500 | 131,072 | $0.15 / $0.60 | Enterprise reasoning, complex tasks |
| `llama-3.1-8b-instant` | Llama 3.1 8B Instant | 1,000 | 131,072 | $0.075 / $0.30 | High-speed chat, lightweight tasks |
| `meta-llama/llama-4-maverick-17b-128e-instruct` | Llama 4 Maverick | 560 | 131,072 | $0.05 / $0.08 | Cost-effective, balanced performance |
| `meta-llama/llama-4-scout-17b-16e-instruct` | Llama 4 Scout | 280 | 131,072 | $0.59 / $0.79 | High-quality generation |
| `openai/gpt-oss-20b` | GPT-OSS 20B | — | — | Batch only | Batch processing |
| `openai/gpt-oss-120b` | GPT-OSS 120B | — | — | Batch only | Large-scale batch processing |
| `meta-llama/llama-guard-4-12b` | Llama Guard 4 12B | — | — | See docs | Content moderation, safety |

### Preview Models

> ⚠️ For **evaluation and testing only** — may be discontinued without notice. Do not use in production.

| Model ID | Display Name | Speed (tok/s) | Context | Price (per 1M) | Notes |
|---|---|---|---|---|---|
| `gemma2-9b-it` | Gemma 2 9B | 600 | 8,192 | $0.20 / $0.60 | Google's lightweight model |
| `gemma-7b-it` | Gemma 7B | 750 | 8,192 | $0.11 / $0.34 | Efficient instruction-tuned |
| `mistral-saba-24b` | Mistral Saba 24B | 200 | 262,144 | $1.00 / $3.00 | Large context, Arabic-focused |
| `qwen-2.5-32b` | Qwen 2.5 32B | — | 131,072 | Preview pricing | Multilingual capabilities |

### Audio Models

> Transcription & Translation

| Model ID | Display Name | Price / Hour | Rate Limits | Max File | Best For |
|---|---|---|---|---|---|
| `whisper-large-v3` | Whisper Large v3 | $0.111 | 200K ASH, 300 RPM | 100 MB | High-accuracy transcription |
| `distil-whisper-large-v3-en` | Distil Whisper (EN) | $0.040 | 400K ASH, 400 RPM | 100 MB | Faster English transcription |

*ASH = Audio Seconds per Hour*

### Batch API

The Batch API offers a **50% cost discount** vs. synchronous APIs. Processing window: 24 hours to 7 days.

Ideal for: large-scale async workloads, bulk content generation, model evaluations, overnight jobs.

---

## 🎯 Which Model Should You Use?

### ⚡ Real-Time Chat & Conversational AI

- **`llama-3.1-8b-instant`** — Maximum speed (1,000 tok/s)
- **`llama-4-maverick-17b`** — Best cost/performance balance

*Use for: customer support chatbots, real-time assistants, interactive applications.*

### 🧑‍💻 Code Assistants & Development

- **`llama-3.3-70b-versatile`** — Superior code understanding
- **`llama-4-scout-17b`** — High-quality code generation

*Use for: IDE copilots, code review, documentation generation, test case creation.*

### 🏢 Enterprise Reasoning & Complex Tasks

- **`llama-3.3-70b-versatile`** — Best overall reasoning
- **`mistral-saba-24b`** *(preview)* — Very long context (262K tokens)

*Use for: multi-step reasoning, document analysis, research assistance.*

### 🔍 RAG & Search Applications

- **`llama-3.1-8b-instant`** — Fast retrieval + generation
- **`llama-4-maverick-17b`** — Balanced for RAG workflows

*Groq + Elasticsearch delivers ~3x faster performance (~250ms vs ~1.5s).*

### 📝 Content Moderation & Safety

- **`llama-guard-4-12b`** — Specialized for content safety

*Use for: filtering inputs, moderating generated content, compliance.*

### 🎙️ Audio Transcription & Translation

- **`whisper-large-v3`** — Highest accuracy
- **`distil-whisper-large-v3-en`** — Faster English transcription

*Use for: meeting transcription, podcast processing, voice agents.*

---

## 📊 Performance Benchmarks

### Speed Comparison

| Model | Speed (tok/s) | Best For |
|---|---|---|
| `llama-3.1-8b-instant` | **1,000** | Real-time chat |
| `gemma-7b-it` | 750 | Fast instruction following |
| `gemma2-9b-it` | 600 | Balanced performance |
| `llama-4-maverick-17b` | 560 | Cost-effective production |
| `llama-3.3-70b-versatile` | 500 | Enterprise reasoning |
| `llama-4-scout-17b` | 280 | High-quality generation |

### Real-World Gains

When integrated with **Elasticsearch**, Groq reduces LLM response times from ~1.5 seconds to **under 250ms** — a ~3x improvement over standard GPU-based inference.

---

## 💰 Pricing & Optimization

### Standard Pricing Tiers

| Tier | Input (per 1M tokens) | Output (per 1M tokens) |
|---|---|---|
| Ultra-low cost | $0.05 | $0.08 |
| Low cost | $0.075–$0.15 | $0.30–$0.60 |
| Standard | $0.59–$1.00 | $0.79–$3.00 |

### Cost Optimization Tips

1. **Prototype with smaller models** — use `llama-3.1-8b-instant` first
2. **Use Batch API** for non-urgent workloads — save **50%**
3. **Monitor usage** via GroqCloud dashboards
4. **Implement caching** for frequently repeated queries
5. **Use shorter prompts** — every token counts

---

## 🔐 Production Recommendations

| Environment | Recommendation |
|---|---|
| Learning & prototyping | Free tier (Developer Plan) |
| Internal tools | `llama-3.1-8b-instant` or `llama-4-maverick` |
| Customer-facing apps | Paid tier + appropriate model |
| High-volume batch processing | Batch API (50% discount) |
| Enterprise with strict SLAs | Production models + paid plan |

### Scaling Notes

- Rate limits increase with paid plans
- Batch API handles thousands of requests without impacting standard limits
- Elastic integration enables sub-second search + inference pipelines

---

## 🛠️ Getting Started in Under 5 Minutes

**1.** Sign up at [groq.com](https://groq.com) — no credit card required  
**2.** Generate an API key from the [GroqCloud Console](https://console.groq.com)  
**3.** Install the SDK:

```bash
pip install groq
```

**4.** Make your first API call:

```python
from groq import Groq

client = Groq(api_key="your-api-key")

response = client.chat.completions.create(
    model="llama-3.1-8b-instant",
    messages=[{"role": "user", "content": "Explain quantum computing in 20 words"}]
)

print(response.choices[0].message.content)
```

---

## 🏁 Summary & Recommendations

| Goal | Recommended Model |
|---|---|
| Maximum speed in chat | `llama-3.1-8b-instant` |
| Deeper reasoning | `llama-3.3-70b-versatile` |
| Cost-effective production | `llama-4-maverick-17b` |
| Large-scale batch jobs | Batch API (any model) |
| Content safety | `llama-guard-4-12b` |

Groq combines **unprecedented speed**, **cost-effective pricing** (from $0.05/1M tokens), and a **generous free tier** — making it the performance leader for open-source model inference.

---

## 📚 References

- [Groq Supported Models Documentation](https://console.groq.com/docs/models)
- [Groq Batch API Documentation](https://console.groq.com/docs/batch)
- [Elastic + Groq Integration Guide](https://www.elastic.co/search-labs/tutorials/groq-elastic)
- [GroqCloud Console](https://console.groq.com)
