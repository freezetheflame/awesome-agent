# P11 — Guarded action boundary

## Design question

How can an agent reason freely while keeping irreversible external effects
authorized, observable, and recoverable?

## Shape

```text
agent intent -> policy/argument check -> approval/idempotency -> effect -> receipt
       \-> reject / simulate / request human approval
```

The boundary is a separate component from the model and records the actual
attempt, result, identity, and state change.

## Good fit

- money movement, messages, deletion, deployment, access changes, and writes;
- tool-using loops where duplicate execution is possible.

## Avoid when

The boundary is only a prompt instruction or when no independent postcondition
can verify whether the effect happened.

## Contracts

- canonical action schema and authorization decision are persisted;
- idempotency key/call ID and exactly-once or at-most-once semantics are explicit;
- pre/post state and receipt are recorded;
- retries never silently create a second effect.

## Failure modes and evaluation

Test argument confusion, permission bypass, stale approval, replay duplication,
partial failure, and false receipts. Evaluate policy violations, duplicate
effects, state-delta correctness, audit completeness, and recovery behavior.

## References

- [Model Context Protocol](https://modelcontextprotocol.io/)
- [τ-bench](https://github.com/sierra-research/tau2-bench)
- [AgentDojo](https://github.com/ethz-spylab/agentdojo)

Last checked: 2026-07-31.
