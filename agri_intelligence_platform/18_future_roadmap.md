# AgriGrow Future Roadmap

**Document ID:** AgriGrow-RD-018 | **Version:** 1.0

## North star

Create a trusted field-data layer that becomes more useful as protocols, calibration references, agronomy validation, service coverage and farmer consent mature—not merely as more sensors are added.

| Horizon | Outcomes | Preconditions / no-go rule |
|---|---|---|
| 0–12 months | S1 base device, Android app, secure ingest, pH/EC/moisture validation, pilot dashboards | Do not scale before multi-zone field validation, repair workflow and privacy controls work. |
| 12–24 months | Cellular institutional SKU, multilingual voice assistance, FPO fleet tools, improved regional moisture models, controlled marketplace | Ship only modules with radio/certification and service plan; advice remains evidence-bounded. |
| 24–36 months | Fixed environmental stations, research-grade moisture accessory, lab-result integration, richer crop-stage/pest evidence capture | Validate sensor/label data and avoid conflating device indicator with lab diagnosis. |
| 36+ months | Validated nutrient/organic-carbon assay partnerships, digital twins, public-interest aggregates, interoperable national connectors | Adoption requires protocol, equity, consent, independent accuracy and governance review. |

## Ten-year hardware generations

| Generation | Indicative period | Hardware focus | Evidence gate |
|---|---|---|---|
| G1 | 2026–27 | Tier 0 assisted kit, Tier 1 Pocket Basic, Tier 2 Field Scout S1; common event/probe/calibration contract | Multi-zone measurement/usability and service pilot prove the platform can be trusted. |
| G2 | 2028–29 | Tier 3 FieldLab Backpack, standardised water module, shared charging/service ecosystem and multilingual assisted workflows | FPO/KVK fleet economics, operator reproducibility and repair turnaround meet target. |
| G3 | 2029–30 | Tier 4 Solar Farm Tower, wireless soil probes and managed LoRa/cellular backhaul | Seasonal energy autonomy, site-installation quality and weather/soil reference validation pass. |
| G4 | 2031–32 | Tier 5 network, edge gateway, camera evidence and bounded irrigation/fertigation integrations; Tier 6 research station | Actuation safety case, network reliability and independent research reproducibility are accepted. |
| G5 | 2033–35 | Tier 7 district operations, Tier 8 state grids and Tier 9 national federation; validated next-generation sensing only where evidence permits | Governance, interoperability, privacy, coverage-bias and resilience audits approve expansion. |

Generations overlap; a farmer should not have to replace a working device merely because a higher tier is launched. Backward compatibility means preserving interpretation/provenance and supported sync, not asserting that legacy sensor accuracy equals a newer instrument.

## Research backlog

Prioritise soil-specific moisture calibration; pH/EC sampling protocol adherence; probe ageing/contamination detection; low-power reliable air/particulate accessory design; multilingual explanation comprehension; causal evaluation of advisories; privacy-preserving spatial aggregation; and climate/disaster alert usefulness. For nitrogen, phosphorus, potassium, organic carbon, microbial health, heavy metals and water contamination, evaluate lab-on-chip/optical/electrochemical methods only against reference laboratories across real Indian soils. A low-cost “instant NPK” reading must remain a research hypothesis unless accuracy, interference, calibration burden and field maintenance meet published acceptance criteria.

## Architecture evolution rules

Maintain versioned event/schema contracts and probe abstraction so a new sensor does not break historic interpretation. Treat every new capability as a controlled product line with safety case, calibration protocol, service consumables, privacy impact, model card, compliance assessment, manufacturing source and lifecycle owner. Deprecate APIs and firmware only with field migration evidence; retain a safe measurement-only mode for older supported devices.

## Decision triggers

- Add embedded cellular when phone-gateway failure demonstrably prevents required programme outcomes and total cost/support is justified.
- Add a sensor only when its measurement method, confidence, calibration/service path and farmer action are all defined.
- Expand government/research sharing only after coverage-bias, re-identification and programme-benefit evaluation.
- Automate a recommendation only after a human-in-the-loop pilot demonstrates safety and benefit in the intended crop/region.

The roadmap is intentionally evidence-gated. The strongest platform compounds reliable observations, farmer trust and regional validation; feature volume is not the objective.
