# HF_Leaderboard_Lab_Results

**Project:** `L_COWAGENT`  
**Tier:** `TIER_4_INFERENCE_AGENTS`  
**Slug:** `camel-ai/camel`  
**Commit:** `0106b76830c7`  
**Run:** `2026-09-30T15:07:07.146295+00:00`  

## Isolation Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| HF model | `distilbert-base-uncased` |
| HF load time | `4.42s` |
| Inference device | `cpu` |

## Results

**Framework:** [HuggingFace Open LLM Leaderboard (proxy via distilbert-base-uncased)](https://huggingface.co/docs/leaderboards/en/open_llm_leaderboard/archive)

**Model used:** `distilbert-base-uncased`

### Inference Latency (Classification)

| Metric | Value |
| ------ | ----- |
| Avg latency | **47.6 ms** |
| Min latency | 41.02 ms |
| Max latency | 54.0 ms |
| Samples | 5 |

### Real Tokenization Results

| Field | Value |
| ----- | ----- |
| Token count | **39** |
| Tokenization latency | 1.0 ms |
| Classification label | `LABEL_0` |
| Classification score | 0.5878 |
| Classification latency | 87.03 ms |
| Status | **PASS** |

**Input text tokenized:**
```
L_COWAGENT (camel-ai/camel) — 2243 files, 282302 source lines, licence Apache-2.0, primary language ['Python']
```

**First 20 tokens:**
```
['[CLS]', 'l', '_', 'cow', '##age', '##nt', '(', 'camel', '-', 'ai', '/', 'camel', ')', '—', '224', '##3', 'files', ',', '282', '##30']
```

> Full MMLU/HellaSwag/TruthfulQA/ARC/Winogrande/GSM8K require dedicated GPU.
> These results are CPU inference proxy metrics using distilbert-base-uncased.

---
_Anticloud Benchmark Suite — isolation log — 2026-09-30T15:07:07.146295+00:00_