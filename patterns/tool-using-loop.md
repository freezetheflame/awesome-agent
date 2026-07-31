# P05 — Tool-using loop

## Design question

How should the agent choose the next action from the current observation?

## Shape

```text
goal -> model decision -> permission check -> tool -> observation -> model decision
                    \-> stop / ask / hand off
```

The loop is useful because the environment, not the prompt, determines what is
known next. ReAct is a research ancestor; production systems need stronger
tool, state, and termination contracts.

## Good fit

- browsing, coding, diagnosis, and customer-service tasks with feedback;
- environments where actions change what can be observed next.

## Avoid when

The task can be solved with a fixed workflow, or tools have irreversible effects
without a robust approval boundary.

## Contracts

- every tool has a typed schema, policy, timeout, and error representation;
- observations are labeled as untrusted data, not instructions;
- retries and duplicate calls have explicit idempotency semantics;
- stop conditions include success, failure, budget exhaustion, and escalation.

## Failure modes and evaluation

Test loops, hallucinated tools, prompt injection, stale observations, duplicate
side effects, and false completion. Record the full call ledger and evaluate
task state, process invariants, cost, and termination reason separately.

## References

- [ReAct](https://arxiv.org/abs/2210.03629)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [τ-bench](https://github.com/sierra-research/tau2-bench)

Last checked: 2026-07-31.
