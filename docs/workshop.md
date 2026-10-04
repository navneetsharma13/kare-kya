# Two-Hour Workshop

## Success Criteria

- One task completes specification, tracking, planning, implementation, verification,
  independent review, human acceptance, and closure with evidence.
- The team demonstrates skill loading and actual MCP discovery/invocation.
- Application inference uses a local downloaded model; no cloud fallback.
- Another developer reproduces the completed slice from documented commands.

Model/MCP capability is a required runtime check, not a guarantee. If it fails, record
the blocker and continue the lifecycle exercise with explicitly labeled fixtures.

## Ownership and Time

| Minutes | Work | Owner |
| --- | --- | --- |
| 0-5 | Approve scope, stack, root, and acceptance criteria | All |
| 5-20 | Context/tracker; model download; frontend scaffold | A / B / C |
| 20-40 | Invoke skills, approve contract, verify local model and MCP | All |
| 40-75 | News tool/API; digest UI; integration and deterministic tests | B / C / A |
| 75-100 | Focused tests, failure drill, independent review | All |
| 100-115 | Reproducibility, local demo, acceptance | All |
| 115-120 | Retrospective and follow-up backlog | All |

A owns root configuration and canonical tracking. B owns backend/runtime files.
C owns frontend files. Shared contracts require coordination; do not concurrently edit them.

## Local Setup Checklist

These are proposed setup steps, not commands already run by this scaffold.
Approve dependency installation and tracker initialization before executing them.

1. Verify `python3 --version`, `uv --version`, `node --version`, `npm --version`,
   and `git --version`. Choose Python 3.12 and supported Node LTS compatible with Vite.
2. Check repository status/root. Work in the repository containing the project rules;
   do not create another clone inside it.
3. Check `ollama --version` and `ollama list`; download with `ollama pull qwen3:4b`.
   A 16 GB Mac is the intended test machine, not a guarantee of latency or available memory.
4. Pin `http://localhost:11434/v1`, a non-cloud model tag, small context, and one model run
   at a time. Disable hosted tracing and measure one tool-call/structured-output smoke run.
5. Create Python and frontend dependency manifests only when scaffolding those components.
   Pin compatible versions and document exact setup/test/start commands after verifying them.
6. Install Beads with `brew install beads` if Homebrew is available; verify `bd version`.
   Inspect `bd init --help` before choosing `--skip-agents --skip-hooks` to avoid extra integrations.
7. Use one canonical local Beads operator. Do not copy its live database between machines.
   Add cross-machine Dolt sync only after a create/push/pull/update round trip succeeds.
8. Optional editor integration: install `beads-mcp` with `uv tool install beads-mcp`, then
   add trusted workspace-scoped MCP configuration with the correct executable/database path.
   Confirm a real `ready` result matches CLI output; do not treat config presence as success.

Allow 10 minutes for Beads setup. If blocked, agree on a temporary local backlog;
GitHub Issues is a hosted fallback only with team consent. Do not install Plane today.
By minute 40, stop prolonged capability debugging; by minute 75, stop adding features.

## Dependency Backlog

| Task | Blocked by | Completion evidence |
| --- | --- | --- |
| Tooling/context setup | Human approval | Skill discovery and tracker persistence |
| Local model capability spike | Download/setup | Local endpoint, tool call, validated result |
| News contract and fixtures | Approved specification | Provenance-preserving payload |
| Read-only news MCP | Contract | Direct invocation and source tests |
| Digest agent/API | Model spike and news MCP | Actual model-chosen call and valid citation IDs |
| Digest UI | Contract | Finite cards and explicit states |
| Review and demo | API and UI | Tests, independent review, reproduction |

This table explains dependencies; once Beads is operational, actual issue status lives there.

## Sources and Next Session

Use [OpenAI RSS](https://openai.com/news/rss.xml) first; add
[Anthropic news](https://www.anthropic.com/news) if the adapter is cheap to verify.
Remaining sources: [xAI](https://x.ai/news), [Meta AI](https://ai.meta.com/blog/), and
[DeepMind](https://deepmind.google/blog/). Their feed support is not assumed.

Follow-up work: remaining adapters, persisted digests, scheduling, broader factuality/security
evaluations, optional swipe UX, tested team tracker sync, and deliberate deployment.

References: [PydanticAI Ollama](https://pydantic.dev/docs/ai/models/ollama/),
[MCP client](https://pydantic.dev/docs/ai/mcp/client/),
[Beads](https://github.com/gastownhall/beads), and
[VS Code skills](https://code.visualstudio.com/docs/copilot/customization/agent-skills).