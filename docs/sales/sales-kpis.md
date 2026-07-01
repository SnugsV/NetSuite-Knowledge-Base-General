---
title: Sales KPIs
module: Sales
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Sales KPIs

## Quick Summary

Sales KPIs measure the health of the Order-to-Cash process — order velocity, fulfillment speed, revenue trends, customer behavior, and collection efficiency. Regular monitoring identifies opportunities for improvement and flags emerging problems.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Key Performance Indicators

### Revenue and Growth

| KPI | Calculation | Target |
|---|---|---|
| **Revenue (Net Sales)** | Total sales minus returns and discounts | Track trend |
| **Revenue by Product** | Sales grouped by item category | Identifies top performers |
| **Revenue by Customer** | Sales grouped by customer | Identifies key accounts |
| **Revenue by Region** | Sales grouped by territory | Geographic performance |
| **Year-over-Year Growth** | (Current period / Prior period) - 1 | Positive |

### Order Metrics

| KPI | Calculation | Target |
|---|---|---|
| **Order Volume** | Number of sales orders per period | Track trend |
| **Average Order Value (AOV)** | Total revenue / Number of orders | Increasing |
| **Order Line Items** | Average items per order | Benchmark dependent |
| **Quote-to-Order Conversion** | % of quotes converted to orders | > 30% |

### Fulfillment Metrics

| KPI | Calculation | Target |
|---|---|---|
| **On-Time Shipment Rate** | % of orders shipped by promised date | > 98% |
| **Order Cycle Time** | Average time from order to shipment | < 24 hours |
| **Perfect Order Rate** | % of orders shipped complete and on time | > 95% |
| **Backorder Rate** | % of order lines backordered | < 5% |
| **Fill Rate** | % of demand fulfilled from stock | > 95% |

### Customer Metrics

| KPI | Calculation | Target |
|---|---|---|
| **Customer Acquisition Cost** | Sales expense / New customers | Decreasing |
| **Customer Lifetime Value** | Average revenue per customer over relationship | Increasing |
| **Repeat Purchase Rate** | % of customers ordering again in 12 months | > 40% |
| **Return Rate** | % of revenue returned | < 5% |

### AR and Collections

| KPI | Calculation | Target |
|---|---|---|
| **Days Sales Outstanding (DSO)** | (AR / Revenue) × Days | Decreasing |
| **AR Over 90 Days** | % of AR past 90 days | < 5% |
| **Cash Collection Rate** | Cash collected / Invoiced amount | > 95% |

## Building Sales Dashboards

### Saved Searches for Sales

| Search | Criteria |
|---|---|
| **Orders Pending Fulfillment** | Status = Approved, not yet fulfilled |
| **Orders Past Ship Date** | Ship date < today, not fulfilled |
| **Open Orders by Customer** | Group by customer, count orders |
| **Sales by Sales Rep (Summary)** | Group by rep, sum totals |
| **Customer Returns (Monthly)** | RA count and value by month |
| **Top Customers (Revenue)** | Customer group, revenue descending |

### Dashboard Portlets

| Portlet | Source |
|---|---|
| **Revenue This Month** | Summary search: Sum of total |
| **Open Orders** | Count of orders not fulfilled |
| **Backorders** | Count of backordered lines |
| **Top Customers** | Top 10 by revenue |
| **Order Fulfillment Rate** | % shipped within SLA |

## Business Example

A sales director reviews dashboards weekly:

**Weekly KPI Review**:
- Revenue this month: $450K (on track for $2M target)
- Open orders: 85 (steady)
- Backorder rate: 4.2% (target < 5% — acceptable)
- On-time shipment: 96% (target > 98% — below)
- Orders past ship date: 12 (investigate)
- DSO: 42 days (target < 45 — acceptable)

**Actions**:
- Investigate delayed shipments — two orders held for credit check
- Follow up on 12 past-due orders with fulfillment manager
- Monitor DSO reduction initiatives

## Common Mistakes

- **Vanity metrics that do not drive action**: Total page views or email opens are less useful than order conversion and fill rate
- **No benchmarks**: KPIs without targets or industry comparisons are data points, not measures
- **Manual data collection**: If KPIs require manual effort to compile, they will not be consistently tracked
- **Lagging indicators only**: Balance lagging KPIs (revenue) with leading KPIs (order volume, pipeline)
- **Not sharing KPI dashboards**: KPIs are most valuable when the team can see them and act on them

## Best Practices

- Define 5-7 core sales KPIs and track them weekly
- Set targets based on historical performance and business goals
- Use Saved Searches to automate data collection
- Build a sales dashboard with real-time KPI visibility
- Review KPI trends, not just point-in-time values
- Share KPI reports with sales, fulfillment, and finance teams
- Adjust targets as the business evolves

## Related Articles

- [What Is Order-to-Cash?](what-is-order-to-cash.md)
- [Sales Best Practices](sales-best-practices.md)
- [Customer Management](customer-management.md)
- [Purchasing: Procurement KPIs](../purchasing/procurement-kpis.md)
- [Saved Searches module](../saved-searches/README.md)

## Oracle References

- [Oracle NetSuite Help Center: Sales Reporting](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)