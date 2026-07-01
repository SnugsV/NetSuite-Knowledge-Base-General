---
title: Procurement Best Practices
module: Purchasing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Procurement Best Practices

## Quick Summary

This article consolidates procurement best practices across the entire Procure-to-Pay lifecycle. Following these practices reduces cost, improves vendor relationships, ensures compliance, and builds a procurement function that supports business goals.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Process Best Practices

### Procure-to-Pay

- **Always use purchase orders**: A "no PO, no payment" policy is the single most effective procurement control. Every vendor commitment should have a PO.
- **Create POs before receiving goods**: The PO should exist before the goods arrive. Retroactive POs erode controls.
- **Match before paying**: Always perform three-way matching for inventory items and two-way matching for services before authorizing payment.
- **Close POs promptly**: Close POs when all items are received and all bills are processed. Open POs represent unbudgeted commitments.
- **Reconcile AP weekly**: Review AP aging, identify discrepancies, and resolve them before they become overdue.

### Requisition-to-PO

- **Use requisitions for all non-routine purchases**: Routine purchases (e.g., standing orders from approved vendors) may bypass requisitions, but all others should go through the approval process.
- **Enforce budget verification at requisition**: The system should check budget availability before the requisition is approved.
- **Convert requisitions to POs promptly**: Approved requisitions should be converted within 1-2 business days to maintain momentum and meet deadlines.
- **Standardize requisition fields**: Require item description, estimated cost, department, required date, and justification on every requisition.

## Vendor Management Best Practices

- **Maintain a clean vendor master**: One vendor = one record. Use a consistent naming convention and search before creating new vendors.
- **Require W-9 before activation**: For US vendors, never activate a vendor without a completed W-9.
- **Review vendor lists quarterly**: Inactivate vendors with no recent activity. Verify contact information for active vendors.
- **Classify vendors by category and tier**: Classification enables meaningful spend analysis and performance tracking.
- **Establish vendor performance reviews**: Review on-time delivery, quality, and pricing with key vendors quarterly.

## Control Best Practices

- **Segregate duties**: Separate PO creation, approval, receiving, bill entry, and payment. No single person should control more than two adjacent steps.
- **Set appropriate approval thresholds**: Thresholds should reflect the organization's risk tolerance. Review annually.
- **Monitor control exceptions**: Use Saved Searches to identify POs without receipts, bills without POs, and other exceptions.
- **Audit purchasing activity**: Review the audit trail quarterly for unusual patterns.
- **Document control exceptions**: When controls are bypassed, document why and who authorized it.

## System Configuration Best Practices

- **Enable purchase requisitions**: Even if not used for every purchase, having the feature enabled provides the option.
- **Configure three-way matching**: Enable matching with appropriate tolerances for your business.
- **Set up approval workflows**: Automate approval routing based on value, department, and item type.
- **Create Saved Searches for monitoring**: Build searches for open POs, overdue receipts, pending approvals, and vendor performance.
- **Train users on purchasing processes**: Every user who creates requisitions or POs should understand the process.

## Procurement Health Scorecard

| Metric | Healthy | Warning | Critical |
|---|---|---|---|
| PO Compliance (% spend with PO) | > 95% | 85-95% | < 85% |
| Three-Way Match Rate | > 90% | 80-90% | < 80% |
| Requisition-to-PO Time | < 2 days | 2-5 days | > 5 days |
| On-Time Delivery | > 95% | 85-95% | < 85% |
| Non-PO Spend | < 5% | 5-10% | > 10% |
| Vendor Master Accuracy | > 95% | 85-95% | < 85% |
| Emergency PO % | < 5% | 5-10% | > 10% |
| Early Payment Discount Capture | > 90% | 75-90% | < 75% |

## ERP Integration Summary

| Module | How Purchasing Connects |
|---|---|
| **Inventory** | Item records used on POs; inventory received via Item Receipt |
| **Accounting** | Vendor bills accrue liabilities; payments reduce cash; inventory valuation impacted |
| **Sales** | Drop-ship POs created from sales orders; special order POs for customer fulfillment |
| **Manufacturing** | Raw material POs for production; component availability drives procurement timing |
| **Saved Searches** | PO monitoring, vendor performance, spend analysis, exception reporting |
| **Workflows** | PO and requisition approval routing; automated notifications |
| **SuiteScript** | Automated PO creation; vendor portal integration; EDI processing |

## Related Articles

- [What Is Procurement?](what-is-procurement.md)
- [Purchasing Controls](purchasing-controls.md)
- [Procurement KPIs](procurement-kpis.md)
- [Approval Workflows](approval-workflows.md)
- [Three-Way Matching](three-way-matching.md)
- [All Inventory module articles](../inventory/README.md)

## Oracle References

- [Oracle NetSuite Help Center: Procurement Best Practices](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)