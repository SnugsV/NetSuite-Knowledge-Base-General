---
title: Lot-Tracked Inventory
module: Inventory
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Lot-Tracked Inventory

## Quick Summary

Lot tracking assigns a batch number to a group of identical items, enabling traceability throughout the supply chain — from receipt through fulfillment. Lot numbers track expiration dates, enable recalls, and support quality containment.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Business Question

"If a supplier recalls a batch of raw materials, can I identify every customer who received products made from that batch?"

## Overview

Lot tracking answers the question: "Where did this specific batch come from, and where did it go?" Each time items are received, they are assigned a lot number. As they move through inventory — transfers, adjustments, manufacturing, fulfillment — the lot number follows them. This creates a complete traceability chain.

```
Supplier → Lot ABC-123 → Receipt → Fulfillment → Customer
                                ↓
                           Build Order → Assembly lot DEF-456 → Customer
```

## When to Use Lot Tracking

| Industry | Reason |
|---|---|
| **Food and beverage** | Expiration date management, recall capability |
| **Pharmaceuticals** | Regulatory traceability requirements |
| **Chemicals** | Batch quality control, lot-specific testing |
| **Automotive** | Warranty tracking, recall management |
| **Electronics** | Component traceability for quality issues |
| **Any regulated industry** | Compliance with FDA, ISO, or other standards |

## When Not to Use Lot Tracking

- **Commodity items with no expiration**: Nuts and bolts do not need lot tracking
- **Items with very long shelf lives**: If expiration is not relevant, the cost of lot tracking may exceed the benefit
- **High-volume, low-value items**: The operational overhead of scanning lot numbers on every transaction may outweigh the value of traceability
- **Organizations without quality processes**: Lot tracking without a quality program generates data with no action

## Trade-Offs

| Gained | Complexity Introduced |
|---|---|
| Complete forward and backward traceability | Every receipt, transfer, and fulfillment must record lot numbers |
| Recall capability — identify affected customers in minutes | Lot master data must be maintained |
| Expiration date management | Expired lots must be quarantined and disposed |
| Quality isolation — hold specific lots for testing | Inventory may be blocked from sale while waiting for quality results |

## Lot Numbering Strategies

| Strategy | Example | Best For |
|---|---|---|
| **Supplier Lot Number** | SUP-12345 | Direct pass-through, no internal lot generation |
| **Date-Based** | 20260701 | Simple, human-readable, sorts chronologically |
| **Sequential** | LOT-10042 | Unique, system-generated, no gaps |
| **Hybrid** | 20260701-042 | Date + sequence, combines readability with uniqueness |

## Lot-Enabled Transactions

When lot tracking is enabled, lot information is required on:

| Transaction | Lot Data Captured |
|---|---|
| Item Receipt | Lot number, expiration date, received quantity |
| Inventory Transfer | Lot number and quantity transferred |
| Item Fulfillment | Lot number and quantity shipped — captured at pick |
| Inventory Adjustment | Lot number and quantity adjusted |
| Build Order | Lot numbers of components consumed; lot of assembly produced |

## Expiration Date Management

Lot-tracked items typically have expiration dates. NetSuite can:

- Track expiration date per lot
- Prevent shipping expired lots
- Flag lots approaching expiration
- Automatically quarantine expired lots
- Prioritize picking of soonest-expiring lots (FEFO — First Expiry, First Out)

## Recall and Containment

When a quality issue is identified with a specific lot:

1. **Identify affected lot**: Determine the lot number from supplier records or internal testing
2. **Check inventory**: Use lot number to find all locations with the affected lot
3. **Block inventory**: Quarantine the lot to prevent further shipping
4. **Trace sales**: Identify all customers who received the affected lot
5. **Communicate**: Notify affected customers

Without lot tracking, a recall requires searching through paper records — a process that can take weeks. With lot tracking, it takes minutes.

## Business Example

A food manufacturer implements lot tracking for all raw ingredients.

**Scenario**: A supplier of flour reports that batch F-22071 may contain undeclared allergens.

**Response time without lot tracking**: 3 weeks — manually searching through 6 months of production records to find which products used that flour.

**Response time with lot tracking**: 47 minutes — searching by lot number in NetSuite:

1. Identify lot F-22071: 2 minutes
2. Find all inbound receipts with that lot: 3 minutes
3. Identify all build orders that consumed that lot: 12 minutes
4. Find all finished goods outbound shipments: 18 minutes
5. Identify affected customers and quantities: 12 minutes

## Common Costly Mistakes

- **Tracking lots but not using the data**: Lot tracking without regular lot status reviews is wasted effort
- **Poor lot number quality**: Inconsistent lot numbering (SUP-1234, 07-01-26, LOT42) makes searching difficult
- **No expiration date management**: Without expiration tracking, lot tracking for perishable goods is incomplete
- **Allowing manual lot overrides**: If users can override lot numbers during fulfillment, traceability is broken
- **Not training pickers**: Pickers must scan lot numbers at fulfillment — without training, lots will be picked incorrectly

## Best Practices

- Establish a lot numbering convention and enforce it consistently
- Use FEFO (First Expiry, First Out) picking for date-sensitive items
- Review expired lots monthly and process disposals
- Train warehouse staff on lot scanning at every transaction
- Use barcode scanning to reduce lot entry errors
- Test the recall process annually — run a mock recall to verify traceability
- Integrate lot tracking with quality management for automated lot holds

## Knowledge Check

1. A customer reports a quality issue with a product. You identify the component lot number. What information can you retrieve with lot tracking? (Answer: Which supplier provided it, which production runs used it, which customers received the finished goods, and which inventory locations still hold it.)
2. **Decision**: Your company sells standard office supplies — paper, pens, binders. Should you implement lot tracking? (Answer: No — no regulatory requirement, no expiration concerns, no recall risk.)
3. **Scenario**: Two lots of the same item are in inventory — one expires in 30 days, one in 180 days. Which should be picked first? (Answer: The 30-day lot — FEFO principle.)

## Related Articles

- [Serial Tracking](serial-tracking.md)
- [Bin Management](bin-management.md)
- [Receiving Inventory](../receiving-inventory.md)
- [Cycle Counting](cycle-counting.md)
- [Quality Management](../quality/README.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Lot-Numbered Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Lot Number Setup](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)