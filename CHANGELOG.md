# CHANGELOG — change requests against Track A

> **Document ID:** AGR-CR-000 · **Created:** 2026-07-31
> **Governed by:** [EXECUTION_PRINCIPLES.md](EXECUTION_PRINCIPLES.md) — *Change control*

---

## The freeze state — read this before filing anything

The two halves are easy to confuse:

**Track A (documents 00–27) is closed to addition from today.** No new scope, no new sections, no new specification, ever, except through a change request.

**It is not yet fully frozen.** Freezing is a V0 deliverable, gated on closing the two known contradictions **A-1** (display size) and **A-2** (battery removability). Those two are the last edits made *to* Track A rather than *through* the CR process. A-2 additionally cannot be written until the decision behind it is made — see [ADR-0001](docs/adr/0001-battery-removability.md).

After that, and from now on for everything else: **Track A changes only through a change request, and only when triggered by Track B.**

### Rules

1. **No CR without a trigger.** "It reads better" is not a trigger. Evidence, a decision, or a discovered contradiction is.
2. **One CR per decision.** Do not bundle.
3. **Search for downstream citations before accepting.** A-1 and A-2 exist because one document's statement was cited by another. Grep for the value you are changing.
4. **Log it here** with the CR number and the affected document IDs.

### Template

```markdown
## CR-NNN · <short title>
- **Date / author:**
- **Affected documents:** (list, with section numbers)
- **Trigger:** (which Track B evidence forced this — link the evidence folder)
- **Change:** (what specifically changes, quoting old and new text)
- **Impact:** (cost, schedule, certification, other subsystems, other documents)
- **Decision:** ACCEPTED / REJECTED / DEFERRED, with rationale
```

---

## Open change requests

Numbered and stated, **not yet applied.** A CR listed here has changed nothing until its Decision line reads ACCEPTED and the edit is made.

### CR-001 · Resolve display size contradiction (defect A-1)

- **Date / author:** 2026-07-31 · Founder
- **Affected documents:** [02](agri_intelligence_platform/02_hardware_device_srs.md) §L54, §L73, §L151 (frozen baseline) · [21](agri_intelligence_platform/21_components_milestones_critical_review.md) §L28 (component register)
- **Trigger:** Discovered contradiction. The "Frozen S1 baseline" specifies a **2.4-in** display; the costed component register buys a **Sharp 2.7-in** at ₹500–850. The ₹700 BOM line is priced against a part the frozen baseline does not specify.
- **Change:** *To be written once the size is chosen.* One value, propagated to all four locations.
- **Impact:** Part number, price, enclosure envelope, UI layout. Mechanical envelope is downstream, so this must close before CAD begins. Grep for `2.4` and `2.7` across 00–27 before accepting — this defect exists precisely because one document's number was cited by another.
- **Decision:** **OPEN.** Class: cheap (E-4) — decide within one working day. **Deadline 2026-08-03.** Deciding it needs no measurement; it needs a choice and a search-and-replace.

### CR-002 · Resolve battery removability contradiction (defect A-2)

- **Date / author:** 2026-07-31 · Founder
- **Affected documents:** [02](agri_intelligence_platform/02_hardware_device_srs.md) §L13 (commercial tier table), §L108 (electrical spec) · [16](agri_intelligence_platform/16_manufacturing_strategy.md) (design for disassembly) · [20](agri_intelligence_platform/20_benchmark_matrix_and_buildability.md) row 72 · [22](agri_intelligence_platform/22_tier_0_1_3_portable_product_srs.md) §L64
- **Trigger:** Discovered contradiction. The commercial tier table states "replaceable battery/probes" as a committed product attribute; the electrical spec says "removable pack **only if** … qualification"; the Tier 1 spec says "**only after** ingress validation". A commercial commitment has been made ahead of an engineering decision.
- **Change:** *Blocked.* **The decision must be made before the CR can be written** — see [ADR-0001](docs/adr/0001-battery-removability.md). Writing a CR now would be documenting a hope (E-9), which is the exact failure that produced this defect.
- **Impact:** **Blocks all mechanical work.** Determines gasket architecture, IP54 strategy, drop performance, tooling, parting lines, connector selection and ₹300–600 of BOM.
- **Decision:** **BLOCKED on ADR-0001, due 2026-08-07.**

### CR-003 … CR-008 · Fold review decisions D-13 – D-18 into documents 00–27

- **Date / author:** 2026-07-31 · Founder
- **Affected documents:** Various across 00–27 — one CR each, **not bundled** (rule 2)
- **Trigger:** Decisions D-13 through D-18 were made during buildability review and are recorded **only in [README.md](README.md#design-decisions).** Until folded in, README and Track A diverge, and README is authoritative where they conflict.
- **Change:** One CR per decision:

  | CR | Decision | Primary target |
  |---|---|---|
  | CR-003 | D-13 — primary buyer is an organisation with a trained operator, not an individual farmer | [01](agri_intelligence_platform/01_product_requirements_srs.md), [15](agri_intelligence_platform/15_business_model.md), [26](agri_intelligence_platform/26_india_market_adoption_and_cost_engineering.md) |
  | CR-004 | D-14 — pH and EC move out of Tier 1/2 to the operator tier | [02](agri_intelligence_platform/02_hardware_device_srs.md), [22](agri_intelligence_platform/22_tier_0_1_3_portable_product_srs.md) |
  | CR-005 | D-15 — voice and pictograms are the primary interface, not optional | [04](agri_intelligence_platform/04_mobile_app_srs.md) MOB-F-006 |
  | CR-006 | D-16 — marketplace removed from the roadmap | [10](agri_intelligence_platform/10_marketplace_supply_chain_srs.md), [18](agri_intelligence_platform/18_future_roadmap.md) |
  | CR-007 | D-17 — specify a system uncertainty budget, not an instrument tolerance | [02](agri_intelligence_platform/02_hardware_device_srs.md) or [25](agri_intelligence_platform/25_sensor_catalog_and_validation_protocols.md) — closes gap A-4 |
  | CR-008 | D-18 — freeze Track A; all effort to Track B | [00](agri_intelligence_platform/00_master_index_and_traceability.md) |

- **Impact:** Documentation consistency only. **No engineering impact and no evidence produced.** These sit *below* the evidence backlog in priority — CR-007 is the exception, because ±0.10 pH is a published-claim liability and the slurry-ratio measurement (backlog #4) will supply its replacement number.
- **Decision:** **OPEN — queued behind the evidence backlog.** Filing these is Track A work. Doing it before a single measurement exists would be the documentation-as-progress anti-pattern.

---

## Accepted change requests

*None. No Track B evidence exists yet, and therefore nothing has legitimately triggered a change to Track A.*

---

## Rejected / deferred

*None.*
