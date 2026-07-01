---
title: Units of Measure
module: Inventory
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Units of Measure

## Quick Summary

Units of measure (UOM) define how items are counted, purchased, stored, and sold. NetSuite supports multiple UOMs per item with conversion rates, allowing an item to be purchased by the case, stored by the each, and sold by the dozen — with NetSuite automatically converting between them.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Inventory items can be measured in different units depending on the business process. A manufacturer buys chemicals by the liter, stores them by the liter, but uses them by the milliliter in production. A distributor buys furniture by the container, sells by the piece, and ships by the box.

NetSuite's UOM system manages these conversions automatically.

## UOM Types

Each item can have up to three UOM types:

| UOM Type | Purpose | Example |
|---|---|---|
| **Stock Unit** | The base unit for quantity tracking. All quantities (On Hand, Available, etc.) are stored in this unit. | "Each" for a chair |
| **Purchase Unit** | The unit used when buying from a supplier. Must be convertible to the stock unit. | "Pallet" (24 chairs per pallet) |
| **Sales Unit** | The unit used when selling to customers. Must be convertible to the stock unit. | "Each" for a single chair |

## UOM Conversions

When you define a purchase unit or sales unit that differs from the stock unit, you must define a conversion rate.

| Conversion | Example |
|---|---|
| **Stock Unit** | 1 Each |
| **Purchase Unit** | 1 Case = 12 Each (conversion: 12) |
| **Sales Unit** | 1 Each = 1 Each (conversion: 1) |

NetSuite automatically converts quantities:

- You purchase 5 Cases → NetSuite adds 60 to On Hand (5 × 12)
- You sell 3 Each → NetSuite subtracts 3 from On Hand

## Common UOM Scenarios

| Scenario | Stock Unit | Purchase Unit | Sales Unit |
|---|---|---|---|
| Retail product | Each | Case (12) | Each |
| Bulk chemicals | Liter | Drum (200) | Milliliter (0.001) |
| Hardware distribution | Each | Box (50) | Each |
| Food service | Kilogram | Pallet (500) | Gram (0.001) |
| Cable/wire | Meter | Reel (100) | Meter |

## Setting Up UOMs

UOM definitions are created at:

```
Setup > Accounting > Units of Measure > New
```

When creating a UOM, you define:

1. **UOM Group** — A collection of related units (e.g., "Weight" for kg, g, lb)
2. **Base Unit** — The primary unit for the group (e.g., "Each" for count)
3. **Conversion Rates** — How other units relate to the base

Common UOM groups:

| Group | Units |
|---|---|
| **Count** | Each, Dozen (12), Case (12), Pallet (48), Box (24) |
| **Weight** | Kilogram, Gram, Pound, Ounce, Tonne |
| **Volume** | Liter, Milliliter, Gallon, Quart |
| **Length** | Meter, Centimeter, Inch, Foot, Yard |
| **Area** | Square Meter, Square Foot |

## UOM on Transactions

When creating a transaction, the UOM can be changed as long as the requested quantity can be converted to the stock unit. If a conversion does not exist, NetSuite will not allow the transaction.

**Example**: An item with stock unit "Each" and no conversion to "Kilogram" — you cannot enter a transaction in kilograms.

## Fractional UOM

Some units support fractional quantities (e.g., 0.5 meters of cable). Others do not (0.5 chairs cannot be sold). NetSuite allows you to specify whether a UOM supports fractional quantities.

## Common Mistakes

- **Not defining conversions correctly**: If 1 Case = 12 Each, the conversion rate is 12. Entering 0.0833 (1/12) instead will cause incorrect quantities.
- **Using incompatible UOM groups on transactions**: If you try to sell by weight when only count conversions are defined, the transaction will fail.
- **Assuming all items use the same UOM**: Each item can have different UOMs. A distributor may buy some items by the case and others by the pallet.
- **Not setting a stock unit**: Every inventory item must have a defined stock unit.

## Best Practices

- Define UOM groups before creating items. It is easier to select from existing groups than to create them ad hoc.
- Use UOM groups that reflect your actual business processes. If you never buy by the pallet, do not define pallet conversions.
- Test UOM conversions in a sandbox before using in production.
- Document any non-standard conversions for your team.
- Review UOM configurations during periodic system audits.

## Related Articles

- [Item Records](item-records.md)
- [Item Types](item-types.md)
- [Inventory Concepts](inventory-concepts.md)
- [What Is Inventory Management?](what-is-inventory.md)

## Oracle References

- [Oracle NetSuite Help Center: Units of Measure](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Setting Up Units of Measure](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)