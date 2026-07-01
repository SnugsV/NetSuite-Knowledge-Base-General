---
title: Costing Methods
module: Inventory
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Costing Methods

## Quick Summary

A costing method determines how the cost of inventory is calculated when items are received and how that cost is relieved when items are sold. The choice of costing method affects financial statements, tax liability, pricing decisions, and profitability analysis.

## Difficulty

Advanced

## Estimated Time

20 minutes

## Business Question

"How should I value my inventory, and how much profit did I actually make on each sale?"

## Overview

When you receive inventory, you pay a price. When you sell that inventory, you record the cost of goods sold. The difference between the selling price and the cost is profit. But if you received the same item at different prices on different days, which cost applies to each sale? The costing method answers that question.

## Available Costing Methods

### Average Cost

**How it works**: Every time inventory is received, the total cost of all units on hand is divided by the total quantity. The result is the new average cost. All units are valued at this average until the next receipt.

**Calculation**:
```
Before receipt: 100 units @ $10.00 = $1,000.00
Receipt:        50 units @ $12.00 = $600.00
After receipt:  150 units @ $10.67 = $1,600.00
Next sale of 10 units: COGS = 10 × $10.67 = $106.70
```

**Best for**: Most businesses. Simple, predictable, smooths out price fluctuations.

### Standard Cost

**How it works**: A fixed cost is assigned to each item. Variances between the standard cost and the actual purchase price are recorded in variance accounts.

**Calculation**:
```
Standard cost: $10.00
Receipt: 100 units @ $12.00 = $1,200.00
Inventory value recorded: 100 × $10.00 = $1,000.00
Purchase price variance: $200.00 (goes to variance account)
COGS on sale of 10 units: 10 × $10.00 = $100.00
```

**Best for**: Manufacturing. Provides a stable cost basis for pricing and production decisions.

### FIFO (First In, First Out)

**How it works**: The oldest units are assumed to be sold first. Cost follows the physical flow of goods.

**Calculation**:
```
Layer 1: 100 units @ $10.00 (oldest)
Layer 2: 100 units @ $12.00 (newest)
Sale of 120 units: 100 × $10.00 + 20 × $12.00 = $1,240.00 COGS
Remaining: 80 units @ $12.00 = $960.00
```

**Best for**: Perishable goods, businesses where physical flow matches FIFO, rising cost environments.

### LIFO (Last In, First Out)

**How it works**: The newest units are assumed to be sold first. Less common outside the US.

**Calculation**:
```
Layer 1: 100 units @ $10.00 (oldest)
Layer 2: 100 units @ $12.00 (newest)
Sale of 120 units: 100 × $12.00 + 20 × $10.00 = $1,400.00 COGS
Remaining: 80 units @ $10.00 = $800.00
```

**Best for**: Tax optimization in the US (LIFO often results in higher COGS and lower taxable income in inflationary periods).

### Specific Cost

**How it works**: Each unit or lot has its own identified cost. When sold, the specific cost of that unit is used.

**Best for**: High-value, unique items (vehicles, jewelry, customized equipment).

## Decision Framework

| Business Characteristic | Recommended Method |
|---|---|
| Stable prices, simple operations | Average Cost |
| Manufacturing with BOM | Standard Cost |
| Perishable goods, rising prices | FIFO |
| Tax optimization (US only) | LIFO |
| Unique high-value items | Specific Cost |
| Multiple currencies, global operations | Average Cost or FIFO |

## How Costing Method Affects Financial Statements

| Method | COGS in Rising Price Environment | Inventory Asset | Tax Impact (US) |
|---|---|---|---|
| FIFO | Lower COGS | Higher inventory value | Higher taxable income |
| LIFO | Higher COGS | Lower inventory value | Lower taxable income |
| Average | Between FIFO and LIFO | Between FIFO and LIFO | Between FIFO and LIFO |
| Standard | Depends on variance frequency | Depends on variance frequency | Requires variance management |

## Changing Costing Methods

Changing the costing method for an item that has transaction history is:

- **Difficult**: Most businesses cannot change methods mid-year without significant accounting effort
- **Not supported in all cases**: NetSuite may not allow changing methods once transactions exist
- **Financially significant**: A method change can materially affect reported earnings

**Choose your costing method before entering inventory transactions.**

## Business Example

A distributor experiences rising costs. In January, Widget A costs $10. In June, it costs $12. In December, it costs $14. They sell 1,000 units per month.

| Method | COGS (Full Year) | Ending Inventory Value | Net Income Impact |
|---|---|---|---|
| FIFO | $130,000 | $14,000 (highest) | Highest profit |
| LIFO | $150,000 | $10,000 (lowest) | Lowest profit |
| Average | $140,000 | $12,000 | Middle |

The distributor chooses **Average Cost** for simplicity and reasonable financial reporting.

## Common Costly Mistakes

- **Choosing a method without understanding financial impact**: The same business can report significantly different profits under FIFO vs. LIFO
- **Changing methods mid-year**: Creates audit issues and restated financial statements
- **Using Standard Cost without variance management**: Unmanaged variances accumulate and distort financial reporting
- **Not considering the physical flow**: FIFO makes sense when older inventory is physically sold first. If the newest inventory is sold first, FIFO may not match physical operations
- **Assuming one method fits all items**: Different item categories can use different costing methods, though this adds complexity

## Best Practices

- Choose costing methods during implementation — changing later is difficult
- Document the rationale for each method choice
- For manufacturing, use Standard Cost with regular variance review intervals
- For distribution, Average Cost or FIFO is typically simplest
- Review costing method impact quarterly to ensure the choice still fits the business
- Use Saved Searches to monitor large cost variances

## Knowledge Check

1. A company receives 100 units at $8 and later 100 units at $12. Using FIFO, what is COGS for selling 150 units? (Answer: 100 × $8 + 50 × $12 = $1,400.)
2. **Decision**: Your company manufactures furniture with stable component costs. Which method? (Answer: Standard Cost — stable cost basis for production pricing.)
3. **Scenario**: In a period of rising costs, which method reports the highest inventory asset value? (Answer: FIFO — the newest (most expensive) units remain in inventory.)

## Related Articles

- [Inventory Concepts](../inventory-concepts.md)
- [Landed Cost](landed-cost.md)
- [Multi-Location Strategy](multi-location-strategy.md)
- [Inventory Best Practices](inventory-best-practices.md)
- [Cost Accounting](../accounting/cost-accounting.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Costing Methods](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Average Costing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Standard Costing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)