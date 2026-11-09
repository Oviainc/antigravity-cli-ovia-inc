# Ovia Inc — Antigravity CLI (fork of google-antigravity/antigravity-cli)

<img src="agy-cli-demo.gif" alt="Ovia Inc — Antigravity CLI demo animation from the upstream project assets: the agent harness working inside a terminal" width="100%"/>

We maintain this fork of [google-antigravity/antigravity-cli](https://github.com/google-antigravity/antigravity-cli), the terminal surface of the Antigravity agent harness. Upstream credit: the google-antigravity team and contributors. Licence: no LICENSE file is present in this repository or upstream — use is governed by the upstream Terms of Service linked in the README below, preserved as received.

**Our main site:** https://oviainc.github.io/ai-services/

**Upstream project site:** https://antigravity.google/product/antigravity-cli

**Upstream documentation:** https://antigravity.google/docs/cli/overview

## What this is

Antigravity CLI puts an agent harness in the terminal: the tool understands a codebase, makes edits with permission, and executes commands, without leaving the keyboard-driven flow of a shell session. The upstream README below describes the surface — multi-step reasoning, multi-file editing, tool calling, and persistent history, in a terminal user interface optimized for keyboard-first work and remote SSH sessions with minimal resource overhead.

One structural fact shapes how the fork is read: this repository is the public documentation and examples surface for the CLI, not its source tree. The repo carries the README, a detailed per-release changelog, the demo animation above, and two worked customization examples — a dynamic statusline script that renders agent state, version-control info, and context-window usage as a progress bar, and a terminal-title script that reflects the session state. The CLI itself installs from upstream's published install scripts, as the README below sets out. The same core agent engine and the same settings run in both the CLI and the Antigravity 2.0 desktop application, preferences and permissions sync between them, and a terminal session can be exported to the desktop application to continue there.

## Story

Upstream opened the project under the google-antigravity organization in May 2026, as the terminal companion to the Antigravity 2.0 agent platform: the same agent engine, re-shaped for speed, keyboard efficiency, and low overhead instead of visual orchestration. The changelog tells the development story in unusual detail — release by release, the surface gained skills and slash commands, custom subagents, hooks, MCP tool support, model switching mid-conversation, and steady hardening of the agent loop.

We forked the project into the Oviainc collection on September 17, 2026, at the September 16, 2026 upstream snapshot, version 1.2.4. Since the fork point, upstream has kept shipping at pace — version 1.5.3 at the time of this pass — and the fork keeps the 1.2.4 form deliberately for now, as the reference point our evaluation started from.

The fork sits in our collection in the coding-agent tooling group, beside the context tooling, interface, and database tooling forks we evaluate side by side. Where those projects feed or extend an agent, this one is a complete vendor-built terminal harness, held as a benchmark for how a production agent surface behaves. What we evaluate here is the terminal form itself — a full agent loop that stays usable over SSH and on modest hardware; the permission model around edits and command execution; how settings, history, and sessions carry between a terminal and a desktop surface sharing one engine; and the customization layer shown in the examples, where a statusline surfaces context-window usage — a small, direct piece of context engineering, making the agent's remaining room visible at a glance.

Where the project fits our work:

- **AI agents** — the core fit. A production terminal harness from a major vendor is a reference point for every agent surface we run or build: how the loop handles tool errors, how permissions are asked, and how sessions resume.
- **Context engineering** — the statusline example renders context usage as a live progress bar, and the changelog's work on customization budgets and history shows context treated as a managed resource. Both speak directly to our practice.
- **Business intelligence and data** — data work runs in terminals: pipelines, queries, and transformations on remote machines over SSH. A low-overhead agent surface that works well in exactly that setting is the relevant form for agent-assisted data work.
- **Virtual production** — production pipelines are terminal-heavy and often remote, on render and stage infrastructure where a heavyweight desktop application does not fit. A keyboard-first agent surface with minimal overhead matches that environment.

## Modifications by Ovia Inc

Documentation only. Upstream code and content are unchanged from the fork point, except for documentation notes added in November 2026: a modification reference on November 4, 2026, replaced by this expanded treatment (Ovia section, story, and picture) on November 9, 2026. Where a later commit in this repository says otherwise, that commit governs.

## Sync status

This fork carries documentation commits of our own on top of the September 16, 2026 fork-point snapshot (version 1.2.4), and upstream is 38 commits ahead, at version 1.5.3. No sync has been applied on this pass: keeping a vendor harness current is a deliberate step, taken after a review of what changed between releases, rather than an automatic merge — and the fork's value as an evaluation reference depends on knowing exactly which snapshot is under review. The upstream README below is the fork-point version, preserved as received.

## Related repositories

- [ai-services](https://github.com/Oviainc/ai-services) — our flagship site: AI agents, machine learning in production, and AI products for business
- [Graft-ovia-inc](https://github.com/Oviainc/Graft-ovia-inc) — a local context graph for coding agents, from the same tooling group
- [agents-cli-ovia-inc-studio-labs](https://github.com/Oviainc/agents-cli-ovia-inc-studio-labs) — the CLI and skills for building, evaluating, and deploying agents, evaluated alongside this fork
- [agency-agents-ovia-inc](https://github.com/Oviainc/agency-agents-ovia-inc) — the roster layer of the agent collection: specialized agent definitions organized by division
- [mcp-toolbox-ovia-inc](https://github.com/Oviainc/mcp-toolbox-ovia-inc) — a toolbox that connects agents to databases, from the same tooling group

## Working with us

Start from our site: https://oviainc.github.io/ai-services/ — the contact form there is the fastest way to reach us.

## Licence

No LICENSE file is present in this repository, and none is recorded upstream. The upstream README below links the governing Terms of Service and Privacy Policy; those terms stand as received, and upstream credit remains with the upstream contributors.

---

Ovia Inc — Artificial Intelligence & Context Engineering. Based in Canada, working wherever the work is.

---

# Antigravity CLI

Antigravity CLI understands your codebase, makes edits with your permission, and executes commands — right from your terminal.

- **Official Docs**: [antigravity.google/docs/cli/overview](https://antigravity.google/docs/cli/overview)
- **Official Website**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

Antigravity CLI brings the core capabilities of Antigravity 2.0 (multi-step reasoning, multi-file editing, tool calling, and persistent history) directly to your terminal. It is optimized for keyboard-driven workflows and remote SSH sessions with minimal resource overhead.

---

## Features at a Glance

| Feature | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **Primary Focus** | Speed, keyboard efficiency, low overhead | Comprehensiveness, visual orchestration, project management |
| **Interface** | Terminal User Interface (TUI) | Full Rich GUI Application |
| **Workflows** | SSH/Remote sessions, keyboard-first | Local workspaces, heavy orchestration |
| **Agent Engine** | Shared Core Agent Engine | Shared Core Agent Engine |

---

## Integration

- **Shared Agent Engine**: Both interfaces run on the same core agent engine. Improvements automatically apply to both.
- **Shared Settings**: Preferences and permissions sync bidirectionally.
- **Session Export**: Export terminal sessions to the Antigravity 2.0 GUI to continue working.

---

## Installation

### macOS / Linux
```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

### Windows PowerShell
```powershell
irm https://antigravity.google/cli/install.ps1 | iex
```

### Windows CMD
```cmd
curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd
```

## Usage

After installation, start Antigravity CLI by running:

```bash
agy
```

---

## Authentication

The CLI authenticates via the system keyring, falling back to Google Sign-In if no active session exists.

- **Local**: Automatically opens your default browser.
- **Remote / SSH**: Detects SSH sessions and prints an authorization URL to complete login locally.
- **Sign Out**: Run `/logout` to clear saved credentials.

> [!NOTE]
> For enterprise access, connect your GCP project during onboarding. See the Enterprise page for details.

---

## Terms of Service & Data Use

> [!WARNING]
> AI coding agents are known to have certain security risks, including autonomous code execution, data exfiltration, prompt injection, and supply chain risks. Ensure that you monitor and verify all actions taken by the agent.

By using Antigravity CLI, you agree to help improve the product by allowing Google to collect and use your Interactions data, subject to the Google Terms of Service and Google Privacy Policy. You can choose to opt out at any time via your settings.

### Legal & Privacy Links

- **Terms of Service**: [antigravity.google/terms](https://antigravity.google/terms)
- **Privacy Policy**: [policies.google.com/privacy](https://policies.google.com/privacy)
