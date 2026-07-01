---
title: Backorders and Exceptions
module: Sales
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Backorders and Exceptions

## Quick Summary

Backorders occur when a customer orders more than is available in inventory. Order exceptions include holds, cancellations, credit blocks, and shipping delays. Managing exceptions effectively prevents customer dissatisfaction and lost revenue.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Not every sales order flows smoothly through the O2C lifecycle. Items may be out of stock, credit limits may be exceeded, or shipping information may be incomplete. Backorders and exceptions are the reality of order management — the question is how well they are handled.

## Backorders

A backorder occurs when an item on a sales order cannot be fulfilled because there is not enough available inventory.

### Backorder Causes

| Cause | Mitigation |
|---|---|
| Unexpected demand | Monitor inventory trends and adjust reorder points |
| Supplier delays | Maintain safety stock for critical items |
| Inaccurate inventory counts | Improve cycle counting accuracy |
| Seasonal demand spikes | Plan inventory for seasonal peaks |
| Promotional surges | Build inventory before promotions |

### Backorder Management

| Action | Description |
|---|---|
| **Notify customer** | Communicate the delay and expected ship date immediately |
| **Offer alternatives** | Suggest substitute products or partial fulfillment |
| **Prioritize allocation** | Allocate incoming inventory to oldest backorders first |
| **Cancel if necessary** | If the backorder cannot be filled within a reasonable time, cancel the line |

## Order Holds

Orders can be placed on hold for several reasons:

| Hold Type | Cause | Resolution |
|---|---|---|
| **Credit Hold** | Customer has exceeded credit limit | Review credit, request payment, or increase limit |
| **Price Hold** | Order pricing requires approval | Route to pricing manager for approval |
| **Address Hold** | Shipping address is invalid or incomplete | Contact customer to verify address |
| **Fraud Hold** | Order matches fraud indicators | Review with fraud prevention team |
| **Customer Hold** | Customer account is on hold | Resolve customer account issue |

## Order Cancellations

Orders may be cancelled at various stages:

| Stage | Can Cancel? | Considerations |
|---|---|---|
| **Draft** | Yes — no impact | Simply delete the draft |
| **Approved** | Yes — decommit inventory | Decommit reserved inventory |
| **Picked** | Yes — restock items | Return picked items to bins |
| **Shipped** | No — initiate return process | Create return authorization |
| **Invoiced** | No — create credit memo | Apply credit to customer account |

## Exception Reporting

Use Saved Searches to monitor exceptions:

| Search | Purpose |
|---|---|
| **Orders on Credit Hold** | Identify orders blocked by credit |
| **Open Backorders** | Track unfilled order lines |
| **Orders Past Ship Date** | Identify late shipments |
| **Orders Pending Approval** | Monitor approval bottlenecks |
| **Cancelled Orders** | Review cancellation reasons |

## Business Example

An online retailer processes 500 orders per day.

**Backorder scenario**:
1. A flash sale drives unexpected demand for SKU X — 2,000 units ordered in 2 hours
2. Available inventory: 500 units
3. 500 units ship immediately, 1,500 units backordered
4. Customers notified: expected restock in 10 days
5. Priority allocation: first 500 units of restock go to oldest backorders
6. After restock: all backorders filled within 12 days

**Result**: 92% of backordered customers received their items within the promised timeframe. 8% cancelled.

## Common Mistakes

- **Not notifying customers of backorders**: Customers who are not told about delays may cancel or file disputes
- **No priority for backorder fulfillment**: New orders getting inventory while backorders wait creates customer complaints
- **Ignoring hold queues**: Orders on hold that are not reviewed accumulate and become aged
- **Cancelling orders without customer confirmation**: Cancelling an order the customer still wants causes lost revenue
- **Not analyzing backorder causes**: Recurring backorders on the same items indicate a replenishment or forecasting problem

## Best Practices

- Notify customers immediately when a backorder occurs
- Implement automated priority allocation for backorders
- Review hold queues daily and resolve within 24 hours
- Analyze backorder patterns monthly to identify systemic issues
- Set reorder points based on demand variability
- Use Saved Searches to monitor exception queues in real time

## Knowledge Check

1. A sales order has 50 units of an item, but only 30 are available. What are the options? (Answer: Partial fulfillment of 30, backorder 20. Or hold the order until all 50 are available, if the customer prefers.)
2. **Scenario**: A customer's order has been on credit hold for 5 days. What should be done? (Answer: Contact the customer to resolve the credit issue. If no response, consider cancelling the order.)
3. **Decision**: A key item is backordered every month. What is the root cause? (Answer: Reorder point may be too low, safety stock insufficient, or lead time underestimated.)

## Related Articles

- [Sales Orders](sales-orders.md)
- [Order Fulfillment](order-fulfillment.md)
- [Customer Management](customer-management.md)
- [Inventory: Replenishment](../inventory/replenishment.md)

## Oracle References

- [Oracle NetSuite Help Center: Order Management](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)