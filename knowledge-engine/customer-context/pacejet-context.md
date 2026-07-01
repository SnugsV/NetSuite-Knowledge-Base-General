# Pacejet Customer Context

## Purpose

Defines the customer-specific information required before troubleshooting or configuring Pacejet.

## Required Information

| Context Element | Why It Matters | How to Collect |
|---|---|---|
| **Pacejet version** | API compatibility, feature availability, known issues | Check Pacejet portal: About screen |
| **NetSuite bundle version** | Script behavior, ASD field availability | Check NetSuite: Installed bundles |
| **Enabled carriers** | Determines which carriers are available for rate shopping | Check Pacejet: Carrier activation |
| **Warehouse locations** | Ship-from address for rate calculations | NetSuite: Location records |
| **Item data completeness** | Weight and dimensions affect rate accuracy | Check item records for missing data |
| **Shipping preferences** | Default carrier, service level, automation rules | Check Pacejet: Preferences |
| **International shipping** | Customs documentation, restricted party screening | Ask: "Do you ship internationally?" |

## Optional Information

| Context Element | Why It Matters |
|---|---|
| **Carrier contract details** | Contract rates vs. published rates affect rate shopping results |
| **ASD custom field mapping** | Extended shipping fields may have customer-specific mappings |
| **Label connector configuration** | Custom label templates vary by customer |
| **Automation rules** | Custom rules may override standard carrier selection |
| **Batch shipping configuration** | Batch processing may have different error handling |

## Common Context Gaps

| Gap | Impact | Recovery |
|---|---|---|
| Pacejet version unknown | Cannot check known issues or feature availability | Ask customer to check About screen |
| Bundle version unknown | Script behavior may be version-dependent | Check installed bundles in NetSuite |
| Carrier contracts unknown | May assume rates that do not match customer's contract | Ask customer to verify carrier contract rates |
| Item data completeness unknown | May diagnose wrong rate when missing dimensions cause dimensional weight | Check item records for weight and dimensions |

## Related Documents

- [Pacejet Support Intelligence](../support-intelligence/pacejet-support.md)
- [Pacejet Metadata](../customer-metadata/pacejet-metadata.md)
- [Customer Context Methodology](CUSTOMER_CONTEXT_REASONING.md)