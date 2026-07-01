---
title: Scenario Library
module: Integrations
difficulty: Intermediate
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Pacejet Scenario Library

## Purpose

Real-world business scenarios that demonstrate how Pacejet is configured and used in different operational contexts. Each scenario teaches business reasoning, not button-clicking.

## How to Use This Library

1. Find the scenario closest to your customer's situation
2. Read the business context and objective
3. Understand the recommended configuration
4. Learn from common mistakes
5. Use the validation steps to confirm success

## Scenario 1: High-Volume Parcel Shipping

### Business Context

A distributor ships 500+ packages per day across three carriers (FedEx, UPS, Armour). They currently log into each carrier's website individually to generate labels. On-time shipment rates are dropping because the team spends more time on label generation than on picking and packing.

### Customer Objective

- Automate label generation for all shipments
- Select the lowest-cost carrier automatically
- Reduce per-package handling time by 60%
- Eliminate manual entry of tracking numbers into NetSuite

### Recommended Configuration

| Setting | Value |
|---|---|
| Auto-ship | Enabled |
| Carrier selection rule | Lowest cost |
| Label generation | Standard carrier labels |
| Tracking update | Automatic to NetSuite via connector |

### Business Workflow

```
Fulfillment created in NetSuite
  → Auto-ship triggers Pacejet
  → Rate shopping across FedEx, UPS, Armour
  → Lowest-cost carrier selected automatically
  → Label generated on warehouse printer
  → Tracking number returned to NetSuite
  → Fulfillment updated, customer notifications sent
```

### Common Implementation Mistakes

| Mistake | Impact |
|---|---|
| No auto-ship rules configured | Still requires manual carrier selection for each shipment |
| Item weights not maintained | Wrong rates because dimensional weight used instead of actual weight |
| Package dimensions missing | Rates calculated without dimensional weight consideration |
| Carrier contracts not loaded | Published rates used instead of negotiated contract rates |

### Validation Steps

1. Create a test fulfillment in NetSuite
2. Verify the auto-ship triggers Pacejet
3. Verify rates from all three carriers are displayed
4. Confirm the lowest-cost carrier was selected
5. Verify a label was generated
6. Verify tracking number was returned to NetSuite
7. Verify the fulfillment shows the tracking number

### Success Criteria

- Auto-ship processes 100% of fulfillments
- Label generation time: < 5 seconds per package
- Tracking numbers returned to NetSuite automatically
- No manual carrier selection required

---

## Scenario 2: Multi-Warehouse Operations

### Business Context

A company operates three warehouses (East Coast, Midwest, West Coast). Each warehouse ships to customers in its region. Some customers are served by the nearest warehouse; others have contracted carrier agreements that dictate the carrier regardless of origin.

### Customer Objective

- Configure each warehouse as a separate ship-from location
- Route shipments to the nearest warehouse automatically
- Apply customer-specific carrier agreements where applicable
- Consolidate reporting across all three warehouses

### Recommended Configuration

| Setting | Value |
|---|---|
| Warehouses | 3 ship-from locations configured in NetSuite and Pacejet |
| Fulfillment routing | By warehouse location (nearest to customer) |
| Carrier selection | Lowest cost by origin location |
| Trading partners | Customer-specific carrier agreements where applicable |
| Reporting | Consolidated across all warehouses via Pacejet analytics |

### Business Workflow

```
Sales order assigned to nearest warehouse
  → Fulfillment created at that warehouse
  → Pacejet receives shipment with correct origin
  → Rate shopping from the assigned warehouse
  → Customer-specific carrier agreement applied if applicable
  → Label generated at the shipping warehouse
  → Tracking returned to NetSuite
```

### Common Implementation Mistakes

| Mistake | Impact |
|---|---|
| Warehouses not configured as separate locations | All shipments show same origin, incorrect rates |
| Item location not set on fulfillment | Pacejet receives wrong origin for rate calculation |
| Customer carrier agreements not configured | Contract rates not applied to qualifying customers |
| No routing rules | Shipments may be fulfilled from wrong warehouse |

### Validation Steps

1. Create test fulfillments from each warehouse
2. Verify origin address on labels matches the correct warehouse
3. Verify rates are calculated from the correct origin
4. Test a customer with a carrier agreement — verify contract rate is used
5. Verify tracking numbers return to the correct fulfillment

### Success Criteria

- Each warehouse ships from its correct origin
- Customer carrier agreements are applied automatically
- Reporting shows shipments by warehouse
- No manual origin correction needed

---

## Scenario 3: International Shipping

### Business Context

A manufacturer ships products to customers in Canada, Mexico, and the EU. They need to generate customs documentation, screen against restricted party lists, and manage duties and taxes.

### Customer Objective

- Generate customs invoices with each international shipment
- Screen shipments against restricted party lists
- Include harmonized tariff codes and country of origin on labels
- Provide landed cost estimates to international customers

### Recommended Configuration

| Setting | Value |
|---|---|
| International shipping | Enabled |
| Customs documents | Commercial invoice generated automatically |
| Restricted party screening | Enabled |
| Harmonized tariff codes | Configured on item records |
| Country of origin | Configured on item records |

### Business Workflow

```
International sales order created
  → Fulfillment triggers Pacejet
  → Pacejet screens against restricted party lists
  → Customs documents generated (commercial invoice, packing list)
  → Carrier selected with international service level
  → Label generated with customs information
  → Tracking shared with customer
```

### Common Implementation Mistakes

| Mistake | Impact |
|---|---|
| HS codes not on item records | Customs documents incomplete, shipment delayed |
| Country of origin not configured | Incorrect duties applied, or shipment rejected |
| Restricted party screening off | Compliance risk, potential fines |
| Commercial invoice format wrong | Carrier rejects the shipment at pickup |

### Validation Steps

1. Create a test international fulfillment
2. Verify restricted party screening passes
3. Verify commercial invoice is generated with correct HS codes
4. Verify country of origin on the label
5. Verify carrier international service level is available

### Success Criteria

- Commercial invoices generated for 100% of international shipments
- Restricted party screening active on all international orders
- No customs-related shipment holds

---

## Scenario 4: LTL Freight

### Business Context

A manufacturer ships palletized freight to distributors via LTL carriers (Estes, XPO, TForce). Each shipment has multiple line items, pallet weights, and liftgate requirements.

### Customer Objective

- Get LTL rates from multiple carriers automatically
- Include liftgate and residential delivery surcharges accurately
- Generate Bill of Lading with each shipment
- Track LTL shipments from pickup to delivery

### Recommended Configuration

| Setting | Value |
|---|---|
| LTL carriers | Estes, XPO, TForce activated |
| Freight class | Configured on item or shipment level |
| Accessorials | Liftgate, residential delivery, call before delivery |
| Documents | Bill of Lading generated automatically |

### Business Workflow

```
Fulfillment with multiple line items
  → Pallet dimensions and weight captured
  → Pacejet queries LTL carriers for rates
  → Accessorials (liftgate, residential) included in rate
  → Carrier selected
  → Bill of Lading generated
  → Label generated
```

### Common Implementation Mistakes

| Mistake | Impact |
|---|---|
| Freight class not set | Rates calculated with default class, may be overcharged |
| Liftgate not requested when needed | Driver cannot deliver, reschedule fee |
| Pallet dimensions not captured | Rate based on incorrect dimensional weight |
| Residential delivery not flagged | Additional surcharge not included, invoice adjustment later |

### Validation Steps

1. Create a test LTL fulfillment
2. Verify LTL carriers return rates
3. Verify liftgate and residential surcharges are included
4. Verify Bill of Lading is generated
5. Verify tracking is available

### Success Criteria

- LTL rates from multiple carriers for every freight shipment
- Accessorial surcharges included at time of rating
- Bill of Lading generated automatically

---

## Scenario 5: Drop-Ship Fulfillment

### Business Context

A company sells products that are drop-shipped directly from vendors to customers. The vendor needs a shipping label to attach to the package, but the vendor doesn't have Pacejet. The company generates the label in Pacejet and sends it to the vendor.

### Customer Objective

- Generate labels for drop-ship orders where the vendor ships directly
- Use the vendor's address as the ship-from origin
- Send the label to the vendor electronically
- Track the shipment

### Recommended Configuration

| Setting | Value |
|---|---|
| Drop-ship POs | Create from sales order |
| Fulfillment origin | Vendor address |
| Label generation | Company generates, sends to vendor |
| Tracking | Vendor confirms shipment, tracking entered |

### Business Workflow

```
Drop-ship sales order
  → Purchase order created to vendor
  → Company creates fulfillment (for label generation only)
  → Pacejet generates label with vendor as origin
  → Label sent to vendor
  → Vendor ships and provides tracking
  → Tracking updated in NetSuite
```

### Common Implementation Mistakes

| Mistake | Impact |
|---|---|
| Wrong origin address on label | Package shipped from wrong location, incorrect rates |
| Vendor not set up as location | Cannot generate label with vendor as origin |
| Label format not compatible with vendor's printer | Vendor cannot print the label |
| No process for receiving tracking from vendor | System never shows tracking number |

### Validation Steps

1. Create a test drop-ship sales order
2. Generate the PO to the vendor
3. Generate a label with the vendor's address as origin
4. Verify label format works for the vendor
5. Process a test tracking update

### Success Criteria

- Labels generated for 100% of drop-ship orders
- Vendor can print and use the label
- Tracking numbers returned within 24 hours of shipping

---

## Scenario 6: Returns Processing

### Business Context

A retailer processes 50-100 returns per day. Returned items need a return shipping label, often with a different carrier than the outbound shipment.

### Customer Objective

- Generate return labels from Return Authorizations
- Use return-specific carrier agreements (lower rates for returns)
- Track returned items from customer back to warehouse

### Recommended Configuration

| Setting | Value |
|---|---|
| Return labels | Generated from Return Authorization |
| Return carrier | Configured separately from outbound |
| Tracking | Return tracking linked to RMA |
| Label cost | Charged to returns expense, not COGS |

### Business Workflow

```
Return Authorization created
  → Pacejet generates return label
  → Label sent to customer (email or portal)
  → Customer ships item back
  → Tracking updated in RMA
  → Item received, inspected, restocked or disposed
```

### Common Implementation Mistakes

| Mistake | Impact |
|---|---|
| Return label uses outbound carrier rates | Higher cost than necessary for returns |
| Return label not linked to RMA | Cannot track return status |
| Label cost charged incorrectly | Expense recorded in wrong account |
| Customer doesn't receive label | Return is delayed or abandoned |

### Validation Steps

1. Create a test Return Authorization
2. Generate a return label
3. Verify the return label uses return-specific rates
4. Verify the label is linked to the RMA
5. Send the label and verify delivery

### Success Criteria

- Return labels generated for 100% of RMAs
- Return-specific rates applied
- Return tracking visible in the RMA record

## Related Articles

- [Core Shipping Workflow](shipping-workflow.md)
- [Rate Shopping](rate-shopping.md)
- [Label Generation](label-generation.md)
- [Carrier Integrations](carrier-integrations.md)
- [Pacejet Troubleshooting Case Library](troubleshooting-case-library.md)
- [Pacejet Support Intelligence](../../knowledge-engine/support-intelligence/pacejet-support.md)

## Oracle References

- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)