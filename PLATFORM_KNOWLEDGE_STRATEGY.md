# Platform Knowledge Strategy

This document defines the long-term strategy for growing this repository into a public, AI-friendly knowledge engine for NetSuite and related business systems.

The repository is intended to contain broad, reusable platform knowledge. It must not identify, imply, name, or expose the internal organization that uses private overlays with this knowledge base.

## Core Principle

The public repository explains general platform behavior.

Private repositories explain internal company behavior.

The public repository should remain useful to the broader NetSuite, ERP, integration, shipping, tax, and EDI community without exposing any private operating model, company identity, customer relationships, pricing logic, internal workflows, screenshots, or account-specific configuration.

## Absolute Public-Safety Rule

Do not include the internal company name, initials, aliases, branding, or identifying details anywhere in the public repository.

This includes:

- README files
- documentation articles
- examples
- diagrams
- screenshots
- source-watch configuration
- automation logs
- issue templates
- pull request templates
- sample prompts
- AI instructions
- comments
- filenames
- branch names
- commit messages when practical

The public repository should never make it possible for a reader to identify the private organization that uses it as an internal knowledge foundation.

## Public Repository Scope

This repository may include general, public-safe knowledge about:

- NetSuite concepts
- ERP education
- NetSuite administration
- NetSuite records and transactions
- Saved searches and reporting
- Inventory, purchasing, sales, manufacturing, accounting, and CRM concepts
- SuiteScript, SuiteTalk, REST, and integration patterns
- Pacejet concepts and public documentation summaries
- SPS Commerce and EDI concepts
- Avalara and tax automation concepts
- Shipping, tax, and EDI integration patterns
- AI reasoning frameworks
- Troubleshooting methodology
- Implementation discovery questions
- General best practices
- Public-safe examples that do not reveal private operating details

## Private Repository Scope

Private repositories should contain any organization-specific information, including:

- Internal SOPs
- Internal role guides
- Private NetSuite screenshots
- Saved searches
- Custom fields
- Custom records
- Workflows
- SuiteScripts
- Bundle details
- Integrations and credentials
- Pricing logic
- Manufacturing logic
- Warehouse procedures
- Customer-specific requirements
- Vendor-specific requirements
- Trading partner mappings
- Tax setup details
- Carrier mappings
- Pacejet account configuration
- SPS Commerce document mappings
- Avalara configuration
- Internal AI prompts
- Internal escalation procedures

If publishing a detail would help a competitor, vendor, customer, or outside party understand how the private organization operates, it belongs in a private repository.

## Knowledge Architecture

The long-term architecture has two layers.

```text
Public Knowledge Engine
  |
  |-- NetSuite foundations
  |-- ERP process education
  |-- Integration concepts
  |-- Shipping concepts
  |-- Tax concepts
  |-- EDI concepts
  |-- AI reasoning frameworks

Private Knowledge Overlays
  |
  |-- Internal SOPs
  |-- Internal NetSuite setup
  |-- Internal integrations
  |-- Internal workflows and scripts
  |-- Internal prompts and GPT behavior
  |-- Internal screenshots and examples
```

An internal GPT can use both layers. The public repository provides general platform reasoning. Private repositories provide organization-specific operating context.

## Knowledge Domains

The public repository should grow across these domains.

### NetSuite Core

- Account structure
- Records
- Transactions
- Roles and permissions
- Forms
- Saved searches
- Reporting
- Workflows
- SuiteScript
- SuiteTalk and REST APIs
- Accounting behavior
- Inventory behavior
- Manufacturing behavior

### ERP Operations

- Order to cash
- Procure to pay
- Plan to produce
- Record to report
- Inventory movement
- Returns and credits
- Replenishment
- Warehouse and fulfillment concepts

### Shipping Intelligence

- Shipping workflows
- Carrier concepts
- Rate shopping concepts
- Label generation concepts
- Shipment status
- Shipping error patterns
- NetSuite-to-shipping-system integration patterns

### EDI and Trading Partner Intelligence

- EDI document types
- Trading partner concepts
- Purchase order ingestion
- Acknowledgments
- Advance ship notices
- Invoices
- Error handling
- Mapping concepts
- NetSuite-to-EDI integration patterns

### Tax Automation Intelligence

- Sales tax concepts
- Nexus concepts
- Taxability concepts
- Exemptions
- Address validation
- Tax calculation flows
- NetSuite-to-tax-engine integration patterns

### AI Reasoning and Troubleshooting

- Discovery frameworks
- Decision trees
- Troubleshooting checklists
- Root cause analysis
- Public vs private classification
- Solution selection frameworks
- Validation frameworks

## Supported Platform Families

The repository may include public-safe knowledge for these platform families:

| Platform Family | Public Repository Role |
|---|---|
| NetSuite | ERP foundation, records, transactions, reporting, automation, and integration concepts. |
| Pacejet | Public-safe shipping automation concepts and NetSuite shipping integration patterns. |
| SPS Commerce | Public-safe EDI and trading partner integration concepts. |
| Avalara | Public-safe tax automation and tax calculation integration concepts. |
| AI Systems | Reasoning, documentation, troubleshooting, and knowledge retrieval frameworks. |

Specific account setup, mappings, screenshots, credentials, partner rules, and company-specific procedures remain private.

## Internal GPT Usage Model

An internal GPT should use this public repository as the general reasoning layer.

For a user question, the GPT should:

1. Identify the platform or process involved.
2. Use the public repository to explain general platform behavior.
3. Use private repositories only when organization-specific setup is needed.
4. Clearly separate general platform guidance from private internal procedure.
5. Avoid leaking private content into public documentation.
6. Recommend whether new knowledge belongs in the public repository or a private overlay.

Example reasoning flow:

```text
Question
  |
  |-- Is this general NetSuite, shipping, tax, or EDI behavior?
  |       |
  |       |-- Yes -> use public repository knowledge
  |
  |-- Does the answer require internal setup, screenshots, saved searches, mappings, workflows, scripts, or SOPs?
          |
          |-- Yes -> use private overlay knowledge only
```

## Documentation Update Model

The repository should be maintained like software.

Use small updates:

1. Identify a knowledge gap.
2. Add or improve one article.
3. Keep the content public-safe.
4. Update related indexes if appropriate.
5. Commit the change clearly.
6. Review for accidental private identifiers.

Avoid large, unfocused rewrites unless the repository architecture changes.

## Vendor Documentation Monitoring

A scheduled monitoring process may check official documentation sources for changes.

Potential sources:

- NetSuite release notes and help documentation
- Pacejet public documentation
- SPS Commerce public documentation
- Avalara public documentation and developer resources

The monitor should not automatically rewrite documentation at first.

Instead, it should:

1. Check known source pages on a scheduled cadence.
2. Detect meaningful changes.
3. Record source URL, timestamp, and change summary.
4. Open an issue or draft pull request for review.
5. Suggest repository files that may need updates.
6. Require human or AI-assisted review before changing public documentation.

This protects the repository from accidental misinformation or vendor-documentation noise.

## Source Watch Public-Safety Rule

Source-watch configuration must not reveal the private organization using this repository.

Avoid:

- Private account URLs
- Internal ticket links
- Customer-specific documentation
- Partner-specific portals that require private login
- Internal company names or initials
- Private implementation notes

Use only official public documentation sources unless the monitored source belongs in a private repository.

## Content Classification

Before adding content, classify it:

| Classification | Public Repo? | Notes |
|---|---|---|
| General platform concept | Yes | Good public content. |
| Generic troubleshooting pattern | Yes | Keep examples anonymous and public-safe. |
| Official vendor release summary | Yes | Cite or reference official source. |
| Generic integration concept | Yes | Avoid account-specific mappings. |
| Internal SOP | No | Private repository only. |
| Custom field, script, workflow, or saved search | No | Private repository only. |
| Screenshot from private account | No | Private repository only. |
| Customer/vendor/trading partner specifics | No | Private repository only. |
| Pricing, manufacturing, or fulfillment logic | No | Private repository only. |

## Naming Guidance

Use generic names in public examples.

Preferred examples:

- Example Company
- Example Customer
- Example Vendor
- Example Item
- Example Warehouse
- Example Trading Partner
- Example Carrier

Avoid real company names, internal abbreviations, customer names, vendor names, employee names, item numbers, or locations that could identify the private organization.

## AI-Ready Documentation Expectations

Public articles should include:

- Clear titles
- Plain-language summaries
- Concept definitions
- Process context
- Troubleshooting logic
- Public-safe examples
- Related articles
- Oracle or vendor reference guidance where appropriate
- Explicit public/private boundary reminders for sensitive topics

AI systems should be able to answer general questions from the public repository without needing private information.

## Long-Term Vision

The public repository should become a broad, durable knowledge engine for ERP and connected business systems.

The private repositories should become internal operating overlays.

Together, they support an internal GPT that can:

- Explain general platform behavior
- Answer internal process questions
- Help troubleshoot issues
- Draft training guidance
- Suggest documentation updates
- Identify whether a question needs public knowledge, private knowledge, or both

The public repository remains generic, reusable, and anonymous. The private overlays contain the internal operating reality.
