---
title: Receiving Inventory
module: Inventory
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Receiving Inventory

## Quick Summary

Receiving inventory is the process of accepting goods from a supplier and recording them into NetSuite. The Item Receipt transaction increases inventory quantity and value, creates an accounts payable liability, and provides the foundation for accurate stock records.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Receiving is where inventory enters the business. When a purchase order is placed with a vendor and the goods arrive, the receiving team inspects the shipment and records what was received. This single transaction — the Item Receipt — has consequences across inventory, accounting, purchasing, and operations.

## The Receiving Workflow

```
Vendor ships goods
       ↓
Goods arrive at receiving dock
       ↓
Inspect shipment (quantity, damage, quality)
       ↓
Match to Purchase Order
       ↓
Create Item Receipt in NetSuite
       ↓
Inventory increases
       ↓
Items move to putaway / bin location
```

## Departments Involved

| Department | Role |
|---|---|
| **Receiving / Warehouse** | Physically receive and inspect goods |
| **Purchasing** | Ensure receipt matches the purchase order |
| **Quality** | Inspect for damage or defects |
| **Accounting** | Match receipt to vendor bill for payment |
| **Inventory Control** | Verify quantities and investigate discrepancies |

## The Item Receipt Transaction

The Item Receipt is the core transaction for receiving inventory. It is created against a purchase order.

```
Transactions > Purchasing > Receive Items
```

Each Item Receipt records:

| Field | Purpose |
|---|---|
| **Purchase Order** | The PO being received against |
| **Item** | What was received |
| **Quantity** | How many units were received |
| **Location** | Where the items are being placed |
| **Bin (if enabled)** | Specific storage location |
| **Date** | When the receipt occurred |

## Receiving Methods

### Full Receipt

Receiving the complete PO quantity. All items and quantities match the purchase order. NetSuite automatically marks the PO as fully received.

### Partial Receipt

Receiving only part of a purchase order. Common when a vendor ships in multiple batches. The PO remains open until the remaining quantities are received.

### Over-Receipt

Receiving more than the ordered quantity. NetSuite allows this only if the PO is configured for over-receipt. Requires reconciliation with the vendor.

### Direct Drop Ship Receipt

When a vendor ships directly to a customer, the receipt is created against a drop-ship purchase order. The items are received and fulfilled simultaneously — they never enter physical inventory.

## Putaway

After receiving, items must be moved to their storage locations. Putaway can be:

- **Directed put-away** (WMS): The system suggests a bin location
- **Manual put-away**: The warehouse worker chooses where to place items
- **Location transfer**: A follow-up transaction moves items from the receiving dock location to the storage location

Putaway is a warehouse process, not a NetSuite transaction, but the bin assignment should be updated in the system when items are moved to permanent locations.

## Accounting Impact

Every Item Receipt has an accounting side:

| Account | Debit/Credit | Amount |
|---|---|---|
| **Inventory Asset** | Debit | Quantity × Cost |
| **Accrued Purchases (or AP)** | Credit | Quantity × Cost |

This means receiving inventory creates an asset on the balance sheet and a corresponding liability. When the vendor bill is later entered and matched, the liability is replaced with an accounts payable entry.

## Three-Way Matching

For accurate financial control, three documents should match:

1. **Purchase Order** — What was ordered
2. **Item Receipt** — What was received
3. **Vendor Bill** — What is being paid for

When all three agree, the transaction is clean. Discrepancies between any two require investigation.

## Business Example

A distributor orders 500 units of SKU CHR-100 at $15 each. The truck arrives with 480 units — 20 units are backordered. The receiving clerk:

1. Verifies the PO exists for 500 units
2. Counts 480 units received
3. Notes no visible damage
4. Creates an Item Receipt for 480 units against the PO
5. NetSuite increases On Hand to 480
6. The PO shows "Partially Received" — 20 remain open

## Common Bottlenecks

| Bottleneck | Impact |
|---|---|
| Unlabeled incoming goods | Delays receiving while items are identified |
| Damaged goods without process | No standard workflow for rejections and vendor returns |
| No receiving schedule | Carriers arrive at peak hours, causing dock congestion |
| Missing PO information | Receiving team cannot match goods to the correct order |
| No putaway process after receipt | Items sit on the dock, visible in the system but not available for picking |

## Operational Risks

- **Receiving without a PO**: Creates unmatched receipts that are difficult to reconcile
- **Incorrect quantities**: Overstated inventory leads to stockouts when orders cannot be fulfilled
- **No damage inspection**: Damaged goods recorded as good inventory cause downstream quality issues
- **Delayed receipt entry**: System shows lower inventory than physically exists, causing unnecessary purchases

## Common Mistakes

- **Entering Item Receipts without inspecting goods**: "Receiving by paper" — entering quantities before physically verifying
- **Not recording partial receipts**: Waiting for the full shipment before entering any receipt leaves inventory records inaccurate
- **Using Inventory Adjustments instead of correcting the receipt**: If the receipt was incorrect, adjust the receipt — don't create a separate adjustment
- **Not assigning locations**: Items received without a location default to an unspecified location, making them harder to find and pick

## Best Practices

- Always inspect goods before entering the Item Receipt
- Record receipts promptly — on the same day goods arrive
- Use partial receipts for split shipments — don't wait for the complete order
- Match Item Receipts to Vendor Bills within the same period
- Train receiving staff on basic discrepancy resolution
- Use barcode scanning for high-volume receiving environments
- Perform random spot checks on received quantities

## Knowledge Check

1. Your PO is for 200 units. The vendor ships 150 and the remaining 50 are backordered. How do you record this? (Answer: Partial receipt for 150. The PO stays open for the remaining 50.)
2. **Scenario**: An Item Receipt is entered but the corresponding Vendor Bill has not been created. Where does the inventory value sit on the balance sheet? (Answer: Inventory Asset debited, Accrued Purchases credited.)
3. **True/False**: Over-receiving is always allowed in NetSuite. (Answer: False — over-receipt requires PO configuration.)

## Related Articles

- [Fulfilling Orders](fulfilling-orders.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Cycle Counting](cycle-counting.md)
- [Purchase Orders](../purchasing/README.md) (future module)
- [Inventory Concepts](inventory-concepts.md)

## Oracle References

- [Oracle NetSuite Help Center: Item Receipts](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Receiving Items](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)