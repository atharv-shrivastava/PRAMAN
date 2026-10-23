# Feature 10: Infrastructure Evidence Assistance

## Purpose
Help reviewers identify missing, inconsistent or insufficiently supported infrastructure-related evidence in an application.

## Inputs
Prescribed checklists, submitted certificates, photographs, videos, floor plans and institution declarations where relevant to the application category.

## Capabilities
- Check whether required evidence items were submitted.
- Extract available names, dates, reference numbers and declared measurements.
- Compare declarations across associated documents.
- Identify unreadable or low-quality images that need resubmission.
- Where technically justified, flag visible differences between current and prior evidence.
- Recommend additional evidence or physical inspection where the authorized workflow requires it.

## Computer-vision boundary
Image analysis may flag visible indicators but cannot reliably establish every building safety, area, ownership or infrastructure requirement from photographs alone. Do not treat a model output as proof that infrastructure exists or is compliant.

## Workflow
Evidence is indexed by application and page/image. Checks produce traceable advisory findings. Officers inspect the originals and decide whether further evidence or an inspection is required.

## MVP
Start with documentary completeness and cross-record checks. Add image-based review only after selecting testable use cases and measuring performance on representative images.