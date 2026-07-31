# P08 — Retrieval-grounded agent

## Design question

What external evidence should be retrieved, cited, and placed in context for
the next decision?

## Shape

```text
question -> retrieve -> filter/rerank -> evidence context -> answer/action -> verify
```

Retrieval is an evidence boundary, not a guarantee of truth. The agent should
distinguish source content from instructions and keep source provenance.

## Good fit

- changing documentation, private knowledge, or large corpora;
- tasks requiring citations, freshness, or source-level auditability.

## Avoid when

The corpus is tiny and stable, retrieval quality cannot be measured, or a
retrieved document can directly authorize an irreversible action.

## Contracts

- chunks carry source ID, version/time, access policy, and trust class;
- retrieval failure is explicit and does not become an empty confident answer;
- context budgets and citation requirements are bounded;
- untrusted text cannot change tool permissions or system policy.

## Failure modes and evaluation

Measure recall, precision, citation entailment, freshness, injection resistance,
and answer quality with and without retrieval. Test stale, conflicting,
poisoned, and access-restricted documents.

## References

- [LlamaIndex](https://www.llamaindex.ai/)
- [OpenAI Cookbook](https://cookbook.openai.com/)
- [OWASP Agentic AI Threats and Mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/)

Last checked: 2026-07-31.
