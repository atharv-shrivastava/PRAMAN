# Feature 01: Institution Profile and Application Management

## Purpose
Maintain a persistent, institution-scoped profile and connect it to application submissions across academic years. The profile gives PRAMAN a reliable identity anchor for evidence comparison and historical analysis.

## Data maintained
Where authorized and available: AICTE Permanent Institute ID, institution name and aliases, address, region, approved programmes/intake records, application history, submitted document versions, known compliance requirements and prior officer observations.

## Workflow
1. A user is authenticated and mapped to an institution through trusted account configuration.
2. The user creates an application and selects its category and academic year.
3. PRAMAN chooses the applicable approved checklist and rule version.
4. The user saves a draft, uploads evidence and submits the application.
5. The system stores status transitions and links all documents/findings to the application and institution.

## Validation
Prevent duplicate application identifiers; validate required metadata; reject unauthorized cross-institution access; and preserve application versions. Institution name aliases must be based on approved or reviewed evidence rather than automatically assumed from fuzzy similarity.

## Outputs
Institution profile, application list, application details, current checklist, linked documents and history.

## Safeguards
Historical or approval data must come from authorized records. A prototype may use synthetic records, clearly labelled. The institution portal must not expose another institution's applications or officer-only notes.