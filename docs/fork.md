# Agentic Office

Back to the [README](../README.md).

This repository starts from [AgentSystemLabs/agent-office](https://github.com/AgentSystemLabs/agent-office) at `852e2ab28c4f3f31bffdf4b20353bd119c9d3270` and preserves its history and MIT notice. The destination repository's original license notice is retained too.

## Run this checkout

Use Node.js 20 or later, Git, and the agent CLIs described in [Choosing an agent](agents.md). GitHub boards and project cloning also need the GitHub CLI authenticated on the office machine.

```sh
git clone https://github.com/aaravkalia-88/agentic-office.git
cd agentic-office
npm ci
npm start
```

`npm ci` builds the client and server through the existing `prepare` script. For development, run `npm run dev`. For checks, run `npm run typecheck`, `npm test`, and `npm run build`.

The inherited installers, update mechanism, release badges, and many deployment examples still refer to the upstream distribution. Use the source checkout above for this fork. Fork release wiring is part of the [expansion plan](../plans/office-manager.md); a fork-specific release has not been published.

## Expansion status

The existing office has manual hiring, agent providers, worker-management hooks, boards, and a queue. The following are planned additions:

- An office manager that decomposes work, chooses specialists, schedules dependencies, and checks their results.
- A complete, versioned [ECC and YouTube catalog](agent-catalog.md), with role prompts kept separate from model and runtime selection.
- A mandatory OpenRouter free-only lane for low-effort manager tasks. Unavailable free capacity keeps work waiting; it never silently switches to a paid model.
- Manager controls and task visibility in both the 3D office and `/lite`.

See the [implementation sequence and acceptance criteria](../plans/office-manager.md). These capabilities are not enabled by this documentation.
