---
title: Returns Processing
module: Inventory
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Returns Processing

## Quick Summary

Returns processing handles inventory coming back into the business — from customer returns, vendor returns, or inter-company transfers. Each return type has different workflows, accounting treatments, and inventory implications.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Not all inventory movement is forward. Products come back — customers return defective items, vendors receive defective raw materials, or internal transfers are reversed. Proper returns processing ensures inventory records stay accurate and financial impacts are correctly recorded.

## Types of Returns

| Return Type | Direction | NetSuite Transaction |
|---|---|---|
| **Customer Return** | Customer → Company | Return Authorization, Item Receipt |
| **Vendor Return** | Company → Vendor | Vendor Return, Inventory Adjustment |
| **Transfer Reversal** | Destination → Source | Transfer Order (reverse) |
| **RMA (Return Merchandise Authorization)** | Customer → Company (with authorization) | RMA transaction |

## Customer Returns Workflow

```
Customer requests return
       ↓
Return Authorization created (RMA)
       ↓
Items received at warehouse
       ↓
Inspection / quality check
       ↓
Decision: Restock, Repair, Dispose
       ↓
Item Receipt (return) created
       ↓
Inventory increases
       ↓
Credit Memo issued (if refunding)
```

### Return Authorization

A Return Authorization (RA) is the customer-facing document that authorizes a return. It records:

- Which customer is returning items
- Which items and quantities
- The reason for the return
- The expected condition
- Whether a refund or replacement is authorized

```
Transactions > Returns > Return Authorizations
```

### Inspection and Disposition

When returned items arrive, they should be inspected before being restocked:

| Disposition | Description | Inventory Impact |
|---|---|---|
| **Restock** | Item is in sellable condition | Add to inventory at original cost |
| **Repair** | Item needs rework before resale | Add to inventory at reduced value, or transfer to repair location |
| **Dispose** | Item is damaged beyond use | Do not add to inventory. Create adjustment to write off. |
| **Vendor Return** | Item is defective and will be returned to the supplier | Create vendor return transaction |

## Restocking Fees

Some companies charge restocking fees for returns. The fee is deducted from the refund amount. NetSuite supports restocking fees through return authorization configurations.

## Vendor Returns

When defective or incorrect inventory needs to be returned to a supplier:

1. Create a **Vendor Return** transaction
2. Pick and ship the items back to the vendor
3. Receive a credit from the vendor (or replacement)
4. The inventory adjustment reduces stock

```
Transactions > Purchasing > Enter Vendor Returns
```

## Accounting Impact

### Customer Return Restocked

| Account | Debit/Credit | Amount |
|---|---|---|
| **Inventory Asset** | Debit | Original cost |
| **Cost of Goods Sold** | Credit | Original cost |

The inventory value is restored, and COGS is reduced, reversing the original fulfillment entry.

### Customer Return with Refund

| Account | Debit/Credit | Amount |
|---|---|---|
| **Sales Returns / Revenue** | Debit (reduces revenue) | Sales price |
| **Accounts Receivable** | Credit | Sales price |

The revenue is reduced (or refunded) and the customer's balance is credited.

### Vendor Return

| Account | Debit/Credit | Amount |
|---|---|---|
| **AP / Vendor Credit** | Debit | Cost |
| **Inventory Asset** | Credit | Cost |

## Business Example

A customer received a damaged chair (SKU CHR-100) and requests a return.

1. **RA Created**: Customer service creates a Return Authorization for 1 unit of CHR-100, reason "Damaged in transit"
2. **Item Received**: Warehouse receives the damaged chair
3. **Inspection**: The chair has a cracked frame. Cannot be resold.
4. **Disposition**: Marked for disposal — cannot be restocked
5. **Inventory Adjustment**: 1 unit of CHR-100 is disposed. The adjustment account is "Damaged Goods Expense."
6. **Credit Memo**: Customer is refunded the purchase price
7. **Result**: Inventory is adjusted down by 1 unit. The expense is recorded as damaged goods, not COGS.

## Common Mistakes

- **Restocking damaged items without inspection**: Returned items that are damaged should not be added back to sellable inventory
- **Not using Return Authorizations**: Returns without RA tracking are difficult to reconcile and audit
- **Mixing customer and vendor returns**: Different transactions, different accounting. Keep them separate
- **Incorrect cost on restocked items**: Restocked items should return at their original cost, not current average cost
- **Not tracking return reasons**: Without reason codes, you cannot identify patterns (e.g., a specific product has a high defect rate)

## Best Practices

- Require a Return Authorization for every customer return
- Inspect returned items before restocking — never assume condition
- Use reason codes to categorize returns (defective, wrong item, changed mind, damaged)
- Track return rates by product to identify quality issues
- Set return policies (time limits, condition requirements) and enforce them
- Use Saved Searches to monitor return rates and identify problem products
- Segregate returned inventory until inspection is complete

## Knowledge Check

1. A customer returns an item that is still in perfect condition. What disposition? (Answer: Restock — add back to sellable inventory.)
2. **Scenario**: A supplier delivers 50 units that are the wrong color. You need to send them back. What transaction type? (Answer: Vendor Return.)
3. **True/False**: Restocking a returned item always restores the inventory at the current average cost. (Answer: False — it should restore at the original cost from when the item was sold.)

## Related Articles

- [Receiving Inventory](receiving-inventory.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Fulfilling Orders](fulfilling-orders.md)
- [Inventory Concepts](inventory-concepts.md)
- [Sales Orders](../sales/README.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Return Authorizations](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Processing Returns](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)