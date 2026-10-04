---
name: verify-change
description: "Use when testing, validating, reviewing, demonstrating, or recording acceptance evidence for a Kare-Kya code change."
---

# Verify a Change

Input: requirement, changed files, current hypothesis, and available verification commands.
Read the [lifecycle](../../../docs/lifecycle.md) and
[evidence template](../../../docs/evidence/verification-template.md).

## Procedure

1. Map acceptance criteria to observable checks and identify the cheapest falsifying check.
2. Run that check immediately after the first substantive edit; repair the same slice if it fails.
3. Run the relevant existing tests, then required typecheck/lint/build gates for touched components.
   If no commands exist, state that explicitly; a documentation scaffold is not an app build.
4. Use model stubs and source fixtures in automated tests. Record real local inference and
   live MCP calls separately, including model tag, endpoint, elapsed time, and outcome.
5. For UI changes, check desktop and mobile, keyboard focus, source links, overflow,
   and loading/empty/error/stale/fixture states.
6. Compare generated claims with source excerpts. Schema validity does not prove factuality.
7. Provide the actual diff and results to an independent reviewer; resolve relevant findings.
8. Request human acceptance, attach evidence to the task, and document a reproducible demo.

## Boundaries

- Never invent passed checks, screenshots, tool calls, or human approvals.
- Do not fix unrelated failures or close tasks before acceptance.
- No cloud inference fallback or hosted trace export to make a local check pass.
- Keep secrets, downloaded model files, caches, and raw sensitive logs out of Git.

Output: checks executed, results, review findings, human decision, and unverified requirements.