# User Roles and Access Model

PRAMAN has three user groups. Every permission must be enforced by the backend and storage layer, not merely by hiding controls in the frontend.

## Institution user
Can create and view applications belonging to the user's institution, upload permitted documents, review allowed validation findings, respond to clarification requests and view submission status. Cannot read another institution's restricted files, change officer findings, manage regulatory rules or impersonate officials.

## AICTE officer/reviewer
Can access applications within the officer's assigned scope, view source documents and extracted evidence, inspect findings, record observations, request additional evidence where permitted, mark a finding's review outcome and progress the case through authorized workflow actions. High-impact actions should record the officer, timestamp, reason and relevant case version.

## System/rule administrator
Can manage authorized accounts, roles, institution mappings, document categories, approved checklist versions, configurable rule parameters, notification policies and verification connector settings. Changes to regulatory rules should require controlled approval and produce a version history.

## Access-control requirements
- Use authenticated sessions and least-privilege role-based authorization.
- Scope institution access by a trusted institution identifier derived from authorized account mapping, not an arbitrary client-supplied ID.
- Validate authorization on every API endpoint and file download.
- Use private object storage and short-lived signed download links when applicable.
- Separate administrative configuration from ordinary application review.
- Log sensitive read/write and export actions where required.
- Do not expose secrets, raw documents or personal data in application logs.

## Account lifecycle
Support account approval, role changes, deactivation and session revocation. A deactivated account must lose access promptly. Demo accounts and synthetic data should be clearly marked and must not be confused with official AICTE accounts.