---
title: What Is a Saved Search?
module: Saved Searches
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed:
---

# What Is a Saved Search?

## Quick Summary

A Saved Search is a reusable query in NetSuite that searches records based on criteria you define, displays only the columns you choose, and can be saved, shared, scheduled, and embedded on dashboards. It is the most flexible reporting tool available to every NetSuite user.

## Difficulty

Beginner

## Estimated Time

5 minutes

## Overview

At its simplest, a Saved Search is a question you ask your data. Every record in NetSuite — customers, items, sales orders, invoices, employees — contains fields of information. A Saved Search lets you filter those records to find exactly what you need and display the results in a useful format.

Unlike a one-time search (like Global Search), a Saved Search is saved permanently. You can run it again tomorrow, share it with your team, add it to a dashboard, or have it emailed to you on a schedule.

## What Makes a Saved Search Valuable

### Reusability

You define a search once and run it any time. If you find yourself navigating to the same list or report every day, a Saved Search replaces those clicks with a single click.

### Flexibility

Saved Searches can be simple or complex:

- "Show me all sales orders from last week" — two criteria
- "Show me customers with overdue invoices, grouped by sales rep, with a formula calculating days overdue, only where the total exceeds $10,000" — twelve criteria, a join, a formula, and a summary type

Both are Saved Searches. The difference is in how you configure them.

### Sharing

A Saved Search can be personal (only you see it), shared with your role, or made available to everyone in the account. This makes them a team productivity tool, not just a personal one.

### Automation

Saved Searches can be:

- Emailed on a schedule (daily, weekly, monthly)
- Added to dashboards as portlets
- Used as data sources for SuiteScript
- Exported to CSV
- Integrated into approvals and workflows

### The Bridge Between Operations and Reporting

Saved Searches sit between raw data and formal reports. They give operational users — warehouse managers, sales leads, customer service supervisors — the ability to build their own monitoring tools without waiting for a report developer.

## A Simple Example

Imagine you manage a warehouse. Every day you want to see:

- Items with quantity on hand below 10 units
- Items received in the last 24 hours
- Items that haven't moved in 90 days

Each of these is a Saved Search. You create them once, add them to your dashboard, and check them every morning. No menus to navigate, no filters to set — the search is already configured.

## How Saved Searches Fit in NetSuite

```
Raw Data (records, transactions)
    ↓
Saved Searches (filter, display, group, calculate)
    ↓
Dashboards │ Reports │ Email │ CSV │ SuiteScript │ Workflows
```

## Common Myths

- **"Saved Searches are just for administrators"**: Anyone with the appropriate permissions can create saved searches.
- **"Saved Searches are the same as reports"**: Reports have fixed structures optimized for financial presentation. Saved Searches are more flexible for operational use. See [Saved Search vs. Reports](saved-search-vs-reports.md).
- **"Saved Searches are slow"**: With proper configuration, saved searches perform well even on large data sets. Performance issues are usually caused by overly complex criteria or missing filters. See [Performance Best Practices](performance-best-practices.md).
- **"I need SuiteScript to do useful searches"**: Most business needs can be met with saved searches alone. SuiteScript becomes necessary only when you need to use search results programmatically.

## Related Articles

- [Saved Search Types](saved-search-types.md)
- [Building Your First Search](building-your-first-search.md)
- [Saved Search vs. Reports](saved-search-vs-reports.md)
- [Global Search](../getting-started/global-search.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)