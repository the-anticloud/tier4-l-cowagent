# L5 Narrow / L2 General Classification — L_COWAGENT
**Platform:** Anticloud | **Tier:** TIER_4_INFERENCE_AGENTS | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
L_COWAGENT implements copy-on-write state management for long-running Anticloud agents. Each agent step creates a lightweight state snapshot rather than copying full state. Narrow scope: Anticloud agent state management — not a general agent framework.

## L2 General
L2 General: any TIER_4 agent that runs long multi-step tasks benefits from CoW memory efficiency. TIER_9 robotics mission planners and TIER_6 security auditors both use L_COWAGENT for state isolation between steps.

## PAX 27B Integration
PAX 27B generates each agent step. L_COWAGENT manages the state snapshots: before each PAX call, a CoW snapshot is created; if PAX output is rejected by the verifier, the agent rolls back to the previous state.

## AIOSS Audit Chain
Every agent step (step ID + input state hash + PAX output hash + accepted/rejected + next state hash) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
GDPR Art. 5 (data minimisation in agent state). ISO 27001 A.8.2.
