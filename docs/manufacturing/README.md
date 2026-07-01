# Manufacturing

This module covers the Plan-to-Produce lifecycle — how organizations transform raw materials into finished goods using bills of materials, work orders, routings, and manufacturing costing.

## Learning Path

| Step | Article | Est. Time | Topic |
|---|---|---|---|
| 1 | [What Is Manufacturing?](what-is-manufacturing.md) | 10 min | Plan-to-Produce lifecycle |
| 2 | [Item Types for Manufacturing](item-types-for-manufacturing.md) | 10 min | Assembly items, BOM items |
| 3 | [Bills of Materials](bills-of-materials.md) | 20 min | BOM structure and management |
| 4 | [Work Orders](work-orders.md) | 20 min | The core manufacturing transaction |
| 5 | [Component Issuing](component-issuing.md) | 15 min | Releasing materials to production |
| 6 | [Manufacturing Routings](manufacturing-routings.md) | 15 min | Production steps and work centers |
| 7 | [Work in Progress](work-in-progress.md) | 15 min | WIP accounting and tracking |
| 8 | [Backflushing](backflushing.md) | 10 min | Automated component consumption |
| 9 | [Manufacturing Costing](manufacturing-costing.md) | 20 min | Costing methods, variance analysis |
| 10 | [Manufacturing KPIs](manufacturing-kpis.md) | 10 min | Metrics, monitoring, dashboards |
| 11 | [Manufacturing Best Practices](manufacturing-best-practices.md) | 15 min | Consolidated reference |
| 12 | [Capstone Scenario](capstone-scenario.md) | 20 min | End-to-end manufacturing case study |
| 13 | [Manufacturing Glossary](manufacturing-glossary.md) | 5 min | Key terms |
| — | **Estimated total time** | **185 min** | — |

## Prerequisites

- [Inventory module](../inventory/README.md) — item records, types, locations
- [Purchasing module](../purchasing/README.md) — raw material procurement
- [Sales module](../sales/README.md) — demand-driven production

## How Manufacturing Connects

| Module | Connection |
|---|---|
| **Inventory** | Raw materials consumed, finished goods produced |
| **Purchasing** | Raw material procurement for production |
| **Sales** | Demand-driven work orders from sales orders |
| **Accounting** | WIP valuation, COGS, cost variances |
| **Saved Searches** | Work order tracking, component availability |

## The Plan-to-Produce Flow

```
Vendor → Raw Materials → Work Order → WIP → Finished Goods → Customer
                                                                 
    Inventory          Manufacturing          Inventory          Sales
```