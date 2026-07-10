# Cross-Vendor Support

## Purpose

This section helps support teams and AI assistants diagnose incidents that cross NetSuite, Avalara, Pacejet, and SPS Commerce.

NetSuite is usually the operational hub. Avalara, Pacejet, and SPS Commerce each depend on NetSuite records, transaction status, addresses, items, customers, permissions, scripts, workflows, and connector timing. A symptom in one system may be caused by data or status in another.

## Learning Order

1. [NetSuite-Centered Integration Map](netsuite-centered-integration-map.md) - Understand how NetSuite data flows into Avalara, Pacejet, and SPS Commerce.
2. [Cross-Vendor Incident Intake Checklist](integration-incident-intake-checklist.md) - Gather clean troubleshooting context before proposing fixes.
3. [Release and Update Review Workflow](release-update-review-workflow.md) - Review vendor releases, connector changes, and monthly updates without losing history.
4. [Screenshot and Log Redaction Checklist](screenshot-log-redaction-checklist.md) - Keep support examples public-safe before adding them to documentation or AI references.

## What This Section Is For

Use this section when:

- A NetSuite transaction behaves differently after a vendor sync, tax calculation, shipment, or EDI document.
- A screenshot or error could belong to more than one system.
- A user is unsure whether the issue is NetSuite, Avalara, Pacejet, SPS Commerce, a connector, a workflow, or a script.
- A vendor release or connector update may have changed behavior.
- A support example needs to be sanitized before it becomes documentation.

## System Roles

| System | Common Role | Typical NetSuite Touchpoints |
|---|---|---|
| NetSuite | Operational source and transaction hub | Customers, items, orders, fulfillments, invoices, credits, roles, workflows, scripts, saved searches |
| Avalara | Tax calculation and compliance support | Customer, item, address, location, transaction date, tax fields, credits, invoices |
| Pacejet | Shipping rates, labels, tracking, carrier services | Item Fulfillment, ship-to address, origin, item weight/dimensions, packages, tracking |
| SPS Commerce | EDI and retail trading partner exchange | Purchase orders, sales orders, acknowledgments, ASNs, invoices, item/customer/location mappings |

## Public-Safe Rule

Keep examples generic. Do not include company-specific SOPs, customer names, item names, order numbers, invoice numbers, tracking numbers, EDI document IDs, tax amounts, custom fields, scripts, workflows, credentials, screenshots, logs, pricing, or private operating procedures.

## Related Sections

- [Advanced NetSuite Troubleshooting](../advanced-troubleshooting/README.md)
- [Advanced Avalara Troubleshooting](../../ecosystem/avalara/ADVANCED_TROUBLESHOOTING.md)
- [Advanced Pacejet Troubleshooting](../integrations/pacejet/advanced-troubleshooting.md)
- [Advanced SPS Commerce Troubleshooting](../integrations/sps-commerce/advanced-troubleshooting.md)
