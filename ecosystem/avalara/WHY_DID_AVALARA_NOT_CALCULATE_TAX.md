# Why Didn't Avalara Calculate Tax?

## Purpose
Help users understand common reasons why tax may not calculate on a NetSuite transaction that is expected to use Avalara or another tax automation platform.

This article is written as a practical troubleshooting framework. It does not replace company-specific tax policy, tax setup, or implementation documentation.

## Short Answer
Tax calculation usually depends on a combination of transaction data, customer data, item data, address data, tax configuration, and integration status.

If Avalara does not calculate tax, start by checking whether NetSuite has enough valid information to determine tax and whether the tax integration was able to process the transaction.

## Common Causes

### Missing or incomplete address information
Tax automation commonly depends on ship-to, bill-to, or transaction address details.

Check whether the transaction has:

- A complete shipping address
- City, state, ZIP or postal code
- Country
- Correct customer address selection
- No obvious address entry errors

### Customer may be exempt
Some customers may be treated as tax exempt depending on tax setup, exemption certificates, entity settings, or transaction details.

Check whether the customer or transaction has exemption-related information.

### Item may not be taxable
Some items may be treated differently for tax purposes depending on item setup, item type, tax category, or product classification.

Check whether the item has the expected tax-related setup.

### Transaction may not be eligible for calculation
Some transactions, statuses, forms, subsidiaries, locations, or transaction types may not trigger tax calculation depending on the configuration.

Check whether the transaction type and status are expected to calculate tax.

### Integration may not have run successfully
A tax automation platform must receive transaction information and return a result. If the integration is unavailable, misconfigured, or blocked by an error, tax may not calculate as expected.

Check for visible error messages, integration logs, or related tax calculation status fields available in the account.

### Transaction changed after tax was calculated
If the shipping address, customer, item, quantity, amount, or fulfillment details changed after tax was calculated, the tax result may need to be recalculated depending on the workflow.

Review whether important transaction fields changed after the last tax calculation event.

## Records to Review
When troubleshooting, review the related records rather than only the transaction total.

Common records include:

- Customer
- Customer address
- Item
- Sales Order
- Invoice
- Credit Memo
- Cash Sale
- Location
- Tax-related configuration records
- Integration or connector records where applicable

## Practical Troubleshooting Flow

1. Confirm the transaction is expected to calculate tax.
2. Review the ship-to and bill-to address information.
3. Confirm the customer is not unexpectedly exempt.
4. Confirm the item is not unexpectedly non-taxable.
5. Check whether the transaction has tax-related warnings or errors.
6. Review whether the tax integration processed the transaction.
7. Recalculate tax only if that is appropriate for the transaction workflow.
8. Escalate to a tax or system administrator if the issue appears configuration-related.

## Questions a User Can Ask the GPT

- Why did this Sales Order not calculate tax?
- What records should I check when Avalara tax is missing?
- Could the customer address prevent tax from calculating?
- Could the customer be tax exempt?
- Could the item setup prevent tax calculation?
- What changed on the transaction after tax was calculated?

## Public-Safe Boundary
Do not document company-specific nexus rules, exemption approval processes, tax setup, custom fields, scripts, workflows, screenshots, or customer-specific tax decisions in this public article.

Company-specific tax procedures belong in a private enterprise repository.

## Related Articles
- `architecture/AVALARA_PLATFORM_OVERVIEW.md`
- `architecture/NETSUITE_TOUCHPOINTS.md`
- `architecture/ECOSYSTEM_DOMAINS.md`
