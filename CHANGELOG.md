# Changelog

All notable changes to this repository will be documented here.

## [0.2.1] - 2026-07-01 — Knowledge Engineering Framework

### Added

- Complete AI Knowledge Engineering Framework (14 documents in `knowledge-engine/`):
  - MASTER_PROJECT_PROMPT.md — Permanent operating instructions for all future work
  - PROJECT_CHARTER.md — Project vision and engineering mindset
  - OPERATING_PROCEDURE.md — Startup sequence for every task
  - DOCUMENTATION_STANDARDS.md — Article structure, cross-linking, naming conventions
  - WRITING_STANDARDS.md — Tone, audience, teaching philosophy
  - AI_STANDARDS.md — AI/LLM/RAG optimization guidelines
  - PROJECT_MEMORY.md — Long-term memory management
  - PROJECT_LIFECYCLE.md — Project phases from foundation through maintenance
  - GITHUB_WORKFLOW.md — Complete GitHub lifecycle documentation
  - RELEASE_PROCESS.md — Versioning and release criteria
  - QUALITY_STANDARDS.md — Measurable quality metrics and scoring
  - REVIEW_CHECKLIST.md — Permanent PR review checklist
  - DECISION_FRAMEWORK.md — Decision-making rules for low/medium/high risk
  - PROMPT_LIBRARY.md — Example prompts for common tasks

### Changed

- Updated README.md to reference Knowledge Engineering Framework
- Updated repository structure diagram in README
- Updated PROJECT_STATUS.md with framework completion

## [2.2.0] - 2026-07-01 — Repository Navigation & Architecture Cleanup

### Added

- PLATFORM_ARCHITECTURE.md — six-layer architecture overview for new contributors and AI agents

### Changed

- PROJECT_STATUS.md — rewritten to reflect v2.2.0 state: 8 complete ERP modules, 6 AI framework layers, Pacejet integration
- docs/README.md — fixed module statuses (18 entries updated), corrected relative links, added administrator and operational learning paths
- BACKLOG.md — added Release 2.2 entry, marked Sprint 0.4 as complete
- SESSION_REPORT.md — added license recommendation and PR #18/#19 resolution

### License

- License recommendation documented (MIT or CC-BY-4.0). No license file added — requires approval.

### PR Resolution

- PR #18/#19: Determined that PR #19 (Pacejet Intelligence Pack implementation) fully supersedes PR #18 (planning). Recommendation: close PR #18 after PR #19 merge.

## [0.2.2] - 2026-07-01 — Governance & Framework Finalization

### Added

- ADR-0001 through ADR-0005 in knowledge-engine/decisions/:
  - Documentation Structure, Article Format, Cross-Link Strategy, Content Lifecycle, AI Collaboration Model
- FRAMEWORK_REVIEW.md — Comprehensive 8-phase review of all framework documents
- FRAMEWORK_FREEZE_RECOMMENDATION.md — Conditional freeze recommendation with blocker resolution path

### Changed

- Finalized ARTICLE_TEMPLATE.md — standardized canonical template matching DOCUMENTATION_STANDARDS.md
- Deprecated document-template.md — content merged into canonical template

### Frozen

The following framework documents are now considered frozen (change requires ADR):
DOCUMENTATION_STANDARDS.md, WRITING_STANDARDS.md, AI_STANDARDS.md, QUALITY_STANDARDS.md,
PROJECT_MEMORY.md, PROJECT_LIFECYCLE.md, DECISION_FRAMEWORK.md

## [0.2.0] - 2026-07-01 — Foundation Refinement & Getting Started

### Added

- Expanded PROJECT_CHARTER.md with comprehensive project standards
- docs/README.md — documentation homepage with learning paths
- 11 new getting-started articles (complete beginner learning path)
- Cross-links across all getting-started articles
- GitHub auth configured (SSH + gh CLI)
- HERMES_OPERATING_PROCEDURE.md

### Changed

- Upgraded PROJECT_STATUS.md to dashboard format
- Enhanced SESSION_REPORT.md with lessons learned, technical debt
- Updated what-is-netsuite.md with improved cross-links

### Removed

- Placeholder stub files from administration, release-notes, basics

## [0.1.1] - 2026-07-01 — Foundation Cleanup

### Added
- Project charter, status, backlog, session report, .gitignore, GitHub templates

### Changed
- Flattened nested wrapper directories
- Merged governance and template files from both wrapper levels

### Removed
- Empty wrapper directories

## [0.1.0] - Foundation

### Added
- Initial repository structure, README, Roadmap, Contribution guide
- Governance folder, templates, source tracking file
- First content articles