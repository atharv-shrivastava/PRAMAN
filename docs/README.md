# PRAMAN Documentation

New here? Start with **[PRAMAN in plain English](START_HERE.md)**. This guide explains the idea, key terms, workflow, and what is planned versus implemented.

## Suggested reading order

| Step | Read | What you'll learn |
|---|---|---|
| 1 | [Product overview](01-product-overview.md) | The problem PRAMAN is designed to solve and its main principles |
| 2 | [User roles and access](02-user-roles-and-access.md) | What institution users, officers, and administrators can do |
| 3 | [End-to-end workflow](03-end-to-end-workflow.md) | What happens from application creation to officer review |
| 4 | [System architecture](architecture/system-architecture.md) | How the frontend, backend, database, OCR, and AI fit together |
| 5 | [Data model](architecture/data-model.md) | The main records and how they relate |
| 6 | [Prototype roadmap](planning/prototype-roadmap.md) | What should be built first |

## Feature specifications

These files explain the intended behaviour of individual parts. They are specifications, not proof that the feature has been implemented.

### Applications and documents
1. [Institution profile and applications](features/01-institution-profile-and-applications.md)
2. [Secure document ingestion and versioning](features/02-document-ingestion-and-versioning.md)
3. [OCR, classification, and structured extraction](features/03-document-understanding.md)

### Validation and compliance intelligence
4. [Configurable regulatory rule engine](features/04-regulatory-rule-engine.md)
5. [Cross-document intelligence](features/05-cross-document-intelligence.md)
6. [Compliance Memory Graph](features/06-compliance-memory-graph.md)
7. [Compliance Drift Engine](features/07-compliance-drift-engine.md)
8. [Authorized source verification](features/08-source-verification.md)
9. [Document integrity and anomaly detection](features/09-integrity-and-anomaly-detection.md)
10. [Infrastructure evidence assistance](features/10-infrastructure-evidence-assistance.md)

### Review and governance
11. [Evidence-linked findings and officer workbench](features/11-findings-and-officer-workbench.md)
12. [Institution response and correction loop](features/12-institution-response-loop.md)
13. [Rule and checklist change management](features/13-rule-change-management.md)
14. [Alerts and notifications](features/14-alerts-and-notifications.md)
15. [Audit trail](features/15-audit-trail.md)
16. [Dashboards, analytics, and reports](features/16-dashboards-and-reports.md)
17. [AI design and boundaries](features/17-ai-design-and-boundaries.md)
18. [Security, privacy, and governance](features/18-security-and-privacy.md)

## Technical design

- [System architecture](architecture/system-architecture.md) — major services and their connections.
- [Data model](architecture/data-model.md) — records, relationships, and persistence.
- [API outline](architecture/api-outline.md) — proposed backend endpoints.
- [Verification-source strategy](architecture/verification-source-strategy.md) — what external verification may be possible, subject to authorization and access.

## Planning and testing

- [Prototype roadmap](planning/prototype-roadmap.md) — recommended implementation phases.
- [Testing and evaluation](planning/testing-and-evaluation.md) — how to measure correctness and quality.
- [Demonstration scenarios](planning/demo-scenarios.md) — suggested demo cases using synthetic or authorized data.
- [Glossary](glossary.md) — definitions of project terms.

## Project status and repository guidance

- [Current project status](../PROJECT_STATUS.md) — documented work, current limits, and next engineering milestone.
- [GitHub upload guide](../GITHUB_UPLOAD_GUIDE.md) — repository/documentation guidance.

**Important:** This repository currently holds the product design and proposed prototype plan. Treat a feature as implemented only when working code and appropriate tests or integration evidence exist. Any simulated verification result must be clearly labelled **SIMULATED**.
