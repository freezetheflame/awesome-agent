# P10 — Human handoff

## Design question

When should the system stop acting and transfer control to a person with enough
context to make a safe decision?

## Shape

```text
agent -> confidence/risk/policy check -> continue | ask clarification | handoff
                                      human decision -> resume or close
```

Handoff is a terminal or explicitly resumable state, not an apology message.

## Good fit

- high-impact, ambiguous, contested, or policy-sensitive tasks;
- operations where human accountability is required.

## Avoid when

The person receives an unstructured transcript, lacks permissions, or the
handoff queue has no service-level ownership.

## Contracts

- handoff payload includes goal, current state, actions taken, evidence,
  unresolved uncertainty, and requested decision;
- external side effects are paused or clearly marked;
- ownership, acknowledgement, timeout, and resume semantics are explicit;
- the agent cannot silently continue after escalation.

## Failure modes and evaluation

Test premature escalation, missed escalation, context loss, duplicate actions,
and stale queued cases. Measure handoff precision/recall, time to ownership,
rework, and outcomes after resumption.

## References

- [OpenAI agent guide](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)

Last checked: 2026-07-31.
