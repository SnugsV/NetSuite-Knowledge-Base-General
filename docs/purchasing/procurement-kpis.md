---
title: Procurement KPIs
module: Purchasing
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Procurement KPIs

## Quick Summary

Procurement KPIs measure the effectiveness of the purchasing function — vendor performance, procurement cycle time, spend analysis, cost savings, and policy compliance. Regular KPI monitoring identifies improvement opportunities and supports strategic decision-making.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Key Performance Indicators

### Spend Analysis

| KPI | Calculation | Target |
|---|---|---|
| **Total Spend** | Sum of all PO amounts (period) | Track trend |
| **Spend by Category** | Total spend grouped by vendor category | Identifies concentration risk |
| **Spend by Department** | Total spend grouped by department | Budget vs. actual |
| **Maestro Spend** | % of spend with preferred vendors | > 80% |
| **Non-PO Spend** | Spend without a purchase order | < 5% |

### Procurement Efficiency

| KPI | Calculation | Target |
|---|---|---|
| **Requisition-to-PO Cycle Time** | Average time from requisition approval to PO creation | < 2 days |
| **PO-to-Receipt Cycle Time** | Average time from PO creation to receipt | Varies by vendor lead time |
| **PO Lines Processed per Buyer** | Number of PO lines per purchasing agent per day | Benchmark dependent |
| **Requisition Approval Time** | Average time from submission to approval | < 24 hours |
| **Emergency PO Percentage** | % of POs marked as emergency | < 5% |

### Vendor Performance

| KPI | Calculation | Target |
|---|---|---|
| **On-Time Delivery Rate** | % of receipts on or before expected date | > 95% |
| **Perfect Order Rate** | % of orders delivered on time, complete, undamaged | > 90% |
| **Quality Defect Rate** | % of receipts with quality issues | < 2% |
| **Invoice Accuracy** | % of invoices matching PO without errors | > 98% |
| **Vendor Lead Time Variance** | Actual vs. promised lead time | ± 2 days |
| **Active Vendor Count** | Number of vendors with PO activity | Manage concentration |

### Cost Savings

| KPI | Calculation | Target |
|---|---|---|
| **Cost Savings** | Reduction in unit price vs. previous period or baseline | As budgeted |
| **Cost Avoidance** | Price increases negotiated down or absorbed | As budgeted |
| **Early Payment Discount Captured** | % of available discounts taken | > 90% |
| **Inflation Impact** | Price increase percentage absorbed vs. passed on | Track trend |

### Compliance

| KPI | Calculation | Target |
|---|---|---|
| **PO Compliance** | % of spend covered by purchase orders | > 95% |
| **Approval Compliance** | % of POs following approval workflow | > 99% |
| **Three-Way Match Rate** | % of bills matching PO and receipt within tolerance | > 90% |
| **Vendor Master Accuracy** | % of vendor records with complete information | > 95% |

## Building KPI Dashboards in NetSuite

Procurement KPIs can be monitored using Saved Searches and dashboards:

### Saved Searches for Procurement

| Search | Criteria |
|---|---|
| **Open POs Overdue** | Expected date < today, status not fully received |
| **Pending Approvals** | Status = pending approval |
| **POs without Receipts (Aged)** | Created > 30 days, no receipts |
| **Bills without PO** | Bill type = Vendor Bill, no PO reference |
| **Vendor Spend by Period** | Summary type: Sum of Amount, Group by Vendor |
| **On-Time Delivery** | Receipt date vs. expected date comparison |

### Dashboard Portlets

| Portlet | Search |
|---|---|
| **Pending Approvals** | Count of POs awaiting approval |
| **Overdue Receipts** | POs past expected receipt date |
| **Top Vendors by Spend** | Vendor spend summary (current month) |
| **PO Compliance Rate** | % of spend with POs |
| **Open PO Value** | Total committed spend not yet received |

## Business Example

A procurement manager reviews KPIs monthly:

**Monthly KPI Review**:
- Total spend: $2.1M (within budget)
- Maestro spend: 82% (target >80% — on track)
- Non-PO spend: 3.2% (target <5% — acceptable)
- On-time delivery: 91% (target >95% — declined from 94% last month)
- Vendor quality: 1.8% defect rate (target <2% — acceptable)
- Emergency PO %: 7% (target <5% — above threshold, investigate)

**Actions taken**:
- Investigate on-time delivery decline — two vendors had shipping issues
- Reduce emergency POs by reviewing requisition lead times
- Maintain approved vendor spend target

## Common Mistakes

- **Tracking too many KPIs**: 5-7 meaningful KPIs are better than 20 that no one monitors
- **Not setting targets**: A KPI without a target is a data point, not a performance measure
- **Ignoring trend direction**: A single month's KPI is less useful than a 3-month trend
- **Manual KPI collection**: If collecting KPIs requires manual effort, they will not be consistently tracked
- **Not acting on KPI data**: Monitoring without action creates reports that no one reads

## Best Practices

- Define 5-7 core procurement KPIs and track them monthly
- Set targets for each KPI based on industry benchmarks or internal goals
- Use Saved Searches to automate KPI data collection
- Build a procurement dashboard for daily monitoring
- Review KPI trends quarterly, not just point-in-time values
- Share KPI reports with stakeholders in purchasing, finance, and operations
- Adjust targets as the business and procurement function mature

## Related Articles

- [What Is Procurement?](what-is-procurement.md)
- [Procurement Best Practices](procurement-best-practices.md)
- [Vendor Management](vendor-management.md)
- [Saved Searches module](../saved-searches/README.md)
- [Dashboards](../getting-started/dashboards.md)

## Oracle References

- [Oracle NetSuite Help Center: Procurement Reporting](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Saved Searches for Purchasing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)