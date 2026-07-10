# Advanced NetSuite Troubleshooting

This module helps advanced users, administrators, consultants, developers, and AI assistants reason through complex NetSuite problems.

It is designed for situations where a user provides an error message, screenshot, failed transaction, script issue, workflow behavior, integration response, or partial context and needs a structured path toward diagnosis.

## Learning Order

1. [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md) - How to reason from symptom to likely system layer
2. [Screenshot and Error Message Triage](screenshot-and-error-message-triage.md) - How to use screenshot context safely and effectively
3. [SuiteScript and Workflow Error Triage](suitescript-and-workflow-error-triage.md) - How to separate script, workflow, deployment, and governance issues
4. [Integration Error Triage](integration-error-triage.md) - How to reason through REST, SOAP, connector, CSV, and middleware failures
5. [Customer Credit Automation Pattern](customer-credit-automation-pattern.md) - How to evaluate saved search, workflow, payment-stage, or scripted approaches for unapplied customer credits
6. [Advanced Saved Search Diagnostics](advanced-saved-search-diagnostics.md) - How to diagnose missing rows, duplicates, formulas, joins, summaries, and role-specific search behavior
7. [Permissions and Role Difference Diagnostics](permissions-and-role-difference-diagnostics.md) - How to troubleshoot access, visibility, forms, data restrictions, workflows, scripts, and integration roles
8. [SuiteFlow Automation Patterns](suiteflow-automation-patterns.md) - How to design and troubleshoot workflow reminders, approvals, blocking, routing, and escalation
9. [SuiteTalk REST and SOAP Troubleshooting](suitetalk-rest-soap-troubleshooting.md) - How to diagnose authentication, permissions, payload, transform, and response issues in integrations
10. [Transaction Lifecycle Troubleshooting](transaction-lifecycle-troubleshooting.md) - How to diagnose sales, purchasing, inventory, accounting, AR, and AP transaction state issues
11. [SuiteScript Troubleshooting Deep Dive](suitescript-troubleshooting-deep-dive.md) - How to troubleshoot script type, deployment, context, permissions, governance, logs, and automation overlap
12. [SuiteAnalytics and Reporting Troubleshooting](suiteanalytics-reporting-troubleshooting.md) - How to troubleshoot reports, workbooks, datasets, dashboards, KPIs, summaries, and performance

## What This Module Is For

Use this module when the question is more complex than a basic how-to.

Examples:

- A user shares a screenshot of a NetSuite error and asks what to check next.
- A transaction will not save, approve, fulfill, bill, or post.
- A saved search, workflow, script, or integration behaves differently for different roles.
- An external system cannot create or update a NetSuite record.
- A process worked previously but began failing after a configuration, release, bundle, role, or data change.
- An accounts receivable process needs safer visibility, review, or automation around unapplied customer credits.
- A saved search has missing rows, duplicate rows, wrong totals, formula errors, or role-specific results.
- One user can perform an action but another user cannot.
- A workflow, script, SuiteTalk integration, report, workbook, dashboard, or transaction process behaves differently than expected.

## Troubleshooting Mindset

Advanced troubleshooting should identify the system layer before proposing a fix.

Common layers include:

- User role and permissions
- Form, field, and mandatory data configuration
- Record status or transaction lifecycle
- Workflow conditions and actions
- SuiteScript execution and deployment context
- Saved search criteria, joins, and formulas
- SuiteTalk REST, SOAP, RESTlet, or connector integration behavior
- Reporting source, workbook dataset, dashboard, and KPI behavior
- Accounting period, posting, tax, inventory, or fulfillment constraints
- Vendor platform behavior for integrations such as Pacejet, SPS Commerce, and Avalara

## Public-Safe Rule

Keep examples generic. Do not include company-specific SOPs, customer examples, custom fields, saved searches, workflows, SuiteScripts, screenshots, pricing, credentials, proprietary processes, or details that reveal how a specific organization operates.

## Related Modules

- [Administration](../administration/README.md)
- [Saved Searches](../saved-searches/README.md)
- [SuiteScript](../suitescript/overview.md)
- [SuiteTalk REST](../suitetalk/rest-overview.md)
- [Integrations](../integrations/README.md)
