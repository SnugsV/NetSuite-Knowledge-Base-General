# SPS Commerce Connector or Portal Error Triage

## Quick Summary

Connector and portal errors should be diagnosed by where the document is visible, what status it is in, whether validation failed, whether NetSuite accepted the update, and whether retry could create a duplicate.

## Public-Safe Boundary

Keep examples generic. Do not publish trading partner IDs, mailbox or VAN credentials, EDI control numbers, production logs, screenshots, document payloads, purchase order numbers, invoice numbers, or private support case details.

## First Questions to Ask

1. Where does the error appear: SPS portal, connector, NetSuite, partner response, VAN/mailbox, or email/support notification?
2. Which document type is involved?
3. Is the document inbound or outbound?
4. Is the document missing, rejected, stuck, duplicated, or partially processed?
5. Did NetSuite create or update the related record?
6. Did a retry already happen?
7. Did credentials, connector setup, maps, roles, scripts, workflows, or partner requirements change recently?

## Diagnostic Layers

### Layer 1: Error Location

Check:

- SPS portal status
- Connector queue or integration status
- NetSuite record status
- Partner acknowledgment or rejection
- VAN/mailbox transmission status
- Support notification or exception report

### Layer 2: Document State

Check:

- Received
- Validated
- Rejected
- Accepted
- Transmitted
- Acknowledged
- Waiting for user correction
- Waiting for partner or connector processing

### Layer 3: Validation and Mapping

Check:

- Required fields
- Item and UOM mapping
- Location and partner mapping
- Date and quantity rules
- Partner-specific requirements
- Duplicate control or duplicate reference behavior

### Layer 4: NetSuite Processing

Check:

- Related record exists
- Record is editable
- Role permissions
- Workflow or script validation
- Locked, closed, fulfilled, billed, or posted state
- Error returned from NetSuite to connector

### Layer 5: Retry and Recovery

Check:

- Whether the prior attempt partially succeeded
- Whether resend creates duplicate risk
- Whether correction should happen in NetSuite, SPS, or partner system
- Whether a document should be replaced, corrected, canceled, or resent
- Whether support escalation is needed

## Common Symptoms

### Portal Shows Error but NetSuite Looks Correct

Likely causes:

- Document failed outbound validation after NetSuite creation
- Partner-specific required field missing
- Connector transmitted a stale or incomplete version
- Acknowledgment/rejection not reflected in NetSuite

### NetSuite Missing Record but SPS Shows Document

Likely causes:

- Inbound document validation failed
- Partner/customer/item mapping issue
- Connector queue issue
- NetSuite role or script blocked creation
- Duplicate prevention stopped import

### Document Reprocessed Twice

Likely causes:

- Retry after timeout
- Duplicate document from partner
- Partial success not recognized
- Manual resend without checking document state
- NetSuite record copied or recreated

### Error Message Is Too Vague

Likely causes:

- Portal summarizes a map or validation failure
- Connector hides detailed NetSuite error
- Partner rejection code needs translation
- Required field is indirectly missing through mapping

## Safe Diagnostic Path

1. Identify the error location and document type.
2. Determine whether the document is visible in SPS, NetSuite, both, or neither.
3. Check document state and acknowledgment/rejection status.
4. Diagnose validation, mapping, and NetSuite processing layers.
5. Confirm whether retry is safe before resending.
6. Escalate credential, map, partner requirement, or production queue issues through the proper support path.

## AI Assistant Response Pattern

When a user asks about an SPS connector or portal error, the assistant should:

1. Ask where the error appears and which document type is involved.
2. Ask whether the document is visible in SPS, NetSuite, both, or neither.
3. Diagnose error location, document state, validation/mapping, NetSuite processing, and retry/recovery.
4. Warn against blind retry when partial success or duplicates are possible.
5. Keep logs, payloads, credentials, partner identifiers, and document numbers private.

## Related Articles

- [Advanced SPS Commerce Troubleshooting](advanced-troubleshooting.md)
- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
