---
title: Approval Workflows
module: Purchasing
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Approval Workflows

## Quick Summary

Approval workflows automate the routing of purchase documents — requisitions, POs, and vendor bills — through the appropriate approvers based on value, department, item type, or other criteria. Workflows enforce purchasing controls without manual intervention.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Overview

Not every purchase should be approved by the same person. A $50 office supply order needs less oversight than a $50,000 equipment purchase. Approval workflows define who can approve what, at what thresholds, and under what conditions. They are the enforcement mechanism for purchasing policy.

## Why Approval Workflows Matter

| Without Workflows | With Workflows |
|---|---|
| Approvers manually track requests | System routes documents automatically |
| Approvals are inconsistent | Approvals follow defined rules |
| No audit trail of who approved what | Complete approval history |
| Delays from lost or forgotten requests | Automatic reminders and escalation |
| Policy violations go unnoticed | Policy is enforced systematically |

## Approval Levels

| Level | Approver | Typical Threshold |
|---|---|---|
| **Level 1** | Department Manager | Up to $5,000 |
| **Level 2** | Purchasing Manager | $5,000 - $25,000 |
| **Level 3** | Finance Director | $25,000 - $100,000 |
| **Level 4** | VP / C-Level | $100,000 - $500,000 |
| **Level 5** | Board / Executive Committee | Over $500,000 |

## Approval Criteria

Workflows can route documents based on:

| Criterion | Example |
|---|---|
| **Total amount** | POs over $10,000 go to finance |
| **Department** | IT purchases go to IT manager |
| **Item type** | Capital equipment requires CFO approval |
| **Vendor** | New vendors require purchasing manager approval |
| **Project** | Project-related purchases go to project manager |
| **Budget** | Purchases exceeding budget require finance approval |
| **Location** | Regional purchases approved by regional manager |

## Workflow Types

### Sequential Approval

Each approver reviews in sequence. The document moves through each level:

```
Requester → Manager → Director → VP
```

### Parallel Approval

Multiple approvers review simultaneously. All must approve:

```
Requester → Manager (and) Finance (and) Legal
```

### Conditional Approval

Routing depends on document attributes:

```
PO < $5,000 → Manager only
PO $5,000-$25,000 → Manager + Purchasing Manager
PO > $25,000 → Manager + Purchasing Manager + Finance Director
```

### Escalation

If an approver does not act within a defined time, the document escalates to the next level:

```
Manager (2 days) → Director (2 days) → VP (auto-approves after 5 days)
```

## Setting Up Approval Workflows in NetSuite

NetSuite workflows are created using the Workflow Manager:

```
Customization > Workflow > Workflows > New
```

A PO approval workflow typically includes:

1. **Trigger**: When a PO status changes to "Pending Approval"
2. **Condition**: Check PO total, department, item type
3. **Action**: Send approval request to the appropriate approver
4. **Approval**: If approved, change status to "Approved"
5. **Rejection**: If rejected, change status to "Rejected" and notify requester
6. **Escalation**: If no response in 48 hours, notify next-level approver

## Purchase Requisition Approval vs. PO Approval

Some organizations approve at both stages:

| Document | Approval Focus |
|---|---|
| **Purchase Requisition** | Budget availability, business need |
| **Purchase Order** | Vendor selection, pricing, terms |

Other organizations approve only at the PO stage, treating the requisition as an informational request. The right approach depends on the organization's size and control requirements.

## Business Example

A mid-sized company uses the following approval matrix:

| Purchase Value | Requisition Approval | PO Approval |
|---|---|---|
| $0 - $500 | Not required | Department Manager |
| $500 - $5,000 | Department Manager | Purchasing Manager |
| $5,000 - $25,000 | Department Manager | Purchasing Manager + Finance Manager |
| $25,000+ | Department + Finance Manager | VP Operations + CFO |

A $15,000 equipment purchase flows:

1. Requisition: Department Manager approves (budget exists)
2. PO created by purchasing
3. Workflow routes PO to Purchasing Manager (vendor selection review)
4. Purchasing Manager approves
5. Workflow routes PO to Finance Manager (budget confirmation)
6. Finance Manager approves
7. PO is approved and sent to vendor

## Common Mistakes

- **Approval workflows that are too complex**: Seven-layer approval for a $100 purchase creates unnecessary delay
- **No escalation rules**: Documents stuck at an approver who is on vacation block the entire process
- **Approval by people without budget visibility**: Approvers need to see the budget impact of what they are approving
- **Not documenting approval thresholds**: When thresholds are informal, approval routing is inconsistent
- **No emergency override process**: There should be a documented process for urgent purchases that bypass normal approval

## Best Practices

- Define approval thresholds based on risk, not just dollar value
- Build escalation timeouts into every workflow (48 hours is common)
- Test workflow routing with sample documents before going live
- Provide approvers with dashboard visibility into pending approvals
- Review approval workflow effectiveness quarterly — adjust thresholds as the business changes
- Log all approval actions for audit trail purposes

## Knowledge Check

1. A $30,000 PO has been waiting for the purchasing manager's approval for 5 days. The manager is on vacation. What should happen? (Answer: The workflow should escalate to the next-level approver after 48 hours.)
2. **Scenario**: Your company has 5 departments, each with its own budget. How should approval workflows be structured? (Answer: Route by department first, then by value threshold within each department.)
3. **Decision**: Should requisitions and POs both require approval, or is one enough? (Answer: It depends on the organization. For tighter control, approve both. For simpler operations, approve at the PO stage only.)

## Related Articles

- [Purchase Orders](purchase-orders.md)
- [Purchase Requisitions](purchase-requisitions.md)
- [Purchasing Controls](purchasing-controls.md)
- [Administration: Permissions](../administration/permissions.md)

## Oracle References

- [Oracle NetSuite Help Center: Approval Workflows](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Workflow Manager](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)