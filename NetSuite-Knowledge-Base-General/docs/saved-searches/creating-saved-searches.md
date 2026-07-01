---
title: Creating Saved Searches
department: NetSuite
module: Saved Searches
status: Draft
version: 0.1
created: 2026-07-01
tags: [saved-searches, create, reports, filters, results]
source_type: Oracle Documentation Summary
---

# Creating Saved Searches

## AI Summary

Creating a saved search starts with selecting a record type, defining criteria, choosing result columns, and saving the search for reuse. The quality of the saved search depends on choosing the right record type and carefully testing filters and results.

## Purpose

Use this guide when creating a new saved search for reporting, dashboards, exports, reminders, or operational monitoring.

## General Navigation

```text
Reports > Saved Searches > All Saved Searches > New
```

Then select the record type for the search.

## Step-by-Step

1. Go to the saved search creation page.
2. Choose the record type.
3. Enter a clear search title.
4. Add criteria filters.
5. Add result columns.
6. Add available filters if users need to adjust results.
7. Configure audience or sharing settings if needed.
8. Test the search with expected records.
9. Save the search.
10. Document the purpose and owner.

## Choosing the Right Search Type

The search type determines which fields, joins, and records are available. For example, a transaction search is often used for sales orders, invoices, purchase orders, item fulfillments, and other transaction records. An item search is better for item master data.

## Testing Checklist

- Does a known record appear?
- Are unwanted records excluded?
- Are quantities, dates, and statuses correct?
- Are transaction line filters set correctly?
- Can the intended users access it?
- Are results clear enough for a non-technical user?

## Common Mistakes

- Picking the wrong record type.
- Forgetting transaction line filters.
- Not checking permissions before sharing.
- Using formulas before confirming simple fields cannot solve the problem.
- Failing to name the search clearly.

## Best Practices

- Start simple, then add complexity.
- Use a test record to validate results.
- Document what the search is meant to answer.
- Avoid making every search public.
- Create a naming convention before the number of searches grows.

## Related Topics

- Saved Searches Overview
- Saved Search Criteria
- Saved Search Results
- Formula Fields
- Saved Search Alerts

## Official References

- Oracle NetSuite: Creating Custom Saved Searches
- Oracle NetSuite: Defining a Saved Search
