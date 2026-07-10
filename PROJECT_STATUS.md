# Project Status

## Dashboard

| Field | Value |
|---|---|
| **Current Version** | 4.0.0 |
| **Current Milestone** | Cross-Vendor Advanced Maintenance |
| **Current Sprint** | Link Validation and Quick Reference Planning |
| **Overall Completion** | Broad ERP curriculum, AI framework, advanced troubleshooting foundations, SPS bulk EDI workflows, cross-vendor support guidance, and self-service support checks are established |
| **Repository Health** | 8.8 / 10 |
| **Open Issues** | Review in GitHub before each maintenance session |
| **Known Risks** | No CI/CD/link checking; tracking files need routine maintenance; documentation links need repeatable validation |

## Completed Work

### Foundation and Governance
- [x] Initial repository structure, README, Roadmap
- [x] Contribution guide, style guide, writing guidelines, review process, AI guidelines
- [x] Article, FAQ, and troubleshooting templates
- [x] Source tracking files
- [x] Project charter, status, backlog, session report, changelog
- [x] GitHub workflow documentation
- [x] Knowledge Engineering Framework in `knowledge-engine/`
- [x] CC BY 4.0 license in `LICENSE.md`
- [x] Maintainer operations handbook in `MAINTAINER.md`
- [x] Repository health scorecard in `REPOSITORY_HEALTH.md`
- [x] Known gaps tracker in `KNOWN_GAPS.md`
- [x] AI-agent startup guide in `AGENTS.md`
- [x] Public-safe contribution and review guidance across core governance files

### ERP Curriculum
- [x] Getting Started learning path
- [x] Administration learning path
- [x] Saved Searches learning path
- [x] Inventory and operations learning path
- [x] Purchasing learning path
- [x] Sales learning path
- [x] Manufacturing learning path
- [x] Accounting learning path

### Advanced NetSuite Content
- [x] Advanced troubleshooting module index
- [x] NetSuite error diagnostic framework
- [x] Screenshot and error-message triage guidance
- [x] SuiteScript and workflow error triage guidance
- [x] Integration error triage guidance
- [x] Customer credit automation pattern
- [x] Advanced saved search diagnostics
- [x] Permissions and role-difference diagnostics
- [x] SuiteFlow automation patterns
- [x] SuiteTalk REST and SOAP troubleshooting
- [x] Transaction lifecycle troubleshooting
- [x] SuiteScript troubleshooting deep dive
- [x] SuiteAnalytics and reporting troubleshooting

### Advanced Avalara Content
- [x] Advanced Avalara troubleshooting index
- [x] Tax calculation troubleshooting
- [x] Address validation and geolocation edge cases
- [x] NetSuite transaction tax flow with Avalara
- [x] Tax codes and item classification deep dive
- [x] Exemption certificate troubleshooting
- [x] Nexus, jurisdiction, and taxability diagnostics
- [x] Connector sync failure and log review
- [x] Returns and filing readiness troubleshooting

### Advanced Pacejet Content
- [x] Advanced Pacejet troubleshooting index
- [x] Shipping rate and carrier-service troubleshooting
- [x] Packing, weights, dimensions, and package-building diagnostics
- [x] Label generation and carrier error troubleshooting
- [x] NetSuite fulfillment and shipment status flow diagnostics
- [x] Address validation and residential/commercial shipping diagnostics
- [x] Tracking, void, reprint, and post-shipment issue guidance

### Advanced SPS Commerce Content
- [x] SPS Commerce integration module index
- [x] Advanced SPS Commerce troubleshooting index
- [x] EDI document lifecycle troubleshooting
- [x] Purchase order acknowledgment and change-order diagnostics
- [x] Bulk purchase order acknowledgment workflow
- [x] ASN and shipment notice troubleshooting
- [x] Bulk ASN workflow
- [x] Invoice/810 mismatch diagnostics
- [x] NetSuite and SPS data-mapping diagnostics
- [x] Connector or portal error triage guidance

### Cross-Vendor Support
- [x] Cross-vendor support index
- [x] NetSuite-centered integration map
- [x] Self-service before escalation guide
- [x] Cross-vendor integration incident intake checklist
- [x] Release and update review workflow
- [x] Screenshot and log redaction checklist

### AI Knowledge Platform Layers
- [x] Support Intelligence Framework
- [x] Customer Context Intelligence Framework
- [x] AI Skill framework and saved search skill
- [x] Solution Architect framework
- [x] Customer Metadata Framework
- [x] Pacejet Intelligence Pack
- [x] Knowledge Intelligence Pipeline
- [x] Agent Runtime Framework
- [x] Experience Intelligence Framework
- [x] AI Validation & Benchmark Framework

## Active Maintenance Work

Phase 1 cleanup is mostly complete, with link validation and release-order review remaining:

- [x] Create maintenance branch for cleanup work
- [x] Update stale project status language
- [x] Confirm license choice and add `LICENSE.md`
- [x] Add maintainer governance guide
- [x] Add repository health scorecard
- [x] Add `KNOWN_GAPS.md`
- [x] Add and link `AGENTS.md`
- [x] Remove named company example from public/private overlay guidance
- [x] Generalize stale AI-agent and platform guidance
- [x] Refresh documentation index guidance
- [x] Refresh session report for the current cleanup pass
- [x] Align roadmap with completed releases and future direction
- [x] Review changelog consistency for current cleanup items
- [x] Add public-safe guidance to core governance writing and review files
- [x] Generalize remaining named-company references found in Avalara and knowledge-acquisition docs
- [x] Deprecate environment-specific Hermes procedure and fixed visible Pacejet link issues
- [ ] Review changelog release ordering before the next tag
- [ ] Validate remaining documentation links with a repeatable tool

## Known Issues

- No CI/CD, Markdown linting, link checking, or metadata validation is configured.
- Some historical tracking documents may drift without periodic review.
- Some governance/template documents may still overlap and should be consolidated or clearly deprecated over time.
- Documentation links still need automated or repo-wide validation.
- Public/private boundary language should be audited periodically as new examples are added.

## Next Milestone

**Cross-Vendor Advanced Maintenance**

Harden the support layer with link validation, quick-reference decision paths, and continued public-safety review.

## Upcoming Priorities

1. Validate remaining documentation links with a repeatable tool.
2. Add frontline quick-reference decision tree for common NetSuite/Avalara/Pacejet/SPS symptoms.
3. Review changelog release ordering before the next tag.
4. Continue periodic public-safety audits.

## Recent Changes

- Created `maintenance/phase-1-repo-health` branch.
- Started aligning project tracking files with completed releases through AI Validation & Benchmark Framework.
- Added `LICENSE.md` using CC BY 4.0 with Oracle trademark clarification.
- Added `MAINTAINER.md` as the repository operations handbook.
- Added `REPOSITORY_HEALTH.md` as the repeatable repository health scorecard.
- Added `KNOWN_GAPS.md` for missing, stale, weak, or incomplete areas.
- Added `AGENTS.md` as the first-stop AI-agent startup guide.
- Removed a named company example from README public/private overlay guidance.
- Generalized stale AI-agent and platform guidance.
- Refreshed `docs/README.md` contribution and license guidance.
- Refreshed `SESSION_REPORT.md` for the current cleanup pass.
- Refreshed `ROADMAP.md`, `BACKLOG.md`, and `CHANGELOG.md` around current maintenance priorities.
- Added public-safe writing and review guidance to governance files.
- Generalized remaining named-company references found in Avalara and knowledge-acquisition docs.
- Deprecated environment-specific Hermes procedure and fixed visible Pacejet link issues.
- Added advanced troubleshooting module and first four advanced diagnostic articles.
- Added customer credit automation pattern for AR credit visibility, review, workflow, payment-stage, and scripted design options.
- Added advanced saved search diagnostics and permissions/role-difference diagnostics.
- Added SuiteFlow automation patterns, SuiteTalk REST/SOAP troubleshooting, transaction lifecycle troubleshooting, SuiteScript troubleshooting deep dive, and SuiteAnalytics/reporting troubleshooting.
- Added Advanced Avalara content priorities to the backlog and project status.
- Added advanced Avalara troubleshooting index and eight advanced Avalara articles.
- Added Advanced Pacejet troubleshooting index and six advanced Pacejet articles.
- Added SPS Commerce integration module, advanced troubleshooting index, six advanced SPS Commerce diagnostic articles, and generalized bulk 855/856 processing workflows.
- Added Cross-Vendor Support with integration map, self-service guide, incident intake checklist, release/update review workflow, and screenshot/log redaction checklist.

## Repository Health Score

**8.8 / 10**

Detailed scoring now lives in `REPOSITORY_HEALTH.md`. The summary below is retained as a quick project status snapshot.

| Criterion | Score | Notes |
|---|---:|---|
| Structure | 9 | Strong module and framework architecture |
| Governance | 9 | Maintainer guide, license, tracking boundaries, known gaps, AI-agent guide, public-safe review guidance, and repository health scorecard are now defined |
| Templates | 8.5 | Canonical article template exists; deprecated template is clearly marked |
| Content | 9.3 | Multiple ERP learning paths, AI framework layers, vendor-specific advanced troubleshooting, SPS bulk EDI workflows, and cross-vendor support guidance are present |
| Project Tracking | 8.6 | Tracking files exist and are being realigned around clearer responsibilities |
| Automation | 2 | No CI/CD, Pages, linting, or link checking yet |
| Readability | 9 | Markdown style is generally clear and AI-friendly |
| AI Readiness | 9.7 | Strong framework orientation, metadata standards, reasoning layers, advanced diagnostic patterns, and cross-system self-service intake guidance |
