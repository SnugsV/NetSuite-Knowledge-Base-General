# SPS Commerce NetSuite Data Mapping Diagnostics

## Quick Summary

Many SPS Commerce issues are mapping issues. Partner identifiers, item codes, UPCs, UOM, locations, ship-to values, carrier codes, charges, and NetSuite fields must align across systems before documents can flow cleanly.

## Public-Safe Boundary

Keep examples generic. Do not publish partner names tied to private requirements, item catalogs, UPCs, customer item numbers, location codes, EDI maps, custom field IDs, logs, screenshots, or private trading partner requirements.

## First Questions to Ask

1. What data value is missing, wrong, rejected, or transformed unexpectedly?
2. Which systems disagree: NetSuite, SPS, trading partner, carrier, warehouse, or accounting?
3. Is the mapping issue tied to one partner, one item, one location, one document type, or all documents?
4. Did item, customer, location, UOM, carrier, price, or custom field setup change recently?
5. Is the affected document inbound or outbound?
6. Is the error validation-related, business-rule-related, or NetSuite-record-related?

## Diagnostic Layers

### Layer 1: Trading Partner Mapping

Check:

- Partner/customer identity
- Ship-to and bill-to identifiers
- Department, store, location, or distribution center codes
- Partner-specific required values
- Duplicate or inactive partner records

### Layer 2: Item Mapping

Check:

- Internal item
- Partner item number
- UPC/GTIN
- Vendor item number
- Customer item number
- Case pack, inner pack, or unit quantity
- Kit, assembly, matrix, or substitution behavior

### Layer 3: Unit of Measure Mapping

Check:

- Each, case, pack, pallet, carton, or other UOM
- Conversion rates
- Ordered vs shipped vs invoiced UOM
- Partner-required UOM codes
- NetSuite item UOM setup

### Layer 4: Location and Address Mapping

Check:

- Ship-from location
- Ship-to location
- Warehouse
- Store/DC code
- Address normalization
- Location-specific partner requirements

### Layer 5: Carrier and Shipment Mapping

Check:

- Carrier code
- Service level
- SCAC or carrier identifier where required
- Tracking number
- Package/carton data
- Routing instruction mapping

### Layer 6: Financial Mapping

Check:

- Price
- Discounts
- Allowances
- Freight
- Handling
- Tax
- Terms
- Charge codes

## Common Symptoms

### Item Rejected

Likely causes:

- Partner item number missing
- UPC mismatch
- UOM mismatch
- Inactive or duplicate item
- Kit or substitute item not mapped

### Location Rejected

Likely causes:

- Store/DC code missing
- Ship-to mapping mismatch
- Location inactive or renamed
- Partner expects a different identifier than NetSuite uses

### Carrier Code Rejected

Likely causes:

- Carrier/service mapping missing
- SCAC or code mismatch
- Routing guide requirement
- Shipping integration sent a different carrier value than SPS map expects

### Price or Charge Rejected

Likely causes:

- Contract price mismatch
- Allowance or charge code missing
- Freight mapping mismatch
- Tax or rounding difference
- Partner-specific tolerance rule

## Safe Diagnostic Path

1. Identify the exact value that failed without exposing private codes.
2. Identify source system and destination system.
3. Confirm whether the issue is partner, item, UOM, location, carrier, shipment, or financial mapping.
4. Compare one failing example to one known-good example.
5. Check whether the value changed recently.
6. Update mapping only through the approved internal process.
7. Document mapping ownership privately.

## AI Assistant Response Pattern

When a user asks about SPS mapping, the assistant should:

1. Ask what value is wrong and which systems disagree.
2. Ask whether the issue is partner, item, UOM, location, carrier, shipment, or financial mapping.
3. Diagnose by mapping layer and compare failing vs known-good examples.
4. Avoid publishing private map values, partner requirements, or item catalog data.

## Related Articles

- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [Purchase Order Acknowledgment and Change Order Diagnostics](sps-po-acknowledgment-change-order-diagnostics.md)
- [ASN and Shipment Notice Troubleshooting](sps-asn-shipment-notice-troubleshooting.md)
- [Invoice and 810 Mismatch Diagnostics](sps-invoice-810-mismatch-diagnostics.md)
