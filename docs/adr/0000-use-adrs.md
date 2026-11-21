---
status: accepted
date: 2026-11-21
decision-makers: Ben Sykes
---

# Record decisions as MADR ADRs

## Context and Problem Statement

Decisions were spread across a README, an agent guide and PR descriptions.
Agents and future readers need one place that says what was decided, why, and
what else was considered.

## Decision Drivers

* Decisions should live next to the code they govern and be reviewed in PRs
* Agents must be able to find and follow them
* Low overhead for a long-lived repo

## Considered Options

* Lightweight ADRs in MADR format in the repo
* Notes in a wiki or the README
* No formal record

## Decision Outcome

Chosen option: "Lightweight ADRs in MADR format in the repo", because they are
versioned and reviewed with the code and give agents a stable place to look.

### Consequences

* Good, because each decision carries its context and rejected options
* Good, because decisions are reviewed in PRs like any other change
* Bad, because ADRs must be written at decision time, and superseded ones marked

### Confirmation

`docs/adr/` holds the template and an index. The `write-adr` agent skill
drafts new ADRs, and decisions are reviewed in PRs.

## Pros and Cons of the Options

### Lightweight ADRs in MADR format in the repo

* Good, because MADR is a widely used, structured but short format
* Good, because supersede-not-edit keeps the history readable
* Bad, because it adds a document to write per decision

### Notes in a wiki or the README

* Good, because there's nothing new to learn
* Bad, because it drifts from the code and loses the rejected options

### No formal record

* Good, because it costs nothing now
* Bad, because the reasoning is lost and agents guess

## More Information

Based on [ai-adr-template](templates/adr-template.md) and the starter ADR
"Use Lightweight ADRs with MADR Format". Rules live in [README](README.md).
