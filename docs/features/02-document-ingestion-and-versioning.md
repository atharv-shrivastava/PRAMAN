# Feature 02: Secure Document Ingestion and Versioning

## Purpose
Accept prescribed evidence safely and preserve a trustworthy chain of versions for review.

## Upload workflow
1. Check authentication, institution scope and upload permission.
2. Enforce supported extensions, MIME inspection, size/page limits and safe filenames.
3. Store the original in private object storage using an opaque object key.
4. Record document category, application, uploader, timestamp, checksum, version and processing status.
5. Queue extraction without blocking the application interface.
6. If a corrected document is submitted, create a new version linked to the previous version.

## Security requirements
Do not execute uploaded files. Apply malware scanning when available, protect against path traversal, store files outside a public web root, use private access policies and issue limited-lived download URLs. Avoid logging document contents.

## Version semantics
Original uploads remain immutable in ordinary workflows. Replacements are new versions with a reason and parent-version reference. The reviewer should be able to compare versions and see which validation runs were based on each version.

## Failure handling
A failed upload must not create a completed document record. Unsupported files, corrupted PDFs, encrypted files and processing-limit violations should receive clear status/error messages and a retry or manual-handling path.

## Outputs
Private stored file, checksum, document version metadata and an extraction job. File storage success must not be confused with document validity or authenticity.