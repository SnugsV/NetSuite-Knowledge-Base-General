---
title: Replenishment
module: Inventory
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Replenishment

## Quick Summary

Replenishment is the process of ensuring inventory is available when needed — ordering the right items, in the right quantities, at the right time. NetSuite supports reorder point-based replenishment and suggested purchase orders to automate the process.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Running out of stock costs money — lost sales, expedited shipping, and customer dissatisfaction. Holding too much stock also costs money — storage, insurance, and capital tied up in inventory. Replenishment is the balancing act between these two risks.

NetSuite's replenishment features help automate the decision of when and how much to order.

## Replenishment Methods

### Reorder Point

The most common method. Each item has a **Reorder Point** (minimum quantity before reordering) and a **Preferred Stock Level** (target quantity after replenishment).

When On Hand + On Order falls below the Reorder Point, NetSuite suggests a purchase order.

```
Example:
  Reorder Point: 100 units
  Preferred Stock Level: 500 units
  Current On Hand: 80 units (below reorder point)
  Suggested Order: 420 units (Preferred - On Hand = 500 - 80)
  But wait — On Order is 50 units
  Suggested Order: 370 units (500 - 80 - 50)
```

### Demand-Based Replenishment

For items with variable demand, historical consumption data is used to calculate reorder points. This is more accurate than fixed reorder points but requires data analysis.

### Time-Phased Replenishment

Used for seasonal or planned demand. Orders are scheduled based on expected future demand rather than current stock levels.

### Min-Max Replenishment

A simplified method where items are ordered up to a maximum quantity whenever the current quantity falls below a minimum.

## Setting Reorder Parameters

Each inventory item can have reorder parameters configured on the item record:

| Field | Purpose |
|---|---|
| **Reorder Point** | The quantity at which a reorder is triggered |
| **Preferred Stock Level** | The target quantity to maintain |
| **Lead Time** | Days between placing and receiving the order |
| **Safety Stock** | Buffer stock for demand variability |
| **Maximum Quantity** | The most you want to hold (space or cash constraint) |

## Suggested Purchase Orders

NetSuite can generate suggested purchase orders based on reorder parameters:

```
Transactions > Purchasing > Create Suggested POs
```

The suggested PO considers:

- Current On Hand quantity
- Open purchase orders (On Order)
- Open sales orders (Committed)
- Reorder Point and Preferred Stock Level
- Lead time
- Item safety stock

The purchasing team reviews the suggestions, adjusts quantities as needed, and creates purchase orders.

## Safety Stock

Safety stock is extra inventory held to protect against uncertainty:

| Uncertainty Source | Safety Stock Purpose |
|---|---|
| **Demand variability** | Customers order more than expected |
| **Supply variability** | Vendor delivers late or short |
| **Lead time variability** | Transit time is longer than expected |
| **Quality variability** | Some units arrive damaged or defective |

Safety stock is calculated based on historical demand variability and desired service level.

## Service Level Trade-Off

| Service Level | Safety Stock | Stockout Risk | Inventory Cost |
|---|---|---|---|
| 95% | Moderate | Low | Moderate |
| 98% | Higher | Very low | Higher |
| 99.5% | Highest | Minimal | Significantly higher |

The last 1-2% of service level often doubles safety stock requirements. The optimal point depends on the item's profit margin and the cost of a stockout.

## Slow-Moving and Dead Stock

Replenishment is about buying the right quantities. For slow-moving or dead stock, the right order quantity may be zero.

Identify slow-moving items:

- **Saved Search**: Items with no sales in 6 months
- **Action**: Review for discontinuation, markdown, or write-off
- **Prevent**: Set appropriate reorder points — do not replenish dead stock

## Business Example

A distributor manages 5,000 SKUs using reorder point replenishment:

- SKU CHR-100: Reorder Point 50, Preferred Stock 200, Lead Time 14 days
- Current On Hand: 45, On Order: 0
- Reorder triggered: Yes (45 < 50)
- Suggested order: 155 (200 - 45)
- Purchasing reviews and orders 155. The PO states 155 units at $15 each.
- 14 days later: Items received, stock is now 200.

## Common Mistakes

- **Setting reorder points without lead time consideration**: If lead time is 30 days and the reorder point covers only 14 days of demand, stockouts are guaranteed
- **Not updating reorder points after demand changes**: Reorder points set a year ago are likely wrong. Review quarterly
- **Ignoring On Order quantities**: The system accounts for On Order, but manual processes may not. Always check what is already coming in
- **Over-relying on suggested orders**: The system suggests based on rules. Human judgment is needed for seasonal demand, promotions, and supplier constraints
- **Not distinguishing between replenishment and new-product buying**: New products have no sales history. Reorder points do not apply until demand patterns are established

## Best Practices

- Review reorder points quarterly based on actual demand
- Calculate safety stock using historical demand variability
- Use Suggested Purchase Orders as a starting point, not a final decision
- Monitor stockout frequency by item — frequent stockouts indicate reorder points that are too low
- Monitor inventory turns — low turns indicate reorder points that are too high
- Use Saved Searches to identify items below reorder point weekly
- Automate the suggested PO review process with a daily or weekly schedule
- Segment inventory by velocity (fast, medium, slow) and set different replenishment strategies

## Knowledge Check

1. An item has a reorder point of 200, preferred stock of 800, current On Hand of 150, and On Order of 100. What is the suggested order quantity? (Answer: 550 — 800 - 150 - 100 = 550.)
2. **Scenario**: A high-margin item stockout costs $5,000 in lost profit per occurrence. How much safety stock is justified? (Answer: Compare the cost of carrying extra stock to the cost of stockouts. If carrying 100 extra units costs $500/year and prevents 2 stockouts/year, the savings are $9,500.)
3. **True/False**: Reorder points should be updated when a vendor changes lead time. (Answer: True — lead time directly affects how early the reorder point should trigger.)

## Related Articles

- [Receiving Inventory](receiving-inventory.md)
- [Cycle Counting](cycle-counting.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Inventory Concepts](inventory-concepts.md)
- [Saved Searches: Low Stock Alerts](../saved-searches/real-world-business-examples.md)
- [Purchase Orders](../purchasing/README.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Replenishment](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Reorder Point Calculations](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)