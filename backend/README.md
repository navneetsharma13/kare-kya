# Backend Implementation Area

Status: placeholder; no Python project, packages, endpoints, or tests exist yet.

Future responsibilities:
- FastAPI lifecycle and health/news/refresh endpoints.
- Typed source and digest contracts.
- Deterministic publisher adapters, provenance, dates, and deduplication.
- Read-only news MCP server and bounded local PydanticAI/Ollama agent.
- Focused unit tests with model stubs and source fixtures.

Proposed organization after implementation begins:

```text
app/
  main.py       API and service lifecycle
  schemas.py    Validated contracts
  sources.py    Source registry and adapters
  news_mcp.py   Read-only MCP tool
  digest.py     Local agent and cache
tests/          Backend-specific tests
```

Create the dependency manifest and lockfile after approved scaffolding.
Document verified install, focused-test, lint, start, and stop commands here.
See [architecture](../docs/architecture.md) and [project rules](../AGENTS.md).