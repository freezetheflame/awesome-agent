# Contributing

Thanks for helping build a useful Agent knowledge map.

## Adding a resource

Please add an entry to the most specific section, or open an issue if a new
section is needed. Each entry should answer:

1. What design or learning question does it help with?
2. Who maintains it, and what is its current maturity?
3. What is the primary evidence or source?
4. What limitation, trade-off, or failure mode should a reader know?
5. When did you last check the link?

Use this template when the entry needs more context:

```markdown
- [Name](https://example.com) — **type; maturity.** Design lesson. Limitation.
  Last checked: YYYY-MM-DD.
```

## Adding a design pattern card

Create a focused file under `patterns/` and add it to `patterns/README.md` and
the pattern index in `README.md`. A card should include:

- the design question and a small architecture diagram;
- good-fit and avoid-when guidance;
- state, tool, permission, and termination contracts;
- failure modes, observability signals, and evaluation suggestions;
- primary references and a last-checked date.

Patterns should describe a system shape and its trade-offs, not advertise a
framework or imply that more autonomy is automatically better.

## Review standards

- Prefer primary papers, official documentation, source repositories, and
  reproducible benchmarks.
- Keep framework and product descriptions factual and specific.
- Do not use star counts, launch announcements, or vendor claims as proof of
  reliability or capability.
- Avoid duplicate lists unless the new resource has a genuinely different
  audience or organizing principle.
- Keep the catalogue useful to both English- and Chinese-speaking readers.
- Remove or mark links that are dead, abandoned, or materially outdated.

## Pull requests

Keep pull requests focused. Explain the design question behind each addition
and mention any link or status checks you performed. Maintainers may reorganize
entries to keep categories coherent.
