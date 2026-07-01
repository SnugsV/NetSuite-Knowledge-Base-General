---
title: Saved Search Types
module: Saved Searches
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed:
---

# Saved Search Types

## Quick Summary

Saved Searches operate on different record types. The search type you choose determines which fields, joins, and criteria are available. Choosing the right search type is the most important decision when creating a saved search.

## Difficulty

Beginner

## Estimated Time

5 minutes

## Overview

When you create a Saved Search, the first thing you choose is the record type to search. This choice determines everything that follows — which fields you can filter on, which related records you can join, and what kind of results you can display.

The most common search types fall into a few broad categories.

## Transaction Searches

Transaction searches are the most commonly used type. They search transaction records — sales orders, purchase orders, invoices, credit memos, item fulfillments, inventory adjustments, and more.

**Use when**: You need to find, summarize, or monitor business transactions.

**Examples:**

- Open sales orders
- Invoices past due
- Purchase orders awaiting approval
- Items shipped today
- Returns processed this month

**Key consideration**: Transaction searches have a Main Line filter. When this is enabled, only the main transaction line is returned (summary-level data). When disabled, individual item lines are returned. This is one of the most common sources of confusion for new users.

## Item Searches

Item searches query the item record — products, services, kits, and assemblies your company buys, sells, or manufactures.

**Use when**: You need to analyze item master data or inventory status.

**Examples:**

- Items below reorder point
- Items with no sales in 90 days
- Items by category and location
- Items with incorrect pricing
- Inactive items

## Customer Searches

Customer searches query customer records and their related data.

**Use when**: You need to analyze your customer base.

**Examples:**

- Customers with overdue balances
- Customers by territory
- Customers with no activity in 6 months
- Top customers by revenue
- Customers missing key information

## Vendor Searches

Vendor searches work like customer searches but for vendor records.

**Use when**: You need to analyze vendor performance or purchasing patterns.

**Examples:**

- Vendors by spend category
- Vendors with open purchase orders
- Vendors with quality issues
- Preferred vendor list

## Employee Searches

Employee searches query employee records and related information.

**Use when**: You need HR or operational data about employees.

**Examples:**

- Employees in specific departments
- Employees with pending approvals
- Employees by supervisor
- Employee training records

## Other Search Types

NetSuite supports dozens of additional search types, including:

| Search Type | Best For |
|---|---|
| **Contact** | People associated with customers and partners |
| **Partner** | Channel and referral relationships |
| **Lead** | Sales leads and prospects |
| **Opportunity** | Sales pipeline opportunities |
| **Support Case** | Customer support incidents |
| **Project Task** | Project and task management |
| **Calendar Event** | Meetings and events |
| **Custom Record** | Any custom record type created by your organization |

## Choosing the Right Type

The search type determines:

- Which **criteria fields** are available
- Which **result columns** can be displayed
- Which **joins** to related records are possible
- Which **summary types** are valid

A common mistake is choosing the wrong search type and then trying to work around its limitations. For example, if you want to find "customers who ordered more than $10,000 last month," you might be tempted to use a Customer search. But to filter by transaction totals, you actually need a Transaction search grouped by customer.

**Rule of thumb**: Choose the search type that corresponds to the records you want in your results, not the context you're thinking about.

## Related Articles

- [What Is a Saved Search?](what-is-a-saved-search.md)
- [Building Your First Search](building-your-first-search.md)
- [Criteria](criteria.md)
- [Joins and Related Records](joins-and-related-records.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Types](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)