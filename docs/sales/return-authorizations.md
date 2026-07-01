---
title: Return Authorizations
module: Sales
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Return Authorizations

## Quick Summary

A Return Authorization (RA) initiates and tracks the process of accepting returned goods from a customer. It documents what is being returned, why, and whether a refund, replacement, or credit will be issued.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Returns are inevitable in any sales operation. Products arrive damaged, customers change their minds, or the wrong item was shipped. A structured return process protects the company's revenue while maintaining customer satisfaction.

## The Return Workflow

```
Customer requests return
       ↓
RA Created and Approved
       ↓
RA sent to customer / return label provided
       ↓
Items received at warehouse
       ↓
Inspection / Quality Check
       ↓
Disposition: Restock, Repair, Dispose
       ↓
Credit Memo or Refund Issued
       ↓
Inventory Adjusted (if restocked)
```

## Return Authorization Fields

```
Transactions > Returns > Return Authorizations
```

| Field | Purpose |
|---|---|
| **Customer** | Who is returning the goods |
| **Sales Order** | Original order reference |
| **Item** | What is being returned |
| **Quantity** | How many units |
| **Return Reason** | Why it is being returned |
| **Disposition** | Restock, repair, or dispose |
| **RMA Number** | Customer-facing return reference |
| **Authorization Status** | Pending, approved, received, closed |

## Disposition Options

| Disposition | Description | Inventory Impact |
|---|---|---|
| **Restock** | Item is sellable — return to inventory | Increase On Hand at original cost |
| **Repair / Rework** | Item needs work before resale | Hold in repair inventory |
| **Dispose** | Item is damaged beyond use | Write off — do not add to inventory |
| **Vendor Return** | Defective item returned to supplier | Vendor return transaction |

## Return Reasons

Categorizing return reasons helps identify trends:

| Category | Reasons |
|---|---|
| **Defective** | Product failed, damaged in transit |
| **Quality** | Does not meet specifications |
| **Customer Error** | Ordered wrong item, changed mind |
| **Fulfillment Error** | Wrong item shipped, incorrect quantity |
| **Shipping Damage** | Damaged during delivery |

## Credit Memo and Refunds

When a return is processed:

| Action | Financial Impact |
|---|---|
| **Credit Memo** | Reduces customer's AR balance |
| **Refund** | Returns cash to customer |
| **Replacement** | Ships new item, no financial adjustment |

## Business Example

A customer received a damaged chair (SKU CHAIR-100) and requests a return.

1. Customer service creates an RA referencing the original sales order
2. Reason: "Damaged in transit"
3. Disposition: Dispose (frame is cracked, cannot be repaired)
4. Return label sent to customer
5. Chair received at warehouse — condition confirmed
6. Credit memo issued for the purchase price
7. Inventory adjustment: 1 unit written off to damaged goods expense
8. RA status: Closed

**Result**: Customer is refunded promptly. The company identifies a packaging issue from the carrier and files a claim.

## Common Mistakes

- **No inspection before restocking**: Adding damaged items back to sellable inventory creates downstream quality issues
- **Poor return reason tracking**: Without reason codes, you cannot identify defect trends by product or supplier
- **Refunding before goods are received**: Issuing credit memos before verifying the return increases fraud risk
- **No return timeframe policy**: Customers returning items years after purchase create inventory and accounting complications
- **Ignoring return rate trends**: A high return rate for a specific product indicates a quality or fulfillment problem

## Best Practices

- Require an RA for every return
- Inspect returned items before restocking or disposing
- Use return reason codes and analyze trends monthly
- Establish clear return policies (time limit, condition requirements, restocking fees)
- Automate credit memo generation from approved RAs
- Monitor return rates by product and customer
- Use Saved Searches to track aging RAs and unresolved returns

## Knowledge Check

1. A customer returns an item that is in perfect condition but no longer needed. What disposition? (Answer: Restock — add back to sellable inventory.)
2. **Scenario**: A returned item is inspected and found to have a manufacturing defect. Should it be restocked? (Answer: No — either send to the vendor for credit or dispose and file a warranty claim.)
3. **Decision**: Your company's return rate for a specific product is 15%. The average return rate is 3%. What should you investigate? (Answer: The product may have a quality issue, the product description may be misleading, or the fulfillment process may be damaging the product.)

## Related Articles

- [Sales Orders](sales-orders.md)
- [Order Fulfillment](order-fulfillment.md)
- [Invoicing and Revenue](invoicing-and-revenue.md)
- [Inventory: Returns Processing](../inventory/returns-processing.md)
- [Inventory: Inventory Adjustments](../inventory/inventory-adjustments.md)

## Oracle References

- [Oracle NetSuite Help Center: Return Authorizations](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)