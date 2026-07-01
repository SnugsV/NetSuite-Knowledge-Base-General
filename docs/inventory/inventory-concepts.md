---
title: Inventory Concepts
module: Inventory
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Inventory Concepts

## Quick Summary

This article explains the core concepts that underpin all inventory management in NetSuite: quantity fields, valuation methods, cost flow assumptions, inventory transactions, and the relationship between inventory and financial accounting.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

To work effectively with inventory in NetSuite, you need to understand several interrelated concepts. These concepts apply to every inventory transaction, every inventory report, and every inventory configuration decision.

## Quantity Concepts

NetSuite tracks multiple quantity values for every inventory item. Understanding the difference between them is critical.

### Quantity On Hand

The physical quantity of an item currently in stock. This is the most fundamental quantity — it represents what you actually have.

**Updated by**: Item receipts, inventory transfers, fulfillments, adjustments, build orders

### Quantity Available

The quantity that can be promised to customers. This is On Hand minus Committed quantities.

**Formula**: `On Hand - Committed = Available`

**Use case**: Customer service checking whether an item can be shipped

### Quantity Committed

The quantity allocated to open sales orders, work orders, or other commitments. This inventory is "spoken for" even though it has not yet shipped.

**Updated by**: Creating a sales order, creating a work order

### Quantity On Order

The quantity expected from purchase orders that have not yet been received.

**Updated by**: Creating a purchase order, receiving against a purchase order

### Quantity In Transit

The quantity that has been shipped between locations but not yet received.

**Updated by**: Transfer order fulfillment, transfer order receipt

### Why These Distinctions Matter

A company that checks On Hand instead of Available may promise inventory that is already committed to another customer. A company that ignores On Order may over-purchase. Each quantity serves a specific decision-making purpose.

```
Example — Chair Model X100:
  On Hand:      100 units physically in the warehouse
  Committed:    40 units allocated to sales orders
  Available:    60 units can be sold to new customers
  On Order:     50 units expected from a supplier next week
```

## Inventory Valuation

Inventory has a cost, and that cost affects financial statements. NetSuite supports several valuation methods. The method you choose determines how the cost of each unit is calculated.

### Available Valuation Methods

| Method | How Cost Is Calculated | Best For |
|---|---|---|
| **Average Cost** | Total cost of all units on hand divided by total quantity. Updated with each receipt. | Most businesses — smooths out price fluctuations |
| **Standard Cost** | A fixed cost assigned to an item. Variances between standard and actual cost are recorded separately. | Manufacturing — predictable cost basis |
| **FIFO (First In, First Out)** | The oldest units are assumed to be sold first. Cost follows the physical flow. | Perishable goods, industries with significant cost changes |
| **LIFO (Last In, First Out)** | The newest units are assumed to be sold first. Less common outside the US. | Tax optimization (US only) |
| **Specific Cost** | Each unit or lot has its own cost. | High-value items, unique items |

### How Valuation Works in Practice

When you receive inventory, the cost is recorded. When you sell or consume inventory, the cost is relieved through Cost of Goods Sold (COGS). The valuation method determines how much cost is relieved.

```
Example — Average Cost:
  Receipt 1: 10 units at $10 each → Average cost = $10.00
  Receipt 2: 10 units at $12 each → Average cost = $11.00 (total $220 / 20 units)
  Sale of 5 units: COGS = 5 × $11.00 = $55.00
```

## Inventory Transactions and Their Impact

Every inventory transaction has both a quantity impact and a financial impact:

| Transaction | Quantity Impact | Financial Impact |
|---|---|---|
| Item Receipt | Increases On Hand | Increases inventory asset, creates AP liability |
| Item Fulfillment | Decreases On Hand | Increases COGS, decreases inventory asset |
| Inventory Transfer | No net change (source decreases, destination increases) | No financial impact (unless average cost differs between locations) |
| Inventory Adjustment | Increases or decreases On Hand | Increases or decreases inventory asset, records gain/loss |
| Build Order (Assembly) | Decreases components, increases assembly | Components' cost becomes assembly's cost |

## Cost of Goods Sold (COGS)

When inventory is sold or consumed, its cost is transferred from the balance sheet (Inventory Asset) to the income statement (Cost of Goods Sold). This is called **cost relief**.

Understanding COGS is essential because it directly affects profitability:

- If COGS is too low, profit appears higher than it actually is
- If COGS is too high, profit appears lower
- The valuation method determines when and how COGS is calculated

## Inventory as a Balance Sheet Asset

From an accounting perspective, inventory is a current asset. When you receive inventory, the asset account increases. When you sell inventory, the asset decreases and COGS increases.

This means inventory decisions have financial consequences:

- Writing off obsolete inventory reduces assets and increases expenses
- Overstating inventory inflates assets and understates COGS
- Incorrect location counts affect valuation if locations have different average costs

## Item Costs Across Transactions

The cost of an item can differ depending on where it is in the supply chain:

| Stage | Cost |
|---|---|
| Purchase Order | Expected cost based on the PO |
| Item Receipt | Actual cost based on the receipt |
| Transfer Order | Cost at the source location |
| Item Fulfillment | Cost at the fulfillment location (may differ if locations have different averages) |

## Knowledge Check

1. A customer wants to order 50 units of Item X. On Hand is 100, Committed is 70, On Order is 30. How many units can you promise? (Answer: 30 — Available = 100 - 70)
2. You receive 50 units at $8 and later 50 units at $12. Using average cost, what is the cost per unit? (Answer: $10.00 — total $1,000 / 100 units)
3. **True/False**: Transferring inventory between two locations that have different average costs can affect the general ledger. (Answer: True — if the average cost differs, the transfer creates a cost variance)

## Related Articles

- [What Is Inventory Management?](what-is-inventory.md)
- [Item Records](item-records.md)
- [Item Types](item-types.md)
- [Inventory Locations](inventory-locations.md)
- [Units of Measure](units-of-measure.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Inventory Concepts](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Inventory Valuation](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)