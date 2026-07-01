---
title: Troubleshooting Case Library
module: Integrations
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Pacejet Troubleshooting Case Library

## Purpose

Structured troubleshooting cases for common Pacejet issues. Each case follows the same reasoning pattern: symptom → questions → evidence → causes → verify → resolve → escalate.

## How to Use This Library

1. Match the customer symptom to a case below
2. Follow the structured diagnostic process
3. Use confidence scoring to determine when to recommend vs. escalate

## Case 1: Label Generation Failure

### Customer Symptom

"The label won't generate. I get an error when I try to ship."

### Questions to Ask First

1. What is the exact error message?
2. Did it work before? When was the last successful label?
3. Is this affecting one shipment or all shipments?
4. What carrier and service are you using?
5. Has anything changed recently? (carrier contract, Pacejet update, item data)

### Metadata Required

| Item | Source |
|---|---|
| Error message text | Pacejet error log or UI |
| Carrier and service | From the shipment |
| Package weight and dimensions | Item record or shipment data |
| Ship-from and ship-to addresses | Fulfillment record |
| Pacejet version | About screen |
| NetSuite bundle version | Installed bundles |

### Records and Logs to Inspect

1. Pacejet error log — look for error codes (AV, CR, LB, DA, CF prefixes)
2. Fulfillment record — verify weight, dimensions, address
3. Item record — verify item weight and dimensions are filled
4. Carrier configuration — is the carrier active?
5. Label configuration — label format, printer settings

### Most Likely Root Causes

| Cause | Probability | How to Verify |
|---|---|---|
| Address validation failed | High | Check if error code starts with AV |
| Missing package data | High | Check weight and dimensions on the item/fulfillment |
| Carrier contract expired | Medium | Check carrier activation status |
| Carrier not configured for this service | Medium | Check carrier service level configuration |
| Label connector configuration issue | Low | Check BarTender integration if using custom labels |

### Validation Steps

1. Try to generate a label in the Pacejet portal (not from NetSuite)
2. If Pacejet portal works, the issue is in the NetSuite integration
3. If Pacejet portal fails, the issue is in the Pacejet or carrier configuration

### Resolution Options

| Root Cause | Resolution |
|---|---|
| Address validation failed | Correct the address or bypass validation |
| Missing package data | Add weight/dimensions to the item record |
| Carrier contract expired | Renew carrier contract in Pacejet |
| Service not configured | Enable the required service level |
| Label connector misconfigured | Correct BarTender field mappings |

### Escalation Guidance

| Condition | Escalate To |
|---|---|
| Pacejet portal also fails | Pacejet support |
| Label connector issue | Customer's label designer or Pacejet label support |
| Carrier contract issue | Carrier representative or Pacejet support |

### Confidence Assessment

| Evidence Collected | Confidence |
|---|---|
| Error code + package data + carrier config | High |
| Error code + package data | Medium |
| Error code only | Low |

---

## Case 2: Incorrect Shipping Rates

### Customer Symptom

"The rate seems too high (or too low). We usually pay less for this shipment."

### Questions to Ask First

1. What rate did you expect and what rate did you get?
2. Is this the right carrier for this shipment?
3. Are you comparing to a contract rate or published rate?
4. Are package dimensions correct?
5. Has the carrier contract changed recently?

### Metadata Required

| Item | Source |
|---|---|
| Expected rate vs. actual rate | Customer estimate vs. Pacejet quote |
| Package weight and dimensions | Item record |
| Ship-from and ship-to addresses | Fulfillment record |
| Carrier and service selected | From the shipment |
| Carrier contract details | Carrier configuration in Pacejet |

### Records and Logs to Inspect

1. Pacejet rate quotes — check the rate breakdown
2. Item record — verify weight and dimensions
3. Carrier configuration — verify contract rates are loaded
4. Surcharge configuration — fuel, residential, delivery area

### Most Likely Root Causes

| Cause | Probability | How to Verify |
|---|---|---|
| Dimensional weight exceeds actual weight | High | Compare dim weight to actual weight |
| Wrong carrier contract applied | Medium | Check carrier contract rates in Pacejet |
| Fuel surcharge increased | Medium | Check current fuel surcharge percentage |
| Residential vs. commercial address | Medium | Check if address is classified as residential |
| Missing dimensions | Low | Check if dimensions are zero (causes dim weight calc issues) |

### Validation Steps

1. Check the dimensional weight calculation: (L × W × H) / DIM factor
2. Compare dim weight to actual weight — the higher one is billed
3. Check the carrier contract rates in Pacejet
4. Verify the address classification (residential vs. commercial)
5. Check fuel surcharge and other accessorials

### Resolution Options

| Root Cause | Resolution |
|---|---|
| Dimensional weight higher | Reduce packaging size, re-classify item dimensions |
| Wrong carrier contract | Reload contract rates in Pacejet |
| Residential surcharge | Verify address classification; use commercial if applicable |
| Fuel surcharge fluctuation | This is a market change; monitor and plan for it |

### Escalation Guidance

| Condition | Escalate To |
|---|---|
| Carrier contract rates need updating | Customer's carrier representative |
| Rate discrepancy > 20% from expected | Pacejet support for rate investigation |
| Issue affects a high volume of shipments | Supervisor for rate negotiation review |

### Confidence Assessment

| Evidence Collected | Confidence |
|---|---|
| Dim weight vs. actual weight + contract rates | High |
| Dim weight vs. actual weight only | Medium |
| Customer estimate only | Low |

---

## Case 3: Missing Tracking Number

### Customer Symptom

"The shipment was processed in Pacejet but the tracking number didn't come back to NetSuite."

### Questions to Ask First

1. Can you see the tracking number in the Pacejet portal?
2. Are there errors in the Pacejet API log?
3. Are there errors in the NetSuite script execution log?
4. Was this a batch shipment or individual?

### Metadata Required

| Item | Source |
|---|---|
| Tracking number in Pacejet (yes/no) | Pacejet portal |
| API error log | Pacejet API log |
| Script execution log | NetSuite script log |
| Fulfillment record | NetSuite |
| ASD field configuration | NetSuite custom fields |

### Records and Logs to Inspect

1. Pacejet portal — does the shipment show as confirmed with a tracking number?
2. Pacejet API log — were there errors in the callback to NetSuite?
3. NetSuite script log — did the update script run successfully?
4. ASD field mapping — are the tracking fields mapped correctly?

### Most Likely Root Causes

| Cause | Probability | How to Verify |
|---|---|---|
| API callback failed | High | Check Pacejet API log for callback errors |
| Script governance limit | Medium | Check NetSuite script log for governance errors |
| ASD field not mapped correctly | Medium | Check ASD field configuration for tracking fields |
| Scheduled script not running | Low | Check scheduled script deployment status |

### Validation Steps

1. Check the shipment in the Pacejet portal — does it have a tracking number?
2. If yes, the issue is in the update back to NetSuite
3. Check the Pacejet API log for callback errors
4. Check the NetSuite script execution log
5. Verify ASD field configuration

### Resolution Options

| Root Cause | Resolution |
|---|---|
| API callback failed | Retry the callback; check API URL configuration |
| Script governance exceeded | Reduce script complexity or increase governance allocation |
| ASD field mapping wrong | Correct the field mapping in ASD configuration |
| Script not scheduled | Deploy the scheduled script for tracking updates |

### Escalation Guidance

| Condition | Escalate To |
|---|---|
| API callback configuration needs correction | Pacejet support |
| Script modification needed | NetSuite administrator or developer |
| Repeated governance limit issues | NetSuite account representative |

### Confidence Assessment

| Evidence Collected | Confidence |
|---|---|
| Tracking in Pacejet + API log + script log | High |
| Tracking in Pacejet + API log | Medium |
| Customer report only | Low |

---

## Case 4: Carrier Authentication Failure

### Customer Symptom

"The carrier says my credentials are wrong, or Pacejet shows a carrier authentication error."

### Questions to Ask First

1. Which carrier is failing authentication?
2. When did the credentials last work?
3. Were the carrier credentials changed recently?
4. Is this affecting one carrier or multiple carriers?

### Metadata Required

| Item | Source |
|---|---|
| Carrier name | From the error |
| Error message | Pacejet error log |
| Credential type | API key, account number, password |
| Date last worked | Customer estimate |
| Recent changes | Customer response |

### Most Likely Root Causes

| Cause | Probability |
|---|---|
| Carrier password or API key changed | High |
| Carrier contract expired | Medium |
| Carrier requires re-authentication | Medium |
| Carrier account suspended | Low |

### Resolution Options

| Root Cause | Resolution |
|---|---|
| Password changed | Update credentials in Pacejet carrier configuration |
| Contract expired | Renew carrier contract |
| Re-authentication required | Complete carrier's re-authentication process |

### Escalation Guidance

Escalate to Pacejet support if credentials are confirmed correct but authentication still fails. Escalate to the carrier if the account is suspended or has a billing issue.

---

## Case 5: Address Validation Failure

### Customer Symptom

"Pacejet says the address is invalid, but it's a valid address."

### Questions to Ask First

1. What is the exact address validation error code? (AV1004, AV1005, AV1008, AV2202)
2. Is the address in the US or another country?
3. Does the address pass validation on the carrier's website directly?
4. Is this a new address or one that worked before?

### Most Likely Root Causes

| Error Code | Meaning | Resolution |
|---|---|---|
| AV1004 | Address not found | Verify the address is correct; add delivery point information |
| AV1005 | Insufficient address data | Add street number, street name, or ZIP+4 |
| AV1008 | Address is a PO Box | Use a physical address for carrier delivery |
| AV2202 | International address issue | Verify international address format matches local standards |

### Escalation Guidance

Escalate if the address validates on the carrier's website but not in Pacejet (possible Pacejet address database issue), or if the issue affects a large volume of orders that need address correction.

---

## Case 6: Batch Processing Failure

### Customer Symptom

"The batch shipment process failed halfway through. Some shipments were processed, some weren't."

### Questions to Ask First

1. How many shipments were in the batch?
2. How many succeeded vs. failed?
3. What do the failed shipments have in common? (same carrier, same item type, same warehouse?)
4. What is the error message on the failed shipments?

### Most Likely Root Causes

| Cause | How to Check |
|---|---|
| One shipment in the batch has invalid data | Find the failed shipment and check its data |
| API rate limit exceeded | Check Pacejet API log for rate limit errors |
| Script governance limit during batch | Check NetSuite script log for timeout or governance errors |
| Carrier-specific failure | Check if all failures are for the same carrier |

### Resolution Options

| Root Cause | Resolution |
|---|---|
| Invalid shipment data | Correct the data and reprocess the failed items |
| Rate limit exceeded | Reduce batch size or increase rate limit |
| Script timeout | Increase script governance allocation or reduce batch size |
| Carrier issue | Process failed items with a different carrier, or retry after carrier issue is resolved |

### Escalation Guidance

Escalate if batch processing fails consistently, or if the batch size needs to be limited due to system constraints. Pacejet support may have recommendations for optimal batch sizes.

## Related Articles

- [Scenario Library](scenario-library.md)
- [Core Shipping Workflow](shipping-workflow.md)
- [Rate Shopping](rate-shopping.md)
- [Pacejet Support Intelligence](../../knowledge-engine/support-intelligence/pacejet-support.md)
- [Pacejet Rate Troubleshooter](../../knowledge-engine/ai-skills/pacejet-rate-troubleshooter.md)
- [Pacejet Label Troubleshooter](../../knowledge-engine/ai-skills/pacejet-label-troubleshooter.md)

## Oracle References

- [Pacejet Knowledge Base: Troubleshooting](https://pacejet.help.descartesservices.com/)