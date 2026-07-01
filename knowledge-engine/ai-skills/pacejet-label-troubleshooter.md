# AI Skill: Pacejet Label Troubleshooter

## Purpose

This skill teaches an AI how to diagnose and resolve label generation failures in Pacejet.

## Skill Flow

```
Customer reports label won't generate
       ↓
1. Check error message
       ↓
2. Verify shipment data
       ↓
3. Check carrier configuration
       ↓
4. Check label configuration
       ↓
5. Test label generation
       ↓
6. Recommend fix
       ↓
7. Escalate if unresolved
```

## Step 1: Check Error Message

The error message identifies the type of failure:

| Error Pattern | Likely Cause |
|---|---|
| Address validation error (AV prefix) | Address failed validation |
| Carrier error (CR prefix) | Carrier rejected the shipment |
| Label error (LB prefix) | Label generation failure |
| Data error (DA prefix) | Missing or incorrect shipment data |
| Configuration error (CF prefix) | Pacejet configuration issue |

## Step 2: Verify Shipment Data

| Data | Required | Impact |
|---|---|---|
| Origin address | Yes | Invalid address = no label |
| Destination address | Yes | Invalid address = no label |
| Package weight | Yes | Zero weight = no label |
| Package dimensions | Yes | Zero dimensions = no label |
| Carrier and service | Yes | Invalid carrier = no label |

## Step 3: Check Carrier Configuration

- Is the carrier activated and configured?
- Are the required service levels enabled?
- Does the carrier support the origin/destination combination?
- Is the carrier contract still valid?

## Step 4: Check Label Configuration

For standard labels:
- Is the label format selected (PDF, ZPL, etc.)?
- Is the printer configured correctly?
- Are label settings correct for the carrier?

For custom labels (Label Connector):
- Is the BarTender integration configured?
- Are the label templates assigned correctly?
- Are the field mappings correct?

## Step 5: Test Label Generation

1. Create a test shipment in the Pacejet portal (not from NetSuite)
2. If the test succeeds in Pacejet, the issue is in the NetSuite integration
3. If the test fails in Pacejet, the issue is in the Pacejet or carrier configuration

## Step 6: Recommend Fix

| Root Cause | Fix |
|---|---|
| Address validation failed | Correct the address or bypass validation |
| Missing package data | Add weight/dimensions to the item or shipment |
| Carrier not configured | Activate the carrier or correct the configuration |
| Label format not set | Select the correct label format |
| Label connector mapping wrong | Correct the BarTender field mapping |
| Printer not configured | Set up the label printer in Pacejet |

## Step 7: Escalate

Escalate when:
- The test shipment also fails in Pacejet
- The carrier is rejecting the shipment for reasons beyond configuration
- The label connector has a configuration error that requires the customer's label designer
- The error requires Pacejet support to resolve

## Related Documents

- [Pacejet Support Intelligence](../support-intelligence/pacejet-support.md)
- [Pacejet Customer Context](../customer-context/pacejet-context.md)
- [Label Generation article](../../docs/integrations/pacejet/label-generation.md)