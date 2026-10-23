# PRAMAN: Product Overview

## Purpose
PRAMAN (Platform for Regulatory Assessment, Monitoring, Authentication & Notification) is a proposed AI-assisted decision-support platform for AICTE approval-related applications. It helps institutions submit applications and supporting evidence, and helps authorized officials review completeness, consistency, source-verification outcomes and changes across application cycles.

## Problem
An application may contain multiple documents that repeat the same facts in different formats. Manual scrutiny can make missing fields, expired documents, conflicting identifiers and changes from prior submissions difficult to spot consistently. Public websites are not automatically APIs, and extracted text is not proof of authenticity.

## Users
- **Institution user:** creates applications, submits documents and responds to authorized deficiency requests.
- **AICTE officer/reviewer:** examines evidence, reviews findings and records official observations or actions.
- **System/rule administrator:** manages accounts, document types, approved checklists, rule versions and connector configuration.

## Product principles
1. Every important finding should be traceable to a source document, extracted value and rule or comparison that produced it.
2. Deterministic checks should be implemented as testable rules, not left to an AI prompt.
3. Verification outcomes must distinguish confirmed results from missing records, unavailable sources and simulations.
4. A warning is not proof of forgery or misconduct.
5. Regulatory decisions remain with the competent authority.

## Signature innovation
The **Compliance Memory Graph** links institutions, application cycles, documents, claims, regulatory rules, verification results and review actions. The **Compliance Drift Engine** compares current evidence with permitted historical records, identifies meaningful changes and traces which checks may need to be run again.

## Initial scope
The first prototype should support one application category and three selected document types. Demonstrate upload, extraction, deterministic validation, cross-document comparison, evidence-linked findings, officer review and recorded resolution before adding more document types or live external integrations.

## Proposed stack
React + Vite, Node.js + Express, PostgreSQL, private object storage, OCR such as RapidOCR, a model API for structured extraction, and a deterministic rule engine. A graph database is not required for the first implementation.