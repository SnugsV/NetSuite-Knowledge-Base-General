---
title: Pacejet Post-Shipment Troubleshooting
module: Integrations
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Pacejet Tracking, Void, Reprint, and Post-Shipment Troubleshooting

## Quick Summary

After a label is created, the main risks are duplicate shipments, incorrect void/reprint handling, missing tracking writeback, shipment edits, and reconciliation differences between NetSuite, Pacejet, and the carrier.

## Public-Safe Boundary

Keep examples generic. Do not publish tracking numbers, customer names, order numbers, labels, carrier account details, claims data, screenshots, logs, or private warehouse procedures.

## First Questions to Ask

1. Was a label created?
2. Was tracking assigned?
3. Is the user trying to void, reprint, change, track, return, or reconcile a shipment?
4. Is the issue in NetSuite, Pacejet, or the carrier site?
5. Did someone retry shipment creation after an error?
6. Did the order or fulfillment change after shipping?
7. Is this a single-package or multi-package shipment?

## Diagnostic Layers

### Layer 1: Shipment State

Check:

- Label created
- Tracking assigned
- Shipment confirmed
- Shipment voided
- Reprint available
- Carrier accepted the shipment

### Layer 2: NetSuite State

Check:

- Item Fulfillment status
- Tracking fields
- Carrier/service fields
- Package count
- Shipment cost
- Downstream invoice or notification state

### Layer 3: Pacejet and Carrier Alignment

Check:

- Pacejet shipment record state
- Carrier tracking state
- Void confirmation
- Reprint history
- Multi-package tracking
- Carrier pickup or manifest/end-of-day process if applicable

### Layer 4: Post-Shipment Changes

Check:

- Fulfillment edited after label
- Address changed after shipment
- Package count changed after label
- Carrier/service changed after label
- Credit, return, or reship process started

## Common Symptoms

### Tracking Missing in NetSuite

Likely causes:

- Writeback failed
- Label created after NetSuite update timeout
- Role or workflow blocked update
- Multi-package tracking did not fully write back
- User printed label outside normal flow

### Need to Reprint Label

Likely considerations:

- Reprint existing label if shipment already exists
- Do not create a new shipment unless the original is voided or intentionally replaced
- Confirm carrier and tracking state before reprocessing

### Need to Void Shipment

Likely considerations:

- Confirm shipment can still be voided
- Confirm carrier accepted void
- Confirm NetSuite reflects voided or replacement state
- Confirm downstream billing or customer notification impact

### Duplicate Shipment Risk

Likely causes:

- Retry after timeout
- Label exists in Pacejet but not NetSuite
- User starts ship-again flow instead of reprint
- Duplicate fulfillment or copied transaction

## Safe Diagnostic Path

1. Confirm whether tracking/label already exists.
2. Check NetSuite, Pacejet, and carrier state before retrying.
3. Use reprint for existing labels when appropriate.
4. Use void workflow before replacement shipment when required.
5. Confirm NetSuite writeback and customer notification impact.
6. Document post-shipment exception handling privately if implementation-specific.

## AI Assistant Response Pattern

When a user asks about tracking, void, or reprint, the assistant should:

1. Ask whether a label and tracking number already exist.
2. Ask whether the requested action is reprint, void, replace, return, or reconcile.
3. Diagnose shipment state, NetSuite state, Pacejet/carrier alignment, and post-shipment changes.
4. Warn against creating a new shipment when reprint or void is the correct path.
5. Keep tracking, label, and customer details private.

## Related Articles

- [Advanced Pacejet Troubleshooting](advanced-troubleshooting.md)
- [Label Generation and Carrier Error Troubleshooting](pacejet-label-carrier-error-troubleshooting.md)
- [NetSuite Fulfillment and Shipment Status Flow](pacejet-fulfillment-shipment-status-flow.md)
- [Core Shipping Workflow](shipping-workflow.md)
