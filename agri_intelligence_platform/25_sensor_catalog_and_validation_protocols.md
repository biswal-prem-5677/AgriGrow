# AgriGrow Sensor Catalogue and Validation Protocols

**Document ID:** AGR-SEN-025 | **Rule:** a sensor class is not released until its product-level method, calibration, cleaning, lifetime and failure limits are validated.

## 1. Production sensor catalogue

| Parameter / tier | Principle and recommended class | Range / product target | Calibration, care and expected life | Failure / alternative / buildability |
|---|---|---|---|---|
| pH water / slurry T1–3 | Replaceable double-junction glass combination electrode + guarded electrometer | 0–14 pH; T2 target ±0.10 after valid calibration | 2/3-point pH 4.01/7/10.01; rinse/store wet; 6–18 month consumable | Dry/contaminated junction, cable leakage; ISFET is future upgrade; READY TODAY |
| EC/TDS/salinity T1–3 | 4-electrode AC conductivity cell; TDS is converted, not sensed | 0–20 mS/cm, T2 ±2% reading target | Cell constant + reference solution; rinse/dry; 1–3 year probe | Polarisation/fouling/temperature; two-electrode is limited cost alternative; READY TODAY |
| Soil VWC T1–6 | FDR/capacitance for portable/fixed; TDR/reference probes for Tier 6 | Relative trend T1; validated VWC T2 target ±3–5% in stated soil profile | Gravimetric regional curves, depth/contact record; 3–10 years fixed probe | Salinity, texture, air gaps, installation; TDR/water-potential complement; READY TODAY with site calibration |
| Soil temperature T1–6 | NTC/RTD adjacent to probe | −20–60 °C; ±0.5 °C target | Two-point check; inspect cable annually | Cable ingress/thermal lag; READY TODAY |
| Ambient T/RH T1–6 | Vented digital T/RH (SHT41-class) | −40–85 °C, 0–100% RH; ±0.3 °C/±2–3% RH system target | Factory reference check; clean shield/membrane; 3–5 years | Solar/self-heating/condensation; aspirated shield for research; READY TODAY |
| Pressure T2–6 | MEMS barometer (BMP390-class) | 300–1250 hPa; ±1 hPa system target | Factory/altitude plausibility; 5+ years | Port blockage/thermal gradient; READY TODAY |
| Light / PAR proxy / UV T2–6 | Photodiode ALS/UV; true PAR needs calibrated quantum sensor | Lux/UV index; labelled proxy where not PAR | Dark/reference/window clean; annual optical check | Window ageing/orientation; quantum pyranometer for research; READY TODAY |
| Rain T4–6 | Tipping bucket preferred for depth; capacitive plate only wet/dry | 0–500 mm/h stated by chosen head | Levelling, debris check, volume calibration; 3–5 years | Blockage/tilt/insect ingress; optical rain is alternative; READY TODAY |
| Wind speed/direction T4–6 | Ultrasonic preferred; cup/vane cost alternative | 0–40 m/s target, stated accuracy | Mast orientation, annual reference/cleaning | Bearing wear/cable/mast turbulence; READY TODAY |
| CO₂ T3–6 accessory | NDIR, not MOS eCO₂ | 400–10,000 ppm typical | Zero/span/warm-up and vent cleaning; 5–10 years | Humidity/thermal/power budget; MOS eCO₂ is not interchangeable; READY TODAY accessory |
| VOC T3–6 accessory | MOX index sensor | Relative index, not gas-speciation claim | Baseline/warm-up/contamination cycle; 3–5 years | Cross-sensitivity/drift; PID/lab GC are alternatives; NEEDS ENGINEERING for field advice |
| PM2.5/PM10 T4–6 accessory | Laser scattering with controlled inlet/fan | Manufacturer stated µg/m³ range | Flow/inlet cleaning/reference campaign; 2–5 years | Humidity/dust/fan contamination; regulatory monitor is separate; NEEDS ENGINEERING |
| Water turbidity T3–6 | Nephelometric optical flow-cell | 0–1,000 NTU class by module | Formazin/reference check, clean cell | Biofouling/bubbles/colour; READY TODAY screening |
| Camera/plant evidence T3–6 | RGB camera; calibrated thermal/multispectral only for defined models | Image + illumination/geometry metadata | Lens target/white balance/aim check; seasonal clean | Lighting/domain shift/privacy; NEEDS ENGINEERING |
| N/P/K / organic C / microbial / metals | Wet chemistry, spectroscopy or lab assay | No generic portable production accuracy target | Lab reference, crop/soil-specific validation | Cross-interference/sample extraction; RESEARCH STAGE |

## 2. Required validation design

For each released sensor: define reference instrument/lab, number of devices/lots/operators/sites, environmental range, sample method, calibration curve/version, repeated-measure variance, bias/RMSE/limits of agreement, failure injection, cleaning/service interval, uncertainty statement and advisory eligibility. Test both new and aged/contaminated probes. A result may be visually plausible but still fails release if reproducibility or method traceability is weak.

### Minimum sample sizes and gates

| Class | Minimum evidence before release |
|---|---|
| Tier 0 manual screen | ≥3 kit lots, ≥30 trained/novice observations, lab comparison and explicit observer/lighting error result |
| Portable pH/EC | ≥10 devices, ≥3 probe lots, ≥3 operators, buffer/reference range, temperature/ageing and field protocol study |
| Soil moisture | ≥3 soil classes, ≥3 depths/installation modes, gravimetric reference, salinity/temperature range and seasonal repeat |
| Tower weather | ≥5 stations, co-location with reference head for ≥30 days plus installation/recovery test |
| AI/vision | Held-out farm/time/crop split, confidence/calibration, error-by-condition report and human escalation test |

## 3. Supplier and lifecycle policy

Use manufacturer datasheet plus independent/reference comparison; never rely solely on marketplace description. Maintain lot/serial/calibration data and alternate-class revalidation. Indian supply is through authorised lab/instrument/EMS channels; Chinese availability may reduce cost but cannot waive traceability, incoming inspection, RF/compliance or measurement validation. Consumables are planned as subscription/service inventory, not one-time hardware margin.
