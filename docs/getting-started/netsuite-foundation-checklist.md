---
title: NetSuite Foundation Checklist
module: Getting Started
difficulty: Beginner
estimated_time: 15 minutes
last_reviewed: 2026-07-06
tags:
  - netsuite
  - implementation
  - administration
  - discovery
  - ai-readiness
public_safe: true
---

# NetSuite Foundation Checklist

## Quick Summary

Before learning a NetSuite feature in isolation, understand the account foundation around it. Most NetSuite questions are easier to solve when you know the account structure, enabled features, roles, transaction flow, item setup, accounting setup, and reporting requirements.

This checklist helps administrators, consultants, contributors, and AI agents gather the context needed to reason about a NetSuite account without exposing company-specific information.

## Why This Matters

NetSuite is highly configurable. The same menu, transaction, saved search, workflow, or script can behave differently depending on account setup.

A strong foundation helps answer questions like:

- Is this a feature issue, permission issue, process issue, data issue, or customization issue?
- Is the user working in the correct role, subsidiary, location, department, class, or account?
- Is the record standard NetSuite behavior or customized behavior?
- Should the solution use configuration, saved searches, workflows, SuiteScript, integrations, or process training?

## Public-Safe Use

This checklist is intentionally generic. It should not include:

- Internal company process details
- Customer, vendor, employee, or pricing information
- Screenshots from a private NetSuite account
- Custom field IDs, script IDs, workflow IDs, saved search IDs, or internal record IDs
- Proprietary manufacturing, fulfillment, pricing, or approval logic

Use this file to teach what information is needed, not to publish private answers.

## Foundation Areas To Understand

### 1. Account Structure

Gather high-level account context:

- NetSuite edition or major product scope
- OneWorld or single-company structure
- Subsidiaries, if applicable
- Locations
- Departments
- Classes
- Currencies
- Fiscal calendar
- Accounting periods

Why it matters:

Account structure affects transactions, reporting, permissions, accounting, inventory movement, intercompany activity, and saved search results.

### 2. Enabled Features

Identify whether relevant features are enabled before designing a solution.

Examples:

- Advanced Inventory Management
- Multi-Location Inventory
- Bin Management
- Lot or Serial Numbered Inventory
- Advanced Receiving
- Advanced Shipping
- Manufacturing features
- SuiteFlow
- SuiteScript
- SuiteTalk or REST Web Services
- SuiteAnalytics Workbooks

Why it matters:

A process may fail or appear unavailable simply because the required feature is disabled, not because the user is doing something wrong.

### 3. Roles and Permissions

Understand the role being used when the issue occurs.

Gather:

- User role
- Center type
- Relevant permissions
- Subsidiary, location, department, or class restrictions
- Whether the user can view, create, edit, or approve the record
- Whether the issue happens for one role or all roles

Why it matters:

Many NetSuite issues are permission or role-context issues. A feature can exist in the account but still be hidden or unavailable to a specific user.

### 4. Records and Transactions

Identify which records are involved.

Examples:

- Customer
- Vendor
- Item
- Sales Order
- Purchase Order
- Item Receipt
- Item Fulfillment
- Invoice
- Vendor Bill
- Inventory Adjustment
- Work Order
- Assembly Build

For each record, understand:

- Record type
- Status
- Required fields
- Related records
- Approval state
- Posting or non-posting behavior
- Custom fields or forms involved

Why it matters:

NetSuite is record-driven. Most workflows depend on relationships between records, not just one screen or transaction.

### 5. Item and Inventory Setup

For inventory or order issues, gather item context:

- Item type
- Inventory, non-inventory, service, assembly, kit, lot-numbered, or serialized item
- Location availability
- Preferred vendor
- Reorder settings
- Costing method
- Units of measure
- Bin, lot, or serial requirements
- Whether the item can be purchased, sold, fulfilled, or built

Why it matters:

Many sales, purchasing, fulfillment, manufacturing, and accounting issues start with item setup.

### 6. Transaction Flow

Map the business process before solving the feature issue.

Common flows:

```text
Lead -> Prospect -> Customer -> Estimate -> Sales Order -> Item Fulfillment -> Invoice -> Payment
```

```text
Vendor -> Purchase Order -> Item Receipt -> Vendor Bill -> Payment
```

```text
Item Demand -> Work Order -> Issue Components -> Build Assembly -> Fulfill Finished Good
```

Why it matters:

A transaction may be blocked because an earlier step is incomplete, approved incorrectly, missing inventory, or tied to a different location or subsidiary.

### 7. Accounting Impact

For transaction and inventory issues, identify the accounting impact:

- Does the transaction post to the general ledger?
- Which accounts are affected?
- Is the period open?
- Is approval required before posting?
- Does the transaction affect inventory valuation?
- Are subsidiaries, departments, classes, or locations required?

Why it matters:

Operational actions often create accounting consequences. A solution that fixes a screen issue but creates accounting problems is not complete.

### 8. Reporting and Saved Search Needs

Understand how users need to see the information.

Gather:

- Business question
- Record type
- Required filters
- Required columns
- Date logic
- Summary or detail view
- Audience
- Export needs
- Dashboard or reminder needs

Why it matters:

Many NetSuite requests are really visibility requests. A saved search, workbook, report, or dashboard may solve the issue better than customization.

### 9. Customizations and Automation

Identify whether behavior is standard or customized.

Look for:

- Custom forms
- Custom fields
- Custom records
- Workflows
- SuiteScripts
- Bundles
- Integrations
- User event behavior
- Scheduled processes
- Map/reduce processing

Why it matters:

Customized behavior should not be assumed to be standard NetSuite behavior. Troubleshooting must separate core platform behavior from account-specific automation.

### 10. Integration Context

For integration issues, gather:

- External system involved
- Direction of data flow
- Trigger method
- Authentication method
- Record types exchanged
- Field mappings
- Error messages
- Sync frequency
- Retry or failure handling
- System of record

Why it matters:

Integration issues usually involve both NetSuite setup and external system behavior. The system of record must be clear before changing data or logic.

## AI Agent Discovery Questions

When an AI agent receives a NetSuite request, it should ask or infer:

1. What record type or business process is involved?
2. What role is the user using?
3. What transaction or record status is present?
4. Is the issue about setup, permissions, data, process, customization, or integration?
5. Are required features enabled?
6. Is the issue standard NetSuite behavior or account-specific behavior?
7. What result does the business actually need?
8. What private information must stay out of public documentation?

## Troubleshooting Pattern

Use this sequence before recommending a solution:

1. Confirm the business process.
2. Identify the record type.
3. Check feature availability.
4. Check role and permission context.
5. Check required setup and master data.
6. Check transaction status and related records.
7. Check accounting or inventory impact.
8. Check customizations and integrations.
9. Decide whether the fix belongs in configuration, process training, saved search, workflow, script, integration, or private SOP documentation.

## Common Mistakes

- Assuming every account has the same features enabled.
- Treating a permission issue as a feature limitation.
- Building a customization before confirming standard configuration options.
- Ignoring transaction status or approval state.
- Troubleshooting inventory without checking item type and location availability.
- Publishing company-specific saved searches, fields, workflows, or screenshots in public documentation.
- Solving the visible symptom without understanding the business process.

## Definition of a Solid NetSuite Base

A NetSuite knowledge base has a solid foundation when it can explain:

- What the account structure controls
- How roles and permissions affect access
- How records relate to transactions
- How items drive inventory, sales, purchasing, manufacturing, and accounting behavior
- How transaction flows create downstream effects
- How saved searches and reports answer business questions
- How workflows, scripts, and integrations should be evaluated
- What information belongs in public documentation versus private repositories

## Related Articles

- [What Is NetSuite?](what-is-netsuite.md)
- [Navigation](navigation.md)
- [Centers and Roles](centers-and-roles.md)
- [Lists and Records](lists-and-records.md)
- [Saved Searches](../saved-searches/README.md)
- [Inventory](../inventory/README.md)
- [Accounting](../accounting/README.md)
- [SuiteScript](../suitescript/README.md)
- [SuiteTalk](../suitetalk/README.md)

## Oracle References To Review

Use Oracle's official NetSuite Help Center and SuiteAnswers for account-specific setup steps, field behavior, permissions, and feature availability. This article is a public-safe reasoning checklist and should not replace official documentation or account-specific validation.
