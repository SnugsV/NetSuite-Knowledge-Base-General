---
title: Work in Progress
module: Manufacturing
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Work in Progress

## Quick Summary

Work in Progress (WIP) is the value of components and labor that have been issued to production but have not yet been completed as finished goods. WIP is a balance sheet account that bridges raw material inventory and finished goods inventory.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Business Question

"What is the value of our partially completed production?"

## Overview

When components are issued to a work order, their value moves from raw material inventory into the WIP account. As labor and overhead are added, WIP increases. When the work order is completed, the total cost transfers from WIP to finished goods inventory.

## The WIP Flow

```
Raw Materials (Inventory Asset)
    ↓  Component Issue
WIP (Manufacturing)
    ↓  Labor, Overhead added during production
WIP (Manufacturing) — increased
    ↓  Work Order Build
Finished Goods (Inventory Asset)
    ↓  Sale
COGS
```

## WIP Accounting

| Transaction | Debit | Credit |
|---|---|---|
| Issue components to work order | WIP Asset | Inventory Asset |
| Add labor cost | WIP Asset | Accrued Payroll |
| Add overhead | WIP Asset | Overhead Absorption |
| Complete work order | Inventory Asset (FG) | WIP Asset |

## Why WIP Matters

- **Balance sheet accuracy**: WIP represents real economic value
- **Cost tracking**: WIP captures actual production cost
- **Variance analysis**: Compare actual WIP to standard cost
- **Inventory valuation**: WIP is part of total inventory value

## Common Customer Questions

**Q**: Why is WIP showing an incorrect balance? **Records to Inspect**: Open work orders, issued but unbuilt components, work orders completed but not closed, component adjustment transactions.

**Q**: WIP has a negative balance. What does this mean? **Common Causes**: Backflushing errors, components issued after build completion, inventory adjustments affecting WIP accounts.

## Related Articles

- [Component Issuing](component-issuing.md)
- [Manufacturing Costing](manufacturing-costing.md)
- [Backflushing](backflushing.md)
- [Work Orders](work-orders.md)

## Oracle References

- [Oracle NetSuite Help Center: WIP](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)