---
title: Real-World Business Examples
module: Saved Searches
difficulty: Intermediate
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Real-World Business Examples

## Quick Summary

This article contains case studies showing how real businesses use Saved Searches to solve operational problems. Each example describes the business problem, the Saved Search solution, configuration notes, and outcomes.

## Difficulty

Intermediate

## Estimated Time

20 minutes

## Case Study 1: Sales Pipeline Dashboard

### Business Problem

A sales director needs to see every open opportunity, its value, the sales rep responsible, and how long it has been in the pipeline. Every Monday, a summary is emailed to the management team.

### Solution

A Transaction Saved Search configured as follows:

```
Search Type: Opportunity
Criteria:
  Status = any of (In Progress, Proposal Sent, Negotiation)
  Close Date = within (Next 90 Days)
  Main Line = Yes

Results:
  Opportunity Name          → Group
  Sales Rep                → Group
  Amount                   → Sum
  Expected Close Date      → Maximum
  Days in Pipeline         → Formula: {today} - {createddate}
  Status                   → Group

Available Filters:
  Sales Rep
  Expected Close Date Range
  
Highlighting:
  Close Date < 14 days → Red background
  Amount > 50000      → Bold

Audience:
  Sales Manager, CEO roles

Schedule:
  Emailed every Monday at 8:00 AM
```

### Business Value

The sales director has a real-time view of the pipeline without logging into NetSuite. The weekly email keeps the management team informed without manual report preparation.

### Key Configuration Insights

- The Days in Pipeline formula uses `{today} - {createddate}` — relative, so it never needs updating
- Available Filters let individual sales managers focus on their team
- Highlighting flags urgent opportunities at a glance

---

## Case Study 2: Inventory Reorder Alert

### Business Problem

A warehouse manager needs to know which inventory items are below reorder point. The alert should run daily and be easily accessible from a dashboard.

### Solution

An Item Saved Search as a dashboard portlet:

```
Search Type: Item
Criteria:
  Item Type = Inventory
  Quantity On Hand < Reorder Point
  Inactive = No

Results:
  Item Name
  Item SKU
  Quantity On Hand
  Reorder Point
  Quantity to Reorder   → Formula: {reorderpoint} - NVL({quantityonhand},0)
  Location

Sort By: Quantity On Hand ascending

Available Filters:
  Location
  Department

Highlighting:
  Quantity On Hand = 0           → Red background
  Quantity On Hand < Reorder Point → Yellow background

Audience:
  Inventory Clerk, Warehouse Worker, Purchasing Manager roles

Dashboard:
  Added as a portlet on the Inventory center dashboard
```

### Business Value

The warehouse team sees low stock items immediately when they log in. The formula column tells them exactly how many to reorder, reducing manual stock checks.

### Key Configuration Insights

- `NVL({quantityonhand},0)` prevents null values for items that have never been stocked
- The search filters out inactive items to prevent noise
- Location filter lets regional warehouse managers focus on their location

---

## Case Study 3: Customer Aging and Collections

### Business Problem

An accounts receivable manager needs to track overdue invoices, prioritize collections, and see which customers need immediate attention.

### Solution

A Transaction Saved Search:

```
Search Type: Transaction
Criteria:
  Type = Invoice
  Status = any of (Open, Past Due)
  Main Line = Yes
  Date Created = on or before (30 days ago)

Results:
  Customer Name                 → Group
  Document Number
  Invoice Date
  Due Date
  Amount                        → Sum
  Days Overdue                  → Formula: {today} - {duedate}
  Aging Bucket                  → Formula: CASE WHEN {today} - {duedate} > 90 THEN '90+'
                                   WHEN {today} - {duedate} > 60 THEN '61-90'
                                   WHEN {today} - {duedate} > 30 THEN '31-60'
                                   ELSE 'Current' END
  Customer : Email              → Join to get customer email

Sort By: Days Overdue descending

Available Filters:
  Customer
  Aging Bucket
  Amount Minimum

Highlighting:
  Days Overdue > 90  → Red background, white text
  Days Overdue > 60  → Yellow background
  Days Overdue > 30  → Italic

Audience:
  Accountant, AR Clerk roles
```

### Business Value

The collections team prioritizes the oldest and largest invoices. The aging bucket formula provides clear categories for reporting. The customer email join enables quick follow-up.

### Key Configuration Insights

- The formula approach to aging buckets is reusable across many search types
- The date range filter prevents scanning all invoices — only the last 30 days are checked for overdue status
- The Amount Minimum filter lets collectors focus on high-value accounts

---

## Case Study 4: Vendor Performance Monitoring

### Business Problem

A purchasing manager needs to track vendor performance — on-time delivery rates, quality issues, and open purchase orders.

### Solution

Three Saved Searches working together:

**Search 1: Open Purchase Orders**

```
Search Type: Transaction
Criteria:
  Type = Purchase Order
  Status = Pending Receipt
  Main Line = Yes

Results:
  Document Number, Vendor Name, Order Date, Expected Date, Total
  Days Since Ordered → Formula: {today} - {trandate}

Sort: Expected Date ascending
```

**Search 2: Late Receipts**

```
Search Type: Transaction
Criteria:
  Type = Item Receipt
  Main Line = No
  Date Created = within (This Month)

Results:
  Vendor Name
  Item
  Quantity
  Expected Date (from Purchase Order join)
  Days Late → Formula: {createddate} - {custbody_expected_date}
```

### Business Value

The purchasing manager has visibility into what is on order, what is late, and which vendors are performing well.

### Key Configuration Insights

- Multiple searches focused on specific questions are easier to maintain than one complex search
- The Expected Date join provides forward-looking visibility
- The Days Late formula creates an objective performance metric

---

## Case Study 5: Manufacturing Exception Monitoring

### Business Problem

A production manager needs to know about manufacturing delays, material shortages, and bottleneck work centers.

### Solution

```
Search Type: Transaction (Build Order)
Criteria:
  Type = Build Order
  Status = any of (In Progress, Planned)
  Main Line = Yes

Results:
  Build Order Number
  Assembly Item
  Quantity
  Date Scheduled
  Date Completed (if closed)
  Status
  Work Center (via custom field join)

Highlighting:
  Date Scheduled < Today and Status ≠ Closed → Red (overdue build)
  Quantity Committed < Quantity → Yellow (material shortage)

Available Filters:
  Assembly Item
  Work Center
  Status
```

### Business Value

The production manager spots bottlenecks before they cause missed ship dates. The highlighting draws attention to overdue builds and material shortages.

---

## Case Study 6: Executive Dashboard KPIs

### Business Problem

An executive team needs a high-level view of business health — revenue, orders, shipments, and exceptions — without navigating through multiple reports.

### Solution

A series of summary saved searches as dashboard portlets:

**KPI Portlet 1: Revenue This Month**

```
Search Type: Transaction
Criteria:
  Type = Invoice
  Status = any of (Billed, Paid)
  Date Created = within (This Month)
  Main Line = Yes

Results:
  Sum of Total
```

**KPI Portlet 2: Open Orders**

```
Search Type: Transaction
Criteria:
  Type = Sales Order
  Status = any of (Pending Fulfillment, Pending Approval)
  Main Line = Yes

Results:
  Count of Document Number
```

**KPI Portlet 3: Shipments Today**

```
Search Type: Transaction
Criteria:
  Type = Item Fulfillment
  Date Created = is (Today)
  Main Line = Yes

Results:
  Count of Document Number
```

### Business Value

Executives see real-time KPIs on their dashboard without manual reporting. Each KPI is a single-number summary search that loads quickly.

### Key Configuration Insights

- Single-number summary searches are the fastest type — ideal for dashboard portlets
- Each KPI is a separate search, making it easy to add, remove, or modify

---

## Summary of Patterns

| Pattern | Search Type | Key Elements |
|---|---|---|
| Pipeline tracking | Opportunity | Group by rep, formula for days in stage |
| Low stock alerts | Item | Quantity vs. reorder point comparison |
| Aging analysis | Transaction | Days overdue formula, aging bucket CASE |
| Vendor monitoring | Transaction | Expected vs. actual date comparison |
| Manufacturing exceptions | Transaction (Build) | Overdue and material shortage flags |
| Executive KPIs | Transaction | Summary type for single-number output |

## Related Articles

- [Saved Search vs. Reports](saved-search-vs-reports.md)
- [Saved Search vs. SuiteAnalytics](saved-search-vs-suiteanalytics.md)
- [Performance Best Practices](performance-best-practices.md)
- [Common Mistakes](common-mistakes.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Search Examples](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)