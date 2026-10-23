# Feature 13: Regulatory Rule and Checklist Change Management

## Purpose
Keep validation requirements aligned with applicable AICTE regulations, the Approval Process Handbook and authorized administrative instructions.

## Rule lifecycle
Draft → review → authorized approval → effective date → active use → superseded/retired. Rejected or draft changes must not affect live application checks.

## Versioned fields
Rule identifier, text/description, source citation, applicability criteria, required evidence, logic/configuration version, effective period, author, reviewer, approval status and change rationale.

## Change impact
When a new approved rule version is activated, PRAMAN can identify open applications that may be affected and present a preview of the checks requiring review. Revalidation must use the correct effective version and preserve past run results.

## AI assistance
A model may summarize source text or propose a structured draft rule, but an authorized domain expert must verify the source, interpretation and configuration before activation.

## Safeguards
Do not rely on unverified rule summaries as legal authority. Keep the original source and version, record approval, and ensure a proposed configuration cannot silently change an in-progress regulatory decision.