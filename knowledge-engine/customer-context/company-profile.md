# Company Profile

## Purpose

Company profile information helps the AI understand the customer's business context. The same problem can have different causes and solutions depending on the company's industry, size, business model, and operations.

## Questions to Ask

### Industry and Business Model

| Question | Why It Matters |
|---|---|
| What industry is the company in? | Different industries use different NetSuite features and have different regulatory requirements. |
| What is the business model? (distributor, manufacturer, retailer, services) | Business model determines which ERP modules are most relevant. |
| Does the company manufacture products? | Manufacturing adds BOMs, work orders, WIP, routings, and cost variance complexity. |
| Does the company sell products, services, or both? | Mixed businesses need both inventory and non-inventory item handling. |

### Company Size and Scale

| Question | Why It Matters |
|---|---|
| Approximate number of users? | Larger deployments often have more role complexity, custom permissions, and performance considerations. |
| Transaction volume per month? | High-volume accounts may hit API limits, script governance limits, or performance thresholds. |
| Number of locations or warehouses? | Multi-location adds complexity to inventory, fulfillment, and transfer processes. |
| Number of SKUs? | Large item masters need different search and management strategies. |

### International Operations

| Question | Why It Matters |
|---|---|
| Does the company operate in multiple countries? | Multi-currency, multi-subsidiary (OneWorld), and international tax compliance are affected. |
| Does the company use OneWorld? | OneWorld adds intercompany accounting, currency conversion, and subsidiary-level configuration. |
| Does the company import products internationally? | Landed cost, customs duties, and multiple freight carriers affect inventory valuation. |
| Do they have multiple legal entities? | Intercompany transactions, elimination, and consolidated reporting. |

## Decision Tree: Business Model Impact

```
Is the company a manufacturer?
  ├── Yes → Manufacturing features are active. Look for BOMs, work orders, WIP, routings.
  │           The problem may involve component consumption, WIP valuation, or cost variances.
  │
  └── No → Manufacturing features are likely inactive.
           The problem is probably in distribution, purchasing, sales, or accounting.

Is the company a retailer?
  ├── Yes → Look for multi-location inventory, point-of-sale integration, returns processing.
  │
  └── No → Focus on wholesale or B2B processes.

Does the company have international operations?
  ├── Yes → Multi-currency, OneWorld, landed cost. Check subsidiary-level configuration.
  │
  └── No → Single-currency, single-subsidiary focus.
```

## How Company Profile Affects Troubleshooting

| Profile Attribute | Troubleshooting Impact |
|---|---|
| Manufacturer | Work order issues, component consumption, WIP, cost variances |
| Distributor | Purchasing, inventory, fulfillment, transfer issues |
| Retailer | Multi-location, returns, POS integration, customer-facing processes |
| Services | Non-inventory items, project-based accounting, revenue recognition |
| International | Multi-currency, OneWorld, intercompany, compliance issues |
| High-volume | Performance, API limits, script governance, batch processing |
| Small business | Simpler configuration, fewer customizations, fewer users to test with |

## Related Documents

- [NetSuite Configuration](netsuite-configuration.md)
- [Problem Classification](problem-classification.md)
- [Customer Interview Framework](customer-interview-framework.md)

## Oracle References

- [Oracle NetSuite Help Center: Company Setup](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)