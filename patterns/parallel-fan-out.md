# P03 — Parallel fan-out/fan-in

## Design question

Which independent subproblems can run concurrently and be merged without
changing semantics?

## Shape

```text
             -> worker A ->
input -> split -> worker B -> merge -> verify
             -> worker C ->
```

The fan-in step owns conflict resolution and completeness checks.

## Good fit

- independent searches, inspections, or candidate generation;
- multiple evidence sources whose outputs can be normalized;
- latency-sensitive work with a clear merge rule.

## Avoid when

Workers share mutable state, depend on each other's intermediate results, or
the merge rule is only a vague model judgment.

## Contracts

- each worker receives an isolated input snapshot and a budget;
- outputs include provenance, status, and partial-failure information;
- merge order is deterministic where ties matter;
- cancellation and timeout behavior are explicit.

## Failure modes and evaluation

Look for correlated errors, duplicate evidence, race-dependent state, and a
majority vote that rewards confident but wrong workers. Measure wall-clock
latency, worker cost, merge validity, coverage of independent evidence, and
performance under missing or contradictory workers.

## References

- [Anthropic — Building effective agents](https://www.anthropic.com/research/building-effective-agents)
- [LlamaIndex Workflows](https://docs.llamaindex.ai/en/stable/module_guides/workflow/)

Last checked: 2026-07-31.
