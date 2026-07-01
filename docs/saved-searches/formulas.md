---
title: Formulas
module: Saved Searches
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Formulas

## Quick Summary

Formula columns perform calculations using values from your records. They can combine fields, apply logic, format output, and create calculated metrics that are not available as standard fields.

## Difficulty

Advanced

## Estimated Time

20 minutes

## Overview

Standard result columns show existing field values. Formula columns let you create new values by combining, transforming, or calculating from existing fields. This is where Saved Searches become truly powerful.

## Formula Types

Saved Searches support four formula types:

| Type | Syntax | Best For |
|---|---|---|
| **Formula (Numeric)** | Numeric expressions and functions | Calculations, sums, thresholds |
| **Formula (Text)** | String manipulation | Concatenation, formatting |
| **Formula (Date)** | Date arithmetic | Days between dates, aging |
| **Formula (Currency)** | Monetary calculations | Profit margins, percentages |

## Common Formulas

### Days Between Dates

```sql
-- Days overdue (Text or Numeric)
{TODAY} - {trandate}
```

### Profit Margin

```sql
-- Profit percentage (Currency or Numeric)
({amount} - {costestimate}) / {amount} * 100
```

### Concatenated Fields

```sql
-- Customer name with location (Text)
{customer} || ' - ' || {location}
```

### Conditional Logic

```sql
-- Status label (Text)
CASE WHEN {status} = 'A' THEN 'Active'
     WHEN {status} = 'B' THEN 'Pending'
     ELSE 'Inactive' END
```

### Boolean Flags

```sql
-- Overdue flag (Text)
CASE WHEN {TODAY} > {duedate} THEN 'OVERDUE' ELSE '' END
```

## Formula Syntax Guidelines

- Field references use curly braces: `{fieldname}`
- Field names use the internal NetSuite field ID, not the display name
- Strings use single quotes: `'Pending'`
- Concatenation uses `||` (double pipe)
- CASE statements are evaluated in order, first match wins
- NVL (null value) function: `NVL({fieldname}, 0)` returns 0 if the field is null

## Finding Field Names

To find the internal field name for a formula:

1. Open the record type in NetSuite
2. Look at the URL or use the field's tooltip
3. Use the Records Browser at **Customization > Records Browser**
4. For custom fields, the field name is typically `custentity_*` or `custbody_*`

## Formula Performance

Formula columns are calculated for every result row. Complex formulas on large result sets can slow search performance.

- Prefer simple arithmetic over complex CASE statements
- Use NVL() to handle null values explicitly
- Test formula searches with limited date ranges first
- Consider using a summary search instead of per-row formulas when possible

## Real Examples

### Inventory Reorder Alert

```sql
-- Numeric formula: Quantity to reorder
CASE WHEN {quantityonhand} < {reorderpoint}
     THEN {reorderpoint} - {quantityonhand}
     ELSE 0 END
```

### Customer Aging Bucket

```sql
-- Text formula: Aging category
CASE WHEN {TODAY} - {duedate} > 90 THEN '90+ Days'
     WHEN {TODAY} - {duedate} > 60 THEN '61-90 Days'
     WHEN {TODAY} - {duedate} > 30 THEN '31-60 Days'
     ELSE 'Current' END
```

### Order Priority Score

```sql
-- Numeric formula: Priority ranking
CASE WHEN {status} = 'Pending Approval' THEN 1
     WHEN {TODAY} - {trandate} > 14 THEN 2
     WHEN {total} > 10000 THEN 3
     ELSE 4 END
```

## Common Mistakes

- **Using field display names instead of internal IDs**: Formulas use internal field IDs. `{trandate}` not `{Date Created}`.
- **Mismatched formula types**: A text formula cannot perform numeric calculations. Use the correct formula type for the intended output.
- **Not handling null values**: If a field is null, arithmetic operations produce null results. Use `NVL()` to provide defaults.
- **Complex formulas with no testing**: Test formulas incrementally. Add one calculation at a time and verify results.
- **Forgetting date arithmetic returns days**: `{TODAY} - {trandate}` returns the number of days, not a formatted date.

## Best Practices

- Test formulas on a small data set before expanding to full searches.
- Use CASE statements for conditional logic — they are readable and maintainable.
- Handle null values explicitly with NVL().
- Use Text formulas for formatting and labels, Numeric formulas for calculations.
- Comment complex formulas by adding a description in the search notes.
- Keep formulas under 10 lines when possible. Split very complex logic into multiple formula columns.

## Related Articles

- [Results](results.md)
- [Summary Types](summary-types.md)
- [Joins and Related Records](joins-and-related-records.md)
- [Performance Best Practices](performance-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Formulas](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Formula Functions Reference](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)