# Capability Reference

## Purpose

Detailed evaluation of each NetSuite capability. Use this reference when comparing solutions for a business requirement.

## Saved Search

| Dimension | Evaluation |
|---|---|
| **When to use** | List data matching criteria, daily email alerts, exportable data, simple dashboards |
| **When not to use** | Formatted reports, interactive analysis, real-time dashboards, multi-source calculations |
| **Advantages** | Fast to build, easy to maintain, no coding, scheduleable, shareable |
| **Trade-offs** | Limited formatting, no drill-down, performance degrades with large datasets |
| **Maintenance** | Minimal — review periodically for criteria accuracy |
| **Performance** | Excellent for indexed fields with date ranges; degrades on non-summary large datasets |
| **Skill level** | Beginner to intermediate |
| **Routing** | [Saved Search Builder Skill](../ai-skills/saved-search-builder.md) |

## SuiteAnalytics Workbook

| Dimension | Evaluation |
|---|---|
| **When to use** | Ad-hoc analysis, formatted reports, drill-down, charts, cross-record type data |
| **When not to use** | Automated email alerts, simple lists, daily reports |
| **Advantages** | Better formatting than saved searches, drag-and-drop, charting, multi-source datasets |
| **Trade-offs** | Cannot be scheduled for email, requires SuiteAnalytics license, steeper learning curve |
| **Maintenance** | Low — workbooks are rebuilt per session or saved for reuse |
| **Performance** | Excellent — optimized for analytic queries |
| **Skill level** | Intermediate |

## Dashboard / KPI

| Dimension | Evaluation |
|---|---|
| **When to use** | Real-time visibility for specific metrics, executive views, at-a-glance monitoring |
| **When not to use** | Detailed data exploration, transactional reports, exportable lists |
| **Advantages** | Real-time, visual, customizable per user or role |
| **Trade-offs** | Limited to portlet-sized data, no deep analysis within the dashboard |
| **Maintenance** | Low — update portlet sources when searches change |
| **Performance** | Real-time — uses live data |
| **Skill level** | Beginner |

## Workflow (SuiteFlow)

| Dimension | Evaluation |
|---|---|
| **When to use** | Automated approval routing, field updates on state change, email notifications, record creation |
| **When not to use** | Complex logic with many conditions, large data processing, real-time integrations |
| **Advantages** | No coding, visual designer, built-in approval system, audit trail |
| **Trade-offs** | Limited to 400 actions per workflow, no external calls, debugging is difficult |
| **Maintenance** | Moderate — workflow changes must be tested thoroughly |
| **Performance** | Good for standard automation; degrades with complex branching |
| **Skill level** | Intermediate |

## SuiteScript

| Dimension | Evaluation |
|---|---|
| **When to use** | Custom business logic beyond workflow capability, integrations, complex calculations, data transformations |
| **When not to use** | Simple automation that workflows can handle, one-time data imports, requests that need configuration changes |
| **Advantages** | Unlimited flexibility, full API access, can call external systems, performance can be optimized |
| **Trade-offs** | Requires JavaScript knowledge, governed by script limits, adds technical debt, needs testing |
| **Maintenance** | High — scripts must be maintained, updated for NetSuite releases, monitored for governance |
| **Performance** | Varies — well-written scripts are fast; poorly written scripts cause governance issues |
| **Skill level** | Advanced |

## RESTlet (SuiteScript API)

| Dimension | Evaluation |
|---|---|
| **When to use** | Real-time API endpoints for external systems, custom web services, integration with third-party apps |
| **When not to use** | Batch data processing (use Map/Reduce), internal process automation |
| **Advantages** | Real-time, standard REST API, accessible from any system, authentication built in |
| **Trade-offs** | Requires API management, governed by script limits, needs security review |
| **Maintenance** | High — API contracts must be versioned and maintained |
| **Performance** | Real-time — depends on the operation complexity |
| **Skill level** | Advanced |

## Map/Reduce Script

| Dimension | Evaluation |
|---|---|
| **When to use** | Large-scale data processing, batch updates, data migration, periodic transformations |
| **When not to use** | Real-time operations, simple one-record updates, automation that workflows handle |
| **Advantages** | Processes large volumes efficiently, resumable on failure, governed by script limits |
| **Trade-offs** | Complex to write and debug, long-running, must handle errors gracefully |
| **Maintenance** | High — must be monitored for governance and failure |
| **Performance** | Excellent for large data volumes — parallelized |
| **Skill level** | Advanced |

## CSV Import

| Dimension | Evaluation |
|---|---|
| **When to use** | One-time data loads, initial migrations, periodic data updates from external files |
| **When not to use** | Real-time data exchange, frequent automated imports, complex data transformations |
| **Advantages** | Simple, no coding, built-in mapping, handles large volumes |
| **Trade-offs** | Manual process, error handling is limited, data validation is basic |
| **Maintenance** | Low — define import templates |
| **Performance** | Fast — optimized bulk import |
| **Skill level** | Beginner |

## SuiteTalk (SOAP/REST Web Services)

| Dimension | Evaluation |
|---|---|
| **When to use** | System-to-system integration, automated data sync, enterprise application integration |
| **When not to use** | Simple one-time imports, UI-level automation |
| **Advantages** | Enterprise-grade, full record access, standard protocols, supports many languages |
| **Trade-offs** | Requires programming, complex setup, governed by API limits |
| **Maintenance** | Moderate — API changes must be tracked |
| **Performance** | Good — depends on operation volume and complexity |
| **Skill level** | Advanced |

## Native Configuration

| Dimension | Evaluation |
|---|---|
| **When to use** | Feature enablement, preference changes, standard settings |
| **When not to use** | Requirements outside standard functionality |
| **Advantages** | No code, low maintenance, fully supported, upgrade-safe |
| **Trade-offs** | Limited to what the feature provides |
| **Maintenance** | Minimal |
| **Performance** | Native — best possible |
| **Skill level** | Beginner to intermediate |

## Custom Record / Custom Field

| Dimension | Evaluation |
|---|---|
| **When to use** | Standard records do not capture all needed data, new data types needed, business-specific classifications |
| **When not to use** | Standard fields exist but are not used, requirement needs multi-record relationships |
| **Advantages** | Extends standard functionality, no code for simple fields, fully integrated |
| **Trade-offs** | Adds complexity to forms and searches, custom fields can slow performance at scale |
| **Maintenance** | Moderate — fields should be documented and reviewed |
| **Performance** | Good — indexed custom fields perform well |
| **Skill level** | Intermediate |

## Third-Party SuiteApp

| Dimension | Evaluation |
|---|---|
| **When to use** | Specialized functionality not in native NetSuite, industry-specific solutions, time-to-market priority |
| **When not to use** | Simple configuration changes, requirements that could be met with standard features |
| **Advantages** | Faster to implement than building custom, vendor-supported, often includes best practices |
| **Trade-offs** | Ongoing licensing cost, vendor dependency, may not fully meet requirements |
| **Maintenance** | Low (vendor-managed) — but version upgrades may change behavior |
| **Performance** | Variable — depends on the SuiteApp quality |
| **Skill level** | Varies |

## Related Documents

- [Solution Selection Trees](solution-selection-trees.md)
- [SOLUTION_ARCHITECT_REASONING.md](SOLUTION_ARCHITECT_REASONING.md)
- [Routing to AI Skills](routing-to-skills.md)