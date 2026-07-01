# Decision Framework

## Purpose

Define how Hermes makes decisions about changes to the repository. This framework categorizes changes by risk level and specifies when to act, recommend, or request approval.

## Decision Categories

### Low-Risk Changes (Implement Without Approval)

These changes are safe to implement directly. They improve quality without affecting structure or standards.

**Examples:**
- Typo fixes, formatting corrections, broken link repairs
- Adding cross-links between existing articles
- Minor wording improvements that don't change meaning
- Removing placeholder content from empty folders
- Adding new "Related Articles" links to existing articles
- Small improvements to documentation standards documents
- Adding FAQ entries to existing articles

**Process:**
1. Identify the improvement
2. Implement it
3. Include in the current commit
4. Note it in SESSION_REPORT.md if significant

### Medium-Risk Changes (Document as Recommendation)

These changes could affect consistency or structure. Document the recommendation but do not implement without review.

**Examples:**
- Renaming folders or restructuring parts of docs/ hierarchy
- Adding new module categories
- Changing the template or metadata format
- Consolidating governance documents
- Adding new sections to the article structure
- Changing naming conventions
- Adding new file types or formats

**Process:**
1. Identify the improvement
2. Add a recommendation to SESSION_REPORT.md under "Ideas Deferred" or "Recommendations"
3. Reference the recommendation in the PR description
4. Do not implement until approved

### High-Risk Changes (Require Approval)

These changes fundamentally affect the project structure, standards, or workflow. They must be proposed and approved before implementation.

**Examples:**
- Adding CI/CD, GitHub Actions, or automation
- Adding MkDocs, GitHub Pages, or any publishing pipeline
- Changing the repository license
- Adding company-specific or proprietary content to the general repo
- Large-scale content migration or deletion
- Changing the branch or merge strategy
- Changing the review or approval process
- Adding new automated tools or integrations
- Changing the project's mission or scope

**Process:**
1. Document the proposal in an issue or SESSION_REPORT.md
2. Explain the rationale, benefits, and risks
3. Wait for approval before implementing
4. If approved, implement in a dedicated branch

## When to Ask for Clarification

Stop and ask for clarification when:

- The requested task conflicts with documented project standards
- The task is ambiguous — multiple valid approaches exist
- The task requires information not available in the repository
- Technical claims cannot be verified against authoritative sources
- The task would require copying Oracle documentation verbatim
- The task involves proprietary or licensed information

## When to Recommend Improvements

Recommend improvements when:

- You notice a pattern that could be standardized
- A process could be automated
- Content is outdated or could be improved
- A standard could be clarified
- Technical debt accumulates
- A new tool or approach would significantly improve quality

## Escalation Path

For urgent issues that block progress:

1. Document the issue in SESSION_REPORT.md under "Blockers"
2. Reference it in the PR description
3. Flag it in the PR summary as a known risk
4. The maintainer reviews and decides

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full operating instructions
- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Stopping conditions
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review checklist
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality standards