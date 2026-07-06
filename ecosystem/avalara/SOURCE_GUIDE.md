# Avalara Source Guide

## Purpose
Identify public Avalara source locations that can be used to build Avalara-related NetSuite knowledge articles.

This guide helps keep future Avalara articles grounded in public product information while avoiding company-specific tax procedures or private implementation details.

## Primary Public Source

### Avalara Knowledge Center
URL: https://knowledge.avalara.com/

The Avalara Knowledge Center is a public help and documentation hub. It presents itself as a place to find answers, how-tos, troubleshooting, and related support information.

Use this source for:

- Product concepts
- How-to topics
- Troubleshooting patterns
- Tax automation terminology
- AvaTax guidance
- Exemption certificate topics
- Address validation topics
- Connector and integration topics when publicly available

## Existing Public Product Source

### Avalara NetSuite Integration Page
URL: https://www.avalara.com/us/en/products/integrations/netsuite.html

Use this source for:

- High-level Avalara and NetSuite positioning
- NetSuite integration context
- Public product capability summaries
- AvaTax and tax compliance overview information

## How to Use Avalara Sources
When building repository articles from Avalara public resources:

1. Start with the Avalara Knowledge Center for practical support topics.
2. Use the Avalara NetSuite integration page for product and integration framing.
3. Summarize concepts in original wording.
4. Connect the concepts back to NetSuite records and transaction workflows.
5. Mark uncertain or implementation-dependent behavior as needing verification.
6. Keep articles focused on what a NetSuite user or support team member may ask.

## Article Types to Create
Avalara source research should support both factual and practical articles.

### Factual Foundation Articles
Examples:

- `PRODUCT_FACTS.md`
- `TERMINOLOGY.md`
- `NETSUITE_TOUCHPOINTS.md`
- `RECORD_RELATIONSHIPS.md`
- `DATA_FLOW.md`

### Practical Question Articles
Examples:

- `WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
- `WHY_IS_THE_TAX_AMOUNT_DIFFERENT_THAN_EXPECTED.md`
- `WHICH_ADDRESS_DOES_AVALARA_USE.md`
- `WHAT_INFORMATION_IS_SENT_TO_AVALARA.md`
- `WHY_IS_A_CUSTOMER_TAX_EXEMPT.md`

## Public-Safe Boundary
Do not include:

- Holland Bar Stool tax configuration
- Nexus decisions
- Customer-specific tax data
- Exemption approval procedures
- Custom NetSuite fields
- Workflows
- Scripts
- Screenshots
- Internal implementation notes
- Private operating procedures

Company-specific Avalara knowledge belongs in a private enterprise repository.

## Related Articles
- `ecosystem/avalara/PRODUCT_FACTS.md`
- `ecosystem/avalara/WHY_DID_AVALARA_NOT_CALCULATE_TAX.md`
- `architecture/AVALARA_PLATFORM_OVERVIEW.md`
