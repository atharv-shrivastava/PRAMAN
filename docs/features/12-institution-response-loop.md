# Feature 12: Institution Response and Correction Loop

## Purpose
Allow institutions to respond to deficiencies through a controlled, auditable process.

## Workflow
1. An authorized officer records a finding and selects a permitted response action.
2. Where the prescribed workflow allows, the case is returned or a clarification request is issued with reasons and a due date.
3. The institution sees only the request and evidence it is allowed to access.
4. The institution submits a response and any additional or replacement files.
5. PRAMAN stores each new file as a new version and links it to the request.
6. Relevant extraction and validation checks run again.
7. The officer reviews the response and records resolution or further action.

## Requirements
A response must point to the finding or request it addresses. Preserve the original submission and prior findings. Send notifications and track their delivery status. Support multiple rounds without losing earlier history.

## Failure handling
If extraction fails on the replacement file, mark processing failed or manual review required; do not silently mark the deficiency resolved.

## Safeguards
Institutions may not edit officer-only notes or change official decisions. The correction loop is only for actions permitted by the actual AICTE process; PRAMAN should not invent additional statutory steps.