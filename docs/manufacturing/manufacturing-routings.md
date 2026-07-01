---
title: Manufacturing Routings
module: Manufacturing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Manufacturing Routings

## Quick Summary

A routing defines the sequence of production steps required to build an assembly item. Each step specifies a work center, setup time, run time, and labor requirements. Routings enable accurate costing and production scheduling.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Business Question

"How long does it take to build one unit, and what resources are required at each step?"

## Overview

While the BOM defines what materials go into a product, the routing defines how it is built. A routing breaks production into steps — cutting, welding, painting, assembly, packaging — each with its own time, labor, and machine requirements.

## Routing Structure

```
Product: Office Chair

Step 10: Cut Frame — Work Center: Cutting (30 min setup, 5 min run)
Step 20: Weld Frame — Work Center: Welding (15 min setup, 8 min run)
Step 30: Paint — Work Center: Painting (20 min setup, 3 min run)
Step 40: Upholster — Work Center: Assembly (10 min setup, 12 min run)
Step 50: Package — Work Center: Packaging (5 min setup, 2 min run)

Total: 80 min setup, 30 min run per unit
```

## Routing Components

| Component | Purpose |
|---|---|
| **Operation Step** | A single production step with an order number |
| **Work Center** | The location or resource where the operation occurs |
| **Setup Time** | Time to prepare the work center (fixed per batch) |
| **Run Time** | Time per unit (variable per unit) |
| **Labor** | Number of workers required |
| **Machine** | Equipment required |

## Business Example

A chair manufacturer implements routings for a new product line. Before routings, production estimates were guesswork. After routings, they can:

- Calculate total production time per order
- Schedule work centers to avoid bottlenecks
- Quote accurate delivery dates to customers
- Identify where efficiency improvements will have the most impact

## Related Articles

- [Work Orders](work-orders.md)
- [Manufacturing Costing](manufacturing-costing.md)
- [What Is Manufacturing?](what-is-manufacturing.md)

## Oracle References

- [Oracle NetSuite Help Center: Manufacturing Routings](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)