---
name: update-docs
description: Update README, docs and ADRs from the current branch's changes. Use only when the user asks.
disable-model-invocation: true
---
1. Ask for the base commit; diff against it.
2. List affected docs (README, docs/, ADRs, glossary).
3. Propose edits, wait for approval, then apply. Do not change application code.
