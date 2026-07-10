# Knowledge Acquisition Engine

## Purpose
The Knowledge Acquisition Engine defines how public information becomes structured knowledge in this repository.

This layer helps contributors and AI systems convert public vendor, product, help center, documentation, FAQ, release note, and community information into public-safe NetSuite ecosystem knowledge.

## Role in the Repository
The repository is not only a documentation library. It is a knowledge operating system.

The Knowledge Acquisition Engine supports that goal by defining:

- Where knowledge can come from
- How sources should be evaluated
- How public information should be summarized
- How vendor documentation should be normalized
- How new articles should be created
- How facts should be cited or marked for verification
- How private or company-specific information should be excluded

## Core Principles
- Use public, authorized sources only.
- Respect login boundaries, paywalls, terms, and access restrictions.
- Separate observed facts from interpretation.
- Do not copy vendor documentation into the repository.
- Summarize, normalize, and connect knowledge to NetSuite concepts.
- Keep articles product-neutral unless the document is specifically about a named platform.
- Keep public and private knowledge clearly separated.
- Prefer small, focused articles over large documents.
- Preserve source awareness for future review and validation.

## Source Categories
Common public source categories may include:

- Vendor websites
- Public help centers
- Public developer documentation
- Public FAQs
- Public release notes
- Public knowledge articles
- Public integration guides
- Public API documentation
- Public marketplace listings
- Public community discussions when appropriate

## Expected Outputs
Knowledge acquisition should result in reusable repository assets such as:

- Platform overview articles
- Business purpose summaries
- NetSuite touchpoint documents
- Terminology references
- Generic workflow explanations
- Public-safe troubleshooting categories
- Article outlines for future expansion
- Source notes for future validation

## Public-Safe Boundary
This layer must not introduce company-specific operating details into the public repository.

Do not include:

- Internal company procedures
- Customer-specific documentation
- Private screenshots
- Saved searches
- Custom fields
- Workflows
- SuiteScripts
- Pricing logic
- Manufacturing logic
- Carrier rules
- EDI maps
- Internal prompts
- Confidential implementation details

If publishing the information helps someone understand how a specific company operates, it belongs in a private enterprise repository.

## Related Architecture Documents
- `architecture/PUBLIC_SAFETY_RULES.md`
- `architecture/KNOWLEDGE_DOMAINS.md`
- `architecture/ARTICLE_CLASSIFICATION.md`
- `architecture/KNOWLEDGE_RELATIONSHIPS.md`
- `architecture/AI_RETRIEVAL_MODEL.md`
- `architecture/ENTERPRISE_KNOWLEDGE_MODEL.md`
- `architecture/ECOSYSTEM_DOMAINS.md`
- `architecture/NETSUITE_TOUCHPOINTS.md`

## Future Documents
Planned documents for this layer include:

- `SOURCE_HIERARCHY.md`
- `VENDOR_RESEARCH_MODEL.md`
- `CONTENT_NORMALIZATION.md`
- `ARTICLE_GENERATION_WORKFLOW.md`
- `SOURCE_CITATION_POLICY.md`
- `RELEASE_NOTE_PROCESS.md`
- `QUALITY_SCORE_MODEL.md`
- `ARTICLE_LIFECYCLE.md`
