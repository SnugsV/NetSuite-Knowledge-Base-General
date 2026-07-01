# Quality Standards

## Purpose

Define measurable quality standards for all repository content. Quality is scored on 7 criteria, each rated 1-10.

## Quality Criteria

### 1. Structure (Weight: High)

Measures how well the repository organizes content.

| Score | Criteria |
|---|---|
| 10 | Perfect modular organization, no orphaned files, all content discoverable |
| 8-9 | Clean multi-module structure, minor improvements possible |
| 6-7 | Adequate structure, some misplaced files or redundant folders |
| 4-5 | Disorganized, multiple issues |
| 1-3 | No clear structure |

**Target: 10**

### 2. Governance (Weight: High)

Measures completeness and quality of governance documentation.

| Score | Criteria |
|---|---|
| 10 | All governance documents exist, consolidated, no overlap |
| 8-9 | Complete set, minor overlap or consolidation needed |
| 6-7 | Core documents exist, gaps in standards |
| 4-5 | Some governance, significant gaps |
| 1-3 | No governance |

**Target: 9**

### 3. Templates (Weight: Medium)

Measures quality and usability of templates.

| Score | Criteria |
|---|---|
| 10 | Single unified template, used consistently across all articles |
| 8-9 | Templates exist, minor inconsistencies |
| 6-7 | Multiple templates with overlap |
| 4-5 | Templates exist but outdated or inconsistently used |
| 1-3 | No templates |

**Target: 9**

### 4. Content (Weight: High)

Measures depth, breadth, and quality of documentation articles.

| Score | Criteria |
|---|---|
| 10 | All modules have Beginner, Intermediate, and Advanced content |
| 8-9 | Most modules have substantial content at multiple levels |
| 6-7 | Core modules have content, some modules empty |
| 4-5 | Few modules have content, mostly stubs |
| 1-3 | Minimal or no content |

**Target: 9 (Phase 3)**

### 5. Project Tracking (Weight: Medium)

Measures quality of project management documentation.

| Score | Criteria |
|---|---|
| 10 | All tracking files current, linked to GitHub issues, health score tracked |
| 8-9 | All tracking files present and current |
| 6-7 | Tracking files present but not always updated |
| 4-5 | Some tracking exists, often outdated |
| 1-3 | No project tracking |

**Target: 10**

### 6. Automation (Weight: Low)

Measures CI/CD, linting, and automation.

| Score | Criteria |
|---|---|
| 10 | Full CI/CD with linting, link checking, auto-deployment |
| 8-9 | Some automation (lint on PR, basic CI) |
| 6-7 | Minimal automation |
| 4-5 | Inconsistent or broken automation |
| 1-3 | No automation |

**Target: 8 (Phase 3)**

### 7. Readability (Weight: High)

Measures how readable content is for humans and AI systems.

| Score | Criteria |
|---|---|
| 10 | Perfect front matter, consistent structure, strong cross-linking, all articles follow standards |
| 8-9 | Consistent Markdown, good cross-linking, minor inconsistencies |
| 6-7 | Readable but inconsistent structure or sparse cross-links |
| 4-5 | Difficult to read, poor structure |
| 1-3 | Unreadable or broken |

**Target: 10**

## Scoring Methodology

Overall health score = average of all 7 criteria scores, rounded to 0.5.

Example:
- Structure: 9
- Governance: 8
- Templates: 8
- Content: 6.5
- Project Tracking: 8.5
- Automation: 2
- Readability: 9.5
- **Health Score: (9+8+8+6.5+8.5+2+9.5) / 7 = 51.5 / 7 = 7.4 → 7.5**

## Health Score Targets by Phase

| Phase | Target | Notes |
|---|---|---|
| Foundation (Phase 0) | 7.5 | Baseline quality established |
| Core Content (Phase 1) | 8.0 | Content and readability improve |
| Depth (Phase 2) | 8.5 | Cross-linking and governance improve |
| Community (Phase 3) | 9.0 | Automation and polish added |
| Maintenance (Phase 4) | 9.0+ | Continuous improvement |

## Cross-Link Quality

Measured separately as a health indicator:

- **Excellent**: Every article has 3-5+ related article links, no dead links
- **Good**: Most articles have links, some gaps, no dead links
- **Fair**: Some articles have links, some dead links
- **Poor**: Few or no cross-links, multiple dead links

## AI Readability

Measured by:

- **Front matter completeness** — Are all required fields present?
- **Section consistency** — Do articles follow the standard structure?
- **Quick summary quality** — Does the summary answer the key questions?
- **Cross-link density** — Are articles connected to each other?

## Maintainability

Measured by:

- **Consistency** — Are articles in the same module structured similarly?
- **Overlap** — Do multiple articles cover the same topic?
- **Outdated content** — Are there articles with deprecated information?
- **Orphaned content** — Are there files not linked from any other file?

## Related Documents

- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review checklist
- [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) — Article standards
- [AI_STANDARDS.md](AI_STANDARDS.md) — AI optimization