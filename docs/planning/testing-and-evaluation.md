# Testing and Evaluation Plan

## Test data
Create synthetic or authorized anonymized samples representing valid, expired, incomplete, inconsistent, duplicate, low-quality and unsupported documents. Keep ground-truth labels separate from the system under test.

## Functional tests
- Application creation and institution access controls.
- File upload limits, invalid types, corrupt/encrypted PDF handling and retry behavior.
- Extraction schema validation and null handling for missing fields.
- Rule applicability, effective dates and versioning.
- Cross-document conflict detection and reviewed alias handling.
- Source-verification outcomes including timeout, mismatch, not found and simulated responses.
- Version replacement and revalidation.
- Officer action permissions and audit event generation.

## Metrics
- Field-level extraction exact-match or precision/recall by field/document type.
- Rule-validation accuracy on labelled cases.
- False-positive rate for valid documents.
- Evidence traceability: proportion of findings linked to correct source page/value.
- Processing latency and failure rate.
- Source-verification success and unavailable-source rate, separated by connector.
- Median officer review time on matched sample tasks.

## Method
Report sample size, document types, scan conditions, thresholds and limitations. Keep real API checks separate from mocked checks. Measure end-to-end performance, not just model performance.

## Acceptance goals
Set numerical thresholds only after collecting a baseline. Do not claim an accuracy number that has not been measured. Any high-impact anomaly detector needs evaluation of false positives and human-review behavior before operational use.