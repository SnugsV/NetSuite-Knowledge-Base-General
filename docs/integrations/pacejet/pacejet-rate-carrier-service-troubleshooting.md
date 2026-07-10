---
title: Pacejet Shipping Rate and Carrier Service Troubleshooting
module: Integrations
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Pacejet Shipping Rate and Carrier Service Troubleshooting

## Quick Summary

When Pacejet does not show expected rates or carrier services, diagnose shipment data before changing rules. Rates depend on address, origin, carrier setup, service eligibility, package data, weights, dimensions, account settings, rules, and carrier responses.

## Public-Safe Boundary

Keep examples generic. Do not publish customer data, order numbers, tracking numbers, negotiated rates, carrier account numbers, API credentials, logs, screenshots, or private rate-shopping rules.

## First Questions to Ask

1. Are rates missing, too high, too low, slow to return, or missing only for one carrier/service?
2. Does the issue affect one shipment, one customer, one destination, one warehouse, one item type, or all shipments?
3. Which carriers and services were expected?
4. Are package weight, dimensions, number of packages, and origin/destination complete?
5. Did carrier credentials, services, rules, warehouses, item data, or Pacejet configuration change recently?
6. Is the issue in NetSuite, Pacejet, or a carrier response?

## Diagnostic Layers

### Layer 1: Shipment Data

Check:

- Ship-to address
- Origin location or warehouse
- Package count
- Weight and dimensions
- Residential/commercial indicator
- Shipment date
- Hazardous, international, oversized, or special-service indicators

### Layer 2: Carrier and Service Setup

Check:

- Carrier enabled in Pacejet
- Carrier account active
- Service level enabled
- Account supports the requested destination and package type
- Credentials or meter/account setup still valid
- Test vs production environment assumptions

### Layer 3: Package Eligibility

Check:

- Weight limits
- Dimensional limits
- Oversize rules
- Package type
- Domestic vs international service support
- PO box, military, rural, or special delivery constraints

### Layer 4: Rate Shopping Rules

Check:

- Preferred carrier rules
- Lowest-cost or fastest-service logic
- Customer-specific or destination-specific rules
- Warehouse or location rules
- Excluded services
- Fallback behavior when no rule matches

### Layer 5: Carrier Response

Check:

- Carrier timeout
- Authentication or account error
- Invalid service request
- Invalid address or postal code
- Service not available for destination
- Missing customs or special service data

## Common Symptoms

### No Rates Returned

Likely causes:

- Missing address, origin, weight, or dimensions
- Carrier credentials or account issue
- No eligible service for the destination or package
- Carrier timeout or outage
- Rule excludes all services

### One Carrier Is Missing

Likely causes:

- Carrier disabled
- Account not active
- Service not enabled
- Carrier does not support the shipment characteristics
- Carrier-specific credentials or API issue

### Rate Looks Too High

Likely causes:

- Wrong package weight or dimensions
- Residential surcharge
- Oversize or dimensional weight
- Wrong service level
- Wrong origin or destination
- Negotiated rate not applied or not available

### Wrong Service Was Selected Automatically

Likely causes:

- Rule priority
- Tie-breaking behavior
- Service exclusion
- Customer or destination override
- Package is ineligible for the expected service

## Safe Diagnostic Path

1. Start with one affected shipment.
2. Compare against one known-good shipment.
3. Confirm shipment address, origin, weight, dimensions, and package count.
4. Confirm carrier and service setup.
5. Check package eligibility and special service requirements.
6. Review rate-shopping rules and carrier responses.
7. Avoid changing carrier rules broadly until the failing layer is clear.

## AI Assistant Response Pattern

When a user asks why Pacejet rates are missing or unexpected, the assistant should:

1. Ask whether all rates are missing or only one carrier/service is missing.
2. Ask for generic shipment context: destination type, package count, weight/dimensions, origin, and expected service.
3. Diagnose shipment data, carrier setup, package eligibility, rules, and carrier response layers.
4. Recommend comparing one failing shipment to one known-good shipment.
5. Avoid exposing negotiated rates or carrier account details.

## Related Articles

- [Advanced Pacejet Troubleshooting](advanced-troubleshooting.md)
- [Rate Shopping](rate-shopping.md)
- [Carrier Integrations](carrier-integrations.md)
- [Packing, Weights, Dimensions, and Package Building](pacejet-packing-weight-dimension-diagnostics.md)
- [Address Classification Diagnostics](pacejet-address-classification-diagnostics.md)
