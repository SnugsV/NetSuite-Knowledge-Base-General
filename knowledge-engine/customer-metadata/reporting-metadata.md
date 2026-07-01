# Reporting Metadata

## Purpose

Defines exactly what metadata must be collected before designing SuiteAnalytics Workbooks, dashboards, KPIs, or custom reports. Reporting solutions depend heavily on the customer's data structure, field availability, and user access.

## Required Metadata

### SuiteAnalytics Workbooks

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Business question to answer** | Defines what the workbook should show | Ask: "What question are you trying to answer with this workbook?" |
| **Data sources required** | One or multiple record types — determines dataset design | Ask: "What data sources does this workbook need?" |
| **Record types and relationships** | How record types relate to each other (e.g., Sales Order → Item Fulfillment) | Ask: "How do these records relate to each other?" |
| **User role** | Determines which data the user can see | Ask: "What role will use this workbook?" |
| **Output format** | Table, chart, pivot, or combination | Ask: "Do you need a table, chart, or both?" |

### Dashboards

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Dashboard center** | Home, Sales, Inventory, or custom center | Ask: "Which center should this dashboard appear in?" |
| **Target audience** | Role-specific or public | Ask: "Who should see this dashboard?" |
| **Portlet types needed** | Saved search, KPI, report snapshot, or custom portlet | Ask: "What type of information should appear on this dashboard?" |
| **Existing dashboards** | Avoids duplicating existing dashboard content | Ask: "What dashboards do you already have?" |

### KPIs

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Metric definition** | What is being measured (revenue, orders, fulfillment rate) | Ask: "What specific metric do you want to track?" |
| **Time period** | Current period, rolling 12 months, custom | Ask: "What time period should this KPI cover?" |
| **Target or benchmark** | Determines whether the KPI shows performance vs. target | Ask: "Is there a target value for this KPI?" |
| **Source data** | Saved search, summary search, or formula | Ask: "Where does this data come from?" |

### Reports (Standard or Custom)

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Report type** | Financial, transaction, list, or custom | Ask: "What type of report do you need?" |
| **Standard report that is close** | May only need modification rather than creation | Ask: "Is there a standard report that is almost what you need?" |
| **Frequency** | One-time, daily, monthly, quarterly | Ask: "How often will this report be run?" |
| **Distribution method** | View in NetSuite, email, CSV export, PDF | Ask: "How should the report be delivered?" |

## Optional Metadata

| Metadata Item | Why It Matters |
|---|---|
| **Sample output from another system** | Helps visualize what the customer expects |
| **Existing dashboard screenshots** | Shows current layout and content |
| **User preferences for layout** | Determines portlet arrangement and visual design |
| **Color or branding requirements** | Dashboard design may need to match company branding |
| **Mobile vs. desktop usage** | Dashboard layout differs by device |

## Validation Checklist

- [ ] Business question confirmed — what is the report trying to answer?
- [ ] Data sources identified and relationships understood
- [ ] User role confirmed for visibility
- [ ] Output format confirmed (table, chart, both)
- [ ] Dashboard center and audience confirmed (if applicable)
- [ ] Existing dashboards/reports reviewed for reuse
- [ ] KPI target or benchmark defined (if applicable)
- [ ] Frequency and distribution method confirmed

## Common Metadata Gaps

| Gap | Impact | Recovery |
|---|---|---|
| Business question unclear | Report does not answer the right question | Clarify the business objective before designing |
| Data sources not identified | Workbook pulls from wrong record type | Identify all data sources needed |
| User role unknown | User cannot see expected results | Confirm the target user's role |
| Existing reports not checked | Duplicate work | Ask about existing reports first |
| Frequency not defined | Report is built for wrong schedule | Confirm how often the report is needed |

## Confidence Impact

| Metadata Collected | Confidence |
|---|---|
| All required + sample output available | High |
| All required + some optional | Medium |
| Business question unclear or role unknown | Low |
| Required metadata missing | Unknown — do not proceed |

## Related Documents

- [METADATA_REASONING.md](METADATA_REASONING.md)
- [Solution Architect: Capability Reference](../solution-architect/capability-reference.md)