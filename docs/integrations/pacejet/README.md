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
| - | **Estimated total time** | **75 min** | - |

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

## Related Documents

- [Pacejet Support Intelligence](../../../knowledge-engine/support-intelligence/pacejet-support.md)
- [Pacejet Customer Context](../../../knowledge-engine/customer-context/pacejet-context.md)
- [Pacejet Metadata](../../../knowledge-engine/customer-metadata/pacejet-metadata.md)
- [Pacejet Rate Troubleshooter](../../../knowledge-engine/ai-skills/pacejet-rate-troubleshooter.md)
- [Pacejet Label Troubleshooter](../../../knowledge-engine/ai-skills/pacejet-label-troubleshooter.md)

## Oracle References

- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)
