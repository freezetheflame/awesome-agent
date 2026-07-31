# P06 — Planner-executor

## Design question

Should the system create a plan before taking actions, and how much authority
should the plan have over execution?

## Shape

```text
goal -> planner -> versioned plan -> executor -> observations -> replan or finish
```

Planning is a coordination artifact, not proof that the task succeeded. The
executor must re-check preconditions against live state.

## Good fit

- long-horizon tasks with dependencies and a useful intermediate plan;
- work where humans need to inspect or approve the proposed sequence.

## Avoid when

The environment changes quickly or the cost of planning exceeds the task. A
short adaptive loop is often safer than a stale elaborate plan.

## Contracts

- plan steps have preconditions, postconditions, dependencies, and budgets;
- execution can reject or revise stale steps;
- irreversible steps require separate authorization;
- completion is determined by external checks, not plan exhaustion.

## Failure modes and evaluation

Look for over-planning, stale plans, hidden plan edits, and execution that skips
verification. Compare planned versus executed steps, replan frequency, state
validity, and cost against a loop baseline.

## References

- [Voyager](https://arxiv.org/abs/2305.16291)
- [OpenAI agent guide](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf)

Last checked: 2026-07-31.
