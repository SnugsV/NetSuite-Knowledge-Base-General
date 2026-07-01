---
title: Vendor Bills and Payments
module: Purchasing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Vendor Bills and Payments

## Quick Summary

A vendor bill is the invoice a supplier sends for goods or services provided. Accounts Payable (AP) processes vendor bills, matches them to POs and receipts, and schedules payments. This article covers the bill-to-pay process from end to end.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

The vendor bill is where procurement meets accounting. Up to this point, the process has been operational: need identified, PO created, goods received. Now it becomes financial: the vendor invoice must be verified, entered, approved, and paid.

## The Bill-to-Pay Workflow

```
Vendor sends invoice
       ↓
Invoice received by AP
       ↓
Three-way match (PO, Receipt, Invoice)
       ↓
Bill entered in NetSuite
       ↓
Bill approval (if required)
       ↓
Payment scheduled based on terms
       ↓
Payment processed (check, ACH, card)
       ↓
Bill marked as paid
       ↓
Accounting entries complete
```

## Vendor Bill Entry

Vendor bills are entered at:

```
Transactions > Purchasing > Enter Bills
```

Key fields:

| Field | Purpose |
|---|---|
| **Vendor** | Who the bill is from |
| **Date** | Invoice date |
| **Due Date** | When payment is due (based on terms) |
| **Purchase Order** | The PO this bill is for |
| **Item** | What was purchased |
| **Quantity** | Quantity billed |
| **Amount** | Line total |
| **Expense Account** | GL account for the expense |
| **Memo** | Vendor invoice number or reference |

## Matching Bills to POs

Best practice is to create vendor bills from purchase orders. This ensures:

- The bill references the correct PO
- Line items, quantities, and prices from the PO are pre-populated
- Three-way matching can verify PO, receipt, and bill alignment

To create a bill from a PO:

```
Transactions > Purchasing > Enter Bills
Select "Create from Purchase Order"
Choose the PO → Items and quantities from the PO are loaded
```

## Bill Approval

Bills may require separate approval from the PO approval:

| Approval Stage | Focus |
|---|---|
| **PO Approval** | Commitment to purchase |
| **Bill Approval** | Verification of services received and pricing accuracy |

Bill approval is typically required for:

- Non-PO bills (invoices without a corresponding PO)
- Bills that exceed the PO amount
- Service bills where quantity is not verified at receipt
- High-value bills above a defined threshold

## Payment Methods

| Method | Best For |
|---|---|
| **Check** | Domestic vendors, infrequent payments |
| **ACH / EFT** | Regular vendors, lower cost than checks |
| **Credit Card** | Low-value purchases, expense management |
| **Wire Transfer** | International payments, urgent payments |
| **Electronic Payment** | Vendor portal integration |

## Payment Terms and Discounts

Payment terms affect cash flow:

| Term | Payment Timing |
|---|---|
| **Net 30** | Pay 30 days after invoice date |
| **2% 10, Net 30** | 2% discount if paid within 10 days, otherwise full amount due in 30 |
| **Due on Receipt** | Pay immediately |
| **Prepaid** | Pay before goods are shipped |

Taking early payment discounts can significantly improve profitability. A 2% 10 Net 30 discount is effectively a 36% annual return.

## Accounting Impact

Each stage of the P2P cycle affects the financial statements:

| Transaction | Impact |
|---|---|
| **Item Receipt** | Debit Inventory Asset, Credit Accrued Purchases |
| **Vendor Bill** | Debit Accrued Purchases (or Expense), Credit Accounts Payable |
| **Payment** | Debit Accounts Payable, Credit Cash |

## Business Example

An AP clerk processes 50 vendor bills per day.

**Daily workflow**:

1. Receive invoices from vendors (email, mail, EDI)
2. For each invoice, locate the matching PO in NetSuite
3. Verify that the PO has been fully or partially received
4. Create the bill from the PO — quantities and prices are pre-populated
5. If the invoice matches the PO, save the bill
6. If there is a discrepancy (price changed, quantity different), investigate before saving
7. Schedule payments based on due dates
8. Run payment runs twice per week (checks on Tuesday, ACH on Thursday)

## Common Mistakes

- **Entering bills without a PO reference**: Unmatched bills are difficult to verify and may result in payment errors
- **Paying before the PO is received**: Without receipt verification, you may pay for goods that have not arrived
- **Duplicate payments**: Paying the same invoice twice happens when invoices are entered manually and not matched to existing records
- **Not taking early payment discounts**: 2% 10 Net 30 is a significant saving. Configure systems to capture discounts automatically
- **Delayed bill entry**: Bills entered late delay payment processing and may miss discount windows

## Best Practices

- Create all bills from purchase orders — no PO, no bill (with defined exceptions)
- Match bills to receipts before processing for payment
- Use bill approval workflows for non-PO bills and high-value bills
- Schedule payment runs on regular intervals
- Reconcile AP aging weekly
- Take all available early payment discounts
- Use electronic payments when possible for faster processing and lower cost

## Knowledge Check

1. A vendor invoice for $5,000 arrives. The PO is for $4,800. What should you do? (Answer: Investigate the $200 discrepancy before entering the bill.)
2. **Scenario**: A vendor offers 2% 10 Net 30 on a $10,000 invoice. What is the benefit of paying within 10 days? (Answer: Save $200. If the company has cash available, this is a 36% annualized return.)
3. **True/False**: A vendor bill should always be entered before the goods are received. (Answer: False — the goods should be received first so the three-way match can verify quantity.)

## Related Articles

- [Three-Way Matching](three-way-matching.md)
- [Purchase Orders](purchase-orders.md)
- [What Is Procurement?](what-is-procurement.md)
- [Inventory Receiving](../inventory/receiving-inventory.md)
- [Accounts Payable](../accounting/accounts-payable.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Vendor Bills](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Accounts Payable](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)