# Founder Harness: Product Backlog

- Status: Approved by the Product Owner on 2026-11-23.
- Date: 2026-11-23
- Source: `prd.md` v0.1

## Product Goal

A founder adds an automatic quality gate to a GitHub repo.
The gate stops bad code before it reaches `main`.

## Rules

- The Product Owner orders the items. The top item is the next to build.
- A Sprint has 1 Sprint Goal and 1 or more items. It has no time box: it ends when its items are done.
- Each item gets its own feature spec, made with Spec Kit (`spec.md`, `plan.md`, `tasks.md`).
- A check item covers both languages: JavaScript/TypeScript is user story P1, Python is P2.
- A new idea goes into "Later ideas", not into a new PRD.

## Ordered items

| Order | ID | Item | Why | Proposed Sprint | Status |
|---|---|---|---|---|---|
| 1 | PB-01 | Base: reusable workflow in `founder-harness`, caller file, setup guide with branch protection | All checks need it. | Sprint 1 | To do |
| 2 | PB-02 | Secret scan (Gitleaks) | Easiest check. It works for all languages. It proves the success metric. | Sprint 1 | To do |
| 3 | PB-03 | Dependency audit (`npm audit`, `pip-audit`) | Finds packages with known security holes. It needs only the lock file. | Sprint 2 | To do |
| 4 | PB-04 | Build check | Stops a PR that breaks the app build. | Sprint 2 | To do |
| 5 | PB-05 | Lint and format (ESLint and Prettier, Ruff) | Finds simple errors and keeps the code style the same. | Sprint 3 | To do |
| 6 | PB-06 | Type check (`tsc`, mypy) | Finds wrong data types before run time. | Sprint 3 | To do |
| 7 | PB-07 | Tests (`npm test`, `pytest`) | Stops a PR that breaks existing tests. The founder repo must already have tests. | Sprint 4 | To do |
| 8 | PB-08 | Security code scan, SAST (Semgrep or CodeQL) | Finds unsafe code patterns. CodeQL is free only for public repos. | Sprint 4 | To do |

## Sprint 1 (proposed)

- Sprint Goal: a founder adds the harness to a repo, and a PR with a fake secret gets a red X.
- Items: PB-01, PB-02.
- Before Sprint 1: the Product Owner approves `../architecture/architecture-overview.md`.

## Later ideas (not ordered, not in the prototype)

- AI review of each PR (Devin Review or a CI step that calls an AI model).
- Local Git hooks on the founder's computer.
- A setup script that also sets branch protection.
- Spec Kit setup for founder repos.
- More languages and other Git hosts.
- SHA pinning of the harness version in the caller file (see AD-2).
- A one-time full-history secret scan, started by hand (see AD-3).

## Questions to come back to

- Q1: The Spec Kit demo is paused at Step 5 (`/speckit.specify`).
