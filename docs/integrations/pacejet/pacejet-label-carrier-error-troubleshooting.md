---
title: Pacejet Label Generation and Carrier Error Troubleshooting
module: Integrations
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Pacejet Label Generation and Carrier Error Troubleshooting

## Quick Summary

Label failures usually happen after rating, when final shipment data is submitted to a carrier. Diagnose carrier response, package data, service eligibility, printer/output path, retry safety, and NetSuite writeback before reprocessing.

## Public-Safe Boundary

Keep examples generic. Do not publish labels, tracking numbers, customer addresses, carrier account numbers, credentials, production logs, screenshots, negotiated rates, or private warehouse procedures.

## First Questions to Ask

1. Did rating succeed before label generation failed?
2. Is the error from Pacejet, the carrier, NetSuite, printer/output, or a custom label process?
3. Does it happen for one carrier, one service, one package type, one warehouse, or all labels?
4. Was a label or tracking number created before the error appeared?
5. Is it safe to retry, or could retry create a duplicate shipment/label?
6. Are custom labels, thermal printers, or label connector tools involved?

## Diagnostic Layers

### Layer 1: Pre-Label Shipment Data

Check:

- Final carrier and service
- Ship-to and origin address
- Package count, weight, and dimensions
- Special services
- International/customs data if relevant
- Residential/commercial classification

### Layer 2: Carrier Response

Check:

- Authentication or account error
- Service unavailable
- Invalid package dimensions or weight
- Address issue
- Missing customs or special service data
- Carrier timeout or outage

### Layer 3: Pacejet Processing

Check:

- Shipment state
- Whether a label was created
- Whether tracking was assigned
- Whether carrier response was saved
- Whether reprint or void is the correct next action

### Layer 4: NetSuite Writeback

Check:

- Tracking number returned
- Item Fulfillment updated
- Carrier/service fields updated
- Shipment cost updated
- Workflow or script blocked writeback
- User permissions to view/update fields

### Layer 5: Printer and Output

Check:

- Label format
- Printer selection
- Thermal printer setup
- PDF vs ZPL or other printer language
- Browser/download behavior
- Custom label template issues

## Common Symptoms

### Rate Succeeds but Label Fails

Likely causes:

- Carrier accepts rating but rejects shipment creation
- Final package data changed
- Missing required service data
- Address or customs validation issue
- Carrier account lacks permission for service

### Label Generated but Did Not Print

Likely causes:

- Printer selection issue
- Label format mismatch
- Browser popup/download behavior
- Thermal printer configuration
- Custom label template or connector issue

### Tracking Exists but NetSuite Was Not Updated

Likely causes:

- Writeback failed
- User role or script permission issue
- NetSuite record locked or changed
- Workflow blocked update
- Integration timeout after carrier success

### Retry Creates Duplicate Risk

Likely causes:

- Carrier label was already created
- Tracking exists in Pacejet but not NetSuite
- User retries from the wrong state
- Void/reprint path should be used instead of ship-again path

## Safe Diagnostic Path

1. Determine whether a label/tracking number was already created.
2. Capture sanitized error text and timestamp.
3. Identify whether the error came from Pacejet, carrier, NetSuite, or printer/output.
4. Check final shipment data and carrier service requirements.
5. Check NetSuite writeback and record status.
6. Use reprint or void workflows when appropriate instead of blindly retrying shipment creation.
7. Escalate carrier account or production label issues through the proper support path.

## AI Assistant Response Pattern

When a user asks why a Pacejet label failed, the assistant should:

1. Ask whether rating succeeded and whether tracking or a label was created.
2. Ask where the error appeared: Pacejet, carrier, NetSuite, printer, or custom label path.
3. Diagnose shipment data, carrier response, Pacejet state, NetSuite writeback, and printer/output layers.
4. Warn against blind retry when a carrier label may already exist.
5. Keep label, tracking, customer, and carrier-account details private.

## Related Articles

- [Advanced Pacejet Troubleshooting](advanced-troubleshooting.md)
- [Packing, Weights, Dimensions, and Package Building](pacejet-packing-weight-dimension-diagnostics.md)
- [Tracking, Void, Reprint, and Post-Shipment Troubleshooting](pacejet-post-shipment-troubleshooting.md)
- [Label Generation](label-generation.md)
