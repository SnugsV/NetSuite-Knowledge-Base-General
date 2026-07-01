---
title: Component Issuing
module: Manufacturing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Component Issuing

## Quick Summary

Component issuing is the process of releasing raw materials and sub-assemblies from inventory to a work order. Issuing moves material from general inventory to Work in Progress (WIP), where it becomes part of the production cost.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Business Question

"How do raw materials get consumed during production?"

## Overview

Before production can begin, the required components must be issued from inventory. Issuing can happen manually (picking components from bins and recording the issue) or automatically (backflushing — components are consumed when the finished good is built).

## Issue Methods

### Manual Issuing

Pick components from inventory and record the issue against the work order:

```
Transactions > Manufacturing > Work Orders > Issue Components
```

**Best for**: Make-to-order, low-volume, high-value production where component tracking is critical.

### Backflushing

Components are automatically consumed when the work order is built. No manual issue transaction is needed.

**Best for**: High-volume, stable BOMs, repetitive manufacturing.

### Partial Issuing

Components issued in batches — some now, some later. Useful for long production runs where components are consumed at different stages.

## Records to Inspect

When components are not issuing correctly:

| Record | What to Check |
|---|---|
| **Work Order** | Status, BOM revision, quantities |
| **Component Item** | Quantity on hand, location |
| **BOM** | Component list, quantities, yield |
| **Inventory Location** | Correct location for the work order |

## Business Example

A work order for 100 chairs requires 100 frames, 200 meters of fabric, 100 foam pieces, and 100 hardware kits.

The production team issues components in two batches:

1. Day 1: Issue all frames and hardware kits (50%)
2. Day 3: Issue fabric and foam (50%)

The work order tracks each issue as it happens. WIP increases with each issue.

## Related Articles

- [Work Orders](work-orders.md)
- [Backflushing](backflushing.md)
- [Work in Progress](work-in-progress.md)
- [Bills of Materials](bills-of-materials.md)

## Oracle References

- [Oracle NetSuite Help Center: Component Issuing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)