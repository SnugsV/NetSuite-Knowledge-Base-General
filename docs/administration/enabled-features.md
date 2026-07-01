---
title: Enabled Features
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Enabled Features

## Quick Summary

The Enable Features page is where administrators turn NetSuite features on and off. Feature enablement controls which capabilities are available in the account — from basic features like inventory management to advanced modules like SuiteScript and WMS. Enabling a feature can change the user interface, add new transactions, and affect performance.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

NetSuite ships with most features disabled by default. This allows each account to enable only what it needs, keeping the interface clean and reducing complexity. The Enable Features page is the central control point for all feature-level configuration.

```
Setup > Company > Enable Features
```

## How Feature Enablement Works

Features are organized into categories:

| Category | Examples |
|---|---|
| **Transactions** | Sales Orders, Purchase Orders, Inventory |
| **Records** | Customers, Vendors, Partners |
| **Company** | Multi-Currency, Subsidiaries, Departments |
| **Accounting** | Revenue Recognition, Fixed Assets, Multi-Book |
| **SuiteCloud** | SuiteScript, SuiteTalk, CSV Import, Web Services |
| **CRM** | Campaign Management, Support Cases, Commission Reporting |
| **Web Presence** | Checkout, Web Store, Site Builder |

Each feature has a checkbox. When checked, the feature becomes available in the account. Some features have additional sub-options.

## Irreversible Features

Some features, once enabled, cannot be disabled. These are marked with a warning icon in the Enable Features page. Examples include:

- **Multi-Currency** — Once transactions exist in multiple currencies, the feature cannot be turned off
- **Advanced Inventory** — Once bin numbers, lots, or serial numbers are in use, the feature cannot be disabled
- **Multi-Book Accounting** — Once multiple accounting books have transactions, the feature is permanent
- **OneWorld (Subsidiaries)** — Once subsidiaries are created, they cannot be removed

Before enabling an irreversible feature, verify that the organization needs it and understands the commitment.

## Feature Dependencies

Some features require other features to be enabled first. For example:

- **Advanced Inventory** requires **Inventory Management** to be enabled
- **WMS** requires **Advanced Inventory** and **Multiple Inventory Locations**
- **SuiteTalk REST Web Services** requires **Web Services** to be enabled
- **Revenue Management** requires **Revenue Recognition** to be enabled

When you enable a feature, NetSuite automatically enables any required dependencies.

## Feature Impact on the Interface

Enabling a feature can change what users see:

- New menu items appear (e.g., enabling Inventory adds the **Transactions > Inventory** menu)
- New fields appear on records (e.g., enabling Multi-Currency adds currency fields to transaction records)
- New portlets become available for dashboards
- New transaction types become available

These changes happen immediately for all users with appropriate permissions.

## Feature Enablement and Permissions

Enabling a feature makes it available in the account, but permissions control who can access it. A feature can be enabled but restricted to specific roles. For example:

1. Admin enables **Inventory Management**
2. The **Sales Representative** role has no inventory permissions
3. Sales representatives see no inventory-related menus or records

See [Permissions](permissions.md) for how access is controlled.

## Feature Enablement Checklist

Before enabling a feature:

- [ ] Does the organization need this feature now? Not "someday" — now.
- [ ] Is the feature irreversible? If so, are you sure?
- [ ] Are all dependencies already enabled?
- [ ] Have you tested this feature in a sandbox account?
- [ ] Do you understand how this feature affects the interface for existing users?
- [ ] Have you identified which roles need access to this feature?

## Common Mistakes

- **Enabling features "just in case"**: Every enabled feature adds complexity. Only enable what is actually needed.
- **Not checking irreversible status**: Enabling an irreversible feature without understanding the commitment can cause problems if the organization's needs change.
- **Enabling features in production without sandbox testing**: Always test feature enablement in a sandbox first, especially irreversible features.
- **Forgetting to update permissions after enabling a feature**: Enabling a feature does not automatically grant access to users. Permissions must be updated separately.

## Best Practices

- Enable features only when there is a clear business need.
- Test irreversible features in a sandbox before enabling in production.
- After enabling a feature, review which roles need access and update permissions accordingly.
- Document why each feature was enabled and when.
- Review the Enable Features page periodically to disable unused features.
- Schedule feature enablement during low-usage periods to minimize user disruption.

## Related Articles

- [Company Setup](company-setup.md)
- [Company Preferences](company-preferences.md)
- [Permissions](permissions.md)
- [Administration Overview](administration-overview.md)
- [Sandbox and Release Preview](sandbox-and-release-preview.md)

## Oracle References

- [Oracle NetSuite Help Center: Enable Features](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)