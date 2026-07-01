---
title: Saved Search vs. Reports
module: Saved Searches
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Saved Search vs. Reports

## Quick Summary

Saved Searches and NetSuite Reports serve different purposes. Saved Searches are flexible, user-driven operational tools. Reports are structured, presentation-ready financial documents. Choosing the right tool depends on what you need to accomplish.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

New NetSuite users often wonder: "Should I use a Saved Search or a Report?" The answer depends on what you are trying to do. Both tools access the same data, but they present it differently and serve different audiences.

## Key Differences

| Dimension | Saved Search | Report |
|---|---|---|
| **Purpose** | Operational monitoring, data extraction, exception tracking | Financial reporting, formal presentation |
| **Flexibility** | Highly flexible — you define everything | Structured — NetSuite defines the layout |
| **Output format** | Table of rows and columns | Formatted document with headers, summaries, and totals |
| **Export** | CSV export | CSV, PDF, HTML, Excel |
| **Sharing** | By role or personal | By role or personal |
| **Dashboard** | Portlet | Report can be displayed in a portlet |
| **Permissions** | Search permissions | Report permissions |
| **Learning curve** | Steeper — requires understanding criteria/results | Gentler — choose fields from a list |

## When to Use a Saved Search

Use a Saved Search when:

- **You need operational data** — "Show me all open sales orders"
- **You need to customize columns and filters** — "I want specific fields in a specific order"
- **You need to group and summarize** — "Total sales by region"
- **You need formulas** — "Days overdue, profit margin, custom calculations"
- **You need the data elsewhere** — CSV export, SuiteScript, workflow trigger
- **You need scheduled emails** — Regular data delivery to specific users
- **You need exception monitoring** — "Items below reorder point, overdue invoices"

## When to Use a Report

Use a Report when:

- **You need formatted financial statements** — Balance sheets, income statements, cash flow
- **You need presentation-ready output** — Headers, footers, page breaks, company logos
- **You need standard financial layouts** — Trial balance, general ledger, transaction detail
- **You are preparing external documents** — Audit reports, financial statements, board materials
- **You need drill-down to transactions** — Report totals link back to underlying records

## Comparison by Use Case

| Use Case | Better Tool | Why |
|---|---|---|
| Monthly sales by region | Saved Search | Custom grouping, flexible date range |
| Balance sheet | Report | Standard financial format |
| Inventory low stock alert | Saved Search | Exception monitoring, dashboard portlet |
| Customer aging | Both | Aged receivables report is standard; but a Saved Search gives more filter options |
| Data extract for integration | Saved Search | CSV export, flexible columns |
| Board presentation | Report | Formatted output, professional appearance |
| Daily open orders dashboard | Saved Search | Live data, custom columns |
| Year-end financial statements | Report | Audit-ready format, GAAP compliance |

## Case Study: Monthly Sales Report

### Using a Saved Search

- Group by customer or sales rep
- Sum total by period
- Add Available Filters for date range and department
- Export to CSV for further analysis
- Add to dashboard as a portlet

### Using a Report

- Select "Sales by Customer" report
- Choose date range
- View formatted output with totals and subtotals
- Print or export as PDF
- Drill down to individual transactions

### Which to Choose?

If you need **flexibility** and **custom data** → Saved Search

If you need **formatting** and **presentation** → Report

## Real-World Pattern

Most organizations use both:

- **Saved Searches** for daily operations, monitoring, and data extraction
- **Reports** for period-end financials, audits, and external communication

The tools complement each other. A financial controller might run Saved Searches for weekly monitoring and standard reports for month-end close.

## Related Articles

- [Saved Search vs. SuiteAnalytics](saved-search-vs-suiteanalytics.md)
- [What Is a Saved Search?](what-is-a-saved-search.md)
- [Performance Best Practices](performance-best-practices.md)
- [Real-World Business Examples](real-world-business-examples.md)

## Oracle References

- [Oracle NetSuite Help Center: Reports vs. Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)