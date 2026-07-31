# P04 — Orchestrator-workers

## Design question

How can a controller delegate dynamic subtasks while keeping each worker
bounded and independently checkable?

## Shape

```text
goal -> orchestrator -> task specs -> workers -> artifacts -> orchestrator -> result
```

The orchestrator creates or revises task specifications; workers do not invent
new permissions or silently redefine the global goal.

## Good fit

- research or coding tasks where subtasks emerge during exploration;
- heterogeneous workers with different tools or expertise;
- workflows that need a central completeness and dependency check.

## Avoid when

The task is a short deterministic sequence. Delegation overhead, coordination
drift, and duplicated context can exceed the benefit.

## Contracts

- task spec includes objective, inputs, allowed tools, budget, deadline, and
  acceptance test;
- worker output is an artifact with status and provenance;
- orchestrator state is append-only or versioned;
- worker failure is represented explicitly rather than converted to success.

## Failure modes and evaluation

Test orphaned tasks, circular delegation, scope creep, duplicate work, and
workers reporting completion without evidence. Measure task coverage, artifact
validity, coordination tokens, critical-path latency, and recovery quality.

## References

- [Microsoft AutoGen](https://microsoft.github.io/autogen/)
- [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/)

Last checked: 2026-07-31.
