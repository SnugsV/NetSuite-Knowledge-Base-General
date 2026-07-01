---
title: Backflushing
module: Manufacturing
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Backflushing

## Quick Summary

Backflushing automatically consumes components from inventory when a work order is built. Instead of manually issuing each component, the system calculates what should have been consumed based on the BOM and the build quantity, and creates the issue transactions automatically.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Business Question

"How do I consume components during high-volume production without manual entry?"

## Overview

In low-volume manufacturing, each component issue is manually recorded. In high-volume manufacturing, manual entry becomes a bottleneck. Backflushing solves this by assuming that if you built 100 chairs, you consumed exactly 100 frames, 200 meters of fabric, and so on — as defined by the BOM.

## When to Use Backflushing

| Use Backflushing When | Don't Use Backflushing When |
|---|---|
| High-volume repetitive manufacturing | Low-volume, high-value production |
| Stable, accurate BOMs | Frequent BOM changes |
| Consistent component consumption | Variable yield or scrap rates |
| Automated production processes | Manual, custom production |
| Cost of tracking individual issues > benefit | Component-level traceability required |

## How Backflushing Works

```
Step 1: Work order built for 100 units of Chair
Step 2: System checks BOM — each chair needs 1 frame, 2m fabric
Step 3: System calculates: 100 × 1 frame = 100 frames consumed
                             100 × 2m fabric = 200m consumed
Step 4: System creates component issue transactions automatically
Step 5: Inventory reduced by consumed quantities
Step 6: WIP increased by component value
Step 7: Finished goods added to inventory at calculated cost
```

## Business Example

A furniture manufacturer runs 50 work orders per week. Before backflushing, each order required 15 minutes of component entry — over 12 hours per week. After backflushing, component consumption is automatic. The team saves 10 hours per week and makes fewer data entry errors.

## Related Articles

- [Component Issuing](component-issuing.md)
- [Work Orders](work-orders.md)
- [Work in Progress](work-in-progress.md)
- [Bills of Materials](bills-of-materials.md)

## Oracle References

- [Oracle NetSuite Help Center: Backflushing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)