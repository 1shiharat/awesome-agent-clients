# Awesome Agent Clients [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of clients and orchestrators for AI coding agents — the desktop, terminal, mobile, web, and IDE apps that **run, manage, and orchestrate** agents like Claude Code, OpenAI Codex, Gemini CLI, OpenCode, Aider, and Cursor CLI.

The last couple of years turned "AI coding agent" from a single chat box into a *fleet*. The tools below are the cockpits: they launch agents, isolate each one in its own git worktree or sandbox, review the diffs, and increasingly let you steer the whole thing from your phone. This list is about the **cockpits, not the agents** — the agents themselves live in [Related](#related-agents-frameworks--protocols).

## Contents

- [Legend](#legend)
- [Desktop & multi-platform clients](#desktop--multi-platform-clients)
- [Terminal & CLI orchestrators](#terminal--cli-orchestrators)
- [IDE & editor plugins](#ide--editor-plugins)
- [Web & self-hosted dashboards](#web--self-hosted-dashboards)
- [Cloud & hosted control planes](#cloud--hosted-control-planes)
- [Session viewers & companion tools](#session-viewers--companion-tools)
- [Archived & notable](#archived--notable)
- [Related: agents, frameworks & protocols](#related-agents-frameworks--protocols)
- [Contributing](#contributing)
- [A note on data quality](#a-note-on-data-quality)

## Legend

Each entry has a metadata sub-line: `repo` · license · platforms · *Distinctive:* what sets it apart.

- 🔓 open source · 🟡 source-available / open-core · 🔒 closed-source
- **MCP** = supports the [Model Context Protocol](https://modelcontextprotocol.io) · **ACP** = supports the [Agent Client Protocol](https://agentclientprotocol.com)
- "Agents" lists the *external* coding agents a tool can drive.

---

## Desktop & multi-platform clients

Native or Electron apps that run on the desktop, most with mobile/web companions.

- [Orca](https://www.onorca.dev/) — Agent Development Environment that runs many CLI coding agents side by side, each with its own git worktree, terminal, and browser tab. 🔓
  - `stablyai/orca` · MIT · macOS/Windows/Linux/iOS/Android/CLI · MCP · *Distinctive:* worktree-per-task + "Design Mode" Chromium capture, mobile companion to steer agents, SSH remote worktrees, GitHub/Linear integration. Drives 25+ agents (Claude Code, Codex, OpenCode, Cursor CLI, …).
- [Paseo](https://paseo.sh/) — Self-hosted daemon that runs ~39 coding agents, with thin desktop/mobile/web/CLI clients connecting to it. 🔓
  - `getpaseo/paseo` · AGPL-3.0 · macOS/iOS/Android/Web/CLI · MCP · *Distinctive:* full mobile feature-parity, on-device voice, E2E-encrypted remote relay, orchestration skills (`/paseo-handoff`, `/paseo-loop`, `/paseo-committee`).
- [Conductor](https://www.conductor.build/) — macOS app (Melty Labs) that runs multiple agents in parallel, each in an isolated workspace with its own branch, terminal, and diff. 🔒
  - `closed-source` · macOS · MCP · Claude Code/Codex/Cursor/OpenCode · *Distinctive:* built-in diff review + merge, create a workspace straight from a GitHub issue.
- [Sculptor](https://imbue.com/sculptor/) — Imbue's desktop app that runs agents in parallel inside isolated containers and syncs their work back to your local repo. 🔓
  - `imbue-ai/sculptor` · MIT · macOS/Linux · Claude Code/Codex · *Distinctive:* container isolation (instead of worktrees), "Pairing Mode" sync into your IDE, code-issue suggestions that launch fix agents.
- [Superset](https://superset.sh/) — Desktop workspace that runs many CLI agents in parallel, each in its own git worktree, with a mobile-friendly web companion. 🟡
  - `superset-sh/superset` · Elastic License 2.0 · macOS/Web/mobile-web · MCP · *Distinctive:* MCP server for programmatic task control, "cloud workspaces" pointing at any machine on your network, phone monitoring.
- [AgentsRoom](https://agentsroom.dev/) — Desktop app (with iOS/Android companions) that orchestrates CLI agents across projects as native local processes with worktree isolation. 🔒
  - `closed-source` (org: `AgentsRoomDev`) · macOS/Windows/Linux/iOS/Android · MCP · Claude Code/Codex/OpenCode/Gemini CLI/Aider/Grok/Mistral · *Distinctive:* 14 specialized agent roles, "Agent Teams" handoff canvas, kanban backlog (incl. public remote-submission), E2E-encrypted mobile sync.
- [AgentsMesh](https://agentsmesh.ai/) — Self-hosted runner fleet that runs terminal agents across multiple machines from one console (web/desktop/iOS/CLI). 🟡
  - `AgentsMesh/AgentsMesh` · BSL-1.1 (→ GPL-2.0) · Web/Desktop/iOS/CLI · MCP · Claude Code/Codex/Gemini CLI/Aider/OpenCode · *Distinctive:* per-pod worktree sandboxes across a machine fleet, "Autopilot" control agent, pod-to-pod Mesh & Channels with @mentions.
- [Parallel Code](https://github.com/johannesjo/parallel-code) — Desktop app that dispatches multiple agent CLIs in parallel, each in its own worktree, with diff review and selective merge. 🔓
  - `johannesjo/parallel-code` · MIT · macOS/Linux · Claude Code/Codex/Gemini CLI/Antigravity/Copilot · *Distinctive:* inline diff comments + per-commit navigation, PR CI watcher, Docker sandboxing, mobile monitoring via QR over Wi-Fi/Tailscale.
- [emdash](https://emdash.sh/) — Desktop app for running 25+ coding-agent CLIs in parallel, each isolated in its own git worktree. 🔓
  - `generalaction/emdash` · Apache-2.0 · macOS/Windows/Linux · *Distinctive:* side-by-side cross-agent diff review, PR create/merge + CI inspection, issue import from Linear/GitHub/Jira/GitLab/Asana.
- [1code](https://1code.dev/) — Open-core desktop/web client that runs Claude Code and Codex locally or in cloud sandboxes with worktree isolation. 🟡
  - `21st-dev/1code` · Apache-2.0 (open-core) · macOS/Windows/Linux/Web/PWA · Claude Code/Codex · *Distinctive:* worktree-per-session + kanban, background/cloud sandbox execution, rollback from any message, PWA mobile control.
- [mux](https://mux.coder.com/) — Coder's desktop/browser app for running many agents in parallel in isolated workspaces, with Local / Worktree / SSH runtimes. 🔓
  - `coder/mux` · AGPL-3.0 · macOS/Linux/Web/browser-ext/VSCode · *Distinctive:* runs its own model-agnostic agent loop, "Best of N" sub-agent fan-out, git divergence/conflict visualization, mobile via server mode.
- [Cline](https://cline.bot/) — Autonomous coding agent whose companion **Kanban** app orchestrates parallel CLI agents in isolated git worktrees. 🔓
  - `cline/cline` (orchestrator: `cline/kanban`) · Apache-2.0 · VSCode/JetBrains/CLI/Web · MCP · drives Claude Code/Codex/Cline CLI · *Distinctive:* kanban board for parallel agents, worktree isolation per task, task dependency chains with auto-commit. (List entry = the Kanban orchestrator; core Cline is the agent.)
- [Agent Teams AI](https://agentteams.live/) — Desktop app that orchestrates teams of coding agents that message each other and review one another's code. 🔓
  - `777genius/agent-teams-ai` · AGPL-3.0 · macOS/Windows/Linux · Claude Code/Codex/OpenCode · *Distinctive:* agent-to-agent + cross-team messaging, hunk-level accept/reject diff review, 5-column kanban, live per-agent CPU/RAM dashboard.
- [claude-code-by-agents](https://claudecode.run/) — Native Swift macOS/iOS app that coordinates multiple Claude Code agents across local and remote machines via @mention routing. 🔓
  - `baryhuang/claude-code-by-agents` · MIT · macOS/iOS/CLI · Claude Code · *Distinctive:* @mention routing to named agents, cross-machine coordination, iMessage-style 2-pane native app.
- [Clave](https://github.com/codika-io/clave) — macOS app for running multiple agent CLI sessions side by side in split/grid layouts. 🔓
  - `codika-io/clave` · MIT · macOS · Claude Code/Gemini CLI/Codex · *Distinctive:* split/grid PTY layouts, "MagicSync" one-click pull/stage/AI-commit/push, SSH/SFTP remote-host execution, prompt queueing.
- [AI Maestro](https://github.com/23blocks-OS/ai-maestro) — Orchestration platform for managing terminal agents across machines, with a dashboard, persistent memory, and inter-agent messaging. 🔓
  - `23blocks-OS/ai-maestro` · MIT · macOS/Linux/Windows(WSL2)/Web/CLI · *Distinctive:* multi-machine peer mesh with auto-discovery, signed Agent Messaging Protocol, code-graph visualization, kanban with dependencies, Slack/Discord/WhatsApp gateways.
- [Dorothy](https://github.com/Charlie85270/Dorothy) — Desktop app that orchestrates Claude Code, Codex, and Gemini in parallel across projects, with a kanban board and a meta-orchestrator agent. 🔓
  - `Charlie85270/Dorothy` · MIT · macOS/Linux · Claude Code/Codex/Gemini · MCP · *Distinctive:* "Super Agent" meta-orchestrator, 5 bundled MCP servers, Telegram/Slack remote control, cron-based autonomous runs.
- [VibeCraft](https://github.com/rayzhudev/vibecraft) — Electron app that manages coding agents on an RTS-style infinite canvas alongside folders, terminals, and browser panels. 🔓
  - `rayzhudev/vibecraft` · Apache-2.0 · macOS/Windows/Linux · Claude Code/Codex · *Distinctive:* infinite pannable canvas with agents as color-coded units, per-agent terminals + git-worktree actions on folder entities.
- [CodePilot](https://github.com/op7418/CodePilot) — Cross-platform desktop client that wraps the Claude Code CLI for file/terminal/git work, with multi-provider models and messaging-app remote control. 🟡
  - `op7418/CodePilot` · BSL-1.1 (→ Apache-2.0) · macOS/Windows/Linux · Claude Code · MCP · *Distinctive:* remote control via Telegram/Feishu/Discord/QQ/WeChat, 17+ model providers with mid-thread switching, MCP runtime dashboard, cron scheduler.
- [opcode](https://github.com/winfunc/opcode) — GUI toolkit for Claude Code: manage sessions, build custom CC agents, run background tasks, configure MCP, and review checkpoints. 🔓
  - `winfunc/opcode` · AGPL-3.0 · macOS/Windows/Linux · Claude Code · MCP · *Distinctive:* custom CC-agent builder, usage analytics, checkpoint timeline/fork. (Tauri app; verify release cadence.)
- [Constellagent](https://constellagent.vercel.app/) — macOS app for running multiple Claude Code sessions in parallel, each with its own terminal, editor, and isolated worktree. 🔓
  - `owengretzinger/constellagent` · license unconfirmed · macOS · Claude Code · *Distinctive:* worktree-per-agent in one window, context-collapsing diff viewer, GitHub PR-status badges, cron automations with sleep/wake recovery.

## Terminal & CLI orchestrators

TUI dashboards and CLI-first tools that spawn and coordinate agents in panes, tmux, and worktrees.

- [cmux](https://cmux.com/) — Native macOS terminal (libghostty) for running and organizing terminal agents in parallel with splits and agent-aware notifications. 🔓
  - `manaflow-ai/cmux` · GPL-3.0-or-later · macOS (+ iOS companion, beta) · *Distinctive:* OSC 9/99/777 notification rings/badges, scriptable embedded browser, `cmux claude-teams` teammate mode, SSH remote. Runs any terminal agent (Claude Code, Codex, OpenCode, Gemini CLI, Aider, Goose, …).
- [Claude Squad](https://smtg-ai.github.io/claude-squad/) — Terminal TUI that manages multiple agent instances in parallel, each in its own git worktree and tmux session. 🔓
  - `smtg-ai/claude-squad` · AGPL-3.0 · macOS/Linux/TUI · Claude Code/Codex/Gemini CLI/Aider/OpenCode/Amp · *Distinctive:* worktree + tmux isolation per session, diff-tab review, experimental yolo/auto-accept background mode.
- [amux](https://github.com/andyrewlee/amux) — Terminal UI for running multiple agents in parallel, each isolated in its own worktree and tmux session. 🔓
  - `andyrewlee/amux` · MIT · macOS/Linux/TUI · Claude Code/Codex/Gemini CLI/Amp/OpenCode/Droid · *Distinctive:* per-agent tmux isolation, integrated diff viewing, trust-gated config scripts, pprof/PTY tracing (Go).
- [OpenKanban](https://github.com/TechDufus/openkanban) — Terminal-UI kanban board where each ticket runs in its own git worktree with an embedded agent terminal. 🔓
  - `TechDufus/openkanban` · AGPL-3.0 · macOS/Linux/TUI · OpenCode/Claude Code/Gemini CLI/Codex/Aider · *Distinctive:* kanban-in-the-terminal, ticket = worktree + agent terminal, multi-project unified board (Go).
- [AgentBox](https://agent-box.sh/) — CLI that runs multiple agents in parallel, each isolated in its own sandboxed VM locally (Docker) or in the cloud. 🔓
  - `madarco/agentbox` · MIT · macOS/Linux/CLI · Claude Code/Codex/OpenCode · *Distinctive:* "teleports" your project into a sandbox VM (Docker/OrbStack or Hetzner/Vercel/Daytona/E2B), sub-second checkpoint startup, VNC + tunnels.
- [Supacode](https://supacode.sh/) — Native macOS command center (libghostty) for running 50+ CLI agents in parallel, each in its own git worktree. 🟡
  - `supabitapp/supacode` · FSL-1.1-ALv2 (→ Apache-2.0) · macOS · *Distinctive:* native (no Electron), GitHub-native PR/CI/conflict resolution from the terminal.
- [dux](https://getdux.app/) — Three-pane TUI for running multiple agent CLIs in parallel, each in its own worktree, with a live git staging workflow. 🔓
  - `patrickdappollonio/dux` · MIT · macOS/Linux/TUI · Claude Code/Codex/OpenCode/+ · *Distinctive:* wraps the real CLIs so MCP/hooks/skills keep working, syntax-highlighted diffs + AI commit messages, spawn from a PR number via `gh`, session forking (Rust).
- [Agent Deck](https://github.com/asheshgoplani/agent-deck) — Terminal "mission control" that runs, organizes, forks, and autonomously monitors many agent sessions across projects. 🔓
  - `asheshgoplani/agent-deck` · MIT · TUI/CLI/Web/macOS/Linux/Windows · MCP · Claude Code/Gemini CLI/OpenCode/Codex/Copilot/Crush · *Distinctive:* "Conductors" for autonomous monitoring/escalation, worktree + Docker isolation, Telegram/Slack control, remote SSH instances.
- [Gas Town](https://github.com/gastownhall/gastown) — Steve Yegge's multi-agent orchestration system coordinating parallel agents with git-backed work state and a watchdog hierarchy. 🔓
  - `gastownhall/gastown` · MIT · CLI/TUI/Web · MCP · Claude Code/Copilot/Codex/Gemini/Cursor/Amp/OpenCode/Pi · *Distinctive:* role hierarchy (Mayor → workers), "beads" git-backed issue tracker as shared memory, bors-style verifying merge queue (Go; experimental).
- [ntm](https://github.com/Dicklesworthstone/ntm) — Go CLI that turns tmux into a control plane for spawning, tiling, and coordinating agents across panes. 🔓
  - `Dicklesworthstone/ntm` · MIT · CLI/TUI/Web · *Distinctive:* worktree + file-reservation locks, "Agent Mail" coordination, two-person approval for high-risk actions, REST/SSE/WebSocket API for remote control. Drives Claude Code/Codex/Antigravity.
- [Agent of Empires](https://github.com/njbrake/agent-of-empires) — Session manager for agents on Linux/macOS, controlled from a terminal TUI or a browser/PWA dashboard. 🔓
  - `njbrake/agent-of-empires` · MIT · CLI/TUI/Web/PWA · ACP · 13 agents incl. Claude Code/OpenCode/Codex/Gemini CLI/Cursor CLI/Copilot · *Distinctive:* tmux + worktrees + Docker sandboxing, ACP-rendered structured agent state in the dashboard, phone access over HTTPS with QR + passphrase (Rust; backed by Mozilla.ai).
- [Antfarm](https://www.antfarm.cool/) — TypeScript CLI that orchestrates teams of specialized agents through deterministic YAML-defined workflows. 🔓
  - `snarktank/antfarm` · MIT · CLI/Web · *Distinctive:* bundled feature-dev / bug-fix / security-audit workflows, inter-agent verification (agents don't self-approve), fresh context per step, web dashboard. (Runs on the OpenClaw runtime.)
- [Scion](https://googlecloudplatform.github.io/scion/) — Experimental host-side CLI + hub that orchestrates agents in isolated containers, each with its own worktree and credentials. 🔓
  - `GoogleCloudPlatform/scion` · Apache-2.0 · CLI/Web/Linux/Cloud · Claude Code/Gemini CLI/Codex/OpenCode · *Distinctive:* container + worktree + credential isolation per agent, agent-to-agent messaging pipeline with flow tracing, deploy to Docker/Podman/VMs/Kubernetes (experimental, not an official Google product).
- [Bernstein](https://bernstein.run/) — Deterministic Python orchestrator that decomposes a goal and runs CLI agents in parallel worktrees, verifying and merging with an audit chain. 🔓
  - `chernistry/bernstein` · Apache-2.0 · CLI/Web/VSCode/Cloud · MCP · 44 agent adapters (Claude Code/Codex/Gemini CLI/Copilot/Aider/Goose/…) · *Distinctive:* zero-LLM deterministic scheduler, verification gates (tests/lint/types/PII), HMAC-SHA256 audit chain + Ed25519-signed agent cards, optional Cloudflare Workers execution.
- [Agent Orchestrator](https://github.com/ComposioHQ/agent-orchestrator) — Composio's agentic orchestrator that spawns fleets of parallel agents, each in its own worktree, and autonomously handles CI fixes, conflicts, and reviews. 🔓
  - `ComposioHQ/agent-orchestrator` · MIT · CLI/Web · Claude Code/Codex/Aider/Cursor/OpenCode/Kimicode · *Distinctive:* runtime-agnostic (tmux/ConPTY/Docker), tracker-agnostic (GitHub/Linear/GitLab), autonomous CI repair + auto-merge, web dashboard with Tailscale remote access.

## IDE & editor plugins

Agents and orchestrators that live inside your editor.

- [Obsidian Agent Client](https://rait-09.github.io/obsidian-agent-client/) — Obsidian plugin that embeds external coding agents inside your vault via the Agent Client Protocol. 🔓
  - `RAIT-09/obsidian-agent-client` · Apache-2.0 · Desktop (Obsidian) · ACP + MCP · Claude Code/Codex/Gemini CLI/OpenCode/Qwen/Kiro/Mistral · *Distinctive:* `@note` mentions as context, multiple simultaneous agent sessions, chat export to Markdown, ACP-native.
- [CodeCompanion.nvim](https://codecompanion.olimorris.dev/) — Neovim plugin that connects to LLM providers and to external agents via ACP from a chat buffer. 🔓
  - `olimorris/codecompanion.nvim` · Apache-2.0 · Neovim · MCP + ACP · Claude Code/Codex/Copilot CLI/Gemini CLI/Goose/Cursor CLI/OpenCode/+ · *Distinctive:* inline buffer transforms, editor-context variables, multiple concurrent chats, broad ACP-agent support.
- [Agentic.nvim](https://github.com/carlos-algms/agentic.nvim) — Neovim plugin providing an in-editor chat interface to any ACP-compatible coding agent. 🔓
  - `carlos-algms/agentic.nvim` · MIT · Neovim · ACP · Claude Code/Gemini/Codex/OpenCode/Cursor/Copilot/Cline/Goose/+ · *Distinctive:* provider switching without losing history, session restore between Neovim and terminal, interactive tool-call approval.
- [Clauditor](https://plugins.jetbrains.com/plugin/30981-clauditor) — JetBrains plugin for managing Claude Code sessions from the editor, with worktree isolation and session-aware diffing. 🔓
  - `bdkent/clauditor` · MIT · JetBrains · Claude Code · *Distinctive:* browse/resume/fork sessions as side-by-side editor tabs, worktree-per-session with PR/rebase controls, real-time status + context/rate-limit tracking, detects external Claude sessions.
- [CC GUI (Claude or Codex)](https://plugins.jetbrains.com/plugin/29342-cc-gui-claude-or-codex-) — JetBrains plugin providing a dual-engine GUI for the Claude Code and OpenAI Codex CLIs. 🔓
  - `zhukunpenglinyutong/jetbrains-cc-gui` · MIT · JetBrains · Claude Code/Codex · MCP · *Distinctive:* `@file` context, image input, conversation rewind, diff comparison + code jumping, skills slash-commands.
- [Claude Code Plus](https://plugins.jetbrains.com/plugin/28343-claude-code-plus) — JetBrains plugin providing a GUI for CLI coding agents inside IntelliJ-based IDEs. 🔓
  - `touwaeriol/claude-code-plus` · MIT · JetBrains · Claude Code (Codex/Gemini CLI per repo) · MCP · *Distinctive:* bundled Claude CLI (no separate install), `@`-mention file search, multi-session, tool-call visibility, click-to-open diffs.

## Web & self-hosted dashboards

Browser-first orchestrators you run locally or self-host.

- [Vibe Kanban](https://www.vibekanban.com/) — Kanban interface for planning, executing, and reviewing tasks across many agent CLIs, each task in an isolated worktree workspace. 🔓
  - `BloopAI/vibe-kanban` · Apache-2.0 · macOS/Web/CLI · Claude Code/Codex/Gemini CLI/Copilot/Amp/Cursor/OpenCode/Droid/Qwen · *Distinctive:* kanban planning, worktree-per-workspace with auto-cleanup, inline-comment diff review, built-in browser preview with device emulation (Rust + TS). (Community-maintained after Bloop's transition.)
- [T3 Code](https://t3.codes/) — Open-source web/desktop control plane (Theo / Ping) that orchestrates Codex, Claude Code, Cursor, and OpenCode from one interface. 🔓
  - `pingdotgg/t3code` · MIT · macOS/Windows/Linux/Web/CLI · *Distinctive:* switch model/agent mid-thread, per-thread git branch + checkpointing, one-button commit/push/PR with generated title/body/changelog, `npx t3@latest`. (Self-described "very early.")
- [Kanban Code](https://github.com/langwatch/kanban-code) — Native desktop app + CLI (LangWatch) for managing multiple Claude Code sessions via a kanban board. 🔓
  - `langwatch/kanban-code` · AGPL-3.0 · macOS/Windows/CLI · Claude Code · *Distinctive:* board driven by Claude Code hooks, worktree-per-card, SSH remote execution with Mutagen sync, Pushover phone/Watch notifications, `--json` CLI for master-agent orchestration.
- [Agent Viewer](https://github.com/hallucinogen/agent-viewer) — Web kanban board for spawning, monitoring, and messaging multiple Claude Code agents running in tmux. 🔓
  - `hallucinogen/agent-viewer` · license unconfirmed · macOS/Linux/Web/mobile (Tailscale) · Claude Code · *Distinctive:* spawn agents into tmux from a path + prompt, Running/Idle/Completed board, live ANSI terminal view, two-file vanilla-JS app.
- [Agent Kanban](https://agent-kanban.dev/) — Agent-first kanban board that treats agents as cryptographically identified team members who claim tasks and open PRs. 🟡
  - `saltbo/agent-kanban` · FSL-1.1-ALv2 (→ Apache-2.0) · CLI/Web · ACP · Claude Code/Codex/Gemini CLI/Copilot/Hermes · *Distinctive:* Ed25519 identity per agent, leader plans/assigns while workers ship PRs, agent-reviews-agent before human sign-off, deployable on Cloudflare Pages + D1.
- [Formic](https://github.com/rickywo/Formic) — Local-first web app that orchestrates Claude Code and Copilot CLI through a Brief → Plan → Declare → Execute → Review pipeline. 🔓
  - `rickywo/Formic` · MIT · Web/CLI · Claude Code/Copilot CLI · *Distinctive:* structured plan-execute-review pipeline, kanban stage columns, file-lease concurrency for safe parallel work, crash-resilient atomic persistence.
- [OpenGoat](https://github.com/marian2js/opengoat) — Platform for building hierarchical organizations of agents that coordinate work across many providers. 🔓
  - `marian2js/opengoat` · MIT · Web/CLI/Desktop · Claude Code/Codex/Cursor/Copilot CLI/OpenCode/Gemini CLI · *Distinctive:* manager→subordinate `reportsTo` hierarchy, strategy-based delegation, role-based skill assignment (built on the OpenClaw engine).
- [Catnip](https://github.com/wandb/catnip) — Self-hostable web service (Weights & Biases) that runs Claude Code in containerized worktree sandboxes, with a native iOS app. 🔓
  - `wandb/catnip` · Apache-2.0 · Web/CLI/iOS/Cloud · Claude Code · *Distinctive:* auto worktree creation for parallel agents, auto-commits to `refs/catnip/$NAME`, runs locally or via GitHub Codespaces/devcontainers, native iOS remote control.

## Cloud & hosted control planes

Hosted (or self-hostable) control planes that run agent fleets in the cloud.

- [Oz](https://www.warp.dev/oz) — Warp's orchestration platform that runs and monitors fleets of cloud coding agents across multiple harnesses. 🟡
  - `warpdotdev/warp` (client; Oz backend hosted) · MIT/AGPLv3 client · Cloud/Web/Desktop/CLI/Mobile · MCP · Claude Code/Codex/Warp Agent · *Distinctive:* interactive agents run locally while autonomous ones run in the cloud, self-hosted or Warp-managed, cron scheduling, multi-model routing, single-pane audit trails.
- [Centaur](https://centaur.run/) — Paradigm's self-hosted control plane that runs CLI agent harnesses inside isolated Kubernetes sandboxes, driven from Slack or an API. 🔓
  - `paradigmxyz/centaur` · Apache-2.0 / MIT · Cloud/CLI/Web · Claude Code/Codex/Amp · *Distinctive:* Slack-native multiplayer agent per thread, durable Postgres-persisted execution surviving restarts, credential injection without exposing secrets, per-conversation K8s sandbox.

## Session viewers & companion tools

These observe and analyze agent sessions — they don't launch or control agents — but pair well with the tools above.

- [AgentsView](https://www.agentsview.io/) — Local-first desktop/CLI/web tool that indexes coding-agent session logs with search, token/cost analytics, and AI-generated insights. 🔓
  - `kenn-io/agentsview` · MIT · macOS/Windows/Linux/CLI/Web · reads 20+ agents (Claude Code, Codex, Aider, Cursor, Gemini CLI, …) · *Distinctive:* FTS5 full-text search, per-model cost dashboards, real-time session streaming, optional Postgres team sync. (Observability only.)
- [Claude Code Kanban](https://github.com/NikiforovAll/claude-code-kanban) — Read-only web kanban that visualizes Claude Code task and subagent activity in real time by watching local files. 🔓
  - `NikiforovAll/claude-code-kanban` · MIT · Web · reads Claude Code · *Distinctive:* watches `~/.claude/tasks` via SSE, subagent/team tracking, dependency/critical-path view, waiting-for-user detection. Never writes to task files.
- [Claude Code Agent Monitor](https://hoangsonww.github.io/Claude-Code-Agent-Monitor/) — Self-hosted real-time dashboard for Claude Code sessions, tool usage, costs, and subagent orchestration via hooks. 🔓
  - `hoangsonww/Claude-Code-Agent-Monitor` · MIT · Web/macOS/Windows/VSCode/CLI · reads Claude Code · MCP · *Distinctive:* D3/Sankey/Mermaid DAG visualization, rules-based alerting + webhooks + Web Push, kanban status board. (Primarily observability.)

## Archived & notable

No longer actively maintained, but historically important reference points.

- [Crystal](https://github.com/stravu/crystal) — Electron app that ran multiple Claude Code/Codex sessions in parallel, each in its own worktree, with side-by-side comparison and diff review. 🔓 `stravu/crystal` · MIT · **archived (Feb 2026)**, superseded by the commercial Nimbalyst. Pioneered worktree-isolated multi-session Claude Code.
- [Terragon](https://github.com/terragon-labs/terragon-oss) — Hosted background-agent fleet orchestrator. 🔓 `terragon-labs/terragon-oss` · Apache-2.0 · **service shut down 2026-01-16**; repo is an unmaintained snapshot.
- [Claude Code Board](https://cc-board.cablate.com/) — Web kanban-style manager for multiple Claude Code CLI sessions. 🔓 `cablate/Claude-Code-Board` · MIT · **no longer maintained** (last update Jan 2026).

## Related: agents, frameworks & protocols

Not clients/orchestrators themselves, but the things the tools above manage and speak to.

**Coding agents (the things being orchestrated)**
- [Claude Code](https://github.com/anthropics/claude-code) · [OpenAI Codex](https://github.com/openai/codex) · [Gemini CLI](https://github.com/google-gemini/gemini-cli) · [OpenCode](https://github.com/sst/opencode) · [Aider](https://github.com/Aider-AI/aider) · [Cursor CLI](https://cursor.com/cli) · [Amp](https://ampcode.com/) · [Pi](https://github.com/parallel-web/pi)

**Agents that double as desktop apps (out of scope as clients)**
- [Goose](https://github.com/block/goose) — Block's extensible Rust agent that talks directly to LLMs and can act as an ACP server. Managed by Orca, Paseo, cmux, and others.
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) — Nous Research's general-purpose self-improving agent; targeted by Agent Kanban and AI Maestro via ACP.
- [OpenClaw](https://github.com/openclaw/openclaw) — Self-hosted personal assistant runtime; powers Antfarm and OpenGoat.

**Multi-agent frameworks & infrastructure (adjacent)**
- [Symphony](https://github.com/openai/symphony) — OpenAI's orchestration spec + Elixir reference impl that runs a Codex session per tracker issue.
- [FleetQ](https://github.com/escapeboy/agent-fleet-o) — General-purpose multi-agent DAG/workflow platform with a native MCP server.
- [AgentTier](https://github.com/agenttier/agenttier) — Kubernetes-native sandbox-as-a-service for running agents (infrastructure layer).

**Protocols**
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) — connects agents to tools/data; the dominant integration protocol here.
- [Agent Client Protocol (ACP)](https://agentclientprotocol.com) — Zed's protocol for embedding agents in editor/host clients; used by Obsidian Agent Client, CodeCompanion.nvim, Agentic.nvim, Agent of Empires, and Agent Kanban.

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for the inclusion
criteria and entry format, then open a PR or [suggest a tool](../../issues/new?template=suggest-a-tool.md).
The fastest way to get an entry corrected is a PR with a source link.

## A note on data quality

This list was compiled from a structured research pass in **June 2026**. Every tool was confirmed
to exist via an official site and/or public repository, but most entries have **not been
independently re-verified**, and metadata such as star counts, version numbers, license details,
and "supported agents" are point-in-time and may be stale or incomplete. Treat them as a starting
point, verify before you depend on a specific claim, and please send corrections. See
[docs/awesome-agent-clients-design.md](docs/awesome-agent-clients-design.md) for scope rules and provenance.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

To the extent possible under law, the contributors have waived all copyright and related or
neighboring rights to this work. See [LICENSE](LICENSE) (CC0-1.0).
