---
title: Drop Ship and Special Orders
module: Inventory
difficulty: Advanced
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Drop Ship and Special Orders

## Quick Summary

Drop ship and special order items are fulfilled directly by a vendor to the customer, bypassing the company's inventory. These workflows enable businesses to offer products they do not stock, expanding their catalog without inventory investment.

## Difficulty

Advanced

## Estimated Time

10 minutes

## Business Question

"How do I sell products I do not stock?"

## Overview

Not every product a company sells needs to be in its warehouse. Some items are shipped directly from the vendor to the customer (drop ship). Others are ordered from a vendor specifically for a customer order (special order). Both workflows avoid holding inventory while enabling a broader product offering.

## Drop Ship

A drop ship item is purchased from a vendor but shipped directly to the customer. The company never handles the inventory.

**Workflow**:
```
Customer places sales order
       ↓
System creates purchase order to vendor
       ↓
System creates purchase order to vendor
       ↓
Vendor ships directly to customer
       ↓
Item Fulfillment auto-created (or manually entered)
       ↓
Customer receives item
       ↓
Vendor bills company
       ↓
Company bills customer
```

## Special Order

A special order item is similar to drop ship but typically involves items not normally stocked. The company orders them specifically for the customer's request.

## When to Use Drop Ship

| Situation | Recommendation |
|---|---|
| Large/bulky items (furniture, equipment) | Drop ship to avoid warehouse storage |
| Vendor has better fulfillment capability | Vendor ships faster or more reliably |
| Low-volume items not worth stocking | Drop ship instead of holding slow movers |
| Custom-configured products | Vendor manufactures to order |
| Testing new product categories | Drop ship before committing to inventory |

## When Not to Use Drop Ship

- **High-volume, small items**: These are typically cheaper to stock and fulfill yourself
- **Vendors with poor reliability**: If the vendor has a history of shipping errors, drop ship risk is high
- **Branded packaging requirements**: If the company requires its own packaging, drop ship may not work
- **Quality-sensitive items**: You cannot inspect drop-shipped items before they reach the customer

## Trade-Offs

| Gained | Complexity Introduced |
|---|---|
| No inventory carrying cost | Lower margin (vendor marks up) |
| Unlimited product catalog | No control over fulfillment experience |
| No warehouse space needed | Customer service complexity (three-party communication) |
| No inventory risk | Return management is more complex |

## Item Setup for Drop Ship

On the item record:

1. Set the **Item Type** to **Non-Inventory** or **Inventory** (if you also stock it)
2. Check **Drop Ship** on the item record
3. Assign a **Preferred Vendor**
4. Configure the **Purchase Unit** and **Sales Unit**
5. Set up **Vendor-specific pricing**

## Order Processing

When a sales order is created for a drop ship item:

1. NetSuite automatically creates a purchase order to the designated vendor
2. The PO references the sales order
3. When the vendor ships, the Item Receipt is created (or automated)
4. The Item Fulfillment is created against the sales order
5. Tracking information flows from the PO to the SO

## Business Example

A furniture retailer sells 5,000 products but only stocks 500 of the best-selling items. The remaining 4,500 products are drop-shipped from manufacturers.

**Workflow**:
- Customer orders a custom sofa from the website
- NetSuite creates a sales order
- NetSuite auto-creates a purchase order to the manufacturer
- Manufacturer builds the sofa (4-week lead time)
- Manufacturer ships directly to the customer
- Sofa arrives at the customer's home — never touches the retailer's warehouse
- Retailer pays manufacturer, bills customer

**Result**: The retailer offers a full furniture catalog with zero inventory investment for 90% of products.

## Common Costly Mistakes

- **No visibility into vendor stock**: The vendor may be out of stock, but the website shows availability. Real-time integration is ideal.
- **Complex returns**: The customer returns to the company, but the company must coordinate with the vendor. Define the returns process before offering drop ship.
- **Brand inconsistency**: The vendor's packaging and documentation arrive at the customer's door. Ensure packaging meets brand standards.
- **No shipment tracking**: Without vendor tracking integration, customer service cannot answer "Where is my order?"
- **Assuming all items can be drop shipped**: Some vendors do not offer drop ship. Verify before setting up the item.

## Best Practices

- Use drop ship for slow movers and bulky items — not for high-volume fast movers
- Establish service level agreements with drop ship vendors (ship within 24 hours, tracking provided)
- Integrate vendor inventory feeds for real-time availability
- Define the returns process with each vendor before listing drop ship items
- Use Saved Searches to monitor drop ship order status daily

## Knowledge Check

1. A customer orders a custom-configured machine that your company does not stock. The manufacturer offers drop ship. Should you use drop ship? (Answer: Yes — the best option for custom-configured items).
2. **Scenario**: A drop-shipped item arrives damaged at the customer's location. Who is responsible? (Answer: The company that sold the item is responsible to the customer. The company then recovers from the vendor.)
3. **Decision**: Your best-selling item costs $5 and fits in a small box. Should you dropship it? (Answer: No — it is cheaper to stock and fulfill yourself than to pay the vendor's handling fee for a high-volume, low-value item.)

## Related Articles

- [Fulfilling Orders](fulfilling-orders.md)
- [Receiving Inventory](receiving-inventory.md)
- [Item Types](../item-types.md)
- [Purchase Orders](../purchasing/README.md) (future module)

## Oracle References

- [Oracle NetSuite Help Center: Drop Shipments](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Special Order Items](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)