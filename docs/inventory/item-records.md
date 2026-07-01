---
title: Item Records
module: Inventory
difficulty: Beginner
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Item Records

## Quick Summary

An item record is the master data that represents a product, part, material, or service in NetSuite. Every inventory transaction — purchasing, selling, transferring, manufacturing, adjusting — references an item record. Getting item records right is the foundation of accurate inventory management.

## Difficulty

Beginner

## Estimated Time

15 minutes

## Overview

If inventory is the operational center of NetSuite, item records are the building blocks. An item record defines what the item is, how it behaves, how it is costed, how it is sold, and how it is tracked.

A well-configured item record contains:

- Identifying information (name, SKU, description)
- Type (inventory, non-inventory, service, kit, assembly)
- Financial information (cost, price, tax code, income/expense accounts)
- Operational information (location, bin, unit of measure)
- Classification information (department, class, category)

## Creating an Item Record

Items are created and managed from:

```
Lists > Accounting > Items > New
```

The item type selection is the first and most important decision. See [Item Types](item-types.md) for guidance on choosing the right type.

## Key Fields on an Item Record

### Identification

| Field | Purpose | Example |
|---|---|---|
| **Item Name** | The display name used throughout NetSuite | "Ergonomic Office Chair" |
| **Item Number / SKU** | The unique identifier for the item | "CHR-ERG-001" |
| **Description** | Detailed description shown on transactions | "Adjustable lumbar support, black mesh" |
| **Display Name** | Name shown on sales forms (can differ from item name) | "Office Chair, Ergonomic" |
| **Vendor Name** | The vendor's name for this item | "ChairCo Model X100" |

### Inventory-Specific Fields

| Field | Purpose |
|---|---|
| **Quantity On Hand** | Current stock level (system-calculated) |
| **Units of Measure** | Stock unit, purchase unit, sale unit |
| **Cost** | Current cost (system-calculated based on valuation method) |
| **Location** | Default storage location |
| **Reorder Point** | Minimum quantity before replenishment is suggested |
| **Preferred Stock Level** | Target quantity for replenishment |

### Financial Fields

| Field | Purpose |
|---|---|
| **Income Account** | Revenue account credited when the item is sold |
| **Expense Account** | COGS account debited when the item is sold |
| **Asset Account** | Inventory asset account where value is held |
| **Tax Schedule** | Default tax treatment for this item |
| **Sales Price** | Default selling price |

### Classification Fields

| Field | Purpose |
|---|---|
| **Department** | Department responsible for this item |
| **Class** | Classification for reporting |
| **Category** | Product grouping (e.g., "Furniture," "Electronics") |

## Item Record Templates

For items that share common attributes (same income account, same tax treatment, same classification), you can create item record templates. Templates pre-populate shared fields so each new item starts with the correct defaults.

Templates are created at:

```
Lists > Accounting > Items > New > Use Template
```

## Item Status

Item records can have different statuses that control their behavior:

| Status | Meaning |
|---|---|
| **Active** | Item can be used on transactions, appears in lists |
| **Inactive** | Item cannot be used on new transactions, but existing transactions remain |
| **Pending** | Item is being set up and is not yet available |

See [Inventory Status](inventory-status.md) for more detail.

## Item Subtab: Key Sections

Each item record has subtabs that organize related information:

| Subtab | What It Contains |
|---|---|
| **Item** | Name, description, classification |
| **Purchasing** | Purchase unit, vendor, lead time, preferred vendor |
| **Sales** | Sales price, tax schedule, revenue recognition |
| **Inventory** | Locations, quantities, reorder points, bin assignments |
| **Accounting** | Accounts, valuation method, tax treatment |
| **Custom** | Custom fields specific to your organization |

## Common Mistakes

- **Not setting the correct item type**: Choosing "Non-Inventory" when you need "Inventory" means NetSuite will not track quantities. This is one of the most common and most consequential errors.
- **Missing account assignments**: Without income, expense, or asset accounts, transactions referencing the item may fail to post to the general ledger.
- **Duplicate item records**: The same product entered under different names or SKUs creates reporting and inventory accuracy issues.
- **Not using templates**: Creating items without templates means entering the same accounts and classifications repeatedly, increasing the chance of errors.
- **Inactive items not cleaned up**: Items that are no longer used should be marked inactive to avoid cluttering lists and reports.

## Best Practices

- Use a consistent naming and SKU convention from day one.
- Set up item record templates for each category of item.
- Assign all required accounts (income, expense, asset) when creating the item record.
- Review item records periodically and mark obsolete items as inactive.
- Use custom fields to capture business-specific information.
- Test new item configurations in a sandbox before implementing in production.

## Knowledge Check

1. You create a new item but forget to assign the Asset Account. When you receive this item, what happens? (Answer: The receipt may fail to post to the general ledger, or the value may post to an incorrect account.)
2. Your purchasing department needs to know the vendor's item number. Where should this be recorded? (Answer: The Vendor Name field on the item record, or a custom field on the Purchasing subtab.)

## Related Articles

- [Item Types](item-types.md)
- [What Is Inventory Management?](what-is-inventory.md)
- [Inventory Concepts](inventory-concepts.md)
- [Inventory Locations](inventory-locations.md)
- [Units of Measure](units-of-measure.md)
- [Inventory Status](inventory-status.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Item Records](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Creating Items](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)