---
title: Filters
module: Saved Searches
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Filters

## Quick Summary

Available Filters are user-facing criteria that let people refine a Saved Search without editing it. They turn a single search into a flexible reporting tool that serves multiple needs.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

When you create a Saved Search, you define fixed criteria that always apply. But users often need to narrow results further — show only this customer, only this month, only orders over a certain amount. Available Filters let them do this without editing the search.

## Available Filters vs. Criteria

| Dimension | Criteria | Available Filters |
|---|---|---|
| **Who sets them** | The search creator | The search user |
| **When they apply** | Always | Optional, at runtime |
| **Flexibility** | Fixed | User can set any value |
| **When to use** | For rules that should never change | For options users need to adjust |

## Adding Available Filters

1. Go to the **Available Filters** subtab when creating or editing a Saved Search
2. Click **Add**
3. Select the field to make available
4. Configure the filter options
5. Save the search

When a user runs the search, they see a filter panel with the available fields. They can set values for any of them to narrow the results.

## Choosing What to Make Available

Good candidates for Available Filters:

| Field | Why |
|---|---|
| **Customer/Vendor** | Users often want to focus on specific accounts |
| **Date Range** | Period-over-period comparisons |
| **Department/Class/Location** | Dimensional breakdowns |
| **Status** | Open vs. closed transactions |
| **Amount/Total** | Threshold-based filtering |
| **Sales Rep** | Individual performance views |

Poor candidates:

| Field | Why |
|---|---|
| **Record Type** | Usually should be fixed in criteria |
| **Main Line** | Should always be set explicitly |
| **Internal ID** | Not meaningful to end users |

## Filter Behavior

When a user sets a filter:

- The filter value is ANDed with the existing criteria — results must satisfy BOTH the criteria AND the filter
- Users can set multiple filters simultaneously
- Users can clear filters to see the full result set
- Filters do not modify the saved search — they only affect the current view

## Default Filter Values

You can set default values for Available Filters. When a user opens the search, these defaults are pre-applied. Users can change or clear them.

Default values are useful for:

- Setting a default date range ("This Month")
- Pre-filtering to a commonly used department
- Setting a minimum threshold for exception searches

## Example: A Flexible Sales Report

Scenario: A sales manager wants to see open orders, but sometimes needs to filter differently.

**Fixed Criteria**:
```
Type = Sales Order
Status = any of (Pending Fulfillment, Pending Approval)
Main Line = Yes
```

**Available Filters**:
```
Customer        → Filter by specific account
Sales Rep       → Filter by salesperson
Date Created    → Filter by order date (default: This Month)
Total           → Filter by minimum amount
```

With this configuration, one search replaces five different searches that would have been needed for different combinations of customer, rep, month, and amount.

## Common Mistakes

- **Not using Available Filters at all**: Without them, users must either edit the search or create duplicate searches for different filter combinations.
- **Making every field available**: Too many filters overwhelm users. Keep it to 3-5 most useful fields.
- **Adding fields that don't make sense**: If a field has no meaningful values in the current context, it just adds noise.
- **Confusing Available Filters with Criteria**: Criteria are fixed rules. Filters are user choices. Use them appropriately.

## Best Practices

- Add 3-5 Available Filters to every search you share.
- Choose filters that cover the most common ways users need to refine results.
- Set sensible defaults for date ranges and thresholds.
- Test filters from the user's perspective — do they make sense?
- Document what each filter does in the search description.

## Related Articles

- [Criteria](criteria.md)
- [Results](results.md)
- [Available Filters](available-filters.md)
- [Building Your First Search](building-your-first-search.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Available Filters](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)