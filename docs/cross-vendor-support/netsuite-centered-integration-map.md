# NetSuite-Centered Integration Map

## Quick Summary

When Avalara, Pacejet, or SPS Commerce has an issue, start by locating the NetSuite record, transaction status, and data layer involved. NetSuite is often the source of the data each connected system evaluates.

## Public-Safe Boundary

Keep examples generic. Do not publish customer names, item names, transaction numbers, custom fields, scripts, workflows, credentials, screenshots, production logs, pricing, EDI identifiers, tracking numbers, or private SOPs.

## High-Level Flow

```text
Customer / Item / Location / Address setup
        |
        v
Sales order, fulfillment, invoice, credit, or related transaction
        |
        +--> Avalara: tax calculation, exemption, jurisdiction, taxability
        |
        +--> Pacejet: rates, carrier service, label, tracking
        |
        +--> SPS Commerce: EDI purchase order, acknowledgment, ASN, invoice
        |
        v
NetSuite status, fields, logs, workflows, scripts, and connector writeback
```

## NetSuite Data That Commonly Matters

### Customer

Used by:

- Avalara for buyer, exemption, address, and tax context.
- SPS Commerce for trading partner/customer mapping.
- Pacejet indirectly through ship-to address and fulfillment context.

Common issues:

- Wrong customer selected.
- Parent/child relationship differs from expected.
- Customer mapping or external identifier is missing.
- Address book differs from transaction address.

### Item

Used by:

- Avalara for item taxability and product classification.
- Pacejet for weight, dimensions, quantity, and package logic.
- SPS Commerce for item identifiers, UPCs, partner SKUs, UOM, and case packs.

Common issues:

- Missing item weight or dimensions.
- Wrong product tax category or item tax code.
- Partner item mapping missing.
- UOM or case pack mismatch.

### Address

Used by:

- Avalara for jurisdiction and tax calculation.
- Pacejet for carrier service availability and residential/commercial classification.
- SPS Commerce for ship-to, ship-from, bill-to, store/DC, and partner routing requirements.

Common issues:

- Transaction address differs from customer default.
- Address changed after calculation, rating, or document generation.
- Postal code maps to an unexpected jurisdiction or service area.
- Ship-to location code is missing or mismatched.

### Sales Order

Used by:

- SPS Commerce as the result of an inbound PO and the basis for acknowledgments.
- Pacejet as the upstream order that produces fulfillment.
- Avalara when tax is calculated before invoicing depending on workflow.

Common issues:

- Order status blocks downstream action.
- PO change conflicts with fulfillment or billing state.
- Item, quantity, date, or price differs from partner expectation.

### Item Fulfillment

Used by:

- Pacejet for rating, labels, carrier selection, tracking, and shipment updates.
- SPS Commerce for ASN/shipment notice data.
- NetSuite billing workflows after shipment.

Common issues:

- Fulfillment not in expected status.
- Package or tracking data missing.
- Pacejet shipped but NetSuite writeback failed.
- ASN generated before package/tracking data was complete.

### Invoice and Credit Memo

Used by:

- Avalara for tax calculation, credits, returns, and filing readiness.
- SPS Commerce for invoice/810 documents and mismatch resolution.
- NetSuite accounting for posting, payment, and reconciliation.

Common issues:

- Invoice does not match PO, shipment, or ASN.
- Tax changed between order and invoice.
- Credit memo does not reference original invoice as expected.
- Posting period or transaction status blocks correction.

## Diagnostic Rule

Before deciding which vendor owns the issue, identify:

1. The NetSuite record type.
2. The current record status.
3. The connected system involved.
4. The data element being evaluated.
5. Whether the connected system received the expected data.
6. Whether the connected system returned a result, rejection, label, tax amount, tracking number, or error.
7. Whether NetSuite accepted the writeback or update.

## Common Cross-System Patterns

### Tax and Shipping Both Look Wrong

Check:

- Transaction ship-to address.
- Customer address vs transaction address.
- Item data and quantity.
- Location/origin.
- Whether address changed after tax/rate calculation.

### Shipment and ASN Do Not Match

Check:

- Item Fulfillment status.
- Package count, carton data, tracking, and carrier code.
- Whether Pacejet tracking wrote back before SPS generated the ASN.
- Whether partner item/UOM mapping matches shipped quantities.

### Invoice and Tax or EDI Do Not Match

Check:

- Invoice created-from relationship.
- Sales order, fulfillment, ASN, and invoice quantity alignment.
- Tax recalculation timing.
- Freight, discounts, allowances, and charges.
- Partner invoice requirements.

## AI Assistant Response Pattern

When a user presents a cross-vendor issue, the assistant should:

1. Ask which NetSuite transaction or record is involved.
2. Ask which connected system shows the symptom.
3. Identify whether the issue is data sent, vendor processing, vendor response, or NetSuite writeback.
4. Check record status, address, item, customer, role, workflow, script, and connector timing.
5. Avoid declaring a vendor cause until the system boundary is clear.

## Related Articles

- [Cross-Vendor Incident Intake Checklist](integration-incident-intake-checklist.md)
- [Advanced NetSuite Troubleshooting](../advanced-troubleshooting/README.md)
- [Advanced Avalara Troubleshooting](../../ecosystem/avalara/ADVANCED_TROUBLESHOOTING.md)
- [Advanced Pacejet Troubleshooting](../integrations/pacejet/advanced-troubleshooting.md)
- [Advanced SPS Commerce Troubleshooting](../integrations/sps-commerce/advanced-troubleshooting.md)
