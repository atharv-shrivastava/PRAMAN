# Prototype Roadmap

## Phase 1 — Foundation
Set up React/Vite, Express, PostgreSQL, authentication, institution scoping, application creation and private document storage. Establish database migrations and a simple audit event model.

**Exit criteria:** an authorized user can create an application and upload a private file; unauthorized cross-institution access is blocked.

## Phase 2 — Document processing
Support three chosen document types, PDF text extraction, OCR for scans, classification and schema-constrained field extraction. Store page-level provenance and handle unsupported files.

**Exit criteria:** a sample document produces structured fields that can be checked against labelled ground truth.

## Phase 3 — Deterministic checks
Implement checklist completeness, date/expiry and selected cross-field checks. Record rule versions and evidence for each finding.

**Exit criteria:** rule tests are repeatable and do not require an AI model to reach the same result.

## Phase 4 — Differentiator
Implement linked claims and evidence, historical comparison, change detection and affected-check tracing.

**Exit criteria:** the demo shows before/after values, sources and the checks that need revalidation.

## Phase 5 — Officer workflow
Add evidence viewer, review actions, clarification requests, institution response, versioned replacement and audit history.

**Exit criteria:** a finding can be resolved through a complete and traceable user workflow.

## Phase 6 — Connectors and polish
Add a labelled mock verification service, dashboard summaries, notifications, export and evaluation reporting. Pursue real external integrations only after access is approved.

## Scope control
Defer advanced visual forgery analysis, broad infrastructure computer vision and multiple AI models until the core pipeline is reliable.