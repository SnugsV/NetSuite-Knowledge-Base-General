# Purchasing Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "Why can't I create a purchase order?" | PO creation |
| "The PO won't approve — it's stuck." | PO approval |
| "I received goods but the PO doesn't show it." | Item Receipt |
| "The vendor bill doesn't match the PO." | Three-way matching |
| "I can't pay this vendor bill." | AP payment |
| "Why is the PO showing the wrong price?" | Vendor pricing |
| "The vendor was paid twice." | Duplicate payment |

## Questions to Ask First

1. What is the PO number or vendor bill number?
2. When did the problem start?
3. What is the exact error message (if any)?
4. Has this vendor, item, or user worked before?
5. Were there any recent changes to purchasing settings or permissions?
6. What is the current status of the affected document?

## Information Required Before Troubleshooting

- Document number (PO, vendor bill, item receipt)
- Vendor name and ID
- Item and quantity involved
- User who created or attempted the transaction
- Error message text
- Date and time of the attempted action
- Any workflow or approval process involved

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| PO won't create | Item record (is it active?), vendor record (is it active?), user permissions |
| PO stuck on approval | Approval workflow configuration, approver's queue, approver's permissions |
| Item Receipt not showing | PO status (is it still Open?), receiving location, quantity already received |
| Vendor bill mismatch | PO price, receipt quantity, bill quantity and price |
| Can't pay bill | Bill status (approved?), payment terms, vendor payment method |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| PO won't create | 1. User lacks PO Create permission. 2. Vendor is on hold or inactive. 3. Item is inactive or out of stock. |
| PO stuck on approval | 1. Approver is out of office. 2. Workflow is misconfigured. 3. Approval threshold exceeded without escalation. |
| Bill doesn't match PO | 1. PO price was updated after the bill was created. 2. Bill was entered for the wrong PO. 3. Quantity tolerance exceeded. |
| Duplicate payment | 1. Bill was entered twice. 2. Payment was applied to the wrong bill. 3. EDI or integration created a duplicate. |

## Support Conversation Pattern

**Customer says**: "I created a vendor bill but it won't let me pay it."

**Interpretation**: The bill may not be approved, or payment terms haven't been met, or there's a payment method configuration issue.

**Questions to ask**:
- What is the vendor bill number?
- What is its current status?
- What payment method are you trying to use?
- Is the vendor's payment method configured?

**Evidence required**: Bill status, payment method, vendor payment configuration, user permissions.

**Most likely causes**:
1. Bill is not yet approved (most common)
2. Vendor payment method is not set up
3. User lacks bill payment permission

**Verification steps**:
1. Check bill status: is it Approved?
2. Check vendor record: is a payment method configured?
3. Check user role: does the user have Bill Payment permission?

**Recommended solution**:
- If not approved: Route for approval or check workflow configuration
- If no payment method: Configure on the vendor record
- If permission issue: Assign appropriate role

**Escalate if**: The bill is approved, payment method is configured, user has permission, and it still won't process.

## Related Saved Searches

- Open POs by vendor
- Bills pending approval
- Unpaid bills by due date
- Vendor payment history

## Related Workflows

- PO Approval Workflow
- Bill Approval Workflow
- Payment Approval Workflow

## Related SuiteScript Considerations

- Custom PO creation scripts may override standard pricing or approval logic
- Integration scripts may create bills or payments automatically
- Custom workflows may add additional approval steps not visible in standard UI

## Related Modules

- [Inventory Management](../inventory/README.md)
- [Sales](../sales/README.md)
- [Accounting](../accounting/README.md)

## Escalation Criteria

Escalate when:
- A data integrity issue is suspected (duplicate records, orphaned transactions)
- A SuiteScript customization is malfunctioning
- An integration is pushing incorrect data
- The root cause cannot be identified after checking all likely causes

## Oracle References

- [Oracle NetSuite Help Center: Purchasing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Purchase Orders](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Vendor Bills](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)