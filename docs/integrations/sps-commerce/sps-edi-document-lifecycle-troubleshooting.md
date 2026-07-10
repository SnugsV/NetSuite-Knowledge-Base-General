# SPS Commerce EDI Document Lifecycle Troubleshooting

## Quick Summary

EDI issues should be diagnosed by document type, direction, trading partner, lifecycle state, acknowledgment, mapping, and NetSuite transaction status. Do not treat every EDI issue as a connector failure.

## Public-Safe Boundary

Keep examples generic. Do not publish partner names tied to private requirements, PO numbers, document control numbers, invoice numbers, ASN IDs, trading partner IDs, map details, production logs, screenshots, or credentials.

## First Questions to Ask

1. Which document type is involved?
2. Is the document inbound or outbound?
3. Is the issue missing, rejected, duplicated, late, stuck, mismatched, or incorrectly mapped?
4. Is the document visible in SPS, NetSuite, both, or neither?
5. Did an acknowledgment or error return?
6. Which NetSuite record should the document create, update, or reference?
7. Did partner requirements, maps, item data, locations, UOM, or connector settings change recently?

## Common Document Types

Common EDI retail document flows include:

- Purchase order / 850
- Purchase order acknowledgment / 855
- Purchase order change / 860
- Advance ship notice / 856
- Invoice / 810
- Functional acknowledgment / 997 or equivalent acknowledgment flow
- Inventory, item, or catalog documents depending on partner setup

## Diagnostic Layers

### Layer 1: Document Identity

Check:

- EDI document type
- Direction
- Trading partner
- Document identifier
- Related NetSuite record
- Expected document sequence

### Layer 2: Transport and Visibility

Check:

- Document received or sent by SPS
- Connector, mailbox, VAN, or portal visibility
- Duplicate or missing transmission
- Timestamp and processing order
- Environment or partner endpoint

### Layer 3: Validation

Check:

- Required segments or fields
- Trading partner-specific requirements
- Item, location, UOM, carrier, and address values
- Date and quantity rules
- Duplicate document control

### Layer 4: NetSuite Transaction State

Check:

- Sales order status
- Fulfillment status
- Invoice status
- Item availability
- Partner/customer mapping
- Locked, closed, billed, shipped, or changed records

### Layer 5: Acknowledgment and Error Handling

Check:

- Whether an acknowledgment was expected
- Whether the document was accepted, accepted with errors, or rejected
- Whether retry is safe
- Whether partner correction or internal correction is required

## Common Symptoms

### Document Missing

Likely causes:

- Partner did not send it
- Document received by SPS but not processed
- Connector sync failed
- Map rejected the document
- Document is in a portal queue or exception state
- NetSuite record could not be created or updated

### Document Rejected

Likely causes:

- Required value missing
- Invalid item, UOM, location, or partner code
- Quantity or date mismatch
- Trading partner rule violation
- NetSuite transaction state does not allow update

### Duplicate Document

Likely causes:

- Partner resent document
- Retry after timeout
- Duplicate control number behavior
- NetSuite import or connector reprocessed the same message
- Original document partially succeeded

### Document Stuck

Likely causes:

- Validation exception
- Mapping error
- Connector queue issue
- Related NetSuite record missing or locked
- User action required in portal or NetSuite

## Safe Diagnostic Path

1. Identify document type, direction, partner, and expected NetSuite record.
2. Confirm visibility in SPS and NetSuite.
3. Check document status and acknowledgment/error state.
4. Validate required fields and trading partner requirements.
5. Check NetSuite record state and mapping.
6. Determine whether retry is safe before resending.
7. Document the resolution without exposing private document data.

## AI Assistant Response Pattern

When a user asks why an EDI document failed, the assistant should:

1. Ask document type and direction.
2. Ask whether the document is visible in SPS, NetSuite, both, or neither.
3. Diagnose identity, transport, validation, NetSuite state, and acknowledgment layers.
4. Warn against blind resend when partial success or duplicate risk exists.
5. Keep document and partner details private.

## Related Articles

- [Advanced SPS Commerce Troubleshooting](advanced-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
- [Connector or Portal Error Triage](sps-connector-portal-error-triage.md)
