# AI Knowledge Metadata Specification

## Purpose

This document defines metadata for consultant-grade knowledge articles in the NetSuite Intelligence Platform.

Traditional documentation metadata helps humans understand where an article belongs. AI knowledge metadata goes further: it helps retrieval systems, knowledge graphs, and Custom GPTs understand what business question an article answers, what records it touches, and how it relates to other knowledge.

Use this specification for product intelligence, integration intelligence, troubleshooting intelligence, and reasoning-oriented articles. Examples include Avalara, SPS Commerce, Pacejet, Shopify, Celigo, RF-SMART, EDI, REST APIs, tax workflows, fulfillment workflows, and cross-system business processes.

## When to Use This Metadata

Use AI knowledge metadata when the article is intended to teach an AI assistant how to reason through a business or system question.

Good fits:

- Product ecosystem articles
- Integration articles
- Troubleshooting guides
- Root cause analysis guides
- Decision trees
- Record relationship articles
- Data flow articles
- Business process articles
- Connector or vendor-specific knowledge clusters

Traditional article metadata is still appropriate for general learning articles such as basic NetSuite navigation, saved search introductions, or beginner ERP education.

## Metadata Block

Every AI knowledge article should begin with this YAML front matter block:

```yaml
---
title:
platform:
cluster:
knowledge_type:
primary_records:
related_records:
related_articles:
keywords:
difficulty:
last_verified:
public_sources:
reasoning_prerequisites:
employee_questions_answered:
---
```

## Field Definitions

### title

The human-readable title of the article.

Use clear, question-friendly wording when possible.

Example:

```yaml
title: Exemption Certificates
```

### platform

The system, product, or ecosystem this article belongs to.

Examples:

```yaml
platform: Avalara
platform: NetSuite / Avalara
platform: SPS Commerce
platform: Pacejet
platform: NetSuite
```

### cluster

The knowledge cluster this article belongs to.

A cluster is a connected group of articles around a business capability or reasoning domain.

Examples:

```yaml
cluster: Exemption Management
cluster: Address Validation
cluster: Transaction Tax Calculation
cluster: EDI Fulfillment
cluster: Shipping Rate Shopping
```

### knowledge_type

The kind of knowledge the article provides.

Recommended values:

```yaml
knowledge_type: Foundation
knowledge_type: NetSuite Integration
knowledge_type: Record Relationships
knowledge_type: Data Flow
knowledge_type: Troubleshooting
knowledge_type: Decision Guide
knowledge_type: Reference
knowledge_type: Reasoning Model
knowledge_type: FAQ
```

### primary_records

The main NetSuite records, vendor records, or business objects involved.

Use a YAML list.

Example:

```yaml
primary_records:
  - Customer
  - Sales Order
  - Invoice
  - Exemption Certificate
```

### related_records

Supporting records or objects that may influence the topic but are not the central focus.

Example:

```yaml
related_records:
  - Customer Address
  - Item
  - Tax Code
  - Nexus
```

### related_articles

Internal article links that help the GPT connect this topic to neighboring concepts.

Use relative paths when known.

Example:

```yaml
related_articles:
  - ../address/ADDRESS_VALIDATION.md
  - ../address/WHICH_ADDRESS_DOES_AVALARA_USE.md
  - CUSTOMER_EXEMPTIONS.md
```

### keywords

Search and retrieval terms that employees, admins, or AI systems might use.

Include synonyms, common phrases, and likely employee wording.

Example:

```yaml
keywords:
  - tax exempt
  - exemption certificate
  - resale certificate
  - customer exempt
  - AvaTax exemption
  - why did tax calculate
```

### difficulty

The expected reasoning level.

Recommended values:

```yaml
difficulty: Beginner
difficulty: Intermediate
difficulty: Advanced
difficulty: Consultant
```

Use `Consultant` when the article explains diagnosis, tradeoffs, record relationships, or cross-system behavior.

### last_verified

The date the public sources and general accuracy were last reviewed.

Use ISO format:

```yaml
last_verified: 2026-07-07
```

If the article is a draft and has not yet been source-verified, use:

```yaml
last_verified:
```

### public_sources

Public, non-proprietary sources used to build or verify the article.

Use source names or URLs. Do not include private Holland Bar Stool sources in the public repository.

Example:

```yaml
public_sources:
  - Avalara Knowledge Center
  - Avalara AvaTax for NetSuite public documentation
  - Oracle NetSuite Help Center
```

### reasoning_prerequisites

Concepts the GPT should understand before using this article for reasoning.

These are not user prerequisites; they are model-reasoning prerequisites.

Example:

```yaml
reasoning_prerequisites:
  - Customer records can contain tax-related attributes
  - Transaction tax calculation depends on addresses, items, nexus, and exemption status
  - Vendor tax engines may evaluate data differently than NetSuite native tax logic
```

### employee_questions_answered

Real-world employee questions this article should help answer.

Write these in natural language. This is one of the most important fields for RAG retrieval.

Example:

```yaml
employee_questions_answered:
  - Why is this customer tax exempt?
  - Why did Avalara still calculate tax for an exempt customer?
  - Where is the exemption certificate stored?
  - What should I check before telling a customer they are tax exempt?
```

## Recommended Article Structure

AI knowledge articles should usually follow this structure:

```markdown
# Article Title

## Quick Summary
## Business Purpose
## Core Concepts
## How NetSuite Thinks About This
## How the External Platform Thinks About This
## Record Relationships
## Data Flow
## Decision Logic
## Common Employee Questions
## Troubleshooting Notes
## Best Practices
## Related Articles
## Public Sources
```

Not every article needs every section. The point is to create reusable consultant memory, not rigid templates.

## Metadata Quality Rules

1. Use original wording.
2. Keep the metadata public-safe.
3. Do not include Holland Bar Stool custom fields, saved searches, workflows, scripts, pricing, manufacturing logic, screenshots, or customer-specific data.
4. Prefer real employee questions over abstract keyword stuffing.
5. Keep `related_articles` current as the cluster grows.
6. Use `last_verified` honestly.
7. Separate public source names from private implementation knowledge.
8. Use `Consultant` difficulty only when the article teaches diagnosis or reasoning.

## RAG and Knowledge Graph Guidance

Good metadata should help answer three questions:

1. Should this article be retrieved?
2. What other articles should be retrieved with it?
3. What reasoning path should the assistant follow after retrieving it?

For best retrieval:

- Put likely employee wording in `employee_questions_answered`.
- Put system terms and synonyms in `keywords`.
- Put record objects in `primary_records` and `related_records`.
- Put conceptual dependencies in `reasoning_prerequisites`.
- Use clusters consistently across related articles.

## Example: Avalara Exemption Article

```yaml
---
title: Exemption Certificates
platform: NetSuite / Avalara
cluster: Exemption Management
knowledge_type: Foundation
primary_records:
  - Customer
  - Exemption Certificate
  - Sales Order
  - Invoice
related_records:
  - Customer Address
  - Item
  - Tax Code
  - Nexus
related_articles:
  - CUSTOMER_EXEMPTIONS.md
  - ITEM_TAXABILITY.md
  - WHY_IS_CUSTOMER_TAX_EXEMPT.md
  - EXEMPTION_TROUBLESHOOTING.md
keywords:
  - exemption certificate
  - tax exempt customer
  - resale certificate
  - Avalara exemption
  - AvaTax exemption
  - customer tax exempt
  - why did tax calculate
difficulty: Consultant
last_verified: 2026-07-07
public_sources:
  - Avalara Knowledge Center
  - Avalara AvaTax public documentation
  - Oracle NetSuite Help Center
reasoning_prerequisites:
  - Tax calculation depends on customer, address, item, transaction, nexus, and exemption data
  - Exemption status may require valid documentation, not just a customer-level flag
  - NetSuite and external tax engines may use different records or sync timing
employee_questions_answered:
  - Why is this customer tax exempt?
  - Why did Avalara calculate tax even though the customer says they are exempt?
  - What record should I check to confirm an exemption certificate?
  - What information does the GPT need before explaining a tax exemption issue?
---
```

## Relationship to Existing Documentation Standards

This specification does not replace the existing documentation front matter standard.

Use the existing documentation standard for general NetSuite learning articles.

Use this AI knowledge metadata standard for intelligence articles that need stronger retrieval, reasoning, and relationship modeling.

Future templates may combine both standards when appropriate.
