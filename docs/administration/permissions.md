---
title: Permissions
module: Administration
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Permissions

## Quick Summary

Permissions are the individual access rights that make up a role. Each permission controls access to a specific feature, record type, transaction, or setup page. Permissions are grouped into categories and assigned to roles, not directly to users.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

A role without permissions is an empty container. Permissions fill that container, defining exactly what the role can do. Understanding the permission model is essential for creating effective roles and maintaining secure access.

## Permission Categories

Permissions are organized into categories in the role editor:

| Category | Examples |
|---|---|
| **Transactions** | Sales Order, Purchase Order, Inventory Adjustment |
| **Reports** | Financial Reports, Saved Searches, SuiteAnalytics |
| **Lists** | Customers, Vendors, Items, Employees |
| **Setup** | Company Setup, User Management, Feature Enablement |
| **Customization** | Forms, Fields, Records, Scripts |
| **CRM** | Campaigns, Cases, Lead Management |

Each category contains multiple individual permissions.

## Permission Levels

Most permissions have four levels:

| Level | Meaning | Use Case |
|---|---|---|
| **None** | No access. The feature is not visible. | Used to restrict access entirely |
| **View** | Can see records but cannot create, edit, or delete | Read-only users, auditors, executives |
| **Create** | Can create new records and view existing ones | Data entry roles |
| **Edit** | Can create, edit, and delete records | Full access to a feature area |

Some permissions have additional levels specific to that feature. For example, transaction permissions may include **Approve** as a separate level.

## How Permissions Work Together

Permissions do not exist in isolation. The effective access a user has depends on the combination of all permissions in their role.

Example:

- A role with **Sales Order — Edit** permission has full access to sales orders
- But if the role also has **Customer — View** permission, the user can only select existing customers; they cannot create new ones
- The combination of permissions determines what the user can actually do with each transaction

## Center Permissions

Center permissions control whether a role can see each center in the interface:

| Permission | Effect |
|---|---|
| **Sales Center — View** | Role can access the Sales center |
| **Inventory Center — View** | Role can access the Inventory center |
| **Setup Center — View** | Role can access the Setup center |
| **Reports Center — View** | Role can access the Reports center |

Without the appropriate center permission, a role cannot see that center's menu items or dashboard, even if they have individual transaction permissions for items in that center.

## Transaction Type Permissions

These control access to specific transaction types:

| Permission | Controls |
|---|---|
| **Sales Order** | Creating, viewing, editing sales orders |
| **Purchase Order** | Creating, viewing, editing purchase orders |
| **Invoice** | Creating, viewing, editing invoices |
| **Inventory Transfer** | Creating, viewing, editing inventory transfers |
| **Journal Entry** | Creating, viewing, editing journal entries |

Each transaction permission has separate levels for creating, viewing, editing, and deleting. This allows granular control (e.g., a user can view invoices but not create them).

## Record Permissions

Record permissions control access to master data:

| Permission | Controls |
|---|---|
| **Customer** | Access to customer records |
| **Vendor** | Access to vendor records |
| **Item** | Access to item records |
| **Employee** | Access to employee records |
| **Partner** | Access to partner records |

## Global vs. Specific Permissions

Some permissions are global (apply to everything in that category), while others are specific:

- **Reports — View** gives access to all standard reports
- **Saved Search — View** only gives access to saved searches
- **SuiteAnalytics Workbook — View** only gives access to workbooks

If you want a role to access all reporting features, you need multiple permissions.

## Testing Permissions

Before deploying role changes, test permissions thoroughly:

1. Create a test user with the role being modified
2. Log in as that user (or impersonate them using the **Log In As** feature)
3. Verify:
   - Only the expected menus and centers appear
   - Expected transactions can be created and edited
   - Restricted transactions are not visible or accessible
   - Reports show only the expected data

Testing from the actual user's perspective is the only way to confirm permissions are correctly configured.

## Common Mistakes

- **Giving Edit permission when View would suffice**: Most users do not need to edit records. Start with View and upgrade only when needed.
- **Forgetting center permissions**: A user with transaction permissions but no center permission cannot access the menu to find those transactions.
- **Not testing after changes**: A permission change that seems harmless can have unexpected effects. Always test with a representative role.
- **Overlapping roles**: A user with two roles may have broader access than either role alone. Review users with multiple roles carefully.

## Best Practices

- Follow the principle of least privilege — grant the minimum permissions needed.
- Prefer View over Create, and Create over Edit, unless there is a clear need.
- Test permission changes in a sandbox before deploying to production.
- Review all roles and their permissions quarterly.
- Document the business reason for permission exceptions.
- Use the **Log In As** feature to test roles from the user's perspective.

## Related Articles

- [Roles](roles.md)
- [Users](users.md)
- [Centers](centers.md)
- [Security Best Practices](security-best-practices.md)
- [Centers and Roles](../getting-started/centers-and-roles.md)

## Oracle References

- [Oracle NetSuite Help Center: Permissions](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Permission Levels](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)