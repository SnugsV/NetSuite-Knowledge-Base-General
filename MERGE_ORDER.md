# Merge Order

## Dependency Rules

- Inventory phases must merge in order (6 → 7 → 8)
- All ERP modules (4-12) can merge in any order but docs/README.md will conflict — merge them sequentially
- Framework extensions (13-17) modify knowledge-engine/README.md — merge sequentially
- PR #19 must merge before PR #22
- PR #21 supersedes PR #20
- PR #19 supersedes PR #18
- PRs #23-25 are independent and can merge after framework extensions

## Merge Sequence

| Step | PR | Branch | Action | Risk |
|---|---|---|---|---|
| 1 | #18 | release/2.1-pacejet-planning | **Close** — superseded by PR #19 | None |
| 2 | #20 | release/2.2-platform-architecture | **Close** — superseded by PR #21 | None |
| 3 | #4 | sprint/0.3-administration | **Merge** — Administration module | Low |
| 4 | #5 | sprint/0.4-saved-searches | **Merge** — resolve docs/README.md | Medium |
| 5 | #6 | sprint/0.5a-inventory-fundamentals | **Merge** — Inventory phase 1 | Low |
| 6 | #7 | sprint/0.5b-inventory-operations | **Merge** — Inventory phase 2 | Low |
| 7 | #8 | sprint/0.5c-advanced-inventory | **Merge** — Inventory phase 3 | Low |
| 8 | #9 | sprint/0.6-purchasing | **Merge** — Purchasing module | Medium |
| 9 | #10 | sprint/0.7-sales | **Merge** — Sales module | Medium |
| 10 | #11 | sprint/0.8-manufacturing | **Merge** — Manufacturing module | Medium |
| 11 | #12 | sprint/0.9-accounting | **Merge** — Accounting module | Medium |
| 12 | #21 | release/2.2-nav-and-cleanup | **Merge** — Nav cleanup, PLATFORM_ARCHITECTURE.md | Low |
| 13 | #26 | release/arch-review-prep | **Merge** — ARCHITECTURE_REVIEW_PREP.md | Low |
| 14 | #13 | release/1.0-ai-support-intelligence | **Merge** — Support Intelligence | Low |
| 15 | #14 | release/1.1-customer-context | **Merge** — Customer Context | Medium |
| 16 | #15 | release/1.2-ai-skill-saved-search | **Merge** — AI Skills | Medium |
| 17 | #16 | release/1.3-ai-solution-architect | **Merge** — Solution Architect | Medium |
| 18 | #17 | release/2.0-customer-metadata | **Merge** — Customer Metadata | Medium |
| 19 | #19 | release/2.1-pacejet-intelligence | **Merge** — Pacejet Intelligence Pack | Low |
| 20 | #22 | release/2.3-2.4-pacejet-scenarios-and-pipeline | **Merge** — Scenarios + Pipeline | Low |
| 21 | #23 | release/2.5-agent-runtime | **Merge** — Agent Runtime | Low |
| 22 | #24 | release/3.0-experience-intelligence | **Merge** — Experience Intelligence | Low |
| 23 | #25 | release/4.0-validation-benchmark | **Merge** — Validation Framework | Low |

## Conflict Resolution Strategy

### docs/README.md (conflicts in steps 3-12)
The docs/README.md file will conflict because each ERP module adds entries and updates statuses. Strategy:
- Keep the latest version (the most recently merged PR's docs/README.md)
- The final docs/README.md will be from PR #12 (Accounting — last ERP module)
- Verify it has all module entries after all merges

### RELEASE_PLAN_0.5.md (conflicts in steps 5-7)
Each inventory phase adds to this file. Strategy:
- Keep the latest version (PR #8 — Advanced Inventory)
- It's a planning artifact, not a navigation-critical file

### knowledge-engine/README.md (conflicts in steps 14-18)
Each framework extension updates the README. Strategy:
- Keep the latest version (PR #17 — Customer Metadata — last framework extension)
- Verify it references all extensions after all merges

### PLATFORM_ARCHITECTURE.md (steps 2, 12)
PR #20 creates it, PR #21 supersedes with a better version. Strategy:
- Close PR #20, keep PR #21's version

### PROJECT_STATUS.md (multiple steps)
Multiple PRs modify this. Strategy: Accept the latest version and do a final update pass.

## Verification

After all merges complete:
1. Run cross-link validation
2. Check all README.md files for accurate module indexes
3. Verify knowledge-engine/README.md references all extensions
4. Verify docs/README.md lists all 9 ERP modules
5. Push final main branch