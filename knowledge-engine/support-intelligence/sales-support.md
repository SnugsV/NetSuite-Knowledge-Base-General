# Sales Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "Why can't I create a sales order?" | SO creation |
| "The sales order won't approve." | SO approval |
| "We shipped the order but it still shows as not fulfilled." | Fulfillment |
| "The customer wasn't invoiced." | Invoicing |
| "Why is the invoice showing the wrong amount?" | Pricing |
| "The customer paid but the invoice is still open." | Payment application |
| "We need to process a return." | Return authorization |

## Questions to Ask First

1. What is the sales order or invoice number?
2. When did the problem start?
3. What is the exact error message?
4. Has this customer, item, or process worked before?
5. Were there any recent changes to sales settings or pricing?
6. What is the current status of the affected document?

## Information Required Before Troubleshooting

- Document number (SO, invoice, fulfillment, RA)
- Customer name and ID
- Item and quantity involved
- User who created or attempted the transaction
- Error message text
- Any credit or collection issues

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| SO won't create | Customer status (active?), item status, user permissions, credit limit |
| SO stuck on approval | Approval workflow, approver queue, credit hold status |
| Not fulfilled | SO status, inventory availability, location setup |
| Not invoiced | Fulfillment status (must be fulfilled first), invoice schedule |
| Wrong invoice amount | Price level, discount applied, quantity shipped vs. ordered |
| Payment not applied | Payment application method, invoice open balance, payment amount |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| SO won't create | 1. Customer on credit hold. 2. Item is inactive. 3. User lacks permission. 4. Customer not fully set up. |
| SO stuck on approval | 1. Credit hold threshold exceeded. 2. Approver is unavailable. 3. Workflow condition not met. |
| Not fulfilled | 1. Inventory not available. 2. SO is on hold. 3. Fulfillment location not set. |
| Payment not applied | 1. Payment was entered as unapplied. 2. Amount doesn't match invoice balance. 3. Customer payment was credited to wrong invoice. |

## Support Conversation Pattern

**Customer says**: "We shipped the order last week but the customer says they haven't received an invoice."

**Interpretation**: The fulfillment was processed but the invoice was either not created or not sent.

**Questions to ask**:
- What is the sales order number?
- Was the Item Fulfillment created?
- Was the invoice generated from the fulfillment?
- Is the invoice showing as "Sent" in the system?

**Evidence required**: Fulfillment record, invoice record, invoice delivery status.

**Most likely causes**:
1. Fulfillment was not created from the SO
2. Invoice was created but not sent to the customer
3. Invoice was created but for the wrong amount
4. Automated invoicing is not configured

**Verification steps**:
1. Check if Item Fulfillment exists for the SO
2. Check if an invoice exists linked to the fulfillment
3. Check invoice delivery method (email, print, EDI)
4. Check invoice status and balance

**Recommended solution**:
- If not fulfilled: Process the fulfillment
- If not invoiced: Create the invoice from the fulfillment
- If not sent: Resend the invoice via email
- Configure auto-invoicing if this is recurring

**Escalate if**: The fulfillment exists and the invoice exists but the customer still reports not receiving it (possible email delivery issue or integration failure).

## Related Saved Searches

- Open sales orders
- Orders pending fulfillment
- Invoices by customer
- Unpaid invoices aging
- Customer payment history

## Related Workflows

- Sales Order Approval Workflow
- Credit Check Workflow
- Automated Invoicing Workflow

## Related SuiteScript Considerations

- Custom pricing scripts may override standard price levels
- Integration scripts may create sales orders or invoices automatically
- Custom fulfillment workflows may add approval steps

## Related Modules

- [Inventory Management](../inventory/README.md)
- [Purchasing](../purchasing/README.md)
- [Accounting](../accounting/README.md)

## Escalation Criteria

Escalate when:
- Integration between NetSuite and e-commerce platform is failing
- Credit card payment gateway is not processing
- SuiteScript pricing engine is returning incorrect values
- Customer account shows data corruption (duplicate records, wrong balances)

## Oracle References

- [Oracle NetSuite Help Center: Sales](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Sales Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Invoicing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)