# AgriGrow Manufacturing Strategy

**Document ID:** AgriGrow-MFG-016 | **Version:** 1.0

## 1. Make-in-India production strategy

Start with an Indian EMS partner capable of controlled PCB assembly, test fixtures, traceability and NPI support; source globally where necessary but qualify local/regional alternates for enclosure, cables, battery packs, packaging and final assembly. Treat pH/EC probes and optical/precision sensors as quality-critical supply chains requiring incoming verification—not commodities selected only on lowest quote.

Supplier selection is an RFI/RFQ process, not a static list: verify financial stability, ISO-quality system, ESD controls, BGA/6-layer capability, test engineering, traceability, counterfeit avoidance, environmental compliance, repair handling, capacity ramp, export/logistics, data/IP protection and willingness to support failure analysis. Obtain at least two qualified sources for strategic components where realistic; avoid falsely dual-sourcing precision sensors without revalidation.

## 2. NPI gates

| Gate | Deliverables | Approval condition |
|---|---|---|
| EVT | Engineering BOM, prototypes, bring-up fixtures, architecture risks | Functions and measurement principles demonstrated |
| DVT | Frozen mechanical/electrical design candidate, DFM/DFT, reliability/cert pre-scan | Design requirements and calibration method validated |
| PVT | Tooling, work instructions, test stations, supplier quality plans | Line yield, fixture GR&R, traceability and packaging validated |
| MP | Controlled ramp, first article, lot controls, service spares | Release board accepts measured yield/reliability/cert evidence |

No production part substitution is allowed without engineering change control: form/fit/function, AFE/RF/EMC/measurement impact, firmware/SBOM effect, requalification and inventory disposition must be assessed.

### Manufacturing route by product family

| Tier family | Recommended production route | Critical controls |
|---|---|---|
| 0 | Indian kitting/printing and controlled chemical/consumable procurement | Lot/expiry, comparator consistency, language/protocol inserts and QR batch traceability. |
| 1–3 | EMS-built PCBA, injection-moulded portable enclosure and final functional/calibration line | RF/AFE segregation, probe identity, secure provisioning, fixture GR&R and repairable construction. |
| 4 | Low/medium-volume station assembly with qualified mast, solar, battery and enclosure suppliers | Solar/power derating, sealing, surge/earthing, cable glands, site-installation kit and burn-in. |
| 5–6 | Project integration plus factory-accepted modules; commissioning by trained partners | Radio survey, site acceptance, sensor installation geometry, actuator safety boundary and spares strategy. |
| 7–9 | Systems integration and software/service operations, not mass manufacture of a single device | Interoperability certification, secure federation, data-steward handover, capacity and DR acceptance. |

Shared modules should use a common approved-vendor list only where the electrical, environmental and calibration profiles actually match. For example, a Tier 2 pH electrode may share a connector with a Tier 3 kit but must not be substituted for a Tier 6 reference probe without its own qualification.

## 3. Assembly and test flow

1. Receive/inspect parts with lot identity, MSL/ESD controls and critical-sensor sampling.
2. SMT 6-layer PCB; SPI/AOI/X-ray where package requires; reflow profile recorded by lot.
3. ICT/flying-probe and programmed functional fixture: rails, current, MCU debug lock, RF identity, display/UI, sensor buses, AFE reference response, USB-C and storage.
4. Secure provisioning in a segregated station: device certificate/public identity, signed firmware, test attestation; private-key process is audited and never displayed/logged.
5. Enclosure build, gasket/torque verification, antenna placement, probe/cable test, barcode/QR scan.
6. Final functional/calibration verification against traceable references, cosmetic/packaging scan and electronic device history record.

Fixture design must use golden units, periodic self-check, calibration interval, operator access control and measurement-system analysis. Final test records link unit serial to firmware, component lots, fixture result and operator/time. Quarantine failures; track Pareto yield loss and complete FRACAS for recurring defects.

## 4. Mechanical, sustainability and repair

Use PC+ABS/TPE selected for UV, chemical, sweat and impact validation. Tool draft, gate, sink, weld lines, gasket compression and antenna detuning must be reviewed before hard tooling. Design for disassembly: captive screws, no destructive adhesive around replaceable battery/probe/display where avoidable, labelled material types, and a spare-parts/service manual. Collect end-of-life units through authorised channels; design packaging to minimise single-use plastic and comply with applicable e-waste/EPR obligations verified at launch.

## 5. Compliance and quality plan

Create a living India/SKU compliance matrix with accredited test lab engagement before DVT. Certification applicability is product- and radio-configuration-specific; BIS lists notified compulsory categories and the TEC maintains IoT/MTCTE material, so engineering must not assume a generic approval is sufficient. [BIS notified products](https://www.bis.gov.in/product-certification/products-under-compulsory-certification/?lang=en) · [TEC MTCTE](https://www.tec.gov.in/public/mandatory-testing-and-certification-of-telecom-equipments-mtcte). Maintain CE/FCC or other export plans separately.

Key quality metrics: incoming defect ppm, first-pass yield, rework, test escape, field return rate, no-fault-found, calibration drift, supplier corrective-action closure and repair turnaround. Target a deliberate 3-year service life; provide consumable availability and software/security support commitments before sale.
