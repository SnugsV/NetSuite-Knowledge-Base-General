---
title: Highlighting Results
module: Saved Searches
difficulty: Intermediate
estimated_time: 5 minutes
status: Draft
last_reviewed:
---

# Highlighting Results

## Quick Summary

Highlighting adds visual emphasis to results that meet specific conditions — turning overdue items red, flagging high-value orders, or marking exceptions. This makes critical information stand out at a glance.

## Difficulty

Intermediate

## Estimated Time

5 minutes

## Overview

Highlighting is conditional formatting for Saved Search results. You define a condition and choose a formatting style (bold, color, background). When the condition is met, the result row is highlighted accordingly.

## Configuring Highlighting

1. In the **Results** subtab, scroll to the **Highlighting** section
2. Click **Add** to create a new highlight rule
3. Set the condition (field, operator, value)
4. Choose the formatting (text color, background color, bold, italic)
5. Save the search

## Highlight Conditions

Highlight conditions use the same field-operator-value structure as Criteria. For example:

| Condition | Format | Behavior |
|---|---|---|
| Days Overdue > 30 | Red text, bold | Overdue items stand out |
| Total > 10000 | Blue text | High-value orders are visible |
| Quantity On Hand < 10 | Yellow background | Low stock items are flagged |
| Status = Pending Approval | Italic | Items needing attention |

## Multiple Highlight Rules

You can define multiple highlight rules. They are evaluated in order. The first matching rule applies. If no rule matches, the row uses default formatting.

Example:
```
Rule 1: Days Overdue > 60  → Red background, white text (critical)
Rule 2: Days Overdue > 30  → Yellow background (warning)
Rule 3: Days Overdue > 0   → Italic (attention)
```

This creates a visual hierarchy where the most critical items are most visible.

## Highlighting for Dashboards

Highlighting is especially useful for dashboard portlets, where users glance at results quickly. A dashboard showing overdue orders with red highlights communicates urgency immediately.

## Common Mistakes

- **Too many highlight rules**: More than 3-4 rules become hard to interpret. Focus on the most important conditions.
- **Overlapping rules**: Ensure rule order is correct. The first matching rule wins.
- **Using subtle formatting**: Highlights should be immediately visible. Avoid light colors on white backgrounds.
- **Highlighting everything**: If most rows are highlighted, the highlight loses meaning. Only highlight exceptions.

## Best Practices

- Use 2-3 highlight rules maximum.
- Put the most severe condition first.
- Use color meaningfully (red = bad/critical, yellow = warning, green = good/resolved).
- Test highlighting by running the search with known data.
- Reserve highlighting for dashboard portlets and exception monitoring — it adds little value for export searches.

## Related Articles

- [Results](results.md)
- [Sorting](sorting.md)
- [Performance Best Practices](performance-best-practices.md)
- [Dashboards](../getting-started/dashboards.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Highlighting](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)