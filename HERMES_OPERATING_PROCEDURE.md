# Hermes Operating Procedure — NetSuite Knowledge Base General

## Purpose

This document defines the permanent workflow for Hermes when working on the NetSuite Knowledge Base General repository. Every task follows this procedure automatically.

## Repository

| Property | Value |
|---|---|
| URL | `https://github.com/SnugsV/NetSuite-Knowledge-Base-General.git` |
| Local path | `/opt/data/home/NetSuite-Knowledge-Base-General` |
| Branch strategy | Sprint / Feature branches from `main` |
| Protected branch | `main` — no direct commits |

## Environment

- Git user: `SnugsV <snugsv@github.com>` (per-repo config)
- GitHub CLI: `/opt/data/home/.local/bin/gh` (installed, not authenticated)
- Auth method: TBD (see Step 2 of setup)
- No sudo available — package installation not possible
- gh CLI was downloaded from GitHub releases (binary, not apt-installed)

## Git Workflow

### Branch Naming

| Pattern | Purpose |
|---|---|
| `main` | Protected — production-ready content |
| `sprint/<name>` | Planned sprint branches (e.g., `sprint/0.3-administration`) |
| `feature/<name>` | Focused additions or fixes |

### Commit Standards

- Summary line: 50 characters max, describing what changed
- Body: optional, describing why it changed
- Use present tense ("Adds X", "Fixes Y", not "Added X")
- One logical change per commit

### Pull Request Workflow

1. Create branch from `main`
2. Perform work in logical commits
3. Push branch (`git push origin <branch>`)
4. Open PR (`gh pr create` or via web)
5. Tag with appropriate labels

## Permanent Startup Sequence

Before EVERY task, Hermes must execute this sequence automatically:

```text
1. cd /opt/data/home/NetSuite-Knowledge-Base-General
2. git checkout main
3. git pull origin main
4. Verify git remote is correct (origin → GitHub)
5. Read PROJECT_CHARTER.md
6. Read PROJECT_STATUS.md
7. Read SESSION_REPORT.md
8. Read BACKLOG.md
9. Verify repository health score
10. Create feature/sprint branch
11. Begin requested work
```

### Startup Sequence Commands

```bash
# Step 1: Get latest
git checkout main
git pull origin main

# Step 2: Read project context (must read all four)
read_file PROJECT_CHARTER.md
read_file PROJECT_STATUS.md
read_file SESSION_REPORT.md
read_file BACKLOG.md

# Step 3: Create branch
git checkout -b sprint/<sprint-name>
```

## Validation Steps

Before committing, always:

1. **Markdown formatting** — Verify all markdown renders correctly
2. **Internal links** — Check that cross-references point to existing files
3. **Front matter** — Verify YAML front matter is complete
4. **Repository structure** — Confirm no files are misplaced
5. **Cross-links** — Ensure related articles section links to existing files
6. **PROJECT_STATUS.md** — Update completed tasks and health score
7. **SESSION_REPORT.md** — Log changes, lessons learned, technical debt
8. **CHANGELOG.md** — Add entry for new version
9. **BACKLOG.md** — Update sprint status

## Commit Sequence

```bash
git add -A
git status                 # Review what's being committed
git commit -m "Summary of changes"
git push origin <branch>   # Push after successful commit
```

## PR Creation (when auth is configured)

```bash
gh pr create \
  --base main \
  --head <branch> \
  --title "Sprint X.Y — Title" \
  --body "Summary of changes, files added/modified, health score"
```

## Repository Health Checks

- Verify `PROJECT_STATUS.md` has up-to-date health score
- Check that no orphaned or wrapper directories exist
- Verify no placeholder stub files remain in active modules
- Confirm cross-links are valid
- Ensure tracking files reference each other consistently

## Session Completion

At the end of every session:

1. Update `PROJECT_STATUS.md` (completed tasks, health score, next priorities)
2. Update `SESSION_REPORT.md` (what changed, lessons learned, technical debt, next goals)
3. Update `BACKLOG.md` (sprint status changes)
4. Update `CHANGELOG.md` (new version entry)
5. Validate all cross-links
6. Commit and push
7. Open PR

## Authentication Setup (One-Time)

To enable push and PR creation:

1. Generate a GitHub PAT (classic with `repo` scope, or fine-grained with content+PRs permissions)
2. Run: `gh auth login --with-token < ~/github-token`
3. Or generate SSH key: `gh auth login` (interactive, browser-based)
4. Verify: `gh auth status`

## Known Constraints

- No sudo available — cannot install packages via apt
- `gh` CLI binary manually placed at `/opt/data/home/.local/bin/gh`
- PATH must include `$HOME/.local/bin` for `gh` command (added to `.bashrc`)
- No CI/CD configured — manual review required
- No LICENSE.md — project should not go public without one
- No Markdown link checker — validation requires manual or AI review