# SDLC workflow
Stages: requirements (grill-with-docs) → spec (to-spec) → tickets (to-tickets)
→ implement → code-review → e2e-tests → update-docs → pr.
Rules:
- Never start the next stage without my explicit approval.
- Before implementing, show a short plan (files, tests) and wait for approval.
- Commit before code-review; review against the commit before the work.
- If sub-agents are unavailable, do the work sequentially.
- Refer to skills by name (run the code-review skill); don't assume /name or $name syntax.
