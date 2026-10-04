# Developer Cookbook — L_COWAGENT
**Stack:** Python 3.11, copy-on-write state management, PAX 27B, SQLite, AIOSS_FORMAT
**Domain:** CoW (Copy-on-Write) agent: memory-efficient stateful agent execution for Anticloud

## CoW agent execution
```python
from l_cowagent import CoWAgent, Step

agent = CoWAgent(
    pax_model="./pax-27b-q4.gguf",
    state_db="./cowagent_state.db",
    aioss_chain="./cowagent.aioss"
)

agent.set_initial_state({
    "task": "Audit TIER_7 for HIPAA compliance",
    "tier": "TIER_7_BIOSIGNALS_NEURO",
    "steps_completed": []
})

# Execute steps with automatic CoW snapshots
for step_result in agent.run_steps(max_steps=10):
    print(f"Step {step_result.step_id}: {step_result.action}")
    if not step_result.accepted:
        print(f"  Rolled back to step {step_result.rollback_to}")
    print(f"  Chain: {step_result.chain_hash}")

print("Final state:", agent.current_state)
```

## Manual state inspection
```python
snapshots = agent.list_snapshots()
for s in snapshots:
    print(f"Step {s.step_id}: state_hash={s.hash[:16]}, accepted={s.accepted}")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
