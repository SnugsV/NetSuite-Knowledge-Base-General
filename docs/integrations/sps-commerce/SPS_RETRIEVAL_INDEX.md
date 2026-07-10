# SPS Commerce Retrieval Index

## Purpose

This index helps AI assistants choose the right SPS Commerce article set for common EDI questions.

## Current Foundation Articles

| Question Type | Start With | Then Retrieve |
|---|---|---|
| What is EDI? | fundamentals/EDI_OVERVIEW.md | fundamentals/EDI_DOCUMENT_TYPES.md |
| Who is the trading partner? | fundamentals/TRADING_PARTNER_CONCEPTS.md | fundamentals/EDI_OVERVIEW.md |
| What kind of document is this? | fundamentals/EDI_DOCUMENT_TYPES.md | fundamentals/TRADING_PARTNER_CONCEPTS.md |
| Is this a purchase order, ASN, or invoice issue? | fundamentals/EDI_DOCUMENT_TYPES.md | README.md |
| Is this partner-specific? | fundamentals/TRADING_PARTNER_CONCEPTS.md | README.md |
| Does this need private review? | README.md | fundamentals/TRADING_PARTNER_CONCEPTS.md |

## Current Retrieval Rule

Start with the visible user symptom, classify the EDI document type, identify trading partner context when relevant, then compare the related NetSuite record and visible document evidence.

## Private Review Triggers

Route to internal review when the answer depends on:

- retailer-specific requirements
- private EDI maps
- trading partner setup
- credentials
- custom fields
- saved searches
- workflows
- scripts
- customer examples
- chargeback decisions
- proprietary procedures

## Suggested Next Retrieval Nodes

- lifecycle/DOCUMENT_STATUS_CONCEPTS.md
- lifecycle/PURCHASE_ORDER_LIFECYCLE_OVERVIEW.md
- lifecycle/ACKNOWLEDGMENT_REASONING.md
- lifecycle/ASN_REASONING.md
- lifecycle/INVOICE_RELATIONSHIP_OVERVIEW.md
- troubleshooting/MISSING_DOCUMENT_OVERVIEW.md
- troubleshooting/REJECTED_DOCUMENT_OVERVIEW.md

## Public-Safe Note

This index is public-safe and conceptual. It does not document retailer-specific maps, account setup, screenshots, credentials, pricing, or proprietary operating procedures.
