---
title: Three-Way Matching
module: Purchasing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Three-Way Matching

## Quick Summary

Three-way matching compares three documents — the purchase order, the item receipt, and the vendor bill — to verify that quantities and prices are consistent before payment is authorized. It is the primary control against overpayment and fraud in the Procure-to-Pay process.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Three-way matching answers three questions:

1. **Did we order it?** (Purchase Order)
2. **Did we get it?** (Item Receipt)
3. **Are we being charged correctly?** (Vendor Bill)

If all three agree, the bill is authorized for payment. Discrepancies are investigated before payment.

## The Three Documents

| Document | What It Confirms | Created By |
|---|---|---|
| **Purchase Order** | What was ordered, at what price | Purchasing |
| **Item Receipt** | What was received, in what quantity | Warehouse / Receiving |
| **Vendor Bill** | What is being invoiced, at what price | Accounts Payable |

## How Matching Works

```
PO:            100 units @ $12.00 = $1,200.00
Item Receipt:  100 units received
Vendor Bill:   100 units @ $12.00 = $1,200.00

Result: MATCH — all three documents agree.
         Bill is authorized for payment.
```

```
PO:            100 units @ $12.00 = $1,200.00
Item Receipt:  95 units received (5 damaged)
Vendor Bill:   100 units @ $12.00 = $1,200.00

Result: QUANTITY MISMATCH — receipt shows 95, bill shows 100.
         Investigate: Were 5 units damaged? Should vendor credit?
```

```
PO:            100 units @ $12.00 = $1,200.00
Item Receipt:  100 units received
Vendor Bill:   100 units @ $12.50 = $1,250.00

Result: PRICE MISMATCH — PO price $12.00, bill price $12.50.
         Investigate: Was a price change communicated?
```

## What Gets Matched

| Element | Source Documents | Tolerance |
|---|---|---|
| **Item** | PO, Receipt, Bill | Must match exactly |
| **Quantity** | PO, Receipt, Bill | Quantity tolerance (e.g., 5% or ±10 units) |
| **Unit Price** | PO, Bill | Price tolerance (e.g., 5% or $0.50) |
| **Total Amount** | PO, Bill | Should match if quantity and price match |
| **Vendor** | PO, Bill | Must match exactly |

## Matching Tolerances

Tolerances allow minor discrepancies to pass without manual intervention:

| Tolerance Type | Typical Setting | Example |
|---|---|---|
| **Quantity** | ±5% or ±10 units | PO 100, Receipt 98 — passes if tolerance is 5% |
| **Price** | ±5% or ±$1.00 | PO $12.00, Bill $12.30 — passes if tolerance is 5% |
| **Amount** | ±$10.00 or ±5% | Total variance less than $10 — passes |

Tolerances should be reviewed periodically. Too tight — every bill requires manual review. Too loose — errors and fraud slip through.

## Two-Way vs. Three-Way Matching

| Method | Documents Matched | When to Use |
|---|---|---|
| **Three-Way Match** | PO + Receipt + Bill | Inventory items where quantity is verified at receipt |
| **Two-Way Match** | PO + Bill only | Services, non-inventory items, where receipt is not verified |
| **One-Way Match** | PO only | Prepaid items, utility bills, subscriptions |

## Exceptions and Resolution

| Exception | Likely Cause | Resolution |
|---|---|---|
| Quantity billed > quantity received | Vendor shipped more than ordered | Contact vendor for return authorization or bill only for received qty |
| Price on bill > price on PO | Price increase not communicated | Verify with purchasing; if valid, update PO |
| Bill received with no PO | Purchased without authorization | Obtain approval or return goods |
| Bill for items not received | Advance payment, or billing error | Check if items are in transit; if not, contact vendor |

## Configuring Matching in NetSuite

Matching settings are configured at:

```
Setup > Accounting > Match Bills to Purchase Orders / Item Receipts
```

Configuration options:

- **Enable matching**: Turn matching on or off
- **Tolerance percentages**: Set acceptable variances
- **Tolerance amounts**: Set absolute dollar thresholds
- **Auto-approve matching bills**: Bills that match within tolerance are automatically approved
- **Require receipt for bill**: Prevent bill entry until the receipt is recorded

## Business Example

An AP department processes 200 vendor bills per week.

**Matching results breakdown**:
- 75% match exactly — auto-approved, payment scheduled
- 15% match within tolerance — auto-approved with note
- 8% have minor discrepancies — manual review, resolved within 24 hours
- 2% have significant discrepancies — escalated to purchasing, may take days to resolve

Without three-way matching, all 200 bills would require manual verification. With matching, 90% are processed automatically.

## Common Mistakes

- **Not using tolerances**: Expecting perfect matches on every bill creates unnecessary manual work
- **Paying before matching**: If payment is processed before the three-way match is complete, overpayments are difficult to recover
- **Allowing non-PO bills without controls**: Non-PO bills bypass the matching process. They should require higher-level approval
- **Not following up on exceptions**: Unresolved matching exceptions accumulate and lead to overdue bills or duplicate payments
- **Ignoring receipt tolerances**: Quantity tolerances on receipts affect the matching process. Set them appropriately

## Best Practices

- Use three-way matching for all inventory purchases
- Use two-way matching for services and non-inventory items
- Set tolerances that balance efficiency with control
- Review matching exception reports weekly
- Investigate and resolve exceptions within 5 business days
- Train AP staff on the matching process and common exception types
- Use NetSuite's auto-approve feature for bills that match within tolerance

## Knowledge Check

1. A PO has 500 units at $8 each. The receipt shows 500 units. The bill shows 500 units at $8.25 each. What is the issue? (Answer: Price mismatch — bill price exceeds PO price by $0.25.)
2. **Scenario**: A bill is entered without a PO reference. Can three-way matching be performed? (Answer: No — matching requires a PO. Non-PO bills require a higher level of approval.)
3. **Decision**: For a consulting engagement with time-and-materials billing, should you use three-way matching? (Answer: No — use two-way matching (PO + bill) because there is no physical receipt to match.)

## Related Articles

- [Vendor Bills and Payments](vendor-bills-and-payments.md)
- [Purchase Orders](purchase-orders.md)
- [What Is Procurement?](what-is-procurement.md)
- [Inventory Receiving](../inventory/receiving-inventory.md)

## Oracle References

- [Oracle NetSuite Help Center: Three-Way Matching](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Bill Matching](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)