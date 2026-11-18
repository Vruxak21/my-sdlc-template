# UI Skills

> Practical UI skills for creating polished product interfaces and motion studies.

This collection contains UI-focused skills that are useful for day-to-day product
design and frontend implementation. It currently includes Stageshow, a skill and
React kit for product illustrations, cursor stories, transitions, and motion design.

Works with **Claude Code**, **Cursor**, **Codex**, and **Antigravity**.

## Included skill

### Stageshow

Stageshow helps create high-quality interface demonstrations and product illustrations.
It includes:

- Portable React components and CSS for UI scenes
- Polished example compositions
- Motion, choreography, and visual-study references
- Verification tools and a local preview playground

Start with [`.agents/skills/stageshow/SKILL.md`](.agents/skills/stageshow/SKILL.md).

## Get started

### Create a new project

Use the repository's GitHub template, then copy this collection into the project:

```bash
gh repo create my-app --template Vruxak21/my-sdlc-template --clone
cd my-app
rsync -a ui/.agents ui/.claude ui/skills-lock.json .
```

### Add the collection to an existing project

From the repository root, run:

```bash
rsync -a ui/.agents ui/.claude ui/skills-lock.json /path/to/project/
```

> Use `rsync`, not `cp`, so the Claude Code symlinks remain links.

## Collection layout

| Path | Purpose |
| --- | --- |
| `.agents/skills/stageshow/` | Stageshow skill, React kit, examples, references, and tools |
| `.claude/skills/stageshow` | Claude Code symlink to the Stageshow skill |
| `skills-lock.json` | Upstream source and hash for the collection |

## Skill-specific setup

The Stageshow playground requires Node 20.19 or later:

```bash
cd .agents/skills/stageshow
npm install
npm run dev
```

See [the Stageshow documentation](.agents/skills/stageshow/README.md) for preview,
verification, and copying the kit into another React project.
