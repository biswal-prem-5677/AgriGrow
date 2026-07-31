# ADR-NNNN · <short title in the imperative>

| Field | Value |
|---|---|
| **Status** | OPEN / DECIDED / SUPERSEDED by ADR-NNNN / REVERSED |
| **Class (E-4)** | Cheap (hours–days) / Moderate (weeks, ₹10k–1 L) / Expensive (months, ₹1 L+) |
| **Owner** | Who decides. Not "the team" |
| **Deadline** | A date. Cheap: 1 working day. Moderate: 2 weeks. Expensive: none — that is what makes it expensive |
| **Decided on** | Date, or `—` while OPEN |
| **Evidence** | Link to `evidence/…`, or **NONE — decided on assumption** |
| **Outside review** | Required for Moderate (one opinion) and Expensive (one outside expert). Name them, or state `not required` |

---

## Context

What is true today that forces a decision. **Numbers, not adjectives.** If this section has no number in it, you are probably arguing rather than deciding (E-1).

State which documents currently assert what, and where they contradict each other.

## Decision

One sentence, in the past tense: *"We will …"*

## Assumption decided under

**Required when Evidence is NONE.** Name the thing you are assuming, and what would falsify it. A moderate decision made on incomplete information is correct practice (E-4); a moderate decision made *without recording what you assumed* is not.

## Options considered

| Option | Cost to reverse | Consequence | Verdict |
|---|---|---|---|
| A · | | | **Chosen** / Rejected |
| B · | | | |
| C · | | | |

## Consequences

**Accepted:** what gets worse or more expensive because of this.
**Unlocked:** what can now start.
**Downstream documents:** which Track A documents this contradicts, and which CR fixes them (see [`CHANGELOG.md`](../../CHANGELOG.md)).

## Revisit trigger

The specific measurement, quote or event that would reopen this. Not "if circumstances change."

---

## Rules for using this template

1. **One file per decision.** `docs/adr/NNNN-<slug>.md`, numbered sequentially, never renumbered.
2. **An ADR that exists only in your head is an undecided decision.** If it is not written, it is not decided.
3. **Never edit a DECIDED ADR to match what happened later.** Supersede it with a new one and link both. The record of what you believed at the time is the point.
4. **Cheap decisions do not need this file** unless someone later asks why. Decide them alone, within a working day, and move on — deliberation is the expensive part.
5. **`Evidence: NONE` is permitted and often correct.** Deferring a moderate decision because evidence is missing is the anti-pattern (E-4), not deciding without it. What is *not* permitted is leaving the assumption unrecorded.
