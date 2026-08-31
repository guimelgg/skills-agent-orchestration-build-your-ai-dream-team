# Agent team

Mona's Project Pulse dashboard will be built by a custom four-agent team,
orchestrated through GitHub Copilot CLI in a Codespace. The Orchestrator will
sequence the work, keep file ownership clear, and integrate the specialists'
results; the learner remains in control of all Git operations.

| Agent | Target model | Responsibility | Definition |
| --- | --- | --- | --- |
| Orchestrator | Claude Opus 4.7 (copilot) | Breaks the dashboard work into dependency-aware phases, delegates bounded file scopes to specialists, coordinates parallel work when safe, and verifies the integrated result. | `.github/agents/orchestrator.agent.md` |
| Planner | Claude Opus 4.7 (copilot) | Researches the repository and relevant documentation, then produces an implementation plan covering file assignments, dependencies, edge cases, validation, and open questions. It does not write code. | `.github/agents/planner.agent.md` |
| Coder | GPT-5.5 (copilot) | Implements the dashboard's code and logic with explicit errors and testable behavior. When assigned runnable-app support, it can also create a deterministic VS Code launch configuration that opens the dashboard. | `.github/agents/coder.agent.md` |
| Designer | Gemini 3.1 Pro (copilot) | Shapes the dashboard UI/UX, accessibility, information hierarchy, responsive interaction flow, and visual polish, including recognizable Project Pulse cards, status badges, and priority treatment. | `.github/agents/designer.agent.md` |

All specialists work only within the scopes assigned by the Orchestrator and do
not stage, commit, or push changes.
