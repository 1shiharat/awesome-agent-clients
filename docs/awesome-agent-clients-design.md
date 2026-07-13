# awesome-agent-clients — Design / Spec

**Date:** 2026-06-24
**Status:** Approved direction (platform-based), research-informed v1.

## Purpose

A curated GitHub "awesome list" of **AI coding-agent clients and orchestrators** — the
GUI / CLI / TUI / mobile / web / IDE apps that **wrap, run, manage, or orchestrate** coding
agents (Claude Code, OpenAI Codex, Gemini CLI, OpenCode, Aider, Cursor CLI, Amp, etc.).

The coding agents themselves are **out of scope** as primary entries; they appear only in a
"Related" section as the things being managed.

## Scope rules (inclusion criteria)

A tool is **in scope** if it:

1. Wraps / runs / manages / orchestrates one or more *external* coding agents, AND
2. Is a real, reachable product (official site and/or public repo), AND
3. Is not merely the agent itself, a fork/mirror of a listed tool, or a duplicate entry.

Borderline handling:
- Tools that are an agent **and** ship an orchestrator (e.g. Cline + its Kanban app) are kept,
  pointing at the orchestrator component.
- Tools with their own agent loop but fleet-management UX (e.g. Coder `mux`) are kept with a note.
- Pure observability/session viewers (no agent control) are kept in a dedicated **companion** section,
  clearly labelled.
- General-purpose assistants / DAG frameworks / sandbox infrastructure (Goose, OpenClaw, FleetQ,
  AgentTier, Hermes Agent) are **out of scope** → "Related".

## Repository structure

```
awesome-agent-clients/
├── README.md            # the list (badge, intro, scope, legend, TOC, entries)
├── CONTRIBUTING.md      # inclusion criteria + entry format + PR steps
├── CODE_OF_CONDUCT.md   # Contributor Covenant
├── LICENSE              # CC0-1.0
├── docs/
│   └── awesome-agent-clients-design.md   # this file
└── .github/
    ├── PULL_REQUEST_TEMPLATE.md
    └── ISSUE_TEMPLATE/
        └── suggest-a-tool.md
```

## README section taxonomy (platform-based, the agreed primary axis)

1. Desktop & multi-platform clients
2. Terminal & CLI orchestrators (TUI + CLI-first)
3. IDE & editor plugins (Neovim, JetBrains, Obsidian, …)
4. Web & self-hosted dashboards
5. Cloud & hosted control planes
6. Mobile & remote-control clients (added 2026-07; phone/remote clients)
7. Session viewers & companion tools (observe, don't control)
8. Archived / notable (historical reference)
9. Related: agents, frameworks & protocols (managed agents, MCP, ACP)

Each tool is listed in its single most-appropriate section. A compact metadata sub-line
surfaces repo · license · platforms · supported agents · the one or two distinctive features —
because, per the brief, the right way to record a tool depends on what it actually does.

## Entry format

```
- [Name](best-url) — one neutral sentence (no marketing superlatives). <emoji> [![★](shields.io stars badge)](repo/stargazers)
  - `owner/repo` (or `closed-source`) · License · Platforms · Agents: … · *Distinctive:* …
```

Each entry carries a live shields.io GitHub-stars badge, and **entries are sorted by star
count (descending) within each section** as a transparent adoption signal. Closed-source
products have no badge.

## Curation by adoption (star threshold)

GitHub stars are used as a rough adoption proxy. Tools with **fewer than ~50 stars** are held
back from the main list unless they are uniquely notable; genuinely novel tools can be added
sooner. Star count is a signal, not a quality verdict.

Two badge caveats are documented in the README: the **Cline (Kanban)** badge points at the
orchestrator repo (the parent project is far larger), and the **Oz** badge counts the whole
Warp client rather than Oz alone.

## Provenance & data quality

- Compiled from a multi-agent research workflow (June 2026): ~418 raw candidates → 210 unique
  tools discovered; 49 deeply researched in round 1 + 24 in a gap-fill round (editor-embedded
  + cloud/hosted). Every listed tool was confirmed to exist via an official site and/or repo.
- Entries were later fact-checked against each project's README/site (existence, license,
  platforms, supported agents, MCP/ACP, and feature claims) and corrected (June 2026). The
  feature-level pass found 11 entries with major overstatements (e.g. inflated agent counts,
  unsupported MCP tags, fabricated features) and 13 with minor ones — all fixed. Star counts /
  versions / dates remain point-in-time and may drift; corrections via PR are welcome.

## Star counts (read from GitHub API, 2026-06-29)

All listed repos had their `stargazers_count` read directly from the GitHub API during build,
which also re-confirmed each repo exists. Notable: `multica-ai/multica` is real and large
(~37.7k★) → promoted into the list (Web & self-hosted). Top of list: `cline/cline` (~64k),
`warpdotdev/warp` (~62k), `BloopAI/vibe-kanban` (~27k), `manaflow-ai/cmux` (~23k),
`winfunc/opcode` (~22k, but last push 2025-10).

### Excluded for low adoption (< ~50 stars)

Dropped from v1 (recorded here so reviewers know they were considered, not missed):

- `rickywo/Formic` (~41★) · `codika-io/clave` (~31★) · `NikiforovAll/claude-code-kanban` (~30★) ·
  `rayzhudev/vibecraft` (~26★) · `bdkent/clauditor` (~4★).

## Known pending / earlier exclusions

- **CliDeck** — appeared in discovery but lacked a verified entry → omitted from v1.
- Excluded as too immature / confusing: `swmcc/agentic.nvim` (Pamoja, ~2★),
  `sajithdilshan/agent-cli-plugin` (~0★), `craigsc/cmux` & `EtanHey/cmuxlayer` (name collision / niche).
- ~160 discovered tools were never researched (round 1 capped at 50). Long-tail follow-up welcome.

## 2026-07 update — additions, promotions, corrections

Second discovery pass (2026-07-05) as the space kept growing. **Added 20 tools** (all verified
in-scope, active, ≥50★): openwork, CodexMonitor, Nimbalyst, jean, proliferate (Desktop);
herdr, toad, claude_code_bridge, dmux, claw-orchestrator, tmux-ide, h5i, mngr, Pane, lalph
(Terminal); clideck (Web); sandbox-agent (Cloud); agent-flow, agent-sessions, agenttrace
(Session viewers). **Promoted Symphony** (`openai/symphony`, ~25.8k★) from Related to Cloud.
**Corrected Agent Orchestrator**: `ComposioHQ/agent-orchestrator` now redirects to
`AgentWrapper/agent-orchestrator` (same project, renamed; license now Apache-2.0) — entry updated.
**Flagged opcode** ⚠️ (no commits since 2025-10).

### Considered but skipped (2026-07)
- **In-scope unconfirmed / vague** (high stars, but couldn't verify they wrap external CLIs vs run
  their own agent, or lacked a clear description): `AndyMik90/Aperant` (~14k), `AutoMaker-Org/automaker`
  (~3.2k), `NeuralNomadsAI/CodeNomad` (~2k), `the-open-engine/zeroshot` (~1.6k), `jayminwest/warren`
  (~108, "custom agents"). Revisit with per-repo verification.
- **Name collision**: `mixpeek/amux` (~280★) skipped — clashes with the listed `andyrewlee/amux`.
- **Below the bar / marginal** (noted for a future round): `VisionForge-OU/foreman`, `redevops-io/sidekick`,
  `Ivy-Interactive/Ivy-Tendril`, `oxgeneral/ORCH`, `sortie-ai/sortie`, `vdaubry/bottega`,
  `modimihir07/agentic-os`, `relaydeck/relaydeck`, `doordash-oss/agentic-orchestrator`,
  `dmae97/open-multi-agent-kit`, `ikamensh/kodo`, `amirfish1/claude-command-center`, `monkilabs/opencastle`.

## 2026-07 second pass — comprehensive expansion (~39 added)

A broader three-angle discovery sweep (GitHub, directories/HN/PH, category-focused) surfaced
far more of the (fast-growing) space. Added ~39 verified in-scope tools and a **new "Mobile &
remote-control clients" section** (Happy ~22.6k★, Claude Code UI ~12.6k, VibeTunnel ~4.6k, takopi).
Highlights added: CodeLayer/HumanLayer (~11k), ralph-claude-code (~9.5k), Omnigent (~7.2k),
Mission Control (~5.7k), Aperant (~14.4k), automaker, CodeNomad, Helmor, Agor, HolyClaude,
Agency Orchestrator, CAO (AWS Labs), multi-agent-shogun, claude_code_agent_farm, Citadel,
zeroshot, babysitter, and the Neovim/Emacs cluster (claudecode.nvim, claude-code.nvim,
claude-code-ide.el, agent-shell). Closed-source cloud: **Tembo, Niteshift, Duet**. **claude-flow**
(~64k★) placed in Related (swarm framework, not a turnkey client). **Omnara** moved to Archived
(repo archived). **Agent Orchestrator** confirmed = `AgentWrapper/agent-orchestrator`
(`ComposioHQ/agent-orchestrator` redirects to it — same project, not a duplicate).

### Skipped / deferred (2026-07 second pass)
- **Name collisions**: `mixpeek/amux` (clashes with `andyrewlee/amux`).
- **Own agent / generic framework (out of scope)**: `1jehuang/jcode`, `stagewise-io/stagewise`,
  `collaborator-ai/collab-public`, `0-AI-UG/cate`, `ariana-dot-dev/ariana`, `Runfusion/Fusion`,
  `thesongzhu/Friday`, `CompanyHelm/companyhelm`, `mozilla-ai/otari`, `mathomhaus/guild`, Pochi.
- **Support tooling, not agent runners**: `golbin/gw`, `rohansx/workz`, `clash-sh/clash`,
  `ethanhq/cc-fleet`, `sahithvibudhi/vibe-tree`, `aidenybai/ghast`.
- **Ralph-loop family** (added the top 2; others noted): `mikeyobrien/ralph-orchestrator`,
  `subsy/ralph-tui`, `mikehostetler/wreckit`, `looptroop-ai/LoopTroop`.
- **Below ~50★ or marginal, revisit**: `sortie-ai/sortie` (~103), `amirfish1/claude-command-center`
  (~93), `oxgeneral/ORCH` (~92), `nutthouse/tutti` (~93), `ikamensh/kodo` (~116),
  `monkilabs/opencastle` (~56), `jarredkenny/jmux`, `frenchie4111/harness`, `ouijit/ouijit`,
  `hueyexe/opencode-ensemble`, `leodavinci1/kanbots`, `aannoo/hcom`, plus <50★:
  `ArthurDEV44/paneflow`, `usemozzie/mozzie`, `DanWahlin/ai-agent-board`.
- **Closed-source, notability unverified**: Commander AI, atrium, Scape, Codelegate, Medusa,
  Smith, KingCoding, Invoker, Hermes (contextstudios), PATAPIM (curated-directory listed but
  weaker independent signal), Agent 37.

## Out of scope (recorded for reviewers)

Goose, Hermes Desktop/Agent, OpenClaw (general assistants/agents); FleetQ (general DAG
multi-agent platform); AgentTier (Kubernetes agent-sandbox infrastructure); ghast (cmux fork).
