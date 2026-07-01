# AI Support Intelligence Framework

This directory contains structured support intelligence for NetSuite ERP domains. Each document teaches an AI how to reason through customer problems rather than simply retrieve documentation.

## Purpose

Traditional documentation answers "what." This framework teaches the "why" and "how" of troubleshooting. It provides reusable reasoning patterns that any AI agent can follow to diagnose problems, gather information, and recommend solutions.

## How to Use This Framework

1. Classify the customer's problem into an ERP domain
2. Open the corresponding support intelligence document
3. Follow the reasoning pattern: gather information → identify causes → verify → recommend
4. Use the escalation criteria to determine when to involve a human expert

## Reasoning Framework

The core methodology is documented in [REASONING_FRAMEWORK.md](REASONING_FRAMEWORK.md). Every domain document follows this pattern with domain-specific content.

## Domain Documents

| Document | Domain | Key Topics |
|---|---|---|
| [Purchasing Support](purchasing-support.md) | Procure-to-Pay | PO issues, vendor bills, receiving, matching |
| [Sales Support](sales-support.md) | Order-to-Cash | SO issues, fulfillment, invoicing, returns |
| [Inventory Support](inventory-support.md) | Inventory Management | Item records, transfers, adjustments, costing |
| [Manufacturing Support](manufacturing-support.md) | Plan-to-Produce | Work orders, BOMs, WIP, backflushing |
| [Accounting Support](accounting-support.md) | Record-to-Report | GL, period close, revenue, COGS |
| [Saved Searches Support](saved-searches-support.md) | Reporting | Search results, formulas, performance |
| [Administration Support](administration-support.md) | System Admin | Permissions, features, authentication |
| [Integration Support](integration-support.md) | Cross-Module | Multi-module failures, data flow issues |

## Related Documents

- [MASTER_PROJECT_PROMPT.md](../MASTER_PROJECT_PROMPT.md)
- All completed ERP learning paths under `docs/`