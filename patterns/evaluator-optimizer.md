# P07 — Evaluator-optimizer

## Design question

Can a candidate output be improved by repeatedly applying an explicit evaluator
and a bounded optimizer?

## Shape

```text
input -> generator -> candidate -> evaluator -> feedback -> generator -> accept/reject
```

The evaluator may be a deterministic test, a rubric, or a separate model. Its
scope and judge configuration must be recorded.

## Good fit

- code, structured documents, plans, and responses with testable quality;
- tasks where iteration yields measurable improvement.

## Avoid when

The rubric is vague, evaluator errors are correlated with generator errors, or
iteration can optimize the score while violating the real task contract.

## Contracts

- rubric and severity thresholds are frozen before comparison;
- evaluator output includes evidence and uncertainty, not just a score;
- iteration has a max count, cost, and stop rule;
- final acceptance includes independent task/state checks.

## Failure modes and evaluation

Test reward hacking, judge drift, self-preference, endless revision, and regressions
on dimensions omitted from the rubric. Report judge agreement, pass rate, cost,
and quality against a no-optimization baseline.

## References

- [Reflexion](https://arxiv.org/abs/2303.11366)
- [Anthropic — Building effective agents](https://www.anthropic.com/research/building-effective-agents)

Last checked: 2026-07-31.
