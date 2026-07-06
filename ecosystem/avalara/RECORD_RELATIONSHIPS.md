# Avalara Record Relationships

## Purpose
Explain how common NetSuite records relate to Avalara tax calculation, exemption handling, and tax troubleshooting.

This article helps a NetSuite-focused GPT reason across records instead of treating Avalara issues as isolated transaction problems.

## Source Status
This article is based on public Avalara product information and the repository's existing Avalara foundation articles.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/NETSUITE_TOUCHPOINTS.md`

## Short Answer
Avalara-related questions usually involve a chain of NetSuite records.

A tax issue on a transaction may be caused by the transaction itself, but it may also be caused by the customer, address, item, location, exemption information, or integration status connected to that transaction.

## Core Relationship Model

```text
Customer
  |
  |-- Customer Address
  |
  |-- Exemption Information
  |
  |-- Sales Order
        |
        |-- Item Lines
        |-- Shipping Address
        |-- Billing Address
        |-- Location
        |-- Tax Fields
        |-- Invoice
        |-- Cash Sale
        |-- Credit Memo
```

This model is intentionally generic. Specific account behavior depends on configuration and belongs in private implementation documentation.

## Primary Record Relationships

### Customer to Address
A customer may have one or more billing or shipping addresses. Address quality can affect tax calculation because Avalara references address verification and geolocation as part of tax calculation accuracy.

Questions this relationship helps answer:

- Is the correct customer address being used?
- Is the address complete?
- Is the transaction using a different address than expected?

### Customer to Exemption Information
A customer's exemption status or exemption documentation may affect whether tax is calculated.

Questions this relationship helps answer:

- Is the customer treated as tax exempt?
- Is exemption information active, missing, expired, or incomplete?
- Is the transaction expected to calculate tax for this customer?

### Customer to Sales Order
The customer selected on a sales order can determine default addresses, tax-related fields, and other transaction context.

Questions this relationship helps answer:

- Was the correct customer selected?
- Did customer defaults populate the transaction?
- Did the customer's exemption status affect tax?

### Sales Order to Item Lines
Sales orders contain item lines, and item taxability may affect whether tax calculates on each line.

Questions this relationship helps answer:

- Are all items taxable?
- Are some lines taxable while others are not?
- Did item setup or classification affect the result?

### Sales Order to Address
A sales order may include shipping and billing address information. Depending on the process, tax may depend on one or more address fields.

Questions this relationship helps answer:

- Which address is being used for tax?
- Was the address changed after tax calculated?
- Does the transaction address match the customer address?

### Sales Order to Location
Location can matter when tax depends on origin, fulfillment location, subsidiary, warehouse, or transaction context.

Questions this relationship helps answer:

- Is the correct location selected?
- Did the location change the tax context?
- Does the transaction have enough location information?

### Sales Order to Invoice
An invoice may be created from a sales order. If transaction data changes between order entry and invoicing, tax results may differ.

Questions this relationship helps answer:

- Did the invoice inherit tax from the sales order?
- Did tax recalculate on the invoice?
- Did address, item, amount, or customer data change before invoicing?

### Sales Order to Cash Sale
A cash sale may represent a taxable sales transaction. It may use customer, item, address, and location data similarly to other sales transactions.

Questions this relationship helps answer:

- Is the cash sale using the expected customer?
- Is the transaction address complete?
- Are item lines taxable?

### Sales Order or Invoice to Credit Memo
A credit memo may adjust or reverse prior taxable activity. Avalara states that AvaTax can calculate sales tax on credit memos.

Questions this relationship helps answer:

- Is the credit memo connected to the original transaction?
- Does the credit memo use the same customer and address context?
- Why does credit memo tax differ from the original transaction?

### Transaction to Integration Status
A transaction may need to be sent to Avalara or processed by an integration before tax values are returned to NetSuite.

Questions this relationship helps answer:

- Was the transaction sent successfully?
- Did Avalara return a tax result?
- Is there a visible integration or connector error?

## How to Troubleshoot by Relationship

When a user asks why Avalara did not calculate tax, the GPT should reason through the record chain:

1. Identify the transaction type.
2. Check the customer relationship.
3. Check the customer and transaction addresses.
4. Check exemption information.
5. Check item lines and item taxability.
6. Check transaction status and tax fields.
7. Check location or subsidiary context if relevant.
8. Check integration status or visible errors.

## Common Reasoning Patterns

### Tax missing on the whole transaction
Likely areas to review:

- Customer
- Address
- Transaction type
- Integration status
- Tax configuration

### Tax missing on one line only
Likely areas to review:

- Item
- Item taxability
- Line-level tax data
- Product classification

### Tax differs between sales order and invoice
Likely areas to review:

- Address changes
- Item or quantity changes
- Amount changes
- Recalculation timing
- Invoice creation process

### Customer unexpectedly tax exempt
Likely areas to review:

- Customer exemption status
- Exemption certificate information
- Transaction exemption indicators
- Tax-related customer settings

### Credit memo tax does not match original transaction
Likely areas to review:

- Original transaction linkage
- Customer and address context
- Item lines
- Transaction amounts
- Tax recalculation behavior

## GPT Usage Guidance
The GPT should avoid answering Avalara questions from a single record only.

Avalara questions should usually be answered by considering the relationship between:

- Customer
- Address
- Item
- Transaction
- Location
- Exemption information
- Integration status

If the question depends on private tax setup, nexus decisions, custom fields, scripts, or workflows, the GPT should recommend escalation to a system administrator or tax owner.

## Public-Safe Boundary
Do not include Holland Bar Stool tax setup, nexus decisions, customer-specific exemption rules, custom fields, workflows, scripts, screenshots, or private operating procedures.

Company-specific record behavior belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/BUSINESS_PURPOSE.md`
- `ecosystem/avalara/NETSUITE_TOUCHPOINTS.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
