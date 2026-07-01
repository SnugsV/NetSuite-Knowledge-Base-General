---
title: Available Filters
module: Saved Searches
difficulty: Advanced
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Available Filters

## Quick Summary

Available Filters are user-facing criteria that let people refine a Saved Search without editing it. This article covers advanced configuration — filter relationships, required filters, filter sections, and filter-level permissions.

## Difficulty

Advanced

## Estimated Time

10 minutes

## Overview

Standard Available Filters let users set a single value for a field. Advanced configuration gives more control:

- **Required filters** — Users must set a value before the search runs
- **Filter sections** — Organize filters into groups
- **Filter-level permissions** — Control which roles can see or set each filter
- **Filter defaults** — Pre-set values that users can override

## Required Filters

A required filter forces the user to specify a value before the search returns results. This is useful when:

- The search is meaningless without a specific parameter (e.g., "Orders for customer X" — the customer is required)
- You want to prevent users from accidentally running an unfiltered search on large data sets
- You want to guide users to the most important filter first

To make a filter required, check the **Required** box when adding or editing the Available Filter.

## Filter Sections

Filters can be organized into named sections. This is useful when a search has many available filters — grouping them makes the interface less overwhelming.

Sections appear as visual separators in the filter panel:

```
[Date Filters]
  Date Created
  Due Date

[Reference Filters]
  Customer
  Sales Rep
  Department
```

To create a section, add a filter section heading before the filters you want to group.

## Filter Dependencies

Filters can be configured to appear or hide based on the value of another filter. This is useful for progressive disclosure — showing advanced filters only when needed.

Example: A "Show Advanced Filters" checkbox that reveals additional filtering options.

## Default Values

Default values are pre-applied when the user opens the search. They can be changed or cleared.

Recommended defaults:

| Field | Sensible Default |
|---|---|
| Date Range | This Month |
| Status | Open/Pending (not Closed) |
| Department | User's department (if available) |
| Location | User's location (if available) |

## Multiple Selection

For select-type filters (status, department, class), you can allow multiple selection. Users can pick several values to include, rather than being limited to one.

Enable this by setting the filter type to **Multiple Select** when configuring the filter.

## Filter Permissions

Some available filters can be restricted by role:

- **Show to all roles** — Default. Every user with access to the search sees the filter.
- **Show only to specific roles** — The filter is only visible to certain roles.
- **Hidden but set by default** — The filter has a value that users cannot see or change.

## Common Mistakes

- **Making too many filters required**: Users should be able to run a search with minimal friction. Only make filters required if the search truly cannot function without them.
- **Not setting defaults**: A search without default filters returns unfiltered results, which can be slow on large data sets.
- **Adding filters for fields that don't exist in the results**: Users expect filters to affect what they see. A filter for a field that isn't in the results confuses them.
- **Ignoring filter order**: Put the most commonly used filters first. Group related filters together.

## Best Practices

- Limit Available Filters to 5-7 fields. More than that becomes overwhelming.
- Set date range defaults ("This Month" or "Last 30 Days") for all date-based filters.
- Make critical filters required (customer, date range).
- Group related filters into sections.
- Use filter-level permissions to hide advanced filters from most users.
- Test the filter experience from the user's perspective before publishing.

## Related Articles

- [Filters](filters.md)
- [Audience and Sharing](audience-and-sharing.md)
- [Performance Best Practices](performance-best-practices.md)
- [Criteria](criteria.md)

## Oracle References

- [Oracle NetSuite Help Center: Available Filters](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)