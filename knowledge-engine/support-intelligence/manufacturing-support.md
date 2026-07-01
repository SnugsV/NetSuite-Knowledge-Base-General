# Manufacturing Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "The work order won't build." | Work order completion |
| "Components were not consumed." | Backflushing |
| "WIP balance is wrong." | WIP accounting |
| "The assembly cost is incorrect." | Manufacturing costing |
| "The BOM is missing components." | BOM setup |
| "Why can't I issue components?" | Component issuing |
| "The routing is not applying correctly." | Routings |

## Questions to Ask First

1. What is the work order number?
2. What is the current status of the work order?
3. When was it created and when was the last update?
4. Are all components available in inventory?
5. Is backflushing enabled?
6. Has the work order been modified after creation?

## Information Required Before Troubleshooting

- Work order number
- Assembly item name
- BOM revision being used
- Component items and quantities
- Current WIP balance for the work order
- Actual vs. expected costs

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| Won't build | Work order status, component availability, BOM revision, assembly item setup |
| Components not consumed | Backflushing configuration, BOM quantities, build completion date |
| WIP wrong | Open work orders, issued vs. consumed components, period close status |
| Assembly cost wrong | Component costs, BOM quantities, routing setup, overhead allocation |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| Work order won't build | 1. Components out of stock. 2. BOM revision not current. 3. Work order not in Released status. 4. Assembly item not set up correctly. |
| Components not consumed (backflushing) | 1. Backflushing not enabled on the item. 2. BOM quantity is zero. 3. Component was already issued manually. |
| WIP discrepancy | 1. Components issued but not built. 2. Work order built but not closed. 3. Negative on-hand in WIP location. |

## Support Conversation Pattern

**Customer says**: "I built the work order but the components were not consumed from inventory."

**Interpretation**: The work order was marked complete but the system did not reduce inventory for the components, or it consumed a different quantity than expected.

**Questions to ask**:
- Was the work order built using the Build button or manually completed?
- Is backflushing enabled for the assembly item?
- Were any components already issued manually before the build?
- What is the current On Hand vs. what you expected?

**Evidence required**: Work order history, BOM quantities, component inventory levels, backflushing settings.

**Most likely causes**:
1. Backflushing is not enabled for this assembly item
2. Backflushing is enabled but the BOM quantity is set to zero
3. Components were manually issued, then backflushing also tried to consume them
4. Work order was completed through a custom script or integration

**Verification steps**:
1. Check the assembly item record for backflushing configuration
2. Verify BOM component quantities are correct
3. Check work order history for component issue transactions
4. Review any custom scripts that may affect build behavior

**Recommended solution**:
- If backflushing is off: Enable it, or manually issue the components
- If BOM quantity is zero: Correct the BOM and rebuild
- If double-consumed: Check for duplicate issue transactions and adjust

**Escalate if**: The work order involves custom SuiteScript that controls build behavior, or the component quantity discrepancy is large and unexplained.

## Related Saved Searches

- Open work orders by age
- Work orders with negative WIP
- Component shortage report
- Work order cost variance
- BOM revision history

## Related Workflows

- Work Order Approval Workflow
- Backflushing Workflow
- Manufacturing Order Workflow

## Related SuiteScript Considerations

- Custom build scripts may override standard backflushing behavior
- Integration scripts may create or modify work orders automatically
- Custom cost calculation scripts may affect assembly valuation

## Related Modules

- [Inventory Management](../inventory/README.md) — component availability
- [Purchasing](../purchasing/README.md) — raw material procurement
- [Accounting](../accounting/README.md) — WIP, costing, COGS

## Escalation Criteria

Escalate when:
- WIP balance cannot be reconciled after checking all work orders
- SuiteScript controlling work order behavior is malfunctioning
- Manufacturing cost variance exceeds 10% without clear cause
- BOM or routing data corruption is suspected

## Oracle References

- [Oracle NetSuite Help Center: Manufacturing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Work Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: WIP](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)