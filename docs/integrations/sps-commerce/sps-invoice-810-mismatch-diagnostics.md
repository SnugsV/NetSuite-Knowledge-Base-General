# SPS Commerce Invoice and 810 Mismatch Diagnostics

## Quick Summary

Invoice/810 rejections often come from mismatches against the purchase order, acknowledgment, shipment, receipt, pricing, allowances, charges, taxes, quantities, or partner-specific invoice rules.

## Public-Safe Boundary

Keep examples generic. Do not publish partner names tied to private requirements, invoice numbers, PO numbers, item SKUs, pricing, allowances, chargeback details, logs, screenshots, or private billing procedures.

## First Questions to Ask

1. Is the invoice missing, rejected, duplicated, late, or mismatched?
2. Is the invoice related to the correct PO and shipment?
3. Are quantities, prices, taxes, freight, allowances, and charges aligned with partner expectations?
4. Did the order change after acknowledgment or shipment?
5. Is the NetSuite invoice generated from the correct fulfillment/order state?
6. Is the rejection from SPS, the partner, or NetSuite?

## Diagnostic Layers

### Layer 1: Invoice Identity

Check:

- Related PO
- Related sales order
- Related fulfillment/ASN
- Invoice number or document reference
- Trading partner
- Duplicate invoice behavior

### Layer 2: Quantity and Item Match

Check:

- Ordered quantity
- Acknowledged quantity
- Shipped quantity
- Invoiced quantity
- Backorders, cancellations, or substitutions
- UOM and case pack values

### Layer 3: Price, Allowance, Charge, and Tax

Check:

- Unit price
- Extended price
- Freight
- Handling
- Discounts
- Allowances
- Tax
- Rounding rules

### Layer 4: Partner Invoice Rules

Check:

- Required fields
- Allowed invoice timing
- Invoice per PO, shipment, or fulfillment expectation
- Required references
- Allowed charge codes
- Payment terms or remittance requirements

### Layer 5: NetSuite and Connector State

Check:

- Invoice status
- Created-from relationship
- Posting period
- Tax and freight fields
- Workflow or script changes
- Connector transmission and acknowledgment status

## Common Symptoms

### Invoice Rejected for Quantity Mismatch

Likely causes:

- Invoiced quantity differs from shipped or accepted quantity
- Partial shipment not represented correctly
- UOM conversion issue
- Backorder or cancellation not reflected
- Item substitution not handled as expected

### Invoice Rejected for Price Mismatch

Likely causes:

- NetSuite price differs from PO price
- Discount or allowance missing
- Freight or handling charge mapped incorrectly
- Rounding difference
- Partner expects contract or transmitted price

### Invoice Missing Required Reference

Likely causes:

- PO reference missing
- Shipment/ASN reference missing
- Partner location or department reference missing
- Remittance or terms data missing
- Connector mapping issue

### Duplicate Invoice

Likely causes:

- Retry after timeout
- Invoice copied or regenerated
- Partner already accepted earlier document
- Connector did not detect prior transmission

## Safe Diagnostic Path

1. Identify invoice, related PO, related fulfillment, and document status without exposing details.
2. Compare ordered, acknowledged, shipped, and invoiced quantities.
3. Compare price, freight, taxes, allowances, and charges.
4. Check required partner references and invoice timing.
5. Check connector acknowledgment and retry history.
6. Determine whether correction, credit/rebill, or resend is appropriate through the proper business process.

## AI Assistant Response Pattern

When a user asks about SPS invoice rejection, the assistant should:

1. Ask whether the rejection is quantity, price, reference, timing, tax/freight, duplicate, or format related.
2. Ask whether the invoice matches the PO, ASN/fulfillment, and partner rules.
3. Diagnose identity, quantity/item match, price/charge/tax, partner invoice rules, and NetSuite connector state.
4. Avoid exposing pricing or partner-specific rules.

## Related Articles

- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [ASN and Shipment Notice Troubleshooting](sps-asn-shipment-notice-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
