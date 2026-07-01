---
title: SuiteScript Overview
department: NetSuite
module: SuiteScript
status: Draft
version: 0.1
created: 2026-07-01
tags: [suitescript, automation, customization, javascript, suitecloud]
source_type: Oracle Documentation Summary
---

# SuiteScript Overview

## AI Summary

SuiteScript is NetSuite's JavaScript-based scripting platform for customization and automation. SuiteScript 2.x and 2.1 use a modular API style and support different script types for client-side behavior, server-side processing, scheduled automation, RESTlets, Suitelets, user events, and more.

## Purpose

Use SuiteScript when standard NetSuite configuration, workflows, saved searches, or reports cannot fully support the business requirement.

## Key Concepts

- **SuiteScript 2.x / 2.1:** Modern modular scripting APIs.
- **Modules:** API areas such as records, searches, runtime, files, email, and tasks.
- **Script Types:** Different execution contexts such as Client Script, User Event Script, Scheduled Script, Map/Reduce Script, Suitelet, and RESTlet.
- **Governance:** NetSuite limits script usage through usage units and execution limits.
- **Deployment:** Scripts must be uploaded, configured, and deployed in NetSuite.

## Common Use Cases

- Validate fields before saving a record.
- Automate record creation or updates.
- Build custom pages.
- Integrate with external systems.
- Process large datasets on a schedule.
- Add business rules that cannot be handled by workflow alone.

## Common Mistakes

- Using script when workflow or configuration would be simpler.
- Ignoring governance limits.
- Loading unnecessary modules.
- Not testing in sandbox first.
- Hardcoding account-specific values.
- Not documenting deployment settings.

## Best Practices

- Use SuiteScript 2.x or 2.1 for new development.
- Load only the modules needed by the script.
- Keep scripts focused and maintainable.
- Use sandbox testing before production deployment.
- Document script purpose, owner, deployment, and dependencies.

## Related Topics

- SuiteScript 2.x API Introduction
- SuiteScript 2.1 Modules
- SuiteScript Governance and Limits
- Script Types
- RESTlets
- Suitelets

## Official References

- Oracle NetSuite: SuiteScript Overview
- Oracle NetSuite: SuiteScript 2.x API Introduction
- Oracle NetSuite: SuiteScript Governance and Limits
