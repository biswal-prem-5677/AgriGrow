# AgriGrow — Execution Principles

> **Document ID:** AGR-EXEC-001 · **Version:** 1.1 · **Date:** 2026-07-31
> **Read with:** [README.md](README.md) — the navigation hub. This document is the operating doctrine.
>
> **README tells you what the project is. This tells you how work gets chosen, gated, stopped and decided.**
>
> Re-read this at the start of every week. It is short on purpose.

**Precedence.** When two documents disagree:

**measured evidence in `evidence/` › this document › [README.md](README.md) › documents 00–27.**

This document is authoritative on *how work is chosen, gated, stopped and decided.* README is authoritative on *what the product is.* Neither overrides a measurement, and this document never overrides a product fact. A conflict in any direction is a defect, not a judgement call — resolve it with a change request, not by picking the version you prefer.

---

## Why this document exists

The project's failure mode is not incompetence. It is **28 excellent documents and zero measurements.**

That did not happen through laziness. It happened because writing architecture feels like progress, is always available, never fails, and produces something you can show people. Measuring leakage current can fail, needs borrowed equipment, and produces one number nobody applauds.

Every principle below exists to counter a specific temptation this project has already demonstrated. They are not general startup advice. They are guardrails against *these* mistakes.

---

## The prime directive

> **Convert claims into evidence, in the cheapest order, until the product is real or provably impossible.**

Everything else is subordinate.

## The hierarchy

> **Buildability > Completeness > Innovation > Ambition**

Innovation is accepted only where it does not materially reduce feasibility. When two of these conflict, the left one wins — always, without discussion.

---

# The twelve execution principles

## E-1 · Evidence beats argument

**Rule.** When a disagreement is about a physical fact, the answer is a measurement, not a longer discussion. Budget the measurement instead of the debate.

**Why here.** Two independent buildability reviews, with every correction applied, moved the buildability score by zero. Not because the reviews were wrong, but because reviews are arguments and the score measures evidence. The pH analog front end is referenced in **21 of the 28 documents** and has been measured zero times.

**How to apply.** Any time you catch yourself constructing a case for why something will work, stop and ask: *what would measure this, and what does it cost?* If under ₹25,000 and under two weeks, measure it instead of arguing it.

**Tripwire.** You wrote more than 300 words defending a design choice without a number in it.

---

## E-2 · Work the bottleneck, only the bottleneck

**Rule.** Look at the dependency graph. Find the red box. Work it. Anything that does not unblock the current bottleneck is procrastination with good intentions.

**Why here.** Three items block everything: the unmeasured pH AFE leakage, the unmade battery-removability decision, and the unfunded agronomy knowledge base. Writing firmware, designing a logo, refining the cloud schema or expanding the benchmark matrix does not move any of them.

**How to apply.** Keep the [Complete Dependency Graph](README.md#complete-dependency-graph) open. Red boxes are the work list, with two named exceptions and no others:

- **The one blue box.** The observation schema is nearly free and every piece of software depends on it. Build it once, early, and it stops being work. It is an exception because it is *cheap and blocking*, not because it is interesting.
- **The standing parallel lane** (see [How to choose what to do next](#how-to-choose-what-to-do-next)). Items whose lead time is longer than the work itself — the analog collaborator, season windows, free quotes — cannot wait their turn behind a bottleneck, because waiting is the entire cost.

Nothing outside red boxes and those two exceptions qualifies.

**Tripwire.** You spent a productive week and no red box changed colour.

---

## E-3 · Buy the cheapest information first

**Rule.** Rank candidate work by **information gained per rupee and per week**, not by enthusiasm, readiness, or how much you enjoy it.

**Why here.** A ₹20,000 leakage coupon can kill or confirm the highest-risk subsystem in the product. Three months of firmware development tells you nothing about whether the product is viable. They are not comparable activities, and the cheap one goes first.

**How to apply.** Before starting anything, write one line: *"This costs ₹X and Y weeks, and it tells me Z."* If you cannot fill in Z with a decision you will actually make differently, don't start.

**Tripwire.** You cannot state what decision the current task informs.

---

## E-4 · Decide reversibly fast, irreversibly slow

**Rule.** Classify every decision by cost-to-reverse. Cheap: decide today, alone, move on. Expensive: require evidence, a written ADR, and one outside opinion.

| Cost to reverse | Examples | Process |
|---|---|---|
| **Cheap** (hours–days) | Language choice, folder layout, UI copy, library selection, breadboard topology | Decide alone, within one working day. Don't hold a meeting with yourself |
| **Moderate** (weeks, ₹10k–1 L) | PCB revision, sensor candidate, app framework, cloud provider | Written ADR + evidence. Decide within a week |
| **Expensive** (months, ₹1 L+) | Injection tooling, certification submission, inventory commitment, public accuracy claim, EMS selection | Evidence from a passed gate + ADR + one outside expert. Never decide under time pressure |

**Where ADRs live.** `docs/adr/NNNN-<slug>.md`, one file per decision, using [`docs/adr/adr-template.md`](docs/adr/adr-template.md). An ADR that exists only in your head is an undecided decision.

**Why here.** Battery removability is asserted or conditioned across **four documents** — [02](agri_intelligence_platform/02_hardware_device_srs.md) (commercial table and electrical spec), [16](agri_intelligence_platform/16_manufacturing_strategy.md) (design for disassembly), [20](agri_intelligence_platform/20_benchmark_matrix_and_buildability.md) (row 72, "where safety validated") and [22](agri_intelligence_platform/22_tier_0_1_3_portable_product_srs.md) (only after ingress validation) — and decided in none of them. That looks like caution. It is a moderate-cost decision blocking an entire subsystem. Deferring a moderate decision as though it were expensive is not caution — it is cost with no benefit.

**How to apply.** If a decision has been open more than two weeks and is not in the Expensive column, **you are required to decide it this week**, even on incomplete information. Record the assumption you decided under.

**Tripwire.** Any decision open past its class deadline: cheap >1 working day, moderate >2 weeks. (Expensive decisions have no deadline — that is what makes them expensive, and why misclassifying one is so costly.)

---

## E-5 · WIP limit: one

**Rule.** At most **one** open hardware experiment, **one** open software task, and **one** open partner conversation thread. Finish before starting.

**Why here.** A solo founder with five open threads finishes zero and feels busy the whole time. Hardware experiments in particular have long idle periods that *feel* like capacity for parallel work — they are not, because context-switching cost on a bench is high and mistakes there are expensive.

**How to apply.** Write the three current items — one per lane — at the top of your weekly log. If you want to start a fourth thing, you must first close one in its lane or explicitly kill it in writing.

**What does not count as an open thread.** Outreach that costs you an email costs nothing to leave outstanding. A message sent to a potential collaborator becomes an open partner thread only when someone replies and it requires work from you. This is what makes the standing parallel lane compatible with a WIP limit of one.

**Tripwire.** A second open item **in any one lane** — not merely four items overall — or any item "in progress" for more than three weeks without a status change.

---

## E-6 · Time-box everything, with a written fallback

**Rule.** Every task gets a date **and** an answer to *"what do I do if I'm not done by then?"* Hardware tasks get double your estimate.

**Why here.** Hardware iteration is bound by other people's queues, not by your effort: PCB fab and assembly runs weeks, tooling runs months, certification runs longer still and reworks. Optimism compresses none of them, and an untimed task in a hardware project silently becomes a quarter. See the lead-time table in [E-10](#e-10--schedule-backwards-from-what-cannot-move) — and note that those figures are **ASSUMED**, not quoted.

**How to apply.** Format: *"Leakage coupon measured by 15 Sept. If not: use the borrowed electrometer at a lower temperature and note the reduced confidence rather than waiting for chamber access."*

**Tripwire.** A task with no date, or a date that has passed without a recorded decision to extend or abandon.

---

## E-7 · Never pilot through a failed core assumption

**Rule.** If a gate criterion fails, **stop or redesign.** Do not scale up to find out. Do not run the pilot anyway to gather more data.

**Why here.** Your own [21_components_milestones_critical_review.md](agri_intelligence_platform/21_components_milestones_critical_review.md) §3 says this: *"Stop or redesign if measurement validity, safe service economics or user trust fails; do not 'pilot through' a failed core assumption."* It is the single best sentence in the package. It is also the hardest rule to obey, because by pilot stage you have spent real money and told people it will work.

**How to apply.** The Go/No-Go criteria in the [roadmap](README.md#release-plan) are binding, not advisory. Before each gate, re-read the criterion you wrote *before* you had results.

**Tripwire.** You are constructing an argument for why a failed criterion does not really count, or why the sample was unrepresentative, or why it will resolve at higher volume.

---

## E-8 · Write the kill criterion before the experiment

**Rule.** Before any experiment or gate, write down in advance what result makes you stop. Pre-registered, dated, unedited afterwards.

**Why here.** Post-hoc, every result looks encouraging. Every founder finds validation in their own interviews. Pre-registration is the only defence against your own optimism, and it is free.

**How to apply.** First line of every `evidence/` folder README: **"KILL IF: …"**. Never edit it after seeing data — if you believe it was wrong, write a new dated entry explaining why and leave the original visible.

**Tripwire.** An experiment folder with no `KILL IF` line, or one edited after the results date.

---

## E-9 · Document a decision, never a hope

**Rule.** Track A records what was **decided** and **why**. If it is not decided, write `OPEN`, name who decides it, and give a date. Never write aspirational prose that reads like a commitment.

**Why here.** This is precisely how defect **A-2** happened. The commercial tier table states "replaceable battery" as a committed product attribute; the electrical spec says it is conditional on qualification that has not happened. Aspirational prose in one document became a fact cited by another. **A-1** is the neighbouring failure — a frozen 2.4-in display value contradicted by the 2.7-in part the component register actually prices — and it shows the same thing from the other side: an untagged number is not traceable to whoever decided it, so nobody notices when a second document disagrees. Both survived every review round and were found only by reading the package against itself.

**How to apply.** Every specification statement must be classifiable as one of: **DECIDED** (with rationale and date), **OPEN** (with owner and date), **ASSUMED** (with what would validate it), or **MEASURED** (with a link to `evidence/`). Anything that fits none of these is prose and should be deleted.

**Tripwire.** A specification sentence you cannot label with one of the four tags.

---

## E-10 · Schedule backwards from what cannot move

**Rule.** Identify the immovables first, then fit everything else around them. Do not build a forward-looking plan and hope the calendar cooperates.

**The immovables in this project:**

| Immovable | Lead time | Consequence of missing it |
|---|---|---|
| **Agricultural season** | Kharif ≈ Jun–Oct · Rabi ≈ Nov–Mar · Dry-season vertisol cracking ≈ Mar–May | **Lose a full year.** Cannot be bought with money |
| Precision analog collaborator | 4–6 months to find | Every hardware milestone slips by the same amount |
| Certification lab queue | 4–7 months serialised, with rework | Blocks any commercial sale |
| Injection tooling | 8–14 weeks after design freeze | Blocks pilot build |
| PCB fab + assembly | 3–5 weeks per iteration | Multiply by the number of iterations you will actually need — assume three |

**Provenance of these numbers — read this before planning against them.** Only the 4–6 month analog-collaborator figure is corroborated anywhere in the package ([README → Risk Summary](README.md#risk-summary)). The tooling, PCB and certification lead times appear in **no** document 00–27 and behind **no** quote. By [E-9](#e-9--document-a-decision-never-a-hope) they are **ASSUMED**, and by the [evidence tiers](#what-counts-as-evidence) they are not evidence. Plan with them, never publish them, and replace each with a written quote (Tier B) at the first opportunity — three EMS emails and one toolmaker email cost ₹0 and are already in the standing parallel lane.

**How to apply.** Write the season you are targeting for field validation. Count backwards through tooling, PCB iterations and design freeze. That gives you the real deadline for the decisions blocking mechanical work. **Start the analog-collaborator search in parallel with everything, from today.**

**Tripwire.** Your plan has field trials starting in a month where the soil condition you need to test does not occur.

---

## E-11 · Every rupee buys information or revenue

**Rule.** No spend on polish, branding, scale, optionality or "being ready" before V1 evidence exists.

**Why here.** With ₹20,000–₹2,00,000 available against a ₹9–16 crore programme, capital efficiency is not a virtue — it is the entire strategy. Money spent on anything other than learning or earning is money that shortens your runway to no purpose.

**Spend authority (solo founder, self-funded):**

| Amount | Requirement |
|---|---|
| Up to ₹5,000 | Just spend it. Deliberation costs more than the money |
| ₹5,001 – ₹25,000 | Name the decision it unblocks, in one line, in the log |
| ₹25,001 – ₹1,00,000 | Written expected information + kill criterion + fallback if it fails |
| Above ₹1,00,000 | Requires evidence from a passed gate. Never spend this on optionality |

Bands do not overlap: a purchase sits in exactly one row. Cumulative spend on one question is what counts — four ₹6,000 purchases chasing the same answer is a ₹24,000 decision, not four small ones.

**Tripwire.** A purchase you cannot connect to a specific open decision or a paying customer.

---

## E-12 · Ship the smallest honest thing

**Rule.** If a capability cannot be validated, **ship without it and say so.** A missing feature is a limitation. An unvalidated feature presented as working is a lie.

**Why here.** This is the project's greatest existing strength — the buildability register already refuses to ship instant N/P/K in a market full of companies claiming it. The rule must survive commercial pressure, which is when it will actually be tested: the first customer who asks for nutrient readings, the first investor who asks why competitors show more features.

**How to apply.** If pH fails its gate, ship moisture-only and publish the limitation. If moisture fails in vertisols, publish the soil restriction. **Restricting a claim is a valid product outcome.** Hiding a known limitation is not.

**Tripwire.** Any published claim you could not defend with an `evidence/` folder, or any known limitation absent from the product documentation.

---

# Decision rights

Solo founders drift into two failures: deciding things they are not qualified to decide, and deferring things nobody else will ever decide for them. This table separates the two.

| Decision | Who decides | Why |
|---|---|---|
| Everything reversible | **You, today** | Nobody else is coming. Deliberation is the expensive part |
| Product scope, price, segment | **You — informed by paying customers, not opinions** | Only money is signal |
| pH/EC analog topology and layout | **You + an analog engineer's review before PCB commit** | Guarded pA-bias design fails in ways that are invisible without experience |
| Battery pack safety and removability | **You + pack assembler + test lab** | Safety-critical and certification-gated |
| Any actuation design (Tier 5) | **Do not decide alone. Requires a control-safety consultant** | Injury and liability exposure |
| Certification applicability per SKU | **Accredited lab, not you and not this document** | Notified categories change; being wrong means an unsellable product |
| DPDP consent architecture | **Privacy counsel, once rules are notified** | Legal exposure; rules are still pending |
| Freedom to operate before Tier 5 or public launch | **Patent counsel** | An issued patent does not prove you are free to sell |
| Accuracy, IP rating, battery life, soil applicability claims | **Evidence decides. Nobody's opinion overrides a measurement** | These are the claims that create liability |
| Whether a failed gate can be waived | **Nobody, alone.** Write it down, sleep on it, get one outside read | This is where projects die quietly |

**Rule of thumb:** if being wrong is embarrassing, decide alone and fast. If being wrong is dangerous, expensive to reverse, or illegal, get one outside opinion first — a single competent review, not a committee.

---

# Week zero — the scaffold this doctrine assumes

Every rule above reads or writes a file. **None of those files exist yet.** Until they do, the algorithm below has nothing to read, `KILL IF:` has nowhere to live, and change control points at an absent log. This is one hour of work and it is not optional — it is the only entry on the list before the first Monday.

| Create | Purpose | Rule it serves |
|---|---|---|
| `evidence/` | Track B. One dated folder per experiment: `evidence/<area>/YYYY-MM_<slug>/` | E-1, E-8 |
| `evidence/README.md` | The folder contract: `KILL IF:` first line, method, equipment, raw data, expiry, what surprised you | E-8 |
| **`evidence/STATUS.md`** | **The Engineering Status gate — the canonical live copy.** README's table is a dated snapshot of it | E-2, cadence |
| `evidence/LOG.md` | The daily line and the Monday WIP declaration. The cadence below assumes a log; this is where it lives | E-5, E-11, cadence |
| `CHANGELOG.md` | The CR log against frozen Track A | Change control |
| `docs/adr/` | One ADR per decision, plus `adr-template.md` | E-4 |

**Do not populate them with plans.** An `evidence/` folder containing only intentions is the documentation-as-progress anti-pattern with a new directory name.

---

# How to choose what to do next

## The standing parallel lane — before the list, every Monday

Some work has a lead time longer than any task you could compare it against. It therefore loses every "what is most important this week?" comparison, forever, while its clock runs. **These are exempt from "stop at the first match", and — being outreach rather than open threads — from the WIP limit (E-5).** They cost minutes each week.

```
P1. Analog collaborator: one new contact, this week and every week,
    until found. 4–6 months of lead time, and it starts today or it
    starts later. Nothing you do this week changes that arithmetic.

P2. Season check: is the field-trial window you are targeting still
    reachable, counting backwards through tooling and PCB iterations
    (E-10)? If a decision blocking mechanical work is late, that is
    a schedule fact — record it this week, not next quarter.

P3. Anything whose cost is an email. EMS quotes are ₹0 and flip an
    entire column of the status gate.
```

## Then the list — in order, stop at the first match

```
0. Does the week-zero scaffold exist?
   → Create it. One hour. Everything below reads it.

1. Is a RED BOX in the dependency graph still red?
   → Work it. Nothing else qualifies.

2. Is the BLUE BOX (observation schema) still unbuilt?
   → Build it. It is nearly free and all software waits on it.
     This is a one-time entry — once done it never appears again.

3. Is any Go/No-Go criterion for the current gate unmeasured?
   → Measure it.

4. Is any decision open past its E-4 class deadline?
   → Decide it this week, on incomplete information, and record the assumption.

5. Is `evidence/STATUS.md` older than one week?
   → Update it. You cannot steer without it.

6. Otherwise:
   → Take the cheapest item from the evidence backlog (E-3).

NEVER:
   → Expand Track A. Adding specification is not on this list at all.
```

**If you are ever unsure what to work on, the answer is the pH AFE leakage measurement.** It is the cheapest, highest-information, most blocking item in the project, and it will remain the correct answer until it is done.

---

# What counts as evidence

Rank everything. **The tier required depends on the kind of claim being closed:**

- **A physical claim** — accuracy, leakage, drift, IP rating, battery life, yield, cost — needs **Tier A or Tier B**. Nothing softer closes it, ever.
- **A behavioural or commercial claim** — does a buyer exist, will a novice complete a guided measurement, is the segment real — needs **Tier C, gathered to a pre-registered criterion** (E-8). This is not a relaxation: a criterion written before the interviews, with a stated sample and a stated threshold, is evidence. The same conversations recalled afterwards as "encouraging" are not.

This distinction matters because the roadmap already depends on it. [GO/NO-GO #1](README.md#release-plan) asks *"does a buyer exist?"* and answers it with eight conversations; GO/NO-GO #2 requires *"≥85 % guided-measurement completion by novice operators."* Neither is an instrument measurement. Requiring Tier A for them would make the project's own gates unclosable — and would push you toward the far worse habit of closing them on nothing at all.

**A tier never launders itself.** A Tier C interview about a physical property is still Tier C. Somebody telling you their probe reads accurately is an observation about a person, not about a probe.

| Tier | Counts as | Requirements |
|:--:|---|---|
| **A** | **Instrument measurement** | Raw data file + stated method + equipment identified + date + operator. Reproducible |
| **B** | **Commercial commitment** | Written quote, signed purchase order, signed agreement. On someone else's letterhead |
| **C** | **Primary observation** | Field visit, recorded interview with dated notes, photograph of an actual failure |
| **D** | **Design input only** | Manufacturer datasheet, peer-reviewed paper, standard. **Never release evidence** — a datasheet describes a component, not your product |
| — | **NOT EVIDENCE** | A specification document · a plan or roadmap · a competitor's marketing claim · your own reasoning however careful · **an LLM's assessment, including every review in this project's history** |

That last exclusion is not modesty. Every buildability review in this project — including the ones that produced this document — is Tier "not evidence." They are structured argument. They can tell you *what to measure*. They cannot tell you *what the measurement will say*, and treating them as though they can is the same error as treating a datasheet as a validation report.

**Evidence hygiene:** one dated folder per experiment (`evidence/bench/2026-08_ph_afe_leakage/`), a `README.md` opening with `KILL IF:`, raw data committed unedited, and one line on **what surprised you**. That last line is the most valuable thing you will write, and you will not remember it in two years.

**Evidence expires. Write the expiry date in the folder when you create it.**

| Kind | Valid until |
|---|---|
| Written quote (Tier B) | Its stated validity, or 90 days if it states none |
| Bench measurement (Tier A) | The coupon, the equipment or the topology changes — then it is void, not stale |
| Field result (Tier A/C) | The season and soil class it was taken in. A kharif result is not a rabi result |
| Interview / site visit (Tier C) | 12 months, or the next price change — whichever is sooner |
| Datasheet (Tier D) | Never valid as release evidence. No expiry needed |

An expired cell in the status gate reverts to ❌. That is not bureaucracy — a quote from a supplier who has since repriced is worse than no quote, because you will plan against it.

**Negative results are results, and they are the cheap ones.** A measurement that kills an option has done the job this entire document exists to do. Record it in the identical structure with **`RESULT: KILLED —`** and the number that killed it, so that it is never quietly re-run by a more optimistic version of you in eight months. The evidence backlog shrinks from both ends.

---

# Stop rules

Four kinds of stop. Knowing which one you are in prevents the wrong response.

| Stop type | Trigger | Correct response |
|---|---|---|
| **Gate failure** | A pre-registered criterion is not met | Stop or redesign. **Never** proceed to gather more data at larger scale (E-7) |
| **Scope stop** | A capability cannot be validated in time or budget | Ship without it, publish the limitation (E-12) |
| **Segment stop** | Nobody pays after honest attempts | Change the buyer, not the product. Then change the product |
| **Project stop** | The core measurement is not achievable at any accessible cost | Stop. Publish what you learned. This is a successful outcome — you saved years |

**A project stop is not a failure.** Learning that a ₹15,000 field pH instrument cannot be maintained by its intended user, for ₹2 lakh and four months, is a genuinely good result. Learning it after ₹12 crore and four years is the failure.

---

# Cadence

| Rhythm | Do this | Time |
|---|---|---|
| **Daily** | One line in the log: what I did, what I learned, what is blocked | 2 min |
| **Weekly** | Run the standing parallel lane, then the [work-selection algorithm](#how-to-choose-what-to-do-next). Update `evidence/STATUS.md`. Confirm WIP: **one item per lane** | 30 min |
| **Monthly** | Spend review against E-11. Check for decisions past their deadline. One outreach to a potential collaborator or expert | 1 hour |
| **Per gate** | Re-read the pre-registered criteria *before* looking at results. Write the go/no-go decision and its rationale | 2 hours |
| **Seasonally** | Recheck the backwards schedule from E-10. Seasons move; your plan must not drift past one | 1 hour |

The weekly `STATUS.md` update is the highest-leverage 30 minutes in the project. It is the only artifact that makes stagnation visible, and stagnation in a documentation-heavy project is invisible by default.

---

# Change control — how to unfreeze Track A

**The exact freeze state, because the two halves of it are easy to confuse.** Track A (documents 00–27) is **closed to addition from today** — no new scope, no new sections, no new specification, ever, except through a CR. It is **not yet fully frozen**, because freezing is a V0 deliverable ([README → Release plan → V0](README.md#release-plan)) and it is gated on closing the two known contradictions, A-1 and A-2. Those two are the last edits made *to* Track A rather than *through* the CR process; A-2 additionally cannot be written until the decision behind it is made (E-4).

After that, and from now on for everything else: Track A changes only through a change request, and only when triggered by Track B.

```markdown
## CR-NNN · <short title>
- **Date / author:**
- **Affected documents:** (list, with section numbers)
- **Trigger:** (which Track B evidence forced this — link the evidence folder)
- **Change:** (what specifically changes, quoting old and new text)
- **Impact:** (cost, schedule, certification, other subsystems, other documents)
- **Decision:** ACCEPTED / REJECTED / DEFERRED, with rationale
```

**Rules.**
1. **No CR without a trigger.** "It reads better" is not a trigger. Evidence, a decision, or a discovered contradiction is.
2. **One CR per decision.** Do not bundle.
3. **Search for downstream citations before accepting.** A-1 and A-2 exist because one document's statement was cited by another. Grep for the value you are changing.
4. **Log it in `CHANGELOG.md`** with the CR number and the affected document IDs.

**Immediate backlog — open these first:** CR for A-1 (display size), CR for A-2 (battery removability — decide it first, per E-4), then one CR each for decisions D-13 through D-18 in the README, which currently exist only in the README and contradict documents 00–27. Closing A-1 and A-2 is what completes the freeze.

---

# Named anti-patterns

Each of these has already appeared in this project or is one step away. The tripwire is how you catch it in yourself.

| Anti-pattern | What it looks like | Tripwire |
|---|---|---|
| **Documentation as progress** | A productive month, more pages, no measurements | A calendar week with zero commits under `evidence/` |
| **Architecture expansion** | "We should also document the PCB stack-up philosophy" | You are writing prose about an artifact a tool should produce |
| **Aspirational specification** | Writing "replaceable battery" before deciding it | A sentence you cannot tag DECIDED / OPEN / ASSUMED / MEASURED |
| **Deferring a moderate decision as if it were expensive** | Battery removability open across three documents | Any decision open past its E-4 deadline |
| **Piloting through** | "The trial will tell us more about why it failed" | You are arguing a failed criterion does not count |
| **Premature scale** | Five data stores, k-anonymity, federation APIs at zero users | You are building for a load you cannot name a customer for |
| **Feature answer to a distribution problem** | "Farmers will buy it once we add nutrients" | The proposed fix to "nobody bought it" is a new feature |
| **Sunk-cost defence** | Protecting 187 KB rather than testing it | You feel defensive reading a critique instead of curious |
| **Solo hero mode** | No outside expert contact for months | Three months with no conversation with someone who has shipped hardware |
| **Optionality hoarding** | Keeping three SKUs and two radios "just in case" | You cannot name the customer for a variant you are preserving |
| **Deferred honesty** | A claim in a document you privately know you cannot support | ±0.10 pH survived every review round before anyone measured anything |
| **Review-as-evidence** | Treating a strong critique as a result | You updated a status cell based on an argument rather than a measurement |

---

# The one-page card

Print this. Everything above compresses to it.

```
╔══════════════════════════════════════════════════════════════════╗
║  AGRIGROW — EXECUTION CARD                                       ║
╠══════════════════════════════════════════════════════════════════╣
║  PRIME DIRECTIVE                                                 ║
║    Convert claims into evidence, cheapest first, until the       ║
║    product is real or provably impossible.                       ║
║                                                                  ║
║  HIERARCHY                                                       ║
║    Buildability > Completeness > Innovation > Ambition           ║
║                                                                  ║
║  THE TWELVE                                                      ║
║     1. Evidence beats argument                                   ║
║     2. Work the bottleneck, only the bottleneck                  ║
║     3. Buy the cheapest information first                        ║
║     4. Decide reversibly fast, irreversibly slow                 ║
║     5. WIP limit: one                                            ║
║     6. Time-box everything, with a written fallback              ║
║     7. Never pilot through a failed assumption                   ║
║     8. Write the kill criterion before the experiment            ║
║     9. Document a decision, never a hope                         ║
║    10. Schedule backwards from what cannot move                  ║
║    11. Every rupee buys information or revenue                   ║
║    12. Ship the smallest honest thing                            ║
║                                                                  ║
║  MONDAY QUESTION                                                 ║
║    Is a red box still red?  → Work it.                           ║
║    Unsure?                  → Measure the pH AFE leakage.        ║
║                                                                  ║
║  EVIDENCE                                                        ║
║    A: measurement   B: signed commitment   C: primary observation║
║    NOT evidence: specs, plans, reasoning, LLM reviews.           ║
║                                                                  ║
║  WEEKLY (30 min, non-negotiable)                                 ║
║    Update evidence/STATUS.md. WIP: one item per lane.            ║
║                                                                  ║
║  THE TEST FOR ANY PROPOSAL                                       ║
║    Does this increase the probability that someone pays for a    ║
║    measurement they act on — within a timeframe and budget       ║
║    I can actually reach?                                         ║
║                                                                  ║
║  IF IN DOUBT                                                     ║
║    Subtract. Measure. Ship smaller.                              ║
╚══════════════════════════════════════════════════════════════════╝
```

---

## Document control

| Field | Value |
|---|---|
| Version | 1.1 |
| Date | 2026-07-31 |
| Status | Operating doctrine — binding on all work |
| Companion | [README.md](README.md) |
| Change policy | Amend only when a principle is shown by experience to be wrong. Record the experience that showed it |
| Review trigger | Every gate decision, and any time a tripwire fires twice |
