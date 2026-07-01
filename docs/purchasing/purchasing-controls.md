---
title: Purchasing Controls
module: Purchasing
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Purchasing Controls

## Quick Summary

Purchasing controls are policies, permissions, and system configurations that govern who can purchase what, up to what value, and under what conditions. Effective controls prevent unauthorized spending, reduce fraud risk, and ensure policy compliance.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Procurement involves spending company money. Without controls, any user could commit the organization to any purchase from any vendor at any price. Purchasing controls establish boundaries: who can create POs, who can approve them, what items can be purchased, and from which vendors.

## Control Categories

### Segregation of Duties

The most important control. No single person should have the ability to complete all stages of a purchase:

| Role | Can Create PO | Can Approve PO | Can Receive Items | Can Enter Bill | Can Issue Payment |
|---|---|---|---|---|---|
| Requester | Yes | No | No | No | No |
| Purchasing Agent | Yes | No | No | No | No |
| Approver | No | Yes | No | No | No |
| Receiver | No | No | Yes | No | No |
| AP Clerk | No | No | No | Yes | No |
| Payment Processor | No | No | No | No | Yes |

When duties are segregated, fraud requires collusion between at least two people.

### Permission-Based Controls

In NetSuite, permissions control who can perform each purchasing action:

| Permission | What It Controls |
|---|---|
| **Purchase Order — Create** | Who can create POs |
| **Purchase Order — Approve** | Who can approve POs |
| **Vendor Bill — Create** | Who can enter bills |
| **Vendor Bill — Approve** | Who can approve bills for payment |
| **Item Receipt — Create** | Who can receive items |
| **Vendor Record — Edit** | Who can change vendor information |

### Spending Limits

| Limit Type | How It Works |
|---|---|
| **PO Approval Threshold** | POs above the threshold require higher-level approval |
| **User Spending Limit** | Maximum PO value a user can create |
| **Department Budget** | Total spending limit per department |
| **Vendor Credit Limit** | Maximum exposure per vendor |
| **Item Price Tolerance** | Maximum price variance from standard cost |

### Vendor Controls

- **Approved vendor list** — Only approved vendors can be used
- **New vendor approval** — New vendors require approval before first PO
- **Vendor hold** — Suspend purchasing from a vendor temporarily
- **1099 tracking** — Ensure tax-compliant vendor records

## Implementing Controls in NetSuite

### Role and Permission Configuration

1. Create purchasing roles that reflect the organization's structure
2. Assign appropriate permissions to each role
3. Ensure no role has conflicting permissions (e.g., PO Create and PO Approve)

See [Administration: Permissions](../administration/permissions.md) for detailed guidance.

### Approval Workflow Rules

1. Define approval thresholds by role, department, and purchase type
2. Configure workflows to enforce these rules automatically
3. Set up escalation for overdue approvals

See [Approval Workflows](approval-workflows.md) for configuration details.

### Vendor Approval Policies

1. Require W-9 and banking information before vendor activation
2. Implement new vendor approval workflow
3. Regularly review vendor master for inactive or duplicate records

## Red Flags and Warning Signs

| Red Flag | Possible Issue |
|---|---|
| PO created and approved by the same user | Segregation of duties violation |
| Frequent POs just below approval threshold | Threshold avoidance |
| New vendor with no approval record | Vendor control bypass |
| PO to a vendor not on the approved list | Unauthorized vendor use |
| Bill entered before receipt | Potential advance payment or fraud |
| Vendor address matches employee address | Related-party transaction risk |

## Common Mistakes

- **Insufficient segregation of duties**: In small companies, the same person may fill multiple roles. At minimum, separate PO creation from PO approval and payment processing.
- **Thresholds that are too rigid**: A department that needs $5,100 should not require VP approval because of a $100 policy gap. Set thresholds with flexibility.
- **No vendor approval process**: Any user adding a vendor to the system can create a PO to that vendor. Control vendor creation.
- **Ignoring the audit trail**: Every purchasing action is logged. Review the audit trail periodically for unusual patterns.
- **Over-control**: Too many approval steps for low-value purchases frustrates employees and encourages policy bypass.

## Best Practices

- Segregate purchasing, receiving, and payment duties
- Require two-party approval for all POs over a defined threshold
- Implement vendor approval workflows for new vendors
- Review purchasing controls quarterly
- Use Saved Searches to monitor control exceptions (POs without receipts, bills without POs)
- Train all employees on purchasing policies
- Document control exceptions and the justification

## Knowledge Check

1. The same person creates POs and also approves them. What control issue does this create? (Answer: No segregation of duties — the person could create and approve unauthorized purchases.)
2. **Scenario**: A user creates a PO for $9,800. The approval threshold is $10,000. The user creates another PO for $9,500 the same week. What might be happening? (Answer: Threshold avoidance — splitting purchases to stay under the approval limit.)
3. **True/False**: A small company with only 3 employees cannot implement segregation of duties. (Answer: Partially true — with 3 employees, complete segregation is difficult. Mitigate with regular management review of the audit trail.)

## Related Articles

- [Approval Workflows](approval-workflows.md)
- [Three-Way Matching](three-way-matching.md)
- [Purchase Orders](purchase-orders.md)
- [Administration: Permissions](../administration/permissions.md)
- [Administration: Audit Trail](../administration/audit-trail.md)

## Oracle References

- [Oracle NetSuite Help Center: Purchasing Controls](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)