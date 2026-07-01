---
title: Inventory Adjustments
module: Inventory
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Inventory Adjustments

## Quick Summary

An Inventory Adjustment transaction increases or decreases the quantity and value of inventory on hand. Adjustments are used to correct discrepancies, record damage or theft, write off obsolete inventory, and reconcile counts. Every adjustment has both an operational and a financial impact.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Inventory records should reflect physical reality. When they do not — due to miscounts, damage, theft, shipping errors, or data entry mistakes — an Inventory Adjustment brings the system back into alignment.

Unlike a receipt or fulfillment (which are linked to purchase orders or sales orders), an adjustment is a standalone transaction. It corrects inventory without a corresponding order.

## When to Use Inventory Adjustments

| Situation | Example |
|---|---|
| **Cycle count discrepancy** | You count 95 units but the system shows 100 |
| **Damaged goods** | A fork lift damages 3 units beyond repair |
| **Theft or shrinkage** | 5 units are missing from a retail location |
| **Obsolete inventory write-off** | 50 units of a discontinued product are worthless |
| **Data entry correction** | A receipt was entered for 100 units but only 90 were received |
| **Sample or promotional use** | 10 units were given to a customer as a sample |

## The Adjustment Transaction

```
Transactions > Inventory > Adjust Inventory
```

Each adjustment records:

| Field | Purpose |
|---|---|
| **Location** | Where the inventory is located |
| **Item** | What is being adjusted |
| **Quantity** | The change (+ adds, - subtracts) |
| **Adjustment Account** | The GL account for the offset entry |
| **Date** | When the adjustment occurred |
| **Memo** | Reason for the adjustment |

## Accounting Impact

Every adjustment has an accounting entry:

**Increasing inventory (positive adjustment)**:
| Account | Debit/Credit |
|---|---|
| **Inventory Asset** | Debit |
| **Adjustment Account** | Credit |

**Decreasing inventory (negative adjustment)**:
| Account | Debit/Credit |
|---|---|
| **Adjustment Account** | Debit |
| **Inventory Asset** | Credit |

The **Adjustment Account** determines how the offset is classified. Common choices:

| Adjustment Account | Use |
|---|---|
| **Inventory Shrinkage** | Theft, unexplained losses |
| **Damaged Goods Expense** | Items that cannot be sold |
| **Obsolete Inventory Write-Off** | Discontinued or expired items |
| **Cost of Goods Sold** | Small adjustments that go to COGS |
| **Inventory Variance** | General discrepancy account |

Choosing the right account matters for financial reporting. Inventory shrinkage shows one type of expense; obsolete inventory shows another.

## Adjustment vs. Correction

Not every inventory error needs an adjustment. If the error is in a source transaction (receipt, fulfillment, transfer), correct the source transaction instead.

| Situation | Best Action |
|---|---|
| Item Receipt entered with wrong quantity | Correct the Item Receipt |
| Item Fulfillment shipped wrong item | Correct the Item Fulfillment |
| Physical count differs from system | Inventory Adjustment |
| Damage discovered after receipt | Inventory Adjustment |
| Obsolete inventory needs removal | Inventory Adjustment |

## Reason Codes

Best practice is to require reason codes for every adjustment. Reason codes help:
- Categorize adjustments for reporting
- Identify patterns (e.g., recurring shrinkage in one location)
- Support audit trails

NetSuite does not have built-in reason codes for adjustments by default, but they can be added through custom fields or custom segments.

## Approval Workflows

For high-value adjustments, consider an approval workflow:

| Threshold | Approval Required |
|---|---|
| Any adjustment | No approval |
| Adjustment > $500 | Supervisor approval |
| Adjustment > $5,000 | Manager approval |
| Adjustment > $25,000 | Controller approval |

Workflows can be configured in NetSuite to enforce these thresholds automatically.

## Business Example

During a monthly cycle count, a warehouse team finds that SKU BOLT-100 shows 5,000 units in the system but only 4,850 are physically present — 150 units are missing.

1. The team recounts and confirms 4,850
2. They search for misplaced stock — none found
3. An Inventory Adjustment is created:
   - Item: BOLT-100
   - Location: Chicago Warehouse
   - Quantity: -150
   - Adjustment Account: Inventory Shrinkage
   - Memo: "Count discrepancy — 150 units missing, cause unknown"
4. The system reduces On Hand to 4,850
5. Inventory Asset is reduced by 150 × average cost
6. Inventory Shrinkage expense increases by the same amount

## Common Mistakes

- **Using adjustments to fix transaction errors**: If the error is in the original transaction (receipt, fulfillment), correct the transaction — not the inventory
- **Not documenting the reason**: An adjustment without a memo is an audit risk. Always explain why the adjustment was made
- **Using the wrong adjustment account**: Putting shrinkage into COGS hides operational losses. Use the appropriate account
- **Adjusting without approval**: For significant quantities or values, require authorization before adjusting
- **Adjusting the same item repeatedly**: Frequent adjustments to the same item indicate a process problem, not a counting problem

## Best Practices

- Require a memo on every adjustment explaining the reason
- Use reason codes or categories for tracking adjustment patterns
- Set up approval workflows for high-value adjustments
- Investigate items that require frequent adjustments — the root cause may be a process issue
- Review adjustment reports monthly to identify trends
- Train warehouse staff on what constitutes an adjustment vs. a transaction correction

## Knowledge Check

1. You discover 10 units of an item were damaged when a shelf collapsed. What transaction do you use? (Answer: Inventory Adjustment with a negative quantity.)
2. **Scenario**: An Item Receipt was entered for 200 units but only 180 were actually received. Should you create an adjustment to fix this? (Answer: No — correct the Item Receipt itself.)
3. **True/False**: All inventory adjustments affect the general ledger. (Answer: True — every adjustment changes both quantity and value.)

## Related Articles

- [Cycle Counting](cycle-counting.md)
- [Physical Inventory](physical-inventory.md)
- [Receiving Inventory](receiving-inventory.md)
- [Returns Processing](returns-processing.md)
- [Inventory Concepts](inventory-concepts.md)
- [Saved Searches: Inventory Reporting](../saved-searches/README.md)

## Oracle References

- [Oracle NetSuite Help Center: Inventory Adjustments](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Adjusting Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)