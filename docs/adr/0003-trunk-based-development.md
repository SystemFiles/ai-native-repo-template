---
status: accepted
date: 2026-11-21
decision-makers: Ben Sykes
---

# Use trunk-based development

## Context and Problem Statement

`main` is the releasable state of a long-lived repo. How should changes reach
`main` without long-lived branches drifting from it?

## Decision Drivers

* `main` must always be releasable
* Small, reviewable changes
* Fast feedback from CI
* Works with jj stacked changes

## Considered Options

* Trunk-based development with short-lived branches
* GitFlow with long-lived feature branches
* Environment branches (dev/staging/prod)

## Decision Outcome

Chosen option: "Trunk-based development with short-lived branches", because
`main` is the releasable state and small PRs keep it reviewable.

### Consequences

* Good, because changes integrate often and conflicts stay small
* Good, because `main` stays close to what the next release contains
* Bad, because large changes must be split into safe steps

### Confirmation

* Branches are named with Conventional Commit prefixes (`feat/…`, `docs/…`)
  and merged into `main` through a PR
* CI (`commitlint`) must pass before merging
* Passing CI is a merge convention. Require the check in branch protection
  when the host plan allows it.

## Pros and Cons of the Options

### Trunk-based development with short-lived branches

* Good, because it keeps changes small
* Good, because jj stacks let one feature ship as several small PRs
* Bad, because it needs CI you trust

### GitFlow with long-lived feature branches

* Good, because in-progress work is isolated
* Bad, because merges get large and late

### Environment branches (dev/staging/prod)

* Good, because each environment maps to a branch
* Bad, because changes are merged several times and environments drift

## More Information

Adapted from the starter ADR "Use Trunk-Based Development with Short-Lived
Branches".
