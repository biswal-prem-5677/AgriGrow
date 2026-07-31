# `evidence/` — Track B

> **Document ID:** AGR-EVID-000 · **Created:** 2026-07-31
> **Governed by:** [EXECUTION_PRINCIPLES.md](../EXECUTION_PRINCIPLES.md) — E-1, E-8, and *What counts as evidence*

**This is the only folder in the repository that can change the project's buildability score.**

`docs/` (Track A) holds claims. This holds proof. A specification section, a plan, a diagram or an argument — however careful — is **not evidence** and does not belong here. Neither does an LLM's assessment, including every review in this project's history.

**If this folder is empty, the project has made no progress, regardless of how much has been written elsewhere.**

---

## The folder contract

One dated folder per experiment. No exceptions, no loose files at the top level.

```
evidence/<area>/YYYY-MM_<slug>/
├── README.md          ← the contract below. First line is KILL IF:
├── raw/               ← unedited instrument output, exactly as captured
└── analysis/          ← optional: scripts, plots, derived tables
```

`<area>` is one of the five directories below. `YYYY-MM` is when the experiment **started**. `<slug>` is lowercase, hyphen-free words joined by underscores: `2026-08_ph_afe_leakage`.

### Every experiment `README.md` must contain, in this order

| # | Field | Rule |
|---|---|---|
| 1 | **`KILL IF: …`** | **The first line of the file.** Written *before* any data is taken. Never edited afterwards (E-8) |
| 2 | **Question** | One sentence. What decision does this inform? If you cannot name the decision, do not run the experiment (E-3) |
| 3 | **Method** | Enough that a stranger could repeat it. Sample sizes, conditions, controls |
| 4 | **Equipment** | Make, model, serial where it exists. Calibration state of the reference instrument |
| 5 | **Operator + dates** | Who, started when, finished when |
| 6 | **Tier** | A / B / C / D, per the table below. A tier never launders itself |
| 7 | **Raw data location** | Path into `raw/`. Committed unedited. If it is not committed, it did not happen |
| 8 | **Result** | The number. Then `RESULT: PASSED` / `RESULT: FAILED` / `RESULT: KILLED — <the number that killed it>` |
| 9 | **Expiry** | A date or a condition, per the expiry table below. Written when the folder is created, not when the result arrives |
| 10 | **What surprised me** | One line. **The most valuable thing you will write here, and you will not remember it in two years** |

### The `KILL IF:` rule

Write it first. Date it. **Never edit it after seeing data.** If you come to believe it was wrong, add a new dated entry below it explaining why, and leave the original visible and unaltered. An experiment folder with no `KILL IF:` line, or one edited after the results date, is a tripwire (E-8).

### Negative results

A measurement that kills an option has done the job this entire folder exists to do, and it is the cheap one. Record it in the identical structure with **`RESULT: KILLED —`** and the number that killed it, so it is never quietly re-run in eight months by a more optimistic version of you.

---

## Areas

| Directory | Holds | First expected occupant |
|---|---|---|
| `bench/` | Instrument measurements on hardware: leakage, noise, drift, power, oscilloscope traces | `2026-08_ph_afe_leakage` — the highest-information item in the project |
| `calibration/` | Gravimetric datasets, buffer runs, per-soil curves, slurry-ratio sensitivity | `2026-08_slurry_ratio_sensitivity` |
| `field/` | Trial logs, site photographs, protocol deviations, season and soil class | Season-gated — see E-10 |
| `interviews/` | FPO / KVK / lab conversations. Dated notes, pre-registered criterion, sample stated up front | `2026-08_fpo_buyer_exists` (8 conversations, GO/NO-GO #1) |
| `quotes/` | EMS, component, tooling and certification quotations. On someone else's letterhead | `2026-08_ems_quotes` — costs ₹0 and flips an entire column of `STATUS.md` |

Empty directories carry a `.gitkeep`. Delete it when the first real folder lands.

---

## Evidence tiers

**The tier required depends on the kind of claim being closed.**

- **A physical claim** — accuracy, leakage, drift, IP rating, battery life, yield, cost — needs **Tier A or Tier B**. Nothing softer closes it, ever.
- **A behavioural or commercial claim** — does a buyer exist, will a novice complete a guided measurement, is the segment real — needs **Tier C gathered to a pre-registered criterion.** A criterion written before the interviews, with a stated sample and a stated threshold, *is* evidence. The same conversations recalled afterwards as "encouraging" are not.

| Tier | Counts as | Requirements |
|:--:|---|---|
| **A** | Instrument measurement | Raw data file + stated method + equipment identified + date + operator. Reproducible |
| **B** | Commercial commitment | Written quote, signed purchase order, signed agreement. On someone else's letterhead |
| **C** | Primary observation | Field visit, recorded interview with dated notes, photograph of an actual failure |
| **D** | Design input only | Datasheet, peer-reviewed paper, standard. **Never release evidence** |
| — | **NOT EVIDENCE** | A specification · a plan · a competitor's marketing claim · your own reasoning · an LLM's assessment |

**A tier never launders itself.** A Tier C interview about a physical property is still Tier C. Somebody telling you their probe reads accurately is an observation about a person, not about a probe.

---

## Expiry

**Write the expiry date in the folder when you create it.** An expired cell in [`STATUS.md`](STATUS.md) reverts to ❌ — a quote from a supplier who has since repriced is worse than no quote, because you will plan against it.

| Kind | Valid until |
|---|---|
| Written quote (Tier B) | Its stated validity, or 90 days if it states none |
| Bench measurement (Tier A) | The coupon, the equipment or the topology changes — then it is **void, not stale** |
| Field result (Tier A/C) | The season and soil class it was taken in. A kharif result is not a rabi result |
| Interview / site visit (Tier C) | 12 months, or the next price change — whichever is sooner |
| Datasheet (Tier D) | Never valid as release evidence. No expiry needed |

---

## Files in this directory

| File | Purpose |
|---|---|
| `README.md` | This contract |
| [`STATUS.md`](STATUS.md) | **The Engineering Status gate — canonical live copy.** README.md's table is a dated snapshot of it. Update weekly |
| [`LOG.md`](LOG.md) | Daily one-liner, weekly WIP declaration, weekly work-selection result |

---

## What must never go in here

- A plan for an experiment that has not been run. **An `evidence/` folder containing only intentions is the documentation-as-progress anti-pattern with a new directory name.**
- A conclusion without the raw data it came from.
- An edited `KILL IF:` line.
- A cleaned-up dataset replacing the original capture.
