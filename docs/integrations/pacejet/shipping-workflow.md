---
title: Core Shipping Workflow
module: Integrations
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Core Shipping Workflow

## Quick Summary

The core shipping workflow connects NetSuite Item Fulfillment to Pacejet for rate shopping, label generation, and tracking updates. Understanding this flow is essential for troubleshooting and configuration.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## The End-to-End Workflow

### Step 1: Fulfillment Created

A sales order is fulfilled in NetSuite, creating an Item Fulfillment record. Key data passed to Pacejet includes:

- Ship-to address
- Item weights and quantities
- Inventory location (origin)
- Package dimensions
- Shipping preferences (carrier, service)

### Step 2: Shipment Sent to Pacejet

From the Item Fulfillment, the user clicks the Pacejet ship button (or automation triggers the shipment). SuiteScript collects fulfillment data and sends a POST request to the Pacejet API.

### Step 3: Rate Shopping

Pacejet queries all enabled carriers for rates based on the shipment data. Rates are returned sorted by cost, transit time, or a custom ruleset.

### Step 4: Carrier Selection

The carrier can be selected:
- **Manually** — User picks from available rates in the Pacejet UI
- **Automatically** — Rules select the lowest cost, fastest, or preferred carrier
- **By trading partner** — Customer-specific carrier agreements override defaults

### Step 5: Label Generation

Once the carrier is selected, Pacejet generates the shipping label. For standard carriers, Pacejet generates the label. For custom labels, the label connector generates from a BarTender template.

### Step 6: Tracking Returned to NetSuite

Pacejet sends the tracking number and shipment confirmation back to NetSuite through the connector. The Item Fulfillment is updated with:
- Tracking number
- Carrier name
- Service level
- Shipment cost

### Step 7: Post-Shipment

The fulfillment is complete. NetSuite can generate the invoice. The customer can be notified with tracking information.

## Automation Options

| Automation Type | Description |
|---|---|
| **Auto-ship** | Fulfillments are automatically shipped through Pacejet without user interaction |
| **Rules-based carrier selection** | Carrier and service selected by rules (lowest cost, fastest, preferred) |
| **Batch shipping** | Multiple fulfillments shipped in a single batch process |
| **Scheduled shipping** | Shipments processed on a schedule (e.g., hourly, end of day) |

## Business Example

A distributor fulfills 200 orders per day:

1. Warehouse team picks and packs orders in NetSuite
2. Item Fulfillments are created throughout the day
3. Auto-ship rule triggers Pacejet for each fulfillment
4. Rate shopping selects the cheapest carrier for each package
5. Labels generate automatically on the warehouse printer
6. Tracking numbers flow back to NetSuite
7. Customers receive shipment notifications via NetSuite

## Related Articles

- [What Is Pacejet?](what-is-pacejet.md)
- [Rate Shopping](rate-shopping.md)
- [Label Generation](label-generation.md)
- [Sales: Order Fulfillment](../sales/order-fulfillment.md)

## Oracle References

- [Pacejet Knowledge Base: Shipping Workflow](https://pacejet.help.descartesservices.com/)