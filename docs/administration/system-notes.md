---
title: System Notes
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# System Notes

## Quick Summary

System Notes track every change made to a record in NetSuite — who changed what, when, and what the old and new values were. They provide a detailed change history for individual records and are the primary tool for investigating data changes.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Every time a record is created, edited, or deleted in NetSuite, the system creates a System Note. This note records:

- The user who made the change
- The date and time of the change
- The field or field that was changed
- The old value and the new value

System Notes are available on every record type and cannot be deleted by standard users. Only administrators can clear System Notes.

## Viewing System Notes

System Notes are displayed on a subtab of each record. To view them:

1. Open the record
2. Click the **System Notes** subtab

The subtab shows a chronological list of every change made to that record. Each entry includes the date, user, field changed, old value, and new value.

## What System Notes Track

System Notes capture changes to:

- **Standard fields** — Name, date, amount, status, etc.
- **Custom fields** — Any field added by an administrator
- **Sublist entries** — Line items on transactions
- **Addresses** — Shipping and billing addresses
- **Relationships** — Links to other records (e.g., a customer linked to a sales order)

Changes that are NOT captured:

- Page views or record opens (for that, use the Audit Trail)
- Report runs
- Saved search executions
- External system access (for that, use the API log)

## Using System Notes for Troubleshooting

System Notes are invaluable for investigating questions like:

- "Who changed this customer's credit limit?"
- "When was this sales order last modified?"
- "What was the original quantity on this purchase order?"
- "Why did this invoice amount change?"

For each question, the System Notes subtab provides the exact field change, the user who made it, and the timestamp.

## System Notes and Compliance

For compliance purposes, System Notes provide:

- **Auditability** — Every change is attributable to a specific user
- **Historical accuracy** — Old values are preserved in the notes even after fields are updated multiple times
- **Non-repudiation** — Users cannot deny making a change that appears in the notes

Some organizations rely on System Notes for SOC audits, financial audits, and internal investigations.

## System Notes vs. Audit Trail

| Feature | System Notes | Audit Trail |
|---|---|---|
| Scope | Individual record | Entire account |
| What it tracks | Field-level changes on a specific record | All significant account events |
| Who can view | Users with View permission on the record | Administrators only |
| Retention | Permanent (until cleared) | Configurable retention period |
| Purpose | Troubleshooting, change history | Security monitoring, compliance |
| Can be cleared | By administrator only | Cannot be cleared |

Both tools are useful. System Notes are for investigating a specific record. The Audit Trail (covered in [Audit Trail](audit-trail.md)) is for monitoring account-wide activity.

## Clearing System Notes

System Notes accumulate over time and can affect database performance on heavily modified records. An administrator can clear System Notes from a record:

```
Record > Actions > Clear System Notes
```

Clearing System Notes:

- Removes all System Notes for that record
- Cannot be undone
- Does not affect the Audit Trail
- Should only be done when the notes are no longer needed for reference

## Common Mistakes

- **Clearing System Notes prematurely**: Notes provide valuable history. Only clear them when they are no longer needed.
- **Confusing System Notes with the Audit Trail**: System Notes are per-record; the Audit Trail is account-wide. They serve different purposes.
- **Assuming System Notes capture everything**: Page views, report runs, and API calls are not captured in System Notes.
- **Not using System Notes in investigations**: The subtab is often overlooked. When investigating a data issue, check System Notes first.

## Best Practices

- Use System Notes as the first tool when investigating record-level changes.
- Keep System Notes accessible to users who need them for their work (auditors, compliance teams).
- Only clear System Notes on records with excessive change history.
- Educate users that System Notes are permanent and cannot be edited.
- Use the Audit Trail for account-wide monitoring and periodic reviews.

## Related Articles

- [Audit Trail](audit-trail.md)
- [Administration Overview](administration-overview.md)
- [Security Best Practices](security-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: System Notes](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)