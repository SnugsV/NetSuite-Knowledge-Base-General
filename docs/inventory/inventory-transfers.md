---
title: Inventory Transfers
department: NetSuite
module: Inventory
status: Draft
version: 0.1
created: 2026-07-01
tags: [inventory, transfers, locations, transfer-order]
source_type: Oracle Documentation Summary
---

# Inventory Transfers

## AI Summary

Inventory transfers move inventory from one location to another. A basic inventory transfer updates quantities in both locations in one step, while a transfer order is better when the business needs to schedule, ship, receive, and track the movement through stages.

## Purpose

Use inventory transfers when stock needs to be moved between warehouse locations or other inventory locations. The correct transaction type depends on how much process control and tracking is needed.

## Transfer Types

### Basic Inventory Transfer

A basic transfer directly decreases the source location and increases the destination location after saving the transaction.

Use this when:

- The move is simple.
- No shipment tracking is needed.
- The inventory movement is immediate.
- The business does not need separate fulfillment and receipt steps.

### Transfer Order

A transfer order schedules and tracks inventory movement between locations.

Use this when:

- Inventory needs to be shipped and received.
- The business wants visibility into in-transit inventory.
- Warehouse or shipping teams need a more controlled process.
- Pick, pack, and ship workflows may apply.

## General Navigation

Basic inventory transfers are commonly entered from:

```text
Transactions > Inventory > Transfer Inventory
```

Transfer orders are commonly accessed through inventory transaction menus depending on account configuration and role permissions.

## Step-by-Step: Basic Transfer

1. Open the inventory transfer page.
2. Select the source and destination locations.
3. Add the inventory items to transfer.
4. Enter quantities.
5. Review required fields, classifications, memos, and accounting impact.
6. Save the transfer.
7. Confirm the quantities updated as expected.

## Common Mistakes

- Using a basic transfer when the move needs shipment tracking.
- Forgetting that a basic transfer updates inventory immediately.
- Not checking whether bins, lots, or serial numbers are required.
- Not reviewing inventory availability before entering the transfer.
- Failing to document why inventory was moved.

## Best Practices

- Use transfer orders for controlled warehouse moves.
- Use basic transfers for simple immediate moves.
- Add memos or reason codes when available.
- Review source and destination locations carefully before saving.
- Use saved searches or reports to audit inventory movement.

## Related Topics

- Inventory Overview
- Transfer Orders
- Bin Transfers
- Inventory Adjustments
- Inventory Replenishment

## Official References

- Oracle NetSuite: Transferring Inventory
- Oracle NetSuite: Basic Inventory Transfers
- Oracle NetSuite: Inventory Transfer Orders
