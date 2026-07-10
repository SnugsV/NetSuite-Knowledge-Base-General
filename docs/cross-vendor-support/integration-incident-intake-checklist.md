# Cross-Vendor Integration Incident Intake Checklist

## Quick Summary

A cross-vendor incident should be captured by symptom, system, NetSuite record, connected vendor, timing, data changed, error text, and safe evidence. Good intake prevents guessing and reduces duplicate fixes.

## Public-Safe Boundary

Do not collect or publish customer names, item names, transaction numbers, invoice numbers, tracking numbers, EDI identifiers, certificate documents, tax amounts, carrier account details, credentials, screenshots with private data, raw logs, scripts, workflows, or proprietary procedures.

## Intake Questions

### 1. What Happened?

Capture:

- Plain-language symptom.
- Expected result.
- Actual result.
- First date/time noticed.
- Whether the issue is ongoing or one-time.

Examples of safe phrasing:

- Tax did not calculate on one invoice.
- Shipping rate did not return for one fulfillment.
- ASN was rejected for one shipment.
- Integration error appeared after saving a transaction.

### 2. Which System Shows the Symptom?

Choose the first visible symptom:

- NetSuite
- Avalara
- Pacejet
- SPS Commerce
- Connector/middleware
- Carrier
- Trading partner portal
- User email or notification

### 3. Which NetSuite Record Is Involved?

Identify the record type without exposing record numbers:

- Customer
- Item
- Sales order
- Item Fulfillment
- Invoice
- Credit memo
- Return authorization
- Customer payment
- Purchase order
- Vendor bill
- Custom record
- Saved search
- Script or workflow

### 4. Which Vendor Workflow Is Involved?

Identify the connected workflow:

- Avalara tax calculation
- Avalara exemption or certificate logic
- Avalara returns/filing readiness
- Pacejet rate shopping
- Pacejet label generation
- Pacejet tracking or void/reprint
- SPS inbound PO
- SPS PO acknowledgment/change
- SPS ASN/shipment notice
- SPS invoice/810
- SPS connector or portal exception

### 5. What Changed Recently?

Ask about changes to:

- NetSuite role or permission
- Customer, address, item, location, or tax setup
- Workflow or SuiteScript
- Saved search or integration role
- Vendor connector setting
- Vendor release or monthly update
- Carrier, tax, or trading partner requirement
- Import, CSV, API, or manual process

### 6. What Evidence Exists?

Safe evidence can include:

- Sanitized error text
- System where error appears
- Record type and status
- Generic transaction type
- Timestamp
- Whether vendor received data
- Whether vendor returned a result
- Whether NetSuite writeback succeeded
- Comparison to one known-good example

Do not include raw production screenshots or logs until they are redacted.

## Layered Triage Path

1. Identify visible symptom.
2. Identify NetSuite record type and status.
3. Identify connected vendor workflow.
4. Determine whether the issue is data sent, vendor processing, vendor response, or NetSuite writeback.
5. Check recent changes.
6. Compare one affected example to one known-good example.
7. Decide whether the next step is NetSuite review, vendor review, connector review, or business-policy review.

## Vendor-Specific Shortcuts

### Avalara

Ask:

- Which transaction type?
- Which address was used?
- Is the customer expected to be taxable or exempt?
- Which item or charge type is involved?
- Did tax calculate, return zero, or return an error?

### Pacejet

Ask:

- Which Item Fulfillment status?
- Did rates return?
- Did a label or tracking number already exist?
- Are package weight/dimensions complete?
- Is the issue carrier/service, address, package, label, or writeback?

### SPS Commerce

Ask:

- Which EDI document type?
- Inbound or outbound?
- Visible in SPS, NetSuite, both, or neither?
- Accepted, rejected, stuck, duplicated, or missing?
- Which related NetSuite transaction should it create or update?

## AI Assistant Response Pattern

When a user provides a screenshot or partial description, the assistant should:

1. Restate the likely system boundary.
2. Ask for record type, connected vendor, and sanitized error text.
3. Ask whether data reached the vendor and whether NetSuite received a response.
4. Avoid asking for private identifiers or raw logs.
5. Use the relevant vendor article after the intake layer is clear.

## Related Articles

- [NetSuite-Centered Integration Map](netsuite-centered-integration-map.md)
- [Screenshot and Log Redaction Checklist](screenshot-log-redaction-checklist.md)
- [Advanced NetSuite Troubleshooting](../advanced-troubleshooting/README.md)
- [Advanced Avalara Troubleshooting](../../ecosystem/avalara/ADVANCED_TROUBLESHOOTING.md)
- [Advanced Pacejet Troubleshooting](../integrations/pacejet/advanced-troubleshooting.md)
- [Advanced SPS Commerce Troubleshooting](../integrations/sps-commerce/advanced-troubleshooting.md)
