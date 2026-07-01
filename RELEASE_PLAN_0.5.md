# Release Plan 0.5 — Inventory Learning Path

## Overview

### Purpose

Design the definitive Inventory learning path for the NetSuite Knowledge Base. The Inventory module will be one of the largest and most interconnected sections of the repository — inventory touches every operational module in NetSuite.

### The Inventory Learning Opportunity

Inventory is where the "rubber meets the road" in ERP. Every other module interacts with it:

- **Purchasing** creates inventory
- **Sales** consumes inventory
- **Manufacturing** transforms inventory
- **Accounting** values inventory
- **Reporting** monitors inventory
- **Administration** configures inventory features

A person who understands NetSuite Inventory understands how NetSuite works as a system.

### Current State

| Metric | Value |
|---|---|
| Existing articles | 2 (overview.md, inventory-transfers.md) |
| Article format | Legacy (old front matter, no cross-links, no Quick Summary) |
| Cross-links | 0 — neither article links to any other content |
| Module status in docs/README.md | "Started" |
| Sprint in backlog | Sprint 0.5 — Inventory and Operations |

---

## Phase 1 — Inventory Domain Analysis

### Foundational Concepts

| Concept | Description | Prerequisites |
|---|---|---|
| What is inventory management | The business discipline of tracking, valuing, and controlling stock | None |
| Item records | The master data that represents every product, part, or material | Lists and Records (getting-started) |
| Item types | Inventory, non-inventory, service, kit, assembly, group, description | Item records |
| Locations | Physical or logical places where inventory is stored | None |
| Quantity concepts | On Hand, Available, Committed, On Order, In Transit | Item records |
| Inventory valuation | How inventory is valued (cost, average cost, FIFO, standard) | Accounting basics |
| Units of measure | Stock unit, purchase unit, sale unit, conversions | Item records |

### Advanced Concepts

| Concept | Description | Prerequisites |
|---|---|---|
| Multi-location inventory | Managing stock across multiple warehouses | Locations |
| Bin management | Sub-location storage within warehouses | Locations |
| Lot tracking | Batch-level traceability | Advanced Inventory features |
| Serial tracking | Individual item traceability | Advanced Inventory features |
| Matrix items | Items with multiple variations (size, color) | Advanced Inventory features |
| Landed cost | Total cost including freight, insurance, duties | Inventory valuation |
| Drop ship and special order | Fulfilling without stocking | Item types, purchasing |

### Implementation Concepts

| Concept | Description | Prerequisites |
|---|---|---|
| Feature enablement | Inventory Management, Advanced Inventory, WMS features | Administration (enabled-features) |
| Item record setup | Creating and configuring item records | Item types |
| Location setup | Defining warehouses and sub-locations | Administration |
| Units of measure setup | Configuring UOM conversions | Item records |
| Inventory preferences | Account-level inventory behavior settings | Administration (company-preferences) |

### Operational Concepts

| Concept | Description | Prerequisites |
|---|---|---|
| Purchase to stock | Receiving items from vendors | Purchasing, item receipt |
| Order to fulfill | Picking and shipping items to customers | Sales, item fulfillment |
| Inventory transfers | Moving stock between locations | Locations |
| Transfer orders | Tracked multi-step inventory movement | Locations |
| Inventory adjustments | Correcting quantities | Inventory basics |
| Cycle counts | Ongoing inventory verification | Locations |
| Physical counts | Full inventory reconciliation | Inventory basics |
| Replenishment | Automatic reorder suggestions | Inventory planning |

### Reporting Concepts

| Concept | Description | Prerequisites |
|---|---|---|
| Inventory valuation reports | Cost and value analysis | Saved Searches |
| Transaction history | Movement tracking | Saved Searches |
| Stock status | Current availability | Saved Searches |
| Inventory aging | Turnover and slow-moving analysis | Saved Searches |
| Reorder analysis | When and what to reorder | Saved Searches, replenishment |

### Manufacturing Concepts

| Concept | Description | Prerequisites |
|---|---|---|
| Assembly items | Items built from components | Item types |
| Bill of materials | Component structure | Assembly items |
| Build orders | Authorizing assembly production | Assembly items |
| Work orders | Manufacturing execution | Manufacturing feature |
| Demand planning | Forecasting requirements | Advanced inventory |

---

## Phase 2 — Learning Path Design

### Learning Objectives

After completing this module, a reader should be able to:

1. Understand what inventory management is and why companies do it
2. Create and configure item records for different item types
3. Set up locations and manage multi-location inventory
4. Process inventory transactions: transfers, adjustments, receipts, fulfillments
5. Understand inventory valuation methods and their business impact
6. Configure inventory features enabled for their account
7. Run inventory reports and Saved Searches for monitoring
8. Set up replenishment and cycle counting
9. Understand how inventory connects to purchasing, sales, manufacturing, and accounting
10. Avoid common inventory implementation mistakes

### Prerequisites

| Module | Why |
|---|---|
| Getting Started | Understanding records, lists, navigation, and UI concepts |
| Administration | Feature enablement, permissions, company preferences |
| Saved Searches | Inventory reporting and monitoring (designed concurrently) |

### Difficulty Progression

```
Beginner (8 articles)  →  Intermediate (10 articles)  →  Advanced (6 articles)  →  Reference (2 articles)
```

### Estimated Completion Time

- **Full path**: 4-6 hours
- **Core path (Beginner)**: 1.5 hours
- **Operational path (Beginner + Intermediate)**: 3-4 hours

### Suggested Reading Paths

#### Beginner Path (2 hours)
For someone new to NetSuite Inventory.

1. What Is Inventory Management?
2. Item Records
3. Item Types
4. Locations
5. Inventory Transfers
6. Inventory Adjustments
7. Receiving Inventory
8. Fulfilling Orders
9. Common Inventory Mistakes
10. Inventory Glossary

#### Operational Path (4 hours)
For warehouse managers and inventory clerks.

All of Beginner path, plus:

11. Transfer Orders
12. Bin Management
13. Cycle Counting
14. Physical Inventory Counts
15. Replenishment
16. Inventory Reporting
17. Lot and Serial Tracking
18. Real-World Inventory Workflows

#### Implementation Path (6 hours)
For administrators and consultants setting up inventory.

All of Beginner + Operational paths, plus:

19. Inventory Feature Enablement
20. Item Record Configuration
21. Units of Measure
22. Inventory Valuation Methods
23. Multi-Location Setup
24. Landed Cost
25. Matrix Items
26. Inventory Best Practices
27. Inventory Troubleshooting

---

## Phase 3 — Proposed Module Structure

### Complete Article Inventory (26 articles + 1 README)

#### Beginner Tier (9 articles)

| # | Article | Difficulty | Est. Length | Business Value | Priority |
|---|---|---|---|---|---|
| 1 | **README — Module Index** | — | 80 lines | Navigation, learning paths, ERP overview | Critical |
| 2 | **What Is Inventory Management?** | Beginner | 200 lines | Foundational — answers "why inventory" | Critical |
| 3 | **Item Records** | Beginner | 300 lines | Prerequisite for everything | Critical |
| 4 | **Item Types** | Beginner | 300 lines | Critical for understanding what items are | Critical |
| 5 | **Locations** | Beginner | 250 lines | Multi-location is the #1 inventory feature | Critical |
| 6 | **Inventory Transfers** | Beginner | 300 lines | Most common transaction | Critical (exists) |
| 7 | **Inventory Adjustments** | Beginner | 250 lines | Corrections, damages, write-offs | Critical |
| 8 | **Receiving Inventory** | Beginner | 300 lines | Purchasing → Inventory | Critical |
| 9 | **Fulfilling Orders** | Beginner | 300 lines | Inventory → Sales | Critical |

#### Intermediate Tier (10 articles)

| # | Article | Difficulty | Est. Length | Business Value | Priority |
|---|---|---|---|---|---|
| 10 | **Transfer Orders** | Intermediate | 350 lines | Tracked multi-step movement | High |
| 11 | **Bin Management** | Intermediate | 300 lines | Warehouse organization | High |
| 12 | **Cycle Counting** | Intermediate | 250 lines | Accuracy without full counts | High |
| 13 | **Physical Inventory Counts** | Intermediate | 250 lines | Period-end reconciliation | High |
| 14 | **Replenishment** | Intermediate | 300 lines | Automatic reorder suggestions | High |
| 15 | **Inventory Valuation Methods** | Intermediate | 400 lines | Financial impact — most misunderstood | High |
| 16 | **Units of Measure** | Intermediate | 250 lines | Purchase vs. stock vs. sale units | Medium |
| 17 | **Lot and Serial Tracking** | Intermediate | 350 lines | Traceability and compliance | Medium |
| 18 | **Landed Cost** | Intermediate | 300 lines | True cost of inventory | Medium |
| 19 | **Inventory Reporting** | Intermediate | 300 lines | Saved Searches for inventory | Medium |

#### Advanced Tier (6 articles)

| # | Article | Difficulty | Est. Length | Business Value | Priority |
|---|---|---|---|---|---|
| 20 | **Feature Enablement for Inventory** | Advanced | 250 lines | Setup guidance | High |
| 21 | **Multi-Location Setup and Strategy** | Advanced | 350 lines | Design decisions | High |
| 22 | **Matrix Items** | Advanced | 350 lines | Variation management | Medium |
| 23 | **Landed Cost Advanced** | Advanced | 300 lines | Allocation methods | Medium |
| 24 | **Drop Ship and Special Orders** | Advanced | 300 lines | Non-stocked fulfillment | Medium |
| 25 | **Inventory Best Practices** | Advanced | 350 lines | Consolidation of all modules | High |

#### Reference Tier (2 articles)

| # | Article | Difficulty | Est. Length | Business Value | Priority |
|---|---|---|---|---|---|
| 26 | **Common Inventory Mistakes** | Beginner | 300 lines | Learning from others' errors | Critical |
| 27 | **Inventory Glossary** | Beginner | 150 lines | Terminology reference | Medium |

### Estimated Content Volume

| Tier | Articles | Lines | Effort (hours) |
|---|---|---|---|
| Beginner | 9 + README | ~2,200 | 10-12 |
| Intermediate | 10 | ~3,000 | 14-16 |
| Advanced | 6 | ~1,800 | 8-10 |
| Reference | 2 | ~450 | 2-3 |
| **Total** | **27** | **~7,450** | **34-41 hours** |

---

## Phase 4 — ERP Integration Map

### Inventory connects to every module. Each relationship must be documented.

| Module | Inventory Relationship | Cross-Link Target | Articles Affected |
|---|---|---|---|
| **Getting Started** | Item records understanding | Lists and Records | Item Records, Item Types |
| | Center navigation | Navigation | All inventory articles |
| **Administration** | Feature enablement for inventory features | Enabled Features | Feature Enablement for Inventory |
| | Permissions for inventory transactions | Permissions | All operational articles |
| | Company preferences for inventory | Company Preferences | Inventory setup articles |
| **Saved Searches** | Inventory monitoring and reporting | Everything in saved-searches/ | Inventory Reporting |
| | Low stock alerts (case study) | Real-World Business Examples | Replenishment |
| **Purchasing** | Purchase orders create inventory | (future module) | Receiving Inventory |
| | Vendor returns | (future module) | Adjustments |
| **Sales** | Sales orders consume inventory | (future module) | Fulfilling Orders |
| | Order management pipeline | (future module) | Availability checks |
| **Manufacturing** | Assembly items consume components | (future module) | Item Types, Work Orders |
| | Build orders create inventory | (future module) | Manufacturing integration |
| **Accounting** | Inventory valuation affects balance sheet | (future module) | Valuation Methods, Landed Cost |
| | COGS from inventory fulfillment | (future module) | Fulfilling Orders |
| **SuiteScript** | Programmatic inventory queries | SuiteScript Overview | All advanced articles |
| | Inventory automation scripts | (future module) | Best Practices |
| **Workflows** | Approval flows for transfers/adjustments | (future module) | Transfers, Adjustments |
| **SuiteAnalytics** | Inventory analytics workbooks | (future module) | Inventory Reporting |

### Integration Points Documented Per Article

Every inventory article should include a "How This Connects" section that explicitly maps to the modules above. For modules that don't exist yet, the section should note "See [Module Name] when available" as a forward reference.

### Cross-Link Targets

| Article | Links To (minimum) |
|---|---|
| What Is Inventory Management? | Getting Started (all), Administration (overview) |
| Item Records | Lists and Records, Item Types, Saved Searches |
| Item Types | Item Records, Manufacturing (future), Purchasing (future) |
| Locations | Administration (feature enablement), Transfers, Bins |
| Inventory Transfers | Locations, Transfer Orders, Adjustments |
| Receiving Inventory | Purchasing (future), Transfer Orders, Locations |
| Fulfilling Orders | Sales (future), Locations, Transfer Orders |
| Inventory Valuation | Accounting (future), Landed Cost, Saved Searches |
| Inventory Reporting | Saved Searches (all), SuiteAnalytics (future) |
| Feature Enablement for Inventory | Administration (enabled-features), Item Types |

---

## Phase 5 — Business Process Mapping

### Process 1: Purchase-to-Stock

```
Vendor ships → PO Created → Item Receipt → Inventory On Hand → AP Created
```

| Element | Detail |
|---|---|
| **Business goal** | Receive inventory from suppliers accurately and efficiently |
| **Departments involved** | Purchasing, Warehouse, Receiving, Accounting |
| **NetSuite modules** | Purchasing, Inventory, Accounts Payable |
| **Transactions** | Purchase Order, Item Receipt, Vendor Bill |
| **Key decisions** | Direct receipt vs. transfer order receipt; bin assignments |
| **Documentation needed** | Receiving Inventory (this sprint), Purchase Orders (future sprint) |

### Process 2: Order-to-Fulfill

```
Customer orders → Sales Order → Pick → Pack → Ship → Invoice
```

| Element | Detail |
|---|---|
| **Business goal** | Fulfill customer orders from available inventory |
| **Departments involved** | Sales, Warehouse, Shipping, Accounting |
| **NetSuite modules** | Sales, Inventory, Order Management, Accounts Receivable |
| **Transactions** | Sales Order, Item Fulfillment, Package, Invoice |
| **Key decisions** | Partial vs. full fulfillment; backorder handling; bin picking |
| **Documentation needed** | Fulfilling Orders (this sprint), Order Management (future sprint) |

### Process 3: Inventory Transfer

```
Warehouse A → Transfer Order → Ship → Receive → Warehouse B
```

| Element | Detail |
|---|---|
| **Business goal** | Rebalance stock between locations |
| **Departments involved** | Warehouse (sending), Warehouse (receiving) |
| **NetSuite modules** | Inventory |
| **Transactions** | Transfer Order, Inventory Transfer |
| **Key decisions** | Simple vs. tracked transfer; in-transit visibility |
| **Documentation needed** | Inventory Transfers, Transfer Orders (this sprint) |

### Process 4: Cycle Count

```
Schedule count → Count items → Enter counts → Review variances → Adjust
```

| Element | Detail |
|---|---|
| **Business goal** | Maintain inventory accuracy without full physical counts |
| **Departments involved** | Warehouse, Inventory Control |
| **NetSuite modules** | Inventory |
| **Transactions** | Inventory Count, Inventory Adjustment |
| **Key decisions** | Count frequency; ABC classification; variance thresholds |
| **Documentation needed** | Cycle Counting (this sprint), Saved Searches (completed) |

### Process 5: Physical Inventory

```
Plan count → Freeze transactions → Count all items → Enter counts → Adjust → Unfreeze
```

| Element | Detail |
|---|---|
| **Business goal** | Complete inventory reconciliation (typically annual) |
| **Departments involved** | Warehouse, Inventory Control, Accounting, Auditing |
| **NetSuite modules** | Inventory, Accounting |
| **Transactions** | Physical Count Worksheet, Inventory Adjustment |
| **Key decisions** | Count methodology; cutoff timing; valuation impact |
| **Documentation needed** | Physical Inventory Counts (this sprint), Valuation Methods (this sprint) |

### Process 6: Replenishment

```
Low stock alert → Reorder suggestion → Purchase Order → Receipt → Stock
```

| Element | Detail |
|---|---|
| **Business goal** | Maintain optimal stock levels automatically |
| **Departments involved** | Purchasing, Inventory Control |
| **NetSuite modules** | Inventory, Purchasing |
| **Transactions** | Reorder Point calculation, Suggested Purchase Orders |
| **Key decisions** | Reorder points vs. demand planning; safety stock levels |
| **Documentation needed** | Replenishment (this sprint), Saved Searches (completed) |

### Process 7: Inventory Adjustment

```
Identify discrepancy → Document reason → Adjust quantity → Review GL impact
```

| Element | Detail |
|---|---|
| **Business goal** | Correct inventory records to match physical reality |
| **Departments involved** | Warehouse, Inventory Control, Accounting |
| **NetSuite modules** | Inventory, Accounting |
| **Transactions** | Inventory Adjustment |
| **Key decisions** | Reason codes; approval workflow; dollar thresholds |
| **Documentation needed** | Inventory Adjustments (this sprint) |

### Process 8: Returns Processing

```
Customer returns → Return Authorization → Item Receipt → Inspection → Restock/Dispose
```

| Element | Detail |
|---|---|
| **Business goal** | Process customer returns efficiently |
| **Departments involved** | Customer Service, Warehouse, Quality, Accounting |
| **NetSuite modules** | Sales, Inventory, Order Management |
| **Transactions** | Return Authorization, Item Receipt, Credit Memo |
| **Key decisions** | Inspect before restock; disposition paths; restocking fees |
| **Documentation needed** | Receiving Inventory (this sprint), Order Management (future sprint) |

---

## Phase 6 — Learning Experience Design

### Module Structure as an Online Course

The Inventory module should feel like a structured course, not a collection of articles.

#### Section 1: Foundations (Beginner)

| Element | Detail |
|---|---|
| **Articles** | What Is Inventory Management, Item Records, Item Types, Locations |
| **Learning objective** | Understand what inventory is and how NetSuite models it |
| **Study time** | 45 minutes |
| **Exercise** | Create an inventory item record in a sandbox |
| **Knowledge check** | What item types exist? What is a location? |
| **Case study** | A company that grew from single to multi-location |

#### Section 2: Core Transactions (Beginner)

| Element | Detail |
|---|---|
| **Articles** | Inventory Transfers, Inventory Adjustments, Receiving Inventory, Fulfilling Orders |
| **Learning objective** | Process the four core inventory transactions |
| **Study time** | 60 minutes |
| **Exercise** | Create a transfer, an adjustment, a receipt, and a fulfillment in sandbox |
| **Knowledge check** | When do you use a transfer vs. an adjustment? |
| **Case study** | A warehouse that reduced errors by standardizing transfer workflows |

#### Section 3: Intermediate Operations (Intermediate)

| Element | Detail |
|---|---|
| **Articles** | Transfer Orders, Bin Management, Cycle Counting, Physical Inventory, Replenishment |
| **Learning objective** | Manage inventory operations beyond basic transactions |
| **Study time** | 90 minutes |
| **Exercise** | Set up a bin location, perform a cycle count |
| **Knowledge check** | What is the difference between cycle counting and physical inventory? |
| **Case study** | A distributor that reduced stockouts by 40% with replenishment |

#### Section 4: Valuation and Measurement (Intermediate)

| Element | Detail |
|---|---|
| **Articles** | Valuation Methods, Units of Measure, Lot and Serial Tracking, Landed Cost |
| **Learning objective** | Understand how inventory is valued and measured |
| **Study time** | 75 minutes |
| **Exercise** | Compare valuation methods on sample data |
| **Knowledge check** | What happens to COGS when you use average costing? |
| **Case study** | A manufacturer that switched from standard to average costing |

#### Section 5: Advanced Configuration (Advanced)

| Element | Detail |
|---|---|
| **Articles** | Feature Enablement, Multi-Location Setup, Matrix Items, Drop Ship / Special Order |
| **Learning objective** | Configure advanced inventory features |
| **Study time** | 60 minutes |
| **Exercise** | Enable Advanced Inventory in sandbox, configure a matrix item |
| **Knowledge check** | What features are irreversible? |
| **Case study** | Multi-location implementation for a retail chain |

#### Section 6: Mastery (Advanced)

| Element | Detail |
|---|---|
| **Articles** | Inventory Reporting, Inventory Best Practices, Common Mistakes, Glossary |
| **Learning objective** | Become an inventory expert |
| **Study time** | 45 minutes |
| **Exercise** | Design a daily inventory monitoring dashboard |
| **Knowledge check** | Identify 5 common mistakes and how to avoid them |
| **Capstone scenario** | Design a complete inventory setup for a distribution company |

### Recommended Knowledge Checks

Embedded in each article as a "Knowledge Check" section:

1. **True/False**: "An inventory adjustment changes the value of inventory on the balance sheet." (True)
2. **Multiple choice**: "Which transaction should you use to move stock between two warehouses with shipment tracking?" (Transfer Order)
3. **Scenario**: "Your customer service team needs to know whether an item is available to promise. Which quantity field should they check?" (Available, not On Hand)
4. **Scenario**: "You receive 100 units but only 90 are usable. How do you record the 10 damaged units?" (Adjustment with reason code)

### Troubleshooting Labs

Each operational article should include a "Troubleshooting Lab" section:

| Lab | Article |
|---|---|
| Transfer quantities don't match | Inventory Transfers |
| Adjustment didn't post to GL | Inventory Adjustments |
| Item receipt shows wrong quantity | Receiving Inventory |
| Fulfillment can't find available stock | Fulfilling Orders |
| Cycle count variance exceeds threshold | Cycle Counting |
| Replenishment suggests wrong quantity | Replenishment |

---

## Phase 7 — Future Growth

### Modules That Branch from Inventory

This map shows which future modules naturally depend on Inventory knowledge.

```
Inventory Module (this sprint)
    │
    ├──→ Purchasing Module (future)
    │     Purchase orders, vendor management, receiving, procurement
    │     Dependency: Needs inventory for item records and locations
    │
    ├──→ Order Management / Sales Module (future)
    │     Sales orders, fulfillment, returns, availability
    │     Dependency: Needs inventory for availability and fulfillment
    │
    ├──→ Manufacturing Module (future)
    │     Assembly items, BOM, work orders, production
    │     Dependency: Needs inventory for component tracking and build orders
    │
    ├──→ Warehouse Management (future)
    │     WMS, directed putaway, wave picking, RF scanning
    │     Dependency: Needs inventory for bin management and transfers
    │
    ├──→ Advanced Inventory (future)
    │     Lot/serial depth, matrix items, landed cost advanced
    │     Dependency: Needs inventory basics
    │
    ├──→ Inventory Accounting (future)
    │     Valuation deep dive, COGS analysis, period-end inventory
    │     Dependency: Needs inventory for valuation and adjustments
    │
    └──→ Supply Chain Planning (future)
          Demand forecasting, replenishment optimization, safety stock
          Dependency: Needs inventory for reorder history and stock data
```

### Documentation Integration Points for Future Sprints

Each article in this sprint should include forward references where future modules will connect:

| Current Article | Future Integration Point |
|---|---|
| Receiving Inventory | "Vendor returns and purchase order matching are covered in the Purchasing module (planned)" |
| Fulfilling Orders | "Sales order management and backorder handling are covered in the Sales module (planned)" |
| Item Types — Assembly | "Assembly items and bills of materials are covered in the Manufacturing module (planned)" |
| Inventory Valuation | "Period-end inventory valuation and COGS reconciliation are covered in the Accounting module (planned)" |
| Inventory Reporting | "SuiteAnalytics workbooks for inventory analysis are covered in the SuiteAnalytics module (planned)" |
| Replenishment | "Demand planning and forecasting are future topics" |
| Landed Cost | "Advanced landed cost allocation methods are future topics" |

### Recommendations for Future Sprints

1. **Prioritize Purchasing after Inventory** — The purchase-to-stock process is the most common inventory inflow. Without purchasing documentation, the Inventory module is incomplete.
2. **Prioritize Sales/Order Management after Purchasing** — The order-to-fulfill process is the most common inventory outflow.
3. **Manufacturing should follow both** — Manufacturing depends on Inventory, Purchasing, and basic accounting understanding.
4. **WMS should follow Manufacturing** — WMS is an advanced feature that builds on Inventory and Manufacturing.

---

## Summary

| Dimension | Value |
|---|---|
| **Total articles planned** | 27 (1 README + 26 articles) |
| **Estimated content volume** | ~7,450 lines |
| **Estimated effort** | 34-41 hours |
| **Beginner articles** | 9 |
| **Intermediate articles** | 10 |
| **Advanced articles** | 6 |
| **Reference articles** | 2 |
| **Business workflows mapped** | 8 |
| **ERP module connections** | 12 |
| **Knowledge checks** | 12 |
| **Troubleshooting labs** | 8 |
| **Case studies** | 6 |
| **Capstone scenario** | 1 |

### Recommended Implementation Order

```
Phase A: Rewrite existing articles (2 hours)
  ├─ Update overview.md to new standards format
  ├─ Update inventory-transfers.md to new standards format
  └─ Add cross-links to getting-started module

Phase B: Foundation — Beginner tier (10-12 hours)
  ├─ README, What Is Inventory Management, Item Records, Item Types
  ├─ Locations, Inventory Adjustments
  ├─ Receiving Inventory, Fulfilling Orders
  └─ Cross-links to getting-started

Phase C: Operations — Intermediate tier (14-16 hours)
  ├─ Transfer Orders, Bin Management
  ├─ Cycle Counting, Physical Inventory
  ├─ Replenishment, Valuation Methods
  ├─ Units of Measure, Lot/Serial, Landed Cost
  └─ Inventory Reporting

Phase D: Configuration — Advanced tier (8-10 hours)
  ├─ Feature Enablement, Multi-Location Setup
  ├─ Matrix Items, Landed Cost Advanced
  ├─ Drop Ship/Special Orders
  └─ Best Practices

Phase E: Reference + Polish (2-3 hours)
  ├─ Common Mistakes, Glossary
  ├─ Cross-link audit
  ├─ Update docs/README.md
  └─ Update tracking files
```

### Verdict

The Inventory module is the single most important content release remaining. It is the most interconnected module — no other module touches as many parts of NetSuite. Getting the Inventory learning path right will make every future module easier to write because the Inventory article network provides the operational foundation that Purchasing, Sales, Manufacturing, and Accounting all depend on.

> **Would someone who completed this learning path truly understand how inventory works within an ERP — not just how to click through NetSuite?**
>
> **Yes.** The curriculum is designed around business processes, not features. Each article teaches why inventory exists and how it connects to other modules before showing steps. Case studies and knowledge checks reinforce business thinking. The module emphasizes that inventory is not a standalone function — it is the center of a network that includes purchasing, sales, manufacturing, accounting, and reporting.