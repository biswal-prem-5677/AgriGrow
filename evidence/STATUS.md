# Engineering Status Gate — canonical live copy

> **Document ID:** AGR-STATUS-001 · **Last updated:** 2026-07-31 · **Next update due:** 2026-08-07
> **This file is authoritative.** The table in [README.md](../README.md#the-engineering-status-gate) is a dated snapshot of it.
> **Update every Monday, 30 minutes.** It is the only artifact that makes stagnation visible, and stagnation in a documentation-heavy project is invisible by default.

**A cell flips only on a Track B result — never on an argument, a review, or a plan.** Every ❌→✅ files a change request into [`CHANGELOG.md`](../CHANGELOG.md). An expired evidence folder reverts its cell to ❌.

---

## The gate

**Legend:** ✅ done, with an `evidence/` link · ⚠ partial or asserted-not-measured · ❌ not done · n/a not applicable

| Subsystem | Arch | Proto | Bench | Field | Mfg'able | Cert'd | Cost verified | Prod ready |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Tier 0 kit | ✅ | ❌ | ❌ | ❌ | ⚠ | n/a | ❌ | ❌ |
| Tier 2 — moisture + temp | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Tier 2 — pH AFE** | ⚠ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Tier 2 — EC | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Mechanical / enclosure** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Firmware | ✅ | ❌ | ❌ | ❌ | n/a | n/a | n/a | ❌ |
| Android app | ✅ | ❌ | ❌ | ❌ | n/a | n/a | n/a | ❌ |
| Cloud | ✅ | ❌ | ❌ | ❌ | n/a | n/a | ❌ | ❌ |
| Advisory rules | ✅ | ❌ | ❌ | ❌ | n/a | n/a | ❌ | ❌ |
| Agronomy KB | ❌ | ❌ | ❌ | ❌ | n/a | n/a | ❌ | ❌ |
| Tier 4 tower | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Tier 5–9 | ⚠ | ❌ | ❌ | ❌ | n/a | ❌ | ❌ | ❌ |

**Evidence cells filled to date: 0 of 78.**

Three cells deserve attention:

- **Mechanical is ❌ even on architecture** — the battery decision ([ADR-0001](../docs/adr/0001-battery-removability.md)) is unmade, so nothing downstream can start.
- **pH AFE is ⚠ not ✅** — topology chosen, feasibility unmeasured. One number decides whether pH exists as an AgriGrow product.
- **"Cost verified" is ❌ everywhere** — every figure in the package is a planning hypothesis, not a quote. Three EMS emails flip that entire column, at ₹0.

---

## WIP — one item per lane (E-5)

Declared every Monday. A second open item **in any one lane** is a tripwire. Outreach that costs an email is not an open thread until someone replies and it requires work from you.

| Lane | Current item | Opened | Time-box (E-6) | Fallback if not done by then |
|---|---|---|---|---|
| **Hardware experiment** | *none — week-zero scaffold only* | — | — | — |
| **Software task** | *none* | — | — | — |
| **Partner conversation** | *none* | — | — | — |

**Standing parallel lane** — runs before the list, every Monday, exempt from the WIP limit:

| # | Item | Last actioned | Note |
|---|---|---|---|
| P1 | Analog collaborator — one new contact per week until found | **never** | 4–6 month lead time. Starts today or it starts later; nothing this week changes that arithmetic |
| P2 | Season check — is the targeted field-trial window still reachable? | **never** | Target season not yet declared. See open item below |
| P3 | Anything whose cost is an email — EMS quotes, toolmaker lead times | **never** | ₹0 and flips a whole column of this table |

---

## Open decisions and their deadlines (E-4)

A decision open past its class deadline is a tripwire. Cheap: >1 working day. Moderate: >2 weeks. Expensive decisions have no deadline — which is why misclassifying one is so costly.

| ID | Decision | Class | Owner | Deadline | State |
|---|---|---|---|---|---|
| [ADR-0001](../docs/adr/0001-battery-removability.md) | Battery removability (defect A-2) | **Moderate** | Founder | **2026-08-07** | **OPEN — overdue by class; blocks all mechanical work** |
| [CR-001](../CHANGELOG.md) | Display size 2.4 in vs 2.7 in (defect A-1) | Cheap | Founder | **2026-08-03** | OPEN |
| — | Target season for V1 field validation | Moderate | Founder | 2026-08-14 | OPEN — cannot schedule backwards (E-10) until declared |
| — | RTOS: FreeRTOS vs Zephyr | Cheap | Founder | At bring-up | Deferred by design — no hardware to bring up |

---

## Evidence backlog — ranked by information per rupee (E-3)

Not a plan. A queue. Each line states what it costs and what it tells you; a line whose "tells me" column cannot name a decision gets deleted, not started.

| # | Experiment | Cost | Weeks | Tells me | Folder |
|---|---|---:|---:|---|---|
| 1 | **pH AFE leakage coupon** @ 45 °C / 90 % RH | ₹15–25k | 2–4 | Whether pH exists as a product at all | `bench/2026-08_ph_afe_leakage` |
| 2 | **3 EMS quotes** against current BOM | **₹0** | 1–3 | Whether the cost model is real or fiction | `quotes/2026-08_ems_quotes` |
| 3 | **8 conversations** — 5 FPO, 3 KVK, 2 labs | ₹10–30k | 3–6 | Whether a buyer exists (GO/NO-GO #1) | `interviews/2026-08_buyer_exists` |
| 4 | Slurry-ratio sensitivity, 1:1 vs 1:2.5, 3 soils | ₹5–15k | 2–3 | The real uncertainty budget, replacing ±0.10 pH | `calibration/2026-09_slurry_ratio` |
| 5 | Capacitive vs gravimetric in a **vertisol** | ₹10–20k | 3–4 | Whether moisture survives cracking soil | `calibration/2026-09_vertisol_gravimetric` |
| 6 | One Tier 0 kit + **one paid engagement** | ₹12k | 4–8 | Whether anyone pays actual money | `field/2026-09_first_paid_engagement` |

**Item 2 costs ₹0 and is not started.** That is the cheapest thing on the list by an infinite margin.

> **If you are ever unsure what to work on, the answer is item 1.** It is the cheapest, highest-information, most blocking item in the project, and it remains the correct answer until it is done.

---

## Tripwires currently firing

| Tripwire | Rule | Since |
|---|---|---|
| A calendar week with zero commits under `evidence/` | Documentation-as-progress | Project start |
| Battery removability open across four documents, undecided | E-4 — moderate decision deferred as if expensive | Project start |
| No conversation with anyone who has shipped hardware | Solo hero mode | Project start |
| ±0.10 pH survived every review round before anyone measured anything | Deferred honesty | Project start |

These are recorded, not excused. Each one closes with an action, not a paragraph.

---

## Update log

| Date | Cells flipped | By what evidence |
|---|---|---|
| 2026-07-31 | — | File created. Week-zero scaffold. **No measurements exist.** |
