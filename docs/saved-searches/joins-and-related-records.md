---
title: Joins and Related Records
module: Saved Searches
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Joins and Related Records

## Quick Summary

Joins allow a Saved Search to access data from related records — showing customer information in a transaction search, item details in a sales order search, or employee data in a support case search. Joins turn flat searches into cross-record queries.

## Difficulty

Advanced

## Estimated Time

20 minutes

## Overview

Every record in NetSuite is connected to other records. A sales order has a customer, items, a sales rep, a shipping address, and fulfillment records. A customer record has sales history, payment terms, and a sales rep.

Without joins, you can only display fields from the primary record type. With joins, you can display fields from any related record.

## How Joins Work

A join connects the primary search type to a related record type. When you add a join, all fields from the related record become available as result columns and criteria.

Common joins:

| Search Type | Available Joins |
|---|---|
| **Transaction** | Customer, Item, Created By, Department, Class, Location, Terms |
| **Customer** | Sales Rep, Partner, Terms, Currency |
| **Item** | Vendor, Department, Class, Location |
| **Employee** | Supervisor, Department, Role |

## Adding a Join

1. In the **Results** subtab, click **Add**
2. In the field picker, select the joine field (e.g., **Customer...** )
3. Expand the join to see fields from the related record
4. Select the field (e.g., **Customer... > Email**)

The joined field appears as a column in your results.

## Join Types

### Standard Joins

Standard joins follow the primary relationships defined in the record structure:

- **Customer** from a transaction → Customer fields (name, email, terms)
- **Item** from a transaction → Item fields (description, category, cost)
- **Created By** from any record → Employee fields (name, email)
- **Sales Rep** from a customer → Employee fields (name, email)

### Custom Joins

Custom joins link through custom fields or less common relationships. For example, a custom field on a sales order that links to a project record allows a join from the sales order to the project.

Custom joins must be configured in the search type definition or through custom record relationships.

## Joins in Criteria

Joins are not just for results — you can also filter by joined fields in the Criteria tab.

**Example**: Find sales orders where the customer's sales rep has changed recently.

```
Search Type: Transaction
Criteria:
  Type = Sales Order
  Customer : Sales Rep = is (John Smith)
  Date Created = within (This Month)
```

## Joining to Multiple Related Records

You can join to multiple related records in a single search. For example, a transaction search might join to:

- **Customer** for billing information
- **Item** for product details
- **Created By** for the employee who entered the order
- **Ship To Address** for shipping information

Each join is independent and adds its own fields to the available columns.

## Performance and Joins

Joins increase search complexity and can affect performance:

- Each join adds processing time
- Joining to tables with many records (like Customer) is generally fast
- Joining to transaction-level records (like Item Fulfillment from Sales Order) can be slower
- Multiple joins compound the performance impact

**Best practice**: Only join to the records you actually need. Avoid joining "just in case."

## Common Join Patterns

### Transaction with Customer Details

```
Search Type: Transaction
Joins: Customer → Name, Email, Terms, Credit Limit
Fields: Document Number, Date, Customer Name, Customer Email, Total
```

### Customer with Sales Performance

```
Search Type: Customer
Joins: Sales Rep → Name, Email
Fields: Customer Name, Sales Rep Name, Total Sales (summary)
```

### Item with Vendor Information

```
Search Type: Item
Join: Vendor → Name, Lead Time
Fields: Item Name, Vendor Name, Lead Time, Quantity On Hand
Criteria: Item Type = Inventory
```

## Common Mistakes

- **Joining unnecessarily**: If you only need the customer name (which is already available as a standard field), you do not need a join.
- **Using the wrong join field**: "Customer" and "Customer... Email" are different — the first is the customer name; the second is the email from the customer record.
- **Joining too many tables**: Each join adds complexity. Start with one join and test.
- **Joining in criteria without understanding the relationship**: A join filter on criteria can exclude records that have no related record.
- **Expecting transaction-level joins on non-transaction searches**: Customer searches cannot join to sales orders without a specific relationship.

## Best Practices

- Add joins incrementally — test the search after each join.
- Only join to records you need for results or criteria.
- Use joined fields in criteria to filter by related record attributes.
- Consider whether a different search type would eliminate the need for a join.
- Test search performance with and without joins to understand the impact.

## Related Articles

- [Criteria](criteria.md)
- [Results](results.md)
- [Formulas](formulas.md)
- [Summary Types](summary-types.md)
- [Performance Best Practices](performance-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Joins](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Records Browser](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)