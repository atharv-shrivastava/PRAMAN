# Feature 08: Authorized Source Verification

## Purpose
Verify selected claims against issuing authorities or other official sources when an authorized and technically supported method exists.

## Connector strategy
Use a common adapter interface so each connector declares supported document types, fields, authentication method, consent/authorization requirements, request limits and result semantics. Candidate sources may include authorized AICTE records, DigiLocker/NAD for supported academic awards, digital-signature validation, MCA/GST services or state registration systems where appropriate. Availability must be confirmed for each integration.

## Workflow
1. Classify the claim and select a supported connector.
2. Verify the user/system has permission to request the check.
3. Send only permitted fields; record a request reference and timestamp.
4. Normalize the response and compare fields with the submitted evidence.
5. Store source, method, result and compared values.
6. If unsupported, inconclusive or unavailable, route to manual review.

## Normalized outcomes
Verified, mismatch detected, not found, verification pending, source unavailable, manual review required, and simulated.

## Prototype strategy
A mock connector may be used for demonstrations, with synthetic records and a visible SIMULATED label. It must never be presented as a real government response.

## Safeguard
A public search page does not imply API availability or automation permission. An unavailable source or missing search result does not by itself prove a document false.