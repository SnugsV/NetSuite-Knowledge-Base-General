# NetSuite Configuration

## Purpose

The NetSuite configuration — enabled features, installed bundles, and integrations — is the foundation of every support interaction. The same symptom can have different root causes depending on which features are enabled. Never assume features are active without verification.

## Essential Configuration Questions

| Question | Why It Matters |
|---|---|
| Which edition? (Standard, OneWorld) | OneWorld adds multi-subsidiary complexity. |
| Which ERP features are enabled? | Feature availability determines which modules are relevant. |
| Are Advanced features enabled? | Advanced Inventory, Manufacturing, WMS add significant complexity. |
| Which bundles are installed? | Bundles may add custom records, fields, or scripts. |
| What integrations are active? | E-commerce, bank feeds, EDI, shipping — all can introduce data errors. |
| When was the last NetSuite release update? | New releases may change feature behavior. |

## Feature Impact Table

| Feature | When Enabled | When Disabled |
|---|---|---|
| **Advanced Inventory** | Bins, lots, serials, matrix items, cycle counts available | Basic inventory management only |
| **Manufacturing** | BOMs, work orders, routings, WIP | Simple assembly via kit items only |
| **WMS** | Directed putaway, wave picking, RF scanning | Standard pick/pack/ship |
| **Multi-Location Inventory** | Location-level quantity and cost tracking | Single-location inventory |
| **Landed Cost** | Allocate freight/duty to inventory cost | All buying costs expensed |
| **OneWorld** | Multi-subsidiary, intercompany, multi-currency | Single-subsidiary, single-currency |
| **SuiteApprovals** | Approval workflows available | Manual approval only |
| **Advanced Receiving** | Inbound shipment tracking, ASN support | Standard item receipt |

## Integration Points

| Integration Type | Common Issues |
|---|---|
| **E-commerce** (Shopify, Magento, BigCommerce) | Order sync failures, inventory sync delays, pricing mismatches |
| **Bank Feeds** | Authentication expiry, transaction classification errors |
| **EDI** | Order format mismatches, partner configuration issues |
| **Shipping** (UPS, FedEx) | Rate calculation errors, label generation failures |
| **CRM** | Customer sync issues, duplicate records |
| **ERP Connectors** | Data mapping errors, field mismatch |

## Discovering Configuration

### When to Ask About Features

- Always ask about features related to the affected module
- If the customer reports an inventory issue, ask about Advanced Inventory
- If they report a purchasing issue, ask about SuiteApprovals
- If they mention a specific feature (bins, lots, serials), confirm it is enabled

### How to Verify Configuration

Ask the customer to navigate to:

```
Setup > Company > Enable Features
```

Request screenshots of the relevant feature tabs if needed.

### Common Configuration Pitfalls

| Pitfall | Why It Matters |
|---|---|
| Feature partially enabled | Some options may be enabled while related options are not |
| Feature enabled but not configured | Enabled does not mean configured — locations, bins, and items may not be set up |
| Feature enabled but permissions not assigned | Users cannot use a feature without the corresponding role permissions |
| Bundle installed but not configured | Bundles may have setup steps that were not completed |

## Related Documents

- [Company Profile](company-profile.md)
- [Customizations](customizations.md)
- [Metadata Collection](metadata-collection.md)

## Oracle References

- [Oracle NetSuite Help Center: Feature Enablement](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)