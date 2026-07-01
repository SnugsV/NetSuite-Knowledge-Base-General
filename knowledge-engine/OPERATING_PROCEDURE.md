# Operating Procedure

## Purpose

This document defines the startup sequence Hermes must execute before every task. Following this ensures consistency and prevents missed context.

## Permanent Startup Sequence

Before EVERY task, execute this sequence:

```text
Step 1:  cd /opt/data/home/NetSuite-Knowledge-Base-General
Step 2:  git checkout main && git pull origin main
Step 3:  Read PROJECT_CHARTER.md
Step 4:  Read PROJECT_STATUS.md (current state, health, priorities)
Step 5:  Read SESSION_REPORT.md (lessons, debt, last session)
Step 6:  Read BACKLOG.md (sprints, pending work)
Step 7:  Read ROADMAP.md (long-term direction)
Step 8:  Read CHANGELOG.md (version history)
Step 9:  Read MASTER_PROJECT_PROMPT.md (if not yet read this session)
Step 10: Check GitHub for open issues and recent pull requests
Step 11: Verify repository health (structure, cross-links, tracking)
Step 12: Create feature/sprint branch from main
Step 13: Begin requested work
```

## During Work

- Follow [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) for article structure
- Follow [WRITING_STANDARDS.md](WRITING_STANDARDS.md) for tone and voice
- Follow [AI_STANDARDS.md](AI_STANDARDS.md) for AI-friendly formatting
- Consult [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md) for decision making
- Reference [PROMPT_LIBRARY.md](PROMPT_LIBRARY.md) for task patterns

## Before Committing

1. Validate all cross-links point to existing files
2. Verify YAML front matter is complete
3. Confirm Markdown formatting is correct
4. Check file is in the correct module folder
5. Update PROJECT_STATUS.md (completed tasks, health score)
6. Update SESSION_REPORT.md (changes, lessons, debt)
7. Update CHANGELOG.md (version entry)
8. Update BACKLOG.md (sprint status)

## Commit Sequence

```bash
git add -A
git status                    # Review what's being committed
git commit -m "Summary"
git push origin <branch>
```

## PR Creation

```bash
gh pr create \
  --base main \
  --head <branch> \
  --title "Title" \
  --body "Summary, files added/modified, health score"
```

## Session Completion

1. Update PROJECT_STATUS.md (completed tasks, health score, next priorities)
2. Update SESSION_REPORT.md (what changed, lessons learned, technical debt, next goals)
3. Update BACKLOG.md (sprint status changes)
4. Update CHANGELOG.md (new version entry)
5. Validate all cross-links
6. Commit and push
7. Open PR

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full project operating instructions
- [GITHUB_WORKFLOW.md](GITHUB_WORKFLOW.md) — Complete GitHub lifecycle
- [RELEASE_PROCESS.md](RELEASE_PROCESS.md) — Release management