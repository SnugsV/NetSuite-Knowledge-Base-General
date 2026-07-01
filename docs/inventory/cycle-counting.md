---
title: Cycle Counting
module: Inventory
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Cycle Counting

## Quick Summary

Cycle counting is an ongoing inventory verification process where a subset of items is counted on a regular schedule — daily, weekly, or monthly. Unlike a full physical inventory (which stops operations), cycle counting runs continuously with minimal disruption and provides more accurate inventory records over time.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

A physical inventory count requires stopping warehouse operations, counting every item, and reconciling discrepancies. Most companies do this once or twice a year. Cycle counting replaces the annual event with daily, targeted counts of specific items.

The goal of cycle counting is not just to find errors — it is to find the root causes of errors and eliminate them.

## Why Cycle Counting Works

| Physical Inventory | Cycle Counting |
|---|---|
| Annual or semi-annual event | Ongoing daily process |
| Stops warehouse operations | Runs during normal operations |
| Counts every item | Counts a subset of items |
| Finds errors after months of accumulation | Finds errors within days |
| No process improvement focus | Root cause analysis built in |
| Stressful, disruptive event | Routine part of operations |

## Cycle Counting Methods

### ABC Classification

Items are classified by value into categories:

| Class | Percentage of Items | Percentage of Value | Count Frequency |
|---|---|---|---|
| **A** | ~10% | ~70-80% | Monthly or weekly |
| **B** | ~20% | ~15-20% | Quarterly |
| **C** | ~70% | ~5-10% | Semi-annually or annually |

This focuses counting effort on the items that matter most to the business.

### Location-Based Counting

Count all items in a specific location or zone on a rotating schedule. Each location is counted at a set frequency regardless of the items stored there.

### Random Sample Counting

A random subset of items is counted daily. Statistical analysis of the results indicates overall inventory accuracy. If accuracy drops, count frequency increases.

### Exception-Based Counting

Items that have had recent transactions (high velocity), known issues, or frequent adjustments are counted more frequently. Items with stable, accurate records are counted less often.

## Setting Up Cycle Counts in NetSuite

Cycle counting requires the **Advanced Inventory** feature.

1. Enable Advanced Inventory (Setup > Company > Enable Features > Inventory)
2. Configure cycle count schedules for locations
3. Generate cycle count worksheets
4. Count items and record results
5. Review variances and approve adjustments

```
Transactions > Inventory > Cycle Counts
```

## The Cycle Counting Process

```
Schedule count for selected items
       ↓
Generate cycle count worksheet
       ↓
Warehouse team counts items
       ↓
Enter counted quantities in system
       ↓
System compares count to expected quantity
       ↓
Variance within tolerance? → Count is approved, no action needed
Variance exceeds tolerance? → Recount or investigate
       ↓
Confirmed variance → Inventory Adjustment
       ↓
Root cause analysis → Process improvement
```

## Variance Tolerances

Tolerances define how much a count can differ from the system before investigation is required.

| Item Type | Tolerance | Example |
|---|---|---|
| High-value (A class) | 0% — any variance investigated | $500 items must be exact |
| Mid-value (B class) | 2% or ±5 units | Acceptable range |
| Low-value (C class) | 5% or ±20 units | Larger tolerance acceptable |

Tolerances should be reviewed quarterly and adjusted based on actual accuracy trends.

## Root Cause Analysis

When a count discrepancy is found, ask:

- Was the item correctly received? (Receiving error)
- Was the item correctly fulfilled? (Fulfillment error)
- Was it put away in the wrong bin? (Putaway error)
- Was it stolen? (Theft)
- Was it damaged but not recorded? (Damage)
- Was the original count wrong? (System entry error)

Each root cause points to a specific process improvement.

## Business Example

A distributor with 10,000 SKUs uses ABC classification:

- **A items** (1,000 SKUs, 75% of value): 40 items counted daily (approximately monthly per item)
- **B items** (2,000 SKUs, 15% of value): 15 items counted daily (approximately quarterly per item)
- **C items** (7,000 SKUs, 10% of value): 10 items counted daily (approximately annually per item)

Total: 65 items counted daily, 20 minutes of warehouse time, continuous accuracy.

Result after 6 months: Inventory accuracy improves from 85% to 98%. Cycle count adjustments become smaller and less frequent.

## Common Mistakes

- **Counting without investigating variances**: If you adjust and move on, the root cause remains and the error recurs
- **ABC classification that is never updated**: Item values change. Review classifications quarterly
- **Counting too fast without accuracy**: Speed is important, but counting errors defeat the purpose
- **Not counting negative on-hand items**: Negative quantities indicate a problem — they should be counted immediately
- **No tolerance for human error**: Expecting 100% accuracy on high-volume counts is unrealistic. Set reasonable tolerances

## Best Practices

- Start cycle counting immediately — do not wait for perfect processes
- Use ABC classification to prioritize high-value items
- Investigate every variance above tolerance
- Track inventory accuracy percentage over time
- Report accuracy trends to management monthly
- Train counters on proper counting technique
- Integrate cycle counting with bin management for location-specific counting

## Knowledge Check

1. A company with 50,000 SKUs does one physical count per year. What is a better approach? (Answer: Cycle counting — count valuable items monthly, others quarterly or annually.)
2. **Scenario**: An A-class item consistently has count discrepancies. What should you investigate? (Answer: The process around that item — receiving, putaway, picking, or fulfillment.)
3. **True/False**: If a cycle count variance is within tolerance, no adjustment is needed. (Answer: True — the variance is within acceptable range.)

## Related Articles

- [Physical Inventory](physical-inventory.md)
- [Inventory Adjustments](inventory-adjustments.md)
- [Replenishment](replenishment.md)
- [Inventory Locations](inventory-locations.md)
- [Saved Searches: Inventory Reporting](../saved-searches/README.md)

## Oracle References

- [Oracle NetSuite Help Center: Cycle Counting](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Advanced Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)