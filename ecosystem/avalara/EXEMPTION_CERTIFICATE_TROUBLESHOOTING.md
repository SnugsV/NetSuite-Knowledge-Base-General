# Avalara Exemption Certificate Troubleshooting

## Purpose

Help diagnose situations where a customer is expected to be tax exempt but Avalara or NetSuite still calculates tax, or where exemption behavior differs by transaction, item, jurisdiction, or date.

## Source Status

Based on public Avalara product information about exemption certificate management, the Avalara Knowledge Center, and existing repository Avalara articles. Exact exemption treatment depends on tax policy, certificate data, account setup, connector configuration, and jurisdiction rules.

## Quick Summary

Exemption issues are rarely just a checkbox. Exemption treatment can depend on customer identity, certificate status, certificate jurisdiction, effective dates, entity use, item taxability, transaction address, and connector data flow.

## First Questions to Ask

1. Is the customer expected to be fully exempt or exempt only for specific jurisdictions, items, or transaction types?
2. Is there a valid exemption certificate or exemption record?
3. Does the certificate apply to the transaction date and jurisdiction?
4. Is the correct customer selected on the transaction?
5. Is the transaction using the expected ship-to address?
6. Are all items expected to be exempt?
7. Did exemption data sync to the connector or Avalara account?
8. Does the issue happen for one customer, one state, one item, or all transactions?

## Diagnostic Layers

### Layer 1: Customer Identity

Check:

- Correct customer selected
- Parent/child customer relationship
- Customer merged, renamed, or duplicated
- Transaction uses a different customer than expected
- Integration or import mapped customer incorrectly

### Layer 2: Certificate Status

Check:

- Certificate exists
- Certificate is valid and active
- Certificate has not expired
- Certificate applies to transaction date
- Certificate applies to the relevant jurisdiction

### Layer 3: Jurisdiction and Address

Check:

- Ship-to jurisdiction
- Bill-to or origin context if relevant
- Address normalization
- Boundary-sensitive locations
- Whether the certificate covers the destination jurisdiction

### Layer 4: Item and Transaction Type

Check:

- Item taxability
- Product category
- Whether all items are eligible for exemption
- Shipping, handling, fees, or freight lines
- Invoice, credit memo, return, or special transaction behavior

### Layer 5: Connector and Data Flow

Check:

- Exemption data available to Avalara
- Customer code or identifier mapping
- Entity use code or equivalent field
- Connector logs
- Sync timing
- Whether NetSuite and Avalara customer records are aligned

## Common Symptoms

### Customer Is Exempt but Tax Appears

Likely causes:

- Certificate missing, expired, inactive, or not applicable
- Wrong customer selected
- Wrong jurisdiction
- Item not covered by exemption
- Exemption data did not sync
- Transaction date outside certificate effective range

### Exemption Works in One State but Not Another

Likely causes:

- Certificate jurisdiction coverage differs
- Nexus or jurisdiction rules differ
- Address maps to a different jurisdiction than expected
- Certificate type does not apply to all jurisdictions

### Some Lines Are Exempt and Others Are Taxable

Likely causes:

- Product taxability differs by item
- Shipping or fees treated differently
- Item mapping differs across lines
- Exemption applies only to certain item categories

### Credit or Return Exemption Differs from Invoice

Likely causes:

- Credit not linked to original invoice
- Different date or address
- Different customer mapping
- Partial return logic
- Recalculation instead of original transaction reversal behavior

## Safe Diagnostic Path

1. Confirm the expected exemption rule in plain language.
2. Identify customer, transaction type, date, jurisdiction, and item category without exposing sensitive details.
3. Confirm certificate existence, status, dates, and jurisdiction coverage.
4. Confirm customer and address mapping.
5. Check item-level taxability and shipping/fee treatment.
6. Review connector or Avalara logs where available.
7. Escalate tax-policy or certificate-validity questions to tax/accounting ownership.

## AI Assistant Response Pattern

When a user says a customer should be exempt, the assistant should:

1. Ask whether exemption is expected for all items and all jurisdictions or only specific cases.
2. Ask about certificate status, date, jurisdiction, customer, and transaction address.
3. Diagnose customer identity, certificate status, jurisdiction, item, and connector layers.
4. Avoid making legal/tax validity determinations.
5. Keep certificate documents and customer details out of public documentation.

## Related Articles

- [Tax Calculation Troubleshooting](TAX_CALCULATION_TROUBLESHOOTING.md)
- [NetSuite Transaction Tax Flow](NETSUITE_TRANSACTION_TAX_FLOW.md)
- [Nexus, Jurisdiction, and Taxability Diagnostics](NEXUS_JURISDICTION_TAXABILITY_DIAGNOSTICS.md)
- [Record Relationships](RECORD_RELATIONSHIPS.md)

## Public References

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara Exemption Certificate Management product information
- Avalara Developer documentation
