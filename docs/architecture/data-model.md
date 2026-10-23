# Data Model

The proposed MVP can represent the Compliance Memory Graph with relational tables and foreign-key links in PostgreSQL.

## Core tables
- **users:** authenticated identity, role and account state.
- **institutions:** permanent identifier where available, name, aliases and permitted profile details.
- **applications:** institution, category, academic year, status and checklist/rule version.
- **documents:** application, category, private storage key, checksum, version, uploader and processing status.
- **extracted_fields:** document version, field name, value, page/source excerpt, extraction method and confidence metadata.
- **regulatory_rules:** rule code, source, applicability, version, effective period and approval status.
- **validation_runs:** application/document scope, rule version, start/end time and status.
- **validation_findings:** rule, compared values, evidence links, severity, status and resolution.
- **source_verifications:** source/connector, request reference, timestamp, normalized result and comparison details.
- **evidence_links:** relationships between claim, document, application, rule and historical record.
- **review_actions:** actor, action, reason, timestamp and linked finding/application version.
- **notifications:** recipient, event, delivery status and provider reference.
- **audit_events:** chronological record of significant changes and access events.

## Design rules
Use generated IDs, foreign keys, indexes on institution/application/status/date, unique constraints for identifiers and transaction boundaries for multi-step state changes. Do not store full file binaries in ordinary relational rows; store them in private object storage.

## Versioning and provenance
Treat source document versions as immutable. Every extracted field and validation result must identify the exact source version and rule version used. A new upload produces a new version and causes affected checks to rerun.

## Access control
Use backend authorization and, where supported, database row-level security. Derive institution scope from trusted user mapping. Test cross-institution access explicitly.