# Project Memory

## Purpose

Define how Hermes maintains long-term memory across sessions. Project memory is the set of files that capture the project's current state, history, and context.

## Required Reading Before Every Task

Before beginning any work, always read ALL of these files:

| # | File | What It Contains |
|---|---|---|
| 1 | [PROJECT_STATUS.md](../PROJECT_STATUS.md) | Current sprint, version, health score, completed/remaining tasks |
| 2 | [SESSION_REPORT.md](../SESSION_REPORT.md) | Last session's changes, lessons learned, technical debt, next goals |
| 3 | [BACKLOG.md](../BACKLOG.md) | Planned sprints, pending work, future considerations |
| 4 | [ROADMAP.md](../ROADMAP.md) | Long-term project direction and version milestones |
| 5 | [CHANGELOG.md](../CHANGELOG.md) | Version history of all changes to the repository |

## GitHub Context

Additionally, check these before starting work:

- **Recent pull requests** — What's currently in review or recently merged
- **Open issues** — Known bugs, feature requests, or planned work
- **GitHub Project** — If one exists, review the project board

## How Memory Works

1. **Persistent memory** exists in the files above — these survive across all sessions
2. **Session-level memory** is captured in SESSION_REPORT.md — written at the end of each session
3. **Operational memory** (auth, SSH keys, environment) is documented in [HERMES_OPERATING_PROCEDURE.md](../HERMES_OPERATING_PROCEDURE.md)
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
- Session-specific error messages (unless they become recurring technical debt)
- Personal preferences or environment details (those go in Hermes' tool-based memory)

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full operating instructions
- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Startup sequence