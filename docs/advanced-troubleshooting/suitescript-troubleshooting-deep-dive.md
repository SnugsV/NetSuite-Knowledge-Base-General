---
title: SuiteScript Troubleshooting Deep Dive
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 35 minutes
status: Draft
last_reviewed:
---

# SuiteScript Troubleshooting Deep Dive

## Quick Summary

SuiteScript troubleshooting starts with script type, deployment, execution context, logs, permissions, governance, record state, and interaction with workflows or integrations. Do not debug code in isolation from NetSuite context.

## Difficulty

Advanced

## Estimated Time

35 minutes

## Prerequisites

You should understand:

- SuiteScript at a conceptual level
- NetSuite records and transactions
- Script deployments
- Roles and permissions
- Saved searches
- Workflows and forms
- Integration context

## Overview

SuiteScript can solve problems that workflows, saved searches, and standard configuration cannot. It can also create complex failures when scripts assume the wrong execution context, run in the wrong order, exceed governance limits, lack permissions, or conflict with workflows and other scripts.

Common script types include:

- Client script
- User Event script
- Scheduled script
- Map/Reduce script
- Suitelet
- RESTlet
- Portlet
- Workflow Action script
- Mass Update script

## Public-Safe Boundary

Do not publish proprietary script code, account IDs, deployment IDs tied to private processes, internal custom field IDs, stack traces with sensitive data, production logs, customer examples, financial values, screenshots, or private operating procedures.

## First Questions to Ask

1. What script type is involved?
2. What record type and action trigger the issue?
3. What is the execution context: UI, CSV, web services, RESTlet, scheduled, workflow, Map/Reduce, or user event?
4. Does the issue happen for all roles or only some roles?
5. Is the issue an error, missing behavior, wrong field value, timeout, governance limit, duplicate action, or permission issue?
6. Did a workflow, form, field, role, bundle, release, or integration change recently?
7. Are there logs, script execution records, or deployment details available without sensitive values?

## Script Type Fit

### Client Script

Best for browser-side guidance and validation.

Watch for:

- UI-only behavior
- Role and form differences
- Browser timing
- Fields not present on the form
- Logic that should actually run server-side

### User Event Script

Best for record save, submit, and lifecycle validation.

Watch for:

- Before Load vs Before Submit vs After Submit confusion
- Recursive updates
- Context differences between UI, CSV, web services, and scripts
- Record status and permissions
- Interactions with workflows

### Scheduled Script

Best for batch processing on a schedule.

Watch for:

- Governance usage
- Search result size
- Retry and idempotency
- Partial failures
- Record locking or period restrictions

### Map/Reduce Script

Best for large data processing.

Watch for:

- Input search quality
- Key grouping
- Governance in map and reduce stages
- Error summarization
- Restart and retry behavior

### RESTlet or Suitelet

Best for custom integration or controlled UI/service behavior.

Watch for:

- Authentication and role permissions
- Payload validation
- Error response design
- External ID mapping
- Scripts assuming administrator access

## Diagnostic Layers

### Layer 1: Deployment

Check:

- Script deployment status
- Record type
- Audience and role restrictions
- Execution context filters
- Log level
- Whether the deployment is active in the correct account or environment

### Layer 2: Execution Context

Check:

- UI vs CSV vs web services vs scheduled vs workflow context
- Whether logic is intentionally limited by context
- Whether field values differ by context
- Whether workflows or scripts run before or after the script

### Layer 3: Permissions

Check:

- Current user or execution role
- Base record permissions
- Related record permissions
- Custom record and custom segment access
- File cabinet, search, and SuiteScript permissions
- Integration role behavior

### Layer 4: Record State

Check:

- Transaction status
- Approval state
- Posting period
- Existing related records
- Locked or closed records
- Mandatory fields and custom form behavior

### Layer 5: Governance and Performance

Check:

- Usage units
- Search result volume
- Loops and repeated record loads
- External calls
- Large sublists
- Map/Reduce restart behavior
- Timeout or yielding behavior

### Layer 6: Error Handling and Logging

Check:

- Whether errors are logged with enough context
- Whether sensitive data is excluded from logs
- Whether failures stop processing or continue safely
- Whether retries can duplicate work
- Whether users receive actionable messages

## Common Symptoms

### Script Works for Administrator Only

Likely causes:

- Role permissions
- Deployment audience
- Search visibility
- Form or field visibility
- Script assumes unrestricted access

### Script Works in UI but Fails in Integration

Likely causes:

- Execution context difference
- Missing integration role permissions
- Required field not supplied by payload
- Workflow or User Event behavior differs by context
- Script references UI-only fields or client behavior

### Governance Limit Exceeded

Likely causes:

- Too many record loads or saves
- Inefficient search usage
- Processing too many records in one execution
- External calls inside large loops
- Wrong script type for batch work

### Duplicate Records or Duplicate Actions

Likely causes:

- Retry without idempotency
- After Submit recursion
- Multiple deployments
- Workflow and script both performing the same action
- External system resubmitting without stable keys

## When Not to Script

Avoid SuiteScript when:

- A saved search and dashboard would solve awareness.
- A workflow can handle simple routing or field updates.
- The business rule is not defined.
- Accounting policy is unresolved.
- The only reason is to bypass permissions or controls.
- The process has not been tested manually.

## Safe Diagnostic Path

1. Identify script type, deployment, record type, and trigger.
2. Capture sanitized error and log context.
3. Confirm execution context.
4. Check role and deployment audience.
5. Check record state and related records.
6. Review workflows and other scripts on the same record.
7. Check governance and performance.
8. Test with the affected role and context.
9. Add or improve safe logging if needed.
10. Document the final root cause and prevention rule.

## AI Assistant Response Pattern

When a user asks about a SuiteScript issue, the assistant should:

1. Ask for script type, record type, deployment context, and sanitized error.
2. Separate deployment, context, permissions, record state, governance, and automation overlap.
3. Ask whether the issue differs by role or entry method.
4. Recommend checking logs and execution context before changing code.
5. Flag retries, duplicate processing, and financial record updates as high care.
6. Avoid requesting or exposing proprietary code unless the user explicitly provides a safe snippet.

## Related Articles

- [SuiteScript and Workflow Error Triage](suitescript-and-workflow-error-triage.md)
- [SuiteFlow Automation Patterns](suiteflow-automation-patterns.md)
- [SuiteTalk REST and SOAP Troubleshooting](suitetalk-rest-soap-troubleshooting.md)
- [Permissions and Role Difference Diagnostics](permissions-and-role-difference-diagnostics.md)
- [Transaction Lifecycle Troubleshooting](transaction-lifecycle-troubleshooting.md)

## Oracle References

- Oracle NetSuite Help Center: SuiteScript Developer Guide
- Oracle NetSuite Help Center: SuiteScript 2.x Guide
- Oracle NetSuite Help Center: SuiteScript 2.x API Reference
- Oracle NetSuite Help Center: SuiteScript Records Guide
- Oracle NetSuite Help Center: SuiteCloud Development Framework Guide
