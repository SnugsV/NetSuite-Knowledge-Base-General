---
title: Landed Cost
module: Inventory
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Landed Cost

## Quick Summary

Landed cost is the total cost of acquiring inventory, including not just the purchase price but also freight, insurance, customs duties, brokerage fees, and other charges. Accurately capturing landed cost is essential for correct inventory valuation and margin analysis.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Business Question

"After freight, duties, and insurance, what did this inventory actually cost — and what is my true margin?"

## Overview

The purchase price on an invoice is rarely the full cost of getting inventory into the warehouse. A shipment from overseas may include ocean freight, customs duties, port handling, trucking, insurance, and broker fees. Each of these costs should be included in the inventory value to accurately reflect the true acquisition cost.

## What Makes Up Landed Cost

| Cost Component | Example |
|---|---|
| **Purchase Price** | $10,000 — the vendor invoice |
| **Ocean Freight** | $1,200 — shipping from manufacturing port |
| **Insurance** | $200 — cargo insurance |
| **Customs Duties** | $800 — import tariffs |
| **Port Handling** | $300 — unloading and processing |
| **Inland Trucking** | $400 — port to warehouse |
| **Broker Fees** | $150 — customs clearance |
| **Total Landed Cost** | $12,850 |

Without landed cost allocation, the inventory would be valued at $10,000, and the additional $2,850 would be expensed — understating inventory asset and overstating COGS.

## When to Use Landed Cost

| Situation | Recommendation |
|---|---|
| International purchases with freight/duties | Required for accurate inventory valuation |
| Domestic purchases with significant freight | Recommended when freight > 5% of item cost |
| High-value, low-volume purchases | Worth the allocation effort |
| Low-value, high-volume purchases | May not justify the overhead |
| Dropship purchases | Landed cost typically not applicable |

## Allocation Methods

Landed costs must be allocated to the items in the shipment. Common allocation bases:

| Method | How It Works | Best For |
|---|---|---|
| **By Value** | Costs allocated proportionally to item value | Most common — fair and simple |
| **By Weight** | Costs allocated by item weight | Freight-heavy shipments |
| **By Volume** | Costs allocated by item volume | Bulky items that consume container space |
| **By Quantity** | Costs allocated equally per unit | Homogeneous items in a shipment |
| **By Custom Rule** | User-defined allocation percentage | Complex shipments with mixed allocation needs |

## Landed Cost in NetSuite

NetSuite supports landed cost through the **Landed Cost** feature (requires enablement).

Setup path:
```
Setup > Accounting > Landed Cost > Set Up Landed Cost
```

The landed cost process:

1. Create or import a purchase order and item receipt
2. Enter the additional costs (freight, duty, etc.) as landed cost transactions
3. Allocate the costs to the received items
4. NetSuite adjusts the inventory value to include the landed costs

## Impact on Cost and Margin

Landed cost affects three financial metrics:

| Metric | Without Landed Cost | With Landed Cost |
|---|---|---|
| **Inventory Value** | $10,000 | $12,850 |
| **COGS (per unit)** | $10.00 | $12.85 |
| **Gross Margin (at $20 sale)** | 50% | 35.75% |

Reporting margin without landed cost overstates profitability by 14 percentage points in this example.

## Timing of Landed Cost Entry

Landed costs can be entered:

- **At receipt**: Most accurate, but requires all cost information to be available when goods arrive
- **After receipt**: Common when freight invoices arrive after the goods. An adjustment is posted to update inventory value.
- **At period end**: Least accurate — costs are estimated or allocated retroactively

The timing affects inventory valuation accuracy between receipt and the cost entry.

## Business Example

A furniture importer receives a container from Vietnam containing 200 chairs at $50 each ($10,000 total). Additional costs:

- Ocean freight: $2,000
- Customs duties (12%): $1,200
- Port handling: $500
- Inland trucking: $300
- Total additional: $4,000

Using value-based allocation:

- Each chair's purchase price is $50
- Total additional cost per chair: $4,000 / 200 = $20
- Landed cost per chair: $70

Without landed cost: The chairs are valued at $50. COGS is $50. Margin on a $100 sale: 50%.

With landed cost: The chairs are valued at $70. COGS is $70. True margin on a $100 sale: 30%.

## Common Costly Mistakes

- **Not capturing landed cost at all**: The most common mistake. Freight and duties are expensed, inventory is undervalued, and margins appear higher than they are
- **Inconsistent allocation methods**: Changing allocation methods between shipments creates inconsistent inventory valuations
- **Timing mismatches**: Entering costs long after the receipt creates inventory value adjustments that are difficult to reconcile
- **Not reviewing landed cost reports**: Landed cost should be reviewed monthly to verify costs were captured
- **Over-allocating**: Assigning more cost than the total shipment value can overstate inventory

## Best Practices

- Enable landed cost if any significant buying costs exist beyond the purchase price
- Use value-based allocation as the default method
- Enter landed costs as close to receipt as possible
- Reconcile landed cost accounts monthly
- Use Saved Searches to identify receipts without landed costs
- Train purchasing staff to capture all cost components at the time of ordering

## Knowledge Check

1. A shipment has $5,000 in freight costs for 1,000 units. What is the landed cost impact per unit? (Answer: $5,000 / 1,000 = $5.00 per unit added to the purchase price.)
2. **Decision**: Your company buys locally with free delivery. Do you need landed cost? (Answer: No — no additional costs beyond the purchase price.)
3. **Scenario**: A freight invoice arrives 3 weeks after the goods. How do you handle the timing? (Answer: Enter the landed cost as an adjustment after receipt. NetSuite will update the inventory value retroactively.)

## Related Articles

- [Costing Methods](costing-methods.md)
- [Receiving Inventory](receiving-inventory.md)
- [Inventory Concepts](../inventory-concepts.md)
- [Multi-Location Strategy](multi-location-strategy.md)

## Oracle References

- [Oracle NetSuite Help Center: Landed Cost](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Landed Cost Allocation](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)