---
title: Item Types for Manufacturing
module: Manufacturing
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Item Types for Manufacturing

## Quick Summary

Manufacturing uses specific item types — Assembly Items for finished goods and non-inventory or inventory items for raw materials and components. Understanding how each item type behaves in manufacturing is essential for accurate BOMs and work orders.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

In distribution, items are either stocked or not. In manufacturing, items can also be "produced" — assembled from other items. This distinction requires additional item types and a Bill of Materials to define the production recipe.

## Assembly Items

Assembly Items represent products that are built from components. Key characteristics:

- Have a Bill of Materials (BOM) defining their component structure
- Can be built through Work Orders
- Have quantity tracking like inventory items
- Cost is calculated from component costs plus production costs
- Can be sold like any other item

## Item Types Used in Manufacturing

| Type | Role in Manufacturing |
|---|---|
| **Inventory Item** | Raw materials, components, and finished goods (standard stock) |
| **Assembly Item** | Finished goods built from components via BOM |
| **Non-Inventory Item** | Services or supplies used in production but not tracked |
| **Kit Item** | Pre-configured bundle — NOT a manufactured item |

## Assembly vs. Kit

New users often confuse Assemblies and Kits:

| Dimension | Assembly | Kit |
|---|---|---|
| **Built or bundled?** | Built — transforms components | Bundled — groups components |
| **BOM required** | Yes | No |
| **Work Order** | Yes | No |
| **Inventory impact** | Components consumed, assembly added | Components reduced, no kit created |
| **Cost** | Build cost from components | Sum of component prices |

## Business Example

A bicycle manufacturer creates an Assembly Item for "Mountain Bike X100." Its BOM includes a frame (inventory item), wheels (inventory), drivetrain (inventory), and labor (non-inventory service item). When a work order is built, the components are consumed and the finished bicycle appears in inventory.

## Related Articles

- [What Is Manufacturing?](what-is-manufacturing.md)
- [Bills of Materials](bills-of-materials.md)
- [Work Orders](work-orders.md)
- [Inventory: Item Types](../inventory/item-types.md)

## Oracle References

- [Oracle NetSuite Help Center: Assembly Items](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)