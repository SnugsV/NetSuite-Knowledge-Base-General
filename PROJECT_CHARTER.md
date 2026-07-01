# Project Charter

## Mission

The NetSuite Knowledge Base General project creates a community-driven, AI-friendly, and maintainable reference library for NetSuite administrators, developers, consultants, business users, and students.

This project complements Oracle's official documentation by providing original explanations, implementation guidance, best practices, troubleshooting notes, and cross-linked content optimized for both human readers and AI assistants. It does not replace Oracle's official documentation.

## Documentation Philosophy

1. **Original Content** — Write summaries, explanations, and guides using original language. Do not copy, mirror, or republish Oracle documentation.
2. **Source-Linked** — Every article that references official Oracle material must include a link to the authoritative source. Prefer linking to the Help Center, SuiteAnswers, or the REST API Browser.
3. **Topic-Focused** — Keep each file focused on one topic. If a section grows too long, split it into its own article.
4. **AI-Friendly** — Use consistent front matter, clear headings, quick summaries, and structured sections so both humans and AI systems can retrieve information quickly.
5. **Version-Controlled** — All changes are tracked through Git. Use branches, pull requests, and descriptive commit messages.

## Quality Standards

- Every article must include a quick summary, difficulty level, and Oracle reference links.
- Articles must be reviewed before moving from Draft to Approved status.
- Metadata front matter must be present and complete before marking a document as Reviewed.
- Placeholder or stub articles (single-line READMEs in folders) are acceptable for structure but should be replaced with real content before the version 1.0 release.

## Git Workflow

- The `main` branch is protected. All work must be done on feature or sprint branches.
- Branch naming: `sprint/<name>` for planned sprints, `feature/<name>` for focused additions.
- Pull requests require review before merging.
- Commit messages should describe what changed and why.
- Squash merges are preferred for sprint branches.

## AI-Friendly Documentation Standards

AI assistants may be used to research, write, edit, and review documentation. When working with AI:

- Provide clear context about the project, target audience, and module.
- Verify all technical claims against official Oracle documentation.
- Ensure all Oracle references are accurate links.
- Review AI-generated content for consistency with the project style guide.
- Treat AI as a tool, not a replacement for human review of technical accuracy.

## Oracle Documentation Policy

Oracle NetSuite's official documentation is the authoritative source for technical accuracy. This project:

- **References** Oracle documentation but does not reproduce it.
- **Links** to official sources for deeper reading.
- **Summarizes** concepts in original language for learning and quick reference.
- **Does not** scrape, republish, or mirror Oracle documentation.

## Architectural Change Policy

Major architectural changes — including restructuring the docs/ folder hierarchy, adding new doc section categories, changing the template system, adding automation (CI/CD, MkDocs, GitHub Pages), or introducing new content types — must be:

1. Documented in a proposal or issue
2. Reviewed before implementation
3. Approved by the project maintainer

This prevents fragmentation and keeps the knowledge base consistent over time.

## Target Audience

- NetSuite administrators
- SuiteScript developers
- Consultants and implementation teams
- Finance, accounting, inventory, sales, and operations teams
- Business owners evaluating or operating NetSuite
- AI assistants and knowledge-base systems

## Licensing

Content in this repository is available for community use. See [LICENSE.md](LICENSE.md) for details.