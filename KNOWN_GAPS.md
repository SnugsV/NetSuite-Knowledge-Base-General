# Known Gaps

Use this file to track missing, stale, weak, or incomplete areas without overstating current repository status.

## Current Gaps

- Link checking, Markdown linting, and metadata validation are not automated.
- Some guidance files may still overlap with `AGENTS.md` and should be reviewed during future maintenance.
- Public docs need periodic audits to ensure private-repository guidance stays generic and avoids named company examples.
- `knowledge-engine/AI_AGENT_USAGE_ADDENDUM.md` is referenced in cleanup notes but does not currently exist on `main`; confirm whether it should be added, restored, or removed from references.
- Template and framework-review files intentionally include example links such as `../path/article.md`; link validation should ignore or specially handle example links.
- Remaining documentation links need a dedicated pass, especially older inventory related-article links and references to modules that do not yet exist, such as warehouse, quality, and warranty.
- Some historical review/planning files still mention old PR numbers or superseded merge plans; keep them as historical notes or clearly mark them as archived.
- Changelog release ordering should be reviewed before the next tagged release.
- The new `history/` area has folder indexes but no archived vendor-update notes yet; add notes only when a public vendor update materially supersedes current guidance.
