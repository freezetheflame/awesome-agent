# P02 — Router

## Design question

Which specialized workflow, model, tool set, or policy should handle this
request?

## Shape

```text
request -> classifier/router -> path A | path B | human | reject
```

The router should select a bounded path, not become a hidden general-purpose
agent.

## Good fit

- support requests separated by product or risk level;
- tasks with materially different tools or context requirements;
- early policy decisions such as allowed, needs approval, or refuse.

## Avoid when

Classes overlap heavily or a wrong route is expensive and hard to detect. Add a
reject/clarification path and abstention threshold before adding more classes.

## Contracts

- route labels and confidence/abstention semantics are versioned;
- each path declares allowed tools, budget, and terminal conditions;
- the original request and route decision are preserved for audit;
- a route cannot silently widen permissions.

## Failure modes and evaluation

Measure confusion by class, abstention quality, worst-class recall, and the cost
of a wrong route. Test adversarial wording, ambiguous inputs, and route drift
after model or policy changes.

## References

- [LangGraph — Workflows and agents](https://langchain-ai.github.io/langgraph/)
- [Google ADK](https://google.github.io/adk-docs/)

Last checked: 2026-07-31.
