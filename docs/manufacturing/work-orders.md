---
title: Work Orders
module: Manufacturing
difficulty: Intermediate
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Work Orders

## Quick Summary

A work order authorizes the production of a specific quantity of an assembly item. It pulls components from inventory, tracks production progress, captures labor and overhead costs, and results in finished goods being added to inventory.

## Difficulty

Intermediate

## Estimated Time

20 minutes

## Business Question

"How do I authorize and track the production of a specific quantity of a product?"

## Overview

The work order is the central document in manufacturing. It connects the BOM (what goes into the product) with actual production quantities, dates, and costs.

## Work Order Lifecycle

```
Planned → Released → In Progress → Completed → Closed
```

| Status | Meaning |
|---|---|
| **Planned** | Work order created but not yet released to production |
| **Released** | Released to the floor — components can be issued |
| **In Progress** | Components issued, production actively running |
| **Completed** | All output quantities built and received |
| **Closed** | Final costs applied, work order no longer editable |

## Creating a Work Order

```
Transactions > Manufacturing > Work Orders > New
```

Key fields:

| Field | Purpose |
|---|---|
| **Assembly Item** | What is being built |
| **Quantity** | How many units |
| **BOM Revision** | Which BOM to use |
| **Location** | Where production occurs |
| **Start Date** | When production begins |
| **Due Date** | When production should complete |

## Work Order Components

When a work order is created from a BOM:

- Component requirements are calculated (BOM quantity × work order quantity)
- Required quantities are checked against available stock
- Shortages are flagged for purchasing

## Build Completion

When production is complete, the work order is built:

```
Transactions > Manufacturing > Work Orders > Build
```

Building a work order:

- Consumes the specified component quantities
- Adds the assembly output to inventory
- Records the production cost
- Updates WIP accounts

## Common Customer Questions

**Q**: Why won't my work order build? **Records to Inspect**: Component inventory availability, BOM revision status, assembly item setup, work order status.

**Q**: Why did the build consume more components than expected? **Common Causes**: Backflushing configuration, BOM quantity errors, manual issue adjustments.

## Related Articles

- [Bills of Materials](bills-of-materials.md)
- [Component Issuing](component-issuing.md)
- [Manufacturing Routings](manufacturing-routings.md)
- [Work in Progress](work-in-progress.md)

## Oracle References

- [Oracle NetSuite Help Center: Work Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)