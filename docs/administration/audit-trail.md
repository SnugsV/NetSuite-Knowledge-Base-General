---
title: Audit Trail
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Audit Trail

## Quick Summary

The Audit Trail is a record of significant events in a NetSuite account — user logins, permission changes, configuration updates, and other administrative actions. Unlike System Notes (which track field-level changes on individual records), the Audit Trail provides an account-wide view of who did what and when.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

The Audit Trail is the primary tool for security monitoring and compliance in NetSuite. It captures events that matter from an administrative and security perspective:

- User management events (new users, role changes, deactivations)
- Permission and role changes
- Configuration changes (features, preferences, forms)
- Login activity (successful and failed logins)
- System configuration modifications

```
Setup > Users > Audit Trail
```

## What the Audit Trail Captures

| Event Category | Examples |
|---|---|
| **User Events** | User created, user deactivated, role assigned, role removed, password reset |
| **Role Events** | Role created, role modified, permission changed, center access changed |
| **Configuration Events** | Feature enabled/disabled, company information changed, preference updated |
| **Login Events** | Successful login, failed login, account locked, password changed |
| **Customization Events** | Custom field created, form modified, custom record created |
| **Integration Events** | API access, token creation, token revocation |

## Viewing the Audit Trail

To access the Audit Trail:

```
Setup > Users > Audit Trail
```

The Audit Trail page displays a filterable table with:

| Column | Description |
|---|---|
| Date | When the event occurred |
| User | Who performed the action |
| Event | What action was taken |
| Record Type | The type of record affected (if applicable) |
| Record Name | The specific record affected (if applicable) |
| IP Address | The IP address from which the action was performed |

## Filtering the Audit Trail

The Audit Trail can be filtered by:

- **Date range** — Show events from a specific period
- **User** — Show events by a specific user
- **Event type** — Show only specific types of events
- **Record type** — Show events affecting a specific record type
- **IP address** — Show events from a specific IP address

Filters are essential because a busy account generates thousands of Audit Trail entries per day.

## Audit Trail vs. System Notes

Understanding the difference is important for using both tools effectively:

| Dimension | Audit Trail | System Notes |
|---|---|---|
| **Scope** | Account-wide events | Individual record changes |
| **Granularity** | Event-level (e.g., "Role modified") | Field-level (e.g., "Credit limit changed from 5000 to 10000") |
| **Access** | Administrators only | Users with record View permission |
| **Retention** | Configurable (default depends on account) | Permanent until cleared |
| **Can be cleared** | No | Yes, by administrator |

Use the **Audit Trail** for: security monitoring, compliance audits, investigating who changed a role or permission.
Use **System Notes** for: investigating what changed on a specific record, troubleshooting data issues.

## Audit Trail and Compliance

The Audit Trail is critical for compliance with:

- **SOC audits** — Provides evidence of access controls and change management
- **Financial audits** — Tracks changes to configuration that affect financial reporting
- **Internal investigations** — Traces who accessed specific features or made configuration changes
- **Data privacy regulations** — Demonstrates access controls and monitoring

For compliance purposes, the Audit Trail should be reviewed:

- **Weekly** for high-security environments
- **Monthly** for standard environments
- **After security incidents** to determine scope

## Audit Trail Retention

Audit Trail data is retained based on account configuration. In production accounts, retention is typically 90-365 days depending on the account's edition and configuration. In sandbox accounts, retention may be shorter.

If longer retention is needed, consider:

- Exporting Audit Trail data periodically to an external system
- Using SuiteScript to capture specific events to a custom record
- Using an external SIEM (Security Information and Event Management) system

## Common Mistakes

- **Relying on the Audit Trail for record-level changes**: For specific field changes on a specific record, use System Notes instead.
- **Not reviewing the Audit Trail regularly**: The Audit Trail is most valuable when reviewed proactively, not just reactively after an incident.
- **Not filtering the Audit Trail**: Without filters, the Audit Trail contains too many entries to be useful.
- **Assuming the Audit Trail captures everything**: It captures administrative and security events, not every transaction or record view.

## Best Practices

- Review the Audit Trail on a regular schedule (weekly or monthly).
- Configure alerts for high-risk events (role changes, permission modifications, feature enablement).
- Export the Audit Trail to an external system if longer retention is needed.
- Use filters to focus on the most significant events for your organization.
- Combine the Audit Trail with System Notes for complete visibility into changes.
- Train administrators to understand what the Audit Trail captures and how to use it.

## Related Articles

- [System Notes](system-notes.md)
- [Security Best Practices](security-best-practices.md)
- [Administration Overview](administration-overview.md)
- [Authentication](authentication.md)

## Oracle References

- [Oracle NetSuite Help Center: Audit Trail](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)