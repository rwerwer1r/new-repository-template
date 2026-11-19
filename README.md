# New Repository Template

A technology-agnostic starter for projects owned by **rwerwer1r**. It includes agent instructions, documentation structure, GitHub issue/PR templates, formatting tools, and CI checks. Each new project chooses its own language, application tests and deployment workflow.

## Start a project

1. Select **Use this template** on GitHub, and create the new repository in the intended account.
2. Read [Initial Tool Setup](docs/tools/initial-setup.md). Review external downloads and generated files before authorizing installation or local Git changes.
3. If you want the shared tools and agent integration, install [mise](https://mise.jdx.dev/) and run:

```sh
mise install
mise run setup
mise run check
```

`setup` resolves the declared Rulesync source, generates agent projections, updates generated ignore entries, and configures the clone-local [Git commit template](docs/tools/git/README.md). Inspect `rulesync.lock` before committing it. See [Project Setup](docs/guides/project-setup.md) for application-specific adaptation and verification.

## What's included

| Area | Starting point |
| --- | --- |
| Agent instructions | [AGENTS.md](AGENTS.md) and [agent lifecycle](docs/development/agents/assets.md) |
| Optional agent Skills | [rulesync.jsonc](rulesync.jsonc) starts with the public [Rulesync](https://github.com/dyoshikawa/rulesync) Skill; add only explicitly reviewed sources |
| Tooling | [mise.toml](mise.toml) configures Node, rumdl, Biome, Lefthook and Rulesync |
| Documentation | [docs/](docs/README.md) contains goal, architecture, development and tool guides; [docs index](docs/INDEX.tsv) is generated |
| Collaboration | [issue forms](.github/ISSUE_TEMPLATE/), [PR template](.github/pull_request_template.md), and [authoring aids](.github/templates/README.md) |
| Work notes | [.inbox/](.inbox/README.md) provides disposable research and handoff scaffolds; no past project records are included |

## Everyday commands

| Action | Command |
| --- | --- |
| Format supported Markdown, code and configuration | `mise run format` (writes files) |
| Check Markdown, Biome and Lefthook | `mise run check` |
| Validate Rulesync declaration | `mise run agents-check` |
| Preview projections after setup | `mise run agents-preview` |
| Reinstall from a reviewed lock | `mise run agents-restore` |
| Deliberately update upstream revisions | `mise run agents-refresh` |
| Preview/retire generated targets | `mise run agents-retire -- <targets> --features <features> [--apply]` |

Git hooks are optional. The included Node.js scripts support documentation tooling; they do **not** determine the application language. Shared CI does not replace application tests. See [Tools](docs/tools/README.md).

## Provenance

Adapted from [mols3131d/new-repository-template](https://github.com/mols3131d/new-repository-template) under the MIT license. The original copyright and license notice is retained in [Third-Party Notices](THIRD_PARTY_NOTICES.md). This version does **not** install or sync Skills from the `mols3131d` account; any additional source must be explicitly chosen for the derived project.
