---
title: What Is Pacejet?
module: Integrations
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# What Is Pacejet?

## Quick Summary

Pacejet is a multi-carrier shipping platform that integrates with NetSuite to provide rate shopping, label generation, tracking, and shipping automation. It connects NetSuite fulfillment to dozens of carrier APIs through a single integration point.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

Shipping is the final step in the Order-to-Cash lifecycle. Without a shipping integration, companies log into carrier websites individually, manually enter shipment data, print labels from different systems, and copy tracking numbers back to NetSuite. Pacejet eliminates this manual process.

## The Shipping Lifecycle

```text
Item Fulfillment created in NetSuite
       |
       v
Shipment data sent to Pacejet
       |
       v
Pacejet queries enabled carriers for rates
       |
       v
Carrier selected (auto or manual)
       |
       v
Label generated
       |
       v
Tracking number returned to NetSuite
       |
       v
Fulfillment updated with tracking
       |
       v
Customer notified
```

## Pacejet Components

| Component | Function |
|---|---|
| **Pacejet Shipping** | Core platform - rate shopping, label generation, carrier management |
| **Pacejet Connector** | NetSuite bundle - SuiteScript integration between NetSuite and Pacejet |
| **Advanced Shipping Data (ASD)** | Extended shipping fields on NetSuite records |
| **Pacejet Label Connector** | Custom label design and generation (BarTender integration) |
| **Pacejet API** | REST API for custom integrations |

## Why Companies Use Pacejet

| Reason | Benefit |
|---|---|
| **Multi-carrier rate shopping** | Compare rates across carriers automatically |
| **Single integration point** | One connection to Pacejet instead of dozens of carrier APIs |
| **Automated tracking** | Tracking numbers flow back to NetSuite automatically |
| **Label standardization** | Consistent label format regardless of carrier |
| **Shipping automation** | Rules-based carrier selection and service level |
| **International shipping** | Customs documentation, restricted party screening |

## Pacejet vs. Native NetSuite Shipping

| Dimension | Native NetSuite | NetSuite + Pacejet |
|---|---|---|
| **Carrier integration** | Limited built-in carriers | Dozens of carriers via Pacejet |
| **Rate shopping** | Per-carrier configuration | Multi-carrier comparison |
| **Label customization** | Standard carrier labels | Custom label via BarTender connector |
| **Automation** | Manual carrier selection | Rules-based carrier and service |
| **International** | Limited customs support | Customs docs, restricted party screening |

## Related Articles

- [Setup and Configuration](setup-and-configuration.md)
- [Shipping Workflow](shipping-workflow.md)
- [Rate Shopping](rate-shopping.md)
- [Carrier Integrations](carrier-integrations.md)
- [Sales: Order Fulfillment](../../sales/order-fulfillment.md)

## Oracle References

- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)
