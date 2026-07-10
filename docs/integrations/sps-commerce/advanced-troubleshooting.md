# Advanced SPS Commerce Troubleshooting

## Purpose

This section helps NetSuite users, administrators, consultants, and AI assistants troubleshoot advanced SPS Commerce EDI and trading partner workflow issues without exposing private partner requirements, production documents, credentials, maps, or operating procedures.

## Learning Order

1. [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md) - Diagnose document status, direction, timing, acknowledgment, and lifecycle issues.
2. [Bulk Purchase Order Acknowledgment Workflow](sps-bulk-po-acknowledgment-workflow.md) - Process eligible sales orders through a generalized bulk EDI 855 workflow and verify batch status.
3. [Purchase Order Acknowledgment and Change Order Diagnostics](sps-po-acknowledgment-change-order-diagnostics.md) - Diagnose 850, 855, changes, acceptance, rejection, and order-update issues.
4. [Bulk ASN Workflow](sps-bulk-asn-workflow.md) - Process eligible shipped item fulfillments through a generalized bulk EDI 856 workflow and verify batch status.
5. [ASN and Shipment Notice Troubleshooting](sps-asn-shipment-notice-troubleshooting.md) - Diagnose 856, carton, tracking, routing, shipment, and fulfillment issues.
6. [Invoice and 810 Mismatch Diagnostics](sps-invoice-810-mismatch-diagnostics.md) - Diagnose invoice mismatches, totals, pricing, allowances, charges, taxes, and partner rejections.
7. [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md) - Diagnose item, partner, UOM, location, address, carrier, and field mapping problems.
8. [Connector or Portal Error Triage](sps-connector-portal-error-triage.md) - Diagnose sync, portal, mailbox, VAN, validation, and retry issues.

## What This Section Is For

Use this section when:

- An EDI document is missing, late, rejected, duplicated, or stuck.
- A purchase order cannot be acknowledged or changed correctly.
- Multiple sales orders need EDI 855 acknowledgments through a controlled bulk process.
- Multiple shipped item fulfillments need EDI 856 ASNs through a controlled bulk process.
- An ASN is rejected or does not match shipment requirements.
- An invoice is rejected or does not match the PO/receipt/shipment.
- NetSuite and SPS Commerce disagree on item, partner, location, UOM, or shipment data.
- A connector, portal, mailbox, or VAN error appears.

## Public-Safe Rule

Keep examples generic. Do not include retailer names tied to private requirements, purchase order numbers, invoice numbers, shipment IDs, tracking numbers, trading partner IDs, EDI map details, VAN/mailbox credentials, production logs, screenshots, chargeback details, pricing, or private SOPs.

## Source Notes

This section is based on public SPS Commerce product information, general EDI document lifecycle patterns, generalized internal workflow patterns, and NetSuite integration troubleshooting concepts. Implementation-specific behavior must be verified against the actual SPS setup, NetSuite account, trading partner requirements, EDI maps, connector configuration, and operating process.

## Related Modules

- [SPS Commerce Integration](README.md)
- [Advanced NetSuite Troubleshooting](../../advanced-troubleshooting/README.md)
- [Sales](../../sales/README.md)
- [Inventory](../../inventory/README.md)
- [Accounting](../../accounting/README.md)
