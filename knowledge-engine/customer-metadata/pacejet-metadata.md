# Pacejet Metadata

## Purpose

Defines the metadata required before troubleshooting, configuring, or designing Pacejet solutions. Without this metadata, diagnosing Pacejet issues is guesswork.

## Required Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Pacejet version** | Feature availability, known issues, API compatibility | Check About screen in Pacejet portal |
| **NetSuite bundle version** | Script behavior, ASD field configuration | Installed bundles in NetSuite |
| **Enabled carriers** | Determines available rate options | Carrier activation page |
| **Carrier contract details** | Contract vs. published rates | Carrier configuration page |
| **Item weight/dimension fields** | Completeness affects rate accuracy | Item record fields |

## Optional Metadata

| Metadata Item | Why It Matters |
|---|---|
| **API log export** | Shows API requests, responses, and errors |
| **Error log export** | Shows Pacejet and carrier errors |
| **Sample shipment data** | Can be used to reproduce issues |
| **Carrier mappings** | How carriers are mapped to NetSuite ship methods |
| **ASD field configuration** | Extended shipping data field mappings |
| **Label connector config** | Custom label template settings |
| **Automation rules** | Rules for carrier selection and auto-ship |
| **Script execution log** | NetSuite script errors during shipment processing |

## Nice-to-Have Metadata

| Metadata Item | Why It Matters |
|---|---|
| **Pacejet portal screenshots** | Visual confirmation of configuration |
| **Test shipment results** | Confirms basic integration workflow |
| **Custom SuiteScript deployments** | Any custom scripts affecting fulfillment |
| **Workflow configurations** | Workflows that trigger after fulfillment |

## Validation Checklist

- [ ] Pacejet version confirmed
- [ ] NetSuite bundle version confirmed
- [ ] Enabled carriers identified
- [ ] Carrier contract details available
- [ ] Item weight and dimension fields verified
- [ ] API log reviewed (if errors present)
- [ ] Error log reviewed (if errors present)
- [ ] Test shipment can be run

## Confidence Impact

| Metadata Collected | Confidence |
|---|---|
| Version + carrier config + sample shipment | High |
| Version + carrier config | Medium |
| Version only | Low |
| No metadata | Unknown — do not proceed |

## Related Documents

- [Pacejet Support Intelligence](../support-intelligence/pacejet-support.md)
- [Pacejet Customer Context](../customer-context/pacejet-context.md)
- [METADATA_REASONING.md](METADATA_REASONING.md)