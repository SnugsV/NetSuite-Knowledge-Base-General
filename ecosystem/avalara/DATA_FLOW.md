# Avalara Data Flow

## Purpose
Explain the high-level flow of information between NetSuite and Avalara during tax-related processes.

This article helps a NetSuite-focused GPT understand the sequence of events behind tax calculation and related troubleshooting questions.

## Source Status
This article is based on public Avalara product information and the repository's existing Avalara foundation articles.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/NETSUITE_TOUCHPOINTS.md`
- `ecosystem/avalara/RECORD_RELATIONSHIPS.md`

## Short Answer
Avalara-related data flow usually starts with a NetSuite transaction, gathers relevant customer, address, item, location, and transaction information, sends tax-relevant data to Avalara, receives a tax result, and stores or displays that result back on the NetSuite transaction.

The exact behavior depends on the NetSuite account, connector, tax setup, and transaction workflow.

## Conceptual Flow

```text
User creates or edits transaction
        |
        v
NetSuite transaction data is available
        |
        v
Customer, address, item, location, and amount data are evaluated
        |
        v
Tax-relevant information is sent to Avalara
        |
        v
Avalara evaluates tax context
        |
        v
Avalara returns tax result or error
        |
        v
NetSuite tax fields and totals are updated or reviewed
        |
        v
User saves, reviews, invoices, credits, or investigates the transaction
```

## Main Data Elements

### Customer Data
Customer data may help determine the buyer, default addresses, exemption status, and transaction context.

Common troubleshooting question:

- Was the correct customer selected?

### Address Data
Address data may help determine where tax applies. Avalara references address verification and geolocation as part of tax calculation accuracy.

Common troubleshooting questions:

- Is the shipping address complete?
- Is the billing address complete?
- Which address is being used?
- Did the address change after tax calculated?

### Item Data
Item data may help determine product or service taxability.

Common troubleshooting questions:

- Are the items taxable?
- Are item classifications or tax categories correct?
- Is tax missing only on certain lines?

### Transaction Data
Transaction data includes type, status, date, amount, line details, discounts, shipping, and tax fields.

Common troubleshooting questions:

- Is this transaction expected to calculate tax?
- Did the amount or line detail change?
- Did tax calculate before or after the change?

### Location or Subsidiary Data
Location, warehouse, subsidiary, or company context may matter depending on account setup and transaction workflow.

Common troubleshooting questions:

- Is the correct location selected?
- Is the transaction associated with the expected business unit or subsidiary?

### Exemption Data
Exemption data may affect whether tax is calculated for a customer or transaction.

Common troubleshooting questions:

- Is the customer tax exempt?
- Is exemption information active or missing?
- Is the transaction expected to be taxable?

### Integration Status
The integration must process the transaction successfully for Avalara tax results to return to NetSuite.

Common troubleshooting questions:

- Was the transaction sent?
- Was there an error?
- Did Avalara return a response?

## Data Flow by Transaction Stage

### Before Calculation
Before tax calculation, review whether the transaction has enough information to determine tax.

Important areas:

- Customer
- Address
- Items
- Transaction date
- Amounts
- Location or subsidiary context
- Exemption information

### During Calculation
During tax calculation, NetSuite and the Avalara connector or integration use transaction data to request a tax result.

Important areas:

- Triggering event
- Connector availability
- Valid transaction data
- Tax-relevant fields
- Communication with Avalara

### After Calculation
After calculation, tax results or errors are reflected back in NetSuite.

Important areas:

- Tax amount
- Tax fields
- Error messages
- Transaction status
- Recalculation needs
- User review

## Common Data Flow Breakpoints

### Missing Data
Tax may not calculate if important information is missing.

Examples:

- Missing address
- Missing customer
- Missing item data
- Missing location context

### Invalid Data
Tax may not calculate correctly if information exists but is incomplete or invalid.

Examples:

- Incomplete ZIP or postal code
- Incorrect state or country
- Incorrect customer address
- Unexpected item classification

### Changed Data
Tax may need to be recalculated if tax-relevant fields change after calculation.

Examples:

- Address changed
- Item changed
- Quantity changed
- Amount changed
- Customer changed

### Integration Issue
Tax may not calculate if the integration cannot process the transaction.

Examples:

- Connector error
- Communication failure
- Missing required configuration
- Transaction not eligible for processing

## GPT Troubleshooting Logic
When answering Avalara tax calculation questions, the GPT should reason through the data flow:

1. What transaction is involved?
2. What customer is selected?
3. What address is being used?
4. What items are on the transaction?
5. Is exemption information involved?
6. Did tax-relevant data change?
7. Did the integration process successfully?
8. What tax result or error is visible in NetSuite?

## Public-Safe Boundary
Do not include company-specific connector setup, tax rules, nexus decisions, custom fields, workflows, scripts, screenshots, or private operating procedures.

Company-specific Avalara data flow belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/TERMINOLOGY.md`
- `ecosystem/avalara/BUSINESS_PURPOSE.md`
- `ecosystem/avalara/NETSUITE_TOUCHPOINTS.md`
- `ecosystem/avalara/RECORD_RELATIONSHIPS.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
