# ADR-0001: Documentation Structure

**Status**: Accepted

**Date**: 2026-07-01

## Context

The repository needs a documentation structure that scales from 20 articles to 10,000+. The structure must support multiple audiences (beginners, administrators, developers, consultants), multiple AI agents, future MkDocs/GitHub Pages, and community contributions.

## Decision

Organize documentation by **module** (business function), with each module in its own directory under `docs/`. Use a flat hierarchy with one level of depth:

```
docs/
  getting-started/
  administration/
  accounting/
  crm/
  inventory/
  manufacturing/
  purchasing/
  sales/
  reporting/
  saved-searches/
  suiteanalytics/
  suitescript/
  suitetalk/
  workflows/
  integrations/
  release-notes/
  troubleshooting/
```

## Rationale

1. **Module-based grouping** aligns with how NetSuite itself is organized (centers, roles, feature groups).
2. **Flat hierarchy** avoids deep nesting that hurts navigation and link maintenance.
3. **Single level of depth** keeps cross-links simple: `../target-module/article.md`.
4. **Separation from non-content directories**: `knowledge-engine/`, `templates/`, `governance/`, `sources/` are siblings of `docs/`, not children.

## Consequences

- Each module directory requires a README.md acting as an index.
- Cross-module links use `../` paths (works at any depth).
- Adding a new module means adding a new directory — no restructuring needed.
- Future sub-modules can be added as subdirectories (e.g., `administration/security/`).
- MkDocs navigation configuration will map directly from folder structure.

## Alternatives Considered

- **Tag-based organization**: Articles tagged by topic, stored flat. Rejected because tags have no hierarchy, making navigation harder for humans.
- **Difficulty-based organization**: Articles organized by difficulty (beginner/, intermediate/, advanced/). Rejected because cross-referencing would span all directories — it's a filter, not an organizational dimension.
- **Single flat directory**: All articles in one folder. Rejected — does not scale past ~50 files.