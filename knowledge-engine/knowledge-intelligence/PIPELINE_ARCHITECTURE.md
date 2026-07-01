# Pipeline Architecture

## Purpose

Full design of the Knowledge Intelligence Pipeline — how it discovers, analyzes, and recommends updates without automatically modifying production documentation.

## Pipeline Flow

```
┌─────────────────────────────────────────────────────────────────┐
│                      Phase 1: Discover                          │
│                                                                 │
│  RSS Feeds → Fetch latest entries                                │
│  Web Pages → Fetch and diff                                      │
│  Version APIs → Check version numbers                            │
│                                                                 │
│  Output: Raw change data                                         │
└──────────────────────────┬──────────────────────────────────────┘
                           ↓
┌──────────────────────────┴──────────────────────────────────────┐
│                      Phase 2: Analyze                            │
│                                                                 │
│  Categorize changes (Critical/Major/Minor/Info)                  │
│  Map changes to repository layers                                │
│  Assess coverage impact                                          │
│                                                                 │
│  Output: Analyzed change list                                    │
└──────────────────────────┬──────────────────────────────────────┘
                           ↓
┌──────────────────────────┴──────────────────────────────────────┐
│                      Phase 3: Compare                            │
│                                                                 │
│  Compare new content to existing repository content              │
│  Identify gaps (topics not covered)                              │
│  Identify deltas (topics that need updating)                     │
│                                                                 │
│  Output: Gap and delta analysis                                  │
└──────────────────────────┬──────────────────────────────────────┘
                           ↓
┌──────────────────────────┴──────────────────────────────────────┐
│                      Phase 4: Recommend                          │
│                                                                 │
│  Generate Knowledge Intelligence Report                          │
│  Suggest specific repository updates                             │
│  Estimate implementation effort                                  │
│  Propose Pull Requests                                           │
│                                                                 │
│  Output: Completed KI Report                                     │
└──────────────────────────┬──────────────────────────────────────┘
                           ↓
┌──────────────────────────┴──────────────────────────────────────┐
│                      Phase 5: Human Review                       │
│                                                                 │
│  Human reviews the KI Report                                     │
│  Prioritizes suggested updates                                   │
│  May create new PRs from suggestions                             │
│  May close suggestions as not applicable                         │
│                                                                 │
│  Output: Approved PRs / Rejected suggestions                     │
└─────────────────────────────────────────────────────────────────┘
```

## Execution Model

The pipeline is designed for these execution environments:

### Hermes Cron Job

```
Schedule: Every 14 days
Trigger: "knowledge-intelligence-pipeline" cron job
Input: Source Registry
Execution: Hermes agent reads sources, generates KI Report
Delivery: KI Report posted to configured channel
```

### GitHub Action

```
Schedule: Cron (biweekly) or workflow_dispatch (manual)
Trigger: Scheduled or manual
Execution: GitHub Action runs script to check sources
Delivery: KI Report created as workflow artifact
```

### AI Agent (Standalone)

```
Schedule: Agent-initiated (manual or cron-triggered)
Trigger: Agent task prompt
Execution: Agent follows pipeline architecture
Delivery: KI Report as agent response
```

## Human Review Gate

No update reaches the repository without human approval:

```
Pipeline generates KI Report
       ↓
Human reviews report
       ↓
Human decides which suggestions to implement
       ↓
Human creates or approves Pull Requests
       ↓
Human merges after standard review
```

## Repository Integration

The pipeline does not create a new architectural layer. It is a maintenance process that feeds into existing layers:

| Pipeline Output → | Feeds Into |
|---|---|
| New feature documentation | Layer 1 — ERP Curriculum |
| Updated support patterns | Layer 2 — Support Intelligence |
| New context requirements | Layer 3 — Customer Context |
| New skill requirements | Layer 4 — AI Skills |
| New capability options | Layer 5 — Solution Architect |
| Updated metadata requirements | Layer 6 — Customer Metadata |

## Failure Modes

| Failure | Impact | Recovery |
|---|---|---|
| Source unavailable | No data for that source this cycle | Log the failure, retry next cycle |
| Page structure changed | Diff algorithm fails | Update diff pattern or selector |
| Version API changed | Version check fails | Update API endpoint or method |
| Rate limited | Slow or incomplete data collection | Implement backoff, reduce frequency |

## Success Criteria

A successful pipeline cycle produces:

- [ ] All enabled sources checked
- [ ] Changes categorized by impact
- [ ] Repository coverage assessed
- [ ] Gaps and deltas identified
- [ ] Knowledge Intelligence Report generated
- [ ] Suggested Pull Requests documented
- [ ] All changes require human review
- [ ] No automatic modifications to production content

## Related Documents

- [SOURCE_REGISTRY.md](SOURCE_REGISTRY.md)
- [MONITORING_STRATEGY.md](MONITORING_STRATEGY.md)
- [KI_REPORT_TEMPLATE.md](KI_REPORT_TEMPLATE.md)
- [RELEASE_PROCESS.md](../RELEASE_PROCESS.md)