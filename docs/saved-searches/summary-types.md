---
title: Summary Types
module: Saved Searches
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Summary Types

## Quick Summary

Summary types transform individual rows into grouped, aggregated results — sums, counts, averages, minimums, maximums. They turn a list of records into meaningful business metrics.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Overview

By default, a Saved Search returns one row per matching record. With Summary Types, you group records by common values and calculate aggregated metrics for each group.

Instead of "100 individual sales orders," you get "Total revenue by customer" or "Order count by month."

## Available Summary Types

| Type | What It Does | Example |
|---|---|---|
| **Sum** | Adds up numeric values | Total revenue by customer |
| **Count** | Counts number of records | Number of orders per month |
| **Average** | Calculates the mean | Average order value by rep |
| **Minimum** | Finds the smallest value | Earliest order date by customer |
| **Maximum** | Finds the largest value | Largest order by customer |
| **Group** | Groups without aggregation | Groups by department without summing |

## How Summary Works

When you apply a Summary Type:

1. **Grouping fields** — Columns without a summary type define the grouping level (e.g., Customer, Month)
2. **Aggregated fields** — Columns with a summary type calculate values for each group (e.g., Sum of Total)
3. **Result** — One row per unique combination of grouping fields, with aggregated values

## Common Summary Patterns

### By Customer

| Group By | Summary | Use Case |
|---|---|---|
| Customer | Sum of Total | Total revenue by customer |
| Customer | Count of Document Number | Order count by customer |
| Customer | Maximum of Date Created | Last order date by customer |

### By Month

| Group By | Summary | Use Case |
|---|---|---|
| Date (Month) | Sum of Total | Monthly revenue trend |
| Date (Month) | Count of Document Number | Monthly order volume |
| Date (Month) | Average of Total | Average order value by month |

### By Sales Rep

| Group By | Summary | Use Case |
|---|---|---|
| Sales Rep | Sum of Total | Sales by rep |
| Sales Rep | Count of Customer | Customer count by rep |
| Sales Rep | Average of Total | Average deal size by rep |

## Building a Summary Search

To create a summary search:

1. Set your criteria as usual
2. In the **Results** subtab, add the grouping columns **without** a summary type
3. Add the value columns **with** a summary type (Sum, Count, etc.)
4. Optionally, add a **Sort By** on a summary column

**Example**: Total sales by customer this month.

```
Criteria:
  Type = Sales Order
  Status = any of (Pending Fulfillment, Shipped, Billed)
  Date Created = within (This Month)
  Main Line = Yes

Results:
  Customer               → Group (no summary)
  Sum of Total           → Sum
  Count of Document#     → Count
  Sort By: Sum of Total descending
```

## Summary vs. Non-Summary Results

| Aspect | Non-Summary | Summary |
|---|---|---|
| Rows | One per matching record | One per group |
| Detail | Full record detail | Aggregated metrics |
| Performance | Fast | Slower (requires computation) |
| Use case | Transaction lists | Metrics and KPIs |

## Limitations

- Summary searches cannot show individual record details — only aggregated values
- Some fields cannot be grouped (memo fields, long text fields)
- Summary searches can be slower than non-summary searches on large data sets
- Once a Summary Type is applied to any column, ALL result columns must either be grouped or have a summary type

## Common Mistakes

- **Mixing summary and non-summary columns**: If any column has a Summary Type, all columns must have either a Summary Type or Group. NetSuite will enforce this, but it catches many new users by surprise.
- **Not understanding what Count counts**: Count counts the number of records in each group. If you use Count on a detail field, the result may be higher than expected if the field has multiple values.
- **Using Sum on non-numeric fields**: Sum only works on currency, numeric, and quantity fields.
- **Forgetting to limit date ranges**: Summary searches on all historical data can be slow. Always add a date range filter.

## Best Practices

- Always include a date range filter in summary searches to limit data volume.
- Use Count to measure volume, Sum to measure value.
- Test with a small data range before expanding to full date ranges.
- For dashboard KPIs, use summary searches with a minimum of grouping columns.
- Combine summary searches with highlighting to flag anomalies.

## Related Articles

- [Results](results.md)
- [Formulas](formulas.md)
- [Criteria](criteria.md)
- [Performance Best Practices](performance-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Summary Search Types](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)