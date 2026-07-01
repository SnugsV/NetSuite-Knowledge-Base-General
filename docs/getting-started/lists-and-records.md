---
title: Lists and Records
module: Getting Started
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Lists and Records

## Quick Summary

Records are the building blocks of NetSuite. A record is any data entry — a customer, an item, a sales order, or a purchase order. Lists are collections of records. Understanding records, record types, transactions, and how they connect is essential for working effectively in NetSuite.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

Everything in NetSuite is built on records. A **record** represents a single piece of data: a customer, an inventory item, a vendor, a sales order, an invoice. Records have **fields** that store specific information — a customer record has fields for name, address, phone number, terms, and currency.

Records are organized into **lists**, which are simply collections of records of the same type. A "Customers" list contains all customer records. An "Items" list contains all item records.

## Record Types

NetSuite has hundreds of record types. The ones you use depend on your role, but the most common are:

### Standard Records

| Record Type | Example Field | Used For |
|---|---|---|
| Customer | Name, email, terms, currency | Companies or individuals you sell to |
| Vendor | Name, address, tax ID | Companies you purchase from |
| Item | Name, SKU, cost, price | Products or services you buy, sell, or manufacture |
| Employee | Name, email, department | People who work for your company |
| Contact | Name, phone, email | People associated with customers, vendors, or partners |
| Partner | Name, commission rate | Channel partners and referral relationships |

### Transaction Records

Transactions are records that represent business events with financial or inventory impact:

| Transaction Type | Purpose |
|---|---|
| Sales Order | Customer order for products or services |
| Invoice | Request for payment after fulfillment |
| Purchase Order | Order placed with a vendor |
| Item Receipt | Confirmation that items were received from vendor |
| Inventory Transfer | Moving stock between locations |
| Inventory Adjustment | Correcting inventory quantities |
| Journal Entry | Manual accounting entry |

### Custom Records

Administrators and developers can create custom record types to store data not covered by standard records. Custom records can have custom fields, forms, scripts, and workflows applied to them.

## Fields and Field Types

Every record has fields. Fields store individual pieces of information. Common field types include:

| Field Type | Example |
|---|---|
| Text | Customer name |
| Date | Order date |
| Select (Dropdown) | Payment terms (Net 30, Net 60) |
| Checkbox | Taxable |
| Currency | Order total |
| Number | Quantity |
| Text Area (Long) | Shipping instructions |

When you see a field with a magnifying glass icon, it is a **link** to another record. For example, on a sales order, the "Customer" field links to the customer record. Clicking the icon opens the linked record.

## Transactions and Records

Transactions are special records because they create financial or inventory impact. Understanding how transactions connect to records is key to understanding NetSuite.

Example — A sales order transaction connects:

- The **customer** record (who is buying)
- **Item records** (what they are buying)
- The **employee** record (who entered the order)
- **Location** records (where it ships from)
- **Fulfillment** records (when it ships)
- **Invoice** records (when it is billed)

Each connection is a field on the transaction. This linked data is what makes NetSuite powerful — a report can show sales by customer, by item, by sales rep, or by location without manual data entry.

## Lists

Lists are accessed from the **Lists** menu. Common lists:

| List Menu Item | What It Shows |
|---|---|
| Lists > Relationships > Customers | All customer records |
| Lists > Employees > Employees | All employee records |
| Lists > Accounting > Items | All item records |
| Lists > Relationships > Vendors | All vendor records |

Lists can be filtered, sorted, and exported. You can also create saved searches based on any list.

## Record Numbers and IDs

Every record in NetSuite is assigned a unique identifier:

- **Internal ID**: A system-generated number (e.g., 12345). Used internally for reporting, scripting, and integrations. Not normally seen by end users.
- **Document Number/Name**: A user-facing identifier (e.g., "SO-12345" for a sales order, "CUST001" for a customer). Can be auto-generated or manually assigned.
- **Custom ID**: Some record types allow custom numbering schemes.

## Common Mistakes

- **Confusing records with transactions**: Transactions are records that create financial or inventory impact. Not all records are transactions.
- **Entering the same data in multiple places**: If a field is linked (e.g., a customer on a sales order), changing it on the transaction does not update the customer record, and vice versa.
- **Not using the link icons**: Clicking the magnifying glass next to a linked field opens the related record. This is faster than navigating through menus.
- **Assuming a field exists because it appears on one record type**: Each record type has its own set of fields.

## Best Practices

- Learn the record types relevant to your role. A sales rep needs customers and sales orders. A warehouse worker needs items and inventory transactions.
- Use the **Lists** menu to browse records. Use **Global Search** to find a specific record.
- When creating a transaction, double-check linked fields — especially the customer, item, and location.
- Use saved searches to find groups of records (e.g., "All customers in Chicago").
- Remember that custom fields and custom records may exist in your account that are not documented in standard guides.

## Related Articles

- [What Is NetSuite?](what-is-netsuite.md)
- [Navigation](navigation.md)
- [Global Search](global-search.md)
- [Glossary](glossary.md)

## Oracle References

- [Oracle NetSuite Help Center: Records](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)