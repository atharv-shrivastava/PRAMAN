# PRAMAN

**P**latform for **R**egulatory **A**ssessment, **M**onitoring, **A**uthentication & **N**otification

**Project title:** An AI-Powered Regulatory Document Verification and Institutional Compliance Intelligence Platform  
**Tagline:** *Every claim needs evidence.*

> **Status:** This repository currently documents a proposed prototype. It does not claim that a deployed system, live AICTE integration, or external verification access already exists.

## What PRAMAN does

PRAMAN is a decision-support platform for AICTE approval-related applications. It helps institutions submit applications and evidence, and helps authorized AICTE officers identify missing information, expired documents, cross-document inconsistencies, historical changes and items requiring further verification.

PRAMAN supports regulatory scrutiny; it does not replace statutory checks, inspections, or decisions reserved for the competent authority.

## Signature innovation

### Compliance Memory Graph
Connects an institution's applications, documents, extracted claims, regulatory rules, source-verification results and officer actions across application cycles.

### Compliance Drift Engine
Compares current evidence with permitted historical records, detects meaningful changes, traces potentially affected validation checks and explains what needs re-verification.

### Evidence-linked findings
Every finding should show its reason, relevant document/page, extracted value, applicable rule and next recommended action. An AI flag is an investigative lead, not proof of fraud or non-compliance.

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

The complete feature-by-feature specification, architecture notes, workflow, data model, API outline, verification strategy, roadmap, testing plan and demonstration scenarios are packaged in **[the detailed documentation ZIP](docs/PRAMAN-GitHub-Docs.zip)**.

| # | Feature | Purpose |
|---|---|---|
| 1 | Institution profile & applications | Maintain institution identity, application categories, academic years and history. |
| 2 | Secure document ingestion & versioning | Validate uploads, store files privately and preserve versions. |
| 3 | Document understanding | OCR, classification, field extraction and page-level evidence. |
| 4 | Regulatory rule engine | Run deterministic, versioned checks against the applicable checklist. |
| 5 | Cross-document intelligence | Compare related claims across submitted documents. |
| 6 | Compliance Memory Graph | Link institutions, applications, evidence, rules and review decisions. |
| 7 | Compliance Drift Engine | Identify historical changes and trace affected checks. |
| 8 | Authorized source verification | Use official verification mechanisms where supported and authorized. |
| 9 | Integrity & anomaly detection | Detect duplicates and suspicious indicators for further review. |
| 10 | Infrastructure evidence assistance | Flag documentary or visual evidence gaps where feasible. |
| 11 | Findings & officer workbench | Present evidence, explanations, status and officer actions. |
| 12 | Institution response loop | Support deficiency requests, replacement documents and revalidation. |
| 13 | Rule change management | Version and approve checklists and regulatory rules. |
| 14 | Alerts & notifications | Notify relevant users of pending work and deadlines. |
| 15 | Audit trail | Record submissions, processing, source responses and review actions. |
| 16 | Dashboards & reports | Summarize application status, findings, ageing and verification outcomes. |
| 17 | AI design & boundaries | Define responsible AI uses, structured outputs and human review. |
| 18 | Security & privacy | Enforce access control, private storage, data minimization and retention controls. |

## Proposed users

- **Institution users:** create applications, upload evidence, review permitted deficiencies and respond to requests.
- **AICTE officers/reviewers:** inspect evidence, review findings, record observations and take authorized workflow actions.
- **System/rule administrators:** manage users, document categories, approved checklists, rule versions and connector configuration.

Access must be role-based and institution-scoped. Institution users must not be able to access another institution's restricted records.

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

## Repository contents

- `README.md` — product overview, workflow and feature index
- `docs/PRAMAN-GitHub-Docs.zip` — detailed documentation pack with individual feature specifications
- `PROJECT_STATUS.md` — implementation status and scope
- `GITHUB_UPLOAD_GUIDE.md` — guidance for extracting and navigating the detailed documentation pack

Feature status must be updated only after implementation and testing are demonstrated.
