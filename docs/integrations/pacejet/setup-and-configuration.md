---
title: Setup and Configuration
module: Integrations
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Setup and Configuration

## Quick Summary

Pacejet setup involves installing the NetSuite bundle, activating carriers, configuring shipping preferences, and testing the integration. Proper setup is the foundation of reliable shipping operations.

## Difficulty

Intermediate

## Estimated Time

15 minutes

## Setup Overview

```
Install NetSuite bundle
       ↓
Configure Pacejet account
       ↓
Activate carriers
       ↓
Configure shipping preferences
       ↓
Configure ASD fields (optional)
       ↓
Configure label settings
       ↓
Test integration
       ↓
Go live
```

## NetSuite Bundle Installation

The Pacejet Connector is installed as a NetSuite bundle:

1. Navigate to Customization > SuiteBundler > Search and Install Bundles
2. Search for "Pacejet Connector"
3. Install the bundle (requires administrator access)
4. Configure bundle preferences and custom fields

## Pacejet Account Configuration

After bundle installation, configure the Pacejet connection:

| Setting | Description |
|---|---|
| Pacejet API URL | Production or sandbox endpoint |
| API Credentials | Authentication token or credentials |
| Default ship-from location | Default warehouse origin |
| Units of measure | Weight (lbs/kg), dimensions (in/cm) |

## Carrier Activation

Pacejet supports dozens of carriers. Each carrier requires:

- Carrier account credentials or contract information
- Service level configuration (ground, express, overnight)
- Rate agreement setup (contract rates or published rates)
- Label format preferences (standard or custom)

## Configuration Checklist

- [ ] NetSuite bundle installed and configured
- [ ] Pacejet API connection verified
- [ ] At least one carrier activated and tested
- [ ] Default ship-from location set
- [ ] Weight and dimension units configured
- [ ] ASD fields configured (if needed)
- [ ] Label format set (standard or custom)
- [ ] Test shipment processed successfully
- [ ] User roles/permissions configured for Pacejet access

## Related Articles

- [What Is Pacejet?](what-is-pacejet.md)
- [Carrier Integrations](carrier-integrations.md)
- [Pacejet Context](../../../knowledge-engine/customer-context/pacejet-context.md)
- [Pacejet Metadata](../../../knowledge-engine/customer-metadata/pacejet-metadata.md)

## Oracle References

- [Pacejet Knowledge Base: Setup](https://pacejet.help.descartesservices.com/)