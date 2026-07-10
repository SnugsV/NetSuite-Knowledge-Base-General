# SPS Bulk ASN Workflow

## Quick Summary

Use this workflow when multiple shipped NetSuite item fulfillments need outbound EDI 856 Advance Ship Notices through SPS Commerce. The goal is to generate and transmit ASNs only after shipment, tracking, carrier, package, and carton data are ready.

## Public-Safe Boundary

Keep examples generic. Do not publish company names, customer names, partner-specific routing requirements, shipment IDs, tracking numbers, carton labels, SSCC values, item SKUs, screenshots, logs, credentials, internal role names, or private warehouse procedures.

## When To Use This Workflow

Use this workflow when:

- Item fulfillments have reached the shipped state.
- The related sales orders came from or are tied to EDI trading partner activity.
- Tracking and package information is complete enough for ASN generation.
- The account has a configured SPS bulk EDI processing page, queue, connector action, or equivalent batch process.

Do not use this workflow when:

- Fulfillments are only picked or packed, not shipped.
- Tracking, carrier, carton, or package data is missing.
- Shipment data is still waiting for a shipping system writeback.
- A prior ASN may already have been accepted.
- The shipment needs manual correction before transmission.

## Prerequisites

Before starting, confirm:

- The user has access to the SPS bulk processing page, queue, or portal process used by the account.
- The target transaction type is Advance Ship Notice or EDI 856.
- Item fulfillments are in the shipped status required by the configuration.
- The fulfillment has the required SPS routing or partner identifier.
- Tracking, carrier, service, ship date, ship-from, and ship-to data are present.
- Package, carton, pallet, or SSCC data is present when required.
- Shipped quantities match what should be reported on the ASN.

## General Batch Workflow

1. Open the configured SPS bulk EDI processing page, connector queue, or equivalent batch-processing tool in NetSuite.
2. Select the bulk transaction type for Advance Ship Notice, commonly EDI 856.
3. Set shipment-related filters such as shipped transaction status, required SPS routing key, or configured EDI eligibility marker.
4. Search or refresh the list of eligible item fulfillments.
5. Review the displayed fulfillments before selecting them. Confirm each shipment is ready for ASN generation.
6. Select only the item fulfillments that should be processed.
7. Submit the selected fulfillments for bulk processing.
8. Open the bulk status, connector status, or portal status page after submission.
9. Monitor each fulfillment until it completes, fails, or requires follow-up.
10. Export or save the status results only if the exported file follows the organization's privacy and retention rules.

## What To Check Before Processing

Check each batch for:

- Correct transaction type
- Shipped fulfillment status
- Correct EDI eligibility marker
- Required tracking number or tracking structure
- Carrier and service mapping
- Ship date and shipment timing
- Package, carton, pallet, or SSCC requirements
- Shipped quantities by line
- Item identifiers and UOM
- Partial shipment, backorder, or closed-line handling
- Whether shipping-system writeback has completed
- Duplicate or previously processed ASNs

## Common Exceptions

### Fulfillment Does Not Appear In The Batch List

Likely causes:

- Fulfillment is not in shipped status.
- The search filter is too narrow.
- The fulfillment does not have the required SPS routing key or EDI eligibility marker.
- The related order is missing required EDI partner data.
- Shipment or package data has not written back yet.

### Fulfillment Appears But Should Not Be Processed

Likely causes:

- Tracking number is missing or incomplete.
- Carrier or service code is not mapped.
- Package or carton contents are not final.
- Partial shipment needs review.
- Fulfillment was edited after shipment or after ASN generation.
- A prior ASN has already been generated or accepted.

### Batch Completes With Errors

Likely causes:

- Required tracking, carrier, carton, or SSCC data is missing.
- Item, UOM, or quantity mapping is incomplete.
- Fulfillment status changed after the batch search loaded.
- Partner validation rejected the pack structure.
- Connector or portal queue failed downstream.

### ASN Is Rejected After Transmission

Likely causes:

- Carton hierarchy does not match partner expectations.
- Tracking is missing, duplicated, or attached to the wrong package.
- Carrier code, SCAC, or service value is invalid.
- Shipped quantities do not match expected order or acknowledgment quantities.
- Required label, packaging, or routing data is missing.

## Pacejet And Shipping-System Timing

When a shipping system such as Pacejet is part of the process, confirm shipping writeback is complete before ASN generation. Tracking, carrier, service, package count, package weight, dimensions, and carton details may be created or updated by the shipping system after fulfillment work starts. Generating the ASN too early can create missing-tracking, wrong-carrier, or incomplete-package errors.

## Safe Reprocessing Rules

Before reprocessing:

1. Confirm whether the original 856 was generated.
2. Confirm whether it was transmitted to SPS Commerce.
3. Confirm whether SPS or the trading partner accepted or rejected it.
4. Review the exact failed fulfillment or status message.
5. Correct the fulfillment, package, tracking, or mapping issue first.
6. Reprocess only the failed or corrected fulfillments, not the full prior batch.
7. Avoid blind resends when the partner may already have accepted the ASN.

## Frontline Self-Service Checks

A frontline team member can usually check:

- Whether the fulfillment is shipped.
- Whether tracking and package information is visible.
- Whether the fulfillment appears in the bulk list.
- Whether the transaction type and filters are correct.
- Whether the bulk status page shows Completed, In Progress, Failed, or Error.
- Whether the same fulfillment was already processed in a prior batch.
- Whether a visible error message points to missing tracking, carrier, package, item, or quantity data.

Escalate when:

- The error references scripts, workflows, connector configuration, maps, credentials, or permissions.
- Shipment data differs between NetSuite, SPS, and the shipping system.
- A document may have been partially transmitted.
- The same issue affects many fulfillments.
- The fix requires changing EDI mapping, carrier mapping, or partner setup.

## AI Assistant Response Pattern

When a user asks how to bulk process ASNs, the assistant should:

1. Confirm the user is working with EDI 856 Advance Ship Notices.
2. Ask whether the fulfillments are shipped and visible in the bulk processing list.
3. Ask whether tracking, carrier, package, and carton data are complete.
4. Walk through selecting the correct transaction type, filtering for shipped eligible fulfillments, reviewing, submitting, and checking status.
5. For failures, route the user to ASN, mapping, connector, or shipping-system diagnostics.
6. Keep company-specific process names, partner data, shipment identifiers, tracking values, carton labels, and screenshots private.

## Related Articles

- [ASN and Shipment Notice Troubleshooting](sps-asn-shipment-notice-troubleshooting.md)
- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
- [Connector or Portal Error Triage](sps-connector-portal-error-triage.md)
- [Pacejet Post-Shipment Troubleshooting](../pacejet/pacejet-post-shipment-troubleshooting.md)
