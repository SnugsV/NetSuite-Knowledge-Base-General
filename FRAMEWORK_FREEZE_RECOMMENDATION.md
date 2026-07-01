# Framework Freeze Recommendation

## Recommendation: **Conditional Freeze**

The Knowledge Engineering Framework should be frozen after the consolidation actions identified in FRAMEWORK_REVIEW.md are complete. The framework is architecturally sound but has document duplication that will cause maintenance drift over time.

---

## What Should Be Frozen

After consolidation, these documents should rarely change:

| Document | Freeze Standard | Change Threshold |
|---|---|---|
| DOCUMENTATION_STANDARDS.md | **Frozen** | Major architectural changes only |
| WRITING_STANDARDS.md | **Frozen** | Major philosophical shifts only |
| AI_STANDARDS.md | **Frozen** | Major shifts in AI technology only |
| QUALITY_STANDARDS.md | **Frozen** | When scoring methodology needs revision |
| PROJECT_MEMORY.md | **Frozen** | When memory architecture changes |
| PROJECT_LIFECYCLE.md | **Frozen** | When phases or exit criteria change |
| DECISION_FRAMEWORK.md | **Frozen** | When risk categories or processes change |

## What Should Remain Flexible

| Document | Change Frequency | Reason |
|---|---|---|
| PROMPT_LIBRARY.md | Grows organically | New task patterns emerge |
| RELEASE_PROCESS.md | Rare | May adjust as project scales |
| GITHUB_WORKFLOW.md | Rare | May change with automation |
| REVIEW_CHECKLIST.md | Rare | May gain items as processes mature |

## Blocker Resolution Path

### Blocker 1: Document Duplication

**Status**: Unresolved — requires action before freeze.

**Documents affected**:
- `knowledge-engine/PROJECT_CHARTER.md` vs `/PROJECT_CHARTER.md`
- `knowledge-engine/OPERATING_PROCEDURE.md` vs `knowledge-engine/GITHUB_WORKFLOW.md` vs `/HERMES_OPERATING_PROCEDURE.md`
- `governance/contribution-guide.md` vs `/CONTRIBUTING.md`

**Resolution**: See Phase 3 consolidation actions in FRAMEWORK_REVIEW.md.

### Blocker 2: Template Duplication

**Status**: Unresolved — requires action before freeze.

**Documents affected**:
- `templates/ARTICLE_TEMPLATE.md` vs `templates/document-template.md`

**Resolution**: Adopt ARTICLE_TEMPLATE.md as canonical. Deprecate document-template.md.

### Blocker 3: Governance File Naming

**Status**: Low priority — can be done pre-freeze or post-freeze.

**Documents affected**: `governance/AI_GUIDELINES.md`, `REVIEW_PROCESS.md`, `STYLE_GUIDE.md`, `WRITING_GUIDELINES.md`, `contribution-guide.md`

**Resolution**: Rename to kebab-case for consistency.

### Blocker 4: MASTER_PROJECT_PROMPT.md Architecture

**Status**: Medium priority — if frozen in current form, drift is inevitable.

**Recommendation**: Restructure as a navigation hub rather than a summary document.

## What Happens If We Freeze Now

If the framework is frozen without addressing the blockers:

**Positive effects**:
- Standards become stable and predictable
- Contributors and AI agents can rely on unchanging guidance
- Framework documents become reference points, not moving targets

**Negative effects**:
- Document duplication will cause guidance to diverge over time
- Two PROJECT_CHARTER.md files will tell different stories
- MASTER_PROJECT_PROMPT.md will drift from its source documents
- Two template formats will cause "which template should I use?" confusion

## Recommended Timeline

Before opening this PR, complete the following (estimated 90 minutes total):

```
High Priority (55 min):
  1. Merge contribution-guide.md → CONTRIBUTING.md          (10 min)
  2. Deprecate document-template.md, finalize ARTICLE_TEMPLATE  (15 min)
  3. Consolidate PROJECT_CHARTER.md                              (15 min)
  4. Restructure MASTER_PROJECT_PROMPT.md as nav hub             (15 min)

Medium Priority (35 min):
  5. Create ADR-0001 through ADR-0005                           (30 min)
  6. Rename governance/ files to kebab-case                      (5 min)

Low Priority (15 min):
  7. Add article size guidance, statuses, module README rules    (15 min)
```

After these actions, the framework can be frozen with confidence.

## Freeze Enforcement

After this release:

1. **Framework documents require ADR** — Changes to frozen documents must be documented in an Architecture Decision Record
2. **Framework changes are high-risk** — Per DECISION_FRAMEWORK.md, framework modifications require approval
3. **PRs must note framework changes** — Any PR that modifies a frozen document must call this out explicitly

## Conclusion

The Knowledge Engineering Framework is architecturally sound and ready for content development. With <90 minutes of consolidation work, it should be frozen to provide stable guidance for the next 6-12 months of content development.

**Recommended action**: Complete the consolidation actions in this PR, then freeze.

## Related Documents

- [FRAMEWORK_REVIEW.md](FRAMEWORK_REVIEW.md) — Full review with all findings
- [knowledge-engine/decisions/](decisions/) — Architecture Decision Records