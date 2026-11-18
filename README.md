# Skills

> A curated collection of practical skills for day-to-day software work.

This repository organizes skills by workflow area so you can add the tools you need
without copying unrelated setup. It is both a skill catalog and a collection of
project templates for supported coding agents.

## Collections

| Collection | Purpose |
| --- | --- |
| [`sdlc/`](sdlc/README.md) | Structured software delivery from discovery and specification through implementation, review, testing, documentation, and pull requests |
| [`ui/`](ui/README.md) | UI design and implementation skills for product illustrations, motion, and polished interface work |

## Choose a collection

### SDLC skills

Create a project from the repository template, then copy the SDLC collection into it:

```bash
gh repo create my-app --template Vruxak21/my-sdlc-template --clone
cd my-app
rsync -a sdlc/.agents sdlc/.claude sdlc/skills-lock.json .
rsync -a --ignore-existing sdlc/AGENTS.md sdlc/CLAUDE.md sdlc/CODING_STANDARDS.md .
```

See the [SDLC installation guide](sdlc/README.md) for workflow and setup details.

### UI skills

Create a project from the repository template, then copy the UI collection into it:

```bash
gh repo create my-app --template Vruxak21/my-sdlc-template --clone
cd my-app
rsync -a ui/.agents ui/.claude ui/skills-lock.json .
```

See the [UI installation guide](ui/README.md) for the available skill and usage details.

> Use `rsync`, not `cp`, so the Claude Code symlinks remain links.

## Repository layout

```text
sdlc/
  .agents/       Skills read by Cursor, Codex, and Antigravity
  .claude/       Claude Code symlinks
  skills-lock.json
ui/
  .agents/       UI skills read by supported coding agents
  .claude/       Claude Code symlinks
  skills-lock.json
```

Skills are invoked as `/name` in Claude Code and `$name` in Codex.
