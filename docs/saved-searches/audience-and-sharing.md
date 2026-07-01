---
title: Audience and Sharing
module: Saved Searches
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Audience and Sharing

## Quick Summary

Audience controls who can see and run a Saved Search. A search can be personal (only you), shared with your role, shared with specific roles, or made available to everyone with appropriate permissions.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Saved Searches can be shared across the organization. The Audience tab controls visibility, ensuring that the right people see the right searches without cluttering everyone's search list.

## Audience Levels

| Level | Who Can See It | Use Case |
|---|---|---|
| **Personal** | Only you | Personal monitoring, work in progress, sensitive searches |
| **Specific Roles** | Users assigned to selected roles | Departmental searches, role-specific reports |
| **All Roles** | Everyone with access to Saved Searches | Company-wide searches |
| **Specific Users** | Only the selected users (not commonly used) | Targeted sharing |

## Setting Audience

1. Go to the **Audience** subtab when creating or editing a Saved Search
2. Select the audience type
3. If choosing specific roles, select the roles from the list
4. Save the search

## Public vs. Private Searches

| Aspect | Public Search | Private Search |
|---|---|---|
| Created by | Any user with permissions | Any user |
| Visible to | Selected roles or all roles | Only the creator |
| Editable by | Creator and administrators | Only the creator |
| Default for new users | Can be pre-configured | Not available |
| Deletion | Creator or administrator | Only the creator |

## Best Practice: Role-Based Sharing

Instead of sharing searches individually, define searches by role:

- **Sales team**: Pipeline reports, open orders, customer activity
- **Warehouse**: Low stock alerts, pending transfers, items to fulfill
- **Finance**: Aging reports, credit limit exceptions, transaction audit
- **Executives**: KPI summaries, trend reports, exception dashboards

This ensures users only see searches relevant to their work.

## Editing and Deleting Public Searches

- The search creator can edit or delete their own searches
- Administrators can edit or delete any search
- Non-creators with access to a public search cannot edit it
- If a search is deleted, users with it on their dashboard will see an error until the portlet is removed

## Search Organization

When many searches exist, organizing them helps users find what they need:

- **Naming conventions**: Use prefixes like "INV - Low Stock," "SALES - Pipeline," "FIN - Aging"
- **Folders**: Saved Searches can be organized into folders for easier navigation
- **Descriptions**: Add a brief description explaining what the search does and when to use it

## Search Visibility and Permissions

Even if a search is shared with a role, the user still needs appropriate record-level permissions to see the data. A user with "View" permission on transactions can run a transaction search but only see transactions they have access to. A user with no transaction permissions cannot run a transaction search at all, regardless of sharing.

## Common Mistakes

- **Making every search public**: Users end up with hundreds of irrelevant searches. Only share what is useful to the audience.
- **Not cleaning up old searches**: Retired searches should be deleted or made private to avoid clutter.
- **Sharing by individual user instead of role**: If you share with specific users, you need to update sharing every time the team changes. Role-based sharing is easier to maintain.
- **Confusing audience with permissions**: Sharing gives visibility to the search. Record-level permissions control what data the user sees.
- **Not using naming conventions**: "Search 1" and "Test" become meaningless as the search count grows.

## Best Practices

- Default to personal searches. Only make a search public when there is a clear reason to share.
- Share by role, not by individual user.
- Use a consistent naming convention (prefix by module or department).
- Add a description to every public search explaining its purpose.
- Review public searches quarterly and archive or delete unused ones.
- Educate users on how to find and use shared searches.

## Related Articles

- [Filters](filters.md)
- [Available Filters](available-filters.md)
- [Performance Best Practices](performance-best-practices.md)
- [Permissions](../getting-started/centers-and-roles.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Audience](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)