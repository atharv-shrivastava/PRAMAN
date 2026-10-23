# Feature 09: Document Integrity and Anomaly Detection

## Purpose
Identify potential document-integrity concerns that warrant further checking, while avoiding unsupported claims that a document is forged.

## Techniques
- Cryptographic hash for exact duplicate file detection.
- Perceptual hashes or image similarity for visually similar files.
- PDF metadata review for unusual or conflicting metadata.
- Digital-signature and certificate-chain validation where relevant.
- Version comparison to highlight changed regions.
- Cross-record checks for mismatched identifiers, dates and issuing details.
- Computer vision research for alterations or inconsistent page regions when data and evaluation support it.

## Processing flow
Generate machine-readable indicators, link each indicator to the file/version and evidence, group related indicators and route them to a reviewer. The UI should distinguish a technical check result from an allegation.

## Example
Two submitted certificates are nearly identical but contain different reference numbers. PRAMAN highlights both versions and the changed region. A reviewer decides whether reuse is legitimate or requires verification.

## Limits
Metadata can be edited or absent; compression may change visual appearance; documents can legitimately be reused; and scans can look different. No single indicator proves forgery.

## Evaluation
Use labelled positive and negative test samples, report false-positive rates, and avoid high-stakes automation unless performance is independently established. All adverse regulatory action remains subject to authorized human verification.