# Purchasing

This module covers the Procure-to-Pay (P2P) lifecycle — how organizations identify needs, select vendors, create purchase orders, receive goods, process invoices, and make payments. Purchasing connects to Inventory, Accounting, Manufacturing, and Reporting.

## Learning Path

| Step | Article | Est. Time | Business Process |
|---|---|---|---|
| 1 | [What Is Procurement?](what-is-procurement.md) | 10 min | The Procure-to-Pay lifecycle |
| 2 | [Vendor Management](vendor-management.md) | 15 min | Vendor records, relationships, classifications |
| 3 | [Purchase Requisitions](purchase-requisitions.md) | 10 min | Internal requests for goods and services |
| 4 | [Purchase Orders](purchase-orders.md) | 20 min | The core purchasing document |
| 5 | [Approval Workflows](approval-workflows.md) | 15 min | PO approval processes and controls |
| 6 | [Vendor Bills and Payments](vendor-bills-and-payments.md) | 15 min | Accounts payable processing |
| 7 | [Three-Way Matching](three-way-matching.md) | 15 min | PO, receipt, and invoice matching |
| 8 | [Purchasing Controls](purchasing-controls.md) | 10 min | Permissions, spending limits, policies |
| 9 | [Procurement KPIs](procurement-kpis.md) | 10 min | Metrics, reporting, and monitoring |
| 10 | [Procurement Best Practices](procurement-best-practices.md) | 15 min | Consolidated reference |
| 11 | [Purchasing Glossary](purchasing-glossary.md) | 5 min | Key terms defined |
| — | **Estimated total time** | **140 min** | — |

## Prerequisites

- [Getting Started module](../getting-started/README.md)
- [Inventory Fundamentals](../inventory/what-is-inventory.md) — receiving inventory is part of procurement
- [Administration module](../administration/README.md) — feature enablement, permissions

## The Procure-to-Pay Flow

```
Need identified
    ↓
Purchase Requisition created
    ↓
Requisition approved
    ↓
Purchase Order issued to vendor
    ↓
Vendor confirms order
    ↓
Goods received (Item Receipt)
    ↓
Three-way match (PO → Receipt → Bill)
    ↓
Vendor Bill entered
    ↓
Bill approved for payment
    ↓
Payment issued
    ↓
Accounting entries complete
```

## How Purchasing Connects

| Module | Connection |
|---|---|
| **Inventory** | Purchase orders create inventory via Item Receipt |
| **Accounting** | Vendor bills, accruals, payments, COGS |
| **Manufacturing** | Raw material procurement for production |
| **Sales** | Drop-ship and special order fulfillment |
| **Saved Searches** | PO monitoring, vendor performance, spend analysis |
| **Workflows** | Approval routing, PO automation |
| **SuiteScript** | Automated PO creation, vendor integration |

## Related Documents

- [Inventory module](../inventory/README.md)
- [Administration module](../administration/README.md)
- [Saved Searches module](../saved-searches/README.md)