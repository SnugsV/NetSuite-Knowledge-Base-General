---
title: Inventory Status
module: Inventory
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed:
---

# Inventory Status

## Quick Summary

Item records in NetSuite can be Active, Inactive, or Pending. The status controls whether the item can be used on transactions, appears in lists, and is available for sales or purchasing. Proper lifecycle management keeps item lists clean and prevents errors.

## Difficulty

Beginner

## Estimated Time

5 minutes

## Overview

Not every item should be available at all times. Discontinued products, seasonal items, and items being set up need different statuses. NetSuite's item status system provides that control.

## Item Statuses

| Status | Meaning | Can Be Sold | Can Be Purchased | Appears in Lists |
|---|---|---|---|---|
| **Active** | Item is available for use | Yes | Yes | Yes |
| **Inactive** | Item is retired or discontinued | No | No | No (unless "Show Inactive" is checked) |
| **Pending** | Item is being set up | No | No | Only in item setup pages |

## Active Items

Active items function normally. They appear on transaction forms, can be searched, and can be sold, purchased, transferred, or adjusted. Most items should be Active during their normal lifecycle.

## Inactive Items

When an item is no longer used — discontinued, obsolete, replaced — it should be marked Inactive. Inactive items:

- Are hidden from standard lists and menus
- Cannot be added to new transactions
- Are NOT deleted — existing transactions that reference the item remain intact
- Can be reactivated if needed

Inactivating is better than deleting because it preserves transaction history.

## Pending Items

The Pending status is used during item setup. While an item is Pending:

- It can be configured with all necessary fields
- It cannot be accidentally used on transactions
- It can be moved to Active when ready

Not all NetSuite accounts have this status available. It depends on feature enablement.

## When to Change Status

| Event | New Status |
|---|---|
| Item created but not ready for use | Pending |
| Item is ready | Active |
| Item is discontinued | Inactive |
| Item is replaced by another SKU | Inactive (note replacement in description) |
| Seasonal item off-season | Inactive |
| Item was inactivated by mistake | Active |

## Bulk Inactivating Items

To inactivate multiple items at once:

1. Run a Saved Search for items matching your criteria (e.g., "Items with no sales in 2 years")
2. Export the results
3. Use CSV Import to update the Inactive field
4. Verify the changes after import

## Effects of Inactivating

| Downstream Effect | What Happens |
|---|---|
| Open purchase orders | Remain open — the item can still be received |
| Open sales orders | Remain open — the item can still be fulfilled |
| Historical transactions | Unchanged |
| Saved searches | Results may exclude inactive items unless the search is configured to include them |
| Dashboard portlets | May exclude inactive items |
| Reorder calculations | Inactive items are excluded |

## Common Mistakes

- **Deleting items instead of inactivating**: Deletion breaks transaction history and removes audit trail references. Always inactivate.
- **Not inactivating obsolete items**: Obsolete items clutter lists, confuse users, and can appear in reports and searches unless explicitly excluded.
- **Inactivating items with open balances**: Before inactivating, ensure all quantities have been either sold, transferred, or adjusted out. An inactive item with quantity on hand creates reconciliation issues.
- **Not communicating status changes**: If purchasing or sales teams are not told an item is being inactivated, it can cause confusion when the item no longer appears in transaction forms.

## Best Practices

- Inactivate, never delete, items that are no longer used.
- Review item lists quarterly and inactivate obsolete items.
- Adjust remaining inventory to zero before inactivating stock-keeping items.
- Communicate planned inactivations to affected teams in advance.
- Use Saved Searches to identify candidates for inactivation (e.g., "Items with no sales in 12 months").

## Related Articles

- [Item Records](item-records.md)
- [Item Types](item-types.md)
- [What Is Inventory Management?](what-is-inventory.md)

## Oracle References

- [Oracle NetSuite Help Center: Item Status](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)