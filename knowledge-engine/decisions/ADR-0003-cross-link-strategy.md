# ADR-0003: Cross-Link Strategy

**Status**: Accepted

**Date**: 2026-07-01

## Context

Cross-links turn individual articles into a connected knowledge network. For AI agents, cross-links form a knowledge graph that can be traversed for related content. For humans, they provide pathways to deeper learning. At 10,000+ articles, cross-links must be systematic, not ad-hoc.

## Decision

1. **Every article must have a "Related Articles" section** at the bottom with at least 3 links.
2. **Links use relative paths**: `[Title](article.md)` (same module) or `[Title](../module/article.md)` (cross-module).
3. **Cross-links must span modules** — at least 1 link should be to a different module.
4. **Links go both directions where possible** — if A links to B, B should link to A.
5. **Links use descriptive text** — not "click here" or "this article."

## Rationale

1. **Relative paths** work in GitHub, MkDocs, and any Markdown renderer without configuration.
2. **Minimum 3 links** ensures no article is an island.
3. **Cross-module linking** connects learning paths across domains.
4. **Bi-directional linking** improves knowledge graph density.

## Consequences

- New articles must identify related articles during creation.
- Existing articles may have sparse cross-links (technical debt).
- Automated link validation is essential at scale.
- Link density becomes a quality metric.

## Alternatives Considered

- **No cross-linking standard**: Rejected — leads to islands of content.
- **Automated cross-link suggestions via AI**: Would be ideal but is not yet implemented. Manual linking is the current approach.
- **Central topic map**: A single file listing all relations. Rejected — doesn't scale and creates a single point of failure.