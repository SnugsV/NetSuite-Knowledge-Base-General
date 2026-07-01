---
title: Manufacturing Best Practices
module: Manufacturing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Manufacturing Best Practices

## Quick Summary

Manufacturing best practices span BOM management, work order processing, costing, quality, and ERP integration. Following these practices reduces production errors, improves cost accuracy, and strengthens the plan-to-produce cycle.

## BOM Management

- Maintain BOM revisions for all assembly items
- Review BOM accuracy quarterly — component substitutions happen
- Use multi-level BOMs for complex products; consider phantom BOMs for sub-assemblies
- Document the effective date and reason for each BOM revision
- Train production staff to report BOM discrepancies

## Work Order Management

- Create work orders for all production — no production without a work order
- Set realistic start and due dates on every work order
- Issue components promptly — delayed issuing delays build completion
- Use backflushing for high-volume, stable BOM production
- Close work orders promptly after build completion

## Costing

- Choose standard costing for complex manufacturing; average costing for simple assembly
- Review standard costs quarterly and update for significant changes
- Investigate all material and labor variances exceeding 5%
- Reconcile WIP accounts monthly
- Monitor cost variance trends — increasing variances indicate process drift

## Quality

- Define inspection points in routings where applicable
- Track first pass yield and scrap rates
- Investigate products with high rework rates
- Use Saved Searches to monitor work order completion and quality metrics

## ERP Integration

| Module | Connection |
|---|---|
| **Inventory** | Raw material availability drives production scheduling |
| **Purchasing** | Shortages flagged during work order creation trigger procurement |
| **Sales** | Customer orders can create demand-driven work orders |
| **Accounting** | WIP valuation, cost variances, COGS impact |
| **Saved Searches** | Work order tracking, component shortage identification |

## Health Scorecard

| Metric | Healthy | Warning | Critical |
|---|---|---|---|
| Schedule Adherence | > 95% | 85-95% | < 85% |
| Unit Cost Variance | ± 5% | ± 10% | > 10% |
| First Pass Yield | > 95% | 85-95% | < 85% |
| Scrap Rate | < 2% | 2-5% | > 5% |
| WIP Aging (open > 30 days) | < 10% | 10-20% | > 20% |

## Related Articles

- [Manufacturing KPIs](manufacturing-kpis.md)
- [Capstone Scenario](capstone-scenario.md)
- [Inventory Best Practices](../inventory/inventory-best-practices.md)
- [Purchasing: Procurement Best Practices](../purchasing/procurement-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Manufacturing Best Practices](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)