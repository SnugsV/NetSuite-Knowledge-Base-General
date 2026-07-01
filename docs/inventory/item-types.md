---
title: Item Types
module: Inventory
difficulty: Beginner
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Item Types

## Quick Summary

NetSuite supports multiple item types, each designed for a specific business purpose. The item type determines how NetSuite tracks quantities, costs, transactions, and financial accounts. Choosing the correct item type is the most important decision when creating an item record.

## Difficulty

Beginner

## Estimated Time

15 minutes

## Overview

Not everything a company buys or sells is "inventory" in the ERP sense. A product stored in a warehouse (inventory) is treated differently from a service billed to a customer (non-inventory), which is different from a product assembled from components (assembly). The item type tells NetSuite how to handle each item.

## Item Type Comparison

| Type | Tracks Quantity | Tracks Cost | Can Be Sold | Can Be Purchased | Can Be Built |
|---|---|---|---|---|---|
| **Inventory** | Yes | Yes | Yes | Yes | No |
| **Non-Inventory** | No | No | Yes | Yes | No |
| **Service** | No | Yes | Yes | No | No |
| **Kit/Package** | No | Custom | Yes | No | No |
| **Assembly** | Yes (BOM) | Yes (from components) | Yes | No | Yes |
| **Group** | No | No | No | No | No |
| **Description** | No | No | No | No | No |
| **Discount** | No | No | No (reduces price) | No | No |
| **Payment** | No | No | No (tender) | No | No |
| **Subtotal** | No | No | No (section total) | No | No |

## Inventory Item

**Best for**: Physical products you buy, store, and sell.

Inventory items are the most common type. NetSuite tracks:

- Quantity On Hand, Available, Committed, On Order
- Cost (using the valuation method configured for the item)
- Locations and bins
- Transaction history (receipts, transfers, fulfillments)
- Reorder points and replenishment

**Example**: A distributor selling office chairs. The chairs are received, stored, and shipped to customers.

**Key decision**: When you create an inventory item, you must select a valuation method (average cost, FIFO, etc.). This decision affects financial reporting and cannot be changed later for items with transaction history.

## Non-Inventory Item

**Best for**: Products you buy and sell without tracking quantities or cost.

Non-inventory items are used for items that pass through the business without being stocked. NetSuite records the purchase and sale but does not track quantity on hand or calculate cost automatically.

**Example**: A company that resells software licenses. The license is ordered for a specific customer and delivered electronically — no stocking, no warehouse.

## Service Item

**Best for**: Labor, consulting, professional services.

Service items track cost (labor rate) and revenue (billable rate) but not physical quantity. They are used for time-based billing, project costing, and service revenue.

**Example**: An implementation consultant's hourly rate. The service item is added to sales orders and purchase orders for subcontracted services.

## Kit / Package Item

**Best for**: Pre-configured bundles of items sold together.

A kit item groups multiple items (inventory, non-inventory, service) into a single sellable unit. When a kit is sold, each component's inventory is reduced individually. Kits do not have their own quantity tracking — selling a kit affects the component quantities.

**Example**: A "Computer Workstation Starter Kit" containing a monitor, keyboard, mouse, and cable. When the kit is sold, each component's inventory is reduced.

## Assembly Item

**Best for**: Items built from components.

Assembly items have a Bill of Materials (BOM) that defines which components and quantities are needed. When a build order is completed, the component quantities are reduced and the assembly quantity is increased.

**Example**: A furniture manufacturer builds chairs from frame components, fabric, and hardware. The assembly item "Office Chair" is built from its component parts.

## Group Item

**Best for**: Displaying a list of items on a sales form without affecting inventory.

A group item displays multiple items on a transaction but does not track them as a unit. Each item in the group is treated individually.

**Example**: A "Recommended Accessories" group that appears as a selection on a sales order.

## Choosing the Right Type

| Your situation | Choose this type |
|---|---|
| You stock it in a warehouse | Inventory Item |
| You buy and sell it without stocking | Non-Inventory Item |
| You bill for time or expertise | Service Item |
| You sell a pre-configured bundle | Kit/Package Item |
| You build it from components | Assembly Item |
| You need to display a list but not track it | Group Item |

## Common Mistakes

- **Using Non-Inventory when you need Inventory**: If you need to track quantities, use Inventory Item. Non-Inventory items have no quantity tracking.
- **Using Kit when you need Assembly**: Kits do not build anything — they are pre-configured selections. If you manufacture or assemble, use Assembly Item.
- **Using Inventory for services**: Service items have different financial behavior. Using Inventory for services creates unnecessary quantity tracking and incorrect financial postings.
- **Not understanding the implications of the choice**: Changing an item type after transactions exist is difficult. Choose carefully during setup.

## Best Practices

- Determine the item type before creating the item record. Changing it later is difficult.
- Use Inventory items for anything you stock and track quantities for.
- Use Assembly items only if you have a defined bill of materials and build process.
- Review item types periodically — a business that starts as a reseller (Non-Inventory) may need to switch to Inventory as it grows.

## Knowledge Check

1. Your company sells software subscriptions. Customers pay monthly, and there is no physical product. Which item type? (Answer: Service Item)
2. Your company assembles bicycle frames from tubes, welds, and paint. Which item type for the finished frame? (Answer: Assembly Item — it has a bill of materials)
3. A retailer stocks shoes in a warehouse and sells them in stores. Which item type? (Answer: Inventory Item)

## Related Articles

- [Item Records](item-records.md)
- [What Is Inventory Management?](what-is-inventory.md)
- [Inventory Concepts](inventory-concepts.md)
- [Inventory Status](inventory-status.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Item Types](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Item Type Comparison](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)