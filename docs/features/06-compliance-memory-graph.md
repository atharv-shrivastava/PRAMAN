# Feature 06: Compliance Memory Graph

## Purpose
Represent the relationships between an institution, its application cycles, documents, extracted claims, rules, verification events, findings and officer actions. This is PRAMAN's signature product concept.

## Conceptual nodes
Institution, Application, DocumentVersion, ExtractedClaim, RegulatoryRuleVersion, ValidationRun, Finding, SourceVerification and ReviewAction.

## Conceptual relationships
Institution has applications; applications contain document versions; documents support extracted claims; claims are checked against rule versions; findings compare claims or reference a verification; review actions resolve or comment on findings; new document versions supersede old ones without deleting them.

## How it works
When a new document arrives, PRAMAN links its extracted claims to the current application. Where authorized history exists, the system links matching claims and displays changed values. A reviewer can trace any finding back to source pages, previous values and the rule that caused the check.

## Implementation
For the MVP, implement the graph as relational tables and foreign-key relationships in PostgreSQL. A dedicated graph database is optional only if later workloads justify it.

## Outputs
An institution evidence timeline, relationship explorer, claim provenance and a list of historical records related to an open finding.

## Safeguards
Only use records the user and system are authorized to access. A missing historical record means “not available in the accessible history”, not “never existed”. Preserve provenance and review decisions so an inferred relationship does not silently become an official fact.