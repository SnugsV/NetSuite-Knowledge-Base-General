# ADR-0004: Content Lifecycle and Review Model

**Status**: Accepted

**Date**: 2026-07-01

## Context

Content in the repository goes through a lifecycle from creation to archival. A clear status model is needed so readers, AI agents, and maintainers know the reliability of any article.

## Decision

Articles progress through 5 statuses:

```
Draft → Review → Approved → Deprecated → Archive
```

| Status | Meaning | AI Consumption | End-User Consumption |
|---|---|---|---|
| **Draft** | Work in progress | Should not be used | Should not be used |
| **Review** | Ready for validation | Use with caution | Use with caution |
| **Approved** | Reviewed and ready | Safe to use | Safe to use |
| **Deprecated** | Replaced by newer content | Not recommended | Not recommended |
| **Archive** | Historical reference | Reference only | Reference only |

Articles move from Draft → Review when the author believes content is complete. They move from Review → Approved after passing the REVIEW_CHECKLIST.md.

## Rationale

1. **Five statuses** cover the full lifecycle without unnecessary complexity.
2. **"Deprecated" vs "Archived"** distinguishes "replaced by something new" from "kept for historical reference."
3. **Front matter visibility** means AI systems can filter articles by status.
4. **No "Published" status** — all content in a public GitHub repo is technically published. Status controls reliability signaling.

## Consequences

- Every article must have a status in front matter.
- Review is a manual process against REVIEW_CHECKLIST.md.
- Deprecated and Archived articles should not be removed — they may be needed for historical reference.
- AI agents should filter by status when retrieving content.

## Alternatives Considered

- **Three statuses (Draft/Review/Approved)**: Rejected — no distinction between deprecated and archived content.
- **Two statuses (Draft/Approved)**: Rejected — no review phase.
- **No status model**: Rejected — readers can't distinguish reliable from unreliable content.