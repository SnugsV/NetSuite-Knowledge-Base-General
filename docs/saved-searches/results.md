---
title: Results
module: Saved Searches
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Results

## Quick Summary

The Results tab defines what columns appear in your Saved Search output. Choosing the right result columns determines whether the search is immediately useful or requires manual reformatting.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

While Criteria determine which records appear, Results determine what information is shown. A well-designed Results configuration shows exactly the columns needed and nothing more.

## Adding Result Columns

1. Go to the **Results** subtab when creating or editing a Saved Search
2. Under **Columns**, click **Add**
3. Select the field to display
4. Configure any field-specific options
5. Drag to reorder columns
6. Repeat for each column

## Column Order

The order of columns matters:

- **First columns** should be identifying fields (Document Number, Name, ID)
- **Middle columns** should be the data the user needs (Amounts, Dates, Quantities)
- **Last columns** should be reference fields (Department, Class, Location)

Users scan left to right. Put the most useful information first.

## Field Selection Options

When you add a column, you can often configure:

| Option | What It Does |
|---|---|
| **Label** | Custom display name for the column |
| **Summary Type** | How to aggregate values (Sum, Count, Average, etc.) |
| **Formula** | Custom calculation using the field value |
| **Function** | Special formatting options |
| **Order** | Sort direction for this column |

## Common Result Columns

### Transaction Searches

| Column | Why It Matters |
|---|---|
| Document Number | Identifies the transaction |
| Date Created | When it was entered |
| Customer/Vendor | Who it's with |
| Status | Current state |
| Total | Monetary value |
| Currency | Transaction currency |
| Department/Class/Location | Dimensional breakdown |

### Item Searches

| Column | Why It Matters |
|---|---|
| Item Name/Number | Identifies the item |
| Description | What it is |
| Quantity On Hand | Current stock |
| Average Cost | Cost basis |
| Sales Price | Selling price |
| Location | Where it's stored |

### Customer Searches

| Column | Why It Matters |
|---|---|
| Company Name | Customer identity |
| Email/Phone | Contact information |
| Terms | Payment terms |
| Credit Limit | Credit control |
| Balance Due | Outstanding amount |
| Sales Rep | Assigned representative |

## Limiting Results

You can limit the number of rows returned:

- **Return results up to** — Maximum number of rows (default 1000, maximum 5000)
- **Skip results before** — Used for pagination

For searches where users need complete data, consider using **Export to CSV** instead of increasing the row limit.

## Custom Labels

Each column can have a custom label that differs from the field name. This is useful when:

- The field name is technical and confusing to end users
- You want a shorter column header
- You need to differentiate between multiple columns using the same field

To set a custom label, enter it in the **Label** field when adding or editing the column.

## Sorting Results

You can sort results by any column. See [Sorting](sorting.md) for details.

## Summary Types

When you add a **Summary Type** to a column, the search groups results and calculates aggregated values. See [Summary Types](summary-types.md) for details.

## Common Mistakes

- **Adding too many columns**: Each extra column makes the results harder to scan. Aim for 5-8 columns maximum.
- **Including fields that don't make sense for the search type**: A customer search cannot display transaction totals without using a join.
- **Poor column order**: Putting amounts before identifying information forces users to hunt for context.
- **Not using custom labels**: Technical field names ("Tran Date," "Custentity_..." ) confuse end users.
- **Setting the row limit too high**: Large result sets take longer to load and may time out. Use filters or exports instead.

## Best Practices

- Limit results to 5-8 columns. More than that becomes hard to read.
- Put the most important identifying column first.
- Use custom labels to make column headers user-friendly.
- If you need many columns, consider whether a report or SuiteAnalytics workbook is a better fit.
- For dashboard portlets, limit results to 10-20 rows and add a drill-down link.

## Related Articles

- [Building Your First Search](building-your-first-search.md)
- [Criteria](criteria.md)
- [Sorting](sorting.md)
- [Summary Types](summary-types.md)
- [Formulas](formulas.md)
- [Highlighting Results](highlighting-results.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Results](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)