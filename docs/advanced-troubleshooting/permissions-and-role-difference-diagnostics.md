---
title: Permissions and Role Difference Diagnostics
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Permissions and Role Difference Diagnostics

## Quick Summary

When NetSuite behaves differently for two users, diagnose the role context before changing records, forms, searches, scripts, or workflows. Most role-difference issues come from record permissions, subsidiary restrictions, audience settings, form access, field visibility, execution context, or data restrictions.

## Difficulty

Advanced

## Estimated Time

30 minutes

## Prerequisites

You should understand:

- Users and roles
- Record permissions
- Centers and forms
- Saved search audiences
- Subsidiaries, departments, classes, locations, and custom segments
- Workflow execution context
- SuiteScript deployment and execution context
- System notes and audit concepts

## Overview

A frequent advanced troubleshooting pattern is that one user can see, edit, approve, fulfill, bill, export, search, or integrate something while another user cannot. The tempting answer is to give the affected user broader permissions. A better answer is to identify the exact layer that differs.

Role-difference issues can affect:

- Page access
- Record visibility
- Field visibility
- Button availability
- Transaction approval or posting
- Saved search results
- Dashboard portlets
- Workflow behavior
- SuiteScript behavior
- Integration behavior
- CSV import or export

## Public-Safe Boundary

Keep examples generic. Do not publish real role names, employee names, customer names, custom permission models, screenshots, scripts, workflows, saved searches, approval rules, subsidiaries, or internal security policy.

## First Questions to Ask

When a role issue is suspected, ask:

1. Which user can complete the action and which user cannot?
2. Which exact role is each user using?
3. What record, page, transaction, search, workflow, script, integration, or dashboard is affected?
4. Is the difference access, visibility, editability, approval, export, button availability, or result content?
5. Does the issue happen only in one subsidiary, location, department, class, or custom segment?
6. Does the issue happen on all forms or only one custom form?
7. Does the issue happen in the UI, CSV import, SuiteScript, SuiteTalk, RESTlet, or connector context?
8. Did anything change recently: role, employee restriction, form, workflow, script, bundle, release, subsidiary, or saved search audience?

## Diagnostic Layers

### Layer 1: Role Selection

Symptoms:

- User reports inconsistent access
- Same person can do something in one session but not another
- Administrator can reproduce only by switching roles

Checks:

- Confirm the user is in the expected role.
- Confirm whether the role is custom or standard.
- Compare the affected role to a known working role.
- Avoid assuming administrator behavior represents normal role behavior.

### Layer 2: Record Permission

Symptoms:

- User cannot view, create, edit, delete, approve, or export a record
- Button or menu option is missing
- Permission error appears when opening or saving a record

Checks:

- Confirm permission level for the base record type.
- Check whether the action requires view, create, edit, full, approval, or special permission.
- Review related records needed by the process.
- For transactions, check whether posting, approval, fulfillment, billing, or payment actions require additional permissions.

### Layer 3: Data Restrictions

Symptoms:

- User can access the record type but not specific records
- Search results differ between users
- Dashboard counts differ by role
- Integration role sees fewer records than expected

Checks:

- Review subsidiary restrictions.
- Review location, department, class, employee, partner, or customer restrictions.
- Review custom segment restrictions.
- Check whether inactive records are hidden.
- Confirm whether the role is limited to own, team, subsidiary, or assigned records.

### Layer 4: Form and Field Visibility

Symptoms:

- User can open a record but cannot see or edit a field
- Field is visible to one role but hidden for another
- Button availability differs by form
- Workflow condition appears wrong because a field is hidden or not populated

Checks:

- Confirm the custom form assigned to the role.
- Review field display type and form-level visibility.
- Check role-specific form preferences.
- Compare whether the same record opened on another form shows the field or button.
- Confirm whether a workflow, script, or sourcing rule is changing field behavior.

### Layer 5: Saved Search Audience and Field Access

Symptoms:

- User cannot find or run a saved search
- Search returns different rows or blank fields
- Dashboard portlet differs from search preview
- Export results differ by role

Checks:

- Confirm saved search audience.
- Confirm whether the user can access the base record type.
- Confirm whether joined records are visible to the role.
- Review restrictions by subsidiary, location, department, class, employee, and custom segment.
- Compare administrator results against a role-based test carefully.

### Layer 6: Workflow Context

Symptoms:

- Workflow triggers for one user but not another
- Approval button, task, email, field update, or transition differs by role
- Workflow appears to skip an expected state

Checks:

- Review workflow initiation and trigger context.
- Review role-based conditions.
- Review transition conditions.
- Review whether the workflow runs as the current user or another context.
- Check workflow history if available.
- Confirm whether hidden fields or form differences affect conditions.

### Layer 7: SuiteScript Context

Symptoms:

- Script error appears for one role but not another
- Button or client script behavior differs by role
- Scheduled or map/reduce script processes different data than expected
- RESTlet, SuiteTalk, or connector role behaves differently from UI roles

Checks:

- Review script deployment audience and status.
- Confirm execution role and execution context.
- Check whether the script assumes administrator-level access.
- Review script logs for permission or missing-field errors.
- Confirm whether the integration role has all required record and field access.
- Check whether the script uses saved searches with role-sensitive results.

## Common Permission Symptoms

### Permission Violation on Save

Likely causes:

- Missing edit or approval permission
- Missing permission for a related record
- Workflow or script attempting an action the role cannot perform
- Record is locked by status, period, approval state, or accounting control

### Missing Button

Likely causes:

- Role lacks action permission
- Record status does not allow action
- Custom form hides the button
- Workflow or script controls the button
- Feature or preference is disabled for the context

### Search Results Differ by User

Likely causes:

- Saved search audience
- Base record permission
- Joined record permission
- Subsidiary, location, department, class, employee, or custom segment restriction
- Inactive records or private search settings

### Integration Role Cannot Create or Update Records

Likely causes:

- Missing create/edit permission
- Missing permission for related records
- Missing list, custom record, file, or transaction permission
- Mandatory field not available to the integration role
- Script, workflow, or form behavior depends on UI-only assumptions

## Safe Diagnostic Path

1. Identify the exact action that fails.
2. Identify the exact role in use.
3. Compare against a known working role.
4. Check base record permissions first.
5. Check data restrictions next.
6. Check form and field visibility.
7. Check saved search audience and joined record visibility.
8. Check workflow and script execution context.
9. Test the smallest permission change in sandbox or a controlled environment.
10. Document the minimum permission required and why.

## Best Practices

- Use least privilege rather than broad administrator-like access.
- Compare roles deliberately; do not rely on memory.
- Test using the affected role, not only an administrator role.
- Watch for hidden related-record permissions.
- Treat integration roles as separate security designs.
- Document why each permission is needed.
- Revisit permissions after major releases, bundle updates, process changes, and new integrations.

## Common Mistakes

- Giving broad permissions without finding the actual missing layer.
- Assuming a missing field is a permission issue when it is a form issue.
- Assuming a saved search issue is a formula issue when it is a role restriction.
- Testing only as administrator.
- Forgetting subsidiary, location, department, class, employee, or custom segment restrictions.
- Ignoring workflow and script deployment audiences.
- Publishing internal role designs or screenshots in public documentation.

## AI Assistant Response Pattern

When a user reports that NetSuite works for one user but not another, the assistant should:

1. Ask which exact action differs.
2. Ask which roles are being compared.
3. Ask whether the difference is access, visibility, editability, approval, export, button availability, or result content.
4. Diagnose in layers: role selection, record permission, data restriction, form/field visibility, search audience, workflow context, script context.
5. Recommend the smallest controlled test before increasing access.
6. Flag integration roles as a separate path when the issue comes from SuiteTalk, RESTlet, connector, or CSV import context.
7. Keep examples generic and avoid publishing internal role design.

## Related Articles

- [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md)
- [Screenshot and Error Message Triage](screenshot-and-error-message-triage.md)
- [Advanced Saved Search Diagnostics](advanced-saved-search-diagnostics.md)
- [SuiteScript and Workflow Error Triage](suitescript-and-workflow-error-triage.md)
- [Roles and Permissions](../administration/roles-and-permissions.md)

## Oracle References

- Oracle NetSuite Help Center: Managing Users and Roles
- Oracle NetSuite Help Center: Authentication Guide
- Oracle NetSuite Help Center: System Notes Guide
- Oracle NetSuite Help Center: SuiteFlow User Guide
- Oracle NetSuite Help Center: SuiteScript Developer Guide
