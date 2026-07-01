# Prompt Library

## Purpose

Example prompts that demonstrate how to use the Knowledge Engineering Framework for common tasks. These prompts are intentionally short — the framework provides the context.

## Build Release

```
Read the Knowledge Engineering Framework and build Release 0.3 — Administration.

Create articles for:
- Users and roles
- Permissions
- Company preferences and setup
- Forms and custom fields
- Authentication and access
- Audit trail basics
- Feature enablement

Follow all project standards.
```

## Review Release

```
Review the current state of the Administration module.

Run through REVIEW_CHECKLIST.md.
Report issues found and recommendations.
```

## Refactor Module

```
Refactor the Inventory module to match current DOCUMENTATION_STANDARDS.md.

Check:
- Front matter completeness
- Article structure compliance
- Cross-link density
- Quick Summary quality
- Common Mistakes sections

Report what was changed and why.
```

## Create Learning Path

```
Create a "Report Consumer" learning path in docs/README.md.

Target audience: Business users who need to run reports but not configure them.
Cover:
- Accessing saved searches
- Running reports
- Exporting data
- Using dashboards
- Understanding KPIs

Link to existing articles where possible.
```

## Improve Cross-Links

```
Audit cross-links in the getting-started and inventory modules.

For each article, ensure:
- At least 3 related article links
- Links go to existing files
- Links span modules (not just within the same directory)
- Two-way linking where possible

Report which articles were modified.
```

## Audit Repository

```
Audit the entire repository against REVIEW_CHECKLIST.md.

Report:
- Files that violate standards
- Broken cross-links
- Missing front matter
- Inconsistent formatting
- Outdated content
- Repository health score

Recommend priorities for cleanup.
```

## Add New Module

```
Create a new module: CRM.

Add:
- docs/crm/README.md with module index
- First 3 articles:
  - Customer Records overview
  - Lead Management
  - Campaign Management

Create folders, structure articles, add front matter.
Update docs/README.md module index.
```

## Framework Improvement

```
Review the Knowledge Engineering Framework for gaps or improvements.

Check:
- Are all framework documents cross-linked?
- Are any standards duplicated across files?
- Is every document referenced where it should be?
- Are there gaps in the framework?

Recommend improvements via DECISION_FRAMEWORK.md guidelines.
```

## Session Wrap-Up

```
Complete the current session.

Update:
- PROJECT_STATUS.md (completed tasks, health score)
- SESSION_REPORT.md (changes, lessons, debt, next goals)
- BACKLOG.md (sprint progress)
- CHANGELOG.md (version entry)

Validate cross-links.
Commit and push.
Open PR.
```

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full operating instructions
- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Startup sequence
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review checklist