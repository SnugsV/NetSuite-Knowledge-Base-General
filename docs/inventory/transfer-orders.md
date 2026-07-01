---
title: Transfer Orders
module: Inventory
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Transfer Orders

## Quick Summary

A Transfer Order is a multi-step inventory movement between locations with tracking at each stage — pending fulfillment, in transit, and received. Unlike a basic inventory transfer (single-step, immediate), Transfer Orders provide visibility into inventory that is moving between warehouses.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

When inventory moves between two locations that have different management, tracking, or accounting requirements, a Transfer Order provides the necessary control. It records the movement through definable stages so that each location can manage its part of the process independently.

## When to Use Transfer Orders vs. Basic Transfers

| Situation | Use |
|---|---|
| Both locations under same manager, immediate move | Basic Transfer |
| Warehouse A ships to Warehouse B with separate teams | Transfer Order |
| You need to know what is in transit | Transfer Order |
| The move requires pick, pack, and ship workflow | Transfer Order |
| Source and destination use different average costs | Transfer Order |
| Simple, immediate stock rebalance | Basic Transfer |

## The Transfer Order Workflow

```
Transfer Order created
       ↓
Status: Pending
       ↓
Source location picks and ships items
       ↓
Status: Shipped / In Transit
       ↓
Items are in transit (tracked in system)
       ↓
Destination location receives items
       ↓
Status: Received
       ↓
Quantities updated at both locations
```

## Creating a Transfer Order

```
Transactions > Inventory > Transfer Orders > New
```

Fields to configure:

| Field | Purpose |
|---|---|
| **Source Location** | Where the inventory is moving from |
| **Destination Location** | Where the inventory is moving to |
| **Items** | What is being transferred |
| **Quantities** | How many units |
| **Date** | When the transfer was initiated |

## Fulfilling a Transfer Order

The source location fulfills the Transfer Order when items are picked and shipped. This:

- Decreases inventory at the source location
- Increases In Transit quantity
- Records the items as shipped
- Changes status to Shipped/In Transit

```
Transactions > Inventory > Transfer Orders > Fulfill
```

## Receiving a Transfer Order

The destination location receives the Transfer Order when items arrive. This:

- Decreases In Transit quantity
- Increases inventory at the destination location
- Records the items as received
- Changes status to Received

```
Transactions > Inventory > Transfer Orders > Receive
```

## In-Transit Inventory

In-transit inventory is a separate quantity field. It represents inventory that has left the source location but has not yet arrived at the destination. This is important because:

- The source location should not sell inventory that is in transit
- The destination location should not sell it until it is received
- In-transit inventory should be visible to planners for replenishment decisions

## Cost Implications

When transferring between locations with different average costs, a cost variance may be recorded.

**Example**:
- Source location average cost: $10.00
- Destination location average cost: $10.50
- Transferring 100 units: The destination records a cost variance of $50 (100 × $0.50)

This variance is recorded as an adjustment to the inventory value and affects the general ledger.

## Business Example

A company with warehouses in Chicago and Atlanta needs to rebalance stock. Chicago has excess of SKU CHR-100 (200 units) but Atlanta is running low (20 units). The target is 100 units at each location.

1. **Create Transfer Order**: 80 units from Chicago to Atlanta
2. **Chicago fulfills**: Warehouse team picks 80 units, ships via truck. Chicago inventory decreases by 80. Status: In Transit.
3. **Transit**: The load is on the road for 3 days. NetSuite shows 80 units In Transit.
4. **Atlanta receives**: Truck arrives, team verifies quantity, receives the Transfer Order. Atlanta inventory increases by 80. In Transit decreases by 80.
5. **Complete**: Both locations now have balanced stock.

## Common Mistakes

- **Using a Basic Transfer when a Transfer Order is needed**: If tracking matters, use Transfer Orders. Basic Transfers have no tracking.
- **Not fulfilling before receiving**: The source must fulfill the Transfer Order before the destination can receive it. Skipping steps breaks the workflow.
- **Forgetting in-transit inventory**: In-transit inventory is real inventory — it just has not arrived yet. Treat it as committed at the source and expected at the destination.
- **Not reconciling in-transit balances**: In-transit quantities should be reviewed weekly and aged items investigated. A Transfer Order that has been in transit for 30 days may be lost.

## Best Practices

- Use Transfer Orders for all inter-warehouse movements where separate teams are involved.
- Review in-transit inventory weekly and investigate aged items.
- Create Transfer Orders with realistic dates based on shipping schedules.
- Communicate scheduled transfers to both warehouse teams in advance.
- Use Saved Searches to monitor open Transfer Orders by age.

## Knowledge Check

1. A Transfer Order is created but not yet fulfilled. Where is the inventory? (Answer: Still at the source location.)
2. **Scenario**: A Transfer Order shows "Shipped" status for two weeks. What should you investigate? (Answer: Whether the shipment was received at the destination or lost in transit.)
3. **True/False**: A Basic Transfer can be used instead of a Transfer Order when the inventory stays in the same building. (Answer: True — if no tracking or multi-step workflow is needed.)

## Related Articles

- [Inventory Locations](inventory-locations.md)
- [Fulfilling Orders](fulfilling-orders.md)
- [Receiving Inventory](receiving-inventory.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Saved Searches: In-Transit Monitoring](../saved-searches/real-world-business-examples.md)

## Oracle References

- [Oracle NetSuite Help Center: Transfer Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Inventory Transfer Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Basic Inventory Transfers](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)