# Agent Design Patterns

These cards describe recurring system shapes, not framework-specific recipes.
Choose the smallest shape that satisfies the task contract, then add autonomy
only when measurement shows it is useful.

## Cards

| ID | Pattern | Primary question | Start here when |
|---|---|---|---|
| P01 | [Prompt chain](prompt-chain.md) | Can a task be split into fixed, inspectable stages? | The steps and intermediate artifacts are known. |
| P02 | [Router](router.md) | Which specialized path should handle this request? | Inputs fall into distinguishable classes. |
| P03 | [Parallel fan-out/fan-in](parallel-fan-out.md) | Which independent views can run concurrently? | Work is decomposable and mergeable. |
| P04 | [Orchestrator-workers](orchestrator-workers.md) | How can a controller delegate bounded subtasks? | Subtasks are dynamic but have clear contracts. |
| P05 | [Tool-using loop](tool-using-loop.md) | How should an agent select tools from observations? | The next action depends on the environment. |
| P06 | [Planner-executor](planner-executor.md) | Should planning be separated from acting? | A plan is useful, but execution must remain bounded. |
| P07 | [Evaluator-optimizer](evaluator-optimizer.md) | How can an output improve against an explicit rubric? | Quality is judgeable and iteration has a budget. |
| P08 | [Retrieval-grounded agent](retrieval-grounded.md) | What evidence should enter the context? | Knowledge is external, changing, or too large for the prompt. |
| P09 | [Memory read/write](memory-read-write.md) | What should persist across tasks or sessions? | Reuse is valuable and retention can be governed. |
| P10 | [Human handoff](human-handoff.md) | When should a person take control? | Risk, ambiguity, or policy requires escalation. |
| P11 | [Guarded action boundary](guarded-action-boundary.md) | How do we constrain irreversible effects? | Tools can change external state, spend money, or expose data. |

## How to use a card

Start with the task's success contract and environment. Treat the diagrams as
design hypotheses, not prescriptions. A pattern is not justified until its
extra latency, tokens, failure surface, and operational complexity are visible
in evaluation.

## Card format

Every card has the same minimum fields:

- design question and core shape;
- preconditions and non-goals;
- state, tool, and termination contracts;
- failure modes and observability signals;
- evaluation suggestions and references.
