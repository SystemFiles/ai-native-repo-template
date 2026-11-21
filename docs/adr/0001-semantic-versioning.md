---
status: accepted
date: 2026-11-21
decision-makers: Ben Sykes
---

# Version releases with SemVer

## Context and Problem Statement

This repo changes in steps that can break existing users. How should we mark
and communicate each release?

## Decision Drivers

* A version should say whether a release can break things
* Bumps should be automatic from commit history
* Simple enough to apply every time

## Considered Options

* Semantic Versioning (SemVer)
* Calendar Versioning (CalVer)
* Incrementing numbers
* No versioning

## Decision Outcome

Chosen option: "Semantic Versioning", because it signals breaking changes and
can be derived from Conventional Commits ([ADR-0002](0002-conventional-commits.md)).

### Consequences

* Good, because `feat!`/`BREAKING CHANGE` maps to a major bump that flags
  risky releases
* Good, because release-please can bump versions and write the changelog
* Bad, because changes must be typed correctly for the version to mean anything

### Confirmation

release-please runs on every push to `main`, opens a release PR that updates
`CHANGELOG.md`, and tags `vX.Y.Z` when merged. Versions start at `0.0.0`; while
on `0.x`, breaking changes bump the minor version.

## Pros and Cons of the Options

### Semantic Versioning (SemVer)

[SemVer 2.0.0](https://semver.org/): MAJOR for breaking changes, MINOR for
backward-compatible features, PATCH for fixes.

* Good, because the number carries meaning
* Good, because tooling derives it from commit types
* Bad, because what counts as breaking needs judgment

### Calendar Versioning (CalVer)

* Good, because it shows when a release happened
* Bad, because it says nothing about impact

### Incrementing numbers

* Good, because it's trivial
* Bad, because it carries no information

### No versioning

* Good, because it costs nothing
* Bad, because there's no way to name a known-good state

## More Information

Adapted from the starter ADR "Use Semantic Versioning".
