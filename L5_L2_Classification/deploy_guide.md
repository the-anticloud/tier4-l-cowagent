# Deploy Guide — L_COWAGENT
**Tier:** TIER_4_INFERENCE_AGENTS | **Stack:** Python 3.11, copy-on-write state management, PAX 27B, SQLite, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, PAX 27B weights, SQLite (stdlib) for state persistence, AIOSS_FORMAT.

## Environment
8GB RAM for CoW state store. GPU for PAX inference.

## AIOSS Integration
```bash
aioss init --module L_COWAGENT --output ./l_cowagent.aioss
aioss append --chain ./l_cowagent.aioss --payload ./output.bin --module L_COWAGENT
aioss verify --chain ./l_cowagent.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_COWAGENT",
    aioss_chain="./L_COWAGENT.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_COWAGENT.aioss --verbose
python -m L_COWAGENT.tests.smoke
```
