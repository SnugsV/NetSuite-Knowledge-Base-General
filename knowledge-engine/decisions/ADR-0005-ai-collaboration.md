# ADR-0005: AI Collaboration Model

**Status**: Accepted

**Date**: 2026-07-01

## Context

AI agents are first-class collaborators in this repository. They research, write, edit, and review documentation. A clear collaboration model is needed to define how AI agents interact with the project, what standards they follow, and what constraints they operate under.

## Decision

1. **AI agents follow the same standards as human contributors** — no separate "AI rules" document.
2. **AI agents read the Knowledge Engineering Framework before starting work** — this provides context, standards, and workflow.
3. **AI agents verify all technical claims against official Oracle documentation** — AI may hallucinate NetSuite behavior.
4. **AI-generated content is reviewed against project standards** before being marked Approved.
5. **AI agents do not have authority to make high-risk changes without approval** — same as human contributors per DECISION_FRAMEWORK.md.
6. **AI agents log work in SESSION_REPORT.md** — sessions are auditable regardless of whether a human or AI performed them.

## Rationale

1. **Same rules for everyone** prevents confusion. Contributors don't need to know whether content was written by a human or AI.
2. **Verification requirement** mitigates AI hallucination risk for NetSuite-specific technical claims.
3. **Review requirement** ensures AI-generated content meets the same quality bar as human-written content.
4. **Session logging** maintains project memory regardless of who performed the work.

## Consequences

- AI agents must spend time reading framework documents before starting work (adds ~90 seconds to startup).
- AI agents must be able to distinguish "NetSuite fact" from "invented behavior" — if uncertain, they must request clarification.
- Reviewers must verify AI-generated content with the same rigor as human content.
- The framework must be self-contained enough for an AI agent to operate independently.

## Alternatives Considered

- **Separate AI-specific standards document**: Rejected — creates two sets of rules that will diverge.
- **AI agents have restricted permissions (read-only)**: Rejected — defeats the purpose of AI collaboration. Same risk model as human contributors.
- **No AI collaboration model**: Rejected — without explicit rules, AI agents would either be blocked entirely or unconstrained.