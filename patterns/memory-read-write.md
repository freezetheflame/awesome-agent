# P09 — Memory read/write

## Design question

What information should persist beyond the current context window, and under
what retention and deletion policy?

## Shape

```text
episode -> extract/validate -> memory store
query -> retrieve/filter -> current context
```

Memory is a governed data product. It should not be an automatic transcript
dump or a second hidden prompt.

## Good fit

- stable user preferences, learned task facts, or reusable summaries;
- repeated work where retrieval from prior episodes has measurable value.

## Avoid when

Facts are highly sensitive, short-lived, cheap to recompute, or difficult to
invalidate when the world changes.

## Contracts

- each memory has owner, source, timestamp, confidence, scope, and expiry;
- writes pass validation and privacy/policy checks;
- reads are relevance- and authorization-filtered;
- correction, deletion, and provenance lookup are first-class operations.

## Failure modes and evaluation

Test stale memories, cross-user leakage, contradictory facts, prompt injection,
and memory poisoning. Measure retrieval usefulness, false recall, deletion
success, privacy incidents, and added token/cost overhead.

## References

- [Generative Agents](https://arxiv.org/abs/2304.03442)
- [Awesome Agent Memory](https://github.com/TeleAI-UAGI/Awesome-Agent-Memory)

Last checked: 2026-07-31.
