---
title: Invoicing and Revenue
module: Sales
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Invoicing and Revenue

## Quick Summary

Invoicing converts fulfilled orders into requests for payment. Revenue recognition determines when revenue is recorded in the financial statements. Together, they complete the financial side of the Order-to-Cash lifecycle.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Once items are shipped, the company needs to get paid. The invoice is the formal request for payment. Revenue recognition is the accounting process that determines when the revenue from that sale is recorded — it may be at shipment, at delivery, or over time, depending on the terms and accounting standards.

## The Invoicing Workflow

```
Order Fulfilled
       ↓
Invoice Generated (from SO or manually)
       ↓
Invoice Sent to Customer
       ↓
Accounts Receivable Updated
       ↓
Payment Received
       ↓
Cash Applied to Invoice
       ↓
AR Reduced, Cash Increased
```

## Invoice Creation

Invoices can be created:

- **From Sales Order**: Automatically after fulfillment
- **From Item Fulfillment**: Directly from the shipment record
- **Manual**: Standalone invoice for services or non-stocked items

Best practice is to create invoices from fulfilled sales orders. This ensures the invoice matches what was actually shipped.

## Invoice Fields

| Field | Purpose |
|---|---|
| **Customer** | Who is being billed |
| **Sales Order** | Reference to the original order |
| **Item** | What was shipped |
| **Quantity** | Quantity shipped |
| **Rate** | Price per unit |
| **Amount** | Line total |
| **Terms** | Payment due date |
| **Due Date** | When payment is expected |

## Revenue Recognition Methods

| Method | When Revenue Is Recognized |
|---|---|
| **At Shipment** | Revenue recorded when goods ship (most common for standard products) |
| **At Delivery** | Revenue recorded when customer receives goods |
| **Over Time** | Revenue recognized over the service period (subscriptions, maintenance) |
| **Upon Milestone** | Revenue recognized when contractual milestones are met (projects) |
| **ASC 606 (Deferred)** | Revenue deferred until performance obligations are satisfied |

## Accounts Receivable

When an invoice is created, an Accounts Receivable (AR) entry is recorded:

| Account | Debit/Credit |
|---|---|
| **Accounts Receivable** | Debit |
| **Revenue / Sales** | Credit |

When the customer pays:

| Account | Debit/Credit |
|---|---|
| **Cash** | Debit |
| **Accounts Receivable** | Credit |

## Customer Payments

Payments can be received as:

| Method | Processing |
|---|---|
| **Check** | Manual entry, deposit to bank |
| **Credit Card** | Payment gateway integration |
| **ACH / Electronic** | Bank transfer, automatic clearing |
| **Wire Transfer** | High-value, international |
| **Customer Portal** | Self-service payment |

## Business Example

A sales order for $5,000 is fulfilled on June 15. The company recognizes revenue at shipment.

1. Invoice generated on June 15 for $5,000
2. AR: +$5,000, Revenue: +$5,000
3. Customer has Net 30 terms — payment due July 15
4. Customer pays via ACH on July 10
5. Cash: +$5,000, AR: -$5,000

If the company used deferred revenue (ASC 606), the $5,000 would initially be recorded as deferred revenue (liability) and recognized over time as the performance obligation is satisfied.

## Common Mistakes

- **Invoicing before fulfillment**: Invoice amounts should match shipped quantities, not ordered quantities
- **Incorrect pricing on invoices**: Invoices with wrong prices require credit memos and re-processing
- **No automated invoice generation**: Manual invoicing is slow and error-prone
- **Revenue recognized too early**: Recognizing revenue before performance obligations are met violates accounting standards
- **Not reconciling AR**: Unreconciled AR balances can hide collection issues

## Best Practices

- Automate invoice generation from fulfilled sales orders
- Match invoice quantities to shipped quantities, not ordered quantities
- Implement revenue recognition rules that comply with ASC 606 / IFRS 15
- Reconcile AR weekly — identify and resolve discrepancies promptly
- Offer multiple payment methods to reduce collection friction
- Send invoices electronically and track delivery status

## Knowledge Check

1. A customer is invoiced for $10,000 on Net 30 terms. When is payment due? (Answer: 30 days after the invoice date.)
2. **Scenario**: A customer pays $5,000 for a one-year software subscription. When should the revenue be recognized? (Answer: Over the 12-month subscription period, not all at once.)
3. **Decision**: Your company ships products FOB shipping point — title passes when goods leave the warehouse. When should revenue be recognized? (Answer: At shipment — when title and risk transfer to the buyer.)

## Related Articles

- [Sales Orders](sales-orders.md)
- [Order Fulfillment](order-fulfillment.md)
- [Sales Best Practices](sales-best-practices.md)
- [Purchasing: Vendor Bills](../purchasing/vendor-bills-and-payments.md)
- [Accounting: Revenue Recognition](../accounting/revenue-recognition.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Invoicing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Revenue Recognition](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)