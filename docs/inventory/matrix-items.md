---
title: Matrix Items
module: Inventory
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Matrix Items

## Quick Summary

A matrix item represents a product with multiple variations — such as size, color, or material — as a single item record with child items for each variation. Matrix items simplify item management for product lines with many configurations.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Business Question

"How do I manage 200 T-shirt variations without creating 200 separate item records?"

## Overview

A clothing company sells T-shirts in 5 sizes and 10 colors. That is 50 unique SKUs. Without matrix items, each SKU is a separate item record. With matrix items, one parent record (the T-shirt) manages all 50 child records, with the size and color as configurable dimensions.

## When to Use Matrix Items

| Situation | Recommendation |
|---|---|
| Product with 2+ variation dimensions (size, color, material) | Matrix item |
| Product with 1 variation dimension (e.g., 5 sizes, 1 color) | Matrix item or individual items |
| Fewer than 5 total variations | Individual items may be simpler |
| Variations that are functionally the same product | Matrix item |
| Variations that are completely different products | Individual items |

## When Not to Use Matrix Items

- **Items with zero variations**: A single product with no configurable options is not a matrix item
- **Completely different products grouped artificially**: A "blue chair" and a "red table" are not variations of the same product
- **Custom-configured products**: Products where each unit is unique (configure-to-order) are better served by other methods
- **Small product lines**: If a product has 3 variations, managing separate item records may be simpler

## Trade-Offs

| Gained | Complexity Introduced |
|---|---|
| Single record manages all variations | Matrix setup requires planning |
| Inventory reporting by parent item | Child items cannot exist without the parent |
| Pricing and description managed centrally | Matrix items require Advanced Inventory |
| Searchable by dimension (size, color) | Transactions may need dimension-level selection |
| Simplified item creation for new variations | Adding a new dimension later is complex |

## Matrix Structure

```
Parent Item: "Cotton T-Shirt"
Dimensions: Size, Color

Child Items (examples):
  T-SHIRT-SML-BLK    (Size: Small, Color: Black)
  T-SHIRT-MED-BLK    (Size: Medium, Color: Black)
  T-SHIRT-LRG-BLK    (Size: Large, Color: Black)
  T-SHIRT-SML-WHT    (Size: Small, Color: White)
  ...
```

Each child item is a separate inventory item with its own:
- Item record and SKU
- Quantity on hand
- Pricing (optional override from parent)
- Vendor information

## Dimensions and Child Item Generation

Dimensions define the variations. Common dimensions:

| Product | Dimensions |
|---|---|
| Clothing | Size, Color |
| Furniture | Material, Finish |
| Hardware | Diameter, Length |
| Packaging | Size, Material |

When dimensions are defined, NetSuite can auto-generate the child items for every combination. For 5 sizes × 10 colors = 50 child items created automatically.

## Matrix Item Pricing

Pricing for matrix items can be set at:

- **Parent level**: All child items share the same price
- **Child level**: Each variation has its own price
- **Dimension level**: All items with a specific dimension value share a price (e.g., all Extra Large sizes cost $2 more)
- **Combination**: Base price at parent, surcharges per dimension

## Reporting with Matrix Items

Matrix items enable reporting by product line, not just by SKU:

- Total inventory value of all T-shirt variations
- Sales by product line (all T-shirt sales aggregated)
- Best-selling size regardless of color
- Worst-selling color regardless of size

Without matrix items, these reports would require grouping 50 separate item records.

## Business Example

An apparel company launches a new fleece jacket in 4 sizes (S, M, L, XL) and 6 colors (Black, Navy, Red, Green, Grey, White). That is 24 SKUs.

**Without matrix items**: Create 24 item records manually. Reports must be grouped manually. Adding a new color (25th item) requires creating another item record.

**With matrix items**:
1. Create one parent item "Performance Fleece Jacket"
2. Define dimensions: Size, Color
3. Generate 24 child items automatically
4. Set base price at parent level
5. Later, add a "Tall" size: 5 sizes × 6 colors = 30 child items. The system generates 6 new child items automatically (5 → 6 sizes, keeping all 6 colors).

## Common Costly Mistakes

- **Too many dimensions**: 4 dimensions × 5 values each = 625 child items. Consider whether all combinations are realistic.
- **Dimensions that change frequently**: A "Season" dimension that changes every 6 months requires re-creating child items
- **Not planning SKU naming**: R-SPK-BLK-US is hard to read. Use a consistent naming convention: CATEGORY-SIZE-COLOR-REGION
- **Matrix items without matrix reporting**: If nobody uses the roll-up reports, the matrix structure adds complexity without value

## Best Practices

- Limit to 2-3 dimensions per matrix. More than 3 generates too many child items.
- Plan SKU naming before creating the matrix — child item names are generated from the pattern
- Use dimension-level pricing when specific variations have different costs
- Use parent-level pricing when all variations cost the same
- Review matrix item sales by dimension to identify slow-moving variations
- Archive (inactivate) child items that are discontinued rather than deleting them

## Knowledge Check

1. A shoe company sells 12 sizes and 8 colors for each model. How many child items per shoe model? (Answer: 96 — 12 × 8.)
2. **Decision**: A furniture company sells tables in 3 sizes and 4 finishes. Should they use matrix items? (Answer: Yes — 12 child items benefit from centralized management and roll-up reporting.)
3. **Scenario**: A matrix item has 50 child items, but 10 have never sold. What should you do? (Answer: Investigate — are they valid combinations that need merchandising, or are they invalid combinations that should be inactivated?)

## Related Articles

- [Item Types](../item-types.md)
- [Item Records](../item-records.md)
- [Inventory Concepts](../inventory-concepts.md)
- [Pricing](../sales/pricing.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Matrix Items](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Matrix Item Setup](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)