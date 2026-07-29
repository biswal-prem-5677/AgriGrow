# AgriGrow Security and Privacy — System Requirements Specification

**Document ID:** AgriGrow-SEC-SRS-012 | **Version:** 1.0

## 1. Security objectives and threat model

Protect farmer data, measurement integrity, device identity, advisory safety and service availability against lost/stolen devices, malicious Bluetooth peers, counterfeit probes/devices, firmware tampering, account takeover, API abuse, insider misuse, supply-chain compromise, malicious model inputs and regional outage. Asset classification: direct identity/contact and precise location are restricted; field observations are confidential; authorised aggregates are controlled; firmware/public documentation may be public. Classifications travel with data and shape logging, export and retention.

## 2. Controls by layer

| Layer | Mandatory controls |
|---|---|
| Hardware/firmware | Secure boot, signed A/B updates, locked debug, unique non-exportable key where available, encrypted local store, physical tamper evidence and secure production provisioning. |
| Mobile/web | OIDC, short-lived tokens, device-bound secure storage, MFA for privileged roles, rate limits, secure session recovery, OWASP testing and no secrets in client. |
| Cloud | Least-privilege workload identities, network segmentation, secrets manager, encryption in transit/at rest, tenant/purpose-aware authorization, WAF/DDoS controls and immutable audit trails. |
| Data/AI | Data minimisation, redacted logs, feature permissions, model registry/change approval, prompt/tool isolation, advisory provenance and kill switch. |
| People/process | Background/role controls proportionate to access, security training, reviewed access, supplier security due diligence, incident runbooks and vulnerability disclosure channel. |

## 3. Privacy requirements

Collect only data needed for a stated farmer/service/programme purpose. Consent UI is local-language, granular, revocable and records notice version, actor, time and scope; withdrawal affects future processing subject to lawful/contractual retention exceptions. Do not make app account, marketplace marketing or research sharing a condition of basic device measurement. Provide authenticated access/correction/export/deletion request paths and a documented identity-verification and response workflow.

Apply purpose-based access rather than a single “logged in” permission. Government/research access is separately approved, time-limited and aggregate/de-identified by default. Precise farm coordinates must be transformed/suppressed in data releases after re-identification review. Privacy impact assessments are required for new sensitive data types, new external sharing, location analytics, biometrics, automated eligibility or material AI changes.

The Digital Personal Data Protection Act, 2023 is the baseline legal reference, but implementation must be reviewed against its commencement notifications, rules, sectoral rules and applicable state/contract requirements at launch. The Act itself is available from [MeitY](https://www.meity.gov.in/static/uploads/2024/02/Digital-Personal-Data-Protection-Act-2023.pdf).

## 4. Assurance and incident response

Maintain asset inventory, threat models, secure SDLC, SBOMs, dependency scanning, penetration tests, third-party assessments, annual tabletop exercises and continuous security logging. Severity triage defines containment, evidence preservation, communication/notification assessment, recovery and root cause. A suspected signing-key/device-key compromise triggers credential revocation, campaign pause, forensic preservation and customer-impact assessment. Security bugs have a published reporting channel and remediation SLAs; secrets/keys are never placed in tickets, screenshots or analytics.
