# End-to-End Workflow

## 1. Create application
An institution user selects the application category and academic year and creates a draft. PRAMAN selects the approved checklist version applicable to that category and period.

## 2. Upload evidence
The user submits required and optional documents. The backend validates file type, size and processing limits, stores the original privately, creates a document version and records uploader and time.

## 3. Process documents
Text-based PDFs are parsed where possible. Scanned pages are rendered and sent to OCR. A document classifier identifies a supported type and an extraction model produces structured fields with source document and page references. Missing or ambiguous values remain null/uncertain.

## 4. Validate
The deterministic rule engine checks required items, date conditions, field formats, identity consistency and other approved requirements. Each run records its rule version and result.

## 5. Compare evidence
Cross-document logic compares relevant claims across the submitted files. The Compliance Memory Graph links current evidence to prior applications, permitted records, applicable rules and earlier findings.

## 6. Verify sources
Where an approved connector is available and authorized, PRAMAN sends a permitted verification request and compares the response with the submitted claim. Otherwise it records source unavailable, unsupported or manual-review-required. Mock results must be explicitly labelled simulated.

## 7. Generate findings
Each finding includes a reason, source evidence, relevant rule or comparison, status and suggested next action. AI-generated explanations must be grounded in stored findings.

## 8. Officer review
An authorized officer reviews findings and evidence, records observations and determines whether a finding is valid, resolved, not applicable with justification, or requires more information.

## 9. Institution response
Where the applicable workflow permits, a deficiency request is sent to the institution. New or replacement evidence is stored as a new version, not as an overwrite of the original.

## 10. Revalidation and audit
PRAMAN reruns checks affected by changed evidence, records which results changed and preserves a chronological audit history. The application then continues through the prescribed approval process; PRAMAN does not make the statutory decision.