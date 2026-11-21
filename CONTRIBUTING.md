# Contributing

Rules are in [AGENTS.md](AGENTS.md); they bind humans too.

## Every change

1. Read the [ADRs](docs/adr/) that touch your area.
2. Branch off `main` with a Conventional Commit prefix (`feat/…`, `fix/…`);
   keep it small ([ADR-0003](docs/adr/0003-trunk-based-development.md)).
3. Open a PR with [the template](.github/PULL_REQUEST_TEMPLATE.md).

## Change CI

Workflows are in `.github/workflows/` and run on the self-hosted runner named
after the repo. Pin actions to a commit SHA with a version comment.

## Record a decision

Copy [the template](docs/adr/templates/adr-template.md) to
`docs/adr/NNNN-title.md` and add it to the [index](docs/adr/README.md). Agents
use the [`write-adr`](.agents/skills/write-adr/SKILL.md) skill.
