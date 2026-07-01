---
title: Multi-Location Strategy
module: Inventory
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Multi-Location Strategy

## Quick Summary

Multi-location inventory management distributes stock across multiple warehouses, stores, or distribution centers. The strategy for how inventory is allocated, transferred, and replenished across locations has significant operational and financial implications.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Business Question

"How should I structure my inventory locations to minimize cost while maximizing service levels?"

## Overview

A company with one warehouse makes simple inventory decisions: receive it, store it, ship it. A company with multiple locations must decide which inventory goes where, when to transfer between locations, and how to fulfill orders from the optimal location.

## Location Strategies

### Centralized Distribution

One central warehouse serves all customers. Regional locations hold minimal or no stock.

| Pros | Cons |
|---|---|
| Lower total inventory | Higher shipping costs to remote customers |
| Single point of inventory management | Longer delivery times |
| Fewer transfers needed | Single point of failure |

### Decentralized Distribution

Multiple regional warehouses each hold stock for their region.

| Pros | Cons |
|---|---|
| Faster delivery to regional customers | Higher total inventory (safety stock at each location) |
| Lower shipping costs | More complex replenishment |
| Regional redundancy | More transfers between locations |

### Hub-and-Spoke

A central hub holds the majority of stock. Regional spokes hold fast-moving items and replenish from the hub.

| Pros | Cons |
|---|---|
| Balance of inventory cost and service levels | More complex logistics |
| Fast movers available locally | Hub-to-spoke transfer management |
| Slow movers at central location | Requires accurate demand forecasting |

### Dropship

No locations hold stock. Vendors ship directly to customers.

| Pros | Cons |
|---|---|
| Zero inventory carrying cost | No control over fulfillment quality |
| Unlimited product catalog | Higher per-unit cost |
| No warehouse required | Complex return management |

## Location Setup in NetSuite

Each location requires:

1. **Location record** — Created at Setup > Company > Locations
2. **Location type** — Warehouse, Store, Dock, etc.
3. **Address and contact information**
4. **Parent location** — For hierarchical structures
5. **Subsidiary assignment** — For OneWorld accounts
6. **Default bin setup** — If using bin management

## Inventory Allocation Decisions

| Decision | Question to Answer |
|---|---|
| **Safety stock by location** | How much buffer should each location hold? |
| **Replenishment source** | Does each location order independently, or from a central hub? |
| **Order fulfillment logic** | Which location fulfills a customer order closest to the customer? |
| **Transfer triggers** | When should inventory be moved between locations? |
| **Slow mover consolidation** | Should slow-moving items be centralized at one location? |

## Cost Implications

Multi-location inventory changes cost dynamics:

- **Average cost by location**: Each location may have different average costs for the same item
- **Transfer costs**: Moving inventory between locations incurs freight and handling costs
- **Location-level COGS**: Cost of goods sold can differ by fulfillment location
- **Tax implications**: Inventory stored in different states or countries may have different tax treatment

## Business Example

A national distributor with 3 warehouses (Northeast, Midwest, Southwest) serves 10,000 customers.

**Challenge**: The Northeast warehouse frequently stocks out of a fast-moving item while the Midwest has excess. The item must be transferred — incurring freight costs and 3 days of transit — or the Northeast customer gets a delayed fulfillment.

**Solution**: Implement hub-and-spoke with the Midwest as the primary hub (largest warehouse, central location), and Northeast/Southwest as spokes holding 2 weeks of demand for fast movers. Transfer slow movers from hub to customer directly.

**Result**: 95% fulfillment from nearest location. Transfers reduced by 60%. Customer satisfaction improved.

## Common Costly Mistakes

- **Duplicating inventory at every location**: Carrying the same items at every location multiplies safety stock and increases carrying costs
- **No fulfillment optimization logic**: Without rules for which location ships which orders, fulfillment defaults may be suboptimal
- **Ignoring location-level costs**: Different locations may have different rent, labor, and tax costs
- **Over-transferring**: Frequent small transfers increase freight cost. Consolidate into larger, less frequent transfers
- **Not consolidating slow movers**: Slow-moving items should be centralized — carrying them at multiple locations wastes capital

## Best Practices

- Segment inventory by velocity: Fast movers at multiple locations, slow movers centralized
- Set location-specific reorder points based on local demand
- Review location inventory levels weekly and rebalance as needed
- Use fulfillment optimization rules to pick the optimal fulfillment location
- Centralize slow-moving and high-value inventory at one location
- Monitor inventory turns by location and investigate locations with significantly different turns

## Knowledge Check

1. A company with 5 regional warehouses carries the same 10,000 SKUs at each location. What is the primary issue? (Answer: Excess safety stock — slow movers are duplicated 5× with no benefit.)
2. **Decision**: Which locations should hold safety stock for a fast-moving item with 2-day delivery expectations? (Answer: Regional locations close to demand centers.)
3. **Scenario**: A central hub ships to 3 regional spokes. A spoke needs 500 units. The hub sends them via transfer order. Which document type handles the hub-to-spoke movement? (Answer: Transfer Order.)

## Related Articles

- [Inventory Locations](../inventory-locations.md)
- [Transfer Orders](transfer-orders.md)
- [Replenishment](../replenishment.md)
- [Cycle Counting](cycle-counting.md)
- [Costing Methods](costing-methods.md)
- [Warehouse Management](../warehouse/README.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Multi-Location Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Location Setup](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)