# Agent Instructions

## Overview

<!-- What this repo is, and how it is laid out. -->

## Hard rules for this repo

- This file should never exceed 100 lines
- Be extremely concise and always ask for permission to update this file.

## Docs

- Docs rarely change. Edit one only when a statement in it became false or a manual step changed.
- Never restate what code says (versions, addresses, names, component lists); link the file or ADR.
- Decisions go in `docs/adr/` (`write-adr` skill), recipes in `CONTRIBUTING.md`.

## How we work

- Plan anything beyond a small fix and wait for approval, then ship one thin slice per PR.
- Do only what was asked. Ask before adding scope, components, files or scripts.
- Prefer upstream documented defaults over overrides or wrappers.
- Check current state first: `main` and open PRs. The human may have changed things.
- New dependency, pattern or reversal: ADR PR first, implement after it merges.
- Live systems: read freely; change only after an explicit OK each time, back up first, verify after.
- Never assume the human did something (stored a secret, merged, applied). Say exactly what to do and where, then wait.
- Use jj, not git, in one isolated jj workspace per task. Rebase onto `trunk()` before pushing. No AI co-author trailers.
- PRs reference their issue.

## Rules

- When writing code in this repo:
 - follow the strangler-fig pattern when doing infra migrations
 - never ship a commit if there is dead code or code that would be made dead in the commit
 - never ship a commit without a deslop pass (remove unnecessary comments, defensive code and inconsistent style)
 - build the minimal possible solution first and expand only if absolutely necessary (LESS CODE IS BETTER)
 - prefer inline CI steps and pinned maintained actions over bespoke scripts
- Conventional commits (ADR-0002), semver (ADR-0001).
- PRs: use `.github/PULL_REQUEST_TEMPLATE.md`; minimal, plain, jargon-free prose.

## Commands

<!-- Commands that build, test, and lint this repo. -->
