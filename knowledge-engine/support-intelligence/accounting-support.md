# Accounting Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "The GL balance is wrong." | GL reconciliation |
| "The trial balance doesn't balance." | Trial balance |
| "I can't close the period." | Period close |
| "Revenue was recognized too early." | Revenue recognition |
| "COGS seems too high." | COGS analysis |
| "AP and GL don't match." | Subledger reconciliation |
| "The deferred revenue balance is wrong." | Deferred revenue |

## Questions to Ask First

1. Which account or period is affected?
2. What is the expected balance vs. the actual balance?
3. When did the problem start (which period)?
4. Were there any system updates or configuration changes?
5. Have all transactions for the period been posted?
6. Are subledgers (AP, AR, Inventory) in balance with the GL?

## Information Required Before Troubleshooting

- Account number and name
- Period and fiscal year
- Expected balance and actual balance from trial balance
- Subledger detail for the account
- Recent journal entries posted to the account
- Period close status

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| GL balance wrong | Trial balance for the account, subledger detail, recent journal entries |
| Trial balance doesn't balance | Unposted transactions, journal entries with unequal debits/credits |
| Can't close period | Unposted transactions, unreconciled accounts, open periods |
| Revenue recognized early | Revenue arrangement setup, fulfillment dates, revenue recognition schedule |
| COGS too high | Item fulfillments, average cost changes, large adjustments |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| GL/AP mismatch | 1. Bill entered but not yet posted to GL. 2. Payment posted but not applied. 3. Time lag between subledger and GL posting. |
| Trial balance out of balance | 1. Journal entry with unequal debits and credits. 2. System posting error. 3. Intercompany transaction not balanced. |
| Can't close period | 1. Unposted transactions exist. 2. Bank account not reconciled. 3. Inventory transactions not completed. 4. Period has unreconciled differences. |
| COGS spike | 1. Average cost increased due to higher-cost receipt. 2. Large inventory adjustment. 3. Valuation method change. |

## Support Conversation Pattern

**Customer says**: "I'm trying to close the month but the system won't let me."

**Interpretation**: The period close validation has identified one or more conditions that prevent closing. These are typically unposted transactions, unreconciled accounts, or open subledger items.

**Questions to ask**:
- What error message is shown?
- Which period are you trying to close?
- Have all AP, AR, and inventory transactions been posted?
- Are all bank accounts reconciled?
- Are there any unapproved journal entries?

**Evidence required**: Error message, period close checklist, unposted transaction report, reconciliation status.

**Most likely causes**:
1. Unposted transactions exist (most common)
2. Bank account not reconciled
3. Inventory subledger not in balance with GL
4. Unapproved journal entries
5. Intercompany accounts not reconciled

**Verification steps**:
1. Run the unposted transactions report
2. Check bank reconciliation status
3. Compare AP/AR subledger totals to GL balances
4. Review pending journal entries
5. Run the period close readiness report

**Recommended solution**:
- Post all unposted transactions
- Complete bank reconciliation
- Reconcile subledgers to GL
- Approve or reverse pending journal entries

**Escalate if**: The period close issue is caused by a data integrity problem, or if the system is reporting an error that doesn't correspond to any visible condition.

## Related Saved Searches

- Unposted transactions
- Journal entries by period
- GL impact by transaction type
- AP aging by GL account
- AR aging by GL account
- Inventory valuation by location

## Related Workflows

- Period Close Workflow
- Journal Entry Approval Workflow
- Month-End Checklist Workflow

## Related SuiteScript Considerations

- Custom allocation scripts may post journal entries affecting the close
- Integration scripts may create transactions that need to post before close
- Custom period close validation may add additional checks

## Related Modules

- [Purchasing](../purchasing/README.md) — AP
- [Sales](../sales/README.md) — AR, revenue
- [Inventory](../inventory/README.md) — valuation
- [Manufacturing](../manufacturing/README.md) — WIP

## Escalation Criteria

Escalate when:
- Trial balance cannot be balanced after all checks
- Data integrity issue (missing journal entries, corrupted GL balances)
- Period close validation is producing false errors
- Integration is creating transactions that cannot be posted

## Oracle References

- [Oracle NetSuite Help Center: Accounting](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Period Close](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Trial Balance](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)