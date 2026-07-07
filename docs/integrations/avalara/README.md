# Avalara Integration Knowledge Hub

## Purpose

This section organizes public-safe Avalara knowledge for the NetSuite Intelligence Platform.

The goal is not to reproduce Avalara documentation. The goal is to help readers and AI assistants reason through common NetSuite and Avalara questions using connected concepts, record relationships, business process context, and troubleshooting paths.

## Public-Safe Scope

This section may include:

- public Avalara concepts
- public AvaTax product capabilities
- NetSuite-centered reasoning
- generic integration patterns
- public-safe troubleshooting guidance
- record relationship explanations
- AI reasoning guidance

This section must not include company-specific tax setup, private examples, internal mappings, screenshots, or proprietary process details.

Private implementation knowledge belongs in a private repository.

## Knowledge Clusters

### Exemption Management

The Exemption Management cluster explains how customer, certificate, item, address, transaction, and timing context can affect exemption-related tax results.

Start here:

1. [Exemption Certificates](exemptions/EXEMPTION_CERTIFICATES.md)
2. [Customer Exemptions](exemptions/CUSTOMER_EXEMPTIONS.md)
3. [Item Taxability](exemptions/ITEM_TAXABILITY.md)
4. [Why Is Customer Tax Exempt?](exemptions/WHY_IS_CUSTOMER_TAX_EXEMPT.md)
5. [Exemption Troubleshooting](exemptions/EXEMPTION_TROUBLESHOOTING.md)
6. [Common Exemption Scenarios](exemptions/COMMON_EXEMPTION_SCENARIOS.md)

Recommended learning path:

```text
Exemption Certificates
  -> Customer Exemptions
  -> Item Taxability
  -> Why Is Customer Tax Exempt?
  -> Exemption Troubleshooting
  -> Common Exemption Scenarios
```

### Transactions

The Transactions cluster explains how NetSuite transaction stages affect Avalara tax reasoning.

Start here:

1. [Sales Orders](transactions/SALES_ORDERS.md)
2. [Invoices](transactions/INVOICES.md)
3. [Cash Sales](transactions/CASH_SALES.md)
4. [Credit Memos](transactions/CREDIT_MEMOS.md)
5. [Transaction Lifecycle](transactions/TRANSACTION_LIFECYCLE.md)

Recommended learning path:

```text
Sales Orders
  -> Invoices
  -> Cash Sales
  -> Credit Memos
  -> Transaction Lifecycle
```

The most important Transactions article for AI reasoning is [Transaction Lifecycle](transactions/TRANSACTION_LIFECYCLE.md), because it teaches the assistant how to compare records across order, billing, payment, and correction stages.

## Exemption Management Relationship Map

```mermaid
flowchart TD
    Customer[Customer]
    Certificate[Exemption Certificate]
    Address[Customer Address]
    Item[Item]
    Transaction[Sales Order or Invoice]
    Line[Transaction Line]
    Avalara[Avalara AvaTax Calculation]
    Result[Tax Result]

    Customer --> Transaction
    Certificate --> Customer
    Address --> Transaction
    Item --> Line
    Line --> Transaction
    Transaction --> Avalara
    Customer --> Avalara
    Certificate --> Avalara
    Address --> Avalara
    Item --> Avalara
    Avalara --> Result
```

## Transaction Lifecycle Map

```mermaid
flowchart LR
    SO[Sales Order]
    INV[Invoice]
    CS[Cash Sale]
    CM[Credit Memo]
    Review[Review or Correction]

    SO --> INV
    SO --> CS
    INV --> CM
    CS --> Review
    CM --> Review
```

This lifecycle map is a generic reasoning model. It is not a company-specific process map.

## Cross-Cluster Reasoning Map

```mermaid
flowchart TD
    Question[Employee Tax Question]
    Exemptions[Exemption Management]
    Transactions[Transactions]
    Customer[Customer]
    Address[Address]
    Item[Item]
    Certificate[Certificate Context]
    Lifecycle[Transaction Lifecycle]
    Troubleshooting[Troubleshooting Path]
    Answer[Consultant-Style Answer]

    Question --> Exemptions
    Question --> Transactions
    Exemptions --> Customer
    Exemptions --> Certificate
    Exemptions --> Item
    Transactions --> Address
    Transactions --> Lifecycle
    Customer --> Troubleshooting
    Address --> Troubleshooting
    Item --> Troubleshooting
    Certificate --> Troubleshooting
    Lifecycle --> Troubleshooting
    Troubleshooting --> Answer
```

## Exemption Troubleshooting Flow

```mermaid
flowchart TD
    Start[Unexpected tax result]
    Txn[Identify exact transaction]
    Customer[Review customer]
    Cert[Review exemption certificate context]
    Address[Review address]
    Item[Review item or line]
    Date[Review transaction date and calculation timing]
    Compare[Compare with similar transaction]
    Explain[Explain likely cause and evidence]
    Internal[Internal verification needed]

    Start --> Txn
    Txn --> Customer
    Customer --> Cert
    Cert --> Address
    Address --> Item
    Item --> Date
    Date --> Compare
    Compare --> Explain
    Compare --> Internal
```

## Coverage Status

| Cluster | Foundation | Integration | Troubleshooting | Reference | Reasoning |
|---|---:|---:|---:|---:|---:|
| Exemption Management | 100% | 100% | 100% | 100% | 90% |
| Transactions | 100% | 100% | 80% | 80% | 100% |
| Returns | 0% | 0% | 0% | 0% | 0% |
| Compliance | 0% | 0% | 0% | 0% | 0% |
| Connector Troubleshooting | 0% | 0% | 0% | 0% | 0% |

Coverage percentages are directional, not formal validation scores. They represent whether the cluster can currently support useful AI-assisted reasoning.

## Suggested Next Cluster: Connector Troubleshooting

After completing the initial Exemption Management and Transactions clusters, the next recommended cluster is Connector Troubleshooting.

Planned connector troubleshooting articles:

- Tax did not calculate
- Tax calculated unexpectedly
- Avalara connection or response issue
- Address validation issue
- Item or product taxability mismatch
- Exemption certificate not applied
- Order and invoice tax mismatch

## AI Retrieval Guidance

When a user asks an Avalara question, retrieve based on the question type.

### Exemption-related retrieval signals

- customer tax exempt
- exemption certificate
- resale certificate
- no tax calculated
- tax calculated for exempt customer
- item taxability
- same customer different tax result
- Avalara exemption issue

The assistant should usually retrieve:

1. the scenario or troubleshooting article,
2. the specific concept article,
3. and the related transaction article.

### Transaction-related retrieval signals

- sales order tax
- invoice tax
- cash sale tax
- credit memo tax
- tax changed between order and invoice
- tax changed after invoicing
- tax correction
- why did tax change

The assistant should usually retrieve:

1. [Transaction Lifecycle](transactions/TRANSACTION_LIFECYCLE.md),
2. the specific transaction article,
3. and any related exemption article if customer, certificate, or item taxability is involved.

## Public Sources

- https://developer.avalara.com/products/avatax/
- https://knowledge.avalara.com/

## Related Framework Documents

- [AI Knowledge Metadata](../../../knowledge-engine/AI_KNOWLEDGE_METADATA.md)
- [ERP Intelligence Knowledge Model](../../../knowledge-engine/KNOWLEDGE_MODEL.md)
- [ERP Intelligence Knowledge Graph](../../../knowledge-engine/KNOWLEDGE_GRAPH.md)
- [Knowledge Cluster Article Template](../../../templates/KNOWLEDGE_CLUSTER_TEMPLATE.md)
