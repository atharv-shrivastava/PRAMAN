# PRAMAN

**P**latform for **R**egulatory **A**ssessment, **M**onitoring, **A**uthentication & **N**otification

**Project title:** An AI-Powered Regulatory Document Verification and Institutional Compliance Intelligence Platform  
**Tagline:** *Every claim needs evidence.*

> **Status:** This repository documents a proposed prototype. It does not claim that a deployed system, live AICTE integration, or external verification access already exists.

## What PRAMAN does

PRAMAN is a decision-support platform for AICTE approval-related applications. It helps institutions submit applications and supporting evidence, and helps authorized AICTE officials identify missing information, expired documents, cross-document inconsistencies, historical changes and items requiring further verification.

PRAMAN supports regulatory scrutiny; it does not replace statutory checks, inspections, or decisions reserved for the competent authority.

## Signature innovation

### Compliance Memory Graph
Links an institution's applications, documents, extracted claims, regulatory rules, source-verification results and officer actions across application cycles.

### Compliance Drift Engine
Compares current evidence with permitted historical records, detects meaningful changes, traces potentially affected validation checks and explains what needs re-verification.

### Evidence-linked findings
Each finding should show its reason, relevant document/page, extracted value, applicable rule and next recommended action. An AI flag is an investigative lead, not proof of fraud or non-compliance.

## End-to-end workflow

1. Institution creates an application and selects its category and academic year.
2. PRAMAN builds the applicable checklist from an approved, versioned rule configuration.
3. Institution uploads supporting documents; files are validated and stored privately with version history.
4. PDF text extraction/OCR identifies text; AI classifies documents and extracts structured fields with evidence.
5. Deterministic rules check required information, dates and configured requirements.
6. Cross-document comparison looks for conflicting names, dates, identifiers and other claims.
7. The Compliance Memory Graph links current evidence to relevant application history and requirements.
8. The Compliance Drift Engine identifies changes and checks that may need to be rerun.
9. Verification connectors query authorized sources when available. Unsupported checks are marked for manual verification; mock checks must be labelled as simulated.
10. PRAMAN produces evidence-linked findings for an authorized officer.
11. The officer reviews evidence, records observations and may request clarification where the prescribed process permits.
12. New evidence is stored as a new version; affected checks rerun and the audit history is preserved.

## Feature catalogue

Open the [complete documentation index](docs/README.md) to access each feature specification independently.

| # | Feature | Specification |
|---|---|---|
| 1 | Institution profile and application management | [Read](docs/features/01-institution-profile-and-applications.md) |
| 2 | Secure document ingestion and versioning | [Read](docs/features/02-document-ingestion-and-versioning.md) |
| 3 | OCR, classification and structured extraction | [Read](docs/features/03-document-understanding.md) |
| 4 | Configurable regulatory rule engine | [Read](docs/features/04-regulatory-rule-engine.md) |
| 5 | Cross-document intelligence | [Read](docs/features/05-cross-document-intelligence.md) |
| 6 | Compliance Memory Graph | [Read](docs/features/06-compliance-memory-graph.md) |
| 7 | Compliance Drift Engine | [Read](docs/features/07-compliance-drift-engine.md) |
| 8 | Authorized source verification | [Read](docs/features/08-source-verification.md) |
| 9 | Document integrity and anomaly detection | [Read](docs/features/09-integrity-and-anomaly-detection.md) |
| 10 | Infrastructure evidence assistance | [Read](docs/features/10-infrastructure-evidence-assistance.md) |
| 11 | Evidence-linked findings and officer workbench | [Read](docs/features/11-findings-and-officer-workbench.md) |
| 12 | Institution response and correction loop | [Read](docs/features/12-institution-response-loop.md) |
| 13 | Rule and checklist change management | [Read](docs/features/13-rule-change-management.md) |
| 14 | Alerts and notifications | [Read](docs/features/14-alerts-and-notifications.md) |
| 15 | Audit trail | [Read](docs/features/15-audit-trail.md) |
| 16 | Dashboards, analytics and reports | [Read](docs/features/16-dashboards-and-reports.md) |
| 17 | AI design and boundaries | [Read](docs/features/17-ai-design-and-boundaries.md) |
| 18 | Security, privacy and governance | [Read](docs/features/18-security-and-privacy.md) |

## Architecture and planning

- [Product overview](docs/01-product-overview.md)
- [User roles and access model](docs/02-user-roles-and-access.md)
- [End-to-end workflow](docs/03-end-to-end-workflow.md)
- [System architecture](docs/architecture/system-architecture.md)
- [Data model](docs/architecture/data-model.md)
- [API outline](docs/architecture/api-outline.md)
- [Verification-source strategy](docs/architecture/verification-source-strategy.md)
- [Prototype roadmap](docs/planning/prototype-roadmap.md)
- [Testing and evaluation plan](docs/planning/testing-and-evaluation.md)
- [Demonstration scenarios](docs/planning/demo-scenarios.md)
- [Glossary](docs/glossary.md)
- [Project status](PROJECT_STATUS.md)

## Proposed technology stack

- **Frontend:** React + Vite
- **Backend:** Node.js + Express
- **Database:** PostgreSQL, potentially hosted through Supabase
- **File storage:** private object storage such as Supabase Storage
- **OCR:** RapidOCR or a benchmarked alternative
- **AI extraction:** a model API such as Gemini with schema-constrained output
- **Validation:** deterministic rules and Zod schemas
- **Processing:** PDF text extraction and page rendering tools
- **Reporting:** charting and PDF-export libraries

The first implementation should be a modular monolith. A graph database is not required for the MVP; relationships can be represented in PostgreSQL.

## Proposed MVP

Start with one application category and three supported document types. Demonstrate one complete flow: upload → extraction with source evidence → deterministic validation → cross-document comparison → officer review → recorded resolution. Add external source verification only where authorization and technical access are confirmed. Otherwise, use clearly labelled simulated responses.

## Safety, privacy and regulatory boundaries

- AI-generated findings are advisory and must not independently reject an institution or declare a document forged.
- An unavailable source is not evidence that a document is false.
- Public website access does not imply API availability or permission to automate access.
- Institutional records and external sources must be accessed only with appropriate authorization.
- Applicable rules and checklists must be grounded in current authoritative material and approved by authorized personnel.
- Protect uploads, restrict access, preserve audit history and apply appropriate retention controls.
- Use synthetic or authorized anonymized test data for demonstrations.

## Evaluation plan

Measure field-extraction accuracy against labelled test data, rule-validation accuracy, false-positive rate, evidence traceability, processing time, verification outcomes and officer review effort. Report actual measured results; do not claim untested accuracy.

See [Project Status](PROJECT_STATUS.md) for the current documented scope and next implementation milestone.