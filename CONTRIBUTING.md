# Contributing

This repository is a framework landscape, not a popularity leaderboard.

## Adding a project

Add a project to the most specific section of `frameworks/README.md`. Each entry
should include:

- official source repository and documentation when available;
- architectural role: SDK/runtime, orchestration, protocol/infra, application,
  or evaluation;
- the primary design center in one sentence;
- a maturity, maintenance, or migration caveat;
- a GitHub attention signal only when useful, with an explicit snapshot date.

Use this shape:

```markdown
| [Project](https://github.com/org/repo) | Python | typed tool loop | verify maintenance/release status | snapshot |
```

## Review standards

- Prefer official repositories, official documentation, papers, benchmarks, and
  reproducible examples.
- Do not describe an application as an SDK, or a protocol as an orchestration
  framework.
- Do not infer reliability, security, or production readiness from stars.
- Call out archived, experimental, migrating, or vendor-specific projects.
- Avoid duplicate links from other Awesome lists unless this catalogue adds a
  useful architectural classification or comparison.
- Keep descriptions factual, compact, and useful to both English- and
  Chinese-speaking readers.

## Pull requests

Keep updates focused. Explain why a project belongs in its category and what a
reader learns from studying it. Include the date of any status or star-count
check. Maintainers may move entries when a project's role changes.
