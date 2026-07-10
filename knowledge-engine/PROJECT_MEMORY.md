# Project Memory

## Purpose

Define how AI agents and maintainers preserve useful project context across sessions. Project memory is the set of files that capture the repository's current state, history, and operating context.

## Required Reading Before Every Task

Before beginning substantial work, review the relevant files below:

| # | File | What It Contains |
|---|---|---|
| 1 | [../AGENTS.md](../AGENTS.md) | First-stop AI-agent startup guidance and public-safety rules |
| 2 | [PROJECT_STATUS.md](../PROJECT_STATUS.md) | Current sprint, version, health score, completed/remaining tasks |
| 3 | [SESSION_REPORT.md](../SESSION_REPORT.md) | Last session's changes, lessons learned, technical debt, next goals |
| 4 | [BACKLOG.md](../BACKLOG.md) | Planned sprints, pending work, future considerations |
| 5 | [ROADMAP.md](../ROADMAP.md) | Long-term project direction and version milestones |
| 6 | [CHANGELOG.md](../CHANGELOG.md) | Version history of all changes to the repository |

## GitHub Context

Additionally, check these before starting work when relevant:

- **Recent pull requests** — What's currently in review or recently merged
- **Open issues** — Known bugs, feature requests, or planned work
- **GitHub Project** — If one exists, review the project board

## How Memory Works

1. **Persistent memory** exists in the files above — these survive across all sessions
2. **Session-level memory** is captured in SESSION_REPORT.md — written at the end of each session
3. **Operational details** such as local paths, tokens, credentials, SSH keys, and machine-specific setup should not be stored in this public repository
4. **Framework knowledge** lives in the `knowledge-engine/` directory — permanent and reusable

## What to Update at Session End

| File | Update |
|---|---|
| PROJECT_STATUS.md | Completed tasks, health score, next priorities |
| SESSION_REPORT.md | What changed, lessons learned, technical debt, ideas deferred, next goals |
| BACKLOG.md | Sprint status (planned → in progress → complete) |
| CHANGELOG.md | New version entry with changes |

## What Not to Save to Memory

- Raw terminal output or command results
- Temporary file listings or directory trees
- Session-specific error messages unless they become recurring technical debt
- Personal preferences, local paths, credentials, tokens, SSH keys, or machine-specific setup details

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full operating instructions
- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Startup sequence
