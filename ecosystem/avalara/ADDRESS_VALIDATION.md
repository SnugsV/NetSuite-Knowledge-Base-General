# Avalara Address Validation

## Purpose
Explain why address quality matters when Avalara or another tax automation platform calculates tax for NetSuite transactions.

This article helps a NetSuite-focused GPT answer questions about missing tax, unexpected tax, address errors, and location-based tax behavior.

## Source Status
This article is based on public Avalara product information and the repository's existing Avalara foundation articles.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/DATA_FLOW.md`

## Short Answer
Address quality matters because tax calculation often depends on where a transaction occurs. If the address is missing, incomplete, inconsistent, or not specific enough, tax may not calculate or may calculate differently than expected.

Avalara references address verification and geolocation as part of AvaTax calculation accuracy.

## Why Address Validation Matters
Tax can vary by location. A complete address may help determine the correct tax context more accurately than a partial address.

Address-related information may affect:

- Jurisdiction determination
- Tax rate selection
- Taxability context
- Shipping destination
- Billing context
- Error handling
- Whether a transaction can be processed by the tax integration

## Common Address Data Elements
When reviewing address quality, check for:

- Customer name or company name
- Street address
- Suite, unit, or apartment number when needed
- City
- State or province
- ZIP or postal code
- Country
- Ship-to address
- Bill-to address

## NetSuite Records to Review
Address validation questions usually involve more than one record.

Review:

- Customer record
- Customer address book
- Sales Order
- Invoice
- Cash Sale
- Credit Memo
- Shipping address
- Billing address
- Location or fulfillment context when relevant

## Common Address Problems

### Missing Address
A transaction may not have enough information to calculate tax.

Examples:

- No shipping address
- No billing address
- Missing country
- Missing postal code

### Incomplete Address
The address may exist, but important elements may be missing.

Examples:

- Street address without city or state
- ZIP code without full street address
- Missing unit or suite information
- Abbreviated or inconsistent address format

### Incorrect Address
The address may be complete but wrong.

Examples:

- Incorrect ZIP or postal code
- Wrong state
- Wrong country
- Old customer address
- Address copied from another customer

### Address Changed After Tax Calculation
If tax-relevant address information changes after tax was calculated, the transaction may need tax recalculation depending on the workflow.

Examples:

- Ship-to address changed
- Customer changed
- Address override changed
- Fulfillment location changed

### Different Addresses on Related Records
A transaction address may differ from the customer default address, invoice address, or fulfillment address.

Examples:

- Customer default address is correct, but transaction address is different
- Sales order and invoice use different addresses
- Billing and shipping addresses are not the same

## Practical Troubleshooting Flow

1. Identify the transaction type.
2. Confirm the customer selected on the transaction.
3. Review the transaction shipping address.
4. Review the transaction billing address.
5. Compare the transaction address to the customer address book.
6. Check for missing city, state, postal code, or country.
7. Confirm whether the address changed after tax calculation.
8. Review visible tax or integration errors.
9. Escalate if the issue depends on private tax configuration or connector setup.

## GPT Usage Guidance
When a user asks why tax did not calculate or why tax looks wrong, the GPT should consider address quality early in the answer.

Useful questions for the GPT to ask or suggest:

- Is the shipping address complete?
- Is the billing address complete?
- Which address is expected to drive tax?
- Did the address change after tax calculated?
- Is the transaction using the customer default address or an override?
- Are there visible address or tax integration errors?

## What This Article Does Not Cover
This article does not define company-specific tax rules, address correction rules, nexus policy, connector configuration, or legal tax guidance.

Those topics belong in private implementation documentation or should be reviewed by a tax/system administrator.

## Public-Safe Boundary
Do not include company-specific address rules, custom fields, workflows, scripts, screenshots, tax setup, or private operating procedures.

Company-specific address validation behavior belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/NETSUITE_TOUCHPOINTS.md`
- `ecosystem/avalara/RECORD_RELATIONSHIPS.md`
- `ecosystem/avalara/DATA_FLOW.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
