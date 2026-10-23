# Feature 03: OCR, Classification and Structured Extraction

## Purpose
Turn unstructured uploaded documents into structured claims while retaining evidence for every important field.

## Pipeline
1. Inspect whether a PDF contains a text layer; extract it directly when reliable.
2. Render scanned pages and perform OCR.
3. Classify the document into a supported category.
4. Extract the fields required for that category using a schema-constrained model response.
5. Validate the output schema and normalize dates, identifiers and whitespace.
6. Store each field with document ID, page number, supporting text or bounding box where available, method and confidence.
7. Route unreadable, conflicting or low-confidence fields to manual review.

## AI use
OCR performs text recognition. A language model can classify the document and map variable layouts/labels to known fields. It must not invent absent values. Missing values should be null with an explanation. Confidence scores should only be displayed if produced and calibrated by the chosen component; a model's self-reported confidence is not automatically a calibrated probability.

## Outputs
Document type, extracted fields, field-level evidence, processing status, and uncertainty/error indicators.

## Testing
Evaluate field-level precision/recall or exact-match accuracy on labelled test documents, separated by document type and scan quality. Include rotated, low-resolution, multi-page and partially obscured test cases.

## Safeguard
Extracted content is a claim from a submitted document, not a verified fact. Preserve source pages so reviewers can inspect the original.