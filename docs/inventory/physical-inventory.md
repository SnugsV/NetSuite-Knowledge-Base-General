---
title: Physical Inventory
module: Inventory
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Physical Inventory

## Quick Summary

A physical inventory is a complete count of all inventory items at a location, performed to reconcile system quantities with physical stock. Physical inventories are typically required for financial reporting and are often conducted annually.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Unlike cycle counting (which counts a subset of items continuously), a physical inventory counts every item at a specific location. It is a full reconciliation event that typically requires freezing transactions during the count period.

## When Physical Inventory Is Required

| Reason | Frequency |
|---|---|
| **Annual financial audit** | Required for audited financial statements |
| **Regulatory compliance** | As required by industry or jurisdiction |
| **New system implementation** | Baseline counts when going live |
| **Major discrepancy investigation** | When cycle counts suggest systemic issues |
| **Inventory conversion** | Changing valuation methods or systems |

## Physical Inventory vs. Cycle Counting

| Dimension | Physical Inventory | Cycle Counting |
|---|---|---|
| **Scope** | All items | Subset of items |
| **Frequency** | Annually (or as needed) | Continuous |
| **Operations impact** | May freeze transactions | Minimal disruption |
| **Accuracy goal** | Snap-shot verification | Ongoing improvement |
| **Root cause analysis** | Limited | Built into the process |

## The Physical Inventory Process

### Phase 1: Planning

- Determine the count date and time
- Decide whether to freeze operations (lock inventory) during the count
- Prepare count worksheets (item lists by location)
- Train counters on procedures
- Communicate the schedule to all affected departments

### Phase 2: Pre-Count

- Stop receiving and fulfilling inventory (freeze period)
- Process all outstanding transactions before the freeze
- Clean up unprocessed receipts and fulfillments
- Organize and label inventory for easy counting

### Phase 3: Counting

- Count teams work in pairs (one counts, one records)
- Count items in location order to avoid double-counting or missing items
- Record counts on worksheets or mobile devices
- Tag counted items to prevent re-counting

### Phase 4: Entry and Reconciliation

- Enter counted quantities into NetSuite
- System compares count to expected (book) quantity
- Generate variance report
- Investigate variances

### Phase 5: Adjustment and Approval

- Create Inventory Adjustments for confirmed variances
- Obtain required approvals for significant adjustments
- Update inventory records
- Document the results

### Phase 6: Post-Count

- Reconcile adjustment accounts
- Review variance patterns for process improvements
- Update cycle count frequencies based on findings
- Resume normal operations

## Creating a Physical Count in NetSuite

NetSuite supports physical count worksheets and count entry:

```
Transactions > Inventory > Create Physical Count Worksheet
```

The worksheet lists all items at selected locations and includes the current book quantity. Counters enter the physical quantity, and the system calculates variances.

## Accounting Impact

Physical inventory adjustments affect the financial statements:

- **Overstated inventory** (book > physical): Decrease inventory asset, recognize expense
- **Understated inventory** (book < physical): Increase inventory asset, reduce expense

The net impact is typically recorded as an adjustment to Cost of Goods Sold or a separate inventory adjustment account.

## Business Example

A retailer conducts its annual physical inventory on January 1. The process:

1. **December 31**: Last shipments received, last orders fulfilled. Inventory is frozen at midnight.
2. **January 1, 8:00 AM**: Count teams begin. The warehouse is divided into 20 zones. Each zone is counted by a pair of employees.
3. **January 1, 4:00 PM**: Counting is complete. 15,000 SKUs counted.
4. **Variance summary**: 92% of items match system quantities exactly. 8% have variances totaling $12,000 (0.8% of inventory value).
5. **Adjustments**: Variances over $500 are investigated. Root causes identified: receiving errors (40%), fulfillment errors (35%), theft (15%), data entry (10%).
6. **Resolution**: Inventory adjustments are entered. Adjusting entries are reviewed by the controller.

## Common Mistakes

- **Not freezing transactions during the count**: Transactions during the count period create discrepancies that are impossible to reconcile
- **Counting without pre-count preparation**: Unprocessed receipts and fulfillments create phantom discrepancies
- **Not training counters**: Untrained counters miscount, miss items, or record quantities incorrectly
- **Rushing the count**: A rushed physical inventory produces unreliable results
- **Not investigating variances**: Adjusting without understanding root causes guarantees the same variances next year

## Best Practices

- Perform cycle counting throughout the year to minimize the physical count surprise
- Freeze inventory for the shortest practical period (ideally 24-48 hours)
- Use pre-printed count worksheets with item locations for each zone
- Count in pairs (one person counts, one person records)
- Investigate all variances above a materiality threshold before adjusting
- Reconcile all transactions up to the freeze moment before starting the count
- Follow up the physical count with a root cause analysis meeting

## Knowledge Check

1. Your physical count shows 950 units but the system shows 1,000. The items cost $5 each. What is the journal entry? (Answer: Debit Adjustment Account $250, Credit Inventory Asset $250.)
2. **Scenario**: During the physical count, a truck arrives with a delivery. Should you receive it? (Answer: Only if the inventory freeze period has ended. If still frozen, the truck should wait or the receipt should be dated after the freeze.)
3. **True/False**: A physical inventory eliminates the need for cycle counting. (Answer: False — they complement each other. Cycle counting improves ongoing accuracy; physical inventory provides the annual reconciliation.)

## Related Articles

- [Cycle Counting](cycle-counting.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Inventory Concepts](inventory-concepts.md)
- [Inventory Valuation](inventory-valuation.md) (future)
- [Saved Searches: Inventory Reporting](../saved-searches/README.md)

## Oracle References

- [Oracle NetSuite Help Center: Physical Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Physical Count Worksheet](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)