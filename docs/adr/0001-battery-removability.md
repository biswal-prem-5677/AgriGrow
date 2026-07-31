# ADR-0001 · Decide whether the Field Scout S1 battery is user-removable

| Field | Value |
|---|---|
| **Status** | **OPEN** |
| **Class (E-4)** | **Moderate** — weeks, ₹300–600 BOM plus tooling consequences |
| **Owner** | Founder — with a pack assembler and a test lab consulted before the *safety* claim is published (see Decision rights) |
| **Deadline** | **2026-08-07.** Already open longer than its class allows |
| **Decided on** | — |
| **Evidence** | **NONE.** No prototype, no gasket, no drop test, no IP54 attempt exists |
| **Outside review** | Required before publishing a safety or IP claim. Not required to make the *architectural* choice |

---

## Context

This is defect **A-2** in [README Appendix A](../../README.md#appendix-a--known-gaps-and-inconsistencies). Four Track A documents assert different things:

| Document | What it says |
|---|---|
| [02](../../agri_intelligence_platform/02_hardware_device_srs.md) §L13 — commercial tier table | "**replaceable** battery/probes" — stated as a committed product attribute |
| [02](../../agri_intelligence_platform/02_hardware_device_srs.md) §L108 — electrical spec | removable pack "**only if** … qualification" |
| [16](../../agri_intelligence_platform/16_manufacturing_strategy.md) | design for disassembly |
| [22](../../agri_intelligence_platform/22_tier_0_1_3_portable_product_srs.md) §L64 | "**only after** ingress validation" |

**A commercial commitment was made ahead of an engineering decision.** That is the mechanism of defect A-2, and it is precisely what [E-9](../../EXECUTION_PRINCIPLES.md#e-9--document-a-decision-never-a-hope) exists to prevent.

**Why it blocks everything downstream.** Mechanical is ❌ even on the *architecture* column of [`STATUS.md`](../../evidence/STATUS.md) because a second gasketed opening is not a detail — it changes gasket architecture, IP54 strategy, drop performance, parting lines, tooling, connector selection and ₹300–600 of BOM. No CAD can start. Nothing downstream of mechanical — tooling (8–14 weeks, **ASSUMED**), certification, pilot build — can start either.

**Relevant frozen baseline:** 4,000 mAh 1S Li-ion, USB-C 5 V charging, IP54 target, PC+ABS + TPE injection-moulded enclosure, replaceable probes.

**The tension.** [D-10](../../README.md#design-decisions) says *"a sealed device containing a 6–18 month consumable is disposable"* — but the 6–18 month consumable it names is **the glass pH electrode, not the battery.** Probe replaceability is already committed and is not in question here. This ADR decides only the battery.

## Decision

*To be written. One sentence, past tense.*

## Assumption decided under

*Required at decision time, because Evidence is NONE.*

## Options considered

| Option | What it means | Cost to reverse | Consequence |
|---|---|---|---|
| **A · User-removable** | Gasketed door, tool-free or single-screw, spare packs sold as a consumable | High once tooled | Second sealed opening on an IP54 device. Compounds the gasket-compression variance already flagged as an IP54 failure risk. Requires a pack + contact system that survives drop. Users can insert a counterfeit pack — a safety exposure, not just a warranty one. **Delivers the strongest field story: an operator sampling 30 farms a week can swap rather than stop** |
| **B · Service-removable** | Sealed to the user; opened by a technician with a tool at scheduled calibration; pack replaced as a service item | Moderate | One gasketed seam instead of two. Honest "serviceable, not disposable" claim without a user-facing safety surface. Battery becomes part of the annual calibration/service visit already in the V1 commercial bundle. **Operator gets no mid-day swap** — a full day of field work must fit one charge or a USB-C power bank |
| **C · Fully sealed** | No serviceable pack; device is replaced or factory-refurbished at end of battery life | Low now, very high later | Simplest IP54 path and cheapest tooling. Contradicts [D-10](../../README.md#design-decisions) and the repairability principle in the README's Engineering Principles. Makes a ₹28,000–45,000 instrument a consumable |

## What would change the answer, and what it costs

Recording this to prevent the decision being deferred *again* on the grounds that evidence is missing. **None of these need to exist before 2026-08-07.**

| Question | How to answer it | Cost |
|---|---|---|
| Does one charge cover a full operator field day? | Energy budget from the frozen baseline: 4,000 mAh against ≤120 mA guided-measurement average and ≤150 µA sleep. **Arithmetic, not a measurement — do it before deciding** | ₹0 |
| Can a two-seam enclosure hold IP54? | Gasket compression trial on a printed shell | ₹5–15k, weeks |
| Will a pack assembler quote a removable pack with protection and authentication? | One email (standing parallel lane P3) | **₹0** |
| Does a removable pack change the certification path? | Ask the test lab during the certification-scope conversation | ₹0 |

**The ₹0 items are not started.** Option A cannot be defended and Option C cannot be costed without them, and both emails cost minutes.

## Leading candidate on current information

**Option B**, on three grounds: the buyer is an organisation with a trained operator ([D-13](../../README.md#design-decisions)), not a consumer — so "technician opens it at annual service" fits the actual service model; it satisfies D-10's serviceability intent without adding a second sealed opening to an enclosure whose IP54 margin is already flagged as a risk; and it is reversible toward A at the next tooling revision, whereas A is not reversible toward B once the door is tooled and sold.

**This is a recommendation, not the decision.** Recorded here so the choice is a judgement being ratified rather than an argument being restarted on 2026-08-07.

## Consequences

*To be written at decision time.* Whatever is chosen: **the commercial tier table in [02](../../agri_intelligence_platform/02_hardware_device_srs.md) §L13 must stop asserting a committed attribute the electrical spec conditions** — that edit is [CR-002](../../CHANGELOG.md), and it cannot be written until this ADR is closed.

## Revisit trigger

A failed IP54 ingress test attributable to the pack seam · a pack assembler declining to supply · an energy-budget result showing one charge cannot cover an operator field day · the first tooling revision after V2 pilot returns.

---

**Fallback if not decided by 2026-08-07 (E-6):** decide **Option B** on the stated assumption, record the assumption in this file, and file CR-002. **Do not extend the deadline** — the cost of deferring this is measured in blocked mechanical weeks against a season-gated schedule ([E-10](../../EXECUTION_PRINCIPLES.md#e-10--schedule-backwards-from-what-cannot-move)), and a wrong-but-recorded decision is cheaper to reverse than an absent one.
