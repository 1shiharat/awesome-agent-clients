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
- Adjacent env/profile/worktree helpers that support agent workflows but don't run/manage the
  agents (e.g. `codex-profiles`, git-worktree wrappers) → **Related › Adjacent tooling**, not the
  main list.

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

## 2026-07-17 refresh — latest-info pass

Star/status refresh over all badged repos + a targeted discovery sweep for tools created or
newly-trending in the late-June→mid-July 2026 window.

- **Status change**: `21st-dev/1code` is now **archived** → moved Desktop → Archived & notable
  (grey badge, "repo archived"), matching Crystal/Terragon/Omnara. `omnara-ai/omnara` re-confirmed
  archived (already in Archived). `winfunc/opcode` still ⚠️ (no commits since 2025-10).
- **Added 8** verified in-scope, active, ≥50★ tools (license/platform read from GitHub API):
  - Desktop: **codeg** (`xintaofei/codeg`, ~2.1k★, Apache-2.0 — aggregates Claude Code/Codex/OpenCode/Pi/Grok Build sessions).
  - Terminal: **OpenSwarm** (`unohee/OpenSwarm`, ~819★, MIT — Claude Code CLI dev-team pipeline; `Intrect-io/OpenSwarm` redirects here),
    **hcom** (`aannoo/hcom`, ~384★, MIT), **codex-orchestrator** (`kingbootoshi/codex-orchestrator`, ~325★, MIT — tmux/Codex),
    **opencode-ensemble** (`hueyexe/opencode-ensemble`, ~169★, MIT), **kodo** (`ikamensh/kodo`, ~116★, MIT),
    **jmux** (`jarredkenny/jmux`, ~72★, AGPL-3.0 — tmux sidebar).
  - Web & self-hosted: **kanbots** (`leodavinci1/kanbots`, ~538★, MIT — kanban, each task a Claude Code/Codex agent).
- **Deferred candidates that crossed ~50★ but held back this pass** (generic/thin descriptions,
  stale, or category unclear — revisit with per-repo verification): `oxgeneral/ORCH` (~91),
  `frenchie4111/harness` (~84), `sortie-ai/sortie` (~106, cloud vs CLI unclear), `nutthouse/tutti`
  (~100, last push 2026-05-05), `monkilabs/opencastle` (~57, last push 2026-05-18),
  `ouijit/ouijit` (~121, AGPL — worktree task-manager, GUI category unclear).
  Still <50★: `usemozzie/mozzie` (48), `DanWahlin/ai-agent-board` (41), `ArthurDEV44/paneflow` (35).
- **Newly-created but held back**: `100yenadmin/Lossless-Codex-Orchestrator-LCO` (~51★, created
  2026-06-28) — genuinely new but borderline (session-recall/approval-gate heavy). Revisit if it grows.
- **Confirmed out of scope / not new**: `iOfficeAI/AionUi` (~30k, created Aug 2025, not new),
  `farion1231/cc-switch` (~118k, provider/config switcher not a runner), `PROrunner926/copilot-cache-scout`
  (cost benchmark), `cpatterson71/agentrooms` (fork of listed `baryhuang/claude-code-by-agents`),
  AgentsRoom (no public repo).

## 2026-07-26 refresh — July-created delta

Incremental discovery scoped to repos **created in July 2026** and not already listed. All
additions verified via GitHub API (exists, not archived, stars, license, created/pushed dates).

- **Added 12** in-scope, active tools:
  - Desktop: **BossConsole** (`risa-labs-inc/BossConsole`, ~189★, Apache-2.0 — JVM operator's console for Claude Code/Codex/Gemini/OpenCode).
  - Terminal: **ringer** (`NateBJones-Projects/ringer`, ~182★, custom license — `codex exec` swarm + web HUD),
    **gridbash** (`jasonsuhari/gridbash`, ~139★, MIT — 100-pane terminal grid),
    **claude-lane-stack** (`VKirill/claude-lane-stack`, ~124★, MIT — PM→AGY/Grok/Codex lanes, auto-merge),
    **ccmux** (`epilande/ccmux`, ~99★, MIT — tmux agent-pane tracker),
    **outsourcerer** (`alexgreensh/outsourcerer`, ~85★, custom license — delegate to cheaper harnesses),
    **ultracodex** (`YuanpingSong/ultracodex`, ~62★, Apache-2.0 — Claude-Code workflow scripts on Codex CLI),
    **sigbound** (`surya-koritala/sigbound`, ~51★, Apache-2.0 — parallel worktrees, test-gated auto-merge, BYO model).
  - Web & self-hosted: **pi-dispatch** (`edgehero/pi-dispatch`, ~77★, MIT — pi-agent as a triggered service),
    **fox-ai-roundtable** (`PeterPanSwift/fox-ai-roundtable`, ~75★, no license — one prompt → 3 CLIs).
  - Session viewers & companion: **recensa** (`S40911120/recensa`, ~65★, MIT — Claude Code transcript viewer),
    **unsnooze** (`saaranshM/unsnooze`, ~60★, MIT — auto-resume limit-stopped agent sessions).
- **Held back — Claude Code skill/plugin orchestrators** (they orchestrate external agent CLIs but
  ship as a CC skill/plugin, not a standalone app/CLI — a category the list has deliberately kept out,
  same as env/profile packs → Related › Adjacent tooling if ever added): `0xwilliamortiz/agents-council`
  (~111), `markfulton/claude-antigravity-agents` (~107), `olsenbrands/fable-foreman` (~90),
  `tomascupr/sous-chef` (~67), `cathrynlavery/codex-build` (~65), `jvogan/a-fable-of-codexes` (~43),
  `joeseesun/qiaomu-model-cli` (~40).
- **Held back — under ~50★ or niche** (revisit if they grow): `omergocmen/CrewCtl` (48),
  `04mg/caw` (48, web multiplexer — novel), `scp3500/pi-manager` (46), `ardhaecosystem/RUDR9` (41, profile pack).
- **Verified out of scope** (Claude-only config/subagent packs, plan visualizers, memory/log/benchmark/security
  tools — no external agent wrapped): `Nanako0129/pilotfish` (~540, CC-subagent config),
  `PromptPartner/agentsmith` (~255, prompt-rules harness), `OthmanAdi/plandeck` (~62, "no AI" YAML kanban),
  `Miguok/fable-harness` (~196), `per-simmons/fable-orchestration`, `ebowman/domestique`, and assorted
  memory/proxy/benchmark/security-agent repos.

## 2026-07-26 curation — scope/freshness tightening

Quality pass ahead of a future `sindresorhus/awesome` submission (which weighs curation over
breadth). Four entries moved out of the main platform sections:

- **opcode** (`winfunc/opcode`) — Desktop → **Archived**. No commits since 2025-10 (was ⚠️-flagged);
  a stale tool in a primary section is misleading. Badge greyed, kept for historical reference.
- **CodeLayer / HumanLayer** (`humanlayer/humanlayer`) — Desktop → **Related › frameworks & infra**.
  The repo/badge is the HumanLayer human-in-the-loop *framework* monorepo (star count reflects the
  framework, not the CodeLayer app); more infrastructure than a standalone client.
- **mux** (`coder/mux`) — Desktop → **Related › agents that double as desktop apps**. Drives its own
  agent loop rather than orchestrating external agent CLIs.
- **Symphony** (`openai/symphony`) — Cloud → **Related › frameworks & infra**. A spec + Elixir
  reference implementation, not a turnkey client (same treatment as claude-flow).

Deferred (not done this pass): raising the ~50★ curation bar to ~100★ to further tighten the list —
revisit when preparing the actual mother-list submission. Note on that submission: it requires the
repo's main README to pass `awesome-lint`, which forbids per-entry badges and the `- [name](url) - desc.`
format — i.e. converting away from the star-badge / star-ranked design. Deferred until the list has
real traction; grow via announcement channels (Show HN / Zenn / X / Reddit) first.

## 2026-11-07 refresh — full audit after a 3.5-month gap

All badged repos re-read through the GitHub GraphQL API; non-GitHub links re-fetched. Discovery ran
24 GitHub searches (repos created since 2026-03, ≥150★) and each candidate's README was read.

- **Removed — repo gone (404)**: `AgentsMesh/AgentsMesh` (site also 404), `joewinke/jat` (site also
  down), `wandb/catnip` (catnip.run is an empty shell, no replacement repo found).
- **Removed — pivoted**: **Duet** (`duet.so` now redirects to Bento, an "every kind of AI"
  subscription, not a Claude Code server).
- **Removed — below the bar**: `surya-koritala/sigbound` (~51★ at listing, 38★ now).
- **De-duplicated**: `bfly123/claude_code_bridge` turned out to redirect to `SeemSeam/claude_codex_bridge`,
  already listed as "Claude Codex Bridge"; the old entry was dropped.
- **Product renames**: Superset → **Paradev** (`ParadevAI/Paradev`; LICENSE.md is now MIT, so 🟡→🔓,
  README states macOS + experimental Linux), Agent Orchestrator → **Orchestrator**
  (`OrchestratorInc/agent-orchestrator`, per PR #20), claude-flow → **Ruflo** (`ruvnet/ruflo`),
  mux → **Xum** (`coder/xum`).
- **Repo moves**: bernstein, Pane, Agent of Empires, herdr, OpenSwarm, codeg, sandbox-agent
  (now the `rivet-dev/agents` monorepo, so its badge covers more than sandbox-agent), OpenCode,
  Goose, Pi (`earendil-works/pi`; the old `parallel-web/pi` link was dead).
- **License fixes**: herdr → Apache-2.0 (🟡→🔓), Kanban Code → Apache-2.0, both confirmed in their
  READMEs. Warp kept as `MIT/AGPLv3` (API reports only AGPL). NOASSERTION rows were not re-read.
- **Description refresh**: herdr now describes itself as an agent runtime with a client ecosystem
  (Ovis, Collie, Heeler, Roamgate), so its entry was rewritten from its README.
- **Link fixes**: emdash → emdash.com, unsnooze → unsnooze.dev; automaker.app (404) and 1code.dev
  (redirect) now point at their repos.
- **⚠️ policy**: now applied by rule: no default-branch commit for **180+ days**, primary sections
  only. Applied to 8: claude-code-plus, claude-code.nvim, ralphy, antfarm, FleetCode, CodexMonitor,
  opengoat, constellagent. Moving to Archived stays reserved for repos actually archived.
- **Added 32** (active, in scope, ≥250★ unless noted): Orkas, nodeterm, Lody, Alethe, PandaCode, Vicoa, TasteCode, Runner, diri, Hermes IDE, Shipyard, Monet, Termio, agent-manager, Martty, Cezar, omg.dev, MulmoTerminal, Grasp, Zozo, Remodex, Nexting, DS Harness Remote, Ovis, Collie, Heeler, Roamgate, Clawd on Desk, abtop, zoetrope, Agenttrail, tmux-agent-sidebar; plus **Sandcastle** under
  Related › frameworks (an SDK). From the queue: Orkas (PR #5), agent-manager (PR #15, badge uses the
  new `wainmann` owner), MulmoTerminal (PR #12), Martty (issue #9, ~81★), Zozo (issue #17,
  closed-source, site read).
- **Held back from PRs/issues**: Kortix (PR #19 — builds its own agents on Pi; no external coding-agent
  CLI in its README, out of scope), Layerbase Workspaces (PR #13 — hosted Ubuntu box with a session
  list, no dispatch or orchestration; infrastructure), under ~50★: OpenCode Android (PR #16, 32),
  Superagent (PR #11, 36), Sillage (PR #10, 11), PinkCollab (PR #14, 10), Kronos (PR #7, 4 and stale),
  Conduit Bridge (issue #18, 0).
- **Held back from discovery**: `NanmiCoder/cc-haha` (~15k, source-available; ships its own runtime
  under `src/`, provenance unverified), `savannahfeder/agentbox` (name clash with listed
  `madarco/agentbox`, same call as `mixpeek/amux`), `lanes-sh/app` (no source in repo),
  `eliasstravik/shepherdr` (herdr plugin), `amplifthq/openmeld` (hosted collaboration, own agent).
  Own agent / other category: `Gentleman-Programming/gentle-shell`, `omnirush-ai/omnirush-gui`,
  `getkimchi/kimchi`, `yyjeqhc/webcodex` (MCP tool runtime).
- **Search limit**: discovery covers repos created since March 2026 with ≥150★; the long tail between
  ~50★ and ~250★ was only partly reviewed.

## 2026-11-08 — description refresh

The 2026-11-07 pass re-checked repos, licenses and stars but not what each tool now does, and many
descriptions were still June–July wording (e.g. T3 Code listed as a 4-agent web control plane after
it shipped desktop/mobile apps, per-thread worktrees, a terminal, a browser panel and a PR view).
Every entry was re-read against its current README/LICENSE (closed-source: its site).

- **Rewritten: 115 of 162 entries** (description, platforms, agent count, MCP/ACP tags), EN + JA.
- **T3 Code** moved Web → Desktop & multi-platform (desktop, web, iOS and Android apps).
- **Marker/license changes**: Paseo (Apache-2.0) and openwork (MIT outside `ee/`) 🟡→🔓; DS Harness
  Remote (now MIT) 🟡→🔓; kanna (MIT text excluding named parties) 🔓→🟡; Agent Viewer (no LICENSE
  file) → `no license` 🟡; Multica tagged `Apache-2.0 (mod.)`, source-available.
- **Removed**: `h5i-dev/h5i` — pivoted to a Lean 4 Rust web framework.
- **Moved to Archived**: automaker — its LICENSE now states it is no longer maintained.
- **Archived notes updated**: Omnara (repo un-archived and now a different product: a managed agent
  platform), opcode (commits resumed 2026-09/11, still no release since v0.2.0).
- **Kept with a note, scope drifting**: Vibe Kanban (sunset by Bloop, community-maintained),
  CodePilot (mostly its own general agent, Claude Code optional), BossConsole (built around its own
  agent), Orkas (own agent team plus external CLIs), OpenSwarm (CI/CD gate, external CLIs optional),
  Agency Orchestrator (role library, coding CLIs one backend). Revisit at the next pass.

## 2026-11-08 — full re-curation (discovery + pruning)

The 11-07 pass only searched repos created since 2026-03 with ≥150★ and pruned only gone/archived
repos. This pass widened both sides.

**Pruning rules (now in the Legend and CONTRIBUTING.md)**
- No default-branch commit in the last 90 days → removed, or moved to Archived if ≥2,000★.
  Archived: CodexMonitor, Aperant, toad, VibeTunnel, ralphy, Antfarm, claude-code.nvim (+ automaker).
  Removed (18): opensessions, fox-ai-roundtable, recensa, OpenKanban, foreman, takopi,
  claude-code-by-agents, FleetCode, Helmor, Agent Viewer, AgentPipe, codex-orchestrator, kanbots,
  OpenGoat, Constellagent, Claude Code Plus, Aizen, multi-agent-shogun.
- Curation bar raised ~50★ → ~100★ (exception: under ~3 months old and actively developed).
  Removed: ultracodex, dux, jmux. Kept: Martty (created 2026-08, very active).
- ⚠️ now means ≤3 default-branch commits in 90 days (was: 180 days without a commit).
- Scope drift → Related › agents that double as apps: CodePilot, BossConsole, Orkas, OpenSwarm,
  Agency Orchestrator (each now centred on its own agent).

**Discovery**
- GitHub: 126 searches (100 keyword queries over name/description/README + 25 topics), no
  creation-date limit, ≥100★, pushed since 2026-08-10 → ~5,200 unlisted repos, keyword-filtered to
  202 for review.
- Web: two research agents (English: HN Show HN, Product Hunt, roundups, directories, other awesome
  lists, closed-source products; CJK: Chinese/Japanese/Korean GitHub queries and community sites)
  → 273 repo candidates + 23 closed-source products.
- Every candidate's README was read (closed-source: site + independent coverage) and checked for
  ≥100★, ≥4 commits since 2026-08-10, not fork/archived, standalone client of separate agents.
- **Added 283 repos + 6 closed-source** (JetBrains Air, GitHub Agent HQ, Xcode, Twill, Replicas,
  Zenflow). New Related block **First-party agent apps** (Codex app, Claude Code desktop, Cursor
  Agents Window, Antigravity, Ona). Coding-agent line gained DeepSeek Harness, Grok Build,
  Antigravity CLI, Qwen Code, Kimi Code.
- **Rejected for distinctness/scope** (not exhaustive): DeepSeek Harness redistributions/launchers
  that bundle the official web UI (anywhere-labs/dsh-desktop, dsh-tauri/deepseek-harness-desktop,
  ningbainb, myYangyunfan, vibeinging, chokwinlee, MichengAI, yyh-001/DSH-X, MarcoG-h/DSH-Launcher,
  cocode-agency/cocode) and on-phone redistributions (Soodok, dphmoblie); DSH plugins (dsh-pocket,
  dsh-sev, dsh-web); API proxies/trace wrappers (claude-tap, cc-viewer); generic routers/assistants
  (RabiRoute, Dodaios); installers/switchers (terminal-jarvis, cc-switch); worktree helpers
  (agent-worktree); possibly discontinued or stale (herdrm, session-kit, hive). First-party agents
  themselves (Kiro, Jules, Devin) left out. Per-candidate verdicts are in the pass's scratch files.
- **Known limits**: the keyword filter on the 5,200-repo GitHub pool can miss tools whose
  description doesn't name an agent; Reddit and X were not swept; star counts of some new CJK repos
  rose very fast and were not audited for star inflation.

## 2026-11-17 refresh — second discovery + pruning pass

Same rules as 11-08 (90-day activity, ~100★ bar, ⚠️ = ≤3 commits in 90 days). All entries re-audited
via GraphQL (stars, archive/fork state, default-branch commits since 2026-08-19).

- **Removed (no default-branch commit in 90 days, <2,000★)**: Bivor, WeChat ACP, dmux.
- **Removed (scope)**: Martty, which now describes itself as a DeepSeek Harness plugin and is still under 100★.
- **Renamed**: Cetus `drewnekota/cetus` → `william-jin-cmu/cetus`.
- **⚠️ reset** to the 11 entries at ≤3 commits/90d: AgentHub (jamesrochabrun), Claude Squad,
  Cline (Kanban), DevThrottle, Dorothy, MioIsland, OpenCovibe, Routa, claude-code-ide.el,
  claude_code_agent_farm, lalph.
- **Discovery**: resumable GitHub keyword/topic harvest plus web search; 92 candidates read against
  their READMEs by verify agents. **Added 74**:
  - Desktop (28): Ekko Studio, Cindy, bb, Clowder AI, Sheprd, Kero, openteams, Timon, Intent, Tucano,
    Codex Bridge, Up.computer, Conduit, Pi GPUI, Gold Band, Threadbear, Antumi, Workbench, Ness, Mokusei,
    touri, xMatrix, Friday, Codealong, Obeya, iCode Workbench, Unstoppable Code, BAND for Developers (closed source).
  - Terminal (12): LoopX, Agent Autoloop, gnhf, tty7, Luvus, wmux (amirlehmam), tsk, numbrone, Imbo, troupe,
    nsq (NeuroSquad), chord.
  - IDE (1): FluxCode.
  - Web (11): It's a Plan, agentes.chat, SoduWork, PandaDOS, Hive, Bosun, Harness Maxxing, wicked-studio,
    PI WEB (Gang-of-Beads), Cocogem, AgentForeman.
  - Cloud (3): AgentConnect, ABCA, pi pod.
  - Mobile (7): Switch, Pi-Remote, Pairfob, cccodroid, OpenCode Mobile (beppe2880), pi-phone, pi-durable telegram.
  - Session viewers (12): Kanzo, Obelisk, herdr-annotate, Capri, Bailong Desktop Pet, Irrlicht, ChatVault,
    Rhizome, agent-board, Flockbook, Muster, Cubicle Crew.
  - Entries under 100★ were all created after 2026-08-17 and have at least 30 commits, so they fall under the new-and-active exception.
- **Related › adjacent tooling**: Worktrunk (git worktree CLI for parallel agent work, not an agent manager; listed under Related).
- **Rejected**:
  - claude-tap: an API proxy.
  - Harp, Wu, GOAT: hard forks of Warp, Zed and T3 Code.
  - herdrm: possibly discontinued. herdr-radar: in maintenance mode.
  - RabiRoute, Dodaios: rejected before.
  - Open Design, SOMA, Eleven: apps for a single domain (design, CAD, reverse engineering), not agent clients.
  - Kun: its own agent runtime.
  - Open Managed Agents: a managed-agent platform.
  - Claudepot: built around account switching.
  - agent-speed: a benchmark.
  - session-migrate: a transcript converter.
  - OpenMicro: a game-controller input device.

## 2026-11-21 refresh — four-day delta

Same rules as 11-08/11-17. Audit window for activity and ⚠️: default-branch commits since 2026-08-23.

- **Removed (repo deleted, 404)**: proliferate, DevThrottle.
- **Removed (no default-branch commit in 90 days, <2,000★)**: AgentHub (jamesrochabrun), Clarc, Pilot Harness, open-tag.
- **Renamed**:
  - Mokusei → Chief (`hupao-creator/Chief`); its description was refreshed.
  - Claude Code History Viewer → Omnilogue (`jhlee0409/omnilogue`).
  - Lody iOS repo moved to `LodyAI/lody-ios`.
- **Updated**:
  - Conductor: Meta acquired it in early November 2026. Conductor Cloud went read-only on Nov 13 and shut down on Nov 20, and from early 2027 the Mac app gets no new models or critical fixes. Sources are news reports quoting the CEO's post, such as The Register on 2026-11-05.
  - Frink: frink.dev returns 402, so the entry links to the GitHub repo.
- **⚠️ reset** to the 13 entries with ≤3 commits in 90 days. Newly flagged: Agent Control Center, Agyn, Claude Control, DSH Remote Web Gateway, Nexting. Cleared: claude-code-ide.el.
- **Discovery**:
  - GitHub search: 75 keyword and topic queries returned 1,757 repos. A filter on description keywords, earlier rejections and activity left 69 to check.
  - Web search: Show HN, andyrewlee/awesome-agent-orchestrators and other awesome lists gave 124 more candidates.
  - Verify agents read the README of every candidate that passed the bar: ≥100★ with >3 commits in 90 days, or created after 2026-08-21 with ≥50★ and ≥30 commits.
- **Added 46**:
  - Desktop (17): ThinkTerm, EnsoCode, Helicon, Farcaster, Termilly, Munder Difflin, Beluga, TOKENICODE,
    TaroBird, Agentaps, Kybern, Prometeu, Muxflow (PR #27), CodeDen, Claude Web, Novadeck, Herdr app.
  - Terminal (5): Axel, broco, ELU, Overseer, pi-cowboy.
  - IDE (1): opencode.nvim (sudo-tee).
  - Web (4): Herdr World, Chief of Staff, Pi Dash, vibepanel.
  - Cloud (1): monoid.
  - Mobile (9): OpenCode Mobile (Eslamasabry), BrewPing, Mobile Codex, RexPocket, Doriterm, Termish, Horus,
    Telegram Agents for Herdr, OpenCode Android (Dajeovv, PR #16).
  - Session viewers (9): Code-Codex, Agent Notifications, Claude Code Filetree, claude-share, Project Sentinel,
    Möbius, whatsmyagentdoing, dotpals, AgentMon Live.
- **Rejected**:
  - Built around their own agent: eigent, nautilo, orbs.
  - Not a client:
    - buddy-android: a phone-automation assistant.
    - claude-show-your-work: renders the agent's output.
    - better-harness: a skill pack.
    - cc-remote: an ACP adapter.
  - Forks or derivatives of listed tools:
    - agent-duel: a hard fork of Paseo.
    - planrelay: Plannotator with its history copied in.
    - Dev-Labs: a fork of Munder Difflin.
  - First-party and not yet public: anomalyco/opencode-android (internal Play testing, no license).
  - herdr-core: covered by the herdr entry.
  - Previously rejected: Dodaios.
  - Closed-source tools found only through Show HN or Product Hunt, with no traction signal yet, were deferred. These include Thrum, CodeConnect, Halyard, Clawdline, Cosyra, Skep and the Mac notch apps.
- **Community submissions on hold** for the ~100★ bar or until public release:
  - Anywhere (PR #29, 19★)
  - Velion (PR #26, closed beta)
  - Open Agent API (#28)
  - Conduit Bridge (#18)
  - Mons (#23)
  - Kronos, Sillage, Superagent, PinkCollab, Layerbase, Kortix (earlier PRs)

## Out of scope (recorded for reviewers)

Goose, Hermes Desktop/Agent, OpenClaw (general assistants/agents); FleetQ (general DAG
multi-agent platform); AgentTier (Kubernetes agent-sandbox infrastructure); ghast (cmux fork).
