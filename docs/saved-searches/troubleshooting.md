---
title: Troubleshooting
module: Saved Searches
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Troubleshooting

## Quick Summary

When a Saved Search doesn't work as expected, systematic debugging identifies the issue. Most problems are caused by incorrect criteria, missing filters, or wrong search type selections.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Troubleshooting a Saved Search is a process of elimination. You systematically test each configuration element until you find the cause of the unexpected behavior.

## Problem: Search Returns No Results

### Checklist

- [ ] Are the criteria too restrictive? Remove criteria one at a time and test each change.
- [ ] Is the search type correct? You cannot find sales orders in a customer search.
- [ ] Are there active records matching the criteria? Verify that at least one record exists.
- [ ] Is the date range correct? A search for "This Month" on the first day of the month may have no data yet.
- [ ] Are there permission restrictions? Do you have access to the records you're searching?
- [ ] Is the Main Line filter correct? On transaction searches, Main Line = Yes only returns summary data.

### Fix Process

1. Remove all criteria and run the search. If results appear, add criteria back one at a time.
2. Check the search type. If wrong, create a new search with the correct type.
3. Verify with a known record by searching for its specific number or ID.
4. Check date range — try "All Dates" to rule out date issues.

## Problem: Search Returns Too Many Results

### Checklist

- [ ] Is the Main Line filter set correctly? Missing Main Line = Yes adds duplicate rows.
- [ ] Are criteria too broad? Add more specific filters.
- [ ] Is the search type correct? A Customer search returns all customers if no criteria are set.
- [ ] Are date ranges set? Without dates, historical and current data appear together.

### Fix Process

1. Set Main Line = Yes explicitly if it's a transaction search.
2. Add date range criteria.
3. Review each criterion — is it actually filtering what you think?
4. Test with a known subset of data.

## Problem: Search Returns Wrong Values

### Checklist

- [ ] Are formula fields correct? Check field names and formula syntax.
- [ ] Are joins correct? Verify that the joined field is the one you intended.
- [ ] Are summary types correct? A Sum of Total is different from a Count of Total.
- [ ] Is the Main Line filter correct? Summary vs. line-level data produces different values.

### Fix Process

1. Remove formulas and check raw field values.
2. Remove joins and check primary record values.
3. Remove summary types and check individual record values.
4. Compare with a known record's actual fields.

## Problem: Search Is Too Slow

### Checklist

- [ ] Is there a date range filter? This is the #1 cause of slow searches.
- [ ] How many joins are used? Each join adds processing time.
- [ ] Are there complex formulas? Formulas calculate per row — many rows = slow.
- [ ] Is the row limit high? More rows = more time.
- [ ] Are there OR conditions? Each OR branch adds a separate query.

### Fix Process

1. Add or restrict the date range. Test.
2. Remove joins one at a time. Test after each removal.
3. Simplify or remove formulas. Test.
4. Reduce the row limit. Test.
5. Convert OR conditions to separate searches if possible.

## Problem: Dashboard Portlet Shows Error

### Checklist

- [ ] Has the original search been deleted or renamed?
- [ ] Does the user have permission to run the search?
- [ ] Has the search's audience been changed?
- [ ] Is the search timing out on large data?

### Fix Process

1. Run the search directly from Reports > Saved Searches.
2. Check if the search still exists and has the correct name.
3. Verify the user's role has access to the search.
4. Re-add the portlet to the dashboard.

## Problem: Formula Field Shows No Value

### Checklist

- [ ] Is the formula type correct? (Numeric, Text, Date, Currency)
- [ ] Are field names in curly braces? `{fieldname}` not `fieldname`
- [ ] Are there null values? Use NVL() to handle nulls.
- [ ] Is the field name the internal ID, not the display name?

### Fix Process

1. Check the formula type matches the expected output.
2. Test with a simple formula first: `{fieldname}` should return the field value.
3. Use NVL to handle nulls: `NVL({fieldname}, 0)`.
4. Verify the internal field ID in the Records Browser.

## Debugging Methodology

When a search isn't working:

1. **Simplify** — Remove everything except essential criteria and one result column
2. **Test** — Run the simplified search
3. **Add back** — Reintroduce elements one at a time
4. **Test again** — Run after each change
5. **Identify** — The element that breaks the search is the problem

## Related Articles

- [Common Mistakes](common-mistakes.md)
- [Performance Best Practices](performance-best-practices.md)
- [Criteria](criteria.md)
- [Formulas](formulas.md)

## Oracle References

- [Oracle NetSuite Help Center: Troubleshooting Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)