# Avalara Nexus, Jurisdiction, and Taxability Diagnostics

## Purpose

Help separate three different troubleshooting questions that often get mixed together: whether the seller has tax obligation, which jurisdiction applies, and whether the product or service is taxable.

## Source Status

Based on public Avalara product information, Avalara Developer documentation, the Avalara Knowledge Center, and existing repository Avalara articles. Final tax decisions depend on business tax policy, Avalara setup, and professional tax review.

## Quick Summary

A tax result may be zero, unexpected, or different from another transaction because of nexus, jurisdiction, taxability, exemption, sourcing, address mapping, or transaction data. Diagnose each layer separately.

## Key Concepts

### Nexus or Tax Obligation

Whether the seller has an obligation to collect tax in a jurisdiction. This is a business/tax policy and setup question.

### Jurisdiction

The tax authority or location context used to determine applicable tax rules. Jurisdiction depends heavily on address and boundary mapping.

### Taxability

Whether the item, service, shipping, fee, discount, or transaction line is taxable in that jurisdiction.

### Exemption

Whether the buyer or transaction is exempt from tax that would otherwise apply.

## First Questions to Ask

1. Is the question about obligation to collect, location/jurisdiction, item taxability, or customer exemption?
2. Which transaction and jurisdiction are being compared?
3. Is the tax result zero, lower, higher, or different from a similar transaction?
4. Is the item, customer, address, transaction date, or transaction type different?
5. Are shipping, handling, discounts, or fees involved?
6. Did tax setup, item mapping, nexus setup, or certificate data change recently?

## Diagnostic Layers

### Layer 1: Nexus or Obligation

Check:

- Whether the company is configured to collect in the jurisdiction
- Effective dates
- State, local, or special jurisdiction context
- Marketplace or channel context if relevant
- Whether the issue is actually a policy/setup question

### Layer 2: Jurisdiction

Check:

- Destination address
- Origin address where relevant
- Address validation and normalization
- City, county, district, and local boundaries
- ZIP/postal code limitations
- Whether expected jurisdiction is based on assumption or actual mapped result

### Layer 3: Product or Line Taxability

Check:

- Item tax code or category
- Product classification
- Service vs tangible goods
- Shipping, freight, handling, discount, and fee lines
- Item mapping consistency across similar items

### Layer 4: Customer Exemption

Check:

- Customer exemption status
- Certificate validity
- Jurisdiction coverage
- Entity use or exemption indicator
- Whether exemption applies to all lines or only some lines

### Layer 5: Transaction Context

Check:

- Transaction date
- Transaction type
- Line amounts
- Related credit, return, or original invoice
- Imported vs UI-entered transaction
- Workflow/script/connector recalculation behavior

## Common Symptoms

### No Tax in a State Where Tax Was Expected

Likely causes:

- No configured obligation/nexus
- Customer exemption
- Non-taxable item
- Address maps outside expected jurisdiction
- Transaction date before effective setup
- Connector did not calculate tax

### Tax in a City or County Looks Wrong

Likely causes:

- Address boundary issue
- ZIP/postal code spans multiple jurisdictions
- Special district applies
- City label differs from taxing jurisdiction
- Origin/destination sourcing assumption is wrong

### Same Item Taxed Differently in Two Places

Likely causes:

- Jurisdiction-specific taxability rules
- Different item mapping
- Different customer exemption status
- Different transaction type or date
- Shipping or discount treatment differs

### Similar Customers Have Different Tax Results

Likely causes:

- Different addresses or jurisdictions
- Different exemption status
- Different customer mapping
- Different transaction dates
- Different subsidiary/location/origin context

## Safe Diagnostic Path

1. Name the layer being investigated: nexus, jurisdiction, taxability, exemption, or transaction data.
2. Compare one affected transaction to one known-good transaction.
3. Confirm address and jurisdiction first.
4. Confirm item taxability and line mapping.
5. Confirm customer exemption.
6. Confirm nexus/obligation setup and effective dates.
7. Escalate policy decisions to tax/accounting ownership.

## AI Assistant Response Pattern

When a user asks why tax differs by state, customer, or item, the assistant should:

1. Separate nexus, jurisdiction, taxability, exemption, and transaction context.
2. Ask what is being compared and what differs between the transactions.
3. Avoid claiming the tax result is legally correct or incorrect.
4. Recommend verifying address mapping, item classification, customer exemption, and nexus setup.
5. Keep examples generic and public-safe.

## Related Articles

- [Tax Calculation Troubleshooting](TAX_CALCULATION_TROUBLESHOOTING.md)
- [Address Validation and Geolocation Edge Cases](ADDRESS_VALIDATION_GEOLOCATION_EDGE_CASES.md)
- [Exemption Certificate Troubleshooting](EXEMPTION_CERTIFICATE_TROUBLESHOOTING.md)
- [Jurisdictions](JURISDICTIONS.md)
- [Geolocation](GEOLOCATION.md)

## Public References

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara Developer: AvaTax documentation
- Avalara tax calculation and tax risk assessment product information
