---
title: Roles
module: Administration
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Roles

## Quick Summary

A role is a collection of permissions that defines what a user can see and do in NetSuite. Roles control access to transactions, records, reports, setup pages, and centers. Every user must have at least one role, and roles are the primary mechanism for controlling access in NetSuite.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Roles are the most important access control mechanism in NetSuite. Instead of assigning permissions to individual users, you define roles — each role represents a job function with specific permissions — and then assign users to roles.

## Role Structure

A role is defined by:

1. **Name and description** — Identifies the role and its purpose
2. **Centers** — Which centers the role can access (Home, Sales, Inventory, etc.)
3. **Permissions** — What the role can do in each area
4. **Restrictions** — Limits on what the role can see or edit

NetSuite includes many predefined roles that cover common job functions. These can be used as-is, copied and customized, or used as starting points for new roles.

## Predefined Roles

| Role | Typical Assignee |
|---|---|
| **Administrator** | Full system access — reserved for 1-3 people |
| **Full Access** | Broad access — used for power users or development accounts |
| **Sales Manager** | Sales reporting, order editing, customer management |
| **Sales Representative** | Enter sales orders, view own customers |
| **Inventory Clerk** | Inventory transfers, adjustments, item lookups |
| **Warehouse Worker** | Fulfill orders, receive inventory |
| **Accountant** | Financial reports, period close, reconciliations |
| **Purchasing Manager** | Purchase orders, vendor management |
| **CEO** | Dashboard, KPIs, high-level reports, limited transaction entry |
| **Human Resources** | Employee records, time tracking |
| **Support Representative** | Customer support cases, communication history |

## Creating a Custom Role

To create a new role:

1. Navigate to **Setup > Users > Manage Roles**
2. Click **New Role**
3. Enter a name and description
4. Select which centers the role can access
5. Set permissions for each area
6. Configure any restrictions
7. Save the role

When creating a custom role, it is best practice to start by copying an existing role that is close to what you need, rather than starting from scratch. This reduces the risk of accidentally granting too many permissions.

## Centers in Roles

Centers control which parts of the NetSuite interface a role can see. When you create or edit a role, you select which centers are available:

| Center | What It Contains |
|---|---|
| Home | Personal dashboard, reminders, KPIs |
| Sales | Sales orders, quotes, customers |
| Inventory | Items, locations, transfers |
| Purchasing | Purchase orders, vendors |
| CRM | Leads, prospects, campaigns |
| Reports | Saved searches, financial reports |
| Setup | Administration pages (admin only) |

A role that cannot access the Sales center will not see any Sales-related menus, records, or dashboards. This is how you restrict users to specific areas of the system.

## Role Restrictions

Roles can have additional restrictions:

- **Transaction approval limits** — Maximum dollar amount a user can approve
- **Order limits** — Maximum order value a user can create
- **Customer type** — Restrict to specific customer categories
- **Item type** — Restrict to specific item categories
- **Location access** — Restrict to specific inventory locations
- **Department access** — Restrict to specific departments

These restrictions are applied on top of the role's permissions. Even if a role has "Edit" permission on sales orders, a dollar limit restriction can prevent the user from editing orders above a certain value.

## Role Assignment

Users can have multiple roles. When assigning roles:

1. Go to the user record
2. Click **Roles** subtab
3. Click **Add Role**
4. Select the role and set a default role

The default role is the one the user starts in when they log in. They can switch roles during their session using the role selector.

## Role Auditing

NetSuite tracks role-related changes in the audit trail. Administrators can review:

- When roles were created or modified
- Which permissions were changed
- Who made the change
- When users were assigned to roles

See [Audit Trail](audit-trail.md) for details on reviewing role changes.

## Common Mistakes

- **Modifying a predefined role instead of copying it**: Predefined roles cannot be restored to their original state if you modify them. Always copy a role before customizing.
- **Creating too many similar roles**: If two roles differ by only one permission, consider whether a restriction would suffice instead of creating a separate role.
- **Not testing role changes in a sandbox**: A permission change that seems safe can have unexpected effects. Always test role modifications in a sandbox first.
- **Assigning the Full Access role as a default**: Full Access provides broad permissions that most users do not need. Use it sparingly.

## Best Practices

- Start with predefined roles and customize as needed.
- Copy a role before modifying it — never change a predefined role directly.
- Name roles clearly using a consistent convention (e.g., "Sales — Read Only," "Sales — Manager").
- Test role changes in a sandbox before deploying to production.
- Review role assignments quarterly.
- Document each custom role, including the business reason for its creation.
- Use role restrictions instead of creating separate roles when the difference is a limit or scope.

## Related Articles

- [Users](users.md)
- [Permissions](permissions.md)
- [Centers](centers.md)
- [Centers and Roles](../getting-started/centers-and-roles.md)
- [Audit Trail](audit-trail.md)

## Oracle References

- [Oracle NetSuite Help Center: Roles](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Creating Custom Roles](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)