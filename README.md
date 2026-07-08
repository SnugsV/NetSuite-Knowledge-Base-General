# NetSuite Intelligence Platform

> Public-safe, AI-friendly NetSuite knowledge designed for consultant-style reasoning, semantic search, RAG, knowledge graphs, and human learning.

## Mission

The NetSuite Intelligence Platform helps people and AI assistants reason through NetSuite and related business-system questions.

This repository is not a replacement for Oracle's official documentation. It provides original, public-safe explanations, reasoning models, record relationships, troubleshooting paths, benchmark questions, and AI-ready Markdown that complement official vendor documentation.

The guiding question for every article is:

> What knowledge would an experienced NetSuite consultant connect together to reason through this problem?

## Who This Is For

- AI assistants and retrieval systems
- NetSuite administrators
- Consultants and implementation teams
- Developers and SuiteScript users
- Finance and accounting teams
- Sales, purchasing, inventory, ecommerce, and operations users
- Business owners evaluating or operating NetSuite
- Students learning ERP concepts

## Project Goals

- Teach reasoning, not just definitions
- Support semantic search, RAG, knowledge graphs, and AI answer generation
- Explain NetSuite records, relationships, workflows, and troubleshooting paths
- Provide public-safe integration knowledge for common NetSuite ecosystem platforms
- Use consistent metadata for retrieval and evaluation
- Cross-link articles so assistants can retrieve related concepts together
- Preserve clear boundaries between public knowledge and private implementation details
- Keep content version controlled, reviewable, and easy to improve over time

## Repository Structure

```text
/                         Root project tracking and governance files
knowledge-engine/         AI knowledge framework and repository operating model
docs/                     Main knowledge base articles by NetSuite area or integration
templates/                Reusable article and knowledge-cluster templates
governance/               Writing, review, and documentation standards
sources/                  Public vendor and documentation reference indexes
assets/                   Diagrams, images, icons, and supporting files
```

## Knowledge Engineering Framework

The `knowledge-engine/` directory defines how this repository should be written, reviewed, and used by AI systems.

Key knowledge-engine documents describe:

- article metadata standards
- reasoning prerequisites
- employee-style questions answered
- related-article linking
- knowledge graph relationships
- benchmark and evaluation design
- public-safe boundaries

Future AI agents should use the knowledge-engine files before creating or updating articles.

## Article Design Principles

Every article should help an assistant answer better questions, not merely retrieve text.

A strong article usually includes:

- metadata for retrieval and knowledge graphs
- quick summary
- core concept or reasoning rule
- relevant records and related records
- lifecycle or relationship model when useful
- consultant-style reasoning sequence
- common employee-style questions
- common misconceptions
- related articles
- public sources
- public-safety review

## AI Retrieval Guidance

Articles should be written so an AI assistant can:

1. Identify the user's symptom or question type.
2. Retrieve the most relevant concept, lifecycle, troubleshooting, and benchmark articles.
3. Compare related records before drawing conclusions.
4. Separate symptoms from root causes.
5. Explain uncertainty and evidence needed.
6. Avoid inventing private setup, internal policy, customer-specific facts, or proprietary processes.
7. Escalate when the answer depends on private configuration or internal review.

## Public-Safe Scope

This repository may include:

- NetSuite concepts
- ERP education
- public vendor and integration concepts
- generic business processes
- generic troubleshooting models
- record relationships
- AI reasoning models
- retrieval and benchmark guidance

This repository must not include:

- company-specific SOPs
- private implementation details
- customer-specific examples
- screenshots of private systems
- custom fields, saved searches, workflows, or scripts from a specific account
- pricing, negotiated rates, credentials, account numbers, or private configuration
- internal prompts or proprietary operating procedures

Private implementation knowledge should live in a separate private repository or internal knowledge source.

## Learning Paths

### Beginner

Start with NetSuite concepts, navigation, roles, dashboards, records, and global search.

### Intermediate

Move into inventory, purchasing, sales, reporting, saved searches, CSV imports, workflows, and transaction relationships.

### Advanced

Explore SuiteScript, SuiteTalk, integrations, SuiteAnalytics, automation, advanced administration, and cross-system reasoning.

### AI and Retrieval

Start with the knowledge-engine files, then review article metadata, knowledge clusters, benchmark questions, and related-article links.

## Evaluation

Benchmark question sets help test whether an AI assistant can reason through NetSuite ecosystem questions like an experienced consultant.

A strong answer should retrieve related articles, compare records, explain evidence, respect public/private boundaries, and escalate appropriately when private review is required.

See [Integration Benchmark Index](docs/integrations/BENCHMARKS.md).

## Disclaimer

Oracle, NetSuite, SuiteScript, SuiteTalk, and related trademarks belong to Oracle Corporation. This repository is community-maintained and is not affiliated with or endorsed by Oracle. Official Oracle documentation should always be treated as the authoritative source.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) and the governance documents before submitting new content.

## Roadmap

See [ROADMAP.md](ROADMAP.md).
