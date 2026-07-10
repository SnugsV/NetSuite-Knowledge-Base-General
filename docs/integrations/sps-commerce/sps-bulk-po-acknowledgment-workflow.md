# SPS Bulk Purchase Order Acknowledgment Workflow

## Quick Summary

Use this workflow when multiple NetSuite sales orders need outbound EDI 855 Purchase Order Acknowledgments through SPS Commerce. The goal is to acknowledge eligible orders in a controlled batch while avoiding duplicate acknowledgments, missing required data, or processing orders that are not ready.

## Public-Safe Boundary

Keep examples generic. Do not publish company names, customer names, partner-specific routing requirements, order numbers, item SKUs, screenshots, logs, credentials, internal role names, or private operating procedures.

## When To Use This Workflow

Use this workflow when:

- Several inbound EDI purchase orders have already created NetSuite sales orders.
- The orders need 855 acknowledgments sent through SPS Commerce.
- The account has a configured SPS bulk EDI processing page, queue, connector action, or equivalent batch process.
- The team needs a repeatable way to verify status after submission.

Do not use this workflow when:

- The inbound PO failed to create a sales order.
- The order needs manual review before acceptance, rejection, backorder, or date change.
- The expected acknowledgment action is unclear.
- A prior acknowledgment may already have been accepted.

## Prerequisites

Before starting, confirm:

- The user has access to the SPS bulk processing page, queue, or portal process used by the account.
- The target transaction type is Purchase Order Acknowledgment or EDI 855.
- Eligible orders have the required SPS routing or partner identifier.
- Sales orders are in a state where acknowledgment generation is allowed.
- Item, UOM, quantity, date, customer, ship-to, and location mappings are complete.
- Any line-level acceptance, rejection, backorder, or date changes have been reviewed.

## General Batch Workflow

1. Open the configured SPS bulk EDI processing page, connector queue, or equivalent batch-processing tool in NetSuite.
2. Select the bulk transaction type for Purchase Order Acknowledgment, commonly EDI 855.
3. Filter for transactions that have the required SPS routing key, trading partner reference, or other configured EDI eligibility marker.
4. Search or refresh the list of eligible sales orders.
5. Review the displayed transactions before selecting them. Confirm each order is ready to acknowledge.
6. Select only the transactions that should be processed. Use select-all options only after confirming the filtered list is correct.
7. Submit the selected transactions for bulk processing.
8. Open the bulk status, connector status, or portal status page after submission.
9. Monitor each transaction until it completes, fails, or requires follow-up.
10. Export or save the status results only if the exported file follows the organization's privacy and retention rules.

## What To Check Before Processing

Check each batch for:

- Correct transaction type
- Correct date range or search filter
- Correct EDI eligibility marker
- Sales order status
- Required customer and ship-to data
- Required item identifiers and UOM
- Accepted, rejected, partial, or changed quantities
- Promise dates, cancel dates, ship dates, or requested delivery dates
- Known order holds or approval blockers
- Duplicate or previously processed acknowledgments

## Common Exceptions

### No Orders Appear In The Batch List

Likely causes:

- The search filter is too narrow.
- Orders do not have the required SPS routing key or EDI eligibility marker.
- The inbound PO did not create a sales order.
- The sales order is not in an eligible status.
- Required mapping failed earlier in the lifecycle.

### Order Appears But Should Not Be Processed

Likely causes:

- Order is on hold or pending review.
- Quantity, date, or item availability needs review.
- The order needs partial acceptance, rejection, or backorder handling.
- A change order was received after the sales order was created.
- A prior acknowledgment has already been generated.

### Batch Completes With Errors

Likely causes:

- Required acknowledgment field is missing.
- Item, UOM, ship-to, or partner mapping is incomplete.
- Sales order state changed after the batch search loaded.
- Partner validation rejected the generated document.
- Connector or portal queue failed downstream.

### Partner Says The Order Was Not Acknowledged

Likely causes:

- The NetSuite batch completed but the SPS transmission failed.
- The document is stuck in a connector, portal, mailbox, or VAN queue.
- The document was rejected after generation.
- The wrong order reference or partner reference was reviewed.
- A replacement or duplicate acknowledgment created confusion.

## Safe Reprocessing Rules

Before reprocessing:

1. Confirm whether the original 855 was generated.
2. Confirm whether it was transmitted to SPS Commerce.
3. Confirm whether SPS or the trading partner accepted or rejected it.
4. Review the exact failed transaction or status message.
5. Reprocess only the failed or corrected transactions, not the full prior batch.
6. Avoid blind resends when the partner may already have accepted the acknowledgment.

## Frontline Self-Service Checks

A frontline team member can usually check:

- Whether the order appears in the bulk list.
- Whether the transaction type and filters are correct.
- Whether the order has an obvious hold, missing status, or missing EDI marker.
- Whether the bulk status page shows Completed, In Progress, Failed, or Error.
- Whether the same order was already processed in a prior batch.
- Whether a visible error message points to a missing field, mapping, or status issue.

Escalate when:

- The error references scripts, workflows, connector configuration, maps, credentials, or permissions.
- The order has conflicting statuses across NetSuite and SPS.
- A document may have been partially transmitted.
- The same issue affects many transactions.
- The fix requires changing EDI mapping or partner setup.

## AI Assistant Response Pattern

When a user asks how to bulk process PO acknowledgments, the assistant should:

1. Confirm the user is working with EDI 855 Purchase Order Acknowledgments.
2. Ask whether the orders are visible in the bulk processing list.
3. Ask whether the orders have the required SPS routing or eligibility marker.
4. Walk through selecting the correct transaction type, filtering, reviewing, submitting, and checking status.
5. For failures, route the user to lifecycle, mapping, connector, or PO acknowledgment diagnostics.
6. Keep company-specific process names, partner data, order identifiers, and screenshots private.

## Related Articles

- [Purchase Order Acknowledgment and Change Order Diagnostics](sps-po-acknowledgment-change-order-diagnostics.md)
- [EDI Document Lifecycle Troubleshooting](sps-edi-document-lifecycle-troubleshooting.md)
- [NetSuite and SPS Data Mapping Diagnostics](sps-netsuite-data-mapping-diagnostics.md)
- [Connector or Portal Error Triage](sps-connector-portal-error-triage.md)
