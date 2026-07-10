# Which Address Does Avalara Use?

## Purpose
Help NetSuite users understand which address records or transaction address fields may be relevant when Avalara calculates tax.

This article is designed for a NetSuite-focused GPT that needs to guide users through address-related tax questions without assuming company-specific configuration.

## Source Status
This article is based on public Avalara product information and the repository's existing Avalara foundation articles.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html
- `ecosystem/avalara/ADDRESS_VALIDATION.md`
- `ecosystem/avalara/DATA_FLOW.md`
- `ecosystem/avalara/RECORD_RELATIONSHIPS.md`

## Short Answer
The address used for tax calculation depends on the transaction, account setup, connector behavior, and business process.

In most troubleshooting situations, users should review the transaction-level shipping address, billing address, customer address book, and any location or fulfillment context that may influence tax calculation.

Do not assume the customer default address is the same address used on the transaction.

## Address Types to Review

### Transaction Shipping Address
The shipping address is often important for sales tax because it represents where goods or services may be delivered.

Review this address when the user asks:

- Why did tax calculate for this location?
- Why did tax not calculate after changing the ship-to address?
- Why does the tax amount differ between two orders?

### Transaction Billing Address
The billing address may also be relevant depending on the transaction type, setup, or business process.

Review this address when the user asks:

- Why does the bill-to address differ from the ship-to address?
- Is the customer billing address incomplete?
- Is tax using the wrong address?

### Customer Default Address
The customer default address may populate a transaction, but it should not automatically be assumed to be the address used for tax.

Review this address when the user asks:

- Did the order pull the wrong customer address?
- Was the customer address updated after the order was created?
- Is the transaction using an old address?

### Customer Address Book
The address book may contain multiple addresses for the same customer. A transaction may use one address even if another address is marked as a default.

Review this area when the user asks:

- Which customer address was selected?
- Are there duplicate or outdated addresses?
- Is the selected transaction address different from the expected address book entry?

### Transaction Address Override
Some transactions may contain manually entered or overridden address information. An override can differ from the customer record.

Review this area when the user asks:

- Did someone manually change the address?
- Why does the order address not match the customer record?
- Did an address override affect tax?

### Location or Fulfillment Context
Location, warehouse, subsidiary, or fulfillment context may matter depending on account setup and transaction workflow.

Review this area when the user asks:

- Did the fulfillment location affect tax?
- Does the order ship from a different location than expected?
- Did location change after the order was entered?

## Common Misunderstandings

### The customer address and transaction address may not match
A customer record may have a correct address while the transaction uses a different, outdated, incomplete, or overridden address.

### Changing a customer address may not update existing transactions
Updating the customer address book may not automatically update transactions that were already created.

### Ship-to and bill-to may serve different purposes
A transaction may contain both shipping and billing addresses. Users should review both before assuming which address drove tax.

### Address changes may require recalculation
If tax-relevant address information changes after tax calculation, the transaction may need tax recalculation depending on the workflow.

### Related records may use different addresses
A sales order, invoice, cash sale, credit memo, and fulfillment record may not always carry identical address context.

## Practical Troubleshooting Flow

1. Open the transaction with the tax issue.
2. Identify the transaction type.
3. Review the transaction shipping address.
4. Review the transaction billing address.
5. Compare transaction addresses to the customer address book.
6. Check for manual address overrides.
7. Review whether the address changed after tax calculated.
8. Review location or fulfillment context if relevant.
9. Check for visible Avalara or tax integration messages.
10. Escalate if address selection depends on private connector setup or account configuration.

## GPT Usage Guidance
When a user asks which address Avalara used, the GPT should avoid making a definitive configuration-specific claim unless the repository contains private account documentation.

Instead, it should guide the user through the likely address sources and explain that the actual address used may depend on NetSuite setup, connector behavior, transaction type, and workflow.

Suggested GPT response pattern:

1. Explain that address selection can depend on setup.
2. Ask which transaction type is involved.
3. Direct the user to compare ship-to, bill-to, customer address book, and transaction overrides.
4. Suggest checking whether tax was calculated before or after an address change.
5. Recommend escalation if connector configuration determines the final behavior.

## Public-Safe Boundary
Do not include company-specific address sourcing rules, custom fields, workflows, connector settings, scripts, screenshots, tax setup, or private operating procedures.

Company-specific address selection behavior belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/ADDRESS_VALIDATION.md`
- `ecosystem/avalara/DATA_FLOW.md`
- `ecosystem/avalara/NETSUITE_TOUCHPOINTS.md`
- `ecosystem/avalara/RECORD_RELATIONSHIPS.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
