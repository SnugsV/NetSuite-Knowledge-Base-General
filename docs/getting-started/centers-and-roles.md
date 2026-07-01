---
title: Centers and Roles
module: Getting Started
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Centers and Roles

## Quick Summary

NetSuite uses roles and centers to control what each user can see and do. A role grants access to specific transactions, records, reports, and setup pages. A center groups those resources into a coherent workspace. Understanding roles and centers is essential for administrators and helpful for every user.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

NetSuite is not a one-size-fits-all application. A warehouse worker, an accountant, a sales representative, and an administrator all see different interfaces, menus, and records when they log in. This is controlled by two related concepts:

- **Roles** — Determine what a user can access (permissions)
- **Centers** — Organize the interface by business function

Together, they create an experience tailored to each user's responsibilities.

## What Is a Role?

A role is a collection of permissions that controls access to NetSuite features. Every user is assigned at least one role. When a user logs in, they choose which role to use (if they have multiple) or are assigned a default role.

A role specifies:

- Which **transactions** the user can create, view, edit, or delete
- Which **lists and records** the user can access
- Which **reports and saved searches** the user can view
- Which **setup pages** the user can modify
- Which **centers** the user can see

## Common Predefined Roles

NetSuite includes many predefined roles that cover common job functions. Examples:

| Role | Typical User |
|---|---|
| Administrator | Full system access, configuration, customization |
| Full Access | Broad access suitable for power users |
| Sales Manager | Sales orders, quotes, customer management, sales reports |
| Sales Representative | Enter sales orders, view own customers |
| Inventory Clerk | Inventory transfers, adjustments, item lookups |
| Warehouse Worker | Fulfill orders, receive inventory |
| Accountant | Financial reports, period close, reconciliations |
| Purchasing Manager | Purchase orders, vendor management |
| CEO | Dashboard, KPIs, high-level reports, limited transaction entry |
| Human Resources | Employee records, time tracking |

Each role can be customized — an administrator can duplicate a standard role, adjust permissions, and assign it to specific users.

## What Is a Center?

A center is a navigational framework that organizes menus, dashboards, and pages around a business function. When you switch to a center, the dashboard, menu options, and available portlets change.

Common centers:

| Center | What It Contains |
|---|---|
| Home | Personal dashboard, reminders, KPIs, recent records |
| Sales | Sales orders, quotes, customers, sales reporting |
| Inventory | Items, locations, transfers, adjustments |
| Purchasing | Purchase orders, vendors, receiving |
| CRM | Leads, prospects, customers, campaigns |
| Reports | Saved searches, financial reports, SuiteAnalytics |
| Setup | Company configuration, users, customization (admin only) |

Not every role has access to every center. An Inventory Clerk role might only have access to Home and Inventory centers.

## How Roles and Centers Work Together

The relationship between roles and centers works like this:

1. An **administrator creates or customizes a role** and selects which centers the role can access
2. The **administrator assigns the role** to users
3. When a **user logs in**, they see only the centers their role allows
4. Within each center, the user sees only the **menu options, records, and transactions** their permissions allow

This means two users in the same center may see different menu items based on their permissions within that center.

## Example Scenario

A company uses NetSuite for sales and inventory. Three users have different experiences:

**Alex (Sales Rep)** — Role: Sales Representative
- Centers: Home, Sales
- Menu: Can create sales orders and quotes, view customers
- Cannot see: Inventory adjustments, purchase orders, setup pages

**Jordan (Warehouse Manager)** — Role: Inventory Clerk
- Centers: Home, Inventory
- Menu: Can view items, create transfers, fulfill orders
- Cannot see: Sales orders, customer records, financial reports

**Sam (Administrator)** — Role: Administrator
- Centers: All centers available
- Menu: Full access to all transactions, lists, reports, and setup pages
- Can do anything in the system

## Prerequisites for Using Roles

- Role assignment is managed by an administrator
- Users can have multiple roles and switch between them
- Some pages and records also enforce permission checks beyond role access (e.g., employee records may be restricted to HR roles)

## Common Mistakes

- **Assuming every user sees the same interface**: Never assume. Always test new features or reports with the intended role.
- **Giving users more permissions than needed**: Start with minimal access and expand only when necessary.
- **Not understanding that role changes take effect on next login**: Changes to role permissions do not apply to active sessions until the user logs out and back in.
- **Assigning the Full Access role as a default**: Full Access is broad and should be reserved for specific needs.

## Best Practices

- Use predefined roles as starting points, then customize for your organization.
- Test new roles in a sandbox account before deploying.
- Review role assignments periodically, especially after employee role changes.
- Document customized roles and the reasons for each permission change.
- Use the Audit Trail to track changes to roles and permissions.

## Related Articles

- [What Is NetSuite?](what-is-netsuite.md)
- [User Interface Overview](user-interface.md)
- [Personalization](personalization.md)
- [Glossary](glossary.md)

## Oracle References

- [Oracle NetSuite Help Center: Roles](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)