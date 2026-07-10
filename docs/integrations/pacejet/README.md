# Pacejet Shipping Integration

This module covers Pacejet, a multi-carrier shipping platform integrated with NetSuite. Pacejet provides rate shopping, label generation, tracking, and shipping automation across dozens of carriers.

## Learning Path

| Step | Article | Est. Time | Topic |
|---|---|---|---|
| 1 | [What Is Pacejet?](what-is-pacejet.md) | 10 min | Platform overview, shipping lifecycle |
| 2 | [Setup and Configuration](setup-and-configuration.md) | 15 min | NetSuite bundle, carrier activation, configuration |
| 3 | [Core Shipping Workflow](shipping-workflow.md) | 15 min | Fulfillment -> Rate -> Label -> Track |
| 4 | [Rate Shopping](rate-shopping.md) | 10 min | Multi-carrier rate comparison |
| 5 | [Label Generation](label-generation.md) | 10 min | Standard and custom labels |
| 6 | [Carrier Integrations](carrier-integrations.md) | 15 min | Supported carriers and configuration |
| 7 | [Advanced Troubleshooting](advanced-troubleshooting.md) | 20 min | Rates, packages, labels, fulfillment status, addresses, tracking, voids, and reprints |
| - | **Estimated total time** | **95 min** | - |

## Prerequisites

- [Sales module](../../sales/README.md) - fulfillment is the starting point
- [Inventory module](../../inventory/README.md) - item weight and dimensions

## How Pacejet Connects

| Module | Connection |
|---|---|
| **Sales** | Sales order -> fulfillment -> shipment |
| **Inventory** | Item weight, dimensions, location data |
| **Fulfillment** | Core integration point |
| **Accounting** | Shipping costs, freight charges |
| **Purchasing** | Drop-ship fulfillment scenarios |

## Advanced Troubleshooting Topics

- [Shipping Rate and Carrier Service Troubleshooting](pacejet-rate-carrier-service-troubleshooting.md)
- [Packing, Weights, Dimensions, and Package Building](pacejet-packing-weight-dimension-diagnostics.md)
- [Label Generation and Carrier Error Troubleshooting](pacejet-label-carrier-error-troubleshooting.md)
- [NetSuite Fulfillment and Shipment Status Flow](pacejet-fulfillment-shipment-status-flow.md)
- [Address Classification and Residential/Commercial Diagnostics](pacejet-address-classification-diagnostics.md)
- [Tracking, Void, Reprint, and Post-Shipment Troubleshooting](pacejet-post-shipment-troubleshooting.md)

## Related Documents

- [Pacejet Support Intelligence](../../../knowledge-engine/support-intelligence/pacejet-support.md)
- [Pacejet Customer Context](../../../knowledge-engine/customer-context/pacejet-context.md)
- [Pacejet Metadata](../../../knowledge-engine/customer-metadata/pacejet-metadata.md)
- [Pacejet Rate Troubleshooter](../../../knowledge-engine/ai-skills/pacejet-rate-troubleshooter.md)
- [Pacejet Label Troubleshooter](../../../knowledge-engine/ai-skills/pacejet-label-troubleshooter.md)

## Public References

- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)
