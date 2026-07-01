# Inventory

This module covers Inventory Management in NetSuite — the systems, processes, and configurations for tracking, valuing, and controlling stock.

## Learning Paths

### Release 0.5A — Inventory Fundamentals (Complete)

Foundational concepts: what inventory is, item records, item types, locations, units of measure, status lifecycle.

See [README](README.md) in the module root for the full inventory curriculum.

### Release 0.5B — Inventory Operations (Current)

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