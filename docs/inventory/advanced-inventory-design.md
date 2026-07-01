---
title: Advanced Inventory Design
module: Inventory
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Advanced Inventory Design

## Quick Summary

Advanced Inventory design involves making architectural decisions about how inventory features are structured — which features to enable, how to organize items and locations, and how to plan for growth. These decisions are difficult to reverse and affect every downstream module.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Business Question

"How should I design my NetSuite inventory architecture to avoid expensive redesigns later?"

## Overview

Inventory configuration decisions made during implementation have long-lasting consequences. Enabling a feature, choosing a costing method, or setting up locations may be straightforward today — but changing them after transactions exist can be extremely difficult or impossible.

This article guides the design decisions that should be made before entering inventory transactions.

## Feature Enablement Decisions

| Feature | Reversible? | Considerations |
|---|---|---|
| Inventory Management | Yes | Foundation feature. Must be enabled. |
| Multi-Location Inventory | No (with transactions) | Enable early even if not immediately used |
| Advanced Inventory | No (with transactions) | Enables bins, lots, serials, matrix items |
| WMS | No (with transactions) | Significant operational impact |
| Multi-Currency | No | Affects purchasing, sales, inventory valuation |
| Multi-Book Accounting | No | Affects inventory valuation reporting |

**Principle**: Enable features before transactions exist. This is much easier than enabling them later.

## Architecture Decision: Items and Locations

### Item Record Design

| Decision | Consideration |
|---|---|
| **Item numbering scheme** | Consistent SKU format prevents confusion. Design before creating items. |
| **Item templates** | Create templates for each item category to ensure consistent field population. |
| **Custom fields** | Add business-specific fields early. Adding later requires updating existing items. |
| **Item groups / categories** | Define categories that match how the business analyzes inventory. |

### Location Design

| Decision | Consideration |
|---|---|
| **Location count and types** | Start with the locations you need now, but design for future locations. |
| **Location naming convention** | Consistent location names prevent errors in transaction entry. |
| **Location hierarchy** | Parent-child location relationships affect reporting. Plan the structure. |
| **Bin naming convention** | Bin names should be intuitive to warehouse staff. Change-resistant once implemented. |

## Feature Interaction Map

Some features require others. Understanding dependencies prevents surprises:

```
Inventory Management
  └── Multi-Location Inventory
        └── Advanced Inventory
              ├── Bin Management
              ├── Lot Tracking
              ├── Serial Tracking
              └── Matrix Items
                    └── WMS
                          └── Directed Putaway
                          └── Wave Picking
                          └── RF Scanning
```

Each level adds complexity. Only go as deep as the business requires.

## Implementation Phasing

Implement advanced inventory in phases, not all at once:

| Phase | Duration | Features |
|---|---|---|
| **Foundation** | Week 1-2 | Inventory Management, item records, locations |
| **Multi-Location** | Week 3-4 | Enable feature, set up all locations, train on transfers |
| **Advanced** | Week 5-8 | Enable Advanced Inventory, implement bins, lots, or serials as needed |
| **WMS (if applicable)** | Week 9-16 | RF scanning, directed putaway, wave picking |

## Testing Strategy

Before going live with advanced features:

1. **Sandbox testing**: Configure everything in a sandbox first
2. **Process walkthrough**: Execute every inventory process that will be used in production
3. **Integration testing**: Test downstream impacts on purchasing, sales, manufacturing, and accounting
4. **User acceptance testing**: Warehouse staff should test and approve before go-live
5. **Parallel run**: Run both old and new processes for a transition period

## Business Example

A growing distributor is moving from a single warehouse to 3 regional locations.

**Architecture decisions**:

1. Enable Multi-Location Inventory before creating any transactions — even though they only have one location today
2. Use a consistent location naming convention: REGION-LOCATION-TYPE (e.g., NE-BOS-WH for Northeast-Boston-Warehouse)
3. Enable Advanced Inventory for future bin management, but do not implement bins until needed
4. Create item templates for each category (Furniture, Electronics, Consumables) to ensure consistent item records
5. Do not enable WMS — the operational complexity is not justified for their volume

**Result**: 18 months later, when the company opens a 4th location and adds bin management, the features are already enabled — they just need to configure and train.

## Common Costly Mistakes

- **Enabling features reactively**: Waiting until you need a feature to enable it often means facing irreversible consequences with existing data
- **Skipping the item template design**: Without templates, item records are inconsistent, causing reporting and integration issues
- **No item numbering convention**: SKU formats that change over time create confusion for purchasing, sales, and warehouse teams
- **Designing for today only**: Locations, bins, and item structures that work for 500 SKUs may break at 5,000 SKUs
- **Not documenting architecture decisions**: When the original implementer is gone, undocumented decisions become mysterious constraints

## Best Practices

- Enable Multi-Location and Advanced Inventory features during initial implementation, even if not immediately used
- Design item numbering and location naming conventions before creating any records
- Create item templates for each category
- Document every architecture decision and the rationale
- Test advanced features in a sandbox before enabling in production
- Phase implementation — do not enable everything at once
- Train warehouse staff on each new feature before going live

## Knowledge Check

1. You are implementing NetSuite for a company with one warehouse that may add a second in 2 years. Should you enable Multi-Location Inventory now? (Answer: Yes — enable it before any transactions exist.)
2. **Scenario**: A company enabled Advanced Inventory after 2 years of transactions. What issues might they face? (Answer: Existing items must be updated. Historical transactions cannot be retroactively binned/lotted. Some design changes require data migration.)
3. **Decision**: A small retailer with 200 SKUs and one store is evaluating WMS. Is this the right time? (Answer: No — WMS is designed for high-volume warehouse operations. The complexity exceeds the benefit.)

## Related Articles

- [Inventory Best Practices](inventory-best-practices.md)
- [Multi-Location Strategy](multi-location-strategy.md)
- [Bin Management](bin-management.md)
- [Costing Methods](costing-methods.md)
- [Enabled Features](../administration/enabled-features.md)

## Oracle References

- [Oracle NetSuite Help Center: Inventory Setup](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Feature Enablement Guide](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)