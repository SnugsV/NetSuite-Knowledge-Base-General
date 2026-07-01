---
title: Users
module: Administration
difficulty: Beginner
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Users

## Quick Summary

A user in NetSuite is anyone who can log in to the account. Users are created from employee records and assigned roles that determine what they can access and do. This article covers creating, managing, and deactivating users.

## Difficulty

Beginner

## Estimated Time

15 minutes

## Overview

Every person who accesses NetSuite must have a user account. User accounts are based on employee records — you typically create an employee record first, then grant that employee NetSuite access.

Users are managed from:

```
Setup > Users > Manage Users
```

## Creating a User

To create a new user:

1. Navigate to **Setup > Users > Manage Users**
2. Click **New User** (or **New Employee** if the employee record does not exist yet)
3. Enter the employee's personal details (name, email, phone)
4. Enter a login email address — this is what the user types to log in
5. Assign one or more roles
6. Save the user record

The new user will receive an email with instructions to set their password and log in.

## Employee Records vs. User Access

In NetSuite, employee records and user access are related but distinct:

| Concept | Description |
|---|---|
| **Employee Record** | The HR record containing name, department, job title, and personal information |
| **User Access** | The ability to log in to NetSuite and access data |
| **Role Assignment** | The permissions granted to the user |

A person can have an employee record without having NetSuite access (e.g., employees who never log in). Conversely, you can grant NetSuite access to someone without creating a full employee record using the **Salesforce/External User** type.

## Roles and Multiple Roles

Users can be assigned multiple roles. When a user with multiple roles logs in, they must select which role to use for that session. They can switch roles during their session without logging out.

Common multi-role scenarios:

- An accountant who needs **Accountant** for their daily work and **Administrator** for occasional configuration
- A warehouse manager who needs **Inventory Clerk** for receiving and **Warehouse Manager** for reporting
- A sales manager who needs **Sales Manager** and **Reporting Manager** for dashboards

Each role gives the user access to the centers, menus, records, and reports defined by that role's permissions.

## Deactivating Users

When an employee leaves the organization or no longer needs NetSuite access, their user account should be deactivated rather than deleted. Deactivation prevents login while preserving the user's transaction history.

To deactivate a user:

```
Setup > Users > Manage Users > [User Name] > Deactivate
```

Deactivating a user:

- Prevents them from logging in
- Preserves all records they created or modified
- Preserves their employee record
- Does not affect the audit trail
- Can be reversed if needed (Reactivate)

## User Statuses

| Status | Meaning |
|---|---|
| **Active** | User can log in and access NetSuite |
| **Inactive** | User cannot log in but records are preserved |
| **Locked** | User was locked due to failed login attempts (can be unlocked by an administrator) |
| **Expired** | User's access period has ended (for temporary or external users) |

## Bulk User Management

For organizations with many users, NetSuite supports bulk operations:

- **CSV Import** — Create or update multiple users at once using a CSV file
- **SuiteScript** — Automate user creation and management programmatically
- **SSO Group Mapping** — Automatically assign roles based on SSO directory groups (see [Single Sign-On](single-sign-on.md))

## Common Mistakes

- **Creating duplicate user records**: Always search for an existing employee record before creating a new user.
- **Not deactivating departing employees**: A deactivated user preserves their transaction history. Deleting a user record breaks the audit trail.
- **Giving too many roles**: Users with multiple roles can accidentally perform actions in the wrong role. Limit roles to what each person actually needs.
- **Using the same email for login and communication**: The login email can differ from the user's contact email. Use a corporate email for login.

## Best Practices

- Use a consistent naming convention for user accounts.
- Deactivate, don't delete, departing users.
- Review active users quarterly to identify inactive accounts.
- Use external user types for contractors and temporary workers.
- Document the roles assigned to each user and why.
- Train users to select the correct role if they have multiple roles assigned.

## FAQ

### Can a user have access without an employee record?

Yes. NetSuite supports external users (for partners, customers, and contractors) who have login access without being employees.

### How do I reset a user's password?

From the user record, click **Reset Password**. The user will receive an email with instructions.

### Can I restrict when a user can log in?

Not through standard settings, but you can use IP address rules to restrict login to specific locations or networks. See [Authentication](authentication.md).

## Related Articles

- [Roles](roles.md)
- [Permissions](permissions.md)
- [Authentication](authentication.md)
- [Centers and Roles](../getting-started/centers-and-roles.md)

## Oracle References

- [Oracle NetSuite Help Center: Users](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Managing Users](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)