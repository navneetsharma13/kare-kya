# Kare-Kya

A learning-first AI news application for people who do not work closely with AI.
Three developers will use a small news digest to practice agentic software development.

Status: context and folder scaffold only. No application, dependencies, tracker database,
model download, or running services have been created by this scaffold.

## Start Here

1. Read the [project rules](AGENTS.md).
2. Follow the [workshop plan](docs/workshop.md) to agree on ownership and setup.
3. Walk through the [development lifecycle](docs/lifecycle.md).
4. Approve the [application architecture](docs/architecture.md) before feature code.

Joining from another machine? Start with the [developer onboarding kit](developer-onboarding/README.md)
or run `/onboard-developer` in VS Code Copilot.

## Folder Map

```text
.github/
  copilot-instructions.md    Editor entry point to shared rules
  agents/                   Read-only planner and reviewer roles
  skills/                   Repeatable task, source, and verification workflows
  prompts/                  Start-task and retrospective prompts
docs/
  workshop.md               Two-hour agenda and local setup
  lifecycle.md              Requirements through delivery and operations
  architecture.md           Runtime boundaries and proposed data contracts
  decisions/                Architecture decision records
  evidence/                 Verification and human acceptance records
specs/                      Feature specifications and acceptance criteria
developer-onboarding/       Portable bootstrap prompt and teammate setup guide
backend/                    Future FastAPI, PydanticAI, and news MCP implementation
frontend/                   Future React/TypeScript/Vite implementation
fixtures/                   Explicitly labeled, provenance-preserving sample data
tests/                      Cross-component and end-to-end checks
```

The active project is the repository containing this file. The redundant empty
nested clone was removed; keep application folders directly under this root.

## Two Separate Agent Environments

- Development assistants use project instructions, skills, Beads, and code/test tools.
- The application agent uses local Ollama inference and read-only news MCP tools.
- Coding skills are not automatically loaded by the application runtime.

Proposed stack: Python/FastAPI/PydanticAI, React/TypeScript/Vite, Ollama Qwen3 4B,
and Beads. Verify installed versions and capability compatibility during setup.

## Working Agreement

Human-approved requirement -> issue -> plan -> small change -> focused test ->
independent review -> human acceptance -> delivery -> retrospective.

One person owns each task and edit area. One canonical Beads operator manages
the local tracker until cross-machine synchronization is tested.

See the [specification template](specs/feature-template.md),
[verification template](docs/evidence/verification-template.md), and
[decision template](docs/decisions/decision-template.md).