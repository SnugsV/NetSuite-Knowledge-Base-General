---
title: Common Mistakes
module: Saved Searches
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Common Mistakes

## Quick Summary

Saved Searches are powerful but have several configuration pitfalls that produce misleading results or poor performance. Understanding these mistakes helps you build reliable searches from the start.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

The most common mistakes in Saved Searches fall into a few categories. Recognizing them will save hours of debugging.

## The Top 10 Mistakes

### 1. Forgetting the Main Line Filter

**Mistake**: Creating a transaction search without setting Main Line = Yes or Main Line = No.

**Result**: Each transaction appears once for the transaction itself plus once for every line item. A sales order with 10 items returns 11 rows — one for the order and one for each item.

**Fix**: Always set Main Line = Yes (for summary data) or Main Line = No (for line-level data) explicitly.

### 2. Choosing the Wrong Search Type

**Mistake**: Selecting "Customer" as the search type when you need to find "customers who have open sales orders."

**Result**: A customer search shows customer records. You cannot filter by sales order status or date because those fields don't exist on the customer record.

**Fix**: Choose the search type that corresponds to the records you want in your results. For "customers with open orders," use a Transaction search grouped by customer.

### 3. Not Using Date Range Filters

**Mistake**: Omitting date criteria from a transaction search.

**Result**: The search scans every transaction in the account — including transactions from years ago. This is slow and may time out.

**Fix**: Always add a date range filter. Use relative dates (This Month, Last 30 Days) so the search stays relevant.

### 4. Overusing OR Conditions

**Mistake**: Creating complex OR logic with many branches.

**Result**: Each OR branch adds a separate query that NetSuite must execute. Too many OR conditions can cause timeouts.

**Fix**: Use OR sparingly. Consider breaking complex OR searches into multiple searches for different conditions.

### 5. Creating Too Many Similar Searches

**Mistake**: Creating five searches that differ only by one filter value (e.g., "Open Orders — Sales Rep A," "Open Orders — Sales Rep B").

**Result**: The search list becomes cluttered. If the criteria change, you must update all five.

**Fix**: Use one search with an Available Filter for Sales Rep. Users can filter for the rep they need.

### 6. Using Fixed Dates

**Mistake**: Setting criteria like `Date Created = before 01/01/2026`.

**Result**: The search becomes outdated. Next month, users won't see current data unless the date is updated.

**Fix**: Use relative date values: `within (This Month)`, `within (Last 30 Days)`, `on or before (Today)`.

### 7. Building from Scratch Instead of Copying

**Mistake**: Clicking "New" and building a search from scratch when a similar search exists.

**Result**: More work, more opportunities for mistakes, inconsistency in naming and structure.

**Fix**: Copy an existing search that's close to what you need, then modify it.

### 8. Ignoring Available Filters

**Mistake**: Creating a search with no Available Filters.

**Result**: Users must edit the search to change filter values. This requires search creation permissions and modifies the original search.

**Fix**: Add 3-5 Available Filters for the most common ways users need to refine results.

### 9. Creating a Search Without Testing

**Mistake**: Saving a search, making it public, and never running it.

**Result**: The search may return zero results, incorrect results, or error messages. Users lose trust in the data.

**Fix**: Always run a search after creating it. Verify with a known record. Check that results match expectations.

### 10. Not Using Descriptions or Naming Conventions

**Mistake**: Naming a search "Test" or "New Search" with no description.

**Result**: Other users cannot tell what the search does. As the search list grows, it becomes unmanageable.

**Fix**: Use descriptive names with module prefixes (e.g., "INV — Low Stock Alert"). Add a 1-2 sentence description explaining purpose and audience.

## Quick Reference

| Symptom | Likely Cause |
|---|---|
| Duplicate rows in transaction search | Main Line filter missing |
| No results when you expect data | Criteria too restrictive or wrong search type |
| Too many results | Criteria too broad or Main Line filter missing |
| Search is slow | No date range, too many joins, or too many OR conditions |
| Wrong columns available | Wrong search type |
| Users can't find the search | No audience configured or poor naming |
| Search returns everything | No criteria or very broad criteria |

## Related Articles

- [Criteria](criteria.md)
- [Building Your First Search](building-your-first-search.md)
- [Saved Search Types](saved-search-types.md)
- [Troubleshooting](troubleshooting.md)
- [Performance Best Practices](performance-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Troubleshooting Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)