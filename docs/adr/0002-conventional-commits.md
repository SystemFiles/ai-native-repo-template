---
status: accepted
date: 2026-11-21
decision-makers: Ben Sykes
---

# Use Conventional Commits

## Context and Problem Statement

SemVer bumps and the changelog ([ADR-0001](0001-semantic-versioning.md)) need
machine-readable commit messages. How should commits be written?

## Decision Drivers

* Drive automated version bumps and changelog
* Keep history readable for people and agents
* Enforce it in CI, not by memory

## Considered Options

* Conventional Commits 1.0.0
* A custom format
* No standard

## Decision Outcome

Chosen option: "Conventional Commits 1.0.0", because release-please and
commitlint support it out of the box and it maps directly to SemVer.

### Consequences

* Good, because version bumps and changelog are automatic
* Good, because history is easy to scan by type and scope
* Bad, because every commit has to follow the format, including fixups

### Confirmation

The `commitlint` workflow checks every commit in a PR against
`@commitlint/config-conventional` (the action's default when the repo has no
commitlint config). The repo merges with merge commits, so each PR commit lands
on `main` and must pass on its own.

## Pros and Cons of the Options

### Conventional Commits 1.0.0

[Spec](https://www.conventionalcommits.org): `<type>[scope][!]: <description>`.

* Good, because it's a documented standard with wide tool support
* Good, because `!` and `BREAKING CHANGE:` mark major bumps
* Bad, because the format feels strict for small changes

### A custom format

* Good, because it can fit local taste
* Bad, because tools need custom configuration

### No standard

* Good, because there's no overhead
* Bad, because automation is impossible

## More Information

Common types: `feat`, `fix`, `docs`, `refactor`, `chore`, `ci`, `test`.
Adapted from the starter ADR "Use Conventional Commits".
