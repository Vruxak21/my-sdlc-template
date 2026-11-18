# SDLC Skills Template

> A ready-to-use project template for structured, approval-driven software delivery.

Built on [Matt Pocock's engineering skills](https://github.com/mattpocock/skills), this
template includes 23 trimmed upstream skills plus three custom skills:
`update-docs`, `e2e-tests`, and `sdlc-next`.

Works with **Claude Code**, **Cursor**, **Codex**, and **Antigravity**.

## Workflow

Each stage is approved before the next one begins:

```text
grill-with-docs -> to-spec -> to-tickets -> implement -> code-review -> e2e-tests -> update-docs -> pr
```

Run `sdlc-next` at any time to see which step comes next.

## Repository layout

| Path | Purpose |
| --- | --- |
| `.agents/skills/` | Real skill files read by Cursor, Codex, and Antigravity |
| `.claude/skills/` | Symlinks to `.agents/skills/` for Claude Code |
| `AGENTS.md` | Workflow rules; `CLAUDE.md` imports this for Claude Code |
| `CODING_STANDARDS.md` | Project-specific standards checked during code review |
| `skills-lock.json` | Upstream source references and hashes for the 23 upstream skills |

## Get started

### Create a new project

Use the repository's GitHub template, then copy this collection into the project:

```bash
gh repo create my-app --template Vruxak21/my-sdlc-template --clone
cd my-app
rsync -a sdlc/.agents sdlc/.claude sdlc/skills-lock.json .
```

### Add the template to an existing project

From the repository root, run:

```bash
rsync -a sdlc/.agents sdlc/.claude sdlc/skills-lock.json /path/to/project/
rsync -a --ignore-existing sdlc/AGENTS.md sdlc/CLAUDE.md sdlc/CODING_STANDARDS.md /path/to/project/
```

> Use `rsync`, not `cp`, so the symlinks remain links.

Then, once per project:

1. Run the `setup-matt-pocock-skills` skill and choose your issue tracker.
2. Fill in `CODING_STANDARDS.md`.

## Notes

- Upstream skills are unmodified. Put workflow rules in `AGENTS.md` instead of editing them.
- Do not run `npx skills update` without checking first; it can overwrite local edits.
- Skills are invoked as `/name` in Claude Code and `$name` in Codex.
- Git must support symlinks: macOS and Linux do by default; Windows requires symlink support to be enabled.

## License

Upstream skills are MIT licensed; see [`LICENSE-mattpocock-skills`](LICENSE-mattpocock-skills).
Custom skills and rules in this repository are yours to license.
