---
id: gbv-tkn
---

Remove the `gbiv reset` command and the soft all-color reset step that `gbiv tidy` runs.

- Why: reset isn't used in practice, and gbv-1ht removes `gbiv mark`, so nothing writes the `[done]` tag that reset's all-color mode keys on.
- Scope: worktree-lifecycle segment (LLD, specs, tests, code), `tidy` becomes rebase-all + tmux clean, README.
- After removal nothing returns a merged worktree to its color branch; `gbiv start` could take that on later if it's missed.
