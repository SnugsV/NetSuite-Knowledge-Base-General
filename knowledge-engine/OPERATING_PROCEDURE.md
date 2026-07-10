# Operating Procedure

## Purpose

This document defines the repeatable operating procedure for repository work. It complements the root [AGENTS.md](../AGENTS.md) startup guide, which is the first-stop guide for AI-assisted maintenance.

## Startup Sequence

Before each task:

1. Start from the latest available `main` branch.
2. Read [AGENTS.md](../AGENTS.md) for public-safety rules and startup order.
3. Read [PROJECT_STATUS.md](../PROJECT_STATUS.md) for current state, health, and priorities.
4. Read [SESSION_REPORT.md](../SESSION_REPORT.md) for recent changes, lessons, and debt.
5. Read [BACKLOG.md](../BACKLOG.md) and [ROADMAP.md](../ROADMAP.md) when planning work.
6. Read [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) if deeper framework context is needed.
7. Check relevant GitHub issues, pull requests, or review threads when the task depends on them.
8. Make focused changes in a reviewable branch or commit scope.

## During Work

- Follow [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) for article structure.
- Follow [WRITING_STANDARDS.md](WRITING_STANDARDS.md) for tone and voice.
- Follow [AI_STANDARDS.md](AI_STANDARDS.md) for AI-friendly formatting.
- Consult [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md) for decision making.
- Reference [PROMPT_LIBRARY.md](PROMPT_LIBRARY.md) for task patterns.
- Keep public documentation generic and free of company-specific implementation details.

## Before Committing

1. Validate all changed cross-links point to existing files.
2. Verify YAML front matter is complete where required.
3. Confirm Markdown formatting is clean.
4. Check each file is in the correct module or governance location.
5. Update tracking files only when the change affects repository state.
6. Confirm no private SOPs, customer examples, custom fields, saved searches, workflows, SuiteScripts, screenshots, pricing, credentials, or proprietary processes were added.

## Commit Sequence

```bash
git add -A
git status
git commit -m "Summary"
git push origin <branch>
```

## PR Creation

```bash
gh pr create \
  --base main \
  --head <branch> \
  --title "Title" \
  --body "Summary, files added/modified, validation performed"
```

## Session Completion

1. Review the final diff.
2. Validate links touched by the work.
3. Update project tracking files if the repository state changed.
4. Commit and push focused changes.
5. Open or update a pull request when working in a branch-based workflow.
6. Report files changed, commits, validation performed, and follow-up work.

## Related Documents

- [AGENTS.md](../AGENTS.md) — AI-agent startup and public-safety guide
- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full project operating instructions
- [GITHUB_WORKFLOW.md](GITHUB_WORKFLOW.md) — Complete GitHub lifecycle
- [RELEASE_PROCESS.md](RELEASE_PROCESS.md) — Release management
