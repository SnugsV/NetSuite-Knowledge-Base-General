---
title: Journal Entries
module: Accounting
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Journal Entries

## Quick Summary

Journal entries record financial transactions in the general ledger. System-generated entries are created automatically by operational transactions. Manual entries are used for adjustments, corrections, allocations, and accruals.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Business Question

"How do I record a transaction that my operational modules do not automatically handle?"

## Overview

Most transactions enter the GL automatically through NetSuite's integrated modules. A sales order fulfillment creates COGS and inventory entries. A vendor bill creates AP and expense entries. But some transactions require manual journal entries — depreciation, accruals, reclassifications, corrections.

## Journal Entry Types

| Type | Source | Example |
|---|---|---|
| **System-generated** | Operational transactions | PO, SO, Work Order |
| **Manual standard** | User-entered | Depreciation, accruals |
| **Intercompany** | Transactions between subsidiaries | Transfer pricing, allocations |
| **Reversing** | Auto-reverses next period | Accruals that settle |

## Common Journal Entries

| Scenario | Debit | Credit |
|---|---|---|
| **Record depreciation** | Depreciation Expense | Accumulated Depreciation |
| **Accrue month-end expense** | Expense | Accrued Liability |
| **Reclassify incorrect account** | Correct Account | Incorrect Account |
| **Record intercompany transfer** | Receivable from Subsidiary | Payable to Subsidiary |

## Common Customer Questions

**Q**: A journal entry won't post. What should I check? **Records to Inspect**: Account is active, debits equal credits, period is open, user has posting permission.

**Q**: The trial balance is out of balance. Where do I start? **Questions to Ask First**: Were any journal entries entered with unequal debits and credits? Was a system posting interrupted? Were any transactions entered in a closed period?

## Related Articles

- [The General Ledger](the-general-ledger.md)
- [Period Close](period-close.md)
- [Financial Statements](financial-statements.md)
- [Financial Controls](financial-controls.md)

## Oracle References

- [Oracle NetSuite Help Center: Journal Entries](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)