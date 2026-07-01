---
title: Sales Orders
module: Sales
difficulty: Intermediate
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Sales Orders

## Quick Summary

A sales order is the core document in the Order-to-Cash lifecycle. It records what a customer wants to buy, at what price, under what terms, and when it should be delivered. The sales order drives fulfillment, invoicing, and revenue recognition.

## Difficulty

Intermediate

## Estimated Time

20 minutes

## Overview

The sales order is the formal commitment to sell. It documents the agreement between the company and the customer: what products or services, in what quantities, at what prices, with what delivery terms. Once accepted, it drives every downstream process.

## The Sales Order Lifecycle

```
Draft → Pending Approval → Approved → Picking → Picked → Packed → Shipped → Invoiced → Closed
```

## Creating a Sales Order

```
Transactions > Sales > Enter Sales Orders
```

Key fields:

| Field | Purpose |
|---|---|
| **Customer** | Who is buying |
| **Date** | Order date |
| **Item** | What is being ordered |
| **Quantity** | How many units |
| **Rate** | Price per unit |
| **Amount** | Line total |
| **Ship Date** | When it needs to ship |
| **Ship To** | Delivery address |
| **Terms** | Payment terms |
| **Sales Rep** | Responsible representative |

## Order Types

| Order Type | Use |
|---|---|
| **Standard Sales Order** | Regular customer order for stocked items |
| **Drop Ship Order** | Order fulfilled by vendor directly to customer |
| **Special Order** | Order for an item not normally stocked, sourced from vendor |
| **Kit Order** | Order for a kit item that groups multiple components |
| **Deposit Order** | Order requiring a deposit before fulfillment |
| **Rush Order** | Priority order with expedited processing |

## Inventory Commitment

When a sales order is created, it commits inventory:

| Commitment Type | Behavior |
|---|---|
| **Standard Commitment** | Reduces Available quantity by the ordered amount |
| **Manual Commitment** | User specifies which location or bin to commit from |
| **No Commitment (backorder)** | Item is backordered until inventory is available |

## Order Approval

Sales orders may require approval based on:

| Condition | Required Approval |
|---|---|
| Order exceeds customer credit limit | Credit department |
| Large order value | Sales management |
| Non-standard pricing or discounts | Pricing approval |
| New customer | Credit verification |
| Rush processing | Operations manager |

## Business Example

A customer calls to order 50 units of Product X at $25 each.

1. Customer service creates a sales order: 50 units, Customer ABC Corp, standard terms
2. System checks credit limit: $15,000 available, order is $1,250 — approved
3. System checks inventory: 200 units available, 50 committed
4. Order status: Approved
5. Warehouse pick list generated
6. Order moves to fulfillment

## Common Mistakes

- **Incomplete order information**: Missing ship dates, ship-to addresses, or line items cause downstream delays
- **Incorrect pricing**: Sales orders with wrong prices create invoicing disputes
- **No inventory check before order entry**: Committing to orders that cannot be filled creates backorders and cancellations
- **Skipping credit check**: Orders that exceed credit limits should be flagged before fulfillment
- **Not setting promised ship dates**: Without promised dates, the fulfillment team cannot prioritize orders

## Best Practices

- Verify customer credit before order approval
- Check inventory availability before accepting orders
- Set clear ship date commitments
- Use sales order templates for common order patterns
- Review open orders daily and prioritize late shipments
- Automate credit check and approval workflows
- Integrate order entry with customer portals for self-service

## Knowledge Check

1. A sales order is created for 100 units. Available inventory is 60 units. What happens? (Answer: 60 units are committed, 40 units are backordered or the order is held until inventory is available.)
2. **Scenario**: A customer places a rush order that requires special pricing approval. The pricing manager is out of the office. What should the workflow do? (Answer: Escalate to the next-level approver or use an escalation rule for urgent orders.)
3. **Decision**: Your company sells both stocked items and custom-configured products. Should both use the same sales order type? (Answer: Yes — standard sales orders handle both. Configure the item accordingly.)

## Related Articles

- [What Is Order-to-Cash?](what-is-order-to-cash.md)
- [Order Fulfillment](order-fulfillment.md)
- [Pricing and Discounts](pricing-and-discounts.md)
- [Backorders and Exceptions](backorders-and-exceptions.md)
- [Inventory: Fulfilling Orders](../inventory/fulfilling-orders.md)

## Oracle References

- [Oracle NetSuite Help Center: Sales Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Creating Sales Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)