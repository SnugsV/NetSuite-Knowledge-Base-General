# Avalara Tax Calculation Troubleshooting

## Purpose

Provide a structured way to diagnose Avalara tax calculation issues in NetSuite, including missing tax, unexpected tax, changed tax, and tax differences between transactions.

## Source Status

Based on public Avalara product and developer documentation, the Avalara Knowledge Center, and existing repository Avalara foundation articles. Exact behavior depends on NetSuite account setup, Avalara account setup, connector configuration, tax policy, and transaction data.

## Quick Summary

When Avalara tax looks wrong, diagnose the transaction data first. Tax calculation is shaped by addresses, customer exemption status, item taxability, transaction type, amounts, shipping, discounts, nexus, jurisdiction, connector status, and NetSuite workflow timing.

## First Questions to Ask

1. What transaction type is affected?
2. Did tax fail to calculate, calculate as zero, calculate too high, calculate too low, or change after an edit?
3. Is this happening on one transaction, one customer, one item, one state, or all transactions?
4. Which address is being used for tax?
5. Is the customer exempt or expected to be taxable?
6. Are shipping, discounts, handling, or freight involved?
7. Did the item, address, customer, nexus setup, connector, or transaction workflow change recently?
8. Is the issue in NetSuite, Avalara, or a connector/API response?

## Diagnostic Layers

### Layer 1: Transaction Context

Check:

- Transaction type
- Transaction status
- Tax calculation timing
- Posting or non-posting status
- Sales order vs invoice vs credit memo behavior
- Whether the transaction was copied, transformed, edited, or imported

### Layer 2: Address and Jurisdiction

Check:

- Ship-to address
- Bill-to address
- Location or origin address
- Address completeness
- ZIP/postal code and state/province
- Boundary-sensitive jurisdictions
- Whether a transaction-level override differs from the customer address book

### Layer 3: Customer and Exemption Status

Check:

- Customer selected on the transaction
- Exemption status
- Certificate availability and validity
- Entity use code or equivalent exemption indicator where applicable
- Whether exemption applies to the transaction jurisdiction and item type

### Layer 4: Item and Taxability

Check:

- Item selected
- Item tax code, tax category, or Avalara-related tax mapping
- Product type or taxability classification
- Shipping, handling, discount, or fee lines
- Whether a taxable and non-taxable item are being compared

### Layer 5: Nexus and Company Setup

Check:

- Whether the seller has tax obligation in the destination jurisdiction
- Company profile and nexus setup
- Jurisdiction configuration
- Effective dates
- Marketplace, direct sale, or special channel context if applicable

### Layer 6: Connector and Sync Behavior

Check:

- Connector status
- Error logs
- Whether transaction data was sent to Avalara
- Whether Avalara returned a tax result or an error
- Whether NetSuite stored the returned result correctly
- Retry or recalculation behavior

## Common Symptoms

### Tax Did Not Calculate

Likely causes:

- Missing or incomplete address
- Connector or API error
- Transaction did not trigger tax calculation
- Required tax fields missing
- Customer or transaction treated as exempt
- No nexus or no tax obligation in the jurisdiction

### Tax Is Zero

Likely causes:

- Customer exemption
- Non-taxable item
- No tax obligation in jurisdiction
- Tax holiday or special rule
- Incorrect item classification
- Address mapped to a different jurisdiction than expected

### Tax Amount Looks Too High or Too Low

Likely causes:

- Wrong address or jurisdiction
- Shipping, handling, discount, or fee treatment
- Item taxability mapping
- Multiple jurisdictions involved
- Sourcing rule difference
- Tax included vs tax added assumption

### Tax Changed After Editing

Likely causes:

- Address changed
- Item or quantity changed
- Date changed
- Exemption status changed
- Transaction transformed from one type to another
- Connector recalculated tax after save or edit

## Safe Diagnostic Path

1. Start with one affected transaction.
2. Record the expected result in plain language.
3. Confirm transaction type, status, and tax calculation timing.
4. Confirm addresses used for tax.
5. Confirm customer exemption and item taxability.
6. Check nexus and jurisdiction assumptions.
7. Review connector or API logs if available.
8. Compare to a similar known-good transaction.
9. Escalate tax policy questions to tax/accounting ownership.
10. Keep customer, transaction, and policy details out of public docs.

## AI Assistant Response Pattern

When a user asks why Avalara tax is wrong, the assistant should:

1. Ask whether tax is missing, zero, too high, too low, or changed after an edit.
2. Ask for transaction type, address context, customer exemption expectation, and item type without requesting sensitive details.
3. Diagnose transaction, address, customer, item, nexus, and connector layers.
4. Recommend comparing one affected transaction to one known-good transaction.
5. Avoid giving tax-policy conclusions; escalate policy decisions to tax/accounting ownership.

## Related Articles

- [Advanced Avalara Troubleshooting](ADVANCED_TROUBLESHOOTING.md)
- [Avalara Data Flow](DATA_FLOW.md)
- [Address Validation and Geolocation Edge Cases](ADDRESS_VALIDATION_GEOLOCATION_EDGE_CASES.md)
- [NetSuite Transaction Tax Flow](NETSUITE_TRANSACTION_TAX_FLOW.md)
- [Nexus, Jurisdiction, and Taxability Diagnostics](NEXUS_JURISDICTION_TAXABILITY_DIAGNOSTICS.md)

## Public References

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara Developer: AvaTax documentation
- Avalara NetSuite integration page
