# P01 — Prompt chain

## Design question

Can the task be decomposed into a fixed sequence of stages whose intermediate
artifacts are useful and inspectable?

## Shape

```text
input -> extract -> transform -> verify -> output
```

Each stage has one responsibility and emits a typed or schema-checked artifact.
The next stage consumes that artifact rather than an unbounded transcript.

## Good fit

- document extraction followed by normalization and validation;
- code generation followed by a fixed test or lint stage;
- multi-step transformations with stable dependencies.

## Avoid when

The next action depends on discoveries in an open-ended environment. Use a
tool-using loop or planner-executor shape instead of hiding branching inside a
chain stage.

## Contracts

- every stage declares input/output schema and timeout;
- invalid artifacts stop or route to a named recovery path;
- stage retries are idempotent or use a new artifact version;
- the final success predicate is independent of the model's claim of success.

## Failure modes and evaluation

Watch for error propagation, silent schema coercion, duplicated side effects,
and brittle prompts between stages. Measure per-stage validity, end-to-end
success, latency, cost, and the fraction of failures diagnosable from artifacts.

## References

- [Anthropic — Building effective agents](https://www.anthropic.com/research/building-effective-agents)
- [OpenAI — A practical guide to building agents](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf)

Last checked: 2026-07-31.
