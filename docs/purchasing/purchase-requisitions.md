---
title: Purchase Requisitions
module: Purchasing
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Purchase Requisitions

## Quick Summary

A purchase requisition is an internal request for goods or services. It initiates the procurement process by documenting what is needed, by whom, for which department, and within what budget. Requisitions provide control before a purchase order is issued.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

Not everyone in an organization should be able to issue purchase orders. Purchase requisitions allow employees to request purchases while routing them through the appropriate approvals before any commitment to a vendor is made.

## Requisition vs. Purchase Order

| Dimension | Requisition | Purchase Order |
|---|---|---|
| **Purpose** | Internal request | External commitment |
| **Created by** | Any employee with request authority | Purchasing department |
| **Legal status** | No legal obligation | Legally binding contract |
| **Approval** | Budget and need approval | Procurement and financial approval |
| **Vendor** | May or may not specify vendor | Specifies vendor |
| **Converts to** | Can be converted to PO | End of the line |

## Requisition Workflow

```
Employee identifies need
       ↓
Creates purchase requisition in NetSuite
       ↓
Requisition routed for approval
       ↓
Approved → Purchasing creates PO
    or
Rejected → Requester revises or cancels
```

## When to Use Requisitions

| Situation | Requisition Required? |
|---|---|
| Low-value, routine purchase (< $500) | Optional — may use direct PO |
| Mid-value purchase ($500-$5,000) | Recommended |
| High-value purchase (> $5,000) | Required |
| Capital equipment purchase | Required |
| Non-stock items | Recommended |
| Services or consulting | Recommended |
| Emergency purchase | May bypass, but document after |

## Requisition Fields

When creating a purchase requisition:

| Field | Purpose |
|---|---|
| **Item / Description** | What is needed |
| **Quantity** | How many units |
| **Estimated Cost** | Expected price (may be an estimate) |
| **Department** | Who needs it |
| **Charge To** | Budget or project code |
| **Required Date** | When it is needed |
| **Vendor (optional)** | Preferred supplier |
| **Justification** | Business reason for the purchase |

## Approval Routing

Requisitions can be routed for approval based on:

- **Value**: Higher value → higher approval authority
- **Department**: Department manager approval required
- **Item type**: Capital equipment requires finance approval
- **Budget**: Requires budget holder approval
- **Project**: Requires project manager approval

In NetSuite, approval workflows can automate this routing. See [Approval Workflows](approval-workflows.md).

## Converting Requisitions to Purchase Orders

When a requisition is approved, a purchasing agent converts it to a purchase order:

1. Open the approved requisition
2. Click **Create Purchase Order** (or **Convert to PO**)
3. Review the details — item, quantity, vendor, price
4. Add any additional information needed for the PO
5. Save the PO
6. The requisition status updates to "Converted"

## Business Example

A marketing manager needs $3,000 of promotional materials for an upcoming trade show.

1. Manager creates a purchase requisition: 500 promo kits, estimated cost $3,000, department: Marketing, required date: 3 weeks out
2. Requisition is routed to the marketing director for budget approval
3. Marketing director approves
4. Requisition is routed to the purchasing department
5. Purchasing agent sources a vendor, creates a PO for $2,850 (negotiated better pricing)
6. PO is issued to the selected vendor
7. Status: Requisition shows "Converted," PO shows "Open"

## Common Mistakes

- **Bypassing requisitions for non-urgent purchases**: Emergency purchases should be rare. If every purchase is an emergency, the requisition process is not working.
- **Requisitions with insufficient detail**: "Miscellaneous supplies" is not a valid requisition. Specify what is needed and why.
- **No budget verification before requisition creation**: The requisition is the first control point. Verify budget availability before routing for approval.
- **Requisition approval without spending visibility**: If managers approve without seeing their department's total committed spend, they may over-commit.

## Best Practices

- Require purchase requisitions for all purchases above a defined threshold
- Integrate requisitions with budget tracking — the system should prevent requisitions that exceed available budget
- Set clear expectations for approval turnaround time
- Train employees on what information is required for a complete requisition
- Use Saved Searches to monitor requisition aging (time from creation to approval or rejection)

## Knowledge Check

1. Why use a purchase requisition instead of going directly to a purchase order? (Answer: Requisitions provide internal control, budget verification, and approval before any commitment to a vendor.)
2. **Scenario**: A $50,000 equipment purchase requisition is approved by the department manager. Is this sufficient? (Answer: No — high-value purchases typically require finance or executive approval beyond the department level.)
3. **Decision**: Your company has a policy that all purchases over $100 require a requisition. Is this appropriate? (Answer: Likely too restrictive — the approval overhead for $100 purchases exceeds the risk. Set thresholds that match the organization's risk profile.)

## Related Articles

- [Purchase Orders](purchase-orders.md)
- [Approval Workflows](approval-workflows.md)
- [What Is Procurement?](what-is-procurement.md)
- [Vendor Management](vendor-management.md)
- [Administration: Permissions](../administration/permissions.md)

## Oracle References

- [Oracle NetSuite Help Center: Purchase Requisitions](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)