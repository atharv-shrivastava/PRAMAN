# Feature 17: AI Design and Boundaries

## Where AI is used
- Classification of supported document types.
- Structuring OCR/PDF text into defined fields.
- Interpreting variable labels or layouts to identify candidate comparable claims.
- Suggesting relationships among current and historical evidence.
- Drafting plain-language explanations based on stored findings.
- Optional computer-vision checks for specific, evaluated visual anomalies.

## Where deterministic code should be used
Expiry dates, required fields, exact identifiers, schema validation, source-response comparisons, access permissions, notification timing, workflow state transitions and audit recording.

## Structured output
Models should return schema-constrained JSON. Validate every response; reject malformed outputs and mark unsupported values as missing or uncertain. Store the relevant document/page and evidence excerpt for extracted fields.

## Reliability controls
Use deterministic tests, labelled evaluation data, prompts with bounded scope, retry/error handling and review thresholds. Avoid calling a model repeatedly if a deterministic check resolves the condition.

## Human oversight
AI can flag an anomaly or recommend next steps, but must not independently declare forgery, wrongdoing or statutory non-compliance. The authorized official reviews underlying documents and applicable rules.

## Transparency
Show whether a result came from OCR, a model, a deterministic rule, an external source or a simulated connector. Record model/provider and version where appropriate. Never present a mock result as an official verification.