# Benchmark Catalog

## Purpose

The master catalog of all validation benchmarks. Each benchmark is a specific scenario that measures AI consultant behavior.

## Benchmark Naming Convention

`BENCHMARK-{CATEGORY}-{ID}: {Title}`

Categories: SS (Saved Search), SCR (SuiteScript), WF (Workflow), RPT (Reporting), TRBL (Troubleshooting), CFG (Configuration), INT (Integration)

## Saved Search Benchmarks

| ID | Title | Difficulty | Gold Standard |
|---|---|---|---|
| SS-001 | Inventory Below Reorder Point | Beginner | GOLD-SS-001 |
| SS-002 | Customers Inactive 180 Days | Intermediate | GOLD-SS-002 |
| SS-003 | Sales by Territory | Intermediate | GOLD-SS-003 |
| SS-004 | Open Purchase Orders Aged 30+ Days | Intermediate | GOLD-SS-004 |
| SS-005 | Items with Negative Inventory | Beginner | GOLD-SS-005 |
| SS-006 | Vendor Performance Summary | Advanced | GOLD-SS-006 |
| SS-007 | Sales Orders Pending Approval | Beginner | GOLD-SS-007 |
| SS-008 | Inventory Valuation by Location | Advanced | GOLD-SS-008 |

## Troubleshooting Benchmarks

| ID | Title | Difficulty | Gold Standard |
|---|---|---|---|
| TRBL-001 | Pacejet Labels Stopped Printing | Intermediate | GOLD-TRBL-001 |
| TRBL-002 | UPS Authentication Failure | Intermediate | GOLD-TRBL-002 |
| TRBL-003 | Inventory Commitment Issue | Intermediate | GOLD-TRBL-003 |
| TRBL-004 | Work Order Won't Complete | Intermediate | GOLD-TRBL-004 |
| TRBL-005 | Vendor Bill Approval Stuck | Beginner | GOLD-TRBL-005 |
| TRBL-006 | Period Close Blocked | Advanced | GOLD-TRBL-006 |
| TRBL-007 | Saved Search Returns Wrong Results | Beginner | GOLD-TRBL-007 |
| TRBL-008 | Negative On-Hand Quantities | Intermediate | GOLD-TRBL-008 |
| TRBL-009 | Sales Order on Credit Hold | Beginner | GOLD-TRBL-009 |
| TRBL-010 | Assembly Cost Variance | Advanced | GOLD-TRBL-010 |

## Workflow Benchmarks

| ID | Title | Difficulty |
|---|---|---|
| WF-001 | Purchase Order Approval Escalation | Intermediate |
| WF-002 | Customer Onboarding | Intermediate |
| WF-003 | Inventory Hold Notification | Intermediate |
| WF-004 | Sales Order Value Escalation | Intermediate |
| WF-005 | Manufacturing Approval Routing | Advanced |

## Reporting Benchmarks

| ID | Title | Difficulty |
|---|---|---|
| RPT-001 | Daily Sales KPI Dashboard | Intermediate |
| RPT-002 | Executive Summary Dashboard | Intermediate |
| RPT-003 | Monthly Financial Summary | Advanced |
| RPT-004 | Operational Inventory Report | Intermediate |
| RPT-005 | SuiteAnalytics Workbook for Ad-Hoc Analysis | Intermediate |

## Configuration Benchmarks

| ID | Title | Difficulty |
|---|---|---|
| CFG-001 | New User Setup with Role Assignment | Beginner |
| CFG-002 | Custom Field Configuration | Intermediate |
| CFG-003 | SuiteApprovals Workflow Setup | Intermediate |
| CFG-004 | Multi-Location Inventory Enablement | Advanced |

## Benchmark Selection Guide

Use this guide to select benchmarks for evaluation:

| Evaluation Goal | Benchmarks to Use |
|---|---|
| Basic saved search competence | SS-001, SS-005, SS-007 |
| Intermediate ERP reasoning | SS-002, SS-004, TRBL-005, TRBL-007 |
| Troubleshooting methodology | TRBL-001 through TRBL-004 |
| Advanced NetSuite knowledge | SS-008, TRBL-006, TRBL-010 |
| Cross-module reasoning | TRBL-003, TRBL-008, WF-004 |

## Adding Benchmarks

When adding a new capability to the platform, add a corresponding benchmark to this catalog.

| Requirement | Action |
|---|---|
| New AI Skill created | Add benchmark for the skill |
| New integration documented | Add troubleshooting benchmark |
| New ERP module completed | Add configuration and reporting benchmarks |
| New framework layer added | Add reasoning benchmark |

## Benchmark Status

| Status | Meaning |
|---|---|
| Available | Gold standard and evaluation criteria defined |
| In Progress | Scenario defined, gold standard pending |
| Planned | Category identified but not yet designed |

**Current status**: All benchmarks are "Planned" — gold standards must be created as benchmarks are activated.