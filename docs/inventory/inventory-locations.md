---
title: Inventory Locations
module: Inventory
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Inventory Locations

## Quick Summary

A location in NetSuite is a place where inventory is stored, received, or fulfilled. Locations can represent warehouses, retail stores, distribution centers, docks, trucks, or any physical place where stock exists. Proper location setup is essential for accurate inventory tracking.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

Every inventory item in NetSuite can be tracked by location. When you receive inventory, you specify which location it goes to. When you transfer inventory, you specify the source and destination locations. When you fulfill an order, you specify which location the items ship from.

Without locations, all inventory exists in a single abstract pool — you know you have 100 units, but you do not know where they are.

## Why Locations Matter

| Without Locations | With Locations |
|---|---|
| You know total quantity but not where it is | You know quantity at each warehouse |
| Transfers are not tracked | Every movement is recorded |
| Reporting shows one aggregate value | Reporting shows location-level detail |
| Multi-site operations are impossible | Multi-site operations are fully supported |

## Location Types

NetSuite supports several location types:

| Type | Example |
|---|---|
| **Warehouse** | A distribution center where bulk inventory is stored |
| **Store** | A retail location with point-of-sale inventory |
| **Dock** | A receiving or shipping dock within a warehouse |
| **Van / Truck** | Mobile inventory (delivery trucks, service vans) |
| **Partner Location** | A third-party warehouse or fulfillment center |
| **Subsidiary** | A location tied to a OneWorld subsidiary |

## Setting Up Locations

Locations are created and managed at:

```
Setup > Company > Locations > New
```

When creating a location, you define:

| Field | Purpose |
|---|---|
| **Name** | The display name (e.g., "Chicago Warehouse") |
| **Type** | Warehouse, store, dock, etc. |
| **Address** | Physical address of the location |
| **Parent Location** | If this is a sub-location within another location |
| **Inactive** | Whether the location is available for new transactions |

## Multi-Location Inventory

Multi-Location Inventory is a NetSuite feature that must be enabled before you can track inventory by location. When enabled:

- Every inventory transaction requires a location
- Quantities are tracked per location
- Reports can be filtered by location
- Transfers between locations are tracked

See the Administration module for feature enablement guidance.

## Bin Management

Bins are sub-locations within a location — specific shelves, aisles, or areas where inventory is stored. Bin management requires the Advanced Inventory feature.

**Without bins**: You know an item is in the Chicago warehouse, but you do not know which aisle or shelf.

**With bins**: You know the item is in Chicago Warehouse, Aisle 3, Shelf B, Bin 12.

Bins are useful for:

- Warehouse pick-path optimization
- Organized put-away
- Cycle counting by area
- Directed put-away and wave picking (with WMS)

## Location-Level Costs

When average cost is used, each location may have a different average cost for the same item. This happens when items are received at different prices into different locations.

Example:

| Location | Units | Total Cost | Average Cost |
|---|---|---|---|
| Chicago | 100 | $1,000 | $10.00 |
| Atlanta | 50 | $600 | $12.00 |

When inventory is transferred from Chicago to Atlanta, a cost variance may be recorded because the average costs differ.

## Default Location

Each item record has a default location. When creating transactions, this location is pre-populated but can be changed.

## Location Reporting

With locations configured, you can run location-level reports:

- Stock status by location
- Inventory valuation by location
- Transfer history between locations
- Location-level replenishment

## Common Mistakes

- **Not setting up locations at all**: Without locations, all inventory exists in a single pool. This makes multi-site operations impossible and single-site reporting less useful.
- **Creating too many locations too quickly**: Start with your primary warehouses and add locations as needed. Too many locations too early adds unnecessary complexity.
- **Not enabling Multi-Location Inventory before entering transactions**: If you receive inventory without the feature enabled, location data will not be captured.
- **Confusing locations with bins**: Locations are warehouses or stores. Bins are sub-locations within a location.

## Best Practices

- Set up locations even if you have only one warehouse. It prepares your system for growth.
- Use descriptive location names that reflect business function (e.g., "Chicago — Main Warehouse").
- Enable Multi-Location Inventory before entering any inventory transactions.
- For multi-site companies, set up all locations during the initial implementation.
- Use bin management for warehouses with large, diverse inventory.

## Related Articles

- [What Is Inventory Management?](what-is-inventory.md)
- [Inventory Concepts](inventory-concepts.md)
- [Item Records](item-records.md)
- [Lists and Records](../getting-started/lists-and-records.md)
- [Administration module](../administration/README.md) (future)

## Oracle References

- [Oracle NetSuite Help Center: Locations](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Multi-Location Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)