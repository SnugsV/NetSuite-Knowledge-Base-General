# SPS Commerce ASN and Shipment Notice Troubleshooting

## Quick Summary

ASN issues usually come from fulfillment status, carton data, pack structure, item identifiers, quantities, carrier/tracking data, ship dates, routing, or partner-specific shipment requirements.

## Public-Safe Boundary

Keep examples generic. Do not publish partner names tied to private requirements, shipment IDs, tracking numbers, carton labels, SSCC values, item SKUs, order numbers, logs, screenshots, or warehouse procedures.

## First Questions to Ask

1. Is the ASN missing, rejected, late, duplicated, or mismatched?
2. Was the related NetSuite fulfillment shipped?
3. Are carton, pallet, package, or tracking details required?
4. Are quantities shipped different from quantities ordered or acknowledged?
5. Are carrier, service, routing, ship date, or delivery date values required?
6. Did packing or shipment data change after ASN generation?

## Diagnostic Layers

### Layer 1: Fulfillment State

Check:

- Sales order status
- Item Fulfillment status
- Picked, packed, shipped quantities
- Partial fulfillment
- Closed or backordered lines
- Shipment date

### Layer 2: Pack and Carton Structure

Check:

- Carton count
- Carton contents
- Pallet or hierarchy requirements
- SSCC or carton identifiers if used
- Multi-carton and mixed-carton logic
- Package weights and dimensions if required

### Layer 3: Item and Quantity Mapping

Check:

- Partner item identifiers
- UPC, vendor item, customer item, or SKU mapping
- UOM
- Quantity shipped
- Case pack or inner pack values
- Substitutions or discontinued items

### Layer 4: Carrier and Tracking

Check:

- Carrier code
- Service level
- Tracking number
- Routing instructions
- SCAC or carrier identifier where required
- Ship-from and ship-to mapping

### Layer 5: Partner Validation

Check:

- Required ASN timing
- Required fields
- Allowed values
- Routing-guide requirements
- Label or pack-structure expectations
- Rejection messages

## Common Symptoms

### ASN Rejected

Likely causes:

- Missing carton or tracking data
- Invalid carrier code
- Item or UOM mismatch
- Quantity shipped differs from allowed quantity
- Required pack hierarchy missing
- Partner-specific field missing

### ASN Missing

Likely causes:

- Fulfillment not shipped
- Connector did not trigger
- Required shipment data missing
- Document stuck in portal or connector queue
- Fulfillment was created outside expected process

### ASN Quantity Mismatch

Likely causes:

- Partial fulfillment not represented correctly
- Backordered or closed lines
- UOM conversion issue
- Kit, case pack, or multi-carton mapping issue
- User edited fulfillment after ASN creation

### Tracking Is Wrong or Missing

Likely causes:

- Shipping integration did not write tracking back
- Tracking generated after ASN creation
- Multi-package tracking not mapped fully
- Carrier code mapping mismatch

## Safe Diagnostic Path

1. Identify the related sales order and fulfillment state without exposing details.
2. Confirm whether the ASN was generated, transmitted, accepted, or rejected.
3. Compare shipped quantities and package structure to partner requirements.
4. Validate item identifiers, UOM, carton data, carrier, and tracking.
5. Check whether the ASN should be corrected, replaced, or resent.
6. Avoid blind resends when the partner may already have accepted a prior ASN.

## AI Assistant Response Pattern

When a user asks about an ASN issue, the assistant should:

1. Ask whether the ASN is missing, rejected, late, duplicated, or mismatched.
2. Ask for generic fulfillment state, package/carton requirement, tracking status, and quantity context.
3. Diagnose fulfillment state, pack/carton structure, item/quantity mapping, carrier/tracking, and partner validation.
4. Keep partner-specific routing requirements and shipment identifiers private.

## Related Articles

- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
- [Connector or Portal Error Triage](sps-connector-portal-error-triage.md)
