# Release Plan 2.1 — Pacejet Integration Architecture

## Overview

### Purpose

Design the first Ecosystem Integration Learning Path, using Pacejet as the template for every future NetSuite integration. Pacejet is a multi-carrier shipping platform that integrates with NetSuite to provide rate shopping, label generation, tracking, and shipping automation.

### Why Pacejet First

Shipping is the intersection of Sales, Inventory, Fulfillment, and Accounting — it touches the core ERP workflows already documented in this repository. Pacejet is also one of the most widely used NetSuite ecosystem integrations.

### Integration Architecture

```
Sales Order → Item Fulfillment → Pacejet API
                                      ↓
                              Rate Shopping (Carrier A, B, C...)
                                      ↓
                              Label Generation
                                      ↓
                              Tracking Number Back to NetSuite
                                      ↓
                              Fulfillment Updated with Tracking
                                      ↓
                              Invoice Generated
```

### Key Components

| Component | Function |
|---|---|
| **Pacejet Shipping** | Core multi-carrier shipping platform |
| **Pacejet Connector** | NetSuite bundle that bridges NetSuite ↔ Pacejet |
| **Pacejet Scale Service** | Weight capture integration |
| **Pacejet Cubiscan** | Dimension capture integration |
| **Advanced Shipping Data (ASD)** | Extended shipping data fields in NetSuite |
| **Pacejet Label Connector** | Custom label generation via third-party tools |
| **Pacejet API** | REST API for programmatic access |
| **Carrier Modules** | Individual carrier integrations (FedEx, UPS, etc.) |

---

## Phase 1 — Architecture Analysis

### NetSuite Bundle Architecture

The Pacejet Connector NetSuite bundle provides:

- Custom records for shipment data
- Custom fields on sales orders and item fulfillments
- SuiteScript for integration logic
- Button actions on fulfillment records
- Scheduled scripts for status updates

### Data Flow

```
NetSuite Item Fulfillment
  → SuiteScript collects shipment data
  → POST to Pacejet API (shipment request)
  → Pacejet rates and selects carrier
  → Label generated (Pacejet or label connector)
  → Tracking number returned to NetSuite
  → Item Fulfillment updated with tracking
  → Sales Order status updated
```

### Shipping Workflow

| Step | System | Description |
|---|---|---|
| 1 | NetSuite | Sales order created, approved |
| 2 | NetSuite | Item Fulfillment created |
| 3 | NetSuite | Pacejet button clicked or automation triggered |
| 4 | Pacejet | Rate shopping across enabled carriers |
| 5 | Pacejet | Carrier selected (auto or manual) |
| 6 | Pacejet | Label generated |
| 7 | Pacejet | Tracking number sent back to NetSuite |
| 8 | NetSuite | Fulfillment updated, tracking available |
| 9 | NetSuite | Invoice created |

### Carrier Integrations

Each carrier has its own module within Pacejet:

| Carrier | Features |
|---|---|
| FedEx | Rates, labels, tracking, address validation, shipment confirm |
| Armour | Rates, labels, tracking |
| Unishippers | Rates, labels, tracking |
| WorldWide Express | Rates, labels, tracking |
| Day and Ross | Canadian carrier, rates, labels |
| eShipping | Rates, labels |
| Estes | LTL rates, labels |
| Evans | Rates, labels |
| TForce | Rates, labels |
| XPO | LTL rates, labels |

---

## Phase 2 — ERP Integration Mapping

### Sales

| Integration Point | Upstream | Downstream |
|---|---|---|
| Sales Order address | Used for rate calculation | Shipping address validation |
| Item weight/dimensions | Used for rate calculation | Packing validation |
| Ship via / carrier preference | Carrier selection input | Rate shopping filter |
| Customer-specific shipping rules | Trading partner configuration | Carrier and service selection |

### Inventory

| Integration Point | Upstream | Downstream |
|---|---|---|
| Item weight | Item record field | Rate calculation |
| Item dimensions | Item record field | Packing optimization |
| Inventory location | Fulfillment location | Origin for rate calculation |
| Bin location | Pick confirmation | Shipment data |

### Fulfillment

| Integration Point | Upstream | Downstream |
|---|---|---|
| Item Fulfillment record | Source of shipment data | Pacejet API request |
| Package information | Packing process | Label generation |
| Tracking number | Pacejet response | Customer notification |
| Fulfillment status | Pacejet update | Sales order status |

### Accounting

| Integration Point | Upstream | Downstream |
|---|---|---|
| Shipping cost | Carrier rate response | COGS or expense |
| Freight charges | Carrier rate response | Customer billing |
| Customs documents | International shipment data | Regulatory compliance |

### Purchasing (Drop Ship)

| Integration Point | Upstream | Downstream |
|---|---|---|
| Vendor address | Purchase order | Drop ship origin |
| Item weight/dimensions | Item record | Rate for drop ship |

---

## Phase 3 — Learning Path Structure

### Tier 1 — Foundation (10 articles)

| Article | Difficulty | Est. Time |
|---|---|---|
| What Is Pacejet? | Beginner | 10 min |
| Pacejet Architecture Overview | Intermediate | 15 min |
| NetSuite Integration Setup | Intermediate | 20 min |
| Core Shipping Workflow | Beginner | 15 min |
| Rate Shopping | Intermediate | 15 min |
| Label Generation | Intermediate | 15 min |
| Tracking and Status Updates | Intermediate | 10 min |
| Supported Carriers | Beginner | 10 min |
| Common Configuration | Intermediate | 15 min |
| Pacejet Glossary | Beginner | 5 min |

### Tier 2 — Operations (8 articles)

| Article | Difficulty | Est. Time |
|---|---|---|
| Batch Shipping | Intermediate | 15 min |
| Automation Options | Advanced | 15 min |
| International Shipping | Advanced | 20 min |
| Return Shipping | Intermediate | 10 min |
| Address Validation | Intermediate | 10 min |
| Advanced Shipping Data (ASD) | Advanced | 15 min |
| Reporting and Analytics | Intermediate | 10 min |
| Error Handling and Troubleshooting | Intermediate | 15 min |

### Tier 3 — Advanced (6 articles)

| Article | Difficulty | Est. Time |
|---|---|---|
| Custom Label Connector | Advanced | 20 min |
| Pacejet API | Advanced | 20 min |
| Multi-Warehouse Shipping | Advanced | 15 min |
| Scale and Cubiscan Integration | Advanced | 10 min |
| Performance and Governance | Advanced | 10 min |
| Integration Best Practices | Advanced | 15 min |

### Total: ~24 articles, ~5 hours

---

## Phase 4 — AI Integration Points

### Support Intelligence (future)

| Topic | Support Patterns |
|---|---|
| Label not generating | Carrier configuration, item data, API connectivity |
| Wrong rate returned | Address validation, package data, carrier contract |
| Tracking not updating | API callback, NetSuite status update, scheduled script |
| Integration not connecting | Bundle version, API credentials, network |
| Automation not triggering | Script governance, workflow condition, button action |

### Customer Context (future)

| Context Element | Why It Matters |
|---|---|
| Carriers enabled | Determines available rate options |
| Pacejet version | API compatibility, feature availability |
| NetSuite bundle version | Script functionality, ASD fields |
| Item data completeness | Weight/dimensions affect rate accuracy |
| Warehouse locations | Multi-origin shipping configuration |
| International shipping needs | Customs documentation, restricted carriers |

### Metadata Collection (future)

| Metadata | Why |
|---|---|
| Carrier contract details | Rate shopping logic |
| Custom label templates | Label connector configuration |
| ASD custom fields | Extended data mapping |
| Script deployment list | Automation scripts on fulfillment |

### AI Skills (future)

| Skill | Purpose |
|---|---|
| Pacejet Configuration | Guide through setup, carrier activation, testing |
| Troubleshooter: Label Issues | Diagnose label generation failures |
| Troubleshooter: Rate Issues | Diagnose incorrect or missing rates |
| Pacejet API Integration | Build custom API-based workflows |

### Solution Architecture (future)

| Decision | Criteria |
|---|---|
| Pacejet vs. native carrier integration | Volume, carrier count, automation needs |
| Pacejet Connector vs. API | Standard vs. custom integration |
| Pacejet + ASD vs. custom fields | Configuration vs. development |
| Auto-rate vs. manual carrier selection | Automation vs. control |

---

## Phase 5 — Deliverables

### 5A — Core Documentation (12 articles)

Pacejet overview, architecture, NetSuite integration setup, core shipping workflow, rate shopping, label generation, tracking, carriers, configuration, glossary, batch shipping, error handling.

### 5B — Advanced Topics (8 articles)

API, custom labels, international shipping, automation, ASD, reporting, scale/Cubiscan, performance.

### 5C — AI Framework Integration (6 documents)

Support Intelligence for Pacejet, Customer Context, Metadata Collection, AI Skills, Solution Architect routing, Pacejet-specific troubleshooting patterns.

### Total Estimated Effort

- **Phase 5A** — 10-12 hours
- **Phase 5B** — 6-8 hours
- **Phase 5C** — 4-5 hours
- **Total** — 20-25 hours

---

## Risks

| Risk | Mitigation |
|---|---|
| Pacejet documentation is extensive but uses different terminology | Map Pacejet terms to NetSuite ERP terms |
| Version fragmentation (multiple bundle versions) | Document by capability, not version; note version-specific features |
| API changes between Pacejet releases | Cross-reference release notes for API stability |
| Customer configurations vary widely | Document with metadata-first approach (collect config before troubleshooting) |
| All Pacejet knowledge base content is proprietary | Teach concepts and integration patterns, not feature lists |

## Recommendations

1. **Build Phase 5A first** — the core documentation creates the foundation
2. **Use Pacejet as the integration template** — the architecture, AI integration points, and metadata patterns apply to any NetSuite ecosystem integration
3. **Build the Pacejet AI Skills second** — troubleshooting label, rate, and tracking issues are the most common support scenarios
4. **Phase 5C should come last** — the AI framework requires the core documentation to exist before patterns can be extracted

## Related Documents

- [Sales Learning Path](../docs/sales/README.md)
- [Inventory Learning Path](../docs/inventory/README.md)
- [Solution Architect Framework](knowledge-engine/solution-architect/README.md)
- [Customer Metadata Framework](knowledge-engine/customer-metadata/README.md)

## Oracle References

- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)
- [Oracle NetSuite Help Center: Shipping](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)