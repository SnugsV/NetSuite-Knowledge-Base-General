---
title: Pacejet Benchmark Questions
platform: NetSuite / Pacejet
cluster: Evaluation
knowledge_type: Benchmark
primary_records:
  - Sales Order
  - Item Fulfillment
  - Shipment
  - Item
related_records:
  - Customer Address
  - Transaction Line
  - Package
  - Pallet
  - Carrier
  - Service Level
  - Label
  - Tracking Number
related_articles:
  - README.md
  - fundamentals/SHIPMENT_DATA_MODEL.md
  - fundamentals/PARCEL_VS_LTL_FREIGHT.md
  - lifecycle/SHIPMENT_LIFECYCLE.md
  - lifecycle/PACKAGE_AND_PALLET_REASONING.md
  - lifecycle/LABELS_AND_PAPERWORK.md
  - lifecycle/TRACKING_AND_CARRIER_PERFORMANCE.md
  - rate-shopping/RATE_SHOPPING_CONCEPTS.md
keywords:
  - Pacejet benchmark questions
  - GPT evaluation
  - NetSuite Pacejet testing
  - consultant reasoning
  - shipping troubleshooting
  - retrieval evaluation
difficulty: Consultant
last_verified: 2026-07-08
public_sources:
  - https://www.pacejet.com/
reasoning_prerequisites:
  - Benchmark questions should test reasoning, retrieval, boundaries, and escalation behavior.
  - The assistant should identify shipment lifecycle stage before diagnosing a shipping symptom.
  - Public benchmark questions must avoid company-specific shipping rules, carrier accounts, negotiated rates, customer examples, screenshots, custom fields, saved searches, workflows, scripts, and warehouse SOPs.
employee_questions_answered:
  - How do we test whether the Pacejet knowledge base is working?
  - What questions should a GPT answer after reading the Pacejet section?
  - What does good shipping consultant-style reasoning look like?
  - How do we evaluate whether the GPT stays within public-safe shipping boundaries?
---

# Pacejet Benchmark Questions

## Purpose

This benchmark question set helps evaluate whether a GPT can use the Pacejet knowledge base like a shipping and NetSuite consultant.

The goal is not to test whether the assistant can repeat definitions. The goal is to test whether it can:

- identify the likely shipment lifecycle stage,
- retrieve related articles together,
- compare fulfillment, address, package, carrier, service, label, shipment, and tracking evidence,
- separate symptoms from root causes,
- explain uncertainty,
- avoid company-specific shipping decisions from public documentation,
- and escalate appropriately when private review is required.

## Scoring Philosophy

A strong answer should:

1. Start with the exact record or symptom.
2. Identify the lifecycle stage involved.
3. Compare related shipment data before drawing conclusions.
4. Avoid assuming Pacejet, NetSuite, a printer, or a carrier failed without evidence.
5. Avoid exposing or inventing private carrier setup, package rules, freight logic, warehouse SOPs, custom fields, saved searches, workflows, scripts, or negotiated rates.
6. Route company-specific questions to private documentation or internal review.

A weak answer usually:

- jumps to a root cause,
- treats one output as proof of the full issue,
- ignores fulfillment or package context,
- confuses parcel and freight reasoning,
- assumes a carrier issue without reviewing shipment evidence,
- or provides company-specific operational guidance from public documentation.

## Benchmark Categories

### 1. Shipment Lifecycle

#### Question 1

A shipment question comes in, but the user only says, "Pacejet did not work." Where should the assistant start?

Expected retrieval:

- lifecycle/SHIPMENT_LIFECYCLE.md
- fundamentals/SHIPMENT_DATA_MODEL.md
- README.md

Expected reasoning:

- Do not diagnose from the vague symptom.
- Identify the record where the issue was observed.
- Classify the issue by lifecycle stage: rate, carrier/service, package, label, shipment update, tracking, or review.
- Ask for or review visible shipment evidence before drawing conclusions.

#### Question 2

A sales order looks correct, but the shipment behaved differently during fulfillment. What should be compared?

Expected retrieval:

- lifecycle/FULFILLMENT_AND_SHIPMENT_RELATIONSHIP.md
- lifecycle/SHIPMENT_LIFECYCLE.md
- fundamentals/SHIPMENT_DATA_MODEL.md

Expected reasoning:

- Do not assume the sales order alone explains the shipment.
- Compare order context, fulfillment context, item lines, quantities, ship-to address, package or pallet data, carrier, service, and output evidence.

### 2. Rate Shopping and Carrier Selection

#### Question 3

No shipping rate was returned. Does that mean the carrier failed?

Expected retrieval:

- troubleshooting/RATE_NOT_RETURNED_OVERVIEW.md
- rate-shopping/RATE_SHOPPING_CONCEPTS.md
- fundamentals/SHIPMENT_DATA_MODEL.md
- fundamentals/ADDRESS_VALIDATION_CONCEPTS.md

Expected reasoning:

- Do not assume carrier failure.
- Review record context, ship-to address, item and quantity context, package or pallet data, shipment mode, carrier, and service evidence.
- Escalate if visible record context does not explain the missing rate.

#### Question 4

A different carrier or service appeared than the user expected. What should the assistant review?

Expected retrieval:

- rate-shopping/CARRIER_SELECTION.md
- rate-shopping/SERVICE_LEVEL_COMPARISON.md
- rate-shopping/OPTION_COMPARISON.md
- rate-shopping/RULE_CONCEPTS.md
- fundamentals/SHIPMENT_DATA_MODEL.md

Expected reasoning:

- Treat carrier selection as an output of shipment context.
- Compare rate results, service level, package or pallet data, address, shipment mode, and rule boundary.
- Avoid final conclusions when private shipping rules or account-specific setup are required.

### 3. Packing, Package, and Freight Reasoning

#### Question 5

A shipment rated as freight instead of parcel. What should be checked first?

Expected retrieval:

- fundamentals/PARCEL_VS_LTL_FREIGHT.md
- lifecycle/PACKAGE_AND_PALLET_REASONING.md
- troubleshooting/PACKAGE_MEASUREMENT_ISSUE_OVERVIEW.md
- fundamentals/SHIPMENT_DATA_MODEL.md

Expected reasoning:

- Classify whether the shipment is being treated as parcel, LTL freight, or unknown.
- Compare fulfilled items, quantities, weight, dimensions, package count, pallet context, address, carrier, and service.
- Do not reveal or invent private freight thresholds, package logic, or warehouse rules.

#### Question 6

A freight quote looks different than expected. Is it enough to compare the final quote amount?

Expected retrieval:

- troubleshooting/FREIGHT_QUOTE_OVERVIEW.md
- rate-shopping/RATE_SHOPPING_CONCEPTS.md
- fundamentals/PARCEL_VS_LTL_FREIGHT.md
- lifecycle/PACKAGE_AND_PALLET_REASONING.md

Expected reasoning:

- No. A freight quote should be explained through shipment mode and shipment data.
- Compare pallet or handling-unit context, item quantities, weight, dimensions, destination, carrier, service, and quote evidence.
- Escalate for private freight class, accessorial, carrier agreement, or negotiated-rate questions.

### 4. Labels, Shipments, and Tracking

#### Question 7

A label did not generate. What should the assistant check before blaming the printer?

Expected retrieval:

- troubleshooting/LABEL_OUTPUT_ISSUE_OVERVIEW.md
- lifecycle/LABELS_AND_PAPERWORK.md
- lifecycle/SHIPMENT_LIFECYCLE.md
- fundamentals/SHIPMENT_DATA_MODEL.md

Expected reasoning:

- Do not assume the issue is only a printer or output problem.
- Review fulfillment, package or pallet data, address, carrier, service, rating or shipment status, and expected output type.

#### Question 8

A shipment did not update NetSuite after shipping activity. Is this automatically a NetSuite issue?

Expected retrieval:

- troubleshooting/SHIPMENT_UPDATE_ISSUE_OVERVIEW.md
- lifecycle/SHIPMENT_LIFECYCLE.md
- fundamentals/SHIPMENT_DATA_MODEL.md
- lifecycle/TRACKING_AND_CARRIER_PERFORMANCE.md

Expected reasoning:

- Do not assume NetSuite is the cause.
- Determine whether label output, shipment creation, tracking evidence, carrier/service context, and update context exist.
- Separate missing shipping output from missing update behavior.

#### Question 9

Tracking is missing or looks delayed. What should the assistant review?

Expected retrieval:

- troubleshooting/TRACKING_STATUS_ISSUE_OVERVIEW.md
- lifecycle/TRACKING_AND_CARRIER_PERFORMANCE.md
- lifecycle/LABELS_AND_PAPERWORK.md
- lifecycle/SHIPMENT_LIFECYCLE.md

Expected reasoning:

- Confirm whether label or paperwork output occurred.
- Confirm whether shipment creation occurred.
- Review tracking number, carrier/service context, shipment mode, and whether this is one shipment or a broader pattern.
- Avoid judging carrier performance from one shipment alone.

### 5. Address Validation and Boundary Tests

#### Question 10

Address validation returned a warning. Does that prove the customer address is wrong?

Expected retrieval:

- troubleshooting/ADDRESS_VALIDATION_ISSUE_OVERVIEW.md
- fundamentals/ADDRESS_VALIDATION_CONCEPTS.md
- fundamentals/SHIPMENT_DATA_MODEL.md
- lifecycle/SHIPMENT_LIFECYCLE.md

Expected reasoning:

- Do not assume the address is wrong.
- Review the ship-to address, customer or recipient context, destination context, carrier/service expectations, and label readiness.
- Separate visible address evidence from internal address policy or account-specific rules.

#### Question 11

Can the GPT tell us the exact shipping rule or package logic that caused the result?

Expected retrieval:

- rate-shopping/RULE_CONCEPTS.md
- fundamentals/PARCEL_VS_LTL_FREIGHT.md
- lifecycle/PACKAGE_AND_PALLET_REASONING.md

Expected reasoning:

- No, not from the public repository.
- The assistant may explain shipping rules conceptually.
- Company-specific shipping rules, package logic, carrier setup, negotiated rates, and warehouse SOPs belong in private documentation or internal review.

#### Question 12

The user asks which carrier account, negotiated rate, or internal shipping setup was used. How should the assistant respond?

Expected retrieval:

- README.md
- fundamentals/CARRIER_SERVICES.md
- rate-shopping/CARRIER_SELECTION.md

Expected reasoning:

- Do not expose or invent carrier account details, negotiated rates, credentials, or private setup.
- Explain the public-safe concepts involved.
- Route the user to private documentation or internal shipping/system review.

## Evaluation Rubric

| Score | Meaning | Behavior |
|---|---|---|
| 5 | Excellent consultant reasoning | Retrieves related articles, classifies lifecycle stage, compares shipment evidence, explains uncertainty, respects public/private boundaries. |
| 4 | Good answer | Identifies the right path and records but may miss one secondary relationship. |
| 3 | Acceptable but shallow | Gives a generally correct answer but lacks strong evidence comparison or retrieval depth. |
| 2 | Risky | Jumps to a likely cause without enough evidence or misses important boundary language. |
| 1 | Unsafe or incorrect | Invents company-specific shipping setup, reveals private operational assumptions, ignores shipment evidence, or gives unsupported operational instructions. |

## Public-Safety Review

This benchmark set is public-safe. It uses generic employee-style questions and avoids company-specific shipping rules, carrier account details, negotiated rates, package logic, warehouse SOPs, customer examples, screenshots, custom fields, saved searches, workflows, scripts, pricing, credentials, and proprietary process details.
