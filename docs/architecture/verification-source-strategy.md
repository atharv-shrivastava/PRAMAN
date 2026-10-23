# Verification Source Strategy

## Principle
Select a verification method based on the exact claim and document type. There is no single public database or universal API that verifies every certificate, lease, approval letter or institutional claim.

## Candidate source categories
- Authorized AICTE institutional/approval records.
- DigiLocker/NAD for supported academic awards and only where the organization has obtained the required access.
- Digital-signature validation for supported signed documents.
- MCA company data or services for relevant company identity claims.
- GST services for GSTIN-specific claims under the appropriate access conditions.
- State registration/land-record systems for covered property claims where supported.

Each candidate must be checked for current documentation, authorization, user consent where required, technical availability, terms and the exact data fields it can verify.

## Connector contract
A connector should declare supported claim types, authorization requirements, request schema and response schema, and normalize outcomes to: verified, mismatch detected, not found, verification pending, source unavailable, manual review required or simulated.

## Logging
Store the source, method, request/reference ID, timestamp, returned fields and comparison method. Minimize the personal data sent and retained.

## Prototype
Use mock connectors containing fictional records where real access is unavailable. Display a persistent SIMULATED label and keep simulated results separate from actual source checks.

## Interpretation
Verification proves only what the method establishes. A valid digital signature does not prove every claim in the document is true. A missing result or an unavailable source is not proof of forgery.