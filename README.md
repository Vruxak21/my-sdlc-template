# SDLC skills template

A project template with Matt Pocock's engineering skills (MIT, https://github.com/mattpocock/skills),
trimmed to 23 skills, plus three custom ones: update-docs, e2e-tests, sdlc-next.
Works with Claude Code, Cursor, Codex and Antigravity.

## Flow (you approve each stage)
grill-with-docs -> to-spec -> to-tickets -> implement -> code-review -> e2e-tests -> update-docs -> pr
Run sdlc-next any time to see which step comes next.

## Layout
- .agents/skills/  real skill files (Cursor, Codex, Antigravity read this)
- .claude/skills/  symlinks to .agents/skills (Claude Code reads this)
- AGENTS.md        workflow rules; CLAUDE.md imports it for Claude Code
- CODING_STANDARDS.md  fill this in per project; code-review checks it
- skills-lock.json upstream source and hashes for the 23 upstream skills

## Use it
New project: click "Use this template" on GitHub, or run
  gh repo create my-app --template Vruxak21/my-sdlc-template
Existing project: from this repo's folder run
  rsync -a .agents .claude skills-lock.json /path/to/project/
  rsync -a --ignore-existing AGENTS.md CLAUDE.md CODING_STANDARDS.md /path/to/project/
(use rsync, not cp, so the symlinks stay links)

Then, once per project: run the setup-matt-pocock-skills skill (choose your issue tracker)
and fill in CODING_STANDARDS.md.

## Notes
- Upstream skills are unmodified. Put workflow rules in AGENTS.md rather than editing them.
- Do not run `npx skills update` here without checking: it can overwrite local edits.
- Skills are invoked as /name in Claude Code and $name in Codex.
- Needs a git setup that supports symlinks (macOS/Linux; Windows needs symlink support enabled).

## License
Upstream skills: MIT, see LICENSE-mattpocock-skills. Custom skills and rules in this repo are yours to license.
