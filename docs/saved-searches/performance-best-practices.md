---
title: Performance Best Practices
module: Saved Searches
difficulty: Advanced
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Performance Best Practices

## Quick Summary

Saved Search performance depends on criteria design, result configuration, and data volume. Well-designed searches run quickly even on large data sets. Poorly designed searches can time out or degrade system performance.

## Difficulty

Advanced

## Estimated Time

10 minutes

## Overview

As your NetSuite account grows, so does the time it takes to run searches. A search that took 3 seconds with 10,000 records might take 30 seconds with 100,000 records — or longer if not designed well.

## What Affects Performance

| Factor | Impact | Mitigation |
|---|---|---|
| **Data volume** | More records = slower searches | Add date range filters, use summary types |
| **Criteria complexity** | Many criteria, OR conditions, joins | Simplify criteria, test iteratively |
| **Result columns** | Many columns = slower rendering | Limit to essential columns |
| **Joins** | Each join adds processing time | Only join necessary tables |
| **Formulas** | Calculated per row | Keep formulas simple |
| **Summary types** | Grouping requires sorting | Limit grouping columns |
| **Row limit** | More rows = slower rendering | Set appropriate limits |

## Design for Performance

### 1. Always Include Date Ranges

Date ranges are the single most effective performance optimization. A search without date filters scans the entire transaction history.

**Poor**: No date filter — scans all records

**Good**: `Date Created = within (This Month)`

**Better**: `Date Created = within (Last 30 Days)` with an Available Filter for custom ranges

### 2. Limit Result Columns

Each additional column adds processing time. Only include columns you actually need.

**Poor**: 20 columns "just in case"

**Good**: 6-8 columns that users actually use

### 3. Be Selective with Joins

Each join adds a table join operation. Only join when you need data from a related record.

**Poor**: Joining to Customer, Item, Department, Class, Location, and Created By "because they might be useful"

**Good**: Joining only to the records needed in results or criteria

### 4. Use Available Filters Over Multiple Searches

Instead of creating five similar searches with different filter values, create one search with Available Filters. This reduces the total number of searches and lowers maintenance.

### 5. Optimize Formulas

| Issue | Fix |
|---|---|
| Nested CASE statements | Simplify logic |
| Unnecessary NVL() calls | Only use where null values are expected |
| Redundant calculations | Calculate once, reference the result |
| Complex string operations | Use multiple formula columns |

## Performance by Search Type

| Search Type | Typical Performance | Notes |
|---|---|---|
| Transaction | Moderate | Most common. Date range filters are critical. |
| Item | Fast | Smaller data set. Joins to vendor can slow it. |
| Customer | Fast | Usually small data set. Summary searches can be slower. |
| Employee | Fast | Usually small data set. |
| Custom Record | Variable | Depends on record count and field complexity. |

## Dashboard Portlets

Saved Searches on dashboards run every time the dashboard loads. For dashboard portlets:

- Limit results to 10-20 rows
- Avoid summary types if possible
- Avoid formulas (calculated in real-time)
- Set row limit to prevent long load times
- Test dashboard load time with the search included

## Scheduled Emails

Saved Searches that are emailed on a schedule run in the background. Performance is less visible but still affects system resources:

- Schedule large searches during off-peak hours
- Avoid scheduling multiple large searches at the same time
- Set appropriate row limits for email results

## Monitoring Performance

If a search is slow:

1. **Run it with minimal date range** — If it's fast, data volume is the issue
2. **Remove joins one at a time** — If it speeds up, a specific join is the problem
3. **Reduce result columns** — If it speeds up, column count is affecting it
4. **Simplify criteria** — Remove OR conditions and test
5. **Check for summary types** — Remove summary types and test

## When to Use an Alternative

If a search is still slow after optimization, consider:

- **Export to CSV** for full data pulls (runs in background)
- **SuiteAnalytics** for complex multi-table analysis
- **SuiteScript** for programmatic data processing
- **A custom report** if the data fits a standard report structure

## Related Articles

- [Criteria](criteria.md)
- [Joins and Related Records](joins-and-related-records.md)
- [Formulas](formulas.md)
- [Summary Types](summary-types.md)
- [Troubleshooting](troubleshooting.md)
- [Saved Search vs. Reports](saved-search-vs-reports.md)
- [Saved Search vs. SuiteAnalytics](saved-search-vs-suiteanalytics.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Performance](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)