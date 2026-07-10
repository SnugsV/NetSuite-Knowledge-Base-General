---
title: Pacejet Packing Weight Dimension Diagnostics
module: Integrations
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Pacejet Packing, Weights, Dimensions, and Package Building Diagnostics

## Quick Summary

Packing issues usually come from missing item weights, incorrect dimensions, package-building rules, cartonization assumptions, multi-package logic, or shipment edits after fulfillment. Diagnose the package data Pacejet receives before changing carrier services or rates.

## Public-Safe Boundary

Keep examples generic. Do not publish item names, SKUs, customer orders, package dimensions tied to private products, warehouse SOPs, screenshots, logs, or private cartonization rules.

## First Questions to Ask

1. Is the issue wrong package count, wrong weight, wrong dimensions, wrong carton, or wrong rate/label because of package data?
2. Does it happen for one item, one item type, one warehouse, one order size, or all shipments?
3. Are weights and dimensions stored on item records or entered during fulfillment?
4. Are kits, assemblies, matrix items, serialized items, or multi-carton shipments involved?
5. Was the fulfillment edited after packing or rating?
6. Are packaging rules manual, rules-based, or automated?

## Diagnostic Layers

### Layer 1: Item Data

Check:

- Item weight
- Item dimensions
- Quantity
- Units of measure
- Kit, assembly, matrix, or member item behavior
- Item-level packaging assumptions

### Layer 2: Fulfillment Data

Check:

- Item Fulfillment lines
- Picked and packed quantities
- Location
- Lot/serial/bin context if relevant
- Whether fulfillment changed after rating or label generation

### Layer 3: Package Building

Check:

- Manual package entry
- Automated cartonization
- Default package type
- Multi-package split rules
- Maximum weight or dimension rules
- Packaging material weight

### Layer 4: Carrier Constraints

Check:

- Carrier weight limits
- Dimensional limits
- Oversize thresholds
- Dimensional weight rules
- Package type restrictions
- International or special service requirements

### Layer 5: Rate and Label Effects

Check:

- Whether package data used for rating matches package data used for label
- Whether shipment was rerated after packing changes
- Whether label reflects final package count
- Whether tracking numbers align to all packages

## Common Symptoms

### Rate Is Too High Because of Package Data

Likely causes:

- Incorrect item weight
- Missing dimensions causing default packaging
- Dimensional weight applies
- Oversize package selected
- Package count higher than expected

### Label Fails After Packing

Likely causes:

- Package exceeds carrier limit
- Missing required package dimension
- Invalid package type
- Weight or unit conversion issue
- Multi-package data incomplete

### Multi-Package Shipment Has Missing Tracking

Likely causes:

- Not all packages processed
- Carrier response includes multiple labels/tracking numbers but writeback is incomplete
- User reprinted only one package label
- Post-label edit changed package count

### Kit or Assembly Packs Incorrectly

Likely causes:

- Parent item and member item weights differ
- Connector sends parent item only or line details differently
- Assembly dimensions are missing
- Pack rules do not account for component packaging

## Safe Diagnostic Path

1. Start with one affected shipment.
2. Compare expected package count, weight, and dimensions to what Pacejet received.
3. Check item record data and unit conversions.
4. Check fulfillment quantities and whether the record changed after rating.
5. Check package-building rules and carrier limits.
6. Rerate only after confirming package data is corrected.
7. Document the packaging rule privately if it is implementation-specific.

## AI Assistant Response Pattern

When a user asks why Pacejet package data is wrong, the assistant should:

1. Ask whether the issue is count, weight, dimensions, package type, rate, label, or tracking.
2. Ask whether the affected shipment involves kits, assemblies, multiple packages, or edited fulfillments.
3. Diagnose item data, fulfillment data, package-building rules, carrier constraints, and rate/label effects.
4. Avoid publishing private product dimensions or warehouse rules.

## Related Articles

- [Advanced Pacejet Troubleshooting](advanced-troubleshooting.md)
- [Shipping Rate and Carrier Service Troubleshooting](pacejet-rate-carrier-service-troubleshooting.md)
- [Label Generation and Carrier Error Troubleshooting](pacejet-label-carrier-error-troubleshooting.md)
- [Core Shipping Workflow](shipping-workflow.md)
