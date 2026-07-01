---
title: Bills of Materials
module: Manufacturing
difficulty: Intermediate
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Bills of Materials

## Quick Summary

A Bill of Materials (BOM) defines the components, quantities, and structure required to build an assembly item. It is the recipe for manufacturing — specifying what goes into a product, how much, and in what order.

## Difficulty

Intermediate

## Estimated Time

20 minutes

## Business Question

"What materials and quantities are required to manufacture one unit of this product?"

## Overview

The BOM is the foundation of manufacturing in NetSuite. It lists every component — raw materials, sub-assemblies, purchased parts, and labor — needed to produce one unit of the parent assembly item.

## BOM Structure

A BOM can be a single level or multi-level:

**Single-Level BOM**:
```
Chair (Assembly)
├── Frame (Inventory)
├── Fabric (Inventory) — 2 meters
├── Foam (Inventory)
└── Hardware Kit (Inventory)
```

**Multi-Level BOM**:
```
Chair (Assembly)
├── Frame Assembly (Assembly)          ← Sub-assembly
│   ├── Steel Tube (Inventory)
│   ├── Welding (Service)
│   └── Paint (Inventory)
├── Seat Assembly (Assembly)           ← Sub-assembly
│   ├── Plywood (Inventory)
│   ├── Foam (Inventory)
│   └── Fabric (Inventory) — 2 meters
└── Hardware Kit (Inventory)
```

## BOM Components per Unit

Each BOM line specifies:

| Field | Purpose |
|---|---|
| **Item** | The component being used |
| **Quantity** | How many units of this component per parent unit |
| **Unit of Measure** | The UOM for the component |
| **Yield** | Expected output percentage (for lossy processes) |
| **Effectivity Date** | When this BOM revision becomes active |
| **Notes** | Manufacturing instructions for this component |

## BOM Revisions

BOMs change over time — component substitutions, quantity adjustments, process improvements. BOM revisions track these changes:

| Revision | Status | Effective Date | Notes |
|---|---|---|---|
| A | Superseded | 2025-01-01 | Original BOM |
| B | Current | 2026-03-15 | Component substitution — new foam supplier |
| C | Pending | 2026-07-01 | Quantity reduction — process improvement |

## Phantom BOMs

A phantom BOM describes a sub-assembly that is built during production but is not stocked as a separate item. Phantom items are consumed invisibly during the parent build.

## Common Customer Questions

**Q**: My BOM shows the correct components but the work order won't build. What should I check?
**Common Causes**: Components are out of stock, BOM revision is not active, or an assembly item is not set up correctly.

**Q**: The work order consumed more components than expected. Why?
**Common Causes**: Yield percentage on the BOM, backflushing configuration, or manual component entry errors.

## Related Articles

- [Work Orders](work-orders.md)
- [Item Types for Manufacturing](item-types-for-manufacturing.md)
- [Component Issuing](component-issuing.md)
- [Inventory: Item Records](../inventory/item-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Bills of Materials](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)