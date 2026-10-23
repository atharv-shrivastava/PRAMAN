# API Outline

These routes are a design proposal, not an implemented contract. Final paths and request schemas should be versioned and documented in code.

## Application endpoints
- POST /api/applications — create a draft for an authorized institution.
- GET /api/applications — list only applications visible to the current user.
- GET /api/applications/:id — retrieve permitted application details and status.
- POST /api/applications/:id/submit — validate submission prerequisites and submit.

## Documents and processing
- POST /api/applications/:id/documents — register/upload a supported document.
- GET /api/documents/:id — fetch permitted metadata.
- POST /api/documents/:id/process — queue extraction where authorized.
- GET /api/documents/:id/versions — view version history.
- GET /api/documents/:id/findings — fetch findings linked to a document.

## Review and verification
- POST /api/applications/:id/validate — run applicable rule checks.
- POST /api/findings/:id/review-actions — record an authorized review outcome.
- POST /api/documents/:id/verify — request a supported source check.
- POST /api/applications/:id/clarification-requests — issue a permitted request for more evidence.

## API requirements
Use authenticated requests, schema validation, consistent error envelopes, pagination, rate limiting, request IDs and authorization checks on every route. Avoid returning raw storage keys or source credentials. Long-running extraction should return a job/status reference rather than blocking the request. Log actions but not sensitive document contents.