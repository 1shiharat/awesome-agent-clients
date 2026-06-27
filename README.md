# Awesome Agent Clients [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

**English** | [日本語](README.ja.md)

> A curated list of clients and orchestrators for AI coding agents — the desktop, terminal, mobile, web, and IDE apps that **run, manage, and orchestrate** agents like Claude Code, OpenAI Codex, Gemini CLI, OpenCode, Aider, and Cursor CLI.

Over the last couple of years, working with AI coding agents went from chatting with one to running many in parallel. The tools below are where you run them: they launch agents, isolate each in its own git worktree or sandbox, review the diffs, and increasingly let you steer everything from your phone. This list is about **those tools, not the agents** — the agents themselves live in [Related](#related-agents-frameworks--protocols).

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

Each entry is one line:

> **[name](link)** ★badge 🔓 — what it does. `license` `platforms` `protocol` `agents`

- 🔓 open source · 🟡 source-available / open-core · 🔒 closed-source
- The ★ badge auto-updates via [shields.io](https://shields.io); **within each section tools are sorted by star count, most-adopted first**. Closed-source products have no badge.
- A license tag like `BSL-1.1→Apache-2.0` means it is source-available now and auto-converts to the named open license later.
- `MCP` / `ACP` mark supported protocols. The last tag lists the *external* coding agents a tool can drive (a count when there are many).
- Curation bar: tools with fewer than ~50 stars are held back (see [Contributing](#contributing)). Stars are a signal, not a verdict.

---

## Desktop & multi-platform clients

Native or Electron apps that run on the desktop, most with mobile/web companions.

- [opcode](https://github.com/winfunc/opcode) [![★](https://img.shields.io/github/stars/winfunc/opcode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/winfunc/opcode/stargazers) 🔓 — GUI toolkit for Claude Code: sessions, custom agents, background runs, and checkpoint review. `AGPL-3.0` `mac/Win/Linux` `MCP` `Claude Code`
- [Superset](https://superset.sh/) [![★](https://img.shields.io/github/stars/superset-sh/superset?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/superset-sh/superset/stargazers) 🟡 — Desktop workspace running 10+ CLI agents in parallel, each in its own worktree, with built-in diff review. `Elastic-2.0` `mac` `10+ agents`
- [Paseo](https://paseo.sh/) [![★](https://img.shields.io/github/stars/getpaseo/paseo?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/getpaseo/paseo/stargazers) 🟡 — Self-hosted daemon running 5 agents from one UI, with desktop/mobile/web/CLI clients connecting to it. `source-available` `Desktop/iOS/Android/Web/CLI` `MCP` `5 agents`
- [Orca](https://www.onorca.dev/) [![★](https://img.shields.io/github/stars/stablyai/orca?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/stablyai/orca/stargazers) 🔓 — Agent Development Environment running many CLI agents side by side, each with its own worktree, terminal, and browser tab. `MIT` `mac/Win/Linux/iOS/Android` `MCP` `25+ agents`
- [CodePilot](https://github.com/op7418/CodePilot) [![★](https://img.shields.io/github/stars/op7418/CodePilot?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/op7418/CodePilot/stargazers) 🟡 — Cross-platform desktop client wrapping the Claude Code CLI, with multi-provider models and messaging-app remote control. `BSL-1.1→Apache-2.0` `mac/Win/Linux` `MCP` `Claude Code`
- [1code](https://1code.dev/) [![★](https://img.shields.io/github/stars/21st-dev/1code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/21st-dev/1code/stargazers) 🟡 — Open-core desktop/web client running Claude Code and Codex locally or in cloud sandboxes, worktree-isolated. `Apache-2.0` `mac/Win/Linux/Web/PWA` `MCP` `Claude Code/Codex`
- [emdash](https://emdash.sh/) [![★](https://img.shields.io/github/stars/generalaction/emdash?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/generalaction/emdash/stargazers) 🔓 — Desktop app running many coding-agent CLIs in parallel, each in its own worktree, with cross-agent diff review. `Apache-2.0` `mac/Win/Linux` `10+ agents`
- [AgentsMesh](https://agentsmesh.ai/) [![★](https://img.shields.io/github/stars/AgentsMesh/AgentsMesh?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AgentsMesh/AgentsMesh/stargazers) 🟡 — Self-hosted runner fleet running terminal agents across multiple machines from one console. `BSL-1.1→GPL-2.0` `Web/Desktop/iOS/CLI` `5 agents`
- [mux](https://mux.coder.com/) [![★](https://img.shields.io/github/stars/coder/mux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coder/mux/stargazers) 🔓 — Coder's desktop/browser app running many agents in parallel via Local/Worktree/SSH runtimes (its own agent loop). `AGPL-3.0` `mac/Linux/Web/VSCode` `multi-model`
- [Agent Teams AI](https://agentteams.live/) [![★](https://img.shields.io/github/stars/777genius/agent-teams-ai?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/777genius/agent-teams-ai/stargazers) 🔓 — Desktop app where teams of agents message each other and review one another's code. `AGPL-3.0` `mac/Win/Linux` `MCP` `Claude Code/Codex/OpenCode`
- [Cline (Kanban)](https://cline.bot/) [![★](https://img.shields.io/github/stars/cline/kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/cline/kanban/stargazers) 🔓 — Companion Kanban app from the Cline project (60k★+) running parallel CLI agents in isolated worktrees. `Apache-2.0` `CLI/Web` `auto-detected agents`
- [claude-code-by-agents](https://claudecode.run/) [![★](https://img.shields.io/github/stars/baryhuang/claude-code-by-agents?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/baryhuang/claude-code-by-agents/stargazers) 🔓 — Native macOS/iOS app coordinating multiple Claude Code agents across machines via @mention routing. `MIT` `mac/iOS` `Claude Code`
- [Parallel Code](https://github.com/johannesjo/parallel-code) [![★](https://img.shields.io/github/stars/johannesjo/parallel-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/johannesjo/parallel-code/stargazers) 🔓 — Desktop app dispatching agent CLIs in parallel, each in its own worktree, with diff review and selective merge. `MIT` `mac/Linux` `Claude Code/Codex/Gemini/+2`
- [AI Maestro](https://github.com/23blocks-OS/ai-maestro) [![★](https://img.shields.io/github/stars/23blocks-OS/ai-maestro?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/23blocks-OS/ai-maestro/stargazers) 🔓 — Orchestration platform managing terminal agents across machines, with a dashboard, memory, and inter-agent messaging. `MIT` `mac/Linux/Win(WSL2)/Web/CLI` `multi-agent`
- [Dorothy](https://github.com/Charlie85270/Dorothy) [![★](https://img.shields.io/github/stars/Charlie85270/Dorothy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Charlie85270/Dorothy/stargazers) 🔓 — Desktop app orchestrating Claude Code, Codex, and Gemini across projects, with a kanban board and meta-orchestrator. `MIT` `mac/Linux` `MCP` `Claude Code/Codex/Gemini`
- [Constellagent](https://constellagent.vercel.app/) [![★](https://img.shields.io/github/stars/owengretzinger/constellagent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/owengretzinger/constellagent/stargazers) 🔓 — macOS app running multiple agent sessions in parallel, each with its own terminal, Monaco editor, and worktree. `license: ?` `mac` `agent-agnostic`
- [Sculptor](https://imbue.com/sculptor/) [![★](https://img.shields.io/github/stars/imbue-ai/sculptor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/imbue-ai/sculptor/stargazers) 🔓 — Imbue's desktop app running agents in parallel inside isolated containers, syncing work back to your repo. `MIT` `mac/Linux` `Claude Code/Codex`
- [Conductor](https://www.conductor.build/) 🔒 — macOS app (Melty Labs) running agents in parallel, each in an isolated workspace with branch, terminal, and diff. `closed-source` `mac` `MCP` `Claude Code/Codex/+2`
- [AgentsRoom](https://agentsroom.dev/) 🔒 — Desktop app (with iOS/Android companions) orchestrating CLI agents across projects as native local processes. `closed-source` `mac/Win/Linux/iOS/Android` `MCP` `7 agents`

## Terminal & CLI orchestrators

TUI dashboards and CLI-first tools that spawn and coordinate agents in panes, tmux, and worktrees.

- [cmux](https://cmux.com/) [![★](https://img.shields.io/github/stars/manaflow-ai/cmux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/manaflow-ai/cmux/stargazers) 🔓 — Native macOS terminal (libghostty) running terminal agents in parallel with splits and agent-aware notifications. `GPL-3.0` `mac (+iOS beta)` `any terminal agent`
- [Gas Town](https://github.com/gastownhall/gastown) [![★](https://img.shields.io/github/stars/gastownhall/gastown?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/gastownhall/gastown/stargazers) 🔓 — Steve Yegge's multi-agent orchestrator coordinating parallel agents via git-backed state and a watchdog hierarchy. `MIT` `CLI/TUI/Web` `8 agents`
- [Claude Squad](https://smtg-ai.github.io/claude-squad/) [![★](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/smtg-ai/claude-squad/stargazers) 🔓 — Terminal TUI managing multiple agent instances in parallel, each in its own worktree and tmux session. `AGPL-3.0` `mac/Linux/TUI` `Claude Code/Codex/Gemini/Aider`
- [Antfarm](https://www.antfarm.cool/) [![★](https://img.shields.io/github/stars/snarktank/antfarm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/snarktank/antfarm/stargazers) 🔓 — TypeScript CLI orchestrating teams of specialized agents through deterministic YAML workflows. `MIT` `CLI/Web` `OpenClaw`
- [Supacode](https://supacode.sh/) [![★](https://img.shields.io/github/stars/supabitapp/supacode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/supabitapp/supacode/stargazers) 🟡 — Native macOS command center (libghostty) running 50+ CLI agents in parallel, each in its own worktree. `FSL→Apache-2.0` `mac` `50+ agents`
- [Scion](https://googlecloudplatform.github.io/scion/) [![★](https://img.shields.io/github/stars/GoogleCloudPlatform/scion?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/GoogleCloudPlatform/scion/stargazers) 🔓 — Experimental host-side CLI + hub (Google Cloud) orchestrating agents in isolated containers with their own worktrees and credentials. `Apache-2.0` `CLI/Web/Linux/Cloud` `Claude Code/Gemini/Codex/OpenCode`
- [TAKT](https://github.com/nrslib/takt) [![★](https://img.shields.io/github/stars/nrslib/takt?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/nrslib/takt/stargazers) 🔓 — Open-source CLI turning coding agents into repeatable YAML workflows (plan→implement→review→fix) with isolated worktrees. `MIT` `CLI` `6 agents`
- [Agent Deck](https://github.com/asheshgoplani/agent-deck) [![★](https://img.shields.io/github/stars/asheshgoplani/agent-deck?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/asheshgoplani/agent-deck/stargazers) 🔓 — Terminal "mission control" that runs, organizes, forks, and autonomously monitors many agent sessions. `MIT` `TUI/CLI/Web` `MCP` `6 agents`
- [ntm](https://github.com/Dicklesworthstone/ntm) [![★](https://img.shields.io/github/stars/Dicklesworthstone/ntm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dicklesworthstone/ntm/stargazers) 🔓 — Go CLI turning tmux into a control plane for spawning, tiling, and coordinating agents across panes. `MIT` `CLI/TUI/Web` `Claude Code/Codex/Antigravity`
- [amux](https://github.com/andyrewlee/amux) [![★](https://img.shields.io/github/stars/andyrewlee/amux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/andyrewlee/amux/stargazers) 🔓 — Terminal UI running multiple agents in parallel, each isolated in its own worktree and tmux session. `MIT` `mac/Linux/TUI` `6 agents`
- [AgentBox](https://agent-box.sh/) [![★](https://img.shields.io/github/stars/madarco/agentbox?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/madarco/agentbox/stargazers) 🔓 — CLI running multiple agents in parallel, each isolated in a sandboxed VM locally (Docker) or in the cloud. `MIT` `mac/Linux/CLI` `Claude Code/Codex/OpenCode`
- [OpenKanban](https://github.com/TechDufus/openkanban) [![★](https://img.shields.io/github/stars/TechDufus/openkanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/TechDufus/openkanban/stargazers) 🔓 — Terminal-UI kanban board where each ticket runs in its own worktree with an embedded agent terminal. `AGPL-3.0` `mac/Linux/TUI` `5 agents`
- [dux](https://getdux.app/) [![★](https://img.shields.io/github/stars/patrickdappollonio/dux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/patrickdappollonio/dux/stargazers) 🔓 — Three-pane TUI running agent CLIs in parallel, each in its own worktree, with live git staging. `MIT` `mac/Linux/TUI` `Claude Code/Codex/OpenCode/+`
- [Agent Orchestrator](https://github.com/ComposioHQ/agent-orchestrator) [![★](https://img.shields.io/github/stars/ComposioHQ/agent-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/ComposioHQ/agent-orchestrator/stargazers) 🟡 — Composio's orchestrator (now ReverbCode) supervising parallel agent sessions in their own worktrees, routing CI/review/conflict feedback to the owning agent. `license: ?` `CLI/Desktop` `23 agents`
- [Agent of Empires](https://github.com/njbrake/agent-of-empires) [![★](https://img.shields.io/github/stars/njbrake/agent-of-empires?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/njbrake/agent-of-empires/stargazers) 🔓 — Session manager for agents on Linux/macOS, driven from a terminal TUI or a browser/PWA dashboard. `MIT` `CLI/TUI/Web/PWA` `ACP` `13 agents`
- [Bernstein](https://bernstein.run/) [![★](https://img.shields.io/github/stars/chernistry/bernstein?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/chernistry/bernstein/stargazers) 🔓 — Deterministic Python orchestrator that decomposes a goal, runs CLI agents in parallel worktrees, and verifies before merge. `Apache-2.0` `CLI/Web/VSCode/Cloud` `MCP` `44 agents`

## IDE & editor plugins

Agents and orchestrators that live inside your editor.

- [CodeCompanion.nvim](https://codecompanion.olimorris.dev/) [![★](https://img.shields.io/github/stars/olimorris/codecompanion.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/olimorris/codecompanion.nvim/stargazers) 🔓 — Neovim plugin connecting to LLM providers and to external agents via ACP from a chat buffer. `Apache-2.0` `Neovim` `MCP+ACP` `9 agents`
- [CC GUI (Claude or Codex)](https://plugins.jetbrains.com/plugin/29342-cc-gui-claude-or-codex-) [![★](https://img.shields.io/github/stars/zhukunpenglinyutong/jetbrains-cc-gui?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/zhukunpenglinyutong/jetbrains-cc-gui/stargazers) 🔓 — JetBrains plugin giving a dual-engine GUI for the Claude Code and Codex CLIs. `MIT` `JetBrains` `MCP` `Claude Code/Codex`
- [Obsidian Agent Client](https://rait-09.github.io/obsidian-agent-client/) [![★](https://img.shields.io/github/stars/RAIT-09/obsidian-agent-client?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/RAIT-09/obsidian-agent-client/stargazers) 🔓 — Obsidian plugin embedding external coding agents in your vault via ACP. `Apache-2.0` `Desktop (Obsidian)` `ACP+MCP` `7 agents`
- [Agentic.nvim](https://github.com/carlos-algms/agentic.nvim) [![★](https://img.shields.io/github/stars/carlos-algms/agentic.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/carlos-algms/agentic.nvim/stargazers) 🔓 — Neovim plugin giving an in-editor chat interface to any ACP-compatible coding agent. `MIT` `Neovim` `ACP` `8+ agents`
- [Claude Code Plus](https://plugins.jetbrains.com/plugin/28343-claude-code-plus) [![★](https://img.shields.io/github/stars/touwaeriol/claude-code-plus?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/touwaeriol/claude-code-plus/stargazers) 🔓 — JetBrains plugin giving a GUI for CLI coding agents inside IntelliJ-based IDEs. `MIT` `JetBrains` `MCP` `Claude Code/Codex/Gemini`

## Web & self-hosted dashboards

Browser-first orchestrators you run locally or self-host.

- [Multica](https://multica.ai/) [![★](https://img.shields.io/github/stars/multica-ai/multica?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/multica-ai/multica/stargazers) 🟡 — Open-source managed-agents platform turning coding agents into board-tracked teammates you assign issues to. `Apache-2.0 (mod.)` `Web/self-hosted/Cloud` `12 agents`
- [Vibe Kanban](https://www.vibekanban.com/) [![★](https://img.shields.io/github/stars/BloopAI/vibe-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/BloopAI/vibe-kanban/stargazers) 🔓 — Kanban interface to plan, run, and review tasks across many agent CLIs, each in an isolated worktree. `Apache-2.0` `mac/Web/CLI` `10 agents`
- [T3 Code](https://t3.codes/) [![★](https://img.shields.io/github/stars/pingdotgg/t3code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/pingdotgg/t3code/stargazers) 🔓 — Open-source web/desktop control plane (Theo/Ping) orchestrating Codex, Claude Code, Cursor, and OpenCode. `MIT` `mac/Win/Linux/Web/CLI` `4 agents`
- [Catnip](https://github.com/wandb/catnip) [![★](https://img.shields.io/github/stars/wandb/catnip?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/wandb/catnip/stargazers) 🔓 — Self-hostable web service (W&B) running Claude Code in containerized worktree sandboxes, with a native iOS app. `Apache-2.0` `Web/CLI/iOS/Cloud` `Claude Code`
- [Agent Viewer](https://github.com/hallucinogen/agent-viewer) [![★](https://img.shields.io/github/stars/hallucinogen/agent-viewer?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hallucinogen/agent-viewer/stargazers) 🔓 — Web kanban board to spawn, monitor, and message multiple Claude Code agents running in tmux. `license: ?` `mac/Linux/Web/mobile` `Claude Code`
- [OpenGoat](https://github.com/marian2js/opengoat) [![★](https://img.shields.io/github/stars/marian2js/opengoat?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/marian2js/opengoat/stargazers) 🔓 — Platform for building hierarchical organizations of agents that coordinate work across many providers. `MIT` `Web/CLI` `5 agents`
- [Agent Kanban](https://agent-kanban.dev/) [![★](https://img.shields.io/github/stars/saltbo/agent-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/saltbo/agent-kanban/stargazers) 🟡 — Agent-first kanban board treating agents as crypto-identified members who claim tasks and open PRs. `FSL→Apache-2.0` `CLI/Web` `ACP` `5 agents`
- [Kanban Code](https://github.com/langwatch/kanban-code) [![★](https://img.shields.io/github/stars/langwatch/kanban-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/langwatch/kanban-code/stargazers) 🔓 — Native desktop app + CLI (LangWatch) managing multiple Claude Code sessions via a kanban board. `AGPL-3.0` `mac/Win/CLI` `Claude Code`

## Cloud & hosted control planes

Hosted (or self-hostable) control planes that run agent fleets in the cloud.

- [Oz](https://www.warp.dev/oz) [![★](https://img.shields.io/github/stars/warpdotdev/warp?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/warpdotdev/warp/stargazers) 🟡 — Warp's platform running and monitoring fleets of cloud coding agents across multiple harnesses. `MIT/AGPLv3` `Cloud/Web/Desktop/CLI` `MCP` `4 agents` *(★ = whole Warp client)*
- [Centaur](https://centaur.run/) [![★](https://img.shields.io/github/stars/paradigmxyz/centaur?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/paradigmxyz/centaur/stargazers) 🔓 — Paradigm's self-hosted control plane running CLI agent harnesses in isolated K8s sandboxes, driven from Slack/API. `Apache-2.0/MIT` `Cloud/CLI/Slack` `Claude Code/Codex/Amp`

## Session viewers & companion tools

These observe and analyze agent sessions — they don't launch or control agents — but pair well with the tools above.

- [AgentsView](https://www.agentsview.io/) [![★](https://img.shields.io/github/stars/kenn-io/agentsview?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/kenn-io/agentsview/stargazers) 🔓 — Local-first tool indexing coding-agent session logs with search, token/cost analytics, and activity insights (observability only). `MIT` `mac/Win/Linux/CLI/Web` `reads 20+ agents`
- [Claude Code Agent Monitor](https://hoangsonww.github.io/Claude-Code-Agent-Monitor/) [![★](https://img.shields.io/github/stars/hoangsonww/Claude-Code-Agent-Monitor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hoangsonww/Claude-Code-Agent-Monitor/stargazers) 🔓 — Self-hosted real-time dashboard for Claude Code sessions, tool use, costs, and subagent activity (observability). `MIT` `Web/mac/Win/VSCode/CLI` `MCP` `reads Claude Code`

## Archived & notable

No longer actively maintained, but historically important reference points.

- [Crystal](https://github.com/stravu/crystal) [![★](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/stravu/crystal/stargazers) — Electron app that ran multiple Claude Code/Codex sessions in parallel, each in its own worktree. `MIT` `mac/Win/Linux` **discontinued → now [Nimbalyst](https://nimbalyst.com/)**
- [Terragon](https://github.com/terragon-labs/terragon-oss) [![★](https://img.shields.io/github/stars/terragon-labs/terragon-oss?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/terragon-labs/terragon-oss/stargazers) — Hosted background-agent fleet orchestrator. `Apache-2.0` **service shut down 2026-01-16; unmaintained snapshot**
- [Claude Code Board](https://cc-board.cablate.com/) [![★](https://img.shields.io/github/stars/cablate/Claude-Code-Board?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/cablate/Claude-Code-Board/stargazers) — Web kanban-style manager for multiple Claude Code CLI sessions. `MIT` **no longer maintained (Jan 2026)**

## Related: agents, frameworks & protocols

Not clients/orchestrators themselves, but the things the tools above manage and speak to.

**Coding agents (the things being orchestrated)**
- [Claude Code](https://github.com/anthropics/claude-code) · [OpenAI Codex](https://github.com/openai/codex) · [Gemini CLI](https://github.com/google-gemini/gemini-cli) · [OpenCode](https://github.com/sst/opencode) · [Aider](https://github.com/Aider-AI/aider) · [Cursor CLI](https://cursor.com/cli) · [Amp](https://ampcode.com/) · [Pi](https://github.com/parallel-web/pi)

**Agents that double as desktop apps (out of scope as clients)**
- [Goose](https://github.com/block/goose) — Block's extensible Rust agent that talks directly to LLMs and can act as an ACP server. Managed by Orca, Paseo, cmux, and others.
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) — Nous Research's general-purpose self-improving agent; targeted by Agent Kanban and AI Maestro via ACP, and a supported agent in Multica.
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

As a rough curation bar, tools with **fewer than ~50 GitHub stars** are usually held back until
they gain some traction (genuinely novel tools may be added sooner). Star count is a signal of
adoption, not a judgment of quality.

## A note on data quality

This list was compiled from a structured research pass in **June 2026**. Every tool was
confirmed to exist via the GitHub API, and each entry was then fact-checked against the project's
own README/site — **licenses, platforms, supported agents, protocols (MCP/ACP), and feature
claims were verified and corrected**. Star badges update live; **sort order within each section
reflects star counts at the time of writing**. Details can still drift as projects evolve, so
verify before depending on a specific claim and please send corrections. Two badge caveats: the
★ badge for **Cline (Kanban)** points at the orchestrator repo while the parent Cline project is
far larger, and the **Oz** badge counts the whole Warp client, not Oz alone. See
[docs/awesome-agent-clients-design.md](docs/awesome-agent-clients-design.md) for scope rules and provenance.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

To the extent possible under law, the contributors have waived all copyright and related or
neighboring rights to this work. See [LICENSE](LICENSE) (CC0-1.0).
