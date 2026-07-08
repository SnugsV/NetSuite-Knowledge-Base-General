---
title: Shipment Lifecycle
platform: NetSuite / Pacejet
cluster: Shipment Lifecycle
knowledge_type: Reasoning Guide
primary_records:
  - Sales Order
  - Item Fulfillment
  - Customer
  - Item
related_records:
  - Customer Address
  - Transaction Line
  - Package
  - Pallet
  - Carrier
  - Service Level
  - Shipment
  - Label
  - Tracking Number
related_articles:
  - ../README.md
  - ../fundamentals/SHIPPING_OVERVIEW.md
  - ../fundamentals/SHIPMENT_DATA_MODEL.md
  - ../fundamentals/PARCEL_VS_LTL_FREIGHT.md
  - ../fundamentals/CARRIER_SERVICES.md
  - ../fundamentals/ADDRESS_VALIDATION_CONCEPTS.md
keywords:
  - shipment lifecycle
  - Pacejet shipment lifecycle
  - NetSuite fulfillment shipping
  - rate shopping lifecycle
  - shipping label lifecycle
  - tracking lifecycle
  - fulfillment to shipment
difficulty: Consultant
last_verified: 2026-07-08
public_sources:
  - https://www.pacejet.com/
reasoning_prerequisites:
  - Shipment questions should be reviewed by lifecycle stage before diagnosing root cause.
  - Shipping outcomes may depend on fulfillment, address, item, package, carrier, service, rate, label, and tracking context.
  - Public documentation should stay conceptual and avoid company-specific shipping operations, customer examples, and setup details.
employee_questions_answered:
  - What stages does a Pacejet shipment go through?
  - Where should I start when troubleshooting a shipment?
  - Why does the lifecycle stage matter for rate, label, or tracking questions?
  - How should a GPT reason from fulfillment to shipment completion?
---

# Shipment Lifecycle

## Quick Summary

The shipment lifecycle explains how a shipping question moves from order or fulfillment context into packing, rating, carrier/service selection, label or paperwork output, shipment creation, tracking, and review.

The core reasoning rule is:

> Identify the lifecycle stage first. A rating issue, packing issue, label issue, tracking issue, and update issue should not be diagnosed the same way.

## Business Purpose

Employees often ask shipping questions after something unexpected happens:

- no rate returned
- unexpected carrier or service
- label did not print
- paperwork looks wrong
- tracking did not appear
- shipment did not update
- freight quote does not match expectation

A consultant-style assistant should first determine where in the lifecycle the issue occurred. That prevents the assistant from troubleshooting a label problem as if it were a rate problem, or a tracking question as if it were a fulfillment setup question.

## Public Pacejet Perspective

Public Pacejet materials describe ERP-integrated shipping for freight, parcel, and wholesale shipments. Public product content describes quote and rate shopping, predictive packing, packing and scan-packing, labels and paperwork, rules, reports and analytics, address validation, carrier performance, and integrations/APIs.

For AI reasoning, those capabilities form a lifecycle:

1. fulfillment context
2. packing context
3. rate or quote context
4. carrier and service context
5. label or paperwork context
6. shipment and tracking context
7. review and performance context

## NetSuite Perspective

In NetSuite-centered reasoning, the shipment lifecycle commonly begins with a sales order or item fulfillment and then moves into shipping execution.

The assistant should identify the exact record and stage where the question starts. A user asking from a sales order, fulfillment, label, tracking number, or carrier status may be looking at a different part of the lifecycle.

## Lifecycle Overview

```mermaid
flowchart LR
    Order[Sales Order or Order Context]
    Fulfillment[Item Fulfillment]
    Pack[Pack or Scan-Pack]
    Rate[Rate or Quote]
    Carrier[Carrier and Service]
    Label[Label and Paperwork]
    Ship[Shipment Created]
    Track[Tracking or Carrier Status]
    Review[Operational Review]

    Order --> Fulfillment
    Fulfillment --> Pack
    Pack --> Rate
    Rate --> Carrier
    Carrier --> Label
    Label --> Ship
    Ship --> Track
    Track --> Review
```

This is a generic reasoning model. It is not a company-specific shipping workflow.

## Lifecycle Stages

| Stage | What It Means | Common Questions |
|---|---|---|
| Order context | The sales or order data that may lead to fulfillment. | What is being shipped? Where is it going? |
| Fulfillment context | The record or process stage where shipping execution begins. | Which items and quantities are being fulfilled? |
| Packing context | Package, box, pallet, weight, and dimension context. | Is this parcel or freight? What package data is used? |
| Rate or quote context | Carrier/service options and rate results. | Why did no rate return? Why this amount? |
| Carrier/service context | Selected or available provider and service. | Why this carrier? Why not another service? |
| Label/paperwork context | Shipping output for the selected service. | Why did the label not print? What paperwork is needed? |
| Shipment/tracking context | Shipment creation and tracking evidence. | Was the shipment created? Where is the tracking number? |
| Review context | Operational analysis after shipment activity. | What happened, and what evidence supports it? |

## Stage-Based Troubleshooting

| Symptom | Likely Lifecycle Stage | First Review |
|---|---|---|
| No rate returned. | Rate or quote context. | Address, package, shipment mode, carrier, and service. |
| Unexpected carrier selected. | Carrier/service context. | Rate result, service level, address, package, and mode. |
| Label did not print. | Label/paperwork context. | Carrier, service, package, address, and label output. |
| Tracking missing. | Shipment/tracking context. | Whether shipment and label creation completed. |
| Freight quote mismatch. | Packing plus rate context. | Shipment mode, pallet/package data, address, carrier, and service. |
| Address validation failed. | Address plus rate/label context. | Ship-to address used at shipping time. |
| Shipment did not update. | Shipment/tracking/update context. | Shipment output, tracking evidence, and update behavior. |

## Consultant Reasoning Sequence

When answering a shipment lifecycle question, the assistant should:

1. Identify the exact symptom or user question.
2. Identify the record where the issue was observed.
3. Determine the lifecycle stage involved.
4. Retrieve the related fundamentals article for that stage.
5. Compare shipment evidence: fulfillment, address, item lines, package, carrier, service, label, and tracking.
6. Avoid explaining the issue from the final output alone.
7. Escalate when the answer depends on account-specific setup or internal operating rules.

## Common Employee Questions

- Where should I start when troubleshooting a shipment?
- Is this a fulfillment, rate, label, tracking, or update issue?
- Why does the shipment look different from the order?
- Why did the rate appear before the label failed?
- Why did a label print but tracking not appear?
- Why does freight behave differently than parcel in the lifecycle?
- What evidence should I gather before escalating?

## Common Misconceptions

| Misconception | Better Reasoning |
|---|---|
| Every shipping problem starts with the carrier. | Start with the lifecycle stage and shipment evidence. |
| A label issue is the same as a rate issue. | Label output happens after carrier/service context and may have different causes. |
| Tracking should exist as soon as a rate is returned. | Tracking usually depends on shipment or label creation, not rate lookup alone. |
| The order alone explains the shipment. | Fulfillment, package, carrier, service, label, and tracking data may all matter. |
| Public docs should define exact company workflow. | Company-specific workflow belongs in private documentation. |

## Public-Safe Boundaries

This article may explain shipment lifecycle concepts, public-safe record relationships, stage-based troubleshooting, and escalation guidance.

This article must not include company-specific shipping procedures, customer examples, screenshots, account setup, pricing, or proprietary operating rules.

## AI Reasoning Guidance

The assistant should use this article whenever a user asks where to start with a Pacejet shipping question or when a symptom could belong to multiple stages.

The assistant should classify the issue by lifecycle stage before retrieving more specific articles. It should usually retrieve this article with [Shipping Overview](../fundamentals/SHIPPING_OVERVIEW.md), [Shipment Data Model](../fundamentals/SHIPMENT_DATA_MODEL.md), and the specific article for the symptom.

## Related Articles

- [Shipping Overview](../fundamentals/SHIPPING_OVERVIEW.md)
- [Shipment Data Model](../fundamentals/SHIPMENT_DATA_MODEL.md)
- [Parcel vs LTL Freight](../fundamentals/PARCEL_VS_LTL_FREIGHT.md)
- [Carrier Services](../fundamentals/CARRIER_SERVICES.md)
- [Address Validation Concepts](../fundamentals/ADDRESS_VALIDATION_CONCEPTS.md)
- [Pacejet Integration Knowledge Hub](../README.md)

## Public Sources

- https://www.pacejet.com/

## Public-Safety Review

This article is public-safe. It avoids company-specific shipping procedures, customer examples, screenshots, account setup, pricing, and proprietary operating rules.
