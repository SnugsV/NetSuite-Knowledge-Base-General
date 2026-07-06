# Avalara Address Troubleshooting

## Purpose
Provide a symptom-driven troubleshooting guide for Avalara-related address issues in NetSuite.

This article helps a NetSuite-focused GPT guide users through practical address checks when tax does not calculate, calculates unexpectedly, or changes after an address update.

## Source Status
This article is based on public Avalara product information and the repository's existing Avalara address knowledge articles.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html
- `ecosystem/avalara/ADDRESS_VALIDATION.md`
- `ecosystem/avalara/WHICH_ADDRESS_DOES_AVALARA_USE.md`
- `ecosystem/avalara/JURISDICTIONS.md`
- `ecosystem/avalara/GEOLOCATION.md`
- `ecosystem/avalara/DATA_FLOW.md`

## Short Answer
When an Avalara tax issue appears address-related, start with the transaction address, not only the customer record.

Review the ship-to address, bill-to address, customer address book, transaction overrides, location context, and whether the address changed after tax was calculated.

## Troubleshooting Principles

- Start with the affected transaction.
- Compare transaction addresses to customer addresses.
- Do not assume the customer default address is the address used for tax.
- Check both missing data and changed data.
- Consider jurisdiction and geolocation when tax differs by location.
- Escalate when the answer depends on private connector setup, tax configuration, or tax policy.

## Symptom: Tax Did Not Calculate After an Address Change

### Likely Causes

- Ship-to address is incomplete.
- Bill-to address is incomplete.
- Address was changed after tax calculated.
- Transaction requires recalculation.
- Address override differs from customer address book.
- Integration did not process the updated transaction.

### NetSuite Records to Review

- Sales Order
- Invoice
- Cash Sale
- Customer
- Customer address book
- Shipping address
- Billing address
- Tax fields
- Integration or connector messages

### Next Steps

1. Confirm which address changed.
2. Review the transaction-level address.
3. Compare it to the customer address book.
4. Confirm city, state, postal code, and country are populated.
5. Check whether tax was recalculated after the change.
6. Review visible tax or integration messages.

## Symptom: Tax Amount Changed Unexpectedly

### Likely Causes

- Address changed.
- Jurisdiction context changed.
- Item, amount, shipping, or discount changed.
- Invoice data differs from sales order data.
- Location or fulfillment context changed.

### NetSuite Records to Review

- Sales Order
- Invoice
- Item lines
- Customer address
- Transaction address
- Location
- Tax fields

### Next Steps

1. Compare the current address to the prior address.
2. Check whether the ship-to or bill-to address changed.
3. Review item and amount changes.
4. Compare related records, such as Sales Order and Invoice.
5. Review jurisdiction and geolocation concepts if the address changed.

## Symptom: Customer Address Looks Correct but Tax Is Wrong

### Likely Causes

- Transaction uses a different address than the customer default.
- Address override exists on the transaction.
- Multiple customer address book entries exist.
- Transaction was created before the customer address was updated.
- Related record uses a different address.

### NetSuite Records to Review

- Customer record
- Customer address book
- Transaction shipping address
- Transaction billing address
- Address override fields
- Related transactions

### Next Steps

1. Do not rely only on the customer record.
2. Open the transaction itself.
3. Compare ship-to and bill-to addresses.
4. Compare transaction address data to the customer address book.
5. Check whether the transaction address was manually overridden.

## Symptom: Sales Order and Invoice Tax Differ

### Likely Causes

- Address changed between sales order and invoice.
- Invoice did not inherit the expected address.
- Transaction was recalculated at a different stage.
- Item, amount, quantity, or discount changed.
- Location or fulfillment context changed.

### NetSuite Records to Review

- Sales Order
- Invoice
- Customer
- Shipping address
- Billing address
- Item lines
- Tax fields

### Next Steps

1. Compare the Sales Order address to the Invoice address.
2. Compare item lines and amounts.
3. Check whether the invoice was created after an address update.
4. Review whether tax recalculated on the invoice.
5. Escalate if transaction lifecycle behavior depends on configuration.

## Symptom: Wrong Jurisdiction or Location-Based Result

### Likely Causes

- Address is incomplete.
- Street-level address data is missing.
- ZIP or postal code does not fully identify the jurisdiction.
- Nearby addresses may fall into different local tax districts.
- Transaction address differs from expected address.

### NetSuite Records to Review

- Transaction address
- Customer address book
- Shipping address
- Billing address
- Location or fulfillment context

### Next Steps

1. Confirm the complete street address.
2. Confirm city, state, postal code, and country.
3. Review whether a transaction override exists.
4. Compare the address to related transactions.
5. Review `JURISDICTIONS.md` and `GEOLOCATION.md`.

## Symptom: Missing Postal Code, State, or Country

### Likely Causes

- Address was entered manually and left incomplete.
- Imported address data is incomplete.
- Customer address book entry is outdated.
- Transaction address override removed required fields.

### NetSuite Records to Review

- Customer address book
- Transaction shipping address
- Transaction billing address
- Imported transaction data where applicable

### Next Steps

1. Add or correct missing address fields.
2. Confirm the address on the transaction, not only the customer record.
3. Recalculate tax if appropriate for the workflow.
4. Review visible errors if tax still does not calculate.

## GPT Usage Guidance
When a user reports an address-related Avalara issue, the GPT should use a symptom-first response.

Recommended pattern:

1. Identify the transaction type.
2. Identify the symptom.
3. Start with transaction-level addresses.
4. Compare against customer address data.
5. Check for overrides or changes.
6. Connect address quality to jurisdiction and geolocation.
7. Recommend escalation for private configuration or tax policy questions.

The GPT should avoid saying which address Avalara definitely used unless private account documentation confirms the implementation behavior.

## Public-Safe Boundary
Do not include Holland Bar Stool-specific address rules, tax setup, custom fields, connector configuration, scripts, workflows, screenshots, or private operating procedures.

Company-specific address troubleshooting belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/ADDRESS_VALIDATION.md`
- `ecosystem/avalara/WHICH_ADDRESS_DOES_AVALARA_USE.md`
- `ecosystem/avalara/JURISDICTIONS.md`
- `ecosystem/avalara/GEOLOCATION.md`
- `ecosystem/avalara/DATA_FLOW.md`
- `ecosystem/avalara/RECORD_RELATIONSHIPS.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
