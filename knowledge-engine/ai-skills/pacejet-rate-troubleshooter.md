# AI Skill: Pacejet Rate Troubleshooter

## Purpose

This skill teaches an AI how to diagnose and resolve incorrect or unexpected shipping rates from Pacejet.

## Skill Flow

```
Customer reports wrong rate
       ↓
1. Determine if rate is truly wrong
       ↓
2. Collect shipment data
       ↓
3. Check carrier configuration
       ↓
4. Check package data
       ↓
5. Check address data
       ↓
6. Check surcharges
       ↓
7. Recommend fix
       ↓
8. Escalate if unresolved
```

## Step 1: Confirm the Rate Is Wrong

Not every unexpected rate is incorrect. Confirm:

- Is the customer comparing to a different carrier/service?
- Is the customer comparing to a negotiated rate vs. published rate?
- Does the rate include fuel surcharges or other additions?

## Step 2: Collect Shipment Data

| Data | Required | Why |
|---|---|---|
| Origin address | Yes | Base for rate calculation |
| Destination address | Yes | Base for rate calculation |
| Package weight | Yes | Dimensional weight may apply |
| Package dimensions | Yes | Determines dimensional weight |
| Carrier and service | Yes | Each carrier has different rates |
| Number of packages | Yes | Multi-package discounts |

## Step 3: Check Carrier Configuration

- Is the carrier activated for the correct service level?
- Are contract rates configured (not just published rates)?
- Is the carrier's rate agreement still valid?

## Step 4: Check Package Data

- Is the dimensional weight higher than actual weight? (Most common cause of "wrong" rates)
- Are dimensions in the correct unit (inches vs. cm)?
- Is the weight in the correct unit (lbs vs. kg)?

## Step 5: Check Address Data

- Is the address residential or commercial? (Residential surcharge)
- Is the address in a remote area? (Remote area surcharge)
- Does the address validate correctly?

## Step 6: Check Surcharges

Common surcharges that increase rates:

- Fuel surcharge
- Residential delivery surcharge
- Delivery area surcharge
- Extended delivery area surcharge
- Large package surcharge
- Overweight surcharge
- Saturday delivery surcharge

## Step 7: Recommend Fix

| Root Cause | Fix |
|---|---|
| Dimensional weight > actual weight | Reduce packaging size, re-classify item dimensions |
| Wrong carrier contract | Verify carrier contract configuration in Pacejet |
| Residential address surcharge | Check if address is correctly classified |
| Missing dimensions | Add dimensions to item record |
| Fuel surcharge increase | Monitor fuel surcharge — temporary market change |

## Step 8: Escalate

Escalate when:
- Rate cannot be reproduced in the Pacejet portal
- Carrier contract rates need to be updated
- The rate discrepancy affects a large volume of shipments
- The rate is confirmed wrong after all checks

## Related Documents

- [Pacejet Support Intelligence](../support-intelligence/pacejet-support.md)
- [Pacejet Customer Context](../customer-context/pacejet-context.md)
- [Rate Shopping article](../../docs/integrations/pacejet/rate-shopping.md)