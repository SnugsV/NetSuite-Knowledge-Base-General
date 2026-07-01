---
title: Administration Overview
module: Administration
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed:
---

# Administration Overview

## Quick Summary

NetSuite administration is the practice of configuring, securing, and maintaining a NetSuite account. Administrators manage users, roles, permissions, features, forms, authentication, and account-level settings. This article explains what administration means in NetSuite and who performs it.

## Difficulty

Beginner

## Estimated Time

5 minutes

## Overview

Administration in NetSuite is not a single task — it is a category of responsibilities that control how the system works for everyone else. Unlike operational tasks (creating a sales order, transferring inventory), administration tasks shape the environment in which those operational tasks happen.

If NetSuite is a building, administration is the electrical wiring, plumbing, and structural framework. Most people never see it, but everyone depends on it working correctly.

## What Administration Covers

NetSuite administration includes:

- **User management** — Creating, activating, and deactivating user accounts
- **Role management** — Defining what each user can access and do
- **Permissions** — Setting granular access levels for features and records
- **Feature enablement** — Turning NetSuite features on and off
- **Form customization** — Configuring how records and transactions appear
- **Authentication** — Setting login methods, password policies, and security controls
- **Company preferences** — Configuring account-wide settings
- **Audit and compliance** — Monitoring changes and maintaining records
- **Testing** — Managing sandbox environments and release previews

## Who Administers NetSuite?

In a small company, one person might handle all administration alongside their regular job. In a larger organization, administration is typically split:

| Administrator Type | Responsibilities |
|---|---|
| **Full Administrator** | All administration tasks. Usually 1-2 people in the organization. |
| **Departmental Administrators** | Role management and permissions for their department only. |
| **Security Administrator** | Authentication, password policies, SSO, compliance monitoring. |
| **System Administrator** | Feature enablement, integrations, SuiteCloud configuration. |

## The Administrator Role

NetSuite comes with a predefined **Administrator** role that has unrestricted access to everything in the account. This role cannot be deleted and is always available.

Key characteristics of the Administrator role:

- Can see and edit every record and transaction in the account
- Can access every setup page
- Can create, modify, and delete roles
- Can enable and disable features
- Can customize forms and fields
- Can view and clear the audit trail
- Cannot be modified or restricted

Because the Administrator role is so powerful, it should be used sparingly. Best practice is to create customized roles with limited permissions for daily tasks and reserve the Administrator role for tasks that genuinely require it.

## The Setup Center

Most administration tasks are performed from the **Setup** center, accessible from the menu bar:

```
Setup > [category] > [specific page]
```

Common administration pages include:

| Page | Menu Path |
|---|---|
| Enable Features | Setup > Company > Enable Features |
| Company Information | Setup > Company > Company Information |
| User Management | Setup > Users > Manage Users |
| Role Management | Setup > Users > Manage Roles |
| Audit Trail | Setup > Users > Audit Trail |
| Form Customization | Setup > Customization > Forms |

## Self-Service vs. Managed Administration

NetSuite allows some self-service administration for non-administrators:

- **Personal dashboard customization** — Any user can customize their own dashboard
- **Personal saved searches** — Any user can create personal saved searches
- **User preferences** — Any user can set their own language, time zone, and notification preferences

These do not require administrator access. See [Personalization](../getting-started/personalization.md) for details.

## Common Mistakes

- **Using the Administrator role for daily work**: Log in with the Administrator role only when you need to perform tasks that require it. Use a role with limited permissions for regular work.
- **Assuming administration is only about permissions**: Feature enablement, form customization, and company preferences are equally important and often overlooked.
- **Making changes without understanding downstream effects**: Enabling a feature can change what users see in their interface. Changing a form can affect how transactions are entered.
- **Not documenting administration decisions**: Configuration decisions should be documented so future administrators understand why something was set up a particular way.

## Best Practices

- Maintain a small list of full administrators (1-3 people maximum).
- Document every configuration change and the reason for it.
- Test changes in a sandbox account before applying them to production.
- Review role assignments and permissions quarterly.
- Use the Administrator role only for tasks that require it.

## Related Articles

- [Company Setup](company-setup.md)
- [Users](users.md)
- [Roles](roles.md)
- [Permissions](permissions.md)
- [Centers and Roles](../getting-started/centers-and-roles.md)

## Oracle References

- [Oracle NetSuite Help Center: Administration](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)