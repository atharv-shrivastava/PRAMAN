# Demonstration Scenarios

Use fictional institutions and synthetic documents unless real data is explicitly authorized and anonymized.

## Scenario 1 — Clean submission
Upload required supported documents. Show successful extraction, all configured checks passing and source evidence attached to extracted fields.

## Scenario 2 — Missing mandatory field
Upload a document with a missing reference number. Show the extracted null value, rule code, source page and a finding requiring completion/manual review.

## Scenario 3 — Expired document
Use a synthetic certificate whose expiry date is earlier than the evaluation date. Show the deterministic rule result and date evidence.

## Scenario 4 — Cross-document conflict
Submit two documents with different institution-name strings or certificate references. Show both excerpts and explain why the conflict needs review without declaring fraud.

## Scenario 5 — Historical drift
Compare an earlier application with a current application containing a changed value. Show before/after values, linked documents and the affected checks.

## Scenario 6 — Verification mismatch
Use a mock connector that deliberately returns a differing reference date. Make the UI clearly mark the result SIMULATED and show the fields compared.

## Scenario 7 — Officer correction loop
The officer requests clarification; the institution uploads a new version; PRAMAN re-extracts and re-runs affected checks while preserving the original file and audit history.

## Demo message
The core demonstration is not a claim that PRAMAN can detect every forgery. It is proof that the system connects evidence, reproducible rules, source-check outcomes and officer review into a traceable workflow.