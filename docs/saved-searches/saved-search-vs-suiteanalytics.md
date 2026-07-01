---
title: Saved Search vs. SuiteAnalytics
module: Saved Searches
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Saved Search vs. SuiteAnalytics

## Quick Summary

SuiteAnalytics is NetSuite's advanced analytics platform for creating custom datasets, workbooks, and visualizations. While Saved Searches are ideal for operational reporting, SuiteAnalytics handles multi-table analysis, ad-hoc exploration, and visual dashboards.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Both Saved Searches and SuiteAnalytics access NetSuite data, but they approach it from different angles. Saved Searches are query-based: you define criteria and get tabular results. SuiteAnalytics is exploration-based: you build datasets by selecting fields and relationships, then visualize them in workbooks.

## Key Differences

| Dimension | Saved Search | SuiteAnalytics |
|---|---|---|
| **Primary use** | Operational monitoring, data extraction | Ad-hoc analysis, visualization, discovery |
| **Interface** | Form-based (criteria + results) | Drag-and-drop canvas |
| **Data model** | Single record type with joins | Multi-table datasets with relationships |
| **Output** | Table of rows | Tables, charts, pivot tables, workbooks |
| **Performance** | Fast for simple queries | Slower but designed for complex analysis |
| **Sharing** | By role | By role, workbook sharing |
| **Export** | CSV | CSV, Excel, PDF |
| **Learning curve** | Moderate | Steeper — requires understanding of data modeling |

## When to Use a Saved Search

- **Daily operational monitoring** — "Open orders, low stock, overdue invoices"
- **Simple data extraction** — "Customer email list, item price list"
- **Exception alerts** — "Items below reorder point"
- **Scheduled email delivery** — Regular reports to specific recipients
- **Dashboard portlets** — Live data on dashboards
- **SuiteScript data source** — Programmatic record queries
- **Workflow triggers** — Searches that initiate automated processes

## When to Use SuiteAnalytics

- **Cross-record analysis** — "Revenue by customer by product category by month"
- **Ad-hoc exploration** — "I wonder what our sales pattern looks like by region"
- **Visual dashboards** — Interactive charts and pivot tables
- **Data discovery** — Finding patterns and trends in large data sets
- **Complex joins** — Multi-table relationships that are difficult in Saved Searches
- **Advanced filtering** — Multiple levels of nested filters

## Comparison by Use Case

| Use Case | Better Tool | Why |
|---|---|---|
| Open sales orders list | Saved Search | Simple, fast, dashboard-ready |
| Revenue trend by customer and region | SuiteAnalytics | Multi-dimensional, visual output |
| Daily low stock alert | Saved Search | Automated, scheduled, portlet |
| Year-over-year sales analysis | SuiteAnalytics | Date comparisons, visual trends |
| Customer email list | Saved Search | Simple CSV export |
| Profitability by item and customer | SuiteAnalytics | Multi-table, calculated measures |
| Items needing reorder | Saved Search | Simple criteria, scheduled |
| Sales territory performance | SuiteAnalytics | Visual, drillable, interactive |

## SuiteAnalytics Strengths

- **Workbooks** — Interactive reports with multiple views (table, chart, pivot)
- **Datasets** — Define once, reuse across workbooks
- **Calculated measures** — Advanced aggregations and formulas
- **Visualizations** — Bar charts, line charts, pie charts, heat maps
- **Drill-down** — Click from summary to detail
- **Cross-record analysis** — Link transactions, items, customers, and more in a single analysis

## When Both Work

In some cases, either tool can work, but one is more efficient:

| Task | Saved Search | SuiteAnalytics |
|---|---|---|
| "Total sales by customer this month" | Summary search, grouped by customer | Dataset with customer and transaction join |
| "Items with no sales in 6 months" | Item search with criteria | Item dataset with sales join |
| "Open purchase orders by vendor" | Transaction search, filtered | Dataset with purchase order and vendor |

## Real-World Pattern

The most common pattern is to use both tools in combination:

- **Saved Searches** for daily operational reports, alerts, and dashboards
- **SuiteAnalytics** for deep-dive analysis, trend identification, and ad-hoc exploration

A warehouse manager uses Saved Searches for daily stock checks. The supply chain analyst uses SuiteAnalytics for quarterly demand forecasting.

## Which Should You Learn First?

Learn **Saved Searches** first. They are:

- Available to every NetSuite user (SuiteAnalytics may require additional licensing)
- Simpler to learn and use
- More widely applicable for daily work
- A foundation for understanding NetSuite's data model

Move to **SuiteAnalytics** when you need:

- Multi-dimensional analysis
- Visual data exploration
- Complex calculated metrics
- Cross-record relationships

## Related Articles

- [Saved Search vs. Reports](saved-search-vs-reports.md)
- [What Is a Saved Search?](what-is-a-saved-search.md)
- [Performance Best Practices](performance-best-practices.md)
- [Real-World Business Examples](real-world-business-examples.md)

## Oracle References

- [Oracle NetSuite Help Center: SuiteAnalytics](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: SuiteAnalytics Workbook Overview](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)