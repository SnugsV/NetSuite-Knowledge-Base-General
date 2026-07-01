# Inventory

This module covers Inventory Management in NetSuite — the systems, processes, and configurations for tracking, valuing, and controlling stock.

## Learning Paths

### Release 0.5A — Inventory Fundamentals (Complete)

Foundational concepts: what inventory is, item records, item types, locations, units of measure, status lifecycle.

See [README](README.md) in the module root for the full inventory curriculum.

### Release 0.5B — Inventory Operations (Complete)

Operational workflows: how inventory moves through an organization. Each article is organized around a business process, not a NetSuite feature.

| Step | Article | Est. Time | Business Process |
|---|---|---|---|
| 1 | [Receiving Inventory](receiving-inventory.md) | 15 min | Purchase-to-stock workflow |
| 2 | [Fulfilling Orders](fulfilling-orders.md) | 15 min | Order-to-ship workflow |
| 3 | [Transfer Orders](transfer-orders.md) | 15 min | Inter-location movement with tracking |
| 4 | [Inventory Adjustments](inventory-adjustments.md) | 10 min | Quantity corrections and write-offs |
| 5 | [Cycle Counting](cycle-counting.md) | 10 min | Ongoing inventory verification |
| 6 | [Physical Inventory](physical-inventory.md) | 10 min | Full period-end reconciliation |
| 7 | [Replenishment](replenishment.md) | 10 min | Automatic reorder management |
| 8 | [Returns Processing](returns-processing.md) | 10 min | Customer returns and restocking |
| — | **Estimated total time** | **95 min** | — |

### Release 0.5C — Advanced Inventory (Current)

Advanced concepts and implementation decisions. Focuses on when and why to use each feature, not just how.

| Step | Article | Est. Time | Topic |
|---|---|---|---|
| 1 | [Bin Management](bin-management.md) | 15 min | Warehouse organization, bin naming, assignment strategies |
| 2 | [Lot Tracking](lot-tracking.md) | 15 min | Batch traceability, expiration, recalls |
| 3 | [Serial Tracking](serial-tracking.md) | 15 min | Unit-level tracking, warranty, service history |
| 4 | [Matrix Items](matrix-items.md) | 15 min | Product variations with multiple dimensions |
| 5 | [Costing Methods](costing-methods.md) | 20 min | Average, standard, FIFO, LIFO, specific cost |
| 6 | [Landed Cost](landed-cost.md) | 15 min | Freight, duty, insurance allocation |
| 7 | [Multi-Location Strategy](multi-location-strategy.md) | 15 min | Centralized, decentralized, hub-and-spoke |
| 8 | [Drop Ship and Special Orders](drop-ship-and-special-orders.md) | 10 min | Vendor-direct fulfillment |
| 9 | [Advanced Inventory Design](advanced-inventory-design.md) | 15 min | Architecture decisions, implementation phasing |
| 10 | [Inventory Best Practices](inventory-best-practices.md) | 15 min | Consolidated reference for all inventory practices |
| — | **Estimated total time** | **150 min** | — |

## Prerequisites

- [Inventory Fundamentals](what-is-inventory.md) — all 0.5A articles
- [Saved Searches module](../saved-searches/README.md) — for inventory reporting
- [Getting Started module](../getting-started/README.md)

## How Inventory Operations Connect

```
Vendor → [Receiving] → Inventory → [Fulfilling] → Customer
                            │
                    ┌───────┼───────┐
                    │       │       │
               [Transfers] [Cycles] [Adjustments]
                    │       │       │
                    └───────┼───────┘
                            │
                      [Replenishment]
                            │
                      [Returns]
```

## Related Documents

- [Release 0.5A — Fundamentals](what-is-inventory.md)
- [Inventory Glossary](inventory-glossary.md)
- [Release Plan 0.5](../../RELEASE_PLAN_0.5.md)