---
title: Rate Shopping
module: Integrations
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Rate Shopping

## Quick Summary

Rate shopping is the process of comparing shipping costs across multiple carriers to select the best option. Pacejet queries enabled carriers in real time and returns rates sorted by cost, transit time, or custom rules.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Without rate shopping, a company uses one carrier for all shipments — often paying more than necessary. With rate shopping, each shipment is evaluated across all available carriers, and the best option is selected automatically or presented to the user.

## How Rate Shopping Works

```
Shipment data sent to Pacejet
       ↓
Pacejet queries each enabled carrier
       ↓
Each carrier returns rate (cost, transit time, service level)
       ↓
Rates displayed sorted by cost or time
       ↓
Carrier selected (auto or manual)
       ↓
Label generated with selected carrier
```

## Carrier Selection Methods

| Method | Description | Best For |
|---|---|---|
| **Lowest Cost** | Automatically selects the cheapest carrier | Cost-conscious shippers |
| **Fastest** | Selects the carrier with shortest transit time | Time-sensitive shipments |
| **Trading Partner** | Uses customer-specific carrier agreement | Contract customers |
| **Rule-based** | Custom rules (zone, weight, value) | Complex shipping requirements |
| **Manual** | User reviews rates and selects | Low-volume or exception handling |

## Rate Shopping Configuration

| Configuration | Impact |
|---|---|
| **Carriers enabled** | Only enabled carriers are queried |
| **Service levels** | Ground, express, overnight, etc. |
| **Contract rates** | Negotiated rates vs. published rates |
| **Surcharges** | Fuel, residential delivery, etc. |

## Related Articles

- [Core Shipping Workflow](shipping-workflow.md)
- [Carrier Integrations](carrier-integrations.md)
- [Pacejet Rate Troubleshooter](../../../knowledge-engine/ai-skills/pacejet-rate-troubleshooter.md)

## Oracle References

- [Pacejet Knowledge Base: Rate Shopping](https://pacejet.help.descartesservices.com/)