---
title: Fulfilling Orders
module: Inventory
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Fulfilling Orders

## Quick Summary

Order fulfillment is the process of picking, packing, and shipping items from inventory to fill a customer's sales order. The Item Fulfillment transaction decreases inventory, triggers COGS recognition, and initiates the billing process.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Fulfillment is where inventory leaves the business. When a customer places an order, the warehouse team picks the items from their storage locations, packs them for shipment, and creates an Item Fulfillment in NetSuite. This transaction has cascading effects: inventory decreases, cost of goods sold is recognized, the customer can be invoiced, and revenue can be recorded.

## The Fulfillment Workflow

```
Sales Order created by customer
       ↓
Order reaches warehouse (pick list generated)
       ↓
Items picked from bins/locations
       ↓
Items packed and labeled
       ↓
Carrier picks up shipment
       ↓
Item Fulfillment created in NetSuite
       ↓
Inventory decreases, COGS recognized
       ↓
Invoice generated (separate step)
```

## Departments Involved

| Department | Role |
|---|---|
| **Sales** | Enter and manage sales orders |
| **Warehouse / Fulfillment** | Pick, pack, and ship items |
| **Shipping** | Coordinate carriers and labels |
| **Accounting** | Generate invoices, recognize revenue |
| **Customer Service** | Communicate shipment status to customers |

## The Item Fulfillment Transaction

The Item Fulfillment is created from a sales order.

```
Transactions > Sales > Fulfill Orders
```

Each Item Fulfillment records:

| Field | Purpose |
|---|---|
| **Sales Order** | The order being fulfilled |
| **Item** | What was shipped |
| **Quantity** | How many units |
| **Location** | Where the items shipped from |
| **Bin (if enabled)** | Specific pick location |
| **Package** | Weight, dimensions, tracking number |
| **Date** | When the fulfillment occurred |

## Fulfillment Methods

### Full Fulfillment

Shipping the complete sales order quantity. The order is marked fully fulfilled and moves to the billing stage.

### Partial Fulfillment

Shipping only part of a sales order. The remaining items stay on the order for later fulfillment. Common when:

- Some items are backordered
- Some items ship from a different location
- The customer accepts split shipments

### Backorder

When ordered items are not available, the order can be partially fulfilled with the remaining items on backorder. NetSuite tracks backordered quantities and can trigger replenishment.

### Drop Ship

The vendor ships directly to the customer. NetSuite creates both a purchase order (to the vendor) and a fulfillment record without the items ever touching the company's inventory.

## Pick, Pack, Ship

### Picking

Creating pick lists from sales orders. Common methods:

- **Single order pick**: One picker picks one order at a time
- **Batch pick**: One picker picks multiple orders simultaneously
- **Zone pick**: Pickers work in assigned warehouse zones
- **Wave pick**: Orders are grouped by shipping deadline

### Packing

After picking, items are packed for shipment. The packing step records:

- Package weight and dimensions
- Shipping carrier and service level
- Tracking number
- Package contents (if multiple packages per order)

### Shipping

The final step transfers the package to the carrier. In NetSuite, shipping is recorded on the Item Fulfillment, often with integration to carrier systems (UPS, FedEx) for rate shopping and label generation.

## Accounting Impact

Every Item Fulfillment has an accounting side:

| Account | Debit/Credit | Amount |
|---|---|---|
| **Cost of Goods Sold** | Debit | Quantity × Average Cost |
| **Inventory Asset** | Credit | Quantity × Average Cost |

This means fulfilling an order:
- Decreases the inventory asset on the balance sheet
- Records COGS as an expense on the income statement
- Creates the basis for profit calculation (Revenue - COGS = Gross Profit)

## Fulfillment and Invoicing

Fulfillment and invoicing are separate steps. An order can be:

- **Fulfilled and not yet invoiced** — Items shipped, customer not yet billed
- **Invoiced and not yet fulfilled** — Customer billed, items not yet shipped (less common)
- **Fulfilled and invoiced together** — Synchronized (most common pattern)

## Business Example

A customer orders 10 units of SKU CHR-100 and 5 units of SKU TBL-200. The warehouse has 8 CHR-100 and 5 TBL-200 available.

The fulfillment team:
1. Picks 8 CHR-100 from bin A-3-12 and 5 TBL-200 from bin B-1-04
2. Packs both items in one box (15.5 kg, tracking number 1Z999999)
3. Creates an Item Fulfillment for the shipped quantities
4. NetSuite decreases On Hand: CHR-100 by 8, TBL-200 by 5
5. The sales order shows "Partially Fulfilled" — 2 CHR-100 remain on backorder

## Common Bottlenecks

| Bottleneck | Impact |
|---|---|
| No pick path optimization | Pickers walk long distances between picks |
| Disorganized bin locations | Items are not in their assigned bins |
| No wave planning | All orders are picked simultaneously without priority |
| Package information not captured | Missing tracking numbers make customer inquiries harder |
| Manual carrier selection | No rate comparison, higher shipping costs |

## Operational Risks

- **Picking the wrong item or quantity**: Creates fulfillment errors, returns, and customer dissatisfaction
- **Fulfilling without available stock**: Results in negative inventory, which causes valuation issues
- **Delayed fulfillment entry**: System shows available inventory that has already been shipped
- **No package tracking**: Customer service cannot provide shipment status

## Common Mistakes

- **Fulfilling from the wrong location**: If multiple locations have stock, the wrong location may be selected, affecting inventory accuracy
- **Skipping the package step**: Without package details, shipping information is missing from the fulfillment record
- **Creating fulfillment without physical picking**: "Fulfill first, pick later" leads to discrepancies when items cannot actually be found
- **Not recording partial fulfillments**: Waiting until everything is available delays revenue recognition

## Best Practices

- Fulfill from the sales order — do not create standalone Item Fulfillments
- Pick items before creating the fulfillment transaction
- Record package details (weight, tracking) for every shipment
- Set up automatic email notifications for shipment confirmations
- Use wave picking for high-volume fulfillment environments
- Reconcile fulfilled quantities with picked quantities daily
- Train pickers on bin location accuracy

## Knowledge Check

1. A sales order has 10 units. Only 6 are available. What are your options? (Answer: Partial fulfillment of 6, backorder 4. Or wait until all 10 are available.)
2. **Scenario**: You fulfill an order for 5 units with an average cost of $12 each. What is the accounting entry? (Answer: Debit COGS $60, Credit Inventory Asset $60.)
3. **True/False**: Fulfillment and invoicing must happen simultaneously in NetSuite. (Answer: False — they are separate steps.)

## Related Articles

- [Receiving Inventory](receiving-inventory.md)
- [Transfer Orders](transfer-orders.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Returns Processing](returns-processing.md)
- [Sales Orders](../sales/README.md) (future module)
- [Inventory Concepts](inventory-concepts.md)

## Oracle References

- [Oracle NetSuite Help Center: Item Fulfillment](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Fulfilling Sales Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)