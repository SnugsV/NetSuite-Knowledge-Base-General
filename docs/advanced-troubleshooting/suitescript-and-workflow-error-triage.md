---
title: SuiteScript and Workflow Error Triage
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 25 minutes
status: Draft
last_reviewed:
---

# SuiteScript and Workflow Error Triage

## Quick Summary

When NetSuite behavior changes unexpectedly, SuiteScript and workflows are common causes. The fastest path is to identify what ran, when it ran, in what context, and whether the issue is caused by script logic, workflow conditions, deployment settings, permissions, governance limits, or record data.

## Difficulty

Advanced

## Estimated Time

25 minutes

## Prerequisites

You should understand:

- NetSuite records and transactions
- SuiteScript script types
- Workflow states and actions
- Roles, forms, and execution contexts
- Basic log review

## Overview

SuiteScript and workflows often overlap. A transaction save may trigger a client script, user event script, workflow action, field sourcing rule, validation rule, scheduled script, Map/Reduce process, or integration script.

Good troubleshooting avoids assuming which automation is responsible. Instead, it narrows the issue by timestamp, record type, execution context, and recent changes.

## First Questions to Ask

1. What record type or transaction type is affected?
2. What action triggered the issue: edit, save, approve, transform, import, API update, scheduled run, or button click?
3. Does it happen in the UI, CSV import, REST/SOAP, RESTlet, Suitelet, scheduled process, or connector?
4. Does it happen for all users or only some roles?
5. Does it happen for all records or only records with certain data?
6. What changed recently: script deployment, workflow edit, bundle update, role change, form change, release, or data import?
7. What exact timestamp should be checked in logs?

## Separate Script Issues From Workflow Issues

### Clues That Point Toward SuiteScript

- Error appears after save, submit, transform, or integration update
- Error mentions script execution, unexpected error, or a technical exception
- Issue appears in execution logs
- Behavior depends on script deployment audience or status
- Issue appears in API, scheduled, Map/Reduce, RESTlet, Suitelet, or user event context
- Processing stops after a large dataset, suggesting governance or timeout behavior

### Clues That Point Toward Workflow

- Error appears as a business-rule message
- Approval, routing, email, field update, or transition behaves unexpectedly
- Issue depends on workflow state or condition
- Issue affects a specific record status or form
- Behavior changed after workflow state, transition, or action edits
- Workflow history shows a failed action or skipped transition

### Clues That Could Be Either

- Field value changes unexpectedly
- Save is blocked
- Button appears or disappears
- Approval status changes
- Email sends unexpectedly
- Record is created, transformed, or updated automatically

When symptoms overlap, check both workflow history and script execution logs.

## SuiteScript Triage Checklist

Review:

- Script type
- Script record and deployment record
- Deployment status
- Audience and role restrictions
- Execution context
- Script parameters
- Recent deployment or bundle changes
- Execution logs around the failure timestamp
- Related record ID and transaction type
- Whether the script is client-side, before submit, after submit, scheduled, Map/Reduce, Suitelet, RESTlet, or workflow action script

Common causes:

- Missing required field value
- Null or unexpected field value
- Role lacks permission to load or update a record
- Script assumes a record exists when it does not
- Search returns no results or too many results
- Governance usage is exhausted
- Script deployment is active in an unintended context
- Bundle or release changed field availability or behavior
- Hardcoded account-specific value was used

## Workflow Triage Checklist

Review:

- Workflow status
- Record type
- Initiation conditions
- Event definition
- Workflow state
- Transition conditions
- Action order
- Context restrictions
- Role restrictions
- Field updates
- Lock record or return user error actions
- Workflow history around the failure timestamp

Common causes:

- Condition is too broad or too narrow
- Transition does not fire because a required condition is false
- Action order creates unexpected data state
- Workflow blocks save with a custom message
- Workflow runs in UI but not CSV or API context
- Role restrictions exclude the affected user
- Field update conflicts with script validation

## Execution Context Matters

The same record can behave differently depending on how it is changed.

Compare:

| Context | What to Check |
|---|---|
| UI edit | Role, form, client script, workflow, user event script |
| CSV import | Import mapping, required fields, user event scripts, workflow context |
| REST/SOAP | Integration role, payload, record schema, user event scripts, permissions |
| RESTlet | RESTlet script logic, authentication, payload, downstream record actions |
| Suitelet | Suitelet UI logic, submitted parameters, record updates |
| Scheduled script | Deployment schedule, parameters, search inputs, governance usage |
| Map/Reduce | Input stage, map/reduce errors, summarized failures, governance |
| Workflow | State, transition, action order, role/context restrictions |

## Log Review Pattern

Use the timestamp of the failure to narrow logs.

Look for:

- Error message
- Script or workflow name
- Deployment ID
- Record type and internal ID
- Execution context
- User or role
- Stack-like details when available
- Governance or usage information
- Repeated failures versus one-time failure

Avoid collecting or publishing private logs that expose customer data, credentials, proprietary code, internal IDs tied to private processes, or company-specific implementation details.

## How to Compare Working and Failing Cases

Compare:

- Same record type, different role
- Same role, different record
- Same action in UI versus API
- Same transaction before and after status change
- Same script deployment before and after a recent change
- Same workflow with execution history for working and failing records

A clean comparison often reveals whether the issue is role, data, status, script, workflow, or context-specific.

## AI Assistant Reasoning Pattern

When a user asks about a script or workflow error, the assistant should:

1. Identify whether the symptom occurred in UI, CSV, API, scheduled, or connector context.
2. Ask for exact error text and timestamp.
3. Ask whether workflow history or script execution logs show a failure.
4. Ask what changed recently.
5. Suggest checking both automation layers if the symptom could be caused by either.
6. Avoid rewriting code or workflow logic without confirmed evidence.
7. Recommend sandbox testing for any configuration, workflow, or script change.

## Best Practices

- Use narrow deployments and clear descriptions.
- Keep workflow conditions explicit.
- Keep scripts focused and modular.
- Log enough context to troubleshoot without exposing private data.
- Avoid hardcoded internal IDs when a safer configuration option exists.
- Test UI, CSV, and API contexts separately when all are supported.
- Document dependencies between workflows and scripts.

## Common Mistakes

- Assuming the newest script caused the problem without checking logs.
- Forgetting that workflows can run only in certain contexts.
- Ignoring role restrictions on deployments.
- Changing workflow conditions without testing existing transactions.
- Treating governance errors as random failures.
- Publishing private script code, custom field IDs, or internal business rules in public documentation.

## Escalation Criteria

Escalate to a NetSuite developer or administrator when:

- A script throws an unhandled error.
- Workflow and script logic conflict.
- The issue affects financial posting, fulfillment, billing, or inventory movement.
- A bundle or release changed automation behavior.
- The fix requires code changes, deployment changes, credentials, or private account configuration.

## Related Articles

- [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md)
- [Screenshot and Error Message Triage](screenshot-and-error-message-triage.md)
- [Integration Error Triage](integration-error-triage.md)
- [SuiteScript Overview](../suitescript/overview.md)
- [Audit Trail](../administration/audit-trail.md)
- [System Notes](../administration/system-notes.md)

## Oracle References

- Oracle NetSuite Help Center: SuiteScript script types documentation
- Oracle NetSuite Help Center: SuiteScript governance and execution logging documentation
- Oracle NetSuite Help Center: SuiteFlow workflow documentation
- Oracle NetSuite Help Center: Script deployment documentation
