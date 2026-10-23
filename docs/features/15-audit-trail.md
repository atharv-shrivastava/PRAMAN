# Feature 15: Audit Trail

## Purpose
Provide a chronological, reviewable record of significant changes and decisions across the application lifecycle.

## Events to capture
Authentication and access changes; application creation and submission; document upload/version replacement; extraction and validation runs; rule versions used; source-verification requests and results; finding creation/resolution; institution responses; officer decisions; notifications; exports and administrative configuration changes.

## Event fields
Event ID, actor, role, timestamp, action, object type/ID, application ID, outcome, reason, request/correlation ID and relevant version references. Avoid storing raw secrets or unnecessary personal data in event payloads.

## Integrity
Ordinary users must not be able to edit or delete audit entries through the app. Consider restricted database permissions, append-only patterns and periodic integrity checks appropriate to the hosting model. Define a retention policy with authorized stakeholders.

## Review use
An officer should be able to reconstruct what evidence existed, which rules ran and who took each action at a particular point in time.

## Safeguard
The audit trail supports accountability but does not itself prove a source document authentic. Access to audit logs is also role-controlled and sensitive exports should be recorded.