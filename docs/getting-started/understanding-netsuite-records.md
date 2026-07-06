---
title: Understanding NetSuite Records
module: Getting Started
difficulty: Beginner
estimated_time: 20 minutes
last_reviewed: 2026-07-06
tags:
  - netsuite
  - records
  - data-model
  - transactions
  - saved-searches
  - workflows
  - suitescript
  - ai-readiness
public_safe: true
---

# Understanding NetSuite Records

## Quick Summary

NetSuite is a record-driven system. Customers, vendors, items, transactions, employees, roles, locations, subsidiaries, files, custom objects, and many configuration objects are represented as records.

Understanding records is one of the most important foundations for learning NetSuite. Saved searches, workflows, SuiteScript, SuiteTalk, REST integrations, reports, dashboards, permissions, forms, and approvals all depend on records.

If you understand what record is involved, how it relates to other records, and what state it is in, most NetSuite problems become easier to reason through.

## Learning Objectives

After reading this article, you should be able to:

- Explain what a NetSuite record is.
- Distinguish master records, transaction records, supporting records, and custom records.
- Understand how records relate to each other.
- Explain why record status, permissions, forms, and customizations affect behavior.
- Use records as the starting point for troubleshooting, reporting, automation, scripting, and integrations.

## What Is a Record?

A record is a structured container for information in NetSuite.

A record usually has:

- A record type
- A unique internal ID
- A name, number, or display value
- Fields
- Sublists
- Related records
- Permissions
- Forms
- System notes or history
- Optional custom fields, workflows, scripts, or integrations

Examples of records include:

- Customer
- Vendor
- Item
- Sales Order
- Purchase Order
- Invoice
- Item Fulfillment
- Item Receipt
- Employee
- Role
- Location
- Subsidiary
- Custom Record

## Why Records Matter

Nearly every NetSuite feature operates on records.

| Feature | How It Uses Records |
|---|---|
| Saved Searches | Search, filter, summarize, and display record data. |
| Reports | Present financial or operational record information. |
| Workflows | Trigger actions when records are created, edited, viewed, or approved. |
| SuiteScript | Reads, creates, updates, deletes, or reacts to records. |
| SuiteTalk and REST APIs | Exchange record data with external systems. |
| Permissions | Control which records and actions a role can access. |
| Forms | Control how record fields and sublists appear to users. |
| Dashboards | Surface record-based reminders, KPIs, reports, and searches. |
| Integrations | Sync records between NetSuite and external systems. |

A user may think they are using a page, menu, or workflow, but underneath that experience is usually a record.

## Major Record Categories

### 1. Master Records

Master records describe core business objects.

Examples:

- Customer
- Vendor
- Partner
- Employee
- Item
- Account
- Location
- Department
- Class
- Subsidiary

Master records often support many transactions. For example, a customer may be connected to estimates, sales orders, invoices, payments, cases, contacts, and opportunities.

### 2. Transaction Records

Transaction records capture business activity.

Examples:

- Estimate
- Sales Order
- Item Fulfillment
- Invoice
- Customer Payment
- Purchase Order
- Item Receipt
- Vendor Bill
- Inventory Adjustment
- Work Order
- Assembly Build
- Journal Entry

Some transaction records post to the general ledger. Others are non-posting but still drive process flow.

### 3. Supporting Records

Supporting records provide classification, setup, or reference data.

Examples:

- Terms
- Units of Measure
- Price Levels
- Payment Methods
- Tax Codes
- Shipping Items
- Billing Schedules
- Accounting Periods
- Manufacturing Routings

Supporting records may not be the main focus of a user request, but they often explain why a transaction behaves a certain way.

### 4. Custom Records

Custom records are account-specific record types created to store information that standard NetSuite records do not cover.

Custom records are powerful, but they are also company-specific. Public documentation should explain custom records conceptually without publishing private custom record names, IDs, fields, or business logic.

## Records vs. Forms

A record is the underlying data object.

A form is the screen layout used to view or edit that record.

The same record type can have multiple forms. A sales order might appear differently for sales, operations, finance, or customer service roles.

Forms can affect:

- Which fields are visible
- Which fields are mandatory
- Field order and layout
- Sublists shown
- Buttons and actions
- Client scripts or workflows attached to the form

Troubleshooting should distinguish between a record issue and a form issue.

## Records vs. Transactions

All transactions are records, but not all records are transactions.

A customer is a record, but it is not a transaction.

A sales order is both a record and a transaction.

A location is a record, but it is not a transaction.

This distinction matters because transaction records may affect process flow, inventory, approval routing, or accounting. Master records usually define entities, items, or classifications used by transactions.

## Record Relationships

Records often connect to other records.

Example sales flow:

```text
Customer
   |
   |-- Estimate
   |-- Sales Order
          |
          |-- Item Fulfillment
          |-- Invoice
                 |
                 |-- Customer Payment
```

Example purchasing flow:

```text
Vendor
   |
   |-- Purchase Order
          |
          |-- Item Receipt
          |-- Vendor Bill
                 |
                 |-- Vendor Payment
```

Example inventory and manufacturing flow:

```text
Item
   |
   |-- Purchase Order
   |-- Item Receipt
   |-- Inventory Adjustment
   |-- Work Order
          |
          |-- Assembly Build
```

Understanding these relationships helps explain why one record cannot be edited, fulfilled, billed, received, closed, deleted, or reported the way a user expects.

## Internal IDs and Display Values

NetSuite often separates what users see from how the system identifies data.

A record may have:

- Name
- Number
- External ID
- Internal ID
- Document number
- Transaction ID
- Script ID

Users often recognize display values. Scripts, integrations, imports, and saved searches may rely on internal IDs, external IDs, or script IDs.

This distinction is important when troubleshooting imports, integrations, formulas, SuiteScript, or saved search criteria.

## Record Status and Lifecycle

Records often move through statuses.

Examples:

- Pending Approval
- Pending Fulfillment
- Partially Fulfilled
- Pending Billing
- Billed
- Closed
- Pending Receipt
- Partially Received
- Paid in Full

Status affects what users can do next.

For example:

- A sales order may not be fulfillable until approved.
- A purchase order may not be billable until items are received, depending on setup.
- A transaction in a closed accounting period may not be editable.
- A work order may require components before it can be built.

When troubleshooting, always check the record status.

## Permissions and Record Access

A role may be able to view one record type but not edit it. Another role may be able to approve but not create. A third role may be restricted by subsidiary, location, department, class, or employee restrictions.

Record access can be affected by:

- Role permissions
- Permission level
- Center type
- Subsidiary restrictions
- Employee restrictions
- Location, department, or class restrictions
- Custom forms
- Workflows
- Scripts

A feature may appear broken when the real issue is that the user's role does not have the correct access.

## Standard Behavior vs. Customized Behavior

NetSuite accounts often include customizations.

A record may be affected by:

- Custom fields
- Custom forms
- Workflows
- User event scripts
- Client scripts
- Scheduled scripts
- Map/reduce scripts
- Bundles
- Integrations
- CSV imports

When behavior seems unusual, do not immediately assume NetSuite standard behavior is wrong. First determine whether customization or automation is affecting the record.

## How Records Connect to Saved Searches

Saved searches are record-based.

Before building a saved search, identify:

- The primary record type
- The business question
- Related records needed
- Criteria
- Results columns
- Summary logic
- Date logic
- Audience

Example:

A request for open orders may start with the Sales Order transaction record. A request for inventory on hand may start with Item, Inventory Balance, or Transaction data depending on the question.

Choosing the wrong primary record type is one of the most common saved search mistakes.

## How Records Connect to Workflows

Workflows act on records.

A workflow usually needs:

- A base record type
- Trigger conditions
- States
- Transitions
- Actions
- Role or field conditions
- Approval or notification logic

A workflow built on the wrong record type may not trigger when expected.

## How Records Connect to SuiteScript

SuiteScript interacts directly with records and record events.

Scripts may:

- Load a record
- Create a record
- Update fields
- Read sublists
- Validate data
- Trigger on save
- Trigger before load
- Trigger after submit
- Process many records in batches

Before scripting, identify whether the problem is truly a scripting problem or whether configuration, workflow, saved search, or training would solve it more simply.

## How Records Connect to Integrations

Integrations usually create, update, retrieve, or sync records.

Integration design should identify:

- System of record
- Record type
- Required fields
- Matching keys
- External IDs
- Field mappings
- Error handling
- Sync direction
- Sync frequency
- Related records

Integration issues often come from missing required fields, mismatched IDs, permissions, invalid record status, or unclear ownership between systems.

## AI Reasoning Pattern

When an AI agent receives a NetSuite request, it should start with records.

Ask:

1. What record type is involved?
2. Is this master data, a transaction, setup data, or a custom record?
3. What related records are upstream or downstream?
4. What is the current record status?
5. What role is the user using?
6. Are permissions, forms, workflows, scripts, or integrations affecting the record?
7. Does this record affect inventory, accounting, reporting, or fulfillment?
8. Is the answer general enough for public documentation, or does it belong in a private repository?

## Troubleshooting Checklist

Use this checklist when a NetSuite issue involves a record:

- [ ] Identify the record type.
- [ ] Confirm whether the record is standard or custom.
- [ ] Check the record status.
- [ ] Review related records.
- [ ] Confirm the user's role and permissions.
- [ ] Check whether the correct form is being used.
- [ ] Check required fields and setup records.
- [ ] Check whether the accounting period is open, if the record posts.
- [ ] Check item, inventory, subsidiary, location, department, and class context where relevant.
- [ ] Check workflows, scripts, bundles, and integrations.
- [ ] Determine whether the fix belongs in configuration, workflow, saved search, script, integration, or process training.

## Common Mistakes

- Thinking NetSuite is menu-driven instead of record-driven.
- Troubleshooting a transaction without checking related records.
- Ignoring status, approval state, or closed periods.
- Confusing display values with internal IDs or external IDs.
- Building saved searches from the wrong base record type.
- Assuming all roles see the same fields and buttons.
- Treating custom behavior as standard NetSuite behavior.
- Publishing private record IDs, custom field IDs, saved search IDs, workflow IDs, or script IDs in public documentation.

## Public-Safe Documentation Guidance

Public documentation may explain:

- What records are
- How record relationships work
- How record status affects behavior
- Why permissions matter
- How records connect to searches, workflows, scripts, and integrations

Public documentation should not publish:

- Private customer, vendor, employee, or item data
- Screenshots from private accounts
- Company-specific custom record structures
- Internal IDs from a live account
- Saved search formulas that reveal proprietary logic
- Workflow or script logic that explains how a specific business operates

## Related Articles

- [NetSuite Foundation Checklist](netsuite-foundation-checklist.md)
- [What Is NetSuite?](what-is-netsuite.md)
- [Lists and Records](lists-and-records.md)
- [Centers and Roles](centers-and-roles.md)
- [Saved Searches](../saved-searches/README.md)
- [Inventory](../inventory/README.md)
- [SuiteScript](../suitescript/README.md)
- [SuiteTalk](../suitetalk/README.md)

## Oracle References To Review

Use Oracle's official NetSuite Help Center and SuiteAnswers for record-specific behavior, permissions, feature availability, scripting APIs, workflow behavior, and integration requirements. This article explains the public-safe reasoning model and should not replace official documentation or account-specific validation.
