---
title: Centers
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Centers

## Quick Summary

Centers are the navigational framework of NetSuite. Each center groups related menus, dashboards, and pages around a business function. Administrators control which centers each role can access, effectively determining what parts of the interface users see.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Centers are the primary organizational structure of the NetSuite interface. Each center represents a functional area — Sales, Inventory, Purchasing, Reports, Setup, and so on. When a user switches to a center, they see a dashboard and menu structure specific to that area.

From an administration perspective, centers are the high-level access control. If a role cannot access the Inventory center, the user sees no inventory-related menus, records, or dashboards — regardless of their individual permissions.

## Standard Centers

| Center | Purpose | Common Users |
|---|---|---|
| **Home** | Personal dashboard, KPIs, reminders | All users |
| **Sales** | Sales orders, quotes, customers | Sales team |
| **Inventory** | Items, locations, transfers | Warehouse, operations |
| **Purchasing** | Purchase orders, vendors | Procurement |
| **CRM** | Leads, prospects, campaigns | Sales, marketing |
| **Reports** | Saved searches, financial reports | All users |
| **Setup** | Administration and configuration | Administrators only |

## Controlling Center Access by Role

Center access is configured in the role definition. When you create or edit a role, you select which centers the role can access:

1. Navigate to **Setup > Users > Manage Roles**
2. Select the role to edit
3. Go to the **Centers** subtab
4. Check the centers the role should access
5. Save the role

A role that is not assigned to a center cannot see that center in the interface. The center's menu items, dashboard, and reports are effectively invisible.

## Center Permissions vs. Transaction Permissions

Center permissions and transaction permissions work together:

- **Center permission** — Whether the role can see the center in the interface
- **Transaction permission** — Whether the role can create, view, or edit specific transactions within that center

A role needs BOTH the center permission AND the relevant transaction permission to work in an area. For example:

- A role with **Sales Center — View** but **Sales Order — None** can see the Sales center but cannot create or view sales orders
- A role with **Inventory Center — None** but **Inventory Transfer — Edit** cannot access inventory menus at all

This dual-layer system prevents accidental access. Even if a transaction permission is granted, the role also needs the center permission to find and use it.

## Custom Centers

Administrators can create custom centers using the **Custom Center** feature. Custom centers are useful for:

- Grouping custom records and transactions in one place
- Creating role-specific landing pages
- Organizing menus for specialized workflows

Custom centers are created at:

```
Setup > Customization > Centers > New
```

## Default Centers by Role

When you create a new role, NetSuite pre-selects some centers based on the role type:

| Role Type | Default Centers |
|---|---|
| Sales roles | Home, Sales, CRM |
| Inventory roles | Home, Inventory |
| Accounting roles | Home, Reports |
| Administrative roles | All centers |

These defaults can be changed at any time.

## Center Visibility and Dashboard

Each center has its own dashboard that serves as its landing page. The dashboard displays portlets relevant to that center's function. For example, the Inventory center dashboard may show low stock alerts, pending transfers, and inventory KPIs.

Administrators can configure center dashboards by:

- Adding or removing portlets
- Configuring KPI metrics for each center
- Setting default portlet layouts

However, individual users can further personalize their own dashboards (see [Personalization](../getting-started/personalization.md)).

## Common Mistakes

- **Not assigning center permissions**: A user can have full Edit permission on sales orders but still not see the Sales center. Both layers must be configured.
- **Giving access to Setup center unnecessarily**: The Setup center should be restricted to administrators and power users who genuinely need it.
- **Confusing centers with navigation menus**: Centers are the top-level framework. Navigation menus appear within centers.
- **Not considering the Home center**: The Home center is usually the default landing page. Ensure every role has access to it.

## Best Practices

- Assign only the centers a role genuinely needs for its function.
- Review center access during role audits.
- Keep the Setup center restricted to administrative roles.
- Use custom centers sparingly — they add complexity.
- Test center access from the perspective of each role after making changes.

## Related Articles

- [Roles](roles.md)
- [Permissions](permissions.md)
- [Centers and Roles](../getting-started/centers-and-roles.md)
- [User Interface Overview](../getting-started/user-interface.md)

## Oracle References

- [Oracle NetSuite Help Center: Centers](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)