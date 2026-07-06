# Repository Health

This document provides a repeatable scorecard for evaluating the health of the NetSuite Knowledge Base General repository.

The goal is not to create a perfect score. The goal is to make repository quality visible, measurable, and easier to improve through small maintenance sprints.

## Purpose

Repository health measures whether the repository is:

- Easy for humans to navigate
- Easy for AI systems to reason over
- Public-safe
- Maintainable over time
- Consistent with the NetSuite Intelligence Platform architecture
- Ready for future automation

This document should be updated during maintenance sprints that materially change repository structure, governance, automation, navigation, or AI-readiness.

## Current Health Summary

| Field | Value |
|---|---|
| Current Score | 8.2 / 10 |
| Last Reviewed | 2026-07-06 |
| Current Sprint | Phase 1 - Repository Health Cleanup |
| Primary Risk Area | Automation |
| Next Review Trigger | Phase 2 documentation quality audit |

## Scoring Scale

| Score | Meaning |
|---:|---|
| 10 | Excellent; clear standard exists and is consistently followed. |
| 8-9 | Strong; mostly consistent with minor gaps. |
| 6-7 | Functional; useful but uneven or incomplete. |
| 4-5 | Weak; significant maintenance or usability risk. |
| 1-3 | Poor; missing, unreliable, or not yet governed. |
| 0 | Not present. |

## Health Categories

| Category | Score | Notes |
|---|---:|---|
| Documentation Coverage | 8.5 | Broad ERP curriculum and AI framework coverage exists; some modules still need deeper examples, FAQs, and Oracle references. |
| Navigation | 8.0 | Strong top-level structure; documentation index still needs formatting and link review. |
| Cross Linking | 7.5 | Many learning paths are linked, but a repository-wide cross-link audit has not been completed. |
| Metadata | 8.0 | Canonical article expectations exist; older content may need metadata review. |
| Governance | 9.0 | Maintainer guidance, tracking file boundaries, roadmap, backlog, changelog, and status files are defined. |
| Public Safety | 9.0 | Public/private boundary is clearly documented; ongoing review is still required. |
| AI Readiness | 9.0 | Strong reasoning frameworks, AI agent guidance, and knowledge-engine architecture are present. |
| Release Hygiene | 8.5 | Changelog and release history exist; unreleased section should stay current during maintenance work. |
| Project Tracking | 8.0 | Tracking files are being realigned and have clearer responsibilities. |
| Automation | 2.0 | No CI, Markdown linting, link checking, metadata validation, or health dashboard automation is configured yet. |

## Overall Score

**8.2 / 10**

The repository is structurally strong and already functions as more than a basic documentation library. The biggest gap is automation. The next most important gaps are documentation index cleanup, cross-link review, metadata consistency, and routine article quality scoring.

## Maintenance Sprint Review Checklist

Use this checklist when updating the score:

- [ ] Did repository structure change?
- [ ] Did navigation improve or degrade?
- [ ] Were new documents added to the correct index?
- [ ] Were tracking documents kept in their proper lanes?
- [ ] Did the change introduce company-specific or private operational details?
- [ ] Were stale references, broken links, or outdated status notes found?
- [ ] Did the work improve AI readability or reasoning quality?
- [ ] Did the work add or improve automation?
- [ ] Does the score need to change?

## Category Definitions

### Documentation Coverage

Measures whether the repository covers the major NetSuite education areas it claims to cover.

Examples:

- ERP learning paths
- NetSuite module explanations
- Troubleshooting guidance
- Implementation guidance
- AI reasoning frameworks
- FAQ and example coverage

### Navigation

Measures whether readers and AI systems can find the right content quickly.

Examples:

- Top-level README clarity
- Documentation index quality
- Module index consistency
- Folder naming consistency
- Learning path discoverability

### Cross Linking

Measures whether related articles, guides, frameworks, and templates connect to one another.

Examples:

- Related articles sections
- Module-to-framework links
- Learning path next-step links
- Governance file references

### Metadata

Measures whether content includes enough structured information for review, maintenance, and AI use.

Examples:

- YAML front matter
- Difficulty level
- Estimated time
- Last reviewed date
- Tags
- Public-safe status
- Related content

### Governance

Measures whether the repository has clear operating rules.

Examples:

- Maintainer guidance
- Project status
- Roadmap
- Backlog
- Changelog
- Session report
- Review process
- Public/private rules

### Public Safety

Measures whether content is appropriate for a public repository.

Examples:

- No company-specific SOPs
- No customer/vendor details
- No private screenshots
- No proprietary manufacturing or pricing logic
- No internal AI prompts
- No private saved searches, custom fields, workflows, or scripts

### AI Readiness

Measures whether content is structured so AI systems can reason over it accurately.

Examples:

- Clear headings
- Explicit definitions
- Step-by-step reasoning
- Decision frameworks
- Troubleshooting patterns
- Context requirements
- Validation methods

### Release Hygiene

Measures whether changes are tracked clearly over time.

Examples:

- Changelog accuracy
- Version order
- Release naming
- Unreleased section quality
- Clear distinction between release history and active work

### Project Tracking

Measures whether status, roadmap, backlog, changelog, and session reporting remain aligned without duplicating responsibilities.

Examples:

- `PROJECT_STATUS.md` describes the current state
- `ROADMAP.md` describes future direction
- `BACKLOG.md` tracks actionable work
- `CHANGELOG.md` records release history
- `SESSION_REPORT.md` records maintenance activity

### Automation

Measures whether repository quality checks are automated.

Examples:

- Markdown linting
- Link checking
- Metadata validation
- GitHub Actions
- Automated health dashboard
- Release automation

## Current Improvement Priorities

1. Add basic Markdown linting.
2. Add repository link checking.
3. Repair documentation index formatting and links.
4. Audit article metadata consistency.
5. Add `KNOWN_GAPS.md` to separate incomplete work from current status.
6. Consider a generated repository health dashboard after scoring stabilizes.

## Update Procedure

When updating this file:

1. Review recent commits and changed files.
2. Check whether the current score still reflects reality.
3. Update category scores only when evidence supports the change.
4. Add notes that explain the reason for score changes.
5. Keep subjective scoring conservative.
6. Update `PROJECT_STATUS.md` if the overall repository health score changes.
7. Update `CHANGELOG.md` if the scorecard itself materially changes.

## Public Safety Reminder

Repository health is not only about completeness. A complete public repository that exposes private company operations is unhealthy.

Use the public/private rule from `MAINTAINER.md` before adding examples, screenshots, formulas, workflows, scripts, or company-specific process guidance.
