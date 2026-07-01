# Monitoring Strategy

## Purpose

How each source is monitored, how changes are detected, and what triggers a Knowledge Intelligence Report.

## Monitoring Methods

### Method 1: RSS / Feed Monitoring

Best for: Sources with RSS feeds or changelogs.

| Source | Feed | Frequency |
|---|---|---|
| Pacejet Help Center | RSS feed available | Daily |
| Shopify API Changelog | RSS feed available | Daily |
| Salesforce Release Notes | RSS feed available | Weekly |

**Process**: Fetch feed → compare to last known entry → identify new entries → extract summary → log findings.

### Method 2: Page Diff Monitoring

Best for: Sources without feeds, where page content changes over time.

| Source | Pages to Monitor | Frequency |
|---|---|---|
| Oracle Help Center | Release notes page | Weekly |
| SuiteAnswers | New article feed | Weekly |
| Pacejet carrier pages | Carrier-specific pages | Biweekly |

**Process**: Fetch page → compare hash or text diff to last known version → identify changes → categorize by impact → log findings.

### Method 3: Version Number Monitoring

Best for: Sources with explicit version numbers.

| Source | Version to Track | Frequency |
|---|---|---|
| NetSuite Release Version | Account release schedule | Biweekly |
| Pacejet Shipping Version | About screen version | Monthly |
| Pacejet Connector Version | Bundle version | Monthly |

**Process**: Track known version → check for new version → if new, investigate change notes → log findings.

## Change Categorization

Every detected change is categorized by impact:

| Category | Description | Action |
|---|---|---|
| **Critical** | Breaking change, deprecated feature, security issue | Immediate PR recommended |
| **Major** | New feature, significant behavior change | Standard PR cycle |
| **Minor** | Bug fix, clarification, minor enhancement | Document in next report |
| **Informational** | Known issue, workaround, tip | Log for reference |

## Monitoring Schedule

| Cadence | Sources | Output |
|---|---|---|
| Daily | Pacejet feeds, integration status pages | Quick check — no full report |
| Weekly | Oracle NetSuite, SuiteAnswers | Brief findings summary |
| Biweekly | All sources | Full Knowledge Intelligence Report |
| Monthly | Carrier updates, version tracking | Version status summary |

## When Not to Monitor

- Do not monitor sources that have not changed in 6+ months (archive them)
- Do not monitor sources that are not related to documented integrations
- Do not monitor sources that do not directly affect the repository's content