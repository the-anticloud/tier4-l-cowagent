# Ledger Status

**Project:** `L_COWAGENT`  
**Tier:** TIER_4_INFERENCE_AGENTS  
**Identity:** Upstream `camel-ai/camel` @ `0106b76830c7` (Apache-2.0)

## Chain state

| Fact | Value |
| --- | --- |
| Upstream | `camel-ai/camel` |
| Commit | `0106b76830c707effe48cd3da384dda38cbed92e` |
| Upstream licence | Apache-2.0 |
| Licence class | permissive |
| Clone size | 145.41 MB |
| Ledger | 0 blocks, chain verified |
| Current TRL | NOT YET MEASURED |
| Post-optimisation TRL | NOT YET MEASURED |
| II budget cap | 1000.0 IIU |
| Verified upstream edits | 1 |

- Blocks: **0**
- Head digest: `None`
- Chain verification: **verified**

## Independent verification

The chain is verifiable without trusting this project's tooling:

```
anticloud ledger verify
anticloud ledger export > ledger.jsonl
```

Each block carries the previous block's digest, so removing or reordering an
entry invalidates every block after it. That property is the reason the
ledger can stand in for a claim of what happened.
