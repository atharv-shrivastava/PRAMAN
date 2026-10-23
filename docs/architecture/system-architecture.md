# System Architecture

## Recommended shape
Start as a modular monolith with a separate OCR worker only if operationally useful. Avoid microservices until an actual scaling or isolation requirement justifies them.

## Components
- **React + Vite frontend:** institution portal, officer workbench and administration screens.
- **Express API:** authentication integration, permissions, application workflow and business rules.
- **PostgreSQL:** institutions, applications, document metadata, extracted fields, rules, findings, verification results and audit events.
- **Private object storage:** original uploads and immutable document versions.
- **Processing worker:** PDF parsing, rendering, OCR and structured extraction job orchestration.
- **AI adapter:** calls the configured model and validates schema-constrained responses.
- **Rule engine:** deterministic, versioned regulatory checks.
- **Verification adapters:** authorized external services or clearly labelled mock connectors.
- **Notification worker:** controlled alerts and retry handling.

## Data flow
Upload → private storage → extraction job → extracted claims/evidence → validation and comparison → findings/graph links → officer review → audit events and reporting.

## Reliability
Use job IDs and idempotency, explicit processing states, retries with limits, timeouts and dead-letter/manual-review paths. External service failures must not make the application appear verified.

## Deployment
Separate development, test and production environments. Keep secrets out of frontend bundles and repositories. Use database migrations, health checks, structured error responses and backups appropriate to the deployment.

## Proposed stack
React/Vite, Node/Express, PostgreSQL (potentially Supabase), private object storage, RapidOCR, a model API such as Gemini and schema validation with Zod.