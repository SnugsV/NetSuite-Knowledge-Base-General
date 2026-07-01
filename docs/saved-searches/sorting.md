---
title: Sorting
module: Saved Searches
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed:
---

# Sorting

## Quick Summary

Sorting controls the order in which results appear. A well-sorted search puts the most important information at the top, making it immediately useful without manual scanning.

## Difficulty

Beginner

## Estimated Time

5 minutes

## Overview

When a Saved Search runs, the results can be sorted by any result column. Sorting can be ascending (A-Z, smallest to largest) or descending (Z-A, largest to smallest).

## Setting Sort Order

1. In the **Results** subtab, locate the **Sort By** section
2. Select the primary sort column
3. Specify **Ascending** or **Descending**
4. Optionally, add secondary and tertiary sort columns

## Sort Direction

| Direction | Text Fields | Numeric Fields | Date Fields |
|---|---|---|---|
| **Ascending** | A to Z | Smallest to largest | Oldest to newest |
| **Descending** | Z to A | Largest to smallest | Newest to oldest |

## Multi-Column Sorting

For most searches, one sort column is sufficient. For complex searches, you can sort by multiple columns:

**Example**: Open sales orders sorted by priority (Status ascending), then by due date (oldest first).

```
Primary sort:  Status (ascending)
Secondary sort: Due Date (ascending)
Tertiary sort:  Total (descending)
```

## Sorting by Formula Columns

Formula columns can also be used for sorting. This is useful when you want to sort by a calculated value:

- Sort by "days overdue" (calculated)
- Sort by "profit margin" (calculated)
- Sort by "custom priority score" (calculated)

## Common Sort Patterns

| Search Type | Recommended Sort |
|---|---|
| Open orders | Due Date ascending (oldest first) |
| Overdue invoices | Days Overdue descending (most overdue first) |
| Inventory items | Quantity On Hand ascending (low stock first) |
| Employee list | Name ascending (alphabetical) |
| Sales by rep | Total descending (highest first) |

## Common Mistakes

- **No sort applied**: Results appear in unpredictable order, usually by internal ID.
- **Wrong sort direction**: A list of overdue items should show the most overdue first (descending), not the least overdue.
- **Sorting by a non-result column**: The sort column must also be in the Results. Hidden or unavailable columns cannot be used for sorting.

## Best Practices

- Always set a sort order. Unsorted results are harder to scan.
- Put the most actionable items first (most overdue, lowest stock, highest value).
- Use multi-column sorting when the primary sort produces ties.
- Be deliberate about ascending vs. descending based on what users need to see first.

## Related Articles

- [Results](results.md)
- [Highlighting Results](highlighting-results.md)
- [Building Your First Search](building-your-first-search.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Sorting](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)