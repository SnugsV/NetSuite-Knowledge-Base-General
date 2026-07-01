---
title: Order Fulfillment
module: Sales
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Order Fulfillment

## Quick Summary

Order fulfillment is the process of picking, packing, and shipping items to complete a customer's sales order. It is where the O2C lifecycle meets the warehouse, converting a promise into a delivered product.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Order fulfillment bridges the gap between the sales order (a promise) and the invoice (a request for payment). The physical act of getting the right items to the right customer at the right time determines whether the customer is satisfied and whether the company gets paid.

## The Fulfillment Workflow

```
Sales Order Approved
       ↓
Pick List Generated
       ↓
Items Picked from Bins/Locations
       ↓
Items Packed for Shipment
       ↓
Carrier Selected / Label Printed
       ↓
Shipment Recorded (Item Fulfillment)
       ↓
Tracking Number Communicated to Customer
       ↓
Order Ready for Invoicing
```

## Fulfillment Methods

| Method | Description | Best For |
|---|---|---|
| **Full Fulfillment** | All items shipped at once | Complete orders with available stock |
| **Partial Fulfillment** | Some items shipped; remaining backordered | Split shipments, phased delivery |
| **Drop Ship** | Vendor ships directly to customer | Non-stocked items, vendor-direct |
| **Cross-Dock** | Incoming receipt is immediately fulfilled | Time-sensitive or just-in-time orders |

## The Item Fulfillment Transaction

The Item Fulfillment records the shipment:

| Field | Purpose |
|---|---|
| **Sales Order** | The order being fulfilled |
| **Item** | What was shipped |
| **Quantity** | How many units |
| **Location** | Where it shipped from |
| **Bin (if enabled)** | Pick location |
| **Package** | Weight, dimensions, tracking |
| **Date** | Shipment date |

## Picking Strategies

| Strategy | How It Works |
|---|---|
| **Single Order Pick** | One picker fulfills one order at a time |
| **Batch Pick** | Pick multiple orders simultaneously, sort later |
| **Zone Pick** | Pickers work in assigned zones; orders consolidated |
| **Wave Pick** | Orders grouped by shipping deadline or carrier |

## Packing and Shipping

After picking, items are packed:

- Box selection based on item dimensions and quantity
- Packing slip included in the box
- Package weight recorded for carrier billing
- Shipping label generated (carrier integration)
- Tracking number recorded on the fulfillment

## Accounting Impact

Fulfillment affects the financial statements:

| Account | Debit/Credit |
|---|---|
| **Cost of Goods Sold** | Debit |
| **Inventory Asset** | Credit |

The fulfillment transaction triggers cost recognition: the inventory value moves from the balance sheet to the income statement.

## Business Example

A customer orders 10 units of SKU A and 5 units of SKU B. The warehouse has 8 of SKU A and 5 of SKU B available.

**Fulfillment**:
- 8 units of SKU A shipped (full order quantity — 2 backordered)
- 5 units of SKU B shipped (full order quantity)
- 2 units of SKU A backordered — customer notified
- Shipment: 1 box, 12 kg, tracking number 1Z999
- Inventory reduced by 13 units
- COGS recorded for 13 units

## Common Mistakes

- **Picking the wrong item or quantity**: Fulfillment errors lead to returns, credits, and customer dissatisfaction
- **Fulfilling without available stock**: Negative inventory causes valuation issues
- **No package details recorded**: Without tracking numbers, customer service cannot answer "Where is my order?"
- **Delayed fulfillment entry**: System shows available inventory that has already been shipped

## Best Practices

- Pick items before entering the fulfillment transaction
- Use barcode scanning to verify picks
- Record package details for every shipment
- Integrate with carrier systems for label printing and tracking
- Set fulfillment SLAs (e.g., ship within 24 hours of order approval)
- Communicate tracking information to customers automatically

## Related Articles

- [Sales Orders](sales-orders.md)
- [Invoicing and Revenue](invoicing-and-revenue.md)
- [Backorders and Exceptions](backorders-and-exceptions.md)
- [Inventory: Fulfilling Orders](../inventory/fulfilling-orders.md)
- [Inventory: Receiving Inventory](../inventory/receiving-inventory.md)

## Oracle References

- [Oracle NetSuite Help Center: Order Fulfillment](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)