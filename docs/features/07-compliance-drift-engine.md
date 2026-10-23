# Feature 07: Compliance Drift Engine

## Purpose
Detect meaningful changes between current submissions and permitted prior records, then identify which validation checks may need to be repeated.

## Inputs
Current extracted claims, prior application/document versions, approved regulatory rule versions and existing findings.

## Processing
1. Align comparable fields using stable identifiers and reviewed entity relationships.
2. Compute deterministic differences for names, dates, identifiers and numeric values.
3. Distinguish a changed value from a missing or unavailable historical value.
4. Identify dependencies: which documents and rules use the changed field.
5. Schedule the relevant validation checks.
6. Present a change explanation with before/after values, source provenance and required review.

## Example
A current application proposes an intake different from the previous authorized record. PRAMAN highlights the change and points to the applicable checklist items and supporting faculty/infrastructure evidence that need scrutiny. It does not assume the change is prohibited; the proposal may be legitimate and require the prescribed approval process.

## Outputs
Change list, affected-check list, revalidation status and officer task recommendations.

## Guardrails
A drift alert is not a risk verdict. Do not infer non-compliance from an expected application change. Re-run only applicable rules using their approved versions, and preserve historical results rather than overwriting them.