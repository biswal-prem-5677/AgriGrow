# AgriGrow Research Platform — System Requirements Specification

**Document ID:** AgriGrow-RES-SRS-009 | **Version:** 1.0

## 1. Purpose

The research platform enables reproducible, permissioned analysis of agricultural observations and linked lab/field outcomes. It must improve evidence without turning farmer data into an unrestricted commodity.

## 2. Study workflow

Researcher submits protocol, purpose, fields/variables, geography/time range, retention, collaborators and planned outputs. Data steward verifies legal basis, consent compatibility, ethics/IRB (where applicable), de-identification risk and minimum necessary fields. An approved dataset is generated as a versioned release with data dictionary, schema, provenance, quality definition, transformation code hash and citation DOI/internal identifier. Results may be reviewed for disclosure risk before release.

## 3. Capabilities

- Dataset catalogue with variable-level sensitivity, method, units, coverage, calibration provenance and known limitations.
- Secure project workspace or controlled export depending on risk tier; no default external-network access for high-risk workspaces.
- Link sensor observations to lab references through pseudonymous sample IDs and time/location tolerances approved by study protocol.
- Reproducible notebooks/jobs pinned to dataset release, container/image, code commit and model version.
- Data-quality tools for unit/method comparison, missingness, calibration state and representative sampling review.

## 4. Controls

Direct identifiers are removed before research release; precise geography and dates are generalised or transformed according to risk assessment. Small groups are suppressed, not merely masked. Researchers cannot use the platform to re-identify, contact or profile farmers; attempts are monitored and may revoke access. Retention expiry destroys workspace keys/exports where technically and legally appropriate, and all release uses are logged.

## 5. Scientific limits

The platform labels device sensor values as field measurements with stated method/uncertainty, not as laboratory assays. Soil texture, depth, water content, salinity, crop practice and site selection can confound results. Publications must state device/firmware/probe/calibration versions, inclusion filters, missing-data handling, geography/time limitations and whether results are observational or causal.
