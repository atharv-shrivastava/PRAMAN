# Working with PRAMAN Documentation

The repository is organized so product, feature, architecture and delivery-planning documentation can be reviewed independently.

## Main entry point
Start at README.md for the product summary and feature index. Open docs/README.md for the full documentation map.

## Folder guide
- docs/ — product overview, user roles and end-to-end workflow.
- docs/features/ — one file per major feature.
- docs/architecture/ — system architecture, data model, API outline and verification-source strategy.
- docs/planning/ — roadmap, testing plan and demonstration scenarios.

## Update discipline
Keep project status accurate. Mark a feature implemented only after it runs and has been tested. Identify mock integrations as simulated. For regulatory requirements, record the official source and applicable version after it has been confirmed.

## Git workflow
Use small commits with descriptive messages such as “docs: clarify source verification statuses”. Keep secrets, API keys, real institutional documents and personal data out of Git. Consider a pull request for substantial architecture or regulatory-rule changes.