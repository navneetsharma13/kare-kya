# Developer Onboarding Kit

Use this kit to give a coding assistant the same project workflow without copying
another developer's personal settings, private skills, credentials, or machine paths.
It guides setup; it does not install software or guarantee identical model capability.

## Start in a Few Prompts

1. Get this repository from GitHub after the scaffold is committed and pushed.
   Open its root folder in your editor, not a parent folder or a clone inside another clone.
2. Sign into your own approved coding assistant. In VS Code, enable your chosen
   Copilot installation; for other editors, check their support for instructions/skills.
3. Attach [bootstrap.prompt.md](bootstrap.prompt.md) to the assistant and say:

   ```text
   Follow the attached developer bootstrap prompt. Start with a read-only readiness
   check for this repository. Do not install anything or change files until I approve.
   ```

4. Review the readiness report and approve only the specific missing setup you want:

   ```text
   Proceed with the approved setup items from your report. Preserve existing files,
   verify each item, and stop before tracker initialization or app implementation.
   ```

5. Start your assigned task:

   ```text
   Plan my assigned task using the shared project context. Identify the files I own,
   acceptance criteria, dependencies, and the first falsifying check. Wait for approval.
   ```

In VS Code Copilot, `/onboard-developer` is a discoverable shortcut to the same
bootstrap prompt. `/start-task` prepares a plan; `/retrospective` reflects on evidence.
If slash commands or agent selection are unavailable, attach the referenced files
manually. Do not assume those features are present in every editor.

## What Travels With the Repository

| Shared artifact | Purpose |
| --- | --- |
| [Project rules](../AGENTS.md) | Scope, ownership, approvals, and runtime safety |
| [Copilot entry point](../.github/copilot-instructions.md) | Discover shared context |
| [Planner](../.github/agents/planner.agent.md) | Read-only task planning |
| [Reviewer](../.github/agents/reviewer.agent.md) | Independent read-only review |
| [Beads skill](../.github/skills/beads-workflow/SKILL.md) | Canonical task lifecycle |
| [Source skill](../.github/skills/news-source/SKILL.md) | News adapters and MCP safety |
| [Verification skill](../.github/skills/verify-change/SKILL.md) | Tests and acceptance evidence |
| [Workshop](../docs/workshop.md) | Local setup and team coordination |

Personal assistant subscriptions, organizational permissions, model downloads,
local executables, and authenticated MCP connections do not travel with Git.
This kit neither copies them nor overrides organization policies.

## Ready Means Verified

- The assistant can name the repository root and report existing changes.
- It has actually read the applicable shared rules and a relevant skill.
- Needed tools have recorded versions or explicit missing/blocked status.
- Editor customization discovery is tested, or manual attachment is recorded as a fallback.
- The tracker operator and assigned edit area are agreed; no competing Beads database is created.
- Local inference and MCP readiness are separately tested before runtime work.

Frontend or documentation tasks can proceed without Ollama on every machine.
Backend live-inference work needs a verified local model; fixtures/stubs remain available
for deterministic tests. Do not expose a teammate's Ollama service publicly.

## Reuse for Another Project

The bootstrap prompt also works as attached context in a different repository.
Existing project instructions take precedence. Have the assistant propose a small,
project-specific context kit, approve its locations, and only then create it.
Do not copy Kare-Kya's stack, news tools, or local-only inference policy into an unrelated
project without a human decision. Never overwrite existing customization files wholesale.