---
title: Integration Benchmark Index
platform: NetSuite Ecosystem
cluster: Evaluation
knowledge_type: Benchmark Index
primary_records:
  - Sales Order
  - Invoice
  - Cash Sale
  - Credit Memo
related_records:
  - Customer
  - Customer Address
  - Item
  - Transaction Line
related_articles:
  - avalara/AVALARA_BENCHMARK_QUESTIONS.md
  - avalara/README.md
keywords:
  - benchmark questions
  - GPT evaluation
  - integration evaluation
  - consultant reasoning
  - NetSuite ecosystem testing
  - retrieval evaluation
difficulty: Consultant
last_verified: 2026-07-07
public_sources:
  - https://developer.avalara.com/products/avatax/
  - https://knowledge.avalara.com/
reasoning_prerequisites:
  - Benchmark files should test reasoning quality, retrieval behavior, escalation behavior, and public-safe boundaries.
  - Each integration should eventually have its own benchmark question set.
  - Public benchmark questions must avoid company-specific examples, private configuration, custom fields, saved searches, scripts, workflows, screenshots, customer details, pricing, and proprietary processes.
employee_questions_answered:
  - How do we evaluate whether a GPT is using this repository correctly?
  - Where are the benchmark question sets for each integration?
  - What should future Pacejet, SPS Commerce, Celigo, Shopify, and RF-SMART benchmarks include?
---

# Integration Benchmark Index

## Purpose

This index organizes benchmark question sets for the NetSuite Intelligence Platform.

The goal is to evaluate whether a GPT can reason through NetSuite ecosystem questions like an experienced consultant. Benchmark questions should test retrieval, record comparison, uncertainty handling, public/private boundaries, and escalation behavior.

This file is not a test of memorization. It is a test of reasoning quality.

## Current Benchmark Sets

| Platform | Benchmark File | Status | Purpose |
|---|---|---|---|
| Avalara | [Avalara Benchmark Questions](avalara/AVALARA_BENCHMARK_QUESTIONS.md) | v1 added | Tests exemption, transaction lifecycle, connector troubleshooting, returns, compliance, and escalation reasoning. |
| Pacejet | Planned | Not started | Should test shipping lifecycle, rate shopping, carrier selection, packaging, labels, and shipment troubleshooting. |
| SPS Commerce | Planned | Not started | Should test EDI document lifecycle, purchase orders, ASNs, invoices, retailer workflows, and error resolution. |
| Celigo | Planned | Not started | Should test integration flow reasoning, sync direction, failures, mapping concepts, and operational escalation. |
| Shopify | Planned | Not started | Should test ecommerce order lifecycle, payments, fulfillment, tax, refunds, and NetSuite relationship reasoning. |
| RF-SMART | Planned | Not started | Should test warehouse scanning, inventory movement, fulfillment, receiving, and operational record relationships. |

## Benchmark Design Principles

A strong benchmark question should require the assistant to:

1. Identify the correct integration cluster.
2. Retrieve related articles together.
3. Compare records before drawing conclusions.
4. Separate symptoms from root causes.
5. Explain what evidence is needed.
6. Avoid final conclusions when private configuration, policy, legal, financial, or operational review is required.
7. Stay within public-safe boundaries.

## What Benchmarks Should Test

| Capability | What It Tests | Example Pattern |
|---|---|---|
| Retrieval quality | Whether the GPT pulls the right article set. | Tax refund question retrieves Returns plus Credit Memos and Transaction Lifecycle. |
| Record comparison | Whether the GPT compares related records. | Sales order versus invoice, invoice versus credit memo, order versus shipment. |
| Symptom triage | Whether the GPT classifies the issue before diagnosing. | No tax, unexpected tax, address issue, label issue, ASN error. |
| Boundary control | Whether the GPT avoids private or unsafe conclusions. | Nexus decisions, filing states, internal mappings, customer-specific setup. |
| Escalation behavior | Whether the GPT knows when internal review is needed. | Private connector settings, legal/tax decisions, mapping issues, account-specific workflows. |
| Consultant reasoning | Whether the answer explains why, not just what. | Uses transaction context, timing, and evidence rather than guesses. |

## Standard Benchmark Structure

Each platform benchmark should use this structure:

```markdown
# Platform Benchmark Questions

## Purpose

## Scoring Philosophy

## Benchmark Categories

### 1. Core Concepts

#### Question 1

Expected retrieval:

Expected reasoning:

### 2. Transaction or Process Lifecycle

### 3. Troubleshooting

### 4. Boundary and Escalation Tests

## Evaluation Rubric

## Public-Safety Review
```

## Recommended Evaluation Rubric

| Score | Meaning | Behavior |
|---|---|---|
| 5 | Excellent consultant reasoning | Retrieves related articles, compares records, explains uncertainty, respects public/private boundaries, and escalates appropriately. |
| 4 | Good answer | Identifies the right path and records but may miss one secondary relationship. |
| 3 | Acceptable but shallow | Gives a generally correct answer but lacks strong record comparison, retrieval depth, or boundary language. |
| 2 | Risky | Jumps to a likely cause without enough evidence or misses important escalation guidance. |
| 1 | Unsafe or incorrect | Gives legal, tax, financial, compliance, or operational advice without support; invents company-specific facts; or ignores record evidence. |

## Platform-Specific Benchmark Guidance

### Avalara

Avalara benchmarks should test:

- exemption reasoning
- transaction lifecycle comparison
- connector troubleshooting
- returns and refund tax reasoning
- compliance boundaries
- audit and nexus escalation

Use: [Avalara Benchmark Questions](avalara/AVALARA_BENCHMARK_QUESTIONS.md)

### Pacejet

Future Pacejet benchmarks should test:

- shipment lifecycle reasoning
- carrier selection and rate shopping concepts
- package and shipment record relationships
- label generation troubleshooting
- freight versus parcel reasoning
- fulfillment and shipping-stage comparisons
- escalation for private carrier setup or account-specific shipping rules

### SPS Commerce

Future SPS Commerce benchmarks should test:

- EDI document lifecycle reasoning
- purchase order, acknowledgment, ASN, and invoice relationships
- retailer compliance concepts
- mapping and validation error triage
- document status interpretation
- escalation for private maps, retailer-specific rules, and customer-specific workflows

### Celigo

Future Celigo benchmarks should test:

- integration flow direction
- source versus destination record reasoning
- sync failures and retries
- mapping concepts
- duplicate or missing record investigation
- escalation for private flow configuration and credentials

### Shopify

Future Shopify benchmarks should test:

- ecommerce order lifecycle
- payment and fulfillment status reasoning
- refunds and returns
- tax and discount context
- customer and address data flow
- NetSuite transaction relationship reasoning

### RF-SMART

Future RF-SMART benchmarks should test:

- warehouse scan lifecycle
- inventory movement reasoning
- receiving, picking, packing, and fulfillment relationships
- item, bin, lot, serial, and location context
- escalation for private warehouse configuration and operational SOPs

## Public-Safety Review

This benchmark index is public-safe. It does not include company-specific workflows, customer examples, screenshots, custom fields, saved searches, scripts, credentials, mappings, pricing, tax decisions, filing positions, internal prompts, or proprietary operational details.
