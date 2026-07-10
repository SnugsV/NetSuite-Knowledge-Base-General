---
title: SuiteAnalytics and Reporting Troubleshooting
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# SuiteAnalytics and Reporting Troubleshooting

## Quick Summary

SuiteAnalytics and reporting issues often come from data source choice, joins, permissions, date logic, summary logic, dashboard context, workbook datasets, or performance constraints. Diagnose whether the problem is data access, data model, calculation, presentation, or timing.

## Difficulty

Advanced

## Estimated Time

30 minutes

## Prerequisites

You should understand:

- Saved searches
- Reports
- SuiteAnalytics Workbooks
- Datasets
- Dashboards and KPIs
- Roles and permissions
- Transaction status and accounting periods

## Overview

NetSuite offers multiple reporting tools. A question that seems like a reporting issue may actually be a data model, role permission, transaction lifecycle, accounting period, or search logic issue.

Common reporting surfaces include:

- Saved searches
- Standard reports
- Custom reports
- SuiteAnalytics Workbooks
- Datasets
- KPIs and scorecards
- Dashboards and portlets
- Exports and integrations

## Public-Safe Boundary

Do not publish private reports, financial results, customer or vendor names, custom field IDs, formulas, screenshots, dashboard layouts, saved search names, workbook datasets, or internal reporting logic.

## Tool Selection

### Saved Search

Best for:

- Operational lists
- Alerts and dashboards
- Workflow/script inputs
- Exports
- Exception monitoring

Watch for criteria, joins, formulas, summaries, and role-specific results.

### Standard or Custom Report

Best for:

- Financial and operational reporting using NetSuite report frameworks
- Period-based analysis
- Familiar report layouts

Watch for accounting period, subsidiary, date, and audience behavior.

### SuiteAnalytics Workbook

Best for:

- Interactive analysis
- Datasets
- Pivot-style exploration
- Visualizations
- Users who need self-service analytics

Watch for dataset design, joins, measures, dimensions, permissions, and performance.

### Dashboard or KPI

Best for:

- At-a-glance monitoring
- Role-based operational views
- Exception visibility

Watch for portlet audience, role context, refresh timing, and source search/report logic.

## First Questions to Ask

1. Which reporting tool is involved: saved search, report, workbook, dataset, KPI, dashboard, or export?
2. What is wrong: missing data, duplicate data, wrong totals, blank values, formula errors, performance, or role-specific results?
3. What record type or dataset is the report based on?
4. Does the issue happen for all users or only some roles?
5. Does the issue happen in detail view, summary view, dashboard view, and export?
6. Are transactions, accounting periods, subsidiaries, currencies, or custom segments involved?
7. Did a field, role, workbook, saved search, release, bundle, workflow, or script change recently?

## Diagnostic Layers

### Layer 1: Reporting Surface

Check:

- Saved search vs report vs workbook vs dashboard
- Whether the tool fits the question
- Whether the same source behaves differently in another surface
- Whether the issue is in the data source or presentation layer

### Layer 2: Data Source and Record Model

Check:

- Base record or dataset
- Transaction header vs line-level data
- Joins and related records
- Measures and dimensions
- Accounting period, posting, and status fields

### Layer 3: Criteria and Filters

Check:

- Date field and date range
- Subsidiary, location, department, class, and custom segment filters
- Status filters
- Posting vs non-posting filters
- Inactive records
- User-specific or role-specific filters

### Layer 4: Calculations and Summaries

Check:

- Formula type
- Null handling
- Summary type
- Currency and exchange rate assumptions
- Duplicate line-level rows
- Aggregation grain

### Layer 5: Permissions and Audience

Check:

- Report or workbook audience
- Dataset access
- Base record permissions
- Joined record permissions
- Field visibility
- Subsidiary or segment restrictions
- Dashboard portlet audience

### Layer 6: Performance and Refresh Timing

Check:

- Result size
- Heavy joins or formulas
- Large date ranges
- Dashboard refresh timing
- Workbook dataset complexity
- Export volume
- Whether a scheduled or staged report is more appropriate

## Common Symptoms

### Dashboard Shows Different Results

Likely causes:

- Portlet audience or role context
- Cached or refreshed data timing
- Search/report source differs from expected
- User-specific filters
- Role restrictions

### Workbook Totals Do Not Match Saved Search

Likely causes:

- Different data source
- Different joins or grain
- Different date field
- Summary logic mismatch
- Role or subsidiary restrictions

### Report Is Slow

Likely causes:

- Large date range
- Heavy joins
- Complex formulas
- Too many columns or groupings
- Detail-level result when summary would work
- Dashboard or export use case better served by a narrower source

### Financial Report Does Not Match Operational Search

Likely causes:

- Posting vs non-posting transaction difference
- Accounting period vs transaction date difference
- Currency or exchange-rate logic
- Header vs line-level data
- Closed or adjusted transactions
- Different subsidiary or book context

## Safe Diagnostic Path

1. Identify the reporting surface and source.
2. Clarify the expected result in plain language.
3. Compare detail and summary views.
4. Confirm date, period, status, posting, subsidiary, and currency logic.
5. Check joins and aggregation grain.
6. Test with the affected role.
7. Compare dashboard, export, and edit/preview behavior.
8. Narrow the source before optimizing performance.
9. Document the final reporting rule and owner.
10. Keep sensitive reporting logic out of public docs.

## AI Assistant Response Pattern

When a user asks about a reporting or analytics issue, the assistant should:

1. Ask which reporting surface is involved.
2. Ask whether the problem is missing data, duplicates, wrong totals, blank values, performance, or role-specific results.
3. Diagnose source, filters, joins, calculations, permissions, and refresh timing.
4. Ask whether accounting periods, subsidiaries, currencies, or transaction lines are involved.
5. Recommend comparing detail vs summary and affected role vs administrator carefully.
6. Keep examples generic and avoid exposing private report logic.

## Related Articles

- [Advanced Saved Search Diagnostics](advanced-saved-search-diagnostics.md)
- [Permissions and Role Difference Diagnostics](permissions-and-role-difference-diagnostics.md)
- [Transaction Lifecycle Troubleshooting](transaction-lifecycle-troubleshooting.md)
- [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md)
- [Reports](../saved-searches/reports.md)
- [SuiteAnalytics](../saved-searches/suiteanalytics.md)

## Oracle References

- Oracle NetSuite Help Center: Reporting Guide
- Oracle NetSuite Help Center: Search Guide
- Oracle NetSuite Help Center: SuiteAnalytics Workbook Guide
- Oracle NetSuite Help Center: Dashboards Guide
- Oracle NetSuite Help Center: SuiteAnalytics Connect Guide
