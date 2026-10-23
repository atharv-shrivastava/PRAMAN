# Feature 04: Configurable Regulatory Rule Engine

## Purpose
Apply deterministic checks against an approved checklist associated with an application category, academic year and effective regulatory version.

## Rule structure
Each rule should include a stable code, name, description, source reference, applicability conditions, severity, required inputs, logic version, effective period, approval state and expected output.

## Example checks
- Required document or field is missing.
- Date format is invalid or a date is outside a permitted range.
- A document's validity has expired relative to the evaluation date.
- An identifier conflicts with another submitted field.
- The declared value differs from an authorized reference record.
- A category-specific checklist item remains unsatisfied.

## Execution
The service selects the approved rules applicable to an application, checks data availability, runs each rule, records the rule version and stores a structured finding. If a required input cannot be extracted, report it as unavailable/needs review rather than treating it as a pass.

## Administration
Rule changes are versioned, reviewed and approved before activation. Historical validation runs retain the versions used at that time. Regulatory content should be confirmed against current authoritative AICTE materials.

## Boundary
The rule engine can identify a requirement that appears unsatisfied; it should not invent law or automatically make a statutory decision. AI may help draft a rule configuration, but authorized personnel must validate and approve it.