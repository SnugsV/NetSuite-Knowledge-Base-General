# Case Template

## Purpose

Standardized template for capturing anonymized consulting cases. Each case captures what happened, what was learned, and how the platform should improve.

## Case Structure

```
CASE-[ID]: [Descriptive Title]

## Summary

One paragraph describing the engagement type (troubleshooting, implementation, configuration, audit).

## Business Scenario

Industry:
Company size:
NetSuite configuration:
Modules involved:
Integrations involved:

## Problem Statement

What the customer reported.
What the expected behavior was.
What the actual behavior was.

## Customer Environment (Anonymized)

This section captures what was learned about the environment. Do not include customer-identifying information.

Enabled features discovered:
Customizations discovered:
Integrations discovered:
Configuration gaps identified:

## Metadata Collected

What metadata was requested:
What metadata was available:
What metadata was missing:
Impact of missing metadata on resolution time:

## Investigation Path

What was checked (in order):
- Record/pattern inspected
- What was found
- Whether this path was productive

## Root Cause

What caused the problem:
Why it happened:
How it was confirmed:

## Resolution

What was done to resolve:
Configuration changes:
Script or workflow changes:
Training or process changes:
Time to resolve:

## Validation

How the resolution was validated:
Did the customer confirm success:
Was a sandbox test performed:

## Confidence Assessment

What was the predicted confidence at each stage:
| Stage | Predicted Confidence | Actual Outcome | Calibration |
|---|---|---|---|
| Initial triage | (High/Med/Low) | (Correct/Wrong/Partial) | (On/Over/Under) |
| After metadata | (High/Med/Low) | (Correct/Wrong/Partial) | (On/Over/Under) |
| Final diagnosis | (High/Med/Low) | (Correct/Wrong/Partial) | (On/Over/Under) |

## Lessons Learned

What assumptions were incorrect:
What should have been checked earlier:
What information should have been requested first:
What would have reduced resolution time:

## Documentation Gaps

What documentation would have helped:
- Missing module or topic
- Missing support pattern
- Missing AI Skill
- Missing metadata requirement
- Missing system context guidance

## Playbook Recommendations

What should change in the platform:
- Support Intelligence updates:
- Customer Context updates:
- AI Skills updates:
- Metadata updates:
- Agent Runtime updates:

## Related Cases

CASE-[ID]: [Related case description]
```

## Case Example (Filled)

```
CASE-001: Missing Tracking Numbers After Pacejet Shipment

## Summary

Troubleshooting engagement for a distributor whose tracking numbers were not returning from Pacejet to NetSuite. The label generated successfully but the tracking number never appeared on the fulfillment record.

## Business Scenario

Industry: Wholesale distribution
Company size: 50 users, 3 warehouses, ~200 shipments/day
NetSuite configuration: OneWorld, Multi-Location, Advanced Inventory
Modules involved: Sales, Inventory, Fulfillment
Integrations involved: Pacejet Connector, ASD, FedEx, UPS

## Problem Statement

Customer reported that tracking numbers were not appearing on Item Fulfillments after processing shipments through Pacejet. Labels generated successfully. The tracking number was visible in the Pacejet portal.

## Metadata Collected

What was requested: Pacejet version, NetSuite bundle version, API log, script execution log
What was available: Version numbers, API log showed successful callback
What was missing: Script execution log (customer was unsure how to access)
Impact: Added 30 minutes to resolution time while guiding customer to find the log

## Investigation Path

1. Checked Pacejet portal → Shipment confirmed with tracking number → Integration is working
2. Checked API log → Callback to NetSuite succeeded → Integration communication is working
3. Checked script execution log → ASD field update script returned "field not found" error → Script issue
4. Checked ASD field configuration → Tracking number field was not mapped to the NetSuite field → Configuration issue

## Root Cause

The ASD custom field for tracking number was not mapped to the corresponding NetSuite field on the fulfillment record. The Pacejet callback succeeded, but the update script could not find the destination field.

## Resolution

Mapped the ASD tracking number field to the NetSuite fulfillment tracking field. Tested with a single shipment — tracking number appeared immediately. Applied to all ASD fields for completeness.

## Confidence Assessment

| Stage | Predicted | Actual | Calibration |
|---|---|---|---|
| Initial triage | Medium | Partial | Over |
| After metadata | Medium | Correct | On |
| Final diagnosis | High | Correct | On |

## Lessons Learned

Assumption that ASD fields were correctly configured was wrong. Should have asked for ASD configuration screenshots earlier. Script execution log should be a required metadata item for tracking issues.

## Documentation Gaps

Missing: Pacejet ASD configuration troubleshooting pattern in support intelligence.
Missing: Script execution log should be listed as required metadata for tracking issues.
Missing: Common mistake: ASD fields not fully mapped during initial setup.

## Playbook Recommendations

Support Intelligence: Add "ASD field not mapped" pattern to pacejet-support.md.
Metadata: Add script execution log to required metadata for Pacejet tracking issues.
AI Skill: Add ASD field verification step to pacejet-label-troubleshooter.md.
```