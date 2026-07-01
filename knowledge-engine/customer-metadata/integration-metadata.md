# Integration Metadata

## Purpose

Defines exactly what metadata must be collected before designing, configuring, or troubleshooting NetSuite integrations — including CSV imports, SuiteTalk web services, RESTlets for external systems, and native connectors.

## Required Metadata

### General Integration

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Integration type** | CSV import, RESTlet, SuiteTalk, native connector — each has different setup requirements | Ask: "Are you importing, syncing, or exchanging data?" |
| **Direction of data flow** | NetSuite to external system, external to NetSuite, or bidirectional | Ask: "Which system is sending data, and which is receiving?" |
| **Data volume and frequency** | Determines whether real-time (RESTlet) or batch (Map/Reduce, CSV) is appropriate | Ask: "How many records and how often?" |
| **External system details** | System name, version, API version determines compatibility | Ask: "What external system are you integrating with?" |
| **Existing integrations** | Avoids creating duplicate integrations or conflicting syncs | Request integration list |

### CSV Import

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Import type** | Records, transactions, journal entries, updates — different import types have different required fields | Ask: "What type of data are you importing?" |
| **File format** | Column headers, field order, date format, delimiter | Request a sample file |
| **Field mapping** | Maps CSV columns to NetSuite fields — must match internal field IDs | Request the field mapping (current or desired) |
| **Existing import templates** | Imports may already have saved mappings | Request saved import template list |
| **Data validation rules** | Some imports require unique values, valid dates, or existing record references | Ask: "Are there any data validation requirements?" |

### SuiteTalk (SOAP/REST Web Services)

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Integration type (SOAP vs. REST)** | Different endpoints, authentication, and data formats | Ask: "Which SuiteTalk protocol are you using?" |
| **WSDL version** | API compatibility between NetSuite and the external system | Request the WSDL version being used |
| **Authentication method** | Token-based or OAuth | Confirm authentication configuration |
| **Record types being synced** | Determines which SuiteTalk endpoints are needed | Ask: "What record types are you syncing?" |

### Native Connector / SuiteApp Integration

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Connector version** | Compatibility with current NetSuite release | Request the connector/SuiteApp version |
| **Connection credentials** | API keys, tokens, or credentials for external system | Ask: "Do you have active credentials for this connection?" |
| **Sync frequency** | Real-time, hourly, daily — determines push/pull behavior | Ask: "How often should data sync?" |
| **Error history** | Identifies recurring integration failures | Request error log for the last 30 days |

## Optional Metadata

| Metadata Item | Why It Matters |
|---|---|
| **Test environment availability** | Allows testing without affecting production data |
| **Sandbox availability** | Integration configuration can be tested in a sandbox |
| **External system API documentation** | Confirms available endpoints and data formats |
| **Error logs from external system** | Identifies errors from the external system's perspective |
| **Mapping documentation** | Documents how fields in NetSuite map to fields in the external system |

## Validation Checklist

- [ ] Integration type confirmed
- [ ] Data flow direction confirmed
- [ ] Data volume understood (determines batch vs. real-time)
- [ ] External system identified and API compatibility checked
- [ ] Existing integrations reviewed for conflicts
- [ ] CSV: Sample file format verified
- [ ] CSV: Field mapping confirmed against NetSuite field IDs
- [ ] SuiteTalk: WSDL or protocol version confirmed
- [ ] Error logs reviewed for existing integration issues

## Common Metadata Gaps

| Gap | Impact | Recovery |
|---|---|---|
| Data volume not assessed | Wrong integration method chosen | Confirm record count and frequency |
| External system not fully identified | Authentication or API version mismatch | Request external system details |
| Sample file not provided | CSV import fails due to format issues | Request a sample file |
| Existing integrations not reviewed | New integration may conflict with existing sync | Review all current integrations |
| Error logs not checked | Recurring failures not addressed before new integration | Request error logs |

## Confidence Impact

| Metadata Collected | Confidence |
|---|---|
| All required + sample data reviewed | High |
| All required + some optional | Medium |
| Data volume unknown or sample data not reviewed | Low |
| Required metadata missing | Unknown — do not proceed |

## Related Documents

- [METADATA_REASONING.md](METADATA_REASONING.md)
- [Integration Support](../support-intelligence/integration-support.md)