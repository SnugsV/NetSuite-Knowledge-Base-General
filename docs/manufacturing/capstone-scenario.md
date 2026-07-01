---
title: Capstone Manufacturing Scenario
module: Manufacturing
difficulty: Advanced
estimated_time: 20 minutes
status: Draft
last_reviewed:
---

# Capstone Manufacturing Scenario

## Quick Summary

This capstone scenario applies concepts from Inventory, Purchasing, Sales, and Manufacturing to a realistic production situation. Read the scenario and work through the decisions.

## Estimated Time

20 minutes

## Scenario: Summit Furniture Company

Summit Furniture manufactures custom office chairs. They have recently won a contract to supply 500 ergonomic chairs to a corporate client. This is their largest order ever.

## Company Profile

| Detail | Value |
|---|---|
| Product | Summit Ergo Chair (Assembly Item: CHR-ERG-100) |
| Order quantity | 500 units |
| Delivery deadline | 30 days |
| Production location | Chicago Main Warehouse |
| BOM complexity | 12 components (2 sub-assemblies) |
| Current capacity | 30 chairs per day (1 shift) |

## BOM Summary (per chair)

| Component | Type | Quantity | Cost |
|---|---|---|---|
| Frame Assembly (sub-assembly) | Assembly Item | 1 | $45.00 |
| Seat Cushion | Inventory Item | 1 | $18.00 |
| Fabric (2m per chair) | Inventory Item | 2 meters | $8.00/m |
| Armrests (2 per chair) | Inventory Item | 2 | $5.00 each |
| Pneumatic Cylinder | Inventory Item | 1 | $22.00 |
| Base (5-star) | Inventory Item | 1 | $15.00 |
| Casters (5 per chair) | Inventory Item | 5 | $2.00 each |
| Hardware Kit | Inventory Item | 1 | $6.00 |
| Packaging | Inventory Item | 1 | $4.00 |

## Current Inventory Status

| Component | On Hand | Available | Reorder Point |
|---|---|---|---|
| Frame Assembly | 50 | 30 | 100 |
| Seat Cushion | 200 | 180 | 50 |
| Fabric | 300m | 280m | 200m |
| Armrests | 400 | 380 | 100 |
| Cylinder | 80 | 60 | 50 |
| Base | 60 | 40 | 50 |
| Casters | 2,000 | 1,900 | 500 |
| Hardware Kit | 300 | 290 | 100 |
| Packaging | 150 | 130 | 50 |

## Tasks

### Task 1: BOM Check

Verify the BOM for the Ergo Chair. Calculate the total material cost per chair based on the component costs.

**Question**: What is the total material cost per chair?

### Task 2: Component Availability

For each component, determine whether current available inventory is sufficient for 500 chairs. Identify which components are short and how many units need to be ordered.

**Question**: Which components require purchasing? How many of each?

### Task 3: Production Planning

The factory runs one shift (8 hours) at 30 chairs per day. Determine whether the order can be completed within 30 days.

**Questions**:
- At 30 chairs/day, how many production days are needed for 500 chairs?
- Can the order be completed within 30 days?
- If not, what options exist?

### Task 4: Work Order Setup

The production manager decides to split the order into three work orders:
- WO-001: 200 chairs (start immediately)
- WO-002: 200 chairs (start in 7 days)
- WO-003: 100 chairs (start in 14 days)

For each work order, calculate:
- Component requirements (for WO-001)
- Whether components need to be ordered before the work order can start

### Task 5: Manufacturing Cost

Assume the following additional costs:
- Direct labor: 40 min per chair at $24/hr
- Manufacturing overhead applied at 100% of direct labor cost

**Questions**:
- What is the labor cost per chair?
- What is the overhead cost per chair?
- What is the total manufacturing cost per chair?
- What is the total order cost?

### Task 6: Sales and Margin

The selling price per chair is $225.

**Questions**:
- What is the gross profit per chair?
- What is the gross margin percentage?
- If the customer negotiates a 10% discount, what is the revised margin?

### Task 7: Variance Analysis

After production, the actual results for WO-001 showed:
- Total fabric used: 430m (expected: 400m)
- Labor hours: 160 hours for 200 chairs (expected: 133 hours)

**Questions**:
- What is the material usage variance for fabric?
- What is the labor efficiency variance?
- What could have caused each variance?

## Answer Key

### Task 1: Material Cost per Chair
Frame Assembly: $45.00 + Seat Cushion: $18.00 + Fabric (2m × $8): $16.00 + Armrests (2 × $5): $10.00 + Cylinder: $22.00 + Base: $15.00 + Casters (5 × $2): $10.00 + Hardware: $6.00 + Packaging: $4.00 = **$146.00**

### Task 2: Component Shortages
Components needing purchasing:
- Frame Assembly: Need 500, have 30. Order **470**.
- Fabric: Need 1,000m, have 280m. Order **720m**.
- Cylinder: Need 500, have 60. Order **440**.
- Base: Need 500, have 40. Order **460**.
- Armrests: Need 1,000, have 380. Order **620**.
- Packaging: Need 500, have 130. Order **370**.

### Task 3: Production Timeline
500 chairs / 30 chairs per day = **16.7 days** (17 production days). With 30 calendar days available, the order can be completed with 13 days to spare.

### Task 5: Manufacturing Cost
Labor: 40 min = 0.667 hrs × $24 = **$16.00**. Overhead: 100% × $16 = **$16.00**. Total per chair: $146 + $16 + $16 = **$178.00**. Total order: 500 × $178 = **$89,000**.

### Task 6: Margin
Gross profit: $225 - $178 = **$47**. Margin: 47/225 = **20.9%**. With 10% discount ($202.50): $202.50 - $178 = $24.50, margin = **12.1%**.

### Task 7: Variances
Fabric: (430 - 400) × $8 = **$240 unfavorable** (30m excess). Labor: (160 - 133.3) × $24 = **$640 unfavorable** (26.7 excess hours).

## What You Learned

This scenario demonstrates how manufacturing connects to every part of the ERP. You used BOMs, inventory management, purchasing, work orders, costing, and sales concepts together — just as they interact in a real manufacturing operation.

## Related Articles

- [Bills of Materials](bills-of-materials.md)
- [Work Orders](work-orders.md)
- [Manufacturing Costing](manufacturing-costing.md)
- [Manufacturing Best Practices](manufacturing-best-practices.md)
- [Inventory Concepts](../inventory/inventory-concepts.md)
- [Purchasing: Purchase Orders](../purchasing/purchase-orders.md)
- [Sales: Sales Orders](../sales/sales-orders.md)

## Oracle References

- [Oracle NetSuite Help Center: Manufacturing](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)