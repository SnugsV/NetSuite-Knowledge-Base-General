# Self-Service Before Escalation Guide

## Quick Summary

This guide helps frontline teams and power users check the safest, highest-value troubleshooting areas before escalating to a NetSuite administrator, vendor support, or technical owner.

The goal is not to bypass controls. The goal is to gather better context, resolve simple data/status issues, and narrow the likely system layer.

## Public-Safe Boundary

Keep examples generic. Do not include customer names, item names, order numbers, invoice numbers, tracking numbers, EDI identifiers, tax amounts, custom field IDs, scripts, workflows, screenshots, logs, pricing, credentials, or private operating procedures.

## Self-Service Principles

- Start with the affected transaction or record.
- Compare one affected example to one known-good example.
- Check visible data and status before asking for configuration changes.
- Do not change roles, scripts, workflows, connector settings, tax setup, carrier setup, or EDI maps without approval.
- Capture sanitized error text and timing.
- Escalate with the exact layer already narrowed when possible.

## Safe for Most Users to Check

### NetSuite

Check:

- Transaction type and current status.
- Customer, item, address, quantity, date, and location values.
- Whether the issue affects one record or many records.
- Whether the record was copied, edited, imported, transformed, fulfilled, billed, credited, or voided.
- Whether another user with the same role sees the same result.
- Whether a similar known-good transaction behaves differently.

Do not change:

- Roles or permissions.
- Scripts or workflows.
- Custom forms or mandatory fields.
- Connector configuration.
- Accounting periods or posting controls.

### Avalara

Check:

- Which transaction has the tax issue.
- Whether tax is missing, zero, too high, too low, or changed after edit.
- Ship-to and bill-to address completeness.
- Whether the customer is expected to be taxable or exempt.
- Whether the item, shipping, fee, or discount line is the likely difference.
- Whether a similar transaction taxed correctly.

Do not change:

- Nexus setup.
- Tax codes or item taxability mappings.
- Exemption certificate setup.
- Connector credentials or tax settings.
- Filing or return configuration.

### Pacejet

Check:

- Item Fulfillment status.
- Ship-to address completeness.
- Package count, weight, and dimensions if visible.
- Whether rates returned before label generation.
- Whether a label or tracking number already exists.
- Whether the issue is rate, carrier service, label, tracking, void, reprint, or writeback.

Do not change:

- Carrier account setup.
- Rate-shopping rules.
- Connector credentials.
- Label templates.
- Automation scripts or workflows.
- Shipment retry behavior before checking duplicate risk.

### SPS Commerce

Check:

- Document type if visible: PO, acknowledgment, change, ASN, invoice, or portal error.
- Inbound or outbound direction.
- Whether the document is visible in SPS, NetSuite, both, or neither.
- Whether the document is missing, rejected, stuck, duplicated, or mismatched.
- Related NetSuite record type and status.
- Whether item, UOM, quantity, price, location, carrier, tracking, or invoice reference is the likely mismatch.

Do not change:

- EDI maps.
- Trading partner setup.
- VAN/mailbox credentials.
- Partner-specific requirements.
- Connector settings.
- Document resend/retry without checking duplicate or partial-success risk.

## Power User Checks

Power users or supervisors may also check:

- Saved search results for affected records.
- Dashboard or queue visibility.
- Whether multiple users in the same role see the same issue.
- Whether a transaction is blocked by status rather than permissions.
- Whether required fields are visibly blank.
- Whether a known-good transaction has different customer, item, address, location, quantity, date, or status.

Power users should still avoid configuration changes unless authorized.

## When to Escalate

Escalate when:

- The issue affects many transactions.
- A financial, tax, shipping, or EDI compliance deadline is at risk.
- A role or permission issue is suspected.
- A workflow, script, connector, tax setting, carrier setup, or EDI map may need changing.
- A retry could create duplicate tax, shipment, label, invoice, or EDI document risk.
- A vendor portal or connector shows a system-level error.
- A user cannot determine whether the issue is data, status, vendor response, or NetSuite writeback.

## Escalation Packet

When escalation is needed, provide:

1. System where the symptom appears.
2. NetSuite record type and status.
3. Connected vendor workflow involved.
4. Sanitized error text.
5. Date/time noticed.
6. Whether one record or many records are affected.
7. What changed recently, if known.
8. What the team already checked.
9. Whether a label, tracking number, tax result, EDI acknowledgment, or vendor response already exists.
10. Whether retry could create duplicate risk.

## AI Assistant Response Pattern

When a user asks for help and may not have admin access, the assistant should:

1. Start with safe user-checkable facts.
2. Ask for record type, status, connected vendor, and sanitized error text.
3. Suggest comparisons to a known-good example.
4. Separate safe checks from admin/vendor-only changes.
5. Warn before any retry or change that could duplicate shipments, tax, invoices, or EDI documents.
6. Provide an escalation packet if the issue needs higher access.

## Related Articles

- [Cross-Vendor Support](README.md)
- [NetSuite-Centered Integration Map](netsuite-centered-integration-map.md)
- [Cross-Vendor Incident Intake Checklist](integration-incident-intake-checklist.md)
- [Screenshot and Log Redaction Checklist](screenshot-log-redaction-checklist.md)
- [Advanced NetSuite Troubleshooting](../advanced-troubleshooting/README.md)
- [Advanced Avalara Troubleshooting](../../ecosystem/avalara/ADVANCED_TROUBLESHOOTING.md)
- [Advanced Pacejet Troubleshooting](../integrations/pacejet/advanced-troubleshooting.md)
- [Advanced SPS Commerce Troubleshooting](../integrations/sps-commerce/advanced-troubleshooting.md)
