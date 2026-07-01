---
title: Inventory Transfers
module: Inventory
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Inventory Transfers

## Quick Summary

Inventory transfers move stock from one location to another. A basic inventory transfer updates quantities in both locations in one step. A transfer order provides multi-step tracking with shipment and receipt stages.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

When inventory needs to move between warehouses, stores, or locations, a transfer transaction records the movement. The correct transaction type depends on how much process control is needed.

## Transfer Types

### Basic Inventory Transfer

A basic transfer directly decreases the source location and increases the destination location after saving the transaction. It is a single-step movement with no intermediate tracking.

Use when:
- The move is simple and immediate
- No shipment tracking is needed
- The business does not need separate fulfillment and receipt steps
- Both locations are under the same management

### Transfer Order

A transfer order schedules and tracks inventory movement between locations with defined stages:

1. **Pending** — The transfer is planned but not yet in motion
2. **Shipped/In Transit** — The source location has shipped the items
3. **Received** — The destination location has received the items

Use when:
- Inventory needs to be shipped and formally received
- The business needs visibility into in-transit inventory
- Pick, pack, and ship workflows apply
- The source and destination locations have different managers or teams

## Navigation

| Transaction | Menu Path |
|---|---|
| Basic Inventory Transfer | Transactions > Inventory > Transfer Inventory |
| Transfer Order | Transactions > Inventory > Transfer Orders |

## Step-by-Step: Basic Transfer

1. Open the inventory transfer page
2. Select the source and destination locations
3. Add the inventory items to transfer
4. Enter quantities
5. Review required fields (classifications, memos, accounting impact)
6. Save the transfer
7. Confirm quantities updated as expected

## Step-by-Step: Transfer Order

1. Create a new Transfer Order
2. Select source and destination locations
3. Add items and quantities
4. Save the transfer order (status: Pending)
5. When ready to ship, fulfill the transfer order (status: Shipped/In Transit)
6. When received, receive the transfer order (status: Received)
7. Confirm quantities updated at both locations

## Example Scenario

A company with warehouses in Chicago and Atlanta needs to move 50 units of Chair Model X100 from Chicago to Atlanta.

- **Basic Transfer**: Quantities update immediately in both locations. No tracking.
- **Transfer Order**: Chicago ships 50 units (in transit). Atlanta receives 50 units. Full tracking.

## Common Mistakes

- **Using a basic transfer when a transfer order is needed**: Basic transfers provide no tracking. If you need to know what is in transit, use a transfer order.
- **Forgetting that a basic transfer updates inventory immediately**: There is no undo for a basic transfer. The adjustment happens as soon as you save.
- **Not checking bin, lot, or serial requirements**: If the item uses bins, lots, or serial numbers, the transfer must capture that information.
- **Not reviewing inventory availability before transferring**: Transferring stock that is already committed to sales orders can create fulfillment issues.

## Best Practices

- Use transfer orders for inter-warehouse movements where tracking matters.
- Use basic transfers for simple, immediate moves within the same management structure.
- Add memos or reason codes to document why inventory was moved.
- Review source and destination quantities carefully before saving.
- Use Saved Searches to monitor in-transit inventory and identify stuck transfers.

## Related Articles

- [What Is Inventory Management?](what-is-inventory.md)
- [Inventory Locations](inventory-locations.md)
- [Inventory Concepts](inventory-concepts.md)
- [Item Records](item-records.md)
- [Administration module](../administration/README.md) (future)

## Oracle References

- [Oracle NetSuite: Transferring Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Basic Inventory Transfers](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Inventory Transfer Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)