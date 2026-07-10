# Advanced Avalara Troubleshooting

## Purpose

This section helps NetSuite users, administrators, consultants, and AI assistants troubleshoot advanced Avalara-related issues without exposing private tax policy, customer data, connector configuration, or implementation details.

Use these articles when an Avalara issue is more complex than a basic address or product overview question.

## Learning Order

1. [Tax Calculation Troubleshooting](TAX_CALCULATION_TROUBLESHOOTING.md) - Diagnose missing, unexpected, or changed tax results.
2. [Address Validation and Geolocation Edge Cases](ADDRESS_VALIDATION_GEOLOCATION_EDGE_CASES.md) - Diagnose address, boundary, and jurisdiction-related issues.
3. [NetSuite Transaction Tax Flow](NETSUITE_TRANSACTION_TAX_FLOW.md) - Understand how transaction, customer, item, address, and location data shape Avalara results.
4. [Exemption Certificate Troubleshooting](EXEMPTION_CERTIFICATE_TROUBLESHOOTING.md) - Diagnose exempt customer and certificate-related questions.
5. [Nexus, Jurisdiction, and Taxability Diagnostics](NEXUS_JURISDICTION_TAXABILITY_DIAGNOSTICS.md) - Separate nexus, jurisdiction, item taxability, exemption, and sourcing questions.
6. [Connector Sync Failure and Log Review](CONNECTOR_SYNC_FAILURE_LOG_REVIEW.md) - Diagnose connector, sync, logging, and retry problems.

## What This Section Is For

Use this section when:

- Tax did not calculate on a transaction.
- Tax calculated but the amount looks wrong.
- Tax changed after an address, item, customer, or transaction change.
- A customer should be exempt but tax still appears.
- A transaction appears to use the wrong jurisdiction.
- NetSuite and Avalara appear out of sync.
- A connector, API, or integration log shows an error.

## Public-Safe Rule

Keep examples generic. Do not include customer names, transaction numbers, private tax policy, exemption documents, nexus footprint, custom field IDs, connector credentials, API keys, screenshots, production logs, pricing, or implementation-specific configuration.

## Source Notes

This section is based on existing repository Avalara articles, public Avalara product pages, the Avalara Knowledge Center, and Avalara Developer documentation. Implementation-specific behavior must be verified against the actual NetSuite account, Avalara account, connector setup, and tax policy.

## Related Existing Articles

- [Avalara Data Flow](DATA_FLOW.md)
- [Avalara Address Troubleshooting](ADDRESS_TROUBLESHOOTING.md)
- [Address Validation](ADDRESS_VALIDATION.md)
- [Which Address Does Avalara Use](WHICH_ADDRESS_DOES_AVALARA_USE.md)
- [Jurisdictions](JURISDICTIONS.md)
- [Geolocation](GEOLOCATION.md)
- [Record Relationships](RECORD_RELATIONSHIPS.md)
- [Product Facts](PRODUCT_FACTS.md)
- [Source Guide](SOURCE_GUIDE.md)
