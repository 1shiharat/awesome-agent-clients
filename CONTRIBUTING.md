# Contributing to Awesome Agent Clients

Thanks for helping keep this list accurate and useful! This list curates **clients and
orchestrators for AI coding agents** — the tools that run, manage, and orchestrate agents
like Claude Code, OpenAI Codex, Gemini CLI, OpenCode, Aider, and Cursor CLI.

## What belongs here (inclusion criteria)

A tool is **in scope** if it meets all three:

1. **It wraps or manages external coding agents.** It launches, runs, orchestrates, or
   provides a UI for one or more *separate* coding agents.
2. **It is real and reachable.** It has an official site and/or a public repository that
   actually exists.
3. **It is distinct.** Not a fork/mirror of an already-listed tool, and not a duplicate entry.

**Out of scope** (these belong in [Related](README.md#related-agents-frameworks--protocols),
not as primary entries):

- The coding agents themselves (Claude Code, Codex, Aider, Goose, …).
- General-purpose assistants that happen to do some coding (e.g. OpenClaw, Hermes Agent).
- Generic multi-agent DAG/workflow frameworks and sandbox infrastructure that don't manage
  coding-agent CLIs in a working repo (e.g. FleetQ, AgentTier).

**Borderline cases** are welcome — flag them in your PR and we'll discuss:

- An agent that *also* ships an orchestrator → list the orchestrator component (e.g. Cline → its Kanban).
- A tool with its own agent loop but a fleet-management UX → keep it with a note.
- Pure session viewers / observability tools → the [Session viewers & companion tools](README.md#session-viewers--companion-tools) section, clearly labelled.

### Quality bar

We aim to be comprehensive but curated. As a rough adoption signal, projects with **fewer than
~50 GitHub stars** are usually held back until they gain some traction — unless they do
something genuinely novel. Recent activity and a working install path help. Entries carry a
live GitHub-stars badge and are sorted by star count within each section; the star count is a
signal of adoption, not a judgment of quality.

## Entry format

Add your tool to the **single most appropriate** platform section, keeping entries
alphabetically reasonable within their group. Use this shape:

```markdown
- [Name](best-url) — One neutral sentence describing what it does. <emoji>
  - `owner/repo` (or `closed-source`) · License · Platforms · MCP/ACP · Agents · *Distinctive:* the 1–2 things that set it apart.
```

- **Link** to the official site if it exists, otherwise the repo.
- **Description**: one neutral sentence. No marketing language ("blazingly fast",
  "the best", "revolutionary"). Describe what it *does*, evidence-based.
- **Emoji**: 🔓 open source · 🟡 source-available / open-core · 🔒 closed-source.
- **Platforms**: e.g. macOS, Windows, Linux, iOS, Android, CLI, Web, TUI, Neovim, JetBrains.
- **Agents**: the external coding agents it can drive (omit for session viewers / note "reads").
- Cite a **source** in your PR description for any non-obvious claim.

Example:

```markdown
- [Orca](https://www.onorca.dev/) — Agent Development Environment that runs many CLI coding agents side by side, each with its own git worktree. 🔓
  - `stablyai/orca` · MIT · macOS/Windows/Linux/iOS/Android/CLI · MCP · *Distinctive:* worktree-per-task, "Design Mode" Chromium capture, mobile companion.
```

## How to contribute

1. **Fork** this repository and create a branch.
2. **Edit `README.md`** (and the [Contents](README.md#contents) table if you add a section).
3. Keep the change focused — one tool per PR is easiest to review.
4. **Open a PR** describing the tool and linking a source (official site, repo, release notes).
   Or, if you'd rather not edit, [suggest a tool via an issue](../../issues/new?template=suggest-a-tool.md).

### Corrections

Found a stale star count, wrong license, dead link, or an agent that's no longer supported?
A small PR with a source link is the fastest fix. See the
[data-quality note](README.md#a-note-on-data-quality) — many entries are research-grade and
have not been independently re-verified, so corrections are genuinely appreciated.

## Code of conduct

By participating you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

By contributing, you agree that your contributions are dedicated to the public domain under
[CC0-1.0](LICENSE).
