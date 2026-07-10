---
title: Advanced Pacejet Troubleshooting
module: Integrations
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Advanced Pacejet Troubleshooting

## Quick Summary

This section helps NetSuite users, administrators, shipping teams, consultants, and AI assistants diagnose advanced Pacejet issues across rating, carrier services, packing, labels, fulfillment status, addresses, tracking, voids, and post-shipment workflows.

## Learning Order

1. [Shipping Rate and Carrier Service Troubleshooting](pacejet-rate-carrier-service-troubleshooting.md) - Diagnose missing rates, unexpected rates, carrier/service availability, and rule selection.
2. [Packing, Weights, Dimensions, and Package Building](pacejet-packing-weight-dimension-diagnostics.md) - Diagnose package data, weight, dimension, cartonization, and multi-package issues.
3. [Label Generation and Carrier Error Troubleshooting](pacejet-label-carrier-error-troubleshooting.md) - Diagnose label creation failures, carrier messages, printer/output issues, and retry safety.
4. [NetSuite Fulfillment and Shipment Status Flow](pacejet-fulfillment-shipment-status-flow.md) - Diagnose Item Fulfillment status, shipment timing, tracking writeback, and transaction lifecycle issues.
5. [Address Classification and Residential/Commercial Diagnostics](pacejet-address-classification-diagnostics.md) - Diagnose ship-to address, residential/commercial, validation, and surcharge-related issues.
6. [Tracking, Void, Reprint, and Post-Shipment Troubleshooting](pacejet-post-shipment-troubleshooting.md) - Diagnose post-label changes, tracking, voids, reprints, returns, and reconciliation.

## What This Section Is For

Use this section when:

- Pacejet does not return expected rates.
- A carrier or service is missing.
- Package weight, dimensions, or carton count looks wrong.
- A label fails to generate.
- Tracking does not write back to NetSuite.
- An Item Fulfillment cannot be shipped, voided, reprinted, or updated.
- Residential/commercial classification or address validation affects rates.
- A post-shipment change creates uncertainty.

## Public-Safe Rule

Keep examples generic. Do not include customer names, order numbers, tracking numbers, carrier account numbers, negotiated rates, API credentials, production logs, screenshots, custom scripts, private shipping rules, warehouse procedures, or implementation-specific configuration.

## Source Notes

This section is based on existing repository Pacejet articles, public Pacejet/Descartes support references, and general NetSuite fulfillment and shipping-integration troubleshooting patterns. Implementation-specific behavior must be verified against the actual NetSuite account, Pacejet configuration, carrier setup, and warehouse process.

## Related Existing Articles

- [What Is Pacejet?](what-is-pacejet.md)
- [Core Shipping Workflow](shipping-workflow.md)
- [Rate Shopping](rate-shopping.md)
- [Label Generation](label-generation.md)
- [Carrier Integrations](carrier-integrations.md)
- [Setup and Configuration](setup-and-configuration.md)
