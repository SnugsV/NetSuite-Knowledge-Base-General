# Knowledge Domains

This document defines the public knowledge domain taxonomy for the NetSuite Knowledge Base General repository.

Knowledge domains are the top-level subject areas used to organize articles, guide contributors, support AI retrieval, and prevent private company-specific material from entering the public repository.

## Purpose

Knowledge domains help maintainers and AI assistants answer four questions:

1. Where does this article belong?
2. Which related concepts should it connect to?
3. What level of detail is appropriate for a public repository?
4. Which private details must be excluded?

This document should be used with:

- [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md)
- [ARTICLE_CLASSIFICATION.md](ARTICLE_CLASSIFICATION.md)
- [KNOWLEDGE_LEVELS.md](KNOWLEDGE_LEVELS.md)
- [AI_RETRIEVAL_MODEL.md](AI_RETRIEVAL_MODEL.md)

Some of those documents may be created in later maintenance passes. Until then, this file is the primary taxonomy reference.

## Core Principle

A domain describes a reusable public concept, not a private implementation.

For example:

- Public-safe: how item records support inventory management.
- Not public-safe: how a specific private company names, configures, prices, manufactures, or routes its items.

## Domain Summary

| Domain | Purpose | Typical Audience |
|---|---|---|
| NetSuite Core Platform | Foundational NetSuite concepts, records, navigation, roles, permissions, forms, and account structure. | Beginners, administrators, consultants, AI assistants |
| Administration & Security | Setup, configuration, access control, authentication, auditability, release management, and governance. | Administrators, implementation teams, auditors |
| Financial Management | Accounting flow, posting behavior, periods, accounts, transactions, reconciliation, and financial controls. | Finance teams, administrators, consultants |
| CRM & Customer Lifecycle | Leads, prospects, customers, opportunities, cases, contacts, and customer-facing process flow. | Sales teams, support teams, consultants |
| Order Management | Quotes, sales orders, fulfillment, invoicing, returns, billing, and order-to-cash process flow. | Sales operations, warehouse teams, finance teams |
| Procurement | Vendors, purchase orders, receiving, vendor bills, approvals, and procure-to-pay process flow. | Purchasing teams, operations teams, finance teams |
| Inventory Management | Items, locations, bins, lots, serials, transfers, adjustments, replenishment, and valuation concepts. | Inventory teams, warehouse teams, operations leaders |
| Manufacturing | Assemblies, components, work orders, builds, routings, costing, production planning, and plan-to-produce flow. | Manufacturing teams, operations teams, consultants |
| Warehouse & Fulfillment | Picking, packing, shipping, WMS concepts, carriers, labels, shipment tracking, and fulfillment exceptions. | Warehouse teams, shipping teams, operations teams |
| Reporting & Analytics | Saved searches, reports, SuiteAnalytics, KPIs, dashboards, metrics, and operational visibility. | Analysts, administrators, managers, AI assistants |
| Automation & Workflow | Workflows, approvals, SuiteScript concepts, scheduled logic, automation selection, and automation tradeoffs. | Administrators, developers, solution architects |
| SuiteCloud Development | SuiteScript, SuiteTalk, REST, SOAP, SDF, custom records, custom fields, and technical extensibility concepts. | Developers, technical consultants, AI assistants |
| Integrations & Ecosystem | External systems, APIs, middleware, EDI, tax automation, shipping tools, ownership, and error handling. | Integration teams, consultants, developers |
| Troubleshooting & Support Intelligence | Diagnostic reasoning, issue classification, root cause analysis, evidence gathering, and support workflows. | Support teams, consultants, AI assistants |
| Implementation & Solution Architecture | Discovery, design tradeoffs, module selection, phased rollout, change management, and solution governance. | Consultants, project teams, business leaders |
| AI & Knowledge Engineering | AI-ready documentation, retrieval patterns, knowledge graphs, reasoning frameworks, validation, and benchmark models. | Maintainers, AI builders, enterprise knowledge teams |
| Governance & Public Safety | Repository standards, licensing, contribution rules, public/private boundaries, and review expectations. | Maintainers, contributors, AI assistants |

## Domain Guidelines

### NetSuite Core Platform

Use this domain for foundational NetSuite concepts that apply broadly across modules.

Typical topics:

- Records and transactions
- Lists and forms
- Centers, roles, and permissions
- Navigation and global search
- Dashboards and personalization
- Subsidiaries, locations, departments, and classes
- Standard platform terminology

AI retrieval notes:

- Use this domain when a user asks what something is, where it fits, or how NetSuite is generally structured.
- Link outward to specific process domains when the topic becomes operational.

Public-safety notes:

- Do not publish private role names, account configuration, custom centers, internal forms, or screenshots.

### Administration & Security

Use this domain for account setup, access control, governance, and system administration.

Typical topics:

- Company setup and preferences
- Enabled features
- Users, roles, and permissions
- Authentication and SSO
- Two-factor authentication
- System notes and audit trail
- Sandbox and release preview
- Security best practices

AI retrieval notes:

- Use this domain when the question involves setup, access, configuration, risk, auditability, or governance.
- Connect to SuiteCloud Development when configuration becomes customization.

Public-safety notes:

- Keep examples generic. Do not include private permission matrices, internal access rules, or account-specific controls.

### Financial Management

Use this domain for accounting, transaction impact, controls, and financial process flow.

Typical topics:

- Chart of accounts concepts
- Posting periods
- General ledger impact
- Invoices, vendor bills, credits, payments, and journals
- Reconciliation
- Financial reporting concepts
- Record-to-report flow

AI retrieval notes:

- Use this domain when the question involves posting behavior, accounting impact, financial controls, or reconciliation.
- Cross-link to Reporting & Analytics for visibility and metrics.

Public-safety notes:

- Do not publish private account numbers, margin logic, pricing models, cost structures, financial reports, or close procedures.

### CRM & Customer Lifecycle

Use this domain for customer-facing records and lifecycle concepts.

Typical topics:

- Leads, prospects, and customers
- Contacts
- Opportunities and estimates
- Cases and support records
- Customer communication history
- Customer lifecycle management

AI retrieval notes:

- Use this domain when the question centers on customers, sales pipeline, support process, or customer records.
- Cross-link to Order Management when a customer record becomes a transaction flow.

Public-safety notes:

- Do not include real customer names, customer-specific terms, account assignments, or internal sales procedures.

### Order Management

Use this domain for order-to-cash and sales transaction flow.

Typical topics:

- Estimates and sales orders
- Fulfillment and invoicing
- Customer deposits and payments
- Returns and credits
- Backorders and allocations
- Order status flow
- Order-to-cash process design

AI retrieval notes:

- Use this domain when a user asks how sales transactions move through NetSuite.
- Connect to Inventory Management, Warehouse & Fulfillment, Financial Management, and Integrations & Ecosystem.

Public-safety notes:

- Do not publish private order rules, approval thresholds, customer routing, pricing logic, or fulfillment exceptions tied to a specific organization.

### Procurement

Use this domain for procure-to-pay and vendor transaction flow.

Typical topics:

- Vendors
- Purchase requests and purchase orders
- Receiving
- Vendor bills and payments
- Purchasing approvals
- Landed cost concepts
- Procure-to-pay process design

AI retrieval notes:

- Use this domain when the question involves buying, receiving, vendor billing, or procurement controls.
- Connect to Inventory Management and Financial Management.

Public-safety notes:

- Do not include real vendor names, private vendor terms, negotiated costs, item sourcing rules, or approval policies from a private organization.

### Inventory Management

Use this domain for item master concepts and stock movement.

Typical topics:

- Item records and item types
- Locations and warehouses
- Inventory adjustments and transfers
- Bin management
- Lot and serial tracking
- Replenishment concepts
- Inventory valuation
- Cycle counts

AI retrieval notes:

- Use this domain when a user asks about quantity, movement, valuation, stock visibility, or item setup.
- Connect to Order Management, Procurement, Manufacturing, and Warehouse & Fulfillment.

Public-safety notes:

- Do not publish internal item numbers, private SKU strategy, cost rules, manufacturing logic, or warehouse-specific procedures.

### Manufacturing

Use this domain for production, assemblies, components, and plan-to-produce concepts.

Typical topics:

- Assembly items
- Bills of materials
- Work orders
- Builds and completions
- Routings and work centers
- Component consumption
- Manufacturing costing
- Production planning

AI retrieval notes:

- Use this domain when the question involves making, assembling, planning, consuming components, or production costing.
- Connect to Inventory Management and Financial Management.

Public-safety notes:

- Do not publish private manufacturing logic, routings, product recipes, BOMs, labor standards, production rules, or capacity assumptions.

### Warehouse & Fulfillment

Use this domain for warehouse execution and shipping flow.

Typical topics:

- Picking, packing, and shipping
- Fulfillment records
- WMS concepts
- Carrier services
- Label generation
- Shipment tracking
- Shipping exceptions
- Rate shopping concepts

AI retrieval notes:

- Use this domain when the question involves physical movement, carrier interaction, warehouse execution, or fulfillment exceptions.
- Connect to Order Management, Inventory Management, and Integrations & Ecosystem.

Public-safety notes:

- Do not include private warehouse layouts, pick paths, carrier account details, shipping rules, or internal operating procedures.

### Reporting & Analytics

Use this domain for visibility, metrics, and analysis.

Typical topics:

- Saved searches
- Reports
- SuiteAnalytics workbooks
- KPIs and dashboards
- Search formulas
- Summary reporting
- Operational and financial metrics

AI retrieval notes:

- Use this domain when the user asks how to see, measure, report, monitor, compare, or export information.
- Cross-link to the business domain being reported on.

Public-safety notes:

- Do not publish internal saved search IDs, private formulas tied to business strategy, proprietary KPIs, dashboards, or screenshots.

### Automation & Workflow

Use this domain for choosing and explaining automation patterns.

Typical topics:

- Workflows
- Approvals
- SuiteScript selection
- Scheduled automation
- Notifications and reminders
- Automation tradeoffs
- Error prevention and controls

AI retrieval notes:

- Use this domain when the user asks whether a process should be manual, workflow-driven, scripted, integrated, or governed through configuration.
- Connect to SuiteCloud Development for technical implementation details.

Public-safety notes:

- Do not publish private workflow IDs, script IDs, trigger rules, approval thresholds, or internal exception handling procedures.

### SuiteCloud Development

Use this domain for technical extensibility and development concepts.

Typical topics:

- SuiteScript concepts
- SuiteTalk REST and SOAP concepts
- SuiteCloud Development Framework
- Custom records and fields
- Script types
- Governance and deployment concepts
- API authentication patterns

AI retrieval notes:

- Use this domain when a question requires technical customization, API usage, scripting, deployment, or developer tradeoffs.
- Connect back to business domains so technical guidance remains tied to business outcomes.

Public-safety notes:

- Do not publish private source code, script IDs, custom field IDs, account URLs, tokens, credentials, or internal integration mappings.

### Integrations & Ecosystem

Use this domain for system-to-system communication and third-party platforms.

Typical topics:

- Integration architecture
- REST and SOAP integration concepts
- Middleware concepts
- External IDs and system-of-record decisions
- EDI concepts
- Tax automation concepts
- Shipping platform concepts
- Error handling and reconciliation

AI retrieval notes:

- Use this domain when a question involves multiple systems, data ownership, mapping, synchronization, retries, or external platforms.
- Cross-link to the relevant operational domain and SuiteCloud Development.

Public-safety notes:

- Keep third-party examples generic. Do not include private mappings, credentials, endpoint details, partner-specific requirements, or customer-specific integration logic.

### Troubleshooting & Support Intelligence

Use this domain for diagnosing and resolving issues.

Typical topics:

- Issue intake
- Evidence gathering
- Error classification
- Root cause analysis
- Reproduction steps
- Escalation criteria
- Resolution documentation
- Common failure patterns

AI retrieval notes:

- Use this domain when a user asks why something happened, why a record failed, what to check next, or how to structure support investigation.
- Connect to the affected business or technical domain.

Public-safety notes:

- Do not publish private support tickets, screenshots, customer data, transaction IDs, log exports, or account-specific errors unless fully anonymized and generalized.

### Implementation & Solution Architecture

Use this domain for designing solutions, not just explaining features.

Typical topics:

- Discovery questions
- Capability selection
- Build vs configure vs integrate decisions
- Phased rollout planning
- Data migration concepts
- Change management
- Acceptance criteria
- Risk management

AI retrieval notes:

- Use this domain when the user needs a recommendation, design pattern, or implementation plan.
- Connect to domain-specific articles for execution details.

Public-safety notes:

- Do not publish private project plans, internal priorities, company-specific architecture, stakeholder names, or rollout schedules.

### AI & Knowledge Engineering

Use this domain for making the repository more useful to AI systems.

Typical topics:

- AI-ready Markdown
- Retrieval-aware structure
- Knowledge graph relationships
- Article metadata
- Reasoning frameworks
- Validation and benchmark models
- Prompt and agent patterns
- Knowledge lifecycle management

AI retrieval notes:

- Use this domain when the article helps AI assistants retrieve, classify, reason, validate, or explain NetSuite knowledge.
- Connect to all other domains as the organizing layer.

Public-safety notes:

- Do not publish private prompts that reveal company-specific operating logic, internal data models, or proprietary workflows.

### Governance & Public Safety

Use this domain for standards that protect repository quality and public safety.

Typical topics:

- Contribution rules
- Review checklists
- Licensing
- Public/private content boundaries
- Naming conventions
- Repository maintenance
- Quality scoring
- Deprecation rules

AI retrieval notes:

- Use this domain when determining whether content is allowed, where it belongs, or how it should be maintained.
- Always connect public-safety decisions to `PUBLIC_SAFETY_RULES.md`.

Public-safety notes:

- This domain should be strict. When in doubt, keep private details out of the public repository.

## Cross-Domain Relationships

Many articles should belong to one primary domain and several related domains.

| Primary Domain | Common Related Domains |
|---|---|
| NetSuite Core Platform | Administration & Security, Reporting & Analytics, SuiteCloud Development |
| Administration & Security | Governance & Public Safety, SuiteCloud Development, Troubleshooting & Support Intelligence |
| Financial Management | Reporting & Analytics, Order Management, Procurement, Inventory Management |
| CRM & Customer Lifecycle | Order Management, Reporting & Analytics, Troubleshooting & Support Intelligence |
| Order Management | Inventory Management, Warehouse & Fulfillment, Financial Management, Integrations & Ecosystem |
| Procurement | Inventory Management, Financial Management, Reporting & Analytics |
| Inventory Management | Procurement, Order Management, Manufacturing, Warehouse & Fulfillment |
| Manufacturing | Inventory Management, Financial Management, Reporting & Analytics |
| Warehouse & Fulfillment | Inventory Management, Order Management, Integrations & Ecosystem |
| Reporting & Analytics | Every operational and technical domain |
| Automation & Workflow | SuiteCloud Development, Implementation & Solution Architecture, Governance & Public Safety |
| SuiteCloud Development | Automation & Workflow, Integrations & Ecosystem, NetSuite Core Platform |
| Integrations & Ecosystem | SuiteCloud Development, Troubleshooting & Support Intelligence, Order Management, Procurement, Warehouse & Fulfillment |
| Troubleshooting & Support Intelligence | Every domain where operational or technical issues occur |
| Implementation & Solution Architecture | Every domain involved in design decisions |
| AI & Knowledge Engineering | Every domain that benefits from AI retrieval and reasoning |
| Governance & Public Safety | Every public repository domain |

## Article Domain Metadata

Future articles should include domain metadata when the repository adopts structured front matter.

Recommended fields:

```yaml
primary_domain: Reporting & Analytics
related_domains:
  - Financial Management
  - Inventory Management
knowledge_level: intermediate
article_type: guide
public_safety_review: required
```

Until formal metadata is adopted, maintainers should still classify each article mentally during review.

## Domain Assignment Rules

1. Choose one primary domain.
2. Add related domains only when they materially improve navigation or AI retrieval.
3. Prefer business-process domains over technical domains when the article explains why a process works.
4. Prefer technical domains when the article explains how to build, configure, script, or integrate.
5. Use Governance & Public Safety whenever the article defines repository rules or public/private boundaries.
6. Use AI & Knowledge Engineering when the article improves retrieval, reasoning, validation, or AI agent behavior.
7. Do not create company-specific domains in this public repository.

## Public-Safe Reminder

Do not include private company names, internal identifiers, screenshots, account-specific mappings, saved searches, custom field IDs, workflow IDs, script IDs, credentials, pricing logic, manufacturing logic, or internal procedures in public domain articles.

Use generic examples only.

Before publishing, ask:

> Would this help an outside party understand how a specific private organization operates?

If yes, do not publish it here.
