---
title: Pricing and Discounts
module: Sales
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Pricing and Discounts

## Quick Summary

Pricing strategies and discount structures determine how products are priced for different customers, channels, and situations. NetSuite supports multiple price levels, quantity-based pricing, promotional discounts, and customer-specific pricing.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Not every customer pays the same price. A high-volume distributor gets better pricing than a one-time buyer. Holiday promotions offer temporary discounts. Contract customers have negotiated rates. Pricing management ensures the right customer gets the right price.

## Price Levels

Price levels define standard pricing tiers:

| Price Level | Use | Example |
|---|---|---|
| **List Price** | Base price for all customers | $100.00 |
| **Wholesale** | Reseller pricing (20% off list) | $80.00 |
| **Distributor** | Volume partner pricing (35% off list) | $65.00 |
| **MAP** | Minimum advertised price (retail floor) | $90.00 |
| **Promotional** | Temporary discount campaign | $75.00 |

Each item can have prices defined for multiple price levels on the item record.

## Customer-Specific Pricing

Beyond price levels, individual customers can have negotiated prices:

- **Fixed price per item** — A specific price agreed with the customer
- **Price level override** — A custom price level assigned to this customer only
- **Contract pricing** — Prices defined in a sales contract or agreement

Customer-specific pricing is configured on the customer record or through pricing agreements.

## Quantity Discounts

Volume-based pricing encourages larger orders:

| Quantity Range | Price per Unit |
|---|---|
| 1-99 | $12.00 |
| 100-499 | $11.00 |
| 500-999 | $10.00 |
| 1000+ | $9.00 |

Quantity discounts are configured on the item record.

## Promotional Discounts

Time-limited promotions can be applied:

- **Percentage discount** — 15% off all orders this month
- **Fixed amount off** — $50 off orders over $500
- **Free shipping** — Waive shipping charges for qualifying orders
- **Buy X get Y** — BOGO promotions
- **Bundle discounts** — Discount when items are purchased together

## Discount Approval

For large or unusual discounts, approval workflows can enforce controls:

| Discount % | Approval Required |
|---|---|
| 0-10% | Sales rep authority |
| 10-20% | Sales manager |
| 20-40% | VP of Sales |
| 40%+ | Executive approval |

## Business Example

An electronics distributor sells headphones to three customer tiers:

| Customer | Price Level | Annual Volume | Price per Unit |
|---|---|---|---|
| BestSound Retail | Wholesale | 5,000 units | $45.00 |
| SoundPro Distributor | Distributor | 20,000 units | $38.00 |
| Acme Corp (one-time) | List | 100 units | $55.00 |

**Scenario**: A promotional campaign runs for the holiday season — 10% off all headphones.

- BestSound: $45.00 → $40.50
- SoundPro: $38.00 → $34.20
- Acme: $55.00 → $49.50

The system applies the correct price level first, then the promotional discount.

## Common Mistakes

- **Too many price levels**: 20 price levels confuse the sales team and increase pricing errors
- **Discounts without end dates**: Promotions that are never removed become permanent discounts
- **No discount approval process**: Sales reps granting 50% discounts without authorization erodes margins
- **Customer-specific pricing not documented**: Verbal pricing agreements not recorded in the system cause billing disputes
- **Pricing not aligned with contracts**: Contract pricing that differs from system prices causes invoicing issues

## Best Practices

- Define 3-5 price levels that cover your customer segments
- Use quantity-based pricing to encourage larger orders
- Set discount approval thresholds appropriate to your margins
- Document all customer-specific pricing agreements in the system
- Review price levels and discount structures annually
- Audit discount usage quarterly — identify patterns that erode margin

## Knowledge Check

1. A customer buys 750 units. Price breaks: 1-99 = $12, 100-499 = $11, 500-999 = $10, 1000+ = $9. What is the price per unit? (Answer: $10.00 — the 500-999 price break applies.)
2. **Scenario**: A sales rep offers a 35% discount without approval. Your policy requires approval for discounts over 20%. What happened? (Answer: The rep exceeded their authority. The system or manager should prevent this.)
3. **Decision**: Your company has three distribution channels — retail, wholesale, and direct. How many price levels do you need? (Answer: At least three, plus a list price. Consider additional levels for promotional or contract pricing.)

## Related Articles

- [Customer Management](customer-management.md)
- [Sales Orders](sales-orders.md)
- [Sales Best Practices](sales-best-practices.md)
- [Item Records](../inventory/item-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Pricing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Price Levels](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)