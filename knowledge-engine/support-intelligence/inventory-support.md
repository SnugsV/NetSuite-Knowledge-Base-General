# Inventory Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "Inventory quantities are wrong." | Quantity accuracy |
| "The inventory value doesn't make sense." | Valuation |
| "Why can't I transfer inventory?" | Transfers |
| "The item won't fulfill." | Fulfillment blocking |
| "Negative on-hand quantities." | Quantity errors |
| "Why is the average cost changing?" | Costing |
| "I can't adjust inventory." | Adjustments |

## Questions to Ask First

1. What item and location are affected?
2. What quantity does the system show vs. what do you expect?
3. When did the problem start?
4. Was there a recent receipt, fulfillment, or adjustment?
5. Is this affecting one item or multiple items?
6. Are you using multi-location or Advanced Inventory?

## Information Required Before Troubleshooting

- Item name/number
- Location
- Current system quantity and expected quantity
- Recent transactions affecting the item (receipts, fulfillments, adjustments)
- Valuation method (average, standard, FIFO)
- Whether bins, lots, or serials are used

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| Quantity wrong | Item record: On Hand, Available, Committed, On Order |
| Value wrong | Average cost history, recent receipts with different costs |
| Can't transfer | Transfer order status, location setup, item location setup |
| Negative on-hand | Recent fulfillments or adjustments that over-consumed |
| Can't adjust | User permissions, period status (open?), item status |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| Quantity mismatch | 1. Receipt or fulfillment not entered. 2. Duplicate transaction. 3. Adjustment needed for physical count difference. |
| Unexpected cost change | 1. Receipt at different price changed average cost. 2. Landed cost allocation. 3. Inventory adjustment with value change. |
| Negative on-hand | 1. Fulfilled more than available. 2. Adjustment reduced below zero. 3. Back-dated receipt corrected after fulfillment. |
| Transfer won't complete | 1. Destination location not set up for the item. 2. Bin required but not specified. 3. In-transit inventory not received. |

## Support Conversation Pattern

**Customer says**: "The inventory count for item STEEL-100 shows 500 units, but I know we only have 300."

**Interpretation**: The system quantity does not match the physical count. This could be caused by unrecorded transactions, data entry errors, or process gaps.

**Questions to ask**:
- When was the last physical count or cycle count performed?
- Are there any open work orders consuming this item?
- Was there a recent receipt or return that might not be entered?
- Has there been any theft or damage not recorded?

**Evidence required**: Item record showing On Hand, Available, Committed quantities. Recent transaction history for the item. Any cycle count or adjustment records.

**Most likely causes**:
1. A receipt was entered but items were not physically received
2. A fulfillment was processed but items were not physically picked
3. An adjustment was made without physical verification
4. The item is in a different location than the system shows
5. Cycle counts have not been performed recently

**Verification steps**:
1. Review the item's transaction history for the past 30 days
2. Compare each receipt to physical inbound records
3. Compare each fulfillment to outbound shipping records
4. Check for unprocessed transfer orders
5. Perform a cycle count to confirm physical quantity

**Recommended solution**:
- If missing transactions are found: Enter the missing receipt or adjustment
- If quantities cannot be reconciled: Perform a full physical count and adjust
- If process gap exists: Implement cycle counting for this item

**Escalate if**: The discrepancy is large (>5% of item value), involves multiple items, or cannot be explained after reviewing all recent transactions.

## Related Saved Searches

- Items with negative on-hand
- Items below reorder point
- Inventory value by location
- Adjustment history by item
- Transaction history for an item
- Items with no movement in 90 days

## Related Workflows

- Inventory Adjustment Approval Workflow
- Cycle Count Schedule Workflow
- Physical Count Workflow

## Related SuiteScript Considerations

- Custom inventory valuation scripts may override standard costing
- Integration scripts may create receipts or fulfillments automatically
- Custom bin management scripts may affect location assignment

## Related Modules

- [Purchasing](../purchasing/README.md) — receipts
- [Sales](../sales/README.md) — fulfillments
- [Manufacturing](../manufacturing/README.md) — work order consumption
- [Accounting](../accounting/README.md) — valuation, COGS

## Escalation Criteria

Escalate when:
- Inventory value appears incorrect by more than 5%
- Negative quantities cannot be resolved
- Data integrity issue (duplicate item records, orphaned transactions)
- Landed cost allocation produces unexpected results
- Standard cost variance exceeds 10% without explanation

## Oracle References

- [Oracle NetSuite Help Center: Inventory](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Inventory Adjustments](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Average Costing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)