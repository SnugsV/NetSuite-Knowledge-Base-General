---
title: Pacejet Address Classification Diagnostics
module: Integrations
difficulty: Advanced
estimated_time: 25 minutes
status: Draft
last_reviewed:
---

# Pacejet Address Classification and Residential/Commercial Diagnostics

## Quick Summary

Shipping rates and services can change when an address is incomplete, invalid, classified as residential, classified as commercial, outside service area, or affected by surcharges. Diagnose address source and carrier interpretation before changing carrier rules.

## Public-Safe Boundary

Keep examples generic. Do not publish customer addresses, customer names, order numbers, tracking numbers, screenshots, logs, carrier account details, or private shipping rules.

## First Questions to Ask

1. Is the issue rate difference, missing service, address error, surcharge, label failure, or delivery classification?
2. Which address is used: customer default, transaction ship-to, fulfillment ship-to, or manually edited address?
3. Is the address residential, commercial, PO box, rural, military, international, or special delivery?
4. Did the address validate or normalize?
5. Does the issue affect one destination, one customer, one carrier, or all shipments?
6. Did the address change after rating or label generation?

## Diagnostic Layers

### Layer 1: Address Source

Check:

- Customer address book
- Sales order ship-to
- Item Fulfillment ship-to
- Manual override
- Integration/import-supplied address
- Warehouse or origin address

### Layer 2: Address Completeness

Check:

- Street
- City
- State/province
- ZIP/postal code
- Country
- Suite/unit/building details
- Contact and phone requirements for some services

### Layer 3: Carrier Classification

Check:

- Residential vs commercial
- PO box restrictions
- Remote or extended area
- Rural delivery area
- Military or diplomatic address
- International address requirements

### Layer 4: Rate and Service Effects

Check:

- Residential surcharge
- Delivery area surcharge
- Signature or special-service requirements
- Missing service availability
- Carrier-specific address response
- Address changes between rating and label generation

## Common Symptoms

### Rate Is Higher Than Expected

Likely causes:

- Residential surcharge
- Extended delivery area
- Wrong destination postal code
- Address normalized differently
- Carrier classified destination differently than expected

### Carrier Service Is Missing

Likely causes:

- Service not available to address
- PO box or military destination restriction
- International requirements missing
- Remote area or carrier coverage limitation
- Address incomplete or invalid

### Label Fails After Address Edit

Likely causes:

- Address changed after rating
- Required phone/contact field missing
- Carrier rejects normalized address
- Destination requires additional customs or service data

## Safe Diagnostic Path

1. Identify the exact address source used by the shipment.
2. Compare order, fulfillment, and customer address values.
3. Confirm address completeness.
4. Check residential/commercial and special destination classification.
5. Rerate after address correction before label generation.
6. Avoid publishing real address details in troubleshooting notes.

## AI Assistant Response Pattern

When a user asks why a Pacejet address changes rates or services, the assistant should:

1. Ask which address source is used and whether it changed after rating.
2. Ask whether residential/commercial, PO box, rural, military, or international context is involved.
3. Diagnose address source, completeness, carrier classification, and rate/service effects.
4. Avoid making carrier guarantee claims or exposing addresses.

## Related Articles

- [Advanced Pacejet Troubleshooting](advanced-troubleshooting.md)
- [Shipping Rate and Carrier Service Troubleshooting](pacejet-rate-carrier-service-troubleshooting.md)
- [Label Generation and Carrier Error Troubleshooting](pacejet-label-carrier-error-troubleshooting.md)
- [Core Shipping Workflow](shipping-workflow.md)
