---
title: Capstone: Record-to-Report
module: Accounting
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Capstone: Record-to-Report

## Quick Summary

This capstone scenario traces transactions through the entire Record-to-Report process — from purchasing raw materials through financial statements. Complete each task to apply concepts from Purchasing, Inventory, Manufacturing, Sales, and Accounting.

## Estimated Time

20 minutes

## The Scenario: Precision Manufacturing

Precision Manufacturing makes industrial components. They have the following activity in March.

## Chart of Accounts (Simplified)

| Number | Account | Type |
|---|---|---|
| 1000 | Cash | Asset |
| 1100 | Accounts Receivable | Asset |
| 1200 | Inventory — Raw Materials | Asset |
| 1210 | Inventory — WIP | Asset |
| 1220 | Inventory — Finished Goods | Asset |
| 2000 | Accounts Payable | Liability |
| 2100 | Accrued Expenses | Liability |
| 3000 | Retained Earnings | Equity |
| 4000 | Sales Revenue | Revenue |
| 5000 | COGS | Expense |
| 6000 | Operating Expenses | Expense |

## Transactions in March

### Week 1

**Mar 3**: Purchase raw materials — 1,000 kg of Steel at $5/kg. Terms Net 30.
**Mar 5**: Receive 1,000 kg of Steel. PO shows $5,000.

### Week 2

**Mar 10**: Create Work Order for 500 units of Component X. BOM: 2 kg Steel per unit.
**Mar 12**: Issue 1,000 kg Steel to WO-001.
**Mar 14**: Complete WO-001 — 500 units built. Labor cost: $2,000. Overhead applied: $1,000.

### Week 3

**Mar 17**: Sales Order for 200 units of Component X at $25/unit.
**Mar 18**: Fulfill SO-001 — 200 units shipped. Average cost $12/unit.
**Mar 20**: Invoice customer for $5,000. Terms Net 30.

### Week 4

**Mar 25**: Receive vendor bill for steel — $5,000.
**Mar 28**: Customer pays the $5,000 invoice.
**Mar 31**: Record monthly depreciation: $500.

## Tasks

### Task 1: Record the Mar 5 Item Receipt
What is the journal entry?
**Answer**: Debit Inventory — Raw Materials $5,000, Credit Accrued Purchases $5,000

### Task 2: Record the Mar 12 Component Issue
What is the journal entry? What WIP value results?
**Answer**: Debit Inventory — WIP $5,000, Credit Inventory — Raw Materials $5,000. WIP = $5,000.

### Task 3: Record the Mar 14 Work Order Completion
What is the journal entry? What is the total cost per unit?
**Answer**: Debit Inventory — Finished Goods $8,000, Credit Inventory — WIP $5,000, Credit Accrued Payroll $2,000, Credit Overhead Applied $1,000. Cost per unit: $8,000 / 500 = **$16/unit**.

### Task 4: Record the Mar 18 Fulfillment
What is the journal entry? What is COGS?
**Answer**: Debit COGS $2,400, Credit Inventory — Finished Goods $2,400. COGS = 200 units × $12 avg cost = $2,400.

### Task 5: Record the Mar 20 Invoice
What is the journal entry?
**Answer**: Debit AR $5,000, Credit Sales Revenue $5,000.

### Task 6: Record the Mar 25 Vendor Bill
What is the journal entry?
**Answer**: Debit Accrued Purchases $5,000, Credit AP $5,000.

### Task 7: Record the Mar 28 Customer Payment
What is the journal entry?
**Answer**: Debit Cash $5,000, Credit AR $5,000.

### Task 8: Record the Mar 31 Depreciation
What is the journal entry?
**Answer**: Debit Operating Expenses $500, Credit Accumulated Depreciation $500.

### Task 9: Prepare the Trial Balance
What are the ending balances in Cash, AR, Inventory — Finished Goods, AP, Revenue, COGS, and Operating Expenses?

**Answers**:
- Cash: $5,000 (from payment)
- AR: $0 (paid)
- Inventory — Finished Goods: $5,600 (300 units × $12 + new units at $16)
- AP: $5,000 (steel bill)
- Revenue: $5,000
- COGS: $2,400
- Operating Expenses: $500 (depreciation)

### Task 10: Calculate Gross Profit and Net Income
**Answers**:
- Gross Profit: $5,000 - $2,400 = **$2,600**
- Gross Margin: 52%
- Net Income: $2,600 - $500 = **$2,100**

## What You Learned

This scenario traced transactions from purchasing through financial statements — the complete Record-to-Report lifecycle. Each task demonstrated how operational activity creates accounting entries that ultimately appear in financial reports.

## Related Articles

- [What Is Record-to-Report?](what-is-record-to-report.md)
- [Financial Statements](financial-statements.md)
- [Period Close](period-close.md)
- [Journal Entries](journal-entries.md)
- [The General Ledger](the-general-ledger.md)

## Oracle References

- [Oracle NetSuite Help Center: Record-to-Report](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)