# Review Checklist

## Purpose

This is the permanent PR review checklist. Every pull request must satisfy ALL items before opening. Use this to validate work before committing and before creating the PR.

## Repository

- [ ] Branch named correctly (`sprint/<name>`, `feature/<name>`, `fix/<name>`)
- [ ] No direct commits to `main`
- [ ] Repository structure is clean (no orphaned files or wrapper directories)
- [ ] No placeholder stub files remain in active modules
- [ ] No large binary files added
- [ ] `.gitignore` patterns respected

## Documentation

- [ ] All added/modified files follow the standard article structure
- [ ] Content is original — not copied from Oracle documentation
- [ ] Oracle sources are linked where applicable
- [ ] File is in the correct module folder
- [ ] YAML front matter is present and complete (title, module, difficulty, estimated_time, status)
- [ ] Quick Summary is present (1-3 sentences)
- [ ] Common Mistakes section is present (even if brief)
- [ ] Difficulty matches the content depth
- [ ] No placeholder or stub content — every file has meaningful educational value

## Cross-Links

- [ ] "Related Articles" section is present at the end of each new/modified article
- [ ] Each article links to at least 3 related articles (where possible)
- [ ] All cross-links use relative paths
- [ ] All cross-linked files exist (validate with `test -f`)
- [ ] Links go to the correct path (no broken relative paths)
- [ ] Cross-links span modules, not just within the same directory

## Readability

- [ ] One H1 per article
- [ ] Headings are descriptive, not generic ("What Is NetSuite?" not "Overview")
- [ ] Paragraphs are short (3-5 sentences max)
- [ ] Acronyms are defined on first use
- [ ] Spelling and grammar checked
- [ ] Plain language used (no jargon without explanation)
- [ ] Examples are concrete and practical

## AI Quality

- [ ] Front matter is complete and parsable
- [ ] Quick Summary is self-contained (can be retrieved by RAG independently)
- [ ] Common Mistakes section addresses real user questions
- [ ] FAQ section included where applicable
- [ ] File names are descriptive

## Git Workflow

- [ ] Commits have meaningful messages
- [ ] Commit messages describe what changed and why
- [ ] No unrelated changes mixed in the same commit
- [ ] Branch contains only the intended changes

## Project Tracking

- [ ] PROJECT_STATUS.md updated (completed tasks, health score recalculated, next priorities)
- [ ] SESSION_REPORT.md updated (what changed, lessons learned, technical debt, next goals)
- [ ] BACKLOG.md updated (sprint status changed if applicable)
- [ ] CHANGELOG.md updated (new version entry with changes)

## Definition of Done

- [ ] All requested files exist and are properly formatted
- [ ] Cross-links to related content are present and valid
- [ ] Project tracking files are current
- [ ] Repository health score is recalculated and recorded
- [ ] All changes are committed to a branch
- [ ] Pull request is open for review
- [ ] No project standards are violated

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full operating instructions
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality criteria and scoring
- [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) — Article structure
- [WRITING_STANDARDS.md](WRITING_STANDARDS.md) — Tone and voice