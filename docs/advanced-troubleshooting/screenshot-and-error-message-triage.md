---
title: Screenshot and Error Message Triage
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Screenshot and Error Message Triage

## Quick Summary

A screenshot can help diagnose a NetSuite issue, but it should be treated as evidence, not the whole problem. Good triage extracts the visible error, context, record type, user action, role, and likely system layer while avoiding private or sensitive data.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Prerequisites

You should understand:

- NetSuite navigation and record types
- Roles and permissions
- Basic transaction lifecycle
- The difference between UI, script, workflow, and integration behavior

## Overview

Users often ask advanced questions by sharing a screenshot of an error with partial context. An AI assistant should help turn that screenshot into a structured troubleshooting path.

The goal is not to guess the exact fix from the screenshot alone. The goal is to identify what information is visible, what information is missing, and which NetSuite layer should be investigated first.

## Public-Safe Screenshot Rules

Before using screenshot content in a public or shared context, remove or avoid exposing:

- Customer names
- Vendor names
- Employee names
- Email addresses
- Phone numbers
- Addresses
- Transaction numbers if sensitive
- Pricing or margin data
- Account IDs
- Tokens, secrets, or credentials
- Internal notes
- Company-specific custom fields or scripts

If the screenshot includes private data, summarize the relevant error text instead of storing the image in the public repository.

## What to Extract From a Screenshot

### Error Text

Capture the exact visible message when possible.

Useful details:

- Error title
- Error body
- Field name mentioned
- Record type mentioned
- Script or workflow name mentioned
- Transaction status mentioned
- Button or action attempted

### Page Context

Identify where the user was in NetSuite.

Examples:

- Customer record
- Sales order
- Item fulfillment
- Invoice
- Saved search
- Workflow page
- Script deployment
- CSV import status
- Integration record
- RESTlet or Suitelet page

### User Action

The action often matters more than the page.

Examples:

- Save
- Edit
- Approve
- Fulfill
- Bill
- Receive
- Transform
- Import
- Run search
- Execute script
- Send to connector

### Visible Role or Permission Clues

Look for:

- Missing buttons
- Disabled fields
- Permission denied messages
- Different behavior by role
- Search result visibility differences
- Form or center differences

### Timing and Recency

Ask:

- Did this start today, after a release, after a bundle update, or after a configuration change?
- Does it happen every time or intermittently?
- Does it happen for one record, one user, one subsidiary, one item, or one integration process?

## Triage Pattern

Use this sequence when interpreting screenshot-based questions:

1. Extract the exact error text.
2. Identify the record, page, or process shown.
3. Identify the user action that triggered the error.
4. Ask whether the issue affects all users or one role.
5. Ask whether the issue affects all records or only specific records.
6. Identify the most likely layer: permission, data, status, workflow, script, integration, accounting, inventory, or vendor connector.
7. Suggest evidence to confirm the layer before recommending a fix.

## Common Screenshot Patterns

### Permission or Access Error

Likely checks:

- Role permissions
- Subsidiary, department, class, or location restrictions
- Form access
- Saved search audience
- Integration role permissions

Do not recommend giving broad access until the missing permission is identified.

### Missing Required Field Error

Likely checks:

- Required fields on the form
- Hidden mandatory fields
- Workflow-enforced mandatory fields
- Script validation
- Sourced default values
- CSV or API payload completeness

Ask whether the field is visible on the current form.

### Unexpected Error or Script-Like Error

Likely checks:

- Script execution logs
- Workflow execution history
- Recent script deployment changes
- Bundle updates
- Execution context
- Governance or timeout behavior

Ask for the timestamp and action so logs can be narrowed.

### Transaction Cannot Be Processed

Likely checks:

- Approval status
- Posting period
- Fulfillment, billing, receiving, or payment status
- Inventory availability
- Related records already created
- Accounting or feature setup

Compare a working transaction to the failing transaction.

### Integration or Connector Error

Likely checks:

- Connector logs
- Integration role permissions
- Request payload
- NetSuite record validation
- Authentication status
- Vendor service status
- Recent credential, endpoint, or mapping changes

Ask whether the same action works in the NetSuite UI.

## Good AI Response Structure

When responding to a screenshot-based issue, use this structure:

1. **What the screenshot suggests**: summarize only visible facts.
2. **Most likely layers**: list two or three likely categories.
3. **What to check first**: give safe, low-risk checks.
4. **What information would narrow it**: ask for role, record type, action, timing, and recent changes.
5. **Escalation boundary**: mention when a NetSuite admin, developer, tax owner, or integration owner should review.

## Example Response Pattern

> The screenshot appears to show an error while saving a transaction. I would first determine whether this is a required-field, workflow, or script validation issue. Check whether the field mentioned in the error is visible on the current form, whether the same record saves under an administrator role, and whether a workflow or user event script ran at the same timestamp. If this only happens through an integration, compare the API payload to a transaction that saves successfully in the UI.

## Best Practices

- Ask for exact error text if the screenshot is blurry.
- Ask for the action, not only the page.
- Ask whether the issue affects one user, one role, one record, or all records.
- Prefer read-only checks before recommending configuration changes.
- Separate visible facts from assumptions.
- Redact private data before storing or sharing screenshots.

## Common Mistakes

- Assuming the screenshot shows the root cause.
- Ignoring user role and execution context.
- Missing that a field is hidden but still mandatory.
- Forgetting that scripts and workflows can create custom error messages.
- Recommending broad permission changes.
- Treating API, CSV, and UI behavior as identical.

## Related Articles

- [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md)
- [SuiteScript and Workflow Error Triage](suitescript-and-workflow-error-triage.md)
- [Integration Error Triage](integration-error-triage.md)
- [Permissions](../administration/permissions.md)
- [System Notes](../administration/system-notes.md)

## Oracle References

- Oracle NetSuite Help Center: Roles and permissions documentation
- Oracle NetSuite Help Center: System notes documentation
- Oracle NetSuite Help Center: SuiteScript execution logging documentation
- Oracle NetSuite Help Center: SuiteFlow workflow documentation
