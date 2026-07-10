---
title: Pacejet Fulfillment and Shipment Status Flow
module: Integrations
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Pacejet NetSuite Fulfillment and Shipment Status Flow

## Quick Summary

Pacejet shipping starts from NetSuite fulfillment context. Many shipping issues are actually Item Fulfillment status, transaction lifecycle, role, workflow, script, or writeback issues.

## Public-Safe Boundary

Keep examples generic. Do not publish order numbers, fulfillment numbers, tracking numbers, customer names, custom field IDs, scripts, workflows, screenshots, logs, or private warehouse procedures.

## First Questions to Ask

1. What NetSuite record is involved: sales order, item fulfillment, invoice, return authorization, transfer order, or another record?
2. What action is failing: rate, ship, label, writeback, fulfill, close, invoice, void, reprint, or track?
3. What is the current fulfillment status?
4. Was the fulfillment created manually, by automation, by CSV/import, or by another integration?
5. Did Pacejet create a shipment or label before NetSuite failed to update?
6. Are workflows, scripts, approvals, or role restrictions involved?

## Diagnostic Layers

### Layer 1: Source Transaction

Check:

- Sales order status
- Fulfillment status
- Quantity committed, picked, packed, or shipped
- Location and ship-from context
- Customer and ship-to address
- Shipping method and service preference

### Layer 2: Item Fulfillment Readiness

Check:

- Item Fulfillment exists
- Fulfillment is editable or shippable
- Required shipping fields are present
- Lines and quantities match shipment expectation
- Fulfillment was not already shipped or closed

### Layer 3: Pacejet Shipment State

Check:

- Shipment created
- Rates returned
- Carrier selected
- Label generated
- Tracking assigned
- Void or reprint state

### Layer 4: NetSuite Writeback

Check:

- Tracking field update
- Carrier and service update
- Shipment cost update
- Package details update
- Record lock or workflow/script validation
- User or integration role permission

### Layer 5: Downstream Transaction Flow

Check:

- Whether shipment completion triggers invoicing
- Whether fulfillment status affects customer notification
- Whether tracking must be visible before billing
- Whether edits after shipping create mismatch

## Common Symptoms

### Fulfillment Cannot Be Shipped

Likely causes:

- Fulfillment not ready
- Missing ship-to or origin data
- Required package data missing
- Already shipped or closed
- Workflow/script blocks action
- Role lacks permission

### Pacejet Shipped but NetSuite Did Not Update

Likely causes:

- Writeback failed
- NetSuite record locked
- Script or workflow validation blocked update
- Role permissions
- Timeout after carrier label creation

### NetSuite Shows Shipped but Pacejet State Looks Different

Likely causes:

- Manual update in NetSuite
- Partial writeback
- Duplicate or retried shipment
- Void or reprint not reflected consistently
- Shipment was changed after label generation

### Invoice or Customer Notification Did Not Happen

Likely causes:

- Fulfillment status not updated as expected
- Tracking missing
- Workflow or script condition not met
- Billing process requires a different status
- Email/notification process separate from Pacejet shipping

## Safe Diagnostic Path

1. Identify source transaction and Item Fulfillment status.
2. Confirm whether Pacejet shipment and label already exist.
3. Check fulfillment readiness and required data.
4. Check Pacejet shipment state.
5. Check NetSuite writeback and role/workflow/script blockers.
6. Confirm downstream billing or notification dependencies.
7. Avoid recreating shipments until duplicate risk is understood.

## AI Assistant Response Pattern

When a user asks why Pacejet did not update NetSuite, the assistant should:

1. Ask whether label/tracking exists in Pacejet.
2. Ask current Item Fulfillment status and the failed action.
3. Diagnose source transaction, fulfillment readiness, Pacejet shipment state, NetSuite writeback, and downstream flow.
4. Warn against recreating shipments before checking existing label/tracking state.
5. Keep order, tracking, and implementation details private.

## Related Articles

- [Advanced Pacejet Troubleshooting](advanced-troubleshooting.md)
- [Core Shipping Workflow](shipping-workflow.md)
- [Label Generation and Carrier Error Troubleshooting](pacejet-label-carrier-error-troubleshooting.md)
- [Tracking, Void, Reprint, and Post-Shipment Troubleshooting](pacejet-post-shipment-troubleshooting.md)
