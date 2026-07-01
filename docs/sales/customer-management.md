---
title: Customer Management
module: Sales
difficulty: Beginner
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Customer Management

## Quick Summary

Customer records are the master data for everyone the organization sells to. Well-maintained customer records prevent order errors, support credit management, enable targeted marketing, and power customer analytics.

## Difficulty

Beginner

## Estimated Time

15 minutes

## Overview

Every sales transaction references a customer record. If the customer record has incorrect information — wrong address, outdated contact, incorrect terms — every order, invoice, and shipment built on that data will be wrong.

## Customer Record Structure

Customer records are accessed at:

```
Lists > Relationships > Customers > New
```

Key fields:

| Field | Purpose |
|---|---|
| **Company Name** | Legal business name |
| **Customer Number** | Unique identifier |
| **Email / Phone** | Primary contact |
| **Address** | Billing and shipping addresses |
| **Terms** | Payment terms (defaults from customer) |
| **Currency** | Transaction currency |
| **Credit Limit** | Maximum credit exposure |
| **Sales Rep** | Assigned sales representative |
| **Price Level** | Default pricing tier |
| **Category** | Customer type (wholesale, retail, etc.) |

## Customer Status

| Status | Meaning |
|---|---|
| **Active** | Can place orders and receive shipments |
| **Inactive** | Cannot place new orders — historical records preserved |
| **Hold** | Orders blocked — typically for credit or compliance reasons |

## Customer Classification

Classifying customers enables better reporting and targeted processes:

| Classification | Purpose |
|---|---|
| **Category** | Customer type (distributor, retailer, direct) |
| **Tier** | Value-based segmentation (platinum, gold, silver) |
| **Territory** | Geographic or sales region |
| **Industry** | Vertical market |
| **Price Level** | Pricing tier for this customer |

## Credit Management

Credit management protects the organization from unpaid orders:

| Credit Tool | Purpose |
|---|---|
| **Credit Limit** | Maximum outstanding balance |
| **Credit Hold** | Prevent orders when limit is exceeded |
| **Credit Check Workflow** | Automatic review for orders above threshold |
| **Payment Terms** | Net 30, Net 60, or prepay based on creditworthiness |
| **Deposit Requirement** | Require partial payment before fulfillment |

## Customer Onboarding

A structured process for new customers:

1. Collect legal name, tax ID, and business registration
2. Verify creditworthiness (credit report, trade references)
3. Set payment terms and credit limit
4. Assign price level and sales rep
5. Create customer record with all required information
6. Configure any customer-specific pricing or terms
7. Activate the customer

## Business Example

A wholesale distributor manages 2,000 customer accounts.

**Customer segmentation**:

| Tier | Criteria | Price Level | Terms | Service Level |
|---|---|---|---|---|
| Platinum | > $500K annual | Preferred pricing | Net 45 | Dedicated support |
| Gold | $100K-$500K | Standard discount | Net 30 | Priority support |
| Silver | < $100K | List price | Net 30 | Standard support |
| One-Time | No history | List price | Prepaid | Standard support |

**Credit management**:
- Platinum tier: $100,000 credit limit
- Gold tier: $50,000 credit limit
- Silver tier: $20,000 credit limit
- One-time: Prepaid only

## Common Mistakes

- **Duplicate customer records**: The same customer entered under slightly different names. Use a consistent naming convention and search before creating.
- **Missing or incorrect addresses**: Orders shipped to wrong addresses generate return shipping costs and delays.
- **No credit limit set**: Without credit limits, the company has no automated protection against over-extending credit.
- **Inactive customers not cleaned up**: Old records clutter lists and can be used accidentally.

## Best Practices

- Use a consistent naming convention: "Customer Name, Inc." not "Customer Name Incorporated"
- Collect complete address, contact, and tax information during onboarding
- Set credit limits based on creditworthiness, not just request
- Review customer records quarterly for accuracy
- Inactivate, never delete, customers that no longer purchase
- Use customer categories and tiers for reporting and segmentation

## Knowledge Check

1. A long-standing customer's credit limit is $50,000. Their outstanding balance is $48,000, and they place a new order for $5,000. What happens? (Answer: The order may trigger a credit hold because $48,000 + $5,000 > $50,000.)
2. **Scenario**: A customer has moved to a new address but the old address is still on the record. What risk does this create? (Answer: Shipments go to the wrong address, causing delays, return shipping costs, and potential loss of inventory.)
3. **Decision**: A new customer wants Net 60 terms. What information should you request before setting these terms? (Answer: Credit history, trade references, financial statements, and business registration.)

## Related Articles

- [What Is Order-to-Cash?](what-is-order-to-cash.md)
- [Sales Orders](sales-orders.md)
- [Pricing and Discounts](pricing-and-discounts.md)
- [Purchasing: Vendor Management](../purchasing/vendor-management.md)

## Oracle References

- [Oracle NetSuite Help Center: Customer Records](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Customer Management](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)