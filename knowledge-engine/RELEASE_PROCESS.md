# Release Process

## Purpose

Define the versioning scheme, release criteria, and release procedure for this project.

## Versioning

This project uses a simplified semantic versioning scheme:

```
vMAJOR.MINOR.PATCH
```

| Component | When to Increment | Example |
|---|---|---|
| **MAJOR** | Significant scope expansion, restructuring, or public release | v0.1 → v1.0 |
| **MINOR** | New modules, new features, framework additions | v0.2 → v0.3 |
| **PATCH** | Bug fixes, link repairs, minor updates | v0.2.0 → v0.2.1 |

### Pre-Release Suffixes

- `-alpha` — Very early, incomplete
- `-beta` — Feature-complete but not yet reviewed
- `-rc1` — Release candidate, ready for final review

## Version Tracking

- Current version is recorded in [PROJECT_STATUS.md](../PROJECT_STATUS.md)
- Version history is recorded in [CHANGELOG.md](../CHANGELOG.md)
- Releases are tracked against the [ROADMAP.md](../ROADMAP.md)

## Release Criteria

A release is ready when:

1. **All sprint tasks complete** — The sprint's planned work is done
2. **Content reviewed** — New articles are at minimum at Review status
3. **Cross-links validated** — All links point to existing files
4. **Project tracking updated** — PROJECT_STATUS, SESSION_REPORT, BACKLOG, CHANGELOG are current
5. **Health score calculated** — Repository health score is recalculated and recorded
6. **No critical issues** — No unaddressed bugs or broken content

## Release Procedure

### For Sprint Releases

1. Complete all sprint tasks
2. Run through the REVIEW_CHECKLIST.md
3. Update CHANGELOG.md with new version entry
4. Update PROJECT_STATUS.md with new version number
5. Update BACKLOG.md (mark sprint complete)
6. Update SESSION_REPORT.md with session summary
7. Validate all cross-links
8. Commit all changes
9. Push the branch
10. Open or update the PR
11. After merge, tag the release:

```bash
git tag -a v0.3.0 -m "Sprint 0.3 — Administration"
git push origin v0.3.0
```

### For Patch Releases

1. Make the fix on a branch from main
2. Update CHANGELOG.md
3. Update PROJECT_STATUS.md (patch increment)
4. Commit, push, PR, merge
5. Tag the patch release

## Release Notes

Release notes are captured in:

- **CHANGELOG.md** — Full version history with change descriptions
- **GitHub Releases** — Can be created from tags for public releases
- **Pull request descriptions** — Sprint-level summaries

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full operating instructions
- [GITHUB_WORKFLOW.md](GITHUB_WORKFLOW.md) — GitHub lifecycle
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality metrics
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review checklist