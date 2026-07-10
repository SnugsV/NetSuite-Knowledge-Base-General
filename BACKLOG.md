# Backlog

This file tracks actionable work. Completed release history belongs in `CHANGELOG.md`, future direction belongs in `ROADMAP.md`, and current status belongs in `PROJECT_STATUS.md`.

## Current Maintenance Queue

### Phase 1 - Repository Health Cleanup

**Status: In progress**

- [x] Add and link `AGENTS.md` as the first-stop AI-agent guide.
- [x] Add `KNOWN_GAPS.md` for stale, weak, missing, or incomplete areas.
- [x] Remove named company examples from public/private overlay guidance.
- [x] Refresh README public/private overlay wording.
- [x] Refresh `docs/README.md` contribution, license, and public-safety guidance.
- [x] Generalize stale AI-agent startup guidance in framework files.
- [x] Remove stale PR-status language from `PLATFORM_ARCHITECTURE.md`.
- [x] Align `PROJECT_STATUS.md`, `SESSION_REPORT.md`, `ROADMAP.md`, `CHANGELOG.md`, and `REPOSITORY_HEALTH.md` with completed cleanup work.
- [x] Review core governance writing files for public-safety guidance.
- [x] Add `history/` area for public-safe vendor update history.
- [ ] Review roadmap and changelog for release-order consistency before the next tag.
- [ ] Validate documentation links with a repeatable tool.

### Advanced NetSuite Content

**Status: Complete for current foundation batch**

- [x] Add advanced troubleshooting module.
- [x] Add screenshot and error-message triage guidance.
- [x] Add cross-layer NetSuite error diagnostic framework.
- [x] Add SuiteScript and workflow error triage guidance.
- [x] Add integration error triage guidance.
- [x] Add customer credit automation pattern for AR credit visibility, review, workflow, and scripted design options.
- [x] Add advanced saved search diagnostics.
- [x] Add advanced permissions and role-difference diagnostics.
- [x] Add transaction lifecycle troubleshooting for sales, purchasing, inventory, and accounting.
- [x] Add advanced SuiteFlow automation patterns.
- [x] Add SuiteTalk REST and SOAP troubleshooting patterns.
- [x] Add SuiteScript troubleshooting deep dive.
- [x] Add advanced SuiteAnalytics and reporting troubleshooting.
- [ ] Add advanced release/update review workflow for NetSuite, Pacejet, SPS Commerce, and Avalara.

### Advanced Avalara Content

**Status: Planned**

- [ ] Add Avalara tax calculation troubleshooting.
- [ ] Add Avalara address validation and geolocation edge cases.
- [ ] Add NetSuite transaction tax flow with Avalara.
- [ ] Add exemption certificate troubleshooting.
- [ ] Add nexus, jurisdiction, and taxability diagnostic patterns.
- [ ] Add Avalara connector sync failure and log-review guidance.

### Phase 2 - Documentation Quality Audit

**Status: Planned**

- [ ] Audit Markdown formatting across documentation.
- [ ] Validate YAML front matter coverage.
- [ ] Identify broken or questionable relative links.
- [ ] Identify duplicate or overlapping articles.
- [ ] Review Oracle reference coverage.
- [ ] Score module completeness.
- [ ] Score AI-readiness and retrieval quality.
- [ ] Record findings in `KNOWN_GAPS.md` or a dedicated audit report.

### Phase 3 - Automation

**Status: Planned**

- [ ] Add Markdown linting.
- [ ] Add broken-link checking.
- [ ] Add front matter validation.
- [ ] Add GitHub Actions for documentation checks.
- [ ] Evaluate GitHub Pages, MkDocs, or another publishing path.
- [ ] Consider automated repository health reporting.

## Vendor Update Maintenance

Use this queue to keep NetSuite, Pacejet, SPS Commerce, and Avalara guidance current without cluttering current articles.

- [ ] Review public NetSuite release notes on a regular cadence.
- [ ] Review Pacejet public release or support updates on a regular cadence.
- [ ] Review SPS Commerce public release or support updates on a regular cadence.
- [ ] Review Avalara public release or support updates on a regular cadence.
- [ ] Update current articles when public behavior changes.
- [ ] Add notes to `history/` only when superseded or version-specific behavior remains useful.
- [ ] Link historical notes back to the current article they relate to.

## Completed Content Releases

| Release | Status | Notes |
|---|---|---|
| Foundation | Complete | Initial structure, README, roadmap, contribution guide, governance folder, templates, source tracking, and first articles. |
| Getting Started | Complete | Beginner path, documentation homepage, glossary, navigation, roles, dashboards, search, lists, personalization, and keyboard shortcuts. |
| Administration | Complete | Company setup, preferences, features, users, roles, permissions, forms, authentication, audit trail, sandbox, and security. |
| Saved Searches and Reporting | Complete | Criteria, results, formulas, summaries, reports, SuiteAnalytics, KPIs, dashboards, and CSV import/export. |
| Inventory and Operations | Complete | Items, locations, transfers, adjustments, bins, cycle counts, purchasing, receiving, and fulfillment. |
| Purchasing | Complete | Vendor, procurement, purchasing, receiving, and procure-to-pay guidance. |
| Sales | Complete | Customer, order, fulfillment, invoicing, and order-to-cash guidance. |
| Manufacturing | Complete | Planning, production, assemblies, work orders, and plan-to-produce guidance. |
| Accounting | Complete | Record-to-report concepts, transaction flow, and accounting process guidance. |
| Pacejet Intelligence Pack | Complete | Integration intelligence across curriculum, support, context, skills, architecture, and metadata layers. |
| AI Framework Layers | Complete | Support intelligence, customer context, AI skills, solution architect, customer metadata, runtime, experience, and validation frameworks. |

## Future Content Ideas

- Broader integration intelligence beyond Pacejet.
- SuiteScript examples and troubleshooting patterns.
- SuiteTalk REST and SOAP implementation guides.
- SuiteAnalytics workbook guides.
- CRM learning path.
- Workflows and approvals learning path.
- OneWorld and subsidiaries learning path.
- SuiteCommerce guidance.
- WMS guidance.
- Fixed Assets guidance.
- Revenue Recognition guidance.
- SuiteCloud Developer Framework guidance.

## Public-Safety Backlog

- [ ] Run periodic repository-wide searches for named company examples and private implementation details.
- [ ] Review examples in articles to ensure they stay generic and public-safe.
- [ ] Confirm private overlays or internal knowledge sources are referenced only generically.
- [ ] Add automated checks if a repeatable term list becomes stable.
