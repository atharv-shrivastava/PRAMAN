# Feature 05: Cross-Document Intelligence

## Purpose
Compare related claims across the documents submitted for the same application and explain where they differ.

## Examples
- Different institution-name strings across an application and certificate.
- Different certificate or reference numbers.
- Conflicting issue or expiry dates.
- Declared intake or capacity not matching an available authorized record.
- One file references an organization or address not found in related evidence.
- Duplicate or reused files appear in different document slots.

## Method
First normalize data with deterministic logic (date parsing, whitespace, case and punctuation handling). Apply exact comparisons where appropriate. AI or semantic matching may identify potential aliases or related statements when the meaning is not identical, but the result should be a candidate relationship requiring confirmation.

## Finding structure
Store both compared values, source document and page for each, comparison method, applicable rule and review status. The interface should show the conflicting excerpts side by side.

## Workflow
Findings enter the review queue; an officer can confirm the inconsistency, mark the difference acceptable with a reason, request evidence or close a false positive.

## Safeguard
Different text does not necessarily mean different entities or fraud. Legal names, aliases, abbreviations and legitimate changes need contextual handling. Do not auto-reject applications based on semantic similarity alone.