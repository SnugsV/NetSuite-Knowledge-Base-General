---
title: Purchase Orders
module: Purchasing
difficulty: Intermediate
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Purchase Orders

## Quick Summary

A purchase order (PO) is a legally binding document that communicates a commitment to purchase goods or services from a vendor. The PO is the central document in the Procure-to-Pay lifecycle — it triggers receiving, invoicing, and payment processes.

## Difficulty

Intermediate

## Estimated Time

20 minutes

## Overview

The purchase order is the most important document in procurement. It is the formal offer to buy, specifying what is being ordered, in what quantity, at what price, by when, and under what terms. Once accepted by the vendor, it becomes a legally binding contract.

## The Purchase Order Lifecycle

```
Draft → Pending Approval → Approved → Open → Sent → Partially Received → Fully Received → Closed
```

## PO Types

| PO Type | Use |
|---|---|
| **Standard PO** | One-time purchase of goods or services |
| **Blanket PO** | Long-term agreement for recurring purchases. Defines terms and pricing but not specific quantities. Releases are created against the blanket. |
| **Planned PO** | A PO created from a demand planning process. Converted to a standard PO when the order is placed. |
| **Drop Ship PO** | A PO where the vendor ships directly to the company's customer. The PO references the sales order. |
| **Special Order PO** | A PO created specifically to fulfill a customer order. Items are not stocked. |

## Creating a Purchase Order

```
Transactions > Purchasing > Enter Purchase Orders
```

Key fields:

| Field | Purpose |
|---|---|
| **Vendor** | Who is being ordered from |
| **Vendor Location** | Which vendor location (if multiple) |
| **Currency** | Transaction currency |
| **Item** | What is being ordered |
| **Quantity** | How many units |
| **Rate** | Agreed price per unit |
| **Amount** | Line total (quantity × rate) |
| **Expected Date** | When delivery is expected |
| **Ship To** | Where goods should be delivered |
| **Terms** | Payment terms (defaults from vendor record) |
| **Memo** | Internal notes or instructions |

## PO Line Types

Purchase orders can include different line types:

| Line Type | Use |
|---|---|
| **Item** | Inventory item, non-inventory item, or service item |
| **Comment** | Text-only line for instructions or notes |
| **Group** | Group of items that are ordered together |
| **Estimated Cost** | For services where the final cost is not yet known |

## Blanket Purchase Orders

A blanket PO establishes terms with a vendor for a period (typically one year) without committing to specific quantities:

```
Blanket PO: $100,000 annually for office supplies
  Release 1 (January):  $8,000 — standard monthly order
  Release 2 (February): $7,500 — lower than normal
  Release 3 (March):    $9,000 — includes quarterly supply order
  ...
```

Releases are created against the blanket PO, reducing the remaining balance. Blanket POs are useful for recurring purchases where the exact timing and quantity vary.

## Drop Ship Purchase Orders

When a vendor ships directly to a customer:

1. A sales order is created
2. NetSuite automatically creates a PO to the vendor for the drop ship item
3. The PO references the sales order so the vendor knows the ship-to address
4. The vendor ships and sends an invoice
5. The Item Receipt and Item Fulfillment are created simultaneously

See [Drop Ship and Special Orders](../inventory/drop-ship-and-special-orders.md) for details.

## PO Statuses

| Status | Meaning |
|---|---|
| **Draft** | Being created, not yet finalized |
| **Pending Approval** | Awaiting authorization |
| **Approved** | Authorized but not yet sent to vendor |
| **Open** | Sent to vendor, awaiting fulfillment |
| **Partially Received** | Some items have been received |
| **Fully Received** | All items have been received |
| **Closed** | Fully received and billed |
| **Cancelled** | PO was cancelled before fulfillment |

## Business Example

A construction company needs to order steel beams for a project.

1. Purchasing agent creates a Standard PO: 50 steel beams at $200 each = $10,000
2. PO is routed for approval: the project manager approves (budget check), the purchasing manager approves (vendor selection)
3. PO is sent to the steel supplier (email or electronic)
4. Supplier acknowledges and ships 50 beams
5. Warehouse receives 50 beams, creates an Item Receipt against the PO
6. PO status: Fully Received
7. Supplier invoices $10,000
8. Three-way match: PO (50 × $200), Receipt (50), Invoice ($10,000) — all match
9. Invoice is paid on Net 30 terms

## Common Mistakes

- **Pricing that does not match the vendor agreement**: The PO price should match the contract or quote. Discrepancies cause invoice matching failures.
- **Missing expected dates**: Without expected dates, receiving cannot prioritize incoming shipments and planned delivery dates cannot be tracked.
- **Incorrect ship-to addresses**: A PO with the wrong address causes delivery delays and return shipping costs.
- **Using standard POs when blanket POs are more appropriate**: For recurring purchases, blanket POs reduce administrative overhead.
- **Closing POs prematurely**: A closed PO cannot receive against it. Close POs only after all receipts and invoices are processed.

## Best Practices

- Use POs for all vendor purchases — no PO, no payment policy prevents unauthorized spending
- Verify vendor pricing against the contract or quote before saving the PO
- Set expected dates accurately — they drive receiving schedules and on-time delivery metrics
- Use blanket POs for recurring purchases with established vendors
- Use drop ship POs for vendor-direct fulfillment to customers
- Review open POs weekly and follow up on overdue expected dates

## Knowledge Check

1. What is the difference between a Standard PO and a Blanket PO? (Answer: A Standard PO is for a one-time purchase. A Blanket PO establishes terms for recurring purchases, with releases against the blanket.)
2. **Scenario**: A PO has been partially received. The remaining items are no longer needed. What should you do? (Answer: Close the PO after receiving the remaining items or cancel the line items that are not needed.)
3. **Decision**: Your company buys office supplies every month from the same vendor. Pricing is fixed for the year. Which PO type? (Answer: Blanket PO with monthly releases.)

## Related Articles

- [Purchase Requisitions](purchase-requisitions.md)
- [Approval Workflows](approval-workflows.md)
- [Vendor Management](vendor-management.md)
- [Three-Way Matching](three-way-matching.md)
- [Inventory Receiving](../inventory/receiving-inventory.md)

## Oracle References

- [Oracle NetSuite Help Center: Purchase Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Creating Purchase Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)