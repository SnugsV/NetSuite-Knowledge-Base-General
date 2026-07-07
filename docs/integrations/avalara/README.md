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

### Connector Troubleshooting

The Connector Troubleshooting cluster explains how to investigate Avalara symptoms from a NetSuite-centered perspective.

Start here:

1. [Common Avalara Error Patterns](troubleshooting/COMMON_AVALARA_ERROR_PATTERNS.md)
2. [Tax Did Not Calculate](troubleshooting/TAX_DID_NOT_CALCULATE.md)
3. [Tax Calculated Unexpectedly](troubleshooting/TAX_CALCULATED_UNEXPECTEDLY.md)
4. [Address Validation Issues](troubleshooting/ADDRESS_VALIDATION_ISSUES.md)
5. [Item Taxability Mismatch](troubleshooting/ITEM_TAXABILITY_MISMATCH.md)
6. [Exemption Not Applied](troubleshooting/EXEMPTION_NOT_APPLIED.md)
7. [Order and Invoice Tax Mismatch](troubleshooting/ORDER_INVOICE_TAX_MISMATCH.md)

Recommended learning path:

```text
Common Avalara Error Patterns
  -> Tax Did Not Calculate
  -> Tax Calculated Unexpectedly
  -> Address Validation Issues
  -> Item Taxability Mismatch
  -> Exemption Not Applied
  -> Order and Invoice Tax Mismatch
```

The most important Connector Troubleshooting article for AI reasoning is [Common Avalara Error Patterns](troubleshooting/COMMON_AVALARA_ERROR_PATTERNS.md), because it teaches the assistant to classify the observable symptom before choosing a more specific troubleshooting path.

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

## Connector Troubleshooting Map

```mermaid
flowchart TD
    Symptom[Observable Avalara Symptom]
    Pattern[Common Error Pattern]
    NoTax[Tax Did Not Calculate]
    Unexpected[Tax Calculated Unexpectedly]
    Address[Address Validation Issue]
    Item[Item Taxability Mismatch]
    Exemption[Exemption Not Applied]
    Mismatch[Order Invoice Tax Mismatch]
    Evidence[Record Evidence]
    Escalation[Internal Review if Needed]

    Symptom --> Pattern
    Pattern --> NoTax
    Pattern --> Unexpected
    Pattern --> Address
    Pattern --> Item
    Pattern --> Exemption
    Pattern --> Mismatch
    NoTax --> Evidence
    Unexpected --> Evidence
    Address --> Evidence
    Item --> Evidence
    Exemption --> Evidence
    Mismatch --> Evidence
    Evidence --> Escalation
```

This map teaches the assistant to route from symptom to diagnostic path before recommending escalation.

## Cross-Cluster Reasoning Map

```mermaid
flowchart TD
    Question[Employee Tax Question]
    Exemptions[Exemption Management]
    Transactions[Transactions]
    Connector[Connector Troubleshooting]
    Customer[Customer]
    Address[Address]
    Item[Item]
    Certificate[Certificate Context]
    Lifecycle[Transaction Lifecycle]
    Troubleshooting[Troubleshooting Path]
    Answer[Consultant-Style Answer]

    Question --> Exemptions
    Question --> Transactions
    Question --> Connector
    Exemptions --> Customer
    Exemptions --> Certificate
    Exemptions --> Item
    Transactions --> Address
    Transactions --> Lifecycle
    Connector --> Troubleshooting
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
| Connector Troubleshooting | 100% | 90% | 100% | 80% | 95% |
| Returns | 0% | 0% | 0% | 0% | 0% |
| Compliance | 0% | 0% | 0% | 0% | 0% |

Coverage percentages are directional, not formal validation scores. They represent whether the cluster can currently support useful AI-assisted reasoning.

## Suggested Next Cluster: Returns

After completing the initial Exemption Management, Transactions, and Connector Troubleshooting clusters, the next recommended Avalara cluster is Returns.

Planned Returns articles:

- Return lifecycle
- Refund tax reasoning
- Return troubleshooting

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

### Connector troubleshooting retrieval signals

- Avalara error
- AvaTax error
- connector error
- response error
- tax did not calculate
- tax calculated unexpectedly
- address validation failed
- exemption not applied
- item taxability mismatch
- order invoice tax mismatch

The assistant should usually retrieve:

1. [Common Avalara Error Patterns](troubleshooting/COMMON_AVALARA_ERROR_PATTERNS.md),
2. the specific symptom article,
3. [Transaction Lifecycle](transactions/TRANSACTION_LIFECYCLE.md) when timing or downstream records are involved,
4. and related exemption or item articles when the symptom involves customer, certificate, or item context.

## Public Sources

- https://developer.avalara.com/avatax/errors/
- https://developer.avalara.com/products/avatax/
- https://knowledge.avalara.com/

## Related Framework Documents

- [AI Knowledge Metadata](../../../knowledge-engine/AI_KNOWLEDGE_METADATA.md)
- [ERP Intelligence Knowledge Model](../../../knowledge-engine/KNOWLEDGE_MODEL.md)
- [ERP Intelligence Knowledge Graph](../../../knowledge-engine/KNOWLEDGE_GRAPH.md)
- [Knowledge Cluster Article Template](../../../templates/KNOWLEDGE_CLUSTER_TEMPLATE.md)
