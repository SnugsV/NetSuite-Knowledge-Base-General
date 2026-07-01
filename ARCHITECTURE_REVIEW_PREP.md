# Architecture Review Preparation

## Repository Overview

| Metric | Value |
|---|---|
| Markdown files | 65 |
| Total lines of content | 6,456 |
| Total words | 34,266 |
| Top-level directories | 8 (docs/, knowledge-engine/, governance/, templates/, sources/, .github/, kNowledge-engine/) |
| Root-level .md files | 13 |
| Pull requests (total) | 25 |
| Pull requests (open) | 22 |
| Pull requests (merged) | 3 |
| File types | 65 `.md`, 1 `.gitignore` |

## Module Statistics

### ERP Curriculum (`docs/` — 19 files, 2,111 lines)

| Module | Files | Lines | Status on main |
|---|---|---|---|
| Getting Started | 12 | 1,535 | Complete |
| Inventory | 2 | 156 | Started (2 articles on main; 29 on feature branch) |
| Saved Searches | 2 | 158 | Started (2 articles on main; 23 on feature branch) |
| SuiteScript | 1 | 69 | Started (placeholder) |
| SuiteTalk | 1 | 81 | Started (placeholder) |

**Completion issue**: 8 of 9 planned ERP modules exist only on feature branches and have not been merged to main. Only Getting Started is fully available on main.

### Knowledge Engineering Framework (`knowledge-engine/` — 20 files, 1,767 lines)

| Component | Files | Status on main |
|---|---|---|
| Core framework (14 documents) | 14 | Complete (merged) |
| ADRs | 5 | Complete (merged) |
| Support Intelligence | 0 | Not on main (branch release/1.0-ai-support-intelligence) |
| Customer Context | 0 | Not on main (branch release/1.1-customer-context) |
| AI Skills | 0 | Not on main (branch release/1.2-ai-skill-saved-search) |
| Solution Architect | 0 | Not on main (branch release/1.3-ai-solution-architect) |
| Customer Metadata | 0 | Not on main (branch release/2.0-customer-metadata) |
| Agent Runtime | 0 | Not on main (branch release/2.5-agent-runtime) |
| Experience Intelligence | 0 | Not on main (branch release/3.0-experience-intelligence) |
| Knowledge Intelligence | 0 | Empty dir on main (content on branch release/2.3-2.4) |

### Governance (`governance/` — 5 files, 174 lines)

| File | Lines |
|---|---|
| AI_GUIDELINES.md | 46 |
| STYLE_GUIDE.md | 35 |
| REVIEW_PROCESS.md | 22 |
| WRITING_GUIDELINES.md | 30 |
| contribution-guide.md | 33 |

### Templates (`templates/` — 4 files, 110 lines)

| File | Lines | Status |
|---|---|---|
| ARTICLE_TEMPLATE.md | 58 | Active |
| document-template.md | 17 | Deprecated (header says use ARTICLE_TEMPLATE) |
| FAQ_TEMPLATE.md | 17 | Active |
| TROUBLESHOOTING_TEMPLATE.md | 18 | Active |

### Root Files (13 files, 2,181 lines)

| File | Lines | Purpose |
|---|---|---|
| README.md | 109 | Repository home |
| PROJECT_CHARTER.md | 287 | Project charter |
| PROJECT_STATUS.md | 79 | Status dashboard |
| BACKLOG.md | 128 | Sprint tracking |
| CHANGELOG.md | 88 | Release notes |
| SESSION_REPORT.md | 94 | Session journal |
| ROADMAP.md | 70 | Roadmap |
| CONTRIBUTING.md | 40 | Contribution guide |
| SOURCES.md | 19 | Source index |
| HERMES_OPERATING_PROCEDURE.md | 169 | Agent workflow |
| FRAMEWORK_REVIEW.md | 380 | Framework audit |
| FRAMEWORK_FREEZE_RECOMMENDATION.md | 120 | Freeze recommendation |
| RELEASE_PLAN_0.3.md | 598 | Administration release plan |

---

## AI Layer Statistics (from merged content)

### Framework Core

| Document | Lines | Purpose |
|---|---|---|
| MASTER_PROJECT_PROMPT.md | 187 | Permanent operating instructions |
| OPERATING_PROCEDURE.md | 55 | Task startup sequence |
| PROJECT_CHARTER.md | 52 | Project vision |
| PROJECT_MEMORY.md | 48 | Memory management |
| PROJECT_LIFECYCLE.md | 60 | Phase definitions |
| GITHUB_WORKFLOW.md | 137 | GitHub process |
| RELEASE_PROCESS.md | 67 | Release criteria |
| DOCUMENTATION_STANDARDS.md | 134 | Writing standards |
| WRITING_STANDARDS.md | 93 | Tone and audience |
| AI_STANDARDS.md | 102 | AI optimization |
| QUALITY_STANDARDS.md | 161 | Quality metrics |
| REVIEW_CHECKLIST.md | 78 | PR checklist |
| DECISION_FRAMEWORK.md | 87 | Decision rules |
| PROMPT_LIBRARY.md | 143 | Example prompts |

### ADRs

| ADR | Title |
|---|---|
| ADR-0001 | Documentation Structure |
| ADR-0002 | Article Format |
| ADR-0003 | Cross-Link Strategy |
| ADR-0004 | Content Lifecycle |
| ADR-0005 | AI Collaboration Model |

---

## Integration Statistics

| Integration | Status on main |
|---|---|
| Pacejet Learning Path | Not on main (branch release/2.1-pacejet-intelligence) |
| Pacejet Scenario Library | Not on main (branch release/2.3-2.4) |
| Other integrations | Not documented |

---

## Validation Statistics

| Component | Status on main |
|---|---|
| Validation framework | Not on main (branch release/4.0) |
| Consultant Scorecard | Not on main |
| Benchmark Catalog | Not on main |
| Gold Standards | Not on main |

---

## Internal Link Verification

### Real Broken Links (require fixes)

| Link | From | Issue |
|---|---|---|
| `../inventory/overview.md` | `docs/README.md` | Path resolves to root, not `docs/inventory/` |
| `../inventory/inventory-transfers.md` | `docs/README.md` | Same path resolution issue |
| `../saved-searches/overview.md` | `docs/README.md` | Same path resolution issue |
| `../saved-searches/creating-saved-searches.md` | `docs/README.md` | Same path resolution issue |
| `../suitescript/overview.md` | `docs/README.md` | Same path resolution issue |
| `../suitetalk/rest-overview.md` | `docs/README.md` | Same path resolution issue |
| `../inventory/overview.md` | `knowledge-engine/AI_STANDARDS.md` | Path from knowledge-engine/ resolves incorrectly |
| `../inventory/inventory-transfers.md` | `knowledge-engine/AI_STANDARDS.md` | Same path resolution issue |
| `../saved-searches/overview.md` | `knowledge-engine/DOCUMENTATION_STANDARDS.md` | Path from knowledge-engine/ |
| `../../knowledge-engine/MASTER_PROJECT_PROMPT.md` | `knowledge-engine/DOCUMENTATION_STANDARDS.md` | Path from knowledge-engine/ |
| `../../LICENSE.md` | `knowledge-engine/DOCUMENTATION_STANDARDS.md` | LICENSE.md does not exist |
| `../LICENSE.md` | `docs/README.md` | LICENSE.md does not exist |
| `LICENSE.md` | `PROJECT_CHARTER.md` | LICENSE.md does not exist |
| `navigation.md` | `knowledge-engine/DOCUMENTATION_STANDARDS.md` | References file without path |

### Acceptable Broken Links (template placeholders)

| Link | From |
|---|---|
| `../path/article.md` | FRAMEWORK_REVIEW.md, ARTICLE_TEMPLATE.md, FAQ_TEMPLATE.md, TROUBLESHOOTING_TEMPLATE.md |
| `../module/article.md` | ADR-0003 |

---

## Orphaned Documents

Files not referenced by any other `.md` file in the repository:

| File | Notes |
|---|---|
| `.github/ISSUE_TEMPLATE/bug-report.md` | GitHub templates — expected to be unreferenced |
| `.github/ISSUE_TEMPLATE/documentation-task.md` | GitHub templates — expected to be unreferenced |
| `.github/pull_request_template.md` | GitHub templates — expected to be unreferenced |
| `sources/oracle-source-index.md` | Source tracking — expected to be unreferenced |
| `RELEASE_PLAN_0.3.md` | Planning artifact |
| `knowledge-engine/decisions/ADR-0001.md` through `ADR-0005.md` | ADRs — expected to be unreferenced from Markdown |

---

## Duplicate Concepts

| Concept | Duplicates | Recommendation |
|---|---|---|
| Project Charter | `PROJECT_CHARTER.md` (root) + `knowledge-engine/PROJECT_CHARTER.md` | Consolidate into one |
| Contribution Guide | `CONTRIBUTING.md` (root) + `governance/contribution-guide.md` | Consolidate into root |
| AI Standards | `governance/AI_GUIDELINES.md` (46 lines) + `knowledge-engine/AI_STANDARDS.md` (102 lines) | Consolidate into knowledge-engine |
| Writing Standards | `governance/WRITING_GUIDELINES.md` (30 lines) + `knowledge-engine/WRITING_STANDARDS.md` (93 lines) | Consolidate into knowledge-engine |
| Review Process | `governance/REVIEW_PROCESS.md` (22 lines) + `knowledge-engine/REVIEW_CHECKLIST.md` (78 lines) | Consolidate into knowledge-engine |

---

## Duplicate Files

| Filename | Occurrences | Location |
|---|---|---|
| `README.md` | 4 | root, docs/, docs/getting-started/, knowledge-engine/ |
| `overview.md` | 3 | docs/inventory/, docs/saved-searches/, docs/ (future) |
| `PROJECT_CHARTER.md` | 2 | root, knowledge-engine/ |

---

## Namespace Conflicts

| Namespace | Root | knowledge-engine/ | Issue |
|---|---|---|---|
| PROJECT_CHARTER | `PROJECT_CHARTER.md` | `knowledge-engine/PROJECT_CHARTER.md` | Duplicate content |
| PROJECT_STATUS | `PROJECT_STATUS.md` | — | Only root (correct) |
| REVIEW_CHECKLIST | — | `knowledge-engine/REVIEW_CHECKLIST.md` | Only knowledge-engine (correct) |

---

## Repository Health Summary

### Strengths

| Strength | Evidence |
|---|---|
| **Consistent structure** | 6-layer architecture is well-defined; documents follow established patterns |
| **Strong cross-linking patterns** | Templates and standards define how links should work |
| **Comprehensive core framework** | 14 documents covering all operational aspects |
| **ADRs document key decisions** | 5 ADRs covering structure, format, strategy |
| **Front matter adoption** | 27 files with YAML front matter; 18 with difficulty field; 24 with module field |

### Issues

| Issue | Severity | Details |
|---|---|---|
| **Broken links in docs/README.md** | High | 6 links use `../` prefix which resolves incorrectly from `docs/` directory |
| **Duplicate PROJECT_CHARTER.md** | High | Two versions of the charter — root and knowledge-engine — with overlapping content |
| **Governance vs. framework overlap** | Medium | 5 files in governance/ have corresponding (more complete) versions in knowledge-engine/ |
| **22 open PRs** | Medium | Platform content exists only on branches; main is missing ~90% of the platform |
| **No LICENSE.md** | Medium | Referenced from 3 files but does not exist |
| **kNowledge-engine/ typo directory** | Low | Empty directory with capital N exists alongside knowledge-engine/ |
| **Empty knowledge-intelligence directory** | Low | Directory exists but content is on a feature branch |
| **Orphaned planning artifact** | Low | RELEASE_PLAN_0.3.md exists in root with no references |
| **Template placeholders in links** | Low | FORM_REVIEW.md and templates use `../path/article.md` as examples — expected |

### Health Score

| Criterion | Score | Notes |
|---|---|---|
| **Structure** | 8 | Clean architecture but knowledge-engine/ duplicates governance/ |
| **Content** | 4 | Only getting-started is on main; 8 of 9 modules on branches |
| **Links** | 6 | docs/README.md has systematic path errors; template links fine |
| **Consistency** | 7 | Front matter and structure consistent; duplicates need resolution |
| **Standards** | 9 | ADRs, templates, and quality standards well-documented |
| **Maintainability** | 5 | 22 open PRs and duplicate files increase maintenance burden |

## Items Flagged for Architecture Review

1. **docs/README.md relative link errors** — all `../module/` links should be `module/` since the file is inside `docs/`
2. **Duplicate PROJECT_CHARTER.md** — two versions with overlapping scope; should be one
3. **Governance consolidation** — 5 governance/ files have corresponding knowledge-engine/ versions
4. **22 open PRs** — the platform's content is not on main; this is the single biggest architectural risk
5. **Missing LICENSE.md** — referenced in multiple files but absent
6. **kNowledge-engine/ typo** — empty directory with capital N should be removed
7. **Empty knowledge-intelligence/ directory** — exists on main without content
8. **Orphaned RELEASE_PLAN_0.3.md** — planning artifact from a previous sprint; should be moved or cleaned up

## Related Documents

- [PLATFORM_ARCHITECTURE.md](../PLATFORM_ARCHITECTURE.md) — (exists on branch, not main)
- [FRAMEWORK_REVIEW.md](FRAMEWORK_REVIEW.md) — Previous framework audit
- [FRAMEWORK_FREEZE_RECOMMENDATION.md](FRAMEWORK_FREEZE_RECOMMENDATION.md) — Freeze decision
- [PROJECT_STATUS.md](PROJECT_STATUS.md) — Current project status