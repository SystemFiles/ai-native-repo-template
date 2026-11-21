# Architecture decision records

Each ADR records one decision: the context, the options we looked at, and why
we picked one. ADRs use the [MADR](https://adr.github.io/madr/) format
([template](templates/adr-template.md)).

## Rules

- File name: `NNNN-kebab-case-title.md`. Numbers are sequential and never reused.
- One decision per ADR.
- Once accepted, an ADR is not edited. Write a new ADR that supersedes it and
  set the old one's status to `superseded by ADR-NNNN`.
- Agents follow the [`write-adr`](../../.agents/skills/write-adr/SKILL.md) skill.

| Status | Meaning |
| --- | --- |
| `proposed` | Under discussion |
| `accepted` | Agreed and in force |
| `rejected` | Considered, not adopted |
| `deprecated` | No longer relevant |
| `superseded by ADR-NNNN` | Replaced by a newer ADR |

## Index

| ADR | Decision | Status |
| --- | --- | --- |
| [0000](0000-use-adrs.md) | Record decisions as MADR ADRs | accepted |
| [0001](0001-semantic-versioning.md) | Version releases with SemVer | accepted |
| [0002](0002-conventional-commits.md) | Use Conventional Commits | accepted |
| [0003](0003-trunk-based-development.md) | Use trunk-based development | accepted |
