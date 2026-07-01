---
title: Creating Saved Searches
module: Saved Searches
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Creating Saved Searches

## Quick Summary

Creating a saved search starts with selecting a record type, defining criteria, choosing result columns, and saving the search for reuse. The quality of the saved search depends on choosing the right record type and carefully testing filters and results.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

This article covers the general workflow for creating any Saved Search. For a detailed walkthrough with a concrete example, see [Building Your First Search](building-your-first-search.md).

## General Navigation

```
Reports > Saved Searches > All Saved Searches > New
```

Then select the record type for the search.

## Choosing the Right Search Type

The search type determines which fields, joins, and records are available. For example, a transaction search is used for sales orders, invoices, purchase orders, item fulfillments, and other transaction records. An item search is better for item master data.

See [Saved Search Types](saved-search-types.md) for guidance on choosing.

## Setting Criteria

Criteria filter which records appear. Common criteria include:

- Record type (Sales Order, Invoice, Purchase Order)
- Status (Open, Pending, Closed)
- Date ranges (Created this month, Due this week)
- Amount thresholds (Greater than $10,000)
- Customer, vendor, or item filters

See [Criteria](criteria.md) for detailed guidance.

## Choosing Result Columns

Result columns determine what information is displayed. Good results include:

- Identifying information (document number, name, ID)
- Key data (dates, amounts, quantities)
- Reference fields (department, class, location)

See [Results](results.md) for detailed guidance.

## Adding Available Filters

Available Filters let users refine results without editing the search. Add 3-5 filters for the most common variables users need to change.

See [Filters](filters.md) and [Available Filters](available-filters.md) for detailed guidance.

## Configuring Audience

Set the audience to control who can see and run the search. Personal searches are visible only to the creator. Shared searches are visible to specific roles.

See [Audience and Sharing](audience-and-sharing.md) for detailed guidance.

## Testing

Before publishing a search:

1. Run the search to verify results
2. Check that a known record appears
3. Verify that unintended records are excluded
4. Test the search from the perspective of the intended audience

## Following the Standards

- Give saved searches descriptive names with module prefixes
- Add a short description explaining the search's purpose
- Use consistent naming conventions for department or purpose
- Keep filters simple when possible
- Test results with a known record
- Review permissions before sharing

## Related Articles

- [Building Your First Search](building-your-first-search.md)
- [Saved Search Types](saved-search-types.md)
- [Criteria](criteria.md)
- [Results](results.md)
- [Common Mistakes](common-mistakes.md)

## Oracle References

- [Oracle NetSuite: Creating Custom Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Defining a Saved Search](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)