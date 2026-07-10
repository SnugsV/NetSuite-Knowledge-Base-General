# SPS Commerce Purchase Order Acknowledgment and Change Order Diagnostics

## Quick Summary

Purchase order issues usually involve inbound PO data, acknowledgment status, accepted quantities, dates, item mapping, order changes, or NetSuite sales order state. Diagnose the PO lifecycle before editing orders or resending acknowledgments.

## Public-Safe Boundary

Keep examples generic. Do not publish partner names tied to private requirements, PO numbers, customer names, item SKUs, pricing, delivery dates, map details, logs, screenshots, or private operating procedures.

## First Questions to Ask

1. Is the issue with the inbound PO, PO acknowledgment, or PO change?
2. Is the expected action accept, reject, partially accept, change quantity, change date, cancel, or update an order?
3. Is the related NetSuite sales order created and in the expected status?
4. Are item, UOM, price, ship date, cancel date, or location values mismatched?
5. Did the partner send a change after the order was fulfilled, billed, or closed?
6. Is the issue rejected by SPS, the partner, or NetSuite?

## Diagnostic Layers

### Layer 1: Inbound Purchase Order

Check:

- PO received
- Trading partner identified
- Ship-to and bill-to mapped
- Items mapped
- Quantities and UOM mapped
- Dates mapped
- NetSuite sales order created or updated

### Layer 2: Acknowledgment Intent

Check:

- Accepted, rejected, partially accepted, or changed
- Backordered quantity
- Promise date or ship date
- Substitute item logic if applicable
- Partner-specific acknowledgment requirements

### Layer 3: Change Order Handling

Check:

- Change type
- Quantity change
- Date change
- Cancellation
- Price or item change
- Whether NetSuite order state allows update
- Whether fulfillment or invoice already exists

### Layer 4: Validation and Partner Rules

Check:

- Required acknowledgment fields
- Allowed status codes
- Date format and allowed date windows
- Item and UOM requirements
- Partner-specific tolerance or compliance rules

## Common Symptoms

### PO Did Not Create a Sales Order

Likely causes:

- Trading partner mapping missing
- Customer or ship-to mapping issue
- Item or UOM mapping failure
- Required field missing
- Duplicate PO handling
- Connector or portal exception

### Acknowledgment Rejected

Likely causes:

- Missing required status or date
- Quantity mismatch
- Invalid item reference
- Partner rule violation
- Sales order state changed after acknowledgment generation

### Change Order Cannot Apply

Likely causes:

- Sales order already fulfilled, billed, closed, or locked
- Change conflicts with available quantity
- Item or UOM mapping mismatch
- Partner sent change after internal cutoff
- Workflow or script blocks update

### Partner Says Order Was Not Acknowledged

Likely causes:

- Acknowledgment generated but not transmitted
- Acknowledgment rejected downstream
- Document stuck in portal/connector queue
- Wrong partner document reference
- Duplicate or replacement document confusion

## Safe Diagnostic Path

1. Identify whether the issue is inbound PO, acknowledgment, or change order.
2. Confirm document visibility in SPS and NetSuite.
3. Check related NetSuite sales order state.
4. Validate item, UOM, quantity, dates, and partner requirements.
5. Check acknowledgment or change response status.
6. Avoid resending until duplicate or partial-success risk is understood.

## AI Assistant Response Pattern

When a user asks about SPS PO acknowledgments or changes, the assistant should:

1. Ask whether the issue is 850, 855, or 860/change-related.
2. Ask what the expected outcome is: accept, reject, partial, date change, quantity change, or cancel.
3. Diagnose inbound mapping, acknowledgment intent, change-order handling, validation, and NetSuite order state.
4. Avoid exposing partner-specific compliance rules or PO data.

## Related Articles

- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
- [Connector or Portal Error Triage](sps-connector-portal-error-triage.md)
