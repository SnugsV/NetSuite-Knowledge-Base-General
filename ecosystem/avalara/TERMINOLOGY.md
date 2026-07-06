# Avalara Terminology

## Purpose
Define common Avalara and tax automation terms that appear in NetSuite-related knowledge articles.

This document gives a NetSuite-focused GPT factual vocabulary it can use when answering Avalara questions.

## Source Status
This terminology is based on public Avalara product and support information.

Sources reviewed:

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara NetSuite integration page: https://www.avalara.com/us/en/products/integrations/netsuite.html

## Terms

### Avalara
Avalara is a tax compliance software provider. In a NetSuite context, Avalara is commonly associated with tax calculation, tax compliance workflows, returns, and exemption certificate management.

### AvaTax
AvaTax is Avalara's tax calculation service. Avalara describes AvaTax as using geolocation and address verification to calculate sales tax for a specific address.

### Tax Calculation
Tax calculation is the process of determining the tax amount for a transaction. It may depend on customer information, address information, item taxability, jurisdiction, transaction type, and integration status.

### Sales Tax
Sales tax is tax commonly calculated on sales transactions. In NetSuite, sales tax questions often involve sales orders, invoices, cash sales, credit memos, customers, addresses, and items.

### Use Tax
Use tax is tax that may apply when tax was not collected at the time of purchase or sale. Avalara offers products related to use tax compliance.

### Jurisdiction
A jurisdiction is a tax authority area that may impose tax. A single address can involve more than one jurisdiction.

### Geolocation
Geolocation means identifying a location precisely enough to support tax calculation. Avalara references geolocation as part of AvaTax calculation accuracy.

### Address Verification
Address verification is the process of checking address information. Avalara notes that accurate and complete address data supports more reliable rates.

### Item Taxability
Item taxability describes whether and how an item is taxable. In NetSuite troubleshooting, item setup or classification may affect tax behavior.

### Exemption Certificate
An exemption certificate is documentation that supports a customer's tax-exempt status. Avalara provides exemption certificate management capabilities.

### Returns
Returns are tax filing processes used to prepare, file, and remit tax. Avalara offers returns preparation and filing solutions.

### Nexus
Nexus refers to a business connection with a jurisdiction that may create a tax obligation. Avalara references economic nexus tracking and alerts as part of its compliance capabilities.

### Tax Obligation
A tax obligation is a requirement to collect, report, file, or remit tax in a jurisdiction.

### NetSuite Connector
A NetSuite connector is an integration path between NetSuite and Avalara products. Avalara describes NetSuite connectors for NetSuite editions and OneWorld environments.

### SuiteTax
SuiteTax is NetSuite's tax framework. Avalara describes a NetSuite SuiteTax integration option that can extend SuiteTax capabilities.

### Credit Memo
A credit memo is a transaction that can reverse or adjust prior sales activity. Avalara states that AvaTax can calculate sales tax on credit memos.

## Questions This Supports
- What is AvaTax?
- Why does address quality matter for tax calculation?
- What is an exemption certificate?
- What is nexus?
- What is item taxability?
- How does Avalara relate to NetSuite SuiteTax?

## Public-Safe Boundary
Keep this document limited to public product terminology and generic NetSuite concepts.

Do not add company-specific tax setup, tax policy, custom fields, workflows, scripts, private implementation notes, customer-specific tax decisions, or screenshots.

## Related Articles
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/SOURCE_GUIDE.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
- `architecture/AVALARA_PLATFORM_OVERVIEW.md`
