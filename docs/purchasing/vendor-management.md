---
title: Vendor Management
module: Purchasing
difficulty: Beginner
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Vendor Management

## Quick Summary

Vendor records are the master data for every supplier an organization does business with. Vendor management covers creating and maintaining vendor records, classifying vendors, managing relationships, and tracking performance.

## Difficulty

Beginner

## Estimated Time

15 minutes

## Overview

A vendor record is the foundation of the purchasing relationship. It contains the information needed to do business with a supplier: legal name, address, tax identification, payment terms, currency, and contact information. Well-maintained vendor records prevent payment errors, support compliance, and enable vendor performance analysis.

## Vendor Record Structure

Vendor records are accessed at:

```
Lists > Relationships > Vendors > New
```

Key fields on a vendor record:

| Field | Purpose |
|---|---|
| **Company Name** | Legal business name |
| **Vendor Number** | Unique identifier (can be auto-generated or manual) |
| **Category** | Vendor classification (raw materials, services, supplies) |
| **Terms** | Payment terms (Net 30, 2% 10 Net 30) |
| **Currency** | Transaction currency (for foreign vendors) |
| **Tax ID** | Tax identification number for 1099 reporting |
| **Address** | Remit-to address for invoice submission |
| **Email / Phone** | Primary contact information |
| **Vendor Type** | Company, individual, or 1099 vendor |

## Vendor Classification

Classifying vendors enables meaningful reporting and analysis:

| Classification | Purpose |
|---|---|
| **Category** | What they supply (raw materials, MRO, services, logistics) |
| **Tier** | Strategic importance (preferred, approved, one-time) |
| **Region** | Geographic location for sourcing decisions |
| **Spend Range** | Purchase volume classification |
| **Commodity** | Type of goods or services provided |

## Payment Terms

Payment terms define when and how vendors are paid:

| Term | Meaning |
|---|---|
| **Net 30** | Payment due 30 days after invoice date |
| **Net 60** | Payment due 60 days after invoice date |
| **2% 10 Net 30** | 2% discount if paid within 10 days, otherwise full amount due in 30 |
| **Due on Receipt** | Payment due immediately |
| **COD** | Cash on delivery |
| **Prepaid** | Payment required before shipment |

Terms affect cash flow, working capital, and vendor relationships. Standardizing terms with vendors simplifies AP processing.

## 1099 Reporting

In the US, payments to individual contractors and certain business types must be reported to the IRS using Form 1099-NEC. NetSuite supports 1099 tracking:

- Mark the vendor as **1099 Eligible** on the vendor record
- Select the appropriate **1099 Box** (typically Box 1 for non-employee compensation)
- At year-end, run the 1099 reporting process to generate the required forms

## Vendor Status

| Status | Meaning |
|---|---|
| **Active** | Vendor can be used on purchase orders |
| **Inactive** | Vendor cannot be used on new transactions — historical records remain |
| **Hold** | Vendor is temporarily blocked — no new POs or payments |

## Vendor Performance Tracking

Key vendor performance metrics:

| Metric | Calculation | Target |
|---|---|---|
| **On-Time Delivery** | % of receipts received on or before promised date | > 95% |
| **Quality Defect Rate** | % of received items with quality issues | < 2% |
| **Lead Time Accuracy** | Actual vs. promised lead time variance | ± 2 days |
| **Invoice Accuracy** | % of invoices matching PO without errors | > 98% |
| **Price Competitiveness** | Price relative to market or other vendors | Within 5% |

## Business Example

A distributor maintains 500 vendor records across 20 categories.

**Vendor onboarding process**:

1. Requesting department identifies a new supplier
2. Procurement collects: W-9 (for US vendors), banking information, pricing, lead times
3. Legal reviews and signs the contract
4. Vendor record is created with: company name, address, tax ID, payment terms (Net 30), category (Raw Materials), tier (Approved)
5. Vendor is assigned a default expense account and item default
6. Vendor is activated for PO processing

**Vendor maintenance**:

- Quarterly: Review vendor performance metrics
- Annually: Update W-9 information, confirm payment terms, review pricing
- As needed: Update contact information, address changes

## Common Mistakes

- **Duplicate vendor records**: The same supplier entered under slightly different names. Use a consistent naming convention and search before creating.
- **Missing tax information**: Without a W-9 on file, 1099 reporting is impossible. Require tax information before activating the vendor.
- **Incorrect payment terms**: Paying Net 30 when the contract specifies Net 60 reduces cash flow.
- **No vendor categorization**: Without categories, spend analysis and vendor performance reporting are difficult.
- **Not inactivating inactive vendors**: Old vendor records clutter lists and can be used accidentally.

## Best Practices

- Use a consistent vendor naming convention: "Vendor Name, Inc." not "Vendor Name Incorporated"
- Require W-9 and banking information before creating the vendor record
- Assign default expense accounts on vendor records to streamline PO creation
- Review vendor records quarterly for accuracy
- Inactivate, never delete, vendors that are no longer used
- Use vendor categories for spend analysis and reporting

## Knowledge Check

1. A vendor offers a 2% discount if paid within 10 days. How is this recorded in the vendor record? (Answer: Payment terms "2% 10 Net 30".)
2. **Scenario**: A vendor has been acquired by another company and has a new legal name and tax ID. What should you do? (Answer: Update the vendor record with the new information. If the vendor number changes, consider inactivating the old record and creating a new one.)
3. **Decision**: Your company uses independent contractors who must receive 1099 forms. What must be configured on the vendor record? (Answer: 1099 Eligible = Yes, with the correct 1099 Box.)

## Related Articles

- [What Is Procurement?](what-is-procurement.md)
- [Purchase Orders](purchase-orders.md)
- [Purchase Requisitions](purchase-requisitions.md)
- [Vendor Bills](vendor-bills-and-payments.md)
- [Item Records](../inventory/item-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Vendor Records](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Vendor Management](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)