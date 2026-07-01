# GitHub Workflow

## Purpose

Define the complete GitHub lifecycle for this project — from checkout through release.

## Lifecycle Diagram

```
Checkout → Branch → Develop → Validate → Commit → Push → PR → Review → Merge → Release
```

## Step 1: Checkout

```bash
git checkout main
git pull origin main
```

Always start from main and get the latest.

## Step 2: Create Branch

Use one of these patterns:

| Pattern | When to Use |
|---|---|
| `sprint/<name>` | Planned sprint work |
| `feature/<name>` | Focused features or additions |
| `fix/<name>` | Bug fixes and corrections |

```bash
git checkout -b sprint/0.3-administration
```

## Step 3: Develop

Create and edit files according to project standards.

- Follow [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) for structure
- Follow [WRITING_STANDARDS.md](WRITING_STANDARDS.md) for tone
- Follow [AI_STANDARDS.md](AI_STANDARDS.md) for AI readiness
- Use logical commits — commit after completing each logical piece of work

## Step 4: Validate

Before staging, run through the [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md):

- Cross-links valid
- Front matter complete
- Markdown formatting correct
- Project tracking files updated

## Step 5: Commit

```bash
git add -A
git status         # Review before committing
git commit -m "Summary of changes"
```

Commit message format:

```
Short summary (50 chars max)

Optional longer description explaining motivation.
```

## Step 6: Push

```bash
git push origin <branch-name>
```

First push creates the branch on GitHub. Subsequent pushes update it.

## Step 7: Pull Request

```bash
gh pr create \
  --base main \
  --head <branch-name> \
  --title "Sprint X.Y — Title" \
  --body "Summary of changes, files added/modified, health score"
```

PR body should include:
- Summary of changes
- Files added
- Files modified
- Files removed
- Repository health score
- Known risks

## Step 8: Review

PRs are reviewed against the [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md). The reviewer checks:

- Content quality and originality
- Technical accuracy
- Cross-link validity
- Front matter completeness
- Project tracking updates

## Step 9: Merge

After approval, squash merge into main:

```bash
git checkout main
git pull origin main
git merge --squash <branch-name>
git commit -m "Sprint X.Y — Title"
git push origin main
```

Alternatively, merge via GitHub's squash merge button in the PR.

## Step 10: Release

Follow [RELEASE_PROCESS.md](RELEASE_PROCESS.md) for versioning and tagging.

## Branch Cleanup

After merging:

```bash
git branch -d <branch-name>          # Delete local branch
git push origin --delete <branch-name>  # Delete remote branch
```

## Related Documents

- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Startup sequence
- [RELEASE_PROCESS.md](RELEASE_PROCESS.md) — Release management
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review checklist
- [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md) — Decision-making rules