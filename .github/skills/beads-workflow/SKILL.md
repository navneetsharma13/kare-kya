---
name: beads-workflow
description: "Use when creating, claiming, linking, updating, reviewing, or closing Kare-Kya tasks with the local Beads tracker."
---

# Beads Workflow

Input: task goal, canonical tracker location, operator, and human acceptance criteria.
Read the [project rules](../../../AGENTS.md) and [workshop](../../../docs/workshop.md).

## Procedure

1. Confirm Beads is installed, the canonical database exists, and the designated operator owns changes.
2. Run `bd prime`, `bd ready --json`, and `bd show <id>`; check for existing work before creating a task.
3. Have the operator create or claim the task using `bd create "Title" -p 2`
   or `bd update <id> --claim`. Record its human owner, scope, and acceptance criteria.
4. Link blockers with `bd dep add <child> <parent>`; the child waits for the parent.
5. Attach the approved plan, actual test results, review findings, and human acceptance.
   Inspect the installed CLI help for comment, evidence, and closure-reason syntax.
6. Only after human acceptance, close with `bd close <id>` using the supported reason option.
7. If a remote has been configured and tested, use the installed-version guidance for
   `bd dolt pull` and `bd dolt push`. Ordinary Git sync is separate.

## Boundaries and Checks

- Embedded Dolt is single-writer. Do not run concurrent operators against the same directory.
- Separate local databases do not provide globally atomic claims. Use one operator until sync is proven.
- Do not initialize the tracker, install integrations, or add Git hooks without approval.
- A failed install or MCP connection must be recorded as blocked; CLI use is an explicit alternative.
- Verify task persistence after reopening and compare MCP results with the canonical CLI output.

Output: issue ID, owner, dependencies, status, evidence, and remaining blockers.
[Official Beads documentation](https://github.com/gastownhall/beads).