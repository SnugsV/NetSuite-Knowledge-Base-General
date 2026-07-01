# ADR-0002: Article Format Standard

**Status**: Accepted

**Date**: 2026-07-01

## Context

Every article in the repository must follow a consistent format. Consistency enables:
- Human readers to know where to find information
- AI systems to parse articles structurally
- Automated validation (front matter, cross-links)
- MkDocs rendering without customization

## Decision

All articles use this format:

1. **YAML front matter** (required fields: `title`, `module`, `difficulty`, `estimated_time`, `status`)
2. **Single H1** matching the `title` field
3. **Standard section headings** in fixed order: Quick Summary, Difficulty, Estimated Time, Prerequisites, Overview, Why It Matters, Core Concepts, Step-by-Step, Best Practices, Common Mistakes, FAQ, Related Articles, Oracle References
4. **Required sections**: Quick Summary, Overview, Common Mistakes, Related Articles, Oracle References
5. **Optional sections**: Prerequisites, Step-by-Step, FAQ, Core Concepts

## Rationale

1. **Fixed section order** enables readers and AI systems to predict where information lives.
2. **Required sections** ensure every article has a minimum viable structure for AI retrieval.
3. **Optional sections** provide flexibility without breaking the pattern.
4. **Front matter** enables filtering, classification, and metadata queries in AI systems.

## Consequences

- Every new article must follow this format.
- Existing articles should be updated to match (technical debt).
- Automated validators can check compliance.
- MkDocs templates map directly from headings to page structure.

## Alternatives Considered

- **Free-form structure**: No fixed sections. Rejected — inconsistent structure hurts AI retrieval.
- **Strict structure, all sections required**: Rejected — some articles don't need FAQ or Step-by-Step.
- **JSON front matter instead of YAML**: Rejected — YAML is standard for Markdown front matter.