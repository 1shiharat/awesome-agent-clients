# Awesome Agent Clients [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[English](README.md) | **日本語**

> Claude Code、OpenAI Codex、Gemini CLI、OpenCode、Aider、Cursor CLI といったコーディングエージェントを**動かし、束ね、オーケストレーションする**ためのクライアント／オーケストレーターを集めました。デスクトップ、ターミナル、モバイル、Web、IDE と、動く場所はさまざまです。

ここ1〜2年で、コーディングエージェントの使い方は「1つと対話する」から「何個も同時に走らせる」へと変わりました。下に並べたのは、その何個ものエージェントを動かすための道具です。エージェントを立ち上げ、それぞれを別々の git worktree やサンドボックスに閉じ込め、差分を確認し、最近ではスマホからでも進み具合を見て指示を返せます。集めたのは**エージェント本体ではなく、それを動かす側のツール**。エージェント本体は[関連](#related)にまとめました。

## 目次

- [凡例](#legend)
- [デスクトップ／マルチプラットフォームクライアント](#desktop)
- [ターミナル／CLI オーケストレーター](#terminal)
- [IDE／エディタプラグイン](#ide)
- [Web／セルフホスト型ダッシュボード](#web)
- [クラウド／ホスト型コントロールプレーン](#cloud)
- [モバイル／遠隔操作クライアント](#mobile)
- [セッションビューア／コンパニオンツール](#viewers)
- [アーカイブ／注目プロジェクト](#archived)
- [関連: エージェント・フレームワーク・プロトコル](#related)
- [コントリビュート](#contributing)
- [データ品質についての注記](#dataquality)

<a id="legend"></a>
## 凡例

各エントリは1行です:

> **[名前](リンク)** ★バッジ 🔓 — 何をするか。`license` `platforms` `protocol` `agents`

- 🔓 オープンソース · 🟡 ソースアベイラブル／オープンコア · 🔒 クローズドソース
- ★ バッジは [shields.io](https://shields.io) で自動更新。**各セクションは star 数の多い順**に並べています。クローズドソース製品にバッジはありません。
- `BSL-1.1→Apache-2.0` のようなタグは「今は source-available で、後から指定のオープンライセンスへ自動転換される」という意味です。
- `MCP` / `ACP` は対応プロトコル。末尾のタグは、そのツールが動かせる外部コーディングエージェント（数が多い場合は件数）。
- 収録の目安: star 数が約50に満たないツールは見送ります（[コントリビュート](#contributing)参照）。star はあくまで目安で、優劣の判定ではありません。
- エントリ末尾の ⚠️ は、メンテが停滞している（最近コミットがない）ツールの目印です。並び順は star 基準なので、人気があっても停滞しているツールは上位に残ることがあります。

---

<a id="desktop"></a>
## デスクトップ／マルチプラットフォームクライアント

デスクトップで動くネイティブ／Electron アプリ。モバイルや Web のコンパニオンを持つものも多い。

- [opcode](https://github.com/winfunc/opcode) [![★](https://img.shields.io/github/stars/winfunc/opcode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/winfunc/opcode/stargazers) 🔓 — Claude Code を GUI で扱うツールキット。セッション・カスタムエージェント・バックグラウンド実行・チェックポイント確認。`AGPL-3.0` `mac/Win/Linux` `MCP` `Claude Code` ⚠️ *メンテ停滞ぎみ — 2025-10 以降コミットなし（最新リリース v0.2.0）*
- [Orca](https://www.onorca.dev/) [![★](https://img.shields.io/github/stars/stablyai/orca?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/stablyai/orca/stargazers) 🔓 — 多数の CLI エージェントを並べて走らせ、各々に専用の worktree・ターミナル・ブラウザタブを与える ADE。`MIT` `mac/Win/Linux/iOS/Android` `MCP` `25+ agents`
- [openwork](https://github.com/different-ai/openwork) [![★](https://img.shields.io/github/stars/different-ai/openwork?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/different-ai/openwork/stargazers) 🟡 — Claude Cowork のオープンソース代替。opencode ベースのエージェントセッションをローカル／リモートで実行・管理するデスクトップクライアント。`source-available` `Desktop/Web` `opencode`
- [Aperant](https://aperant.com) [![★](https://img.shields.io/github/stars/AndyMik90/Aperant?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AndyMik90/Aperant/stargazers) 🔓 — 複数の Claude Code ターミナルを起動・連携させ、自律的にマルチセッションでコーディングする Electron 製 Kanban アプリ。`AGPL-3.0` `mac` `Claude Code`
- [Superset](https://superset.sh/) [![★](https://img.shields.io/github/stars/superset-sh/superset?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/superset-sh/superset/stargazers) 🟡 — 10以上の CLI エージェントを並列実行、各々を専用 worktree に隔離する macOS ワークスペース。差分レビュー内蔵。`Elastic-2.0` `mac` `10+ agents`
- [CodeLayer](https://github.com/humanlayer/humanlayer) [![★](https://img.shields.io/github/stars/humanlayer/humanlayer?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/humanlayer/humanlayer/stargazers) 🔓 — 複数の Claude Code セッションを並列で実行・管理する HumanLayer 製の Tauri デスクトップ IDE。承認ワークフロー付き。`Apache-2.0` `Desktop` `Claude Code`
- [Paseo](https://paseo.sh/) [![★](https://img.shields.io/github/stars/getpaseo/paseo?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/getpaseo/paseo/stargazers) 🟡 — 5つのエージェントを1画面で動かすセルフホスト型デーモン。デスクトップ／モバイル／Web／CLI から接続。`source-available` `Desktop/iOS/Android/Web/CLI` `MCP` `5 agents`
- [CodePilot](https://github.com/op7418/CodePilot) [![★](https://img.shields.io/github/stars/op7418/CodePilot?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/op7418/CodePilot/stargazers) 🟡 — Claude Code CLI をラップするクロスプラットフォームのデスクトップクライアント。複数プロバイダ＋メッセージアプリ遠隔操作。`BSL-1.1→Apache-2.0` `mac/Win/Linux` `MCP` `Claude Code`
- [1code](https://1code.dev/) [![★](https://img.shields.io/github/stars/21st-dev/1code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/21st-dev/1code/stargazers) 🟡 — Claude Code と Codex をローカル／クラウドサンドボックスで worktree 隔離して動かすオープンコアのデスクトップ／Web クライアント。`Apache-2.0` `mac/Win/Linux/Web/PWA` `MCP` `Claude Code/Codex`
- [emdash](https://emdash.sh/) [![★](https://img.shields.io/github/stars/generalaction/emdash?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/generalaction/emdash/stargazers) 🔓 — 多数のコーディングエージェント CLI を並列実行、各々を専用 worktree に隔離するデスクトップアプリ。横断差分レビュー付き。`Apache-2.0` `mac/Win/Linux` `10+ agents`
- [CodexMonitor](https://github.com/Dimillian/CodexMonitor) [![★](https://img.shields.io/github/stars/Dimillian/CodexMonitor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dimillian/CodexMonitor/stargazers) 🔓 — 複数の Codex エージェントを監視・オーケストレーションする macOS アプリ。`MIT` `mac` `Codex`
- [automaker](https://automaker.app/) [![★](https://img.shields.io/github/stars/AutoMaker-Org/automaker?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AutoMaker-Org/automaker/stargazers) 🔓 — 作りたい機能を書くとエージェントが実装していく Kanban 開発スタジオ。Codex・Copilot・Cursor・Gemini・OpenCode をプロバイダとして追加できる。`MIT` `Desktop/Web` `Claude Code/Codex/+3`
- [CodeNomad](https://github.com/NeuralNomadsAI/CodeNomad) [![★](https://img.shields.io/github/stars/NeuralNomadsAI/CodeNomad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/NeuralNomadsAI/CodeNomad/stargazers) 🔓 — OpenCode CLI をマルチセッションのデスクトップ作業場にまとめる Electron/Tauri 製「コックピット」。`MIT` `Desktop` `OpenCode`
- [AgentsMesh](https://agentsmesh.ai/) [![★](https://img.shields.io/github/stars/AgentsMesh/AgentsMesh?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AgentsMesh/AgentsMesh/stargazers) 🟡 — 複数マシンのセルフホスト・ランナー群を1コンソールから操り、ターミナルエージェントを動かす。`BSL-1.1→GPL-2.0` `Web/Desktop/iOS/CLI` `5 agents`
- [mux](https://mux.coder.com/) [![★](https://img.shields.io/github/stars/coder/mux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coder/mux/stargazers) 🔓 — 多数のエージェントを Local／Worktree／SSH ランタイムで並列実行する Coder 製アプリ（独自エージェントループ）。`AGPL-3.0` `mac/Linux/Web/VSCode` `multi-model`
- [Agent Teams AI](https://agentteams.live/) [![★](https://img.shields.io/github/stars/777genius/agent-teams-ai?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/777genius/agent-teams-ai/stargazers) 🔓 — エージェントのチームが互いにメッセージし、コードを相互レビューするデスクトップアプリ。`AGPL-3.0` `mac/Win/Linux` `MCP` `Claude Code/Codex/OpenCode`
- [Helmor](https://github.com/dohooo/helmor) [![★](https://img.shields.io/github/stars/dohooo/helmor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/dohooo/helmor/stargazers) 🔓 — 多数のコーディングエージェントを並列実行し、各々を隔離した git ワークスペースで動かすローカルデスクトップワークベンチ。ワンクリック PR 付き。`Apache-2.0` `mac/Win` `Claude Code/Codex/Cursor/OpenCode/Kimi`
- [Nimbalyst](https://github.com/Nimbalyst/nimbalyst) [![★](https://img.shields.io/github/stars/Nimbalyst/nimbalyst?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Nimbalyst/nimbalyst/stargazers) 🔓 — Codex・Claude Code・OpenCode・Copilot 用の視覚的ワークスペース兼 並列セッション／kanban マネージャ。赤緑の差分承認と iOS コンパニオン付き。`MIT` `Desktop/Web/iOS` `Codex/Claude Code/+2`
- [Cline (Kanban)](https://cline.bot/) [![★](https://img.shields.io/github/stars/cline/kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/cline/kanban/stargazers) 🔓 — Cline プロジェクト（60k★超）のコンパニオン Kanban。並列 CLI エージェントを隔離 worktree で動かす。`Apache-2.0` `CLI/Web` `auto-detected agents`
- [jean](https://github.com/coollabsio/jean) [![★](https://img.shields.io/github/stars/coollabsio/jean?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coollabsio/jean/stargazers) 🔓 — Claude Code・Codex・Cursor・OpenCode をまたいでプロジェクト・worktree・セッションを管理する Tauri 製デスクトップ開発環境。`Apache-2.0` `Desktop` `Claude Code/Codex/Cursor/OpenCode`
- [claude-code-by-agents](https://claudecode.run/) [![★](https://img.shields.io/github/stars/baryhuang/claude-code-by-agents?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/baryhuang/claude-code-by-agents/stargazers) 🔓 — 複数の Claude Code エージェントをマシン横断で @メンション振り分けする Swift 製 macOS/iOS アプリ。`MIT` `mac/iOS` `Claude Code`
- [Parallel Code](https://github.com/johannesjo/parallel-code) [![★](https://img.shields.io/github/stars/johannesjo/parallel-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/johannesjo/parallel-code/stargazers) 🔓 — エージェント CLI を並列起動、各々を専用 worktree に隔離して差分レビューと選択マージを行うデスクトップアプリ。`MIT` `mac/Linux` `Claude Code/Codex/Gemini/+2`
- [AI Maestro](https://github.com/23blocks-OS/ai-maestro) [![★](https://img.shields.io/github/stars/23blocks-OS/ai-maestro?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/23blocks-OS/ai-maestro/stargazers) 🔓 — マシンをまたいでターミナルエージェントを束ねるプラットフォーム。ダッシュボード・永続メモリ・エージェント間メッセージング。`MIT` `mac/Linux/Win(WSL2)/Web/CLI` `multi-agent`
- [FleetCode](https://github.com/built-by-as/FleetCode) [![★](https://img.shields.io/github/stars/built-by-as/FleetCode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/built-by-as/FleetCode/stargazers) 🔓 — Claude Code と Codex を git-worktree 隔離で並列実行する軽量なデスクトップ制御ペイン。`license: see repo` `Desktop` `Claude Code/Codex`
- [Dorothy](https://github.com/Charlie85270/Dorothy) [![★](https://img.shields.io/github/stars/Charlie85270/Dorothy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Charlie85270/Dorothy/stargazers) 🔓 — Claude Code・Codex・Gemini をプロジェクト横断で並列にさばくデスクトップアプリ。kanban とメタオーケストレーター付き。`MIT` `mac/Linux` `MCP` `Claude Code/Codex/Gemini`
- [Aizen](https://github.com/vivy-company/aizen) [![★](https://img.shields.io/github/stars/vivy-company/aizen?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/vivy-company/aizen/stargazers) 🔓 — プロジェクトごとの環境（ターミナル・ファイル・ブラウザ・ACP エージェントセッション）を管理するネイティブ macOS ワークスペース（Claude Code・Codex・OpenCode）。`GPL-3.0` `mac` `Claude Code/Codex/OpenCode`
- [Constellagent](https://constellagent.vercel.app/) [![★](https://img.shields.io/github/stars/owengretzinger/constellagent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/owengretzinger/constellagent/stargazers) 🔓 — 複数のエージェントセッションを並列実行する macOS アプリ。各々に専用ターミナル・Monaco エディタ・worktree。`license: ?` `mac` `agent-agnostic`
- [Sculptor](https://imbue.com/sculptor/) [![★](https://img.shields.io/github/stars/imbue-ai/sculptor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/imbue-ai/sculptor/stargazers) 🔓 — エージェントを隔離コンテナで並列実行し、成果をローカルリポジトリへ同期する Imbue 製デスクトップアプリ。`MIT` `mac/Linux` `Claude Code/Codex`
- [proliferate](https://github.com/proliferate-ai/proliferate) [![★](https://img.shields.io/github/stars/proliferate-ai/proliferate?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/proliferate-ai/proliferate/stargazers) 🔓 — Claude Code・Codex・OpenCode・Cursor を各エージェント本来のハーネスで並列実行するローカル＋クラウドのエージェント IDE（YC S25）。`AGPL-3.0` `Desktop/Web/Cloud` `4 agents`
- [Conductor](https://www.conductor.build/) 🔒 — エージェントを並列実行、各々を専用ブランチ・ターミナル・差分の隔離ワークスペースで動かす macOS アプリ（Melty Labs）。`closed-source` `mac` `MCP` `Claude Code/Codex/+2`
- [AgentsRoom](https://agentsroom.dev/) 🔒 — CLI エージェントをプロジェクト横断でネイティブなローカルプロセスとして並列にさばくデスクトップアプリ（iOS/Android 付き）。`closed-source` `mac/Win/Linux/iOS/Android` `MCP` `7 agents`

<a id="terminal"></a>
## ターミナル／CLI オーケストレーター

ペインや tmux、worktree を使ってエージェントを立ち上げ・連携させる、TUI ダッシュボードや CLI 中心のツール。

- [cmux](https://cmux.com/) [![★](https://img.shields.io/github/stars/manaflow-ai/cmux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/manaflow-ai/cmux/stargazers) 🔓 — ターミナルエージェントを並列実行・整理する libghostty ベースのネイティブ macOS ターミナル。分割＋通知付き。`GPL-3.0` `mac (+iOS beta)` `any terminal agent`
- [Gas Town](https://github.com/gastownhall/gastown) [![★](https://img.shields.io/github/stars/gastownhall/gastown?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/gastownhall/gastown/stargazers) 🔓 — Steve Yegge 作のマルチエージェント・オーケストレーター。git バックの状態と見張り階層で束ねる。`MIT` `CLI/TUI/Web` `8 agents`
- [herdr](https://github.com/ogulcancelik/herdr) [![★](https://img.shields.io/github/stars/ogulcancelik/herdr?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/ogulcancelik/herdr/stargazers) 🟡 — 多数のコーディングエージェントのセッションを実行・切替するターミナル常駐のエージェント・マルチプレクサ。`dual-license` `CLI/TUI` `multi-agent`
- [ralph-claude-code](https://github.com/frankbria/ralph-claude-code) [![★](https://img.shields.io/github/stars/frankbria/ralph-claude-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/frankbria/ralph-claude-code/stargazers) 🔓 — Claude Code 向けの自律「Ralph」開発ループ。賢い終了検出付き。`MIT` `CLI` `Claude Code`
- [Agent Orchestrator](https://ao-agents.com) [![★](https://img.shields.io/github/stars/AgentWrapper/agent-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AgentWrapper/agent-orchestrator/stargazers) 🔓 — 並列コーディングエージェントセッションを各々専用 git worktree で起動し、CI 失敗・レビュー・マージ衝突を担当エージェントに差し戻すオーケストレーター。`Apache-2.0` `CLI/Desktop` `23 agents`
- [Claude Squad](https://smtg-ai.github.io/claude-squad/) [![★](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/smtg-ai/claude-squad/stargazers) 🔓 — 複数のエージェントを並列管理するターミナル TUI。各々に専用 worktree と tmux セッション。`AGPL-3.0` `mac/Linux/TUI` `Claude Code/Codex/Gemini/Aider`
- [Omnigent](https://github.com/omnigent-ai/omnigent) [![★](https://img.shields.io/github/stars/omnigent-ai/omnigent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/omnigent-ai/omnigent/stargazers) 🔓 — Claude Code・Codex・Cursor・OpenCode・Hermes・Pi を1つのオーケストレーション層で束ね、設定で差し替えられるメタハーネス。`Apache-2.0` `CLI/Multi` `6 agents`
- [toad](https://github.com/batrachianai/toad) [![★](https://img.shields.io/github/stars/batrachianai/toad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/batrachianai/toad/stargazers) 🔓 — Claude Code・Codex・Copilot などの AI コーディング CLI を1つにまとめるターミナル UI。`AGPL-3.0` `CLI/TUI` `Claude Code/Codex/Copilot/+`
- [Claude Codex Bridge](https://github.com/SeemSeam/claude_codex_bridge) [![★](https://img.shields.io/github/stars/SeemSeam/claude_codex_bridge?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/SeemSeam/claude_codex_bridge/stargazers) 🔓 — 複数の CLI エージェントを制御可能な協調グラフで混在させる「可視化」マルチエージェント TUI ワークスペース。モバイル遠隔操作付き。`AGPL-3.0` `CLI/Web` `9 agents`
- [claude_code_bridge](https://github.com/bfly123/claude_code_bridge) [![★](https://img.shields.io/github/stars/bfly123/claude_code_bridge?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/bfly123/claude_code_bridge/stargazers) 🔓 — Codex・Claude・Gemini・Kimi・Qwen・Cursor・Copilot・Pi・OpenCode を1つのプロジェクトターミナルに混在させる「可視化」マルチエージェント CLI ワークスペース。`AGPL-3.0` `CLI/Web` `9 agents`
- [ralphy](https://github.com/michaelshimeles/ralphy) [![★](https://img.shields.io/github/stars/michaelshimeles/ralphy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/michaelshimeles/ralphy/stargazers) 🔓 — Claude Code・Codex・OpenCode・Cursor・Qwen・Droid を PRD 完了まで回す自律 bash ループ。`license: see repo` `CLI` `6 agents`
- [Agent of Empires](https://github.com/njbrake/agent-of-empires) [![★](https://img.shields.io/github/stars/njbrake/agent-of-empires?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/njbrake/agent-of-empires/stargazers) 🔓 — Linux/macOS 上のエージェントセッションマネージャ。ターミナル TUI とブラウザ／PWA ダッシュボードから操作。`MIT` `CLI/TUI/Web/PWA` `ACP` `13 agents`
- [Antfarm](https://www.antfarm.cool/) [![★](https://img.shields.io/github/stars/snarktank/antfarm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/snarktank/antfarm/stargazers) 🔓 — 決定論的な YAML ワークフローで専門エージェントのチームを動かす TypeScript 製 CLI。`MIT` `CLI/Web` `OpenClaw`
- [Supacode](https://supacode.sh/) [![★](https://img.shields.io/github/stars/supabitapp/supacode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/supabitapp/supacode/stargazers) 🟡 — 50以上の CLI エージェントを並列実行、各々を専用 worktree に隔離する libghostty ベースのネイティブ macOS コマンドセンター。`FSL→Apache-2.0` `mac` `50+ agents`
- [dmux](https://github.com/standardagents/dmux) [![★](https://img.shields.io/github/stars/standardagents/dmux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/standardagents/dmux/stargazers) 🔓 — git worktree とコーディングエージェントのための開発用エージェント・マルチプレクサ。`MIT` `CLI/TUI` `multi-agent`
- [zeroshot](https://github.com/the-open-engine/zeroshot) [![★](https://img.shields.io/github/stars/the-open-engine/zeroshot?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/the-open-engine/zeroshot/stargazers) 🔓 — 独立レビュアーでゲートしたエージェントループを持ち、Claude Code・Codex・Gemini CLI・OpenCode に処理を委ねる自律エンジニアリング CLI。`MIT` `CLI` `Claude Code/Codex/Gemini/OpenCode`
- [Scion](https://googlecloudplatform.github.io/scion/) [![★](https://img.shields.io/github/stars/GoogleCloudPlatform/scion?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/GoogleCloudPlatform/scion/stargazers) 🔓 — エージェントを隔離コンテナで動かし、各々に専用 worktree と認証情報を持たせる実験的なホスト側 CLI＋ハブ（Google Cloud）。`Apache-2.0` `CLI/Web/Linux/Cloud` `Claude Code/Gemini/Codex/OpenCode`
- [babysitter](https://github.com/a5c-ai/babysitter) [![★](https://img.shields.io/github/stars/a5c-ai/babysitter?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/a5c-ai/babysitter/stargazers) 🔓 — 同じ処理を12のコーディングハーネス（Claude Code・Codex・Cursor・Gemini CLI・Copilot・Pi・Hermes・OpenCode ほか）で走らせるハーネス非依存の制御層。`MIT` `CLI` `12 harnesses`
- [multi-agent-shogun](https://github.com/yohey-w/multi-agent-shogun) [![★](https://img.shields.io/github/stars/yohey-w/multi-agent-shogun?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/yohey-w/multi-agent-shogun/stargazers) 🔓 — 最大10並列の Claude Code タスクを「将軍→家老→足軽」階層で走らせる侍テーマの tmux オーケストレーター。`MIT` `CLI/TUI` `Claude Code`
- [TAKT](https://github.com/nrslib/takt) [![★](https://img.shields.io/github/stars/nrslib/takt?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/nrslib/takt/stargazers) 🔓 — コーディングエージェントを再現可能な YAML ワークフロー（plan→implement→review→fix）に落とす OSS CLI。隔離 worktree 付き。`MIT` `CLI` `6 agents`
- [CLI Agent Orchestrator](https://github.com/awslabs/cli-agent-orchestrator) [![★](https://img.shields.io/github/stars/awslabs/cli-agent-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/awslabs/cli-agent-orchestrator/stargazers) 🔓 — 各エージェントを隔離 tmux セッションで動かし、MCP 越しの supervisor–worker で協調させる AWS Labs 製ツール。`Apache-2.0` `CLI/Web` `9 agents`
- [claude_code_agent_farm](https://github.com/Dicklesworthstone/claude_code_agent_farm) [![★](https://img.shields.io/github/stars/Dicklesworthstone/claude_code_agent_farm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dicklesworthstone/claude_code_agent_farm/stargazers) 🔓 — 20体以上の Claude Code エージェントをロックベースの協調とリアルタイム tmux 監視で並列実行。`MIT (+rider)` `CLI/TUI` `Claude Code`
- [Citadel](https://github.com/SethGammon/Citadel) [![★](https://img.shields.io/github/stars/SethGammon/Citadel?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/SethGammon/Citadel/stargazers) 🔓 — Claude Code と Codex の「操作層」。プロジェクト文脈・意図ルーティング・リセット跨ぎの継続性を git worktree で加える。`MIT` `CLI` `Claude Code/Codex`
- [Bernstein](https://bernstein.run/) [![★](https://img.shields.io/github/stars/chernistry/bernstein?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/chernistry/bernstein/stargazers) 🔓 — ゴールを分解し、CLI エージェントを並列 worktree で走らせ、検証してからマージする決定論的な Python 製オーケストレーター。`Apache-2.0` `CLI/Web/VSCode/Cloud` `MCP` `44 agents`
- [tmux-ide](https://github.com/wavyrai/tmux-ide) [![★](https://img.shields.io/github/stars/wavyrai/tmux-ide?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/wavyrai/tmux-ide/stargazers) 🔓 — 任意のプロジェクトを tmux ベースのターミナル IDE に変え、エージェント群（Claude Code・Codex・cursor-agent・Aider）をエージェントごとの状態表示付きで走らせる。`MIT` `CLI/TUI` `Claude Code/Codex/Cursor/Aider`
- [claw-orchestrator](https://github.com/Enderfga/claw-orchestrator) [![★](https://img.shields.io/github/stars/Enderfga/claw-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Enderfga/claw-orchestrator/stargazers) 🔓 — Claude Code・Codex・Gemini・Cursor Agent とカスタム CLI を1つのオーケストレーション系として動かす。`MIT` `CLI` `Claude Code/Codex/Gemini/Cursor/+`
- [Agent Deck](https://github.com/asheshgoplani/agent-deck) [![★](https://img.shields.io/github/stars/asheshgoplani/agent-deck?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/asheshgoplani/agent-deck/stargazers) 🔓 — 多数のエージェントセッションを実行・整理・フォーク・自律監視するターミナル版「司令室」。`MIT` `TUI/CLI/Web` `MCP` `6 agents`
- [h5i](https://github.com/h5i-dev/h5i) [![★](https://img.shields.io/github/stars/h5i-dev/h5i?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/h5i-dev/h5i/stargazers) 🔓 — Claude Code/Codex をサンドボックス化した worktree で走らせ、相互レビューさせ、検証役が再実行・テストして勝者をマージする。`Apache-2.0` `CLI/Web` `Claude Code/Codex`
- [mngr](https://github.com/imbue-ai/mngr) [![★](https://img.shields.io/github/stars/imbue-ai/mngr?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/imbue-ai/mngr/stargazers) 🔓 — 「エージェント版 git」CLI。コーディングエージェントを作成・複製・メッセージし、ローカルの1体から localhost/Docker/Modal/SSH 上の数百体までスケールさせる。`MIT` `CLI` `Claude Code/Codex/+`
- [ntm](https://github.com/Dicklesworthstone/ntm) [![★](https://img.shields.io/github/stars/Dicklesworthstone/ntm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dicklesworthstone/ntm/stargazers) 🔓 — tmux を、ペイン横断でエージェントを立ち上げ・並べ・連携させる司令塔に変える Go 製 CLI。`MIT` `CLI/TUI/Web` `Claude Code/Codex/Antigravity`
- [Pane](https://github.com/dcouple/Pane) [![★](https://img.shields.io/github/stars/dcouple/Pane?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/dcouple/Pane/stargazers) 🔓 — 任意の CLI コーディングエージェントを扱うターミナルファースト・エージェント非依存マネージャ。セルフホスト可能なリモートでスマホからも操作できる。`AGPL-3.0` `CLI/Web/mobile` `any CLI agent`
- [AgentBox](https://agent-box.sh/) [![★](https://img.shields.io/github/stars/madarco/agentbox?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/madarco/agentbox/stargazers) 🔓 — 複数のエージェントを並列実行、各々をローカル（Docker）やクラウドのサンドボックス VM に隔離する CLI。`MIT` `mac/Linux/CLI` `Claude Code/Codex/OpenCode`
- [foreman](https://github.com/VisionForge-OU/foreman) [![★](https://img.shields.io/github/stars/VisionForge-OU/foreman?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/VisionForge-OU/foreman/stargazers) 🔓 — ヘッドレスの Claude Code エージェントを、worktree 隔離した plan→build→e2e のゲート付きパイプラインで起動・監督する Boris 風 TUI。`MIT` `CLI/TUI` `Claude Code`
- [ccswarm](https://github.com/nwiizo/ccswarm) [![★](https://img.shields.io/github/stars/nwiizo/ccswarm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/nwiizo/ccswarm/stargazers) 🔓 — Claude Code を git-worktree 隔離と専門ロールでオーケストレーションするマルチエージェントシステム。`MIT` `CLI` `Claude Code`
- [AgentPipe](https://github.com/kevinelliott/agentpipe) [![★](https://img.shields.io/github/stars/kevinelliott/agentpipe?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/kevinelliott/agentpipe/stargazers) 🔓 — 異なる AI コーディング CLI 同士のマルチエージェント「会話」を共有ルームでオーケストレーションする CLI/TUI。`MIT` `CLI/TUI` `7 agents`
- [amux](https://github.com/andyrewlee/amux) [![★](https://img.shields.io/github/stars/andyrewlee/amux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/andyrewlee/amux/stargazers) 🔓 — 複数のエージェントを並列実行、各々を専用 worktree と tmux セッションに隔離するターミナル UI。`MIT` `mac/Linux/TUI` `6 agents`
- [lalph](https://github.com/tim-smart/lalph) [![★](https://img.shields.io/github/stars/tim-smart/lalph?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/tim-smart/lalph/stargazers) 🔓 — issue（GitHub/Linear）起点で CLI エージェントを worktree で並行実行するオーケストレーター。`MIT` `CLI` `multi-agent`
- [OpenKanban](https://github.com/TechDufus/openkanban) [![★](https://img.shields.io/github/stars/TechDufus/openkanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/TechDufus/openkanban/stargazers) 🔓 — チケットごとに専用 worktree と組み込みエージェントターミナルが立つ、ターミナル UI の kanban ボード。`AGPL-3.0` `mac/Linux/TUI` `5 agents`
- [Agentic Orchestrator (DoorDash)](https://github.com/doordash-oss/agentic-orchestrator) [![★](https://img.shields.io/github/stars/doordash-oss/agentic-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/doordash-oss/agentic-orchestrator/stargazers) 🔓 — Claude Code・Codex・OpenCode を research→plan→implement→review→PR で worktree 連携させる DoorDash OSS の CLI。`Apache-2.0` `CLI` `Claude Code/Codex/OpenCode`
- [dux](https://getdux.app/) [![★](https://img.shields.io/github/stars/patrickdappollonio/dux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/patrickdappollonio/dux/stargazers) 🔓 — エージェント CLI を並列実行、各々を専用 worktree に置く 3 ペイン TUI。git ステージングをその場で扱える。`MIT` `mac/Linux/TUI` `Claude Code/Codex/OpenCode/+`

<a id="ide"></a>
## IDE／エディタプラグイン

エディタの中に住むエージェント／オーケストレーター。

- [CodeCompanion.nvim](https://codecompanion.olimorris.dev/) [![★](https://img.shields.io/github/stars/olimorris/codecompanion.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/olimorris/codecompanion.nvim/stargazers) 🔓 — LLM プロバイダや ACP 経由の外部エージェントにチャットバッファからつなぐ Neovim プラグイン。`Apache-2.0` `Neovim` `MCP+ACP` `9 agents`
- [CC GUI (Claude or Codex)](https://plugins.jetbrains.com/plugin/29342-cc-gui-claude-or-codex-) [![★](https://img.shields.io/github/stars/zhukunpenglinyutong/jetbrains-cc-gui?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/zhukunpenglinyutong/jetbrains-cc-gui/stargazers) 🔓 — Claude Code と Codex の CLI に 2 エンジン構成の GUI をかぶせる JetBrains プラグイン。`MIT` `JetBrains` `MCP` `Claude Code/Codex`
- [claudecode.nvim](https://github.com/coder/claudecode.nvim) [![★](https://img.shields.io/github/stars/coder/claudecode.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coder/claudecode.nvim/stargazers) 🔓 — エディタと Claude Code CLI を WebSocket/MCP ブリッジでつなぐ Neovim 拡張（純 Lua）。`MIT` `Neovim` `MCP` `Claude Code`
- [Obsidian Agent Client](https://rait-09.github.io/obsidian-agent-client/) [![★](https://img.shields.io/github/stars/RAIT-09/obsidian-agent-client?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/RAIT-09/obsidian-agent-client/stargazers) 🔓 — 外部のコーディングエージェントを ACP 経由で Obsidian の vault に取り込むプラグイン。`Apache-2.0` `Desktop (Obsidian)` `ACP+MCP` `7 agents`
- [claude-code.nvim](https://github.com/greggh/claude-code.nvim) [![★](https://img.shields.io/github/stars/greggh/claude-code.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/greggh/claude-code.nvim/stargazers) 🔓 — エディタ内で Claude Code CLI のターミナルをトグルし、ファイル自動リロードや continue/resume に対応する Neovim プラグイン。`MIT` `Neovim` `Claude Code`
- [claude-code-ide.el](https://github.com/manzaltu/claude-code-ide.el) [![★](https://img.shields.io/github/stars/manzaltu/claude-code-ide.el?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/manzaltu/claude-code-ide.el/stargazers) 🔓 — MCP 経由で Claude Code CLI をネイティブ統合し、Emacs のバッファ／ツールへ双方向アクセスを与える Emacs パッケージ。`GPL-3.0` `Emacs` `MCP` `Claude Code`
- [agent-shell](https://github.com/xenodium/agent-shell) [![★](https://img.shields.io/github/stars/xenodium/agent-shell?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/xenodium/agent-shell/stargazers) 🔓 — 任意の ACP 対応エージェント（Claude Agent・Gemini CLI・Auggie・Mistral Vibe ほか）とやり取りするネイティブ Emacs バッファ。`GPL-3.0` `Emacs` `ACP` `multi-agent`
- [Agentic.nvim](https://github.com/carlos-algms/agentic.nvim) [![★](https://img.shields.io/github/stars/carlos-algms/agentic.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/carlos-algms/agentic.nvim/stargazers) 🔓 — ACP 対応エージェントなら何でもエディタ内チャットからつなげる Neovim プラグイン。`MIT` `Neovim` `ACP` `8+ agents`
- [Claude Code Plus](https://plugins.jetbrains.com/plugin/28343-claude-code-plus) [![★](https://img.shields.io/github/stars/touwaeriol/claude-code-plus?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/touwaeriol/claude-code-plus/stargazers) 🔓 — IntelliJ 系 IDE 内で CLI コーディングエージェントを GUI から扱える JetBrains プラグイン。`MIT` `JetBrains` `MCP` `Claude Code/Codex/Gemini`

<a id="web"></a>
## Web／セルフホスト型ダッシュボード

ローカルで動かす、あるいはセルフホストするブラウザ中心のオーケストレーター。

- [Multica](https://multica.ai/) [![★](https://img.shields.io/github/stars/multica-ai/multica?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/multica-ai/multica/stargazers) 🟡 — コーディングエージェントを、issue を割り振れるボード管理のチームメイトに変える OSS の managed-agents プラットフォーム。`Apache-2.0 (mod.)` `Web/self-hosted/Cloud` `12 agents`
- [Vibe Kanban](https://www.vibekanban.com/) [![★](https://img.shields.io/github/stars/BloopAI/vibe-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/BloopAI/vibe-kanban/stargazers) 🔓 — 多数のエージェント CLI でタスクを計画・実行・レビューする kanban。各タスクは隔離 worktree で動く。`Apache-2.0` `mac/Web/CLI` `10 agents`
- [T3 Code](https://t3.codes/) [![★](https://img.shields.io/github/stars/pingdotgg/t3code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/pingdotgg/t3code/stargazers) 🔓 — Codex・Claude Code・Cursor・OpenCode を1画面からさばく OSS の Web／デスクトップ制御プレーン（Theo/Ping）。`MIT` `mac/Win/Linux/Web/CLI` `4 agents`
- [Mission Control](https://github.com/builderz-labs/mission-control) [![★](https://img.shields.io/github/stars/builderz-labs/mission-control?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/builderz-labs/mission-control/stargazers) 🔓 — タスクをコーディングエージェントに割り振り監視する、ローカルの Claude Code・Codex セッションを自動検出するセルフホスト Web ダッシュボード。`MIT` `Web` `Claude Code/Codex`
- [HolyClaude](https://github.com/CoderLuii/HolyClaude) [![★](https://img.shields.io/github/stars/CoderLuii/HolyClaude?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/CoderLuii/HolyClaude/stargazers) 🔓 — Claude Code に加え8つの CLI エージェント・ヘッドレスブラウザ・50以上のツールを Web UI にまとめたコンテナ化 AI コーディングワークステーション。`MIT` `Web/Docker` `9 agents`
- [Agency Orchestrator](https://github.com/jnMetaCode/agency-orchestrator) [![★](https://img.shields.io/github/stars/jnMetaCode/agency-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/jnMetaCode/agency-orchestrator/stargazers) 🔓 — ローカルにインストール済みのエージェント CLI（Claude Code・Gemini・Copilot・Codex ほか）を自動検出し、マルチエージェント実行を組む YAML-DAG ワークフローエンジン。`Apache-2.0` `Web/CLI` `6 agents`
- [Agor](https://github.com/preset-io/agor) [![★](https://img.shields.io/github/stars/preset-io/agor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/preset-io/agor/stargazers) 🟡 — 隔離した git ブランチ・履歴・トークン集計をエージェントセッション周りで管理する Web「チーム司令室」。Claude Code・Codex・Gemini CLI・OpenCode・Copilot・Cursor を駆動。`BSL-1.1` `Web` `6 agents`
- [optio](https://github.com/jonwiggins/optio) [![★](https://img.shields.io/github/stars/jonwiggins/optio?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/jonwiggins/optio/stargazers) 🔓 — コーディングエージェントの群れをタスクからマージ済み PR まで、CI 自己修復付きで運ぶワークフローオーケストレーション。`MIT` `Web` `multi-agent`
- [Alook](https://github.com/alookai/alook) [![★](https://img.shields.io/github/stars/alookai/alook?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/alookai/alook/stargazers) 🔓 — エージェントにロール・受信箱・常駐ローカルランタイムを与えるオーケストレーション層。Web ダッシュボード付きで Claude Code・Codex・OpenCode をラップ。`Apache-2.0` `Web/CLI` `Claude Code/Codex/OpenCode`
- [kanna](https://github.com/jakemor/kanna) [![★](https://img.shields.io/github/stars/jakemor/kanna?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/jakemor/kanna/stargazers) 🔓 — Claude Code と Codex 用の Web ベース UI。`MIT` `Web` `Claude Code/Codex`
- [Catnip](https://github.com/wandb/catnip) [![★](https://img.shields.io/github/stars/wandb/catnip?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/wandb/catnip/stargazers) 🔓 — Claude Code をコンテナ化 worktree サンドボックスで動かすセルフホスト可能な Web サービス（W&B）。iOS アプリ付き。`Apache-2.0` `Web/CLI/iOS/Cloud` `Claude Code`
- [Agent Kanban](https://agent-kanban.dev/) [![★](https://img.shields.io/github/stars/saltbo/agent-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/saltbo/agent-kanban/stargazers) 🟡 — エージェントを暗号鍵で識別するメンバーとして扱い、タスクを取らせ PR まで出させる kanban ボード。`FSL→Apache-2.0` `CLI/Web` `ACP` `5 agents`
- [Agent Viewer](https://github.com/hallucinogen/agent-viewer) [![★](https://img.shields.io/github/stars/hallucinogen/agent-viewer?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hallucinogen/agent-viewer/stargazers) 🔓 — tmux で動く複数の Claude Code エージェントを起動・監視・メッセージする Web kanban ボード。`license: ?` `mac/Linux/Web/mobile` `Claude Code`
- [OpenGoat](https://github.com/marian2js/opengoat) [![★](https://img.shields.io/github/stars/marian2js/opengoat?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/marian2js/opengoat/stargazers) 🔓 — 多数のプロバイダをまたいで作業を連携する、エージェントの階層型組織を組み立てるプラットフォーム。`MIT` `Web/CLI` `5 agents`
- [Kanban Code](https://github.com/langwatch/kanban-code) [![★](https://img.shields.io/github/stars/langwatch/kanban-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/langwatch/kanban-code/stargazers) 🔓 — kanban ボードで複数の Claude Code セッションを束ねるネイティブデスクトップアプリ＋CLI（LangWatch）。`AGPL-3.0` `mac/Win/CLI` `Claude Code`
- [JAT](https://github.com/joewinke/jat) [![★](https://img.shields.io/github/stars/joewinke/jat?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/joewinke/jat/stargazers) 🔓 — 20体以上のエージェントを、ライブセッション・タスク管理・エディタ・自動化トリガーで監督するローカル Web IDE ダッシュボード。`MIT` `Web` `Claude Code/Aider/Cline/Codex/Gemini`
- [Ivy-Tendril](https://github.com/Ivy-Interactive/Ivy-Tendril) [![★](https://img.shields.io/github/stars/Ivy-Interactive/Ivy-Tendril?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Ivy-Interactive/Ivy-Tendril/stargazers) 🟡 — plan→execute→verify→PR のライフサイクルをコスト／トークン追跡付きで管理するエージェント非依存の Web アプリ。Claude・Codex・Copilot・Gemini・OpenCode の CLI をオーケストレーション。`FSL→Apache-2.0` `Web` `5 agents`
- [clideck](https://github.com/rustykuntz/clideck) [![★](https://img.shields.io/github/stars/rustykuntz/clideck?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/rustykuntz/clideck/stargazers) 🔓 — 複数の AI CLI エージェントを同時に実行・連携させるダッシュボード。`MIT` `Web` `multi-agent`

<a id="cloud"></a>
## クラウド／ホスト型コントロールプレーン

エージェントの群れをクラウドで動かす、ホスト型（セルフホストも可）のコントロールプレーン。

- [Oz](https://www.warp.dev/oz) [![★](https://img.shields.io/github/stars/warpdotdev/warp?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/warpdotdev/warp/stargazers) 🟡 — 複数ハーネスをまたいでクラウドのコーディングエージェント群を走らせ・見張る Warp 製プラットフォーム。`MIT/AGPLv3` `Cloud/Web/Desktop/CLI` `MCP` `4 agents` *(★は Warp クライアント全体)*
- [Symphony](https://github.com/openai/symphony) [![★](https://img.shields.io/github/stars/openai/symphony?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/openai/symphony/stargazers) 🔓 — プロジェクト／ボードの作業を、隔離された自律的なコーディングエージェントの実装ランに変える OpenAI 製オーケストレーター（仕様＋Elixir リファレンス実装）。`Apache-2.0` `Cloud/Web` `Codex`
- [sandbox-agent](https://github.com/rivet-dev/sandbox-agent) [![★](https://img.shields.io/github/stars/rivet-dev/sandbox-agent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/rivet-dev/sandbox-agent/stargazers) 🔓 — コーディングエージェントをサンドボックス内で走らせ、HTTP で操作できるようにする（Rivet）。`Apache-2.0` `Cloud/CLI` `Claude Code/Codex/OpenCode/Amp`
- [Centaur](https://centaur.run/) [![★](https://img.shields.io/github/stars/paradigmxyz/centaur?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/paradigmxyz/centaur/stargazers) 🔓 — CLI エージェントハーネスを隔離 K8s サンドボックスで動かし、Slack/API から操作する Paradigm 製のセルフホスト制御プレーン。`Apache-2.0/MIT` `Cloud/CLI/Slack` `Claude Code/Codex/Amp`
- [Tembo](https://tembo.io) 🔒 — コーディングエージェントをクラウドへ移すプラットフォーム。Claude Code・Codex・Cursor・Amp・OpenCode をリポジトリ横断で並列クラウドサンドボックス実行し、Slack/Linear/GitHub/Jira から起動。`closed-source` `Cloud/Slack` `5 agents`
- [Niteshift](https://niteshift.dev) 🔒 — コーディングエージェントのためのフルスタッククラウド。Claude Code・Codex・OpenCode・Pi を持ち込み、ランタイム＋検証ワークフローと数十の同時セッションを Slack/Linear/GitHub から起動。`closed-source` `Cloud/Slack` `4 agents`
- [Duet](https://duet.so) 🔒 — Claude Code を常時稼働のクラウドサーバーで動かし（セッションは数日持続）、スマホから操作できる。スケジューリングとチームチャンネル UI 付き。`closed-source` `Cloud/Mobile` `Claude Code`

<a id="mobile"></a>
## モバイル／遠隔操作クライアント

コーディングエージェントをスマホや遠隔デバイスから起動・操作するためのアプリやブリッジ。

- [Happy](https://github.com/slopus/happy) [![★](https://img.shields.io/github/stars/slopus/happy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/slopus/happy/stargazers) 🔓 — Claude Code と Codex 用のオープンソースなモバイル＋Web クライアント。iOS/Android/Web から並列セッションを起動・生成でき、E2E 暗号化とリアルタイム音声に対応。`MIT` `iOS/Android/Web` `Claude Code/Codex`
- [Claude Code UI](https://github.com/siteboon/claudecodeui) [![★](https://img.shields.io/github/stars/siteboon/claudecodeui?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/siteboon/claudecodeui/stargazers) 🔓 — Claude Code・OpenCode・Cursor CLI・Codex のセッションを遠隔管理する Web＋モバイル GUI。`AGPL-3.0` `Web/Mobile` `Claude Code/OpenCode/Cursor/Codex`
- [VibeTunnel](https://github.com/amantus-ai/vibetunnel) [![★](https://img.shields.io/github/stars/amantus-ai/vibetunnel?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/amantus-ai/vibetunnel/stargazers) 🔓 — 任意のブラウザをターミナルに変え、外出先からコーディングエージェントを操作する。スマホから Claude Code を動かす用途に特化。`MIT` `Web/mobile` `Claude Code/+`
- [takopi](https://github.com/banteg/takopi) [![★](https://img.shields.io/github/stars/banteg/takopi?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/banteg/takopi/stargazers) 🔓 — Codex・Claude Code・OpenCode・Pi のエージェントをチャットから操作する Telegram ブリッジ。`MIT` `Telegram` `Codex/Claude Code/OpenCode/Pi`

<a id="viewers"></a>
## セッションビューア／コンパニオンツール

エージェントのセッションを眺めて分析するためのツール（起動や操作はしない）。上のツールと組み合わせて使う。

- [AgentsView](https://www.agentsview.io/) [![★](https://img.shields.io/github/stars/kenn-io/agentsview?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/kenn-io/agentsview/stargazers) 🔓 — コーディングエージェントのセッションログを索引化し、検索・コスト分析・傾向を見せるローカルファーストのツール（観測専用）。`MIT` `mac/Win/Linux/CLI/Web` `reads 20+ agents`
- [opensessions](https://github.com/Ataraxy-Labs/opensessions) [![★](https://img.shields.io/github/stars/Ataraxy-Labs/opensessions?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Ataraxy-Labs/opensessions/stargazers) 🔓 — 各エージェントのトランスクリプトを読み、セッション横断でライブ状態を表示する Rust 製 tmux サイドバー（Amp・Claude Code・Codex・OpenCode）。`license: see repo` `CLI/TUI` `reads 4 agents`
- [agent-flow](https://github.com/patoles/agent-flow) [![★](https://img.shields.io/github/stars/patoles/agent-flow?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/patoles/agent-flow/stargazers) 🔓 — Claude Code セッションのエージェント／サブエージェントが思考・分岐・連携する様子をリアルタイムのグラフで描く VS Code 拡張。`Apache-2.0` `VSCode` `reads Claude Code`
- [Claude Code Agent Monitor](https://hoangsonww.github.io/Claude-Code-Agent-Monitor/) [![★](https://img.shields.io/github/stars/hoangsonww/Claude-Code-Agent-Monitor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hoangsonww/Claude-Code-Agent-Monitor/stargazers) 🔓 — Claude Code のセッション・ツール使用・コスト・サブエージェントを可視化するセルフホストのリアルタイムダッシュボード（観測）。`MIT` `Web/mac/Win/VSCode/CLI` `MCP` `reads Claude Code`
- [agent-sessions](https://github.com/jazzyalex/agent-sessions) [![★](https://img.shields.io/github/stars/jazzyalex/agent-sessions?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/jazzyalex/agent-sessions/stargazers) 🔓 — Codex と Claude Code のセッションを閲覧・検索・分析・再開できるローカルファーストの macOS アプリ。`MIT` `mac` `reads Codex/Claude Code`
- [agenttrace](https://github.com/luoyuctl/agenttrace) [![★](https://img.shields.io/github/stars/luoyuctl/agenttrace?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/luoyuctl/agenttrace/stargazers) 🔓 — Claude Code と Codex のセッションログからコスト・トークン・時間・ツール失敗を追跡するローカルファーストの TUI。`MIT` `CLI/TUI` `reads Claude Code/Codex`

<a id="archived"></a>
## アーカイブ／注目プロジェクト

もう活発には保守されていないものの、振り返る価値のあるプロジェクト。

- [Crystal](https://github.com/stravu/crystal) [![★](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/stravu/crystal/stargazers) — 複数の Claude Code/Codex セッションを並列実行、各々を専用 worktree で動かした Electron アプリ。`MIT` `mac/Win/Linux` **提供終了 → 現在は [Nimbalyst](https://nimbalyst.com/)**
- [Terragon](https://github.com/terragon-labs/terragon-oss) [![★](https://img.shields.io/github/stars/terragon-labs/terragon-oss?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/terragon-labs/terragon-oss/stargazers) — ホスト型のバックグラウンドエージェント群オーケストレーター。`Apache-2.0` **サービス終了 2026-01-16・保守なしのスナップショット**
- [Claude Code Board](https://cc-board.cablate.com/) [![★](https://img.shields.io/github/stars/cablate/Claude-Code-Board?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/cablate/Claude-Code-Board/stargazers) — 複数の Claude Code CLI セッションを束ねる Web の kanban 風マネージャ。`MIT` **保守終了（2026-01）**
- [Omnara](https://github.com/omnara-ai/omnara) [![★](https://img.shields.io/github/stars/omnara-ai/omnara?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/omnara-ai/omnara/stargazers) — Claude Code/Codex をスマホから起動・監視・操作するモバイルファーストの司令室（YC S25）。`Apache-2.0` **リポジトリはアーカイブ済み**

<a id="related"></a>
## 関連: エージェント・フレームワーク・プロトコル

クライアント／オーケストレーターそのものではないけれど、上のツールが動かしたり連携したりする相手。

**コーディングエージェント（オーケストレーション対象）**
- [Claude Code](https://github.com/anthropics/claude-code) · [OpenAI Codex](https://github.com/openai/codex) · [Gemini CLI](https://github.com/google-gemini/gemini-cli) · [OpenCode](https://github.com/sst/opencode) · [Aider](https://github.com/Aider-AI/aider) · [Cursor CLI](https://cursor.com/cli) · [Amp](https://ampcode.com/) · [Pi](https://github.com/parallel-web/pi)

**デスクトップアプリも兼ねるエージェント（クライアントとしては対象外）**
- [Goose](https://github.com/block/goose) — LLM に直接つなぎ、ACP サーバーとしても動く Block の拡張可能な Rust 製エージェント。Orca・Paseo・cmux などに動かされる側。
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) — Nous Research の汎用自己改善エージェント。Agent Kanban・AI Maestro が ACP 経由で呼び出し、Multica でも対応エージェントとして使える。
- [OpenClaw](https://github.com/openclaw/openclaw) — セルフホストのパーソナルアシスタントランタイム。Antfarm と OpenGoat の土台。

**マルチエージェントフレームワーク／インフラ（隣接領域）**
- [FleetQ](https://github.com/escapeboy/agent-fleet-o) — ネイティブ MCP サーバーを備えた汎用マルチエージェント DAG／ワークフロープラットフォーム。
- [AgentTier](https://github.com/agenttier/agenttier) — エージェントを動かすための Kubernetes ネイティブなサンドボックス as a service（インフラ層）。
- [claude-flow](https://github.com/ruvnet/claude-flow) — Claude Code / Codex をネイティブ統合し、協調するマルチエージェント・スウォームを展開するエージェント・メタハーネス（〜64k★）。ターンキーのクライアントというより重量級のスウォームフレームワーク。

**プロトコル**
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) — エージェントをツールやデータにつなぐ。このリストでいちばん広く使われている統合プロトコル。
- [Agent Client Protocol (ACP)](https://agentclientprotocol.com) — エージェントをエディタやホストクライアントに埋め込む Zed のプロトコル。Obsidian Agent Client・CodeCompanion.nvim・Agentic.nvim・Agent of Empires・Agent Kanban が利用。

**隣接ツール（エージェントの実行はしないが、そのワークフローを支える）**
- [codex-profiles](https://github.com/Ducksss/codex-profiles) — Codex CLI/Desktop を隔離した `CODEX_HOME` プロファイルで起動し、`auth.json` のトークンをコピーせずにアカウント／コンテキストを切り替える依存フリーの Bash ラッパー。`MIT`

<a id="contributing"></a>
## コントリビュート

コントリビュート歓迎です。収録基準とエントリ形式は [CONTRIBUTING.md](CONTRIBUTING.md)（英語）にまとめてあるので、目を通したうえで PR を送るか、[ツールを提案](../../issues/new?template=suggest-a-tool.md)してください。記述の修正は、出典リンクを添えた PR がいちばん早く反映できます。

収録の目安は、GitHub star 数がおよそ **50 未満**のツールは、ある程度使われ始めるまでいったん見送る、という程度のゆるい基準です（とびきり新しい発想のものは早めに入れることもあります）。star はどれだけ使われているかの目安であって、品質の判定ではありません。

<a id="dataquality"></a>
## データ品質についての注記

このリストは **2026 年 6 月**にまとめて調べたものです。全ツールの実在を GitHub API で確かめ、各エントリは元の README や公式サイトと突き合わせて、**ライセンス・対応プラットフォーム・対応エージェント・プロトコル（MCP/ACP）・機能の記述を検証して直してあります**。star バッジは自動で更新され、**並び順は各セクションともまとめた時点の star 数**です。とはいえプロジェクトは動き続けるので、細部は古くなります。何か 1 つの記述に頼る前にご自身で確かめて、おかしい点があれば修正を送ってください。バッジについて 2 点だけ補足を。**Cline (Kanban)** の ★ はオーケストレーター側のリポジトリを指していて、親の Cline プロジェクトはこれよりずっと大きい。**Oz** の ★ は Oz 単体ではなく Warp クライアント全体の数です。スコープの決め方と調べた経緯は [docs/awesome-agent-clients-design.md](docs/awesome-agent-clients-design.md) にまとめています。

## ライセンス

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

法律上可能な範囲で、コントリビューターは本作品に対する著作権および関連・隣接権をすべて放棄しています。[LICENSE](LICENSE)（CC0-1.0）を参照してください。
