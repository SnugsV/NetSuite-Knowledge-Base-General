---
title: Criteria
module: Saved Searches
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Criteria

## Quick Summary

Criteria are the filters that determine which records appear in a Saved Search. They are the most important part of the search — badly chosen criteria produce useless results. Well-designed criteria return exactly the records you need.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

If a Saved Search is a question, Criteria is the "WHERE" clause. Criteria tell NetSuite: *"Only show me records where these conditions are true."*

Criteria are composed of three parts:

1. **Field** — The record field to evaluate (e.g., Status, Date Created, Customer)
2. **Condition** — How to compare (e.g., is, is not, contains, starts with, greater than)
3. **Value** — What to compare against (e.g., "Pending Fulfillment," "30 days ago," "Acme Corp")

## Adding Criteria

1. Go to the **Criteria** subtab when creating or editing a Saved Search
2. Click **Add** to add a new criterion
3. Select the **Field** from the dropdown
4. Choose the **Condition** (the options change based on the field type)
5. Enter or select the **Value**
6. Repeat for each additional criterion

## Field Types and Conditions

Different field types support different conditions:

### Text Fields (Customer Name, Document Number, Memo)

| Condition | Behavior |
|---|---|
| is | Exact match |
| is not | Excludes exact match |
| starts with | Begins with specified text |
| contains | Text appears anywhere in the field |
| does not contain | Text does not appear |
| is empty | Field has no value |
| is not empty | Field has any value |

### Date Fields (Date Created, Due Date, Date Closed)

| Condition | Behavior |
|---|---|
| is | Specific date |
| is within | Date range (e.g., last month, this quarter) |
| is before | Before a specific date |
| is after | After a specific date |
| is on or before | Date or earlier |
| is within  | Relative range (e.g., within 30 days) |

### Numeric Fields (Amount, Total, Quantity)

| Condition | Behavior |
|---|---|
| equal to | Exact number |
| greater than | Above threshold |
| less than | Below threshold |
| between | Within a range |
| is not equal to | Not a specific value |

### Select Fields (Status, Type, Department)

| Condition | Behavior |
|---|---|
| is | One specific value |
| any of | Multiple values (OR logic) |
| none of | Excludes multiple values |
| is not | Not a specific value |

## Combining Criteria

When you add multiple criteria, they are combined with AND by default — all conditions must be true for a record to appear.

To add OR logic:

1. Add the criteria normally
2. Click the **OR** button between criteria groups
3. Add the alternative criteria in the new group

Example: "Show sales orders that are EITHER overdue OR over $10,000"

```
Criteria Group 1:
  Type = Sales Order
  Status = Pending Fulfillment
  Date Created = on or before 30 days ago
  Main Line = Yes
    OR
Criteria Group 2:
  Type = Sales Order
  Total = greater than 10000
  Main Line = Yes
```

## The Main Line Filter

For transaction searches, the **Main Line** filter is essential. It controls whether the search returns one row per transaction (Main Line = Yes) or one row per line item (Main Line = No).

| Setting | Result |
|---|---|
| **Main Line = Yes** | One row per transaction. Summary fields (Total, Date, Customer) are available. |
| **Main Line = No** | One row per line item. Item-level fields (Item, Quantity, Rate) are available. |
| **Main Line filter omitted** | Both transaction and line data are returned, creating duplicate rows. |

**Best practice**: Always set the Main Line filter explicitly. Omitting it is the most common cause of confusing search results.

## Common Criteria Patterns

### Open Transactions

```
Status = any of (Pending Fulfillment, Pending Approval, Pending Receipt)
Main Line = Yes
```

### Date-Range Searches

```
Date Created = within (This Month)
Main Line = Yes
```

### Exception Searches

```
Shipping Date = is empty
Status ≠ Closed
Main Line = Yes
```

### Cross-Reference Searches

```
Customer = is (Acme Corp)
Main Line = Yes
```

## Common Mistakes

- **Omitting the Main Line filter**: Always set Main Line explicitly on transaction searches.
- **Too many criteria**: Start with 2-3 criteria and test. Add more only if needed.
- **Using OR when AND is needed**: Be deliberate about whether you need all conditions (AND) or any condition (OR).
- **Date criteria without thinking about relative dates**: "Before 01/01/2026" will need updating. "Within this month" is relative and stays relevant.
- **Text fields with partial matches**: Use "starts with" or "contains" instead of "is" when you don't know the exact value.

## Best Practices

- Start with minimal criteria and iterate. You can always add more.
- Test criteria with a known record before saving.
- Use Available Filters for criteria that users need to change frequently — that avoids editing the search every time.
- Document what each complex search is filtering and why.
- For date ranges, prefer relative values ("this month," "last 30 days") over fixed dates.

## Related Articles

- [Building Your First Search](building-your-first-search.md)
- [Results](results.md)
- [Filters](filters.md)
- [Joins and Related Records](joins-and-related-records.md)
- [Common Mistakes](common-mistakes.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Criteria](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)