# Architecture Decision Records

> **Governed by:** [EXECUTION_PRINCIPLES.md](../../EXECUTION_PRINCIPLES.md) — [E-4](../../EXECUTION_PRINCIPLES.md#e-4--decide-reversibly-fast-irreversibly-slow), [E-9](../../EXECUTION_PRINCIPLES.md#e-9--document-a-decision-never-a-hope)

One file per decision: `NNNN-<slug>.md`, numbered sequentially, **never renumbered**. Start from [`adr-template.md`](adr-template.md).

**An ADR that exists only in your head is an undecided decision.**

## Status vocabulary

| Status | Meaning |
|---|---|
| **OPEN** | Named, owned, dated — not yet decided. Must carry a deadline from its E-4 class and a fallback (E-6) |
| **DECIDED** | Decided, with a date and either an evidence link or a recorded assumption |
| **SUPERSEDED** | Replaced by a later ADR. **Never edited to match what happened** — the record of what you believed at the time is the point |
| **REVERSED** | Tried, and undone. Say what it cost |

## Index

| # | Decision | Status | Class | Deadline |
|---|---|---|---|---|
| [0001](0001-battery-removability.md) | Battery removability — defect A-2 | **OPEN** | Moderate | **2026-08-07** |

**D-01 through D-18** currently live only in [README → Design Decisions](../../README.md#design-decisions). Migrating them here is Track A housekeeping, queued behind the evidence backlog as CR-003…CR-008 in [`CHANGELOG.md`](../../CHANGELOG.md). Do not migrate them before a measurement exists.

## Note on this directory's parent

`docs/` currently holds **only** ADRs. [README's recommended structure](../../README.md#recommended-structure-to-create-when-implementation-starts) proposes also renaming `agri_intelligence_platform/` → `docs/`. That rename is **OPEN and deliberately not done here**: it breaks roughly sixty relative links in [README.md](../../README.md) and [EXECUTION_PRINCIPLES.md](../../EXECUTION_PRINCIPLES.md). It is a cheap, reversible decision (E-4) whose only cost is a careful search-and-replace, and it should be bundled with CR-001 rather than done piecemeal.
