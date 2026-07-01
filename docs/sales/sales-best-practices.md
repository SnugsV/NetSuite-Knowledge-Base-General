---
title: Sales Best Practices
module: Sales
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Sales Best Practices

## Quick Summary

This article consolidates sales best practices across the entire Order-to-Cash lifecycle. Following these practices improves order accuracy, fulfillment speed, customer satisfaction, and revenue collection.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Customer Management Best Practices

- **Maintain a clean customer master**: One customer = one record. Use a consistent naming convention and search before creating.
- **Verify customer information during onboarding**: Collect legal name, tax ID, billing address, shipping addresses, and credit information before activating.
- **Set appropriate credit limits**: Base credit limits on creditworthiness, not on customer requests. Review annually.
- **Segment customers by value**: Tier customers (platinum, gold, silver) with appropriate pricing, terms, and service levels.
- **Review customer records quarterly**: Update contact information, verify addresses, inactivate dormant accounts.

## Order Management Best Practices

- **Verify inventory before order entry**: Check availability before accepting orders. If inventory is insufficient, set clear expectations for backorders.
- **Automate credit checks**: Integrate credit verification into the sales order workflow. Prevent orders that exceed credit limits.
- **Use sales order templates**: Templates for common order patterns reduce entry errors.
- **Set clear ship date commitments**: Communicate promised dates on the sales order. Fulfillment teams prioritize based on these dates.
- **Review open orders daily**: Identify orders past their ship date and resolve delays.

## Fulfillment Best Practices

- **Fulfill from sales orders**: Create Item Fulfillments from the sales order to maintain data integrity.
- **Pick items before entering fulfillment**: Confirm physical availability before recording the shipment.
- **Use barcode scanning**: Scan items and bins during picking to reduce errors.
- **Record package details**: Weight, tracking number, and carrier on every fulfillment.
- **Integrate with carrier systems**: Automate label printing, rate shopping, and tracking updates.
- **Monitor fulfillment SLAs**: Track time from order approval to shipment and investigate delays.

## Invoicing and AR Best Practices

- **Automate invoice generation**: Create invoices automatically from fulfilled orders.
- **Invoice shipped quantities, not ordered quantities**: Match invoice to what was actually shipped.
- **Send invoices electronically**: Email invoices with links to customer portals for faster payment.
- **Reconcile AR weekly**: Review AR aging, identify discrepancies, and follow up on overdue accounts.
- **Offer multiple payment methods**: Check, credit card, ACH, and customer portal for convenience.
- **Capture early payments**: Encourage prompt payment with discount terms where appropriate.

## Returns Best Practices

- **Require RA for all returns**: Document every return with an authorized reason code.
- **Inspect before restocking**: Never add returned items to inventory without inspection.
- **Track return reasons**: Categorize returns (defective, damage, incorrect item) and analyze trends.
- **Set clear return policies**: Time limits, condition requirements, and restocking fees.
- **Monitor return rates by product**: High return rates indicate quality or fulfillment issues.

## System Configuration Best Practices

- **Enable Sales Order management features**: Quote-to-order, deposit management, and revenue recognition.
- **Configure approval workflows**: Automate credit check, pricing approval, and order hold resolution.
- **Set up Saved Searches for monitoring**: Open orders, backorders, past-due shipments, pending approvals.
- **Build a sales dashboard**: Real-time KPIs for the sales and fulfillment teams.
- **Train sales and customer service teams**: Every user who touches sales orders should understand the O2C process.

## Sales Health Scorecard

| Metric | Healthy | Warning | Critical |
|---|---|---|---|
| On-Time Shipment Rate | > 98% | 95-98% | < 95% |
| Order Cycle Time | < 24 hours | 24-48 hours | > 48 hours |
| Backorder Rate | < 3% | 3-5% | > 5% |
| Fill Rate | > 98% | 95-98% | < 95% |
| Return Rate | < 3% | 3-5% | > 5% |
| DSO | < 45 days | 45-60 days | > 60 days |
| AR Over 90 Days | < 3% | 3-5% | > 5% |
| Perfect Order Rate | > 95% | 90-95% | < 90% |

## ERP Integration Summary

| Module | How Sales Connects |
|---|---|
| **Inventory** | Sales orders commit and consume inventory at fulfillment |
| **Purchasing** | Drop-ship POs generated from sales orders |
| **Accounting** | Invoices create AR, payments affect cash, COGS from fulfillment |
| **Manufacturing** | Sales demand drives production planning |
| **Saved Searches** | Order monitoring, pipeline analysis, customer reporting |
| **Workflows** | Order approval, credit check, fulfillment routing |
| **SuiteScript** | Custom pricing, order automation, portal integration |

## Related Articles

- [What Is Order-to-Cash?](what-is-order-to-cash.md)
- [Sales KPIs](sales-kpis.md)
- [Customer Management](customer-management.md)
- [Sales Orders](sales-orders.md)
- [All Inventory module articles](../inventory/README.md)
- [All Purchasing module articles](../purchasing/README.md)

## Oracle References

- [Oracle NetSuite Help Center: Sales Best Practices](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)