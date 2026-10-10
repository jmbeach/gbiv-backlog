---
id: gbv-1ht
---

Make gbiv's task-tracker integration pluggable so it can pull in tasks, update status (claim / in-progress / done / blocked), etc. against different backing systems.

- vat is the default, built-in system gbiv works with out of the box.
- Future goal: first-class support for systems like Jira.
- Others should be able to contribute support for additional systems — potentially via an extension/plugin system.

Open design questions (resolve in HLD/LLD):
- Shape of the provider interface (list/pull tasks, claim, update status, mark done, block/unblock, assignee).
- Extension mechanism: in-crate trait + cargo features, external executables over a stable protocol (e.g. `gbiv-provider-<name>` speaking JSON on stdin/stdout), or something else.
- How a repo selects/configures its provider (and per-provider auth/config).
- Mapping of vat concepts (IDs, markers, blocked-by) onto systems with richer workflows.
