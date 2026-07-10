# Vendor Update History

This folder is for public-safe historical notes about vendor updates that materially change how NetSuite, Pacejet, SPS Commerce, Avalara, or related ecosystem topics should be explained.

Use Git history for normal article edits. Use this folder only when an older behavior, version-specific note, or superseded public article may still be useful for troubleshooting or comparison.

## When to Archive Here

Archive or summarize historical information here when:

- A vendor release changes a public behavior described in the knowledge base.
- An article is replaced because the old version applies only to a prior product release.
- A troubleshooting pattern remains useful for older accounts or older connector versions.
- A public source changes and the repository needs to preserve why guidance changed.

Do not archive routine wording edits, formatting changes, or minor corrections here. Those belong in normal Git history.

## Public-Safe Rules

Historical notes must follow the same public/private boundary as current documentation.

Do not include company-specific SOPs, customer examples, private screenshots, custom fields, saved searches, workflows, SuiteScripts, pricing, credentials, proprietary processes, or details that reveal how a specific organization operates.

## Folder Structure

```text
history/
  netsuite/
  pacejet/
  sps-commerce/
  avalara/
```

Each vendor folder should keep a short index of notable public updates and link to archived notes when needed.

## Suggested Historical Note Format

```markdown
# Vendor Topic - YYYY-MM Update

## Status
Superseded | Historical reference | Needs review

## Applies To
Product, version, connector, or release window.

## What Changed
Short public-safe summary of the update.

## Why It Matters
How the change affects NetSuite concepts, troubleshooting, or user guidance.

## Current Guidance
Link to the current article that replaced or superseded this note.

## Public Sources
Links to public vendor release notes, help pages, or documentation.
```
