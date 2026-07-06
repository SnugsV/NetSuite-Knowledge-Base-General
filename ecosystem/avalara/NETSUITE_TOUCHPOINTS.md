# Avalara NetSuite Touchpoints

## Purpose
Identify the common NetSuite records and transaction areas that may interact with Avalara or another tax automation platform.

This article helps a NetSuite-focused GPT understand where Avalara-related questions usually connect inside NetSuite.

## Source Status
This article is based on public Avalara product information and the repository's existing NetSuite ecosystem model.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `architecture/NETSUITE_TOUCHPOINTS.md`

## Short Answer
Avalara-related NetSuite questions usually connect to customer, address, item, transaction, tax, and integration data.

When tax does not calculate or appears incorrect, the issue is often related to one or more of these touchpoints rather than Avalara alone.

## Primary NetSuite Touchpoints

### Customer Records
Customer records may affect tax behavior because they can contain billing information, shipping information, exemption status, tax-related settings, and default addresses.

Common questions:

- Is the customer tax exempt?
- Does the customer have the correct address?
- Is the correct customer selected on the transaction?

### Customer Addresses
Address data is one of the most important touchpoints for tax calculation. Avalara references address verification and geolocation as part of tax calculation accuracy.

Common questions:

- Is the ship-to address complete?
- Is the bill-to address complete?
- Which address is being used for tax?
- Is the address valid enough for tax calculation?

### Item Records
Item records may affect tax calculation because different products or services can have different taxability rules.

Common questions:

- Is the item taxable?
- Does the item have the expected tax classification?
- Are all transaction lines using the correct items?

### Sales Orders
Sales orders are often where users first expect tax to calculate during order entry.

Common questions:

- Why did tax not calculate on the sales order?
- Did changing the address change the tax result?
- Did changing the item or quantity require recalculation?

### Invoices
Invoices may represent the final taxable transaction depending on the business process.

Common questions:

- Did tax calculate differently on the invoice than on the sales order?
- Was the invoice created from an order that already had tax calculated?
- Did transaction data change before invoicing?

### Cash Sales
Cash sales may also require tax calculation when they represent taxable sales transactions.

Common questions:

- Why did tax not calculate on a cash sale?
- Is the cash sale using the correct customer and address?

### Credit Memos
Credit memos can adjust or reverse taxable activity. Avalara states that AvaTax can calculate tax on credit memos.

Common questions:

- Why did tax calculate on a credit memo?
- Why does the credit memo tax not match the original transaction?
- Was the credit memo tied to the original transaction?

### Locations
Location information may matter when tax depends on origin, fulfillment location, subsidiary, warehouse, or transaction context.

Common questions:

- Does the transaction have the correct location?
- Did the fulfillment location affect the tax calculation?

### Tax Fields and Tax Totals
Tax-related fields and totals are where users usually notice a problem.

Common questions:

- Why is the tax amount blank?
- Why is the tax amount different than expected?
- Was tax recalculated after the transaction changed?

### Integration or Connector Records
Avalara must receive transaction information and return a result. Connector or integration records may help explain whether the transaction was processed successfully.

Common questions:

- Did the integration run?
- Was there an error message?
- Was the transaction sent to Avalara?

## Troubleshooting Perspective
When investigating an Avalara issue in NetSuite, do not look only at the tax total.

Also review:

1. Customer
2. Customer address
3. Item lines
4. Transaction type
5. Transaction status
6. Location or subsidiary context
7. Tax-related fields
8. Integration status or errors

## GPT Usage Guidance
When a user asks an Avalara question, the GPT should identify which touchpoint is most likely involved before providing troubleshooting steps.

For example:

- Address issue: start with customer and transaction addresses.
- Exemption issue: start with customer and exemption information.
- Item issue: start with item taxability.
- Transaction issue: start with transaction type, status, and tax fields.
- Integration issue: start with connector status or visible error messages.

## Public-Safe Boundary
Do not include company-specific tax configuration, nexus decisions, custom fields, workflows, scripts, screenshots, approval processes, or private operating procedures.

Company-specific Avalara and NetSuite setup belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/BUSINESS_PURPOSE.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
- `architecture/NETSUITE_TOUCHPOINTS.md`
