# Knowledge Engineering Framework

This directory contains the permanent AI Knowledge Engineering Framework for the NetSuite Knowledge Base General project.

## Purpose

The Knowledge Engineering Framework eliminates the need for long prompts by moving all project knowledge — standards, workflows, quality expectations, decision frameworks, and operating procedures — into version-controlled documentation.

Future prompts should be as simple as:

> "Read the Knowledge Engineering Framework and build Release X."

## Directory Contents

| File | Purpose |
|---|---|
| [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) | Permanent operating instructions — the single document future prompts reference |
| [PROJECT_CHARTER.md](PROJECT_CHARTER.md) | Project vision, mission, philosophy, and engineering mindset |
| [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) | Repository maintenance procedure for recurring work |
| [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) | Article structure, cross-linking, naming conventions |
| [WRITING_STANDARDS.md](WRITING_STANDARDS.md) | Tone, audience, teaching philosophy, plain language |
| [AI_STANDARDS.md](AI_STANDARDS.md) | AI optimization, RAG readiness, metadata, knowledge graphs |
| [PROJECT_MEMORY.md](PROJECT_MEMORY.md) | Long-term memory management and startup context |
| [PROJECT_LIFECYCLE.md](PROJECT_LIFECYCLE.md) | Project phases from foundation through maintenance |
| [GITHUB_WORKFLOW.md](GITHUB_WORKFLOW.md) | Complete GitHub lifecycle: branch → merge → release |
| [RELEASE_PROCESS.md](RELEASE_PROCESS.md) | Versioning, release criteria, tagging |
| [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) | Measurable quality metrics and scoring methodology |
| [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) | Permanent PR review checklist |
| [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md) | Decision-making rules: low/medium/high risk |
| [PROMPT_LIBRARY.md](PROMPT_LIBRARY.md) | Example prompts for common tasks |

## How to Use

1. **New AI agent** — Begin with [../AGENTS.md](../AGENTS.md), then read this README and [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md)
2. **Before each task** — Read [PROJECT_MEMORY.md](PROJECT_MEMORY.md) and follow [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md)
3. **When writing documentation** — Reference [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) and [WRITING_STANDARDS.md](WRITING_STANDARDS.md)
4. **When reviewing work** — Use [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md)
5. **When making decisions** — Consult [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md)
6. **When releasing** — Follow [RELEASE_PROCESS.md](RELEASE_PROCESS.md)

## Design Principles

- **Reusable** — Designed for any documentation project, not just this repository
- **Self-documenting** — Every file explains its purpose and how it connects
- **Cross-linked** — Framework documents reference each other
- **Minimal prompts** — The framework eliminates the need for lengthy instructions
- **Version-controlled** — All standards evolve through pull requests, not conversation