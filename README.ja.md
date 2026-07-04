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

---

<a id="desktop"></a>
## デスクトップ／マルチプラットフォームクライアント

デスクトップで動くネイティブ／Electron アプリ。モバイルや Web のコンパニオンを持つものも多い。

- [opcode](https://github.com/winfunc/opcode) [![★](https://img.shields.io/github/stars/winfunc/opcode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/winfunc/opcode/stargazers) 🔓 — Claude Code を GUI で扱うツールキット。セッション・カスタムエージェント・バックグラウンド実行・チェックポイント確認。`AGPL-3.0` `mac/Win/Linux` `MCP` `Claude Code`
- [Superset](https://superset.sh/) [![★](https://img.shields.io/github/stars/superset-sh/superset?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/superset-sh/superset/stargazers) 🟡 — 10以上の CLI エージェントを並列実行、各々を専用 worktree に隔離する macOS ワークスペース。差分レビュー内蔵。`Elastic-2.0` `mac` `10+ agents`
- [Orca](https://www.onorca.dev/) [![★](https://img.shields.io/github/stars/stablyai/orca?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/stablyai/orca/stargazers) 🔓 — 多数の CLI エージェントを並べて走らせ、各々に専用の worktree・ターミナル・ブラウザタブを与える ADE。`MIT` `mac/Win/Linux/iOS/Android` `MCP` `25+ agents`
- [Paseo](https://paseo.sh/) [![★](https://img.shields.io/github/stars/getpaseo/paseo?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/getpaseo/paseo/stargazers) 🟡 — 5つのエージェントを1画面で動かすセルフホスト型デーモン。デスクトップ／モバイル／Web／CLI から接続。`source-available` `Desktop/iOS/Android/Web/CLI` `MCP` `5 agents`
- [CodePilot](https://github.com/op7418/CodePilot) [![★](https://img.shields.io/github/stars/op7418/CodePilot?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/op7418/CodePilot/stargazers) 🟡 — Claude Code CLI をラップするクロスプラットフォームのデスクトップクライアント。複数プロバイダ＋メッセージアプリ遠隔操作。`BSL-1.1→Apache-2.0` `mac/Win/Linux` `MCP` `Claude Code`
- [1code](https://1code.dev/) [![★](https://img.shields.io/github/stars/21st-dev/1code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/21st-dev/1code/stargazers) 🟡 — Claude Code と Codex をローカル／クラウドサンドボックスで worktree 隔離して動かすオープンコアのデスクトップ／Web クライアント。`Apache-2.0` `mac/Win/Linux/Web/PWA` `MCP` `Claude Code/Codex`
- [emdash](https://emdash.sh/) [![★](https://img.shields.io/github/stars/generalaction/emdash?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/generalaction/emdash/stargazers) 🔓 — 多数のコーディングエージェント CLI を並列実行、各々を専用 worktree に隔離するデスクトップアプリ。横断差分レビュー付き。`Apache-2.0` `mac/Win/Linux` `10+ agents`
- [AgentsMesh](https://agentsmesh.ai/) [![★](https://img.shields.io/github/stars/AgentsMesh/AgentsMesh?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AgentsMesh/AgentsMesh/stargazers) 🟡 — 複数マシンのセルフホスト・ランナー群を1コンソールから操り、ターミナルエージェントを動かす。`BSL-1.1→GPL-2.0` `Web/Desktop/iOS/CLI` `5 agents`
- [mux](https://mux.coder.com/) [![★](https://img.shields.io/github/stars/coder/mux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coder/mux/stargazers) 🔓 — 多数のエージェントを Local／Worktree／SSH ランタイムで並列実行する Coder 製アプリ（独自エージェントループ）。`AGPL-3.0` `mac/Linux/Web/VSCode` `multi-model`
- [Agent Teams AI](https://agentteams.live/) [![★](https://img.shields.io/github/stars/777genius/agent-teams-ai?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/777genius/agent-teams-ai/stargazers) 🔓 — エージェントのチームが互いにメッセージし、コードを相互レビューするデスクトップアプリ。`AGPL-3.0` `mac/Win/Linux` `MCP` `Claude Code/Codex/OpenCode`
- [Cline (Kanban)](https://cline.bot/) [![★](https://img.shields.io/github/stars/cline/kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/cline/kanban/stargazers) 🔓 — Cline プロジェクト（60k★超）のコンパニオン Kanban。並列 CLI エージェントを隔離 worktree で動かす。`Apache-2.0` `CLI/Web` `auto-detected agents`
- [claude-code-by-agents](https://claudecode.run/) [![★](https://img.shields.io/github/stars/baryhuang/claude-code-by-agents?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/baryhuang/claude-code-by-agents/stargazers) 🔓 — 複数の Claude Code エージェントをマシン横断で @メンション振り分けする Swift 製 macOS/iOS アプリ。`MIT` `mac/iOS` `Claude Code`
- [Parallel Code](https://github.com/johannesjo/parallel-code) [![★](https://img.shields.io/github/stars/johannesjo/parallel-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/johannesjo/parallel-code/stargazers) 🔓 — エージェント CLI を並列起動、各々を専用 worktree に隔離して差分レビューと選択マージを行うデスクトップアプリ。`MIT` `mac/Linux` `Claude Code/Codex/Gemini/+2`
- [AI Maestro](https://github.com/23blocks-OS/ai-maestro) [![★](https://img.shields.io/github/stars/23blocks-OS/ai-maestro?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/23blocks-OS/ai-maestro/stargazers) 🔓 — マシンをまたいでターミナルエージェントを束ねるプラットフォーム。ダッシュボード・永続メモリ・エージェント間メッセージング。`MIT` `mac/Linux/Win(WSL2)/Web/CLI` `multi-agent`
- [Dorothy](https://github.com/Charlie85270/Dorothy) [![★](https://img.shields.io/github/stars/Charlie85270/Dorothy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Charlie85270/Dorothy/stargazers) 🔓 — Claude Code・Codex・Gemini をプロジェクト横断で並列にさばくデスクトップアプリ。kanban とメタオーケストレーター付き。`MIT` `mac/Linux` `MCP` `Claude Code/Codex/Gemini`
- [Constellagent](https://constellagent.vercel.app/) [![★](https://img.shields.io/github/stars/owengretzinger/constellagent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/owengretzinger/constellagent/stargazers) 🔓 — 複数のエージェントセッションを並列実行する macOS アプリ。各々に専用ターミナル・Monaco エディタ・worktree。`license: ?` `mac` `agent-agnostic`
- [Sculptor](https://imbue.com/sculptor/) [![★](https://img.shields.io/github/stars/imbue-ai/sculptor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/imbue-ai/sculptor/stargazers) 🔓 — エージェントを隔離コンテナで並列実行し、成果をローカルリポジトリへ同期する Imbue 製デスクトップアプリ。`MIT` `mac/Linux` `Claude Code/Codex`
- [Conductor](https://www.conductor.build/) 🔒 — エージェントを並列実行、各々を専用ブランチ・ターミナル・差分の隔離ワークスペースで動かす macOS アプリ（Melty Labs）。`closed-source` `mac` `MCP` `Claude Code/Codex/+2`
- [AgentsRoom](https://agentsroom.dev/) 🔒 — CLI エージェントをプロジェクト横断でネイティブなローカルプロセスとして並列にさばくデスクトップアプリ（iOS/Android 付き）。`closed-source` `mac/Win/Linux/iOS/Android` `MCP` `7 agents`

<a id="terminal"></a>
## ターミナル／CLI オーケストレーター

ペインや tmux、worktree を使ってエージェントを立ち上げ・連携させる、TUI ダッシュボードや CLI 中心のツール。

- [cmux](https://cmux.com/) [![★](https://img.shields.io/github/stars/manaflow-ai/cmux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/manaflow-ai/cmux/stargazers) 🔓 — ターミナルエージェントを並列実行・整理する libghostty ベースのネイティブ macOS ターミナル。分割＋通知付き。`GPL-3.0` `mac (+iOS beta)` `any terminal agent`
- [Gas Town](https://github.com/gastownhall/gastown) [![★](https://img.shields.io/github/stars/gastownhall/gastown?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/gastownhall/gastown/stargazers) 🔓 — Steve Yegge 作のマルチエージェント・オーケストレーター。git バックの状態と見張り階層で束ねる。`MIT` `CLI/TUI/Web` `8 agents`
- [Claude Squad](https://smtg-ai.github.io/claude-squad/) [![★](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/smtg-ai/claude-squad/stargazers) 🔓 — 複数のエージェントを並列管理するターミナル TUI。各々に専用 worktree と tmux セッション。`AGPL-3.0` `mac/Linux/TUI` `Claude Code/Codex/Gemini/Aider`
- [Agent Orchestrator](https://github.com/ComposioHQ/agent-orchestrator) [![★](https://img.shields.io/github/stars/ComposioHQ/agent-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/ComposioHQ/agent-orchestrator/stargazers) 🟡 — 並列エージェントセッションを各々専用 worktree で監督し、CI 失敗・レビュー・衝突を担当に差し戻す Composio 製（現 ReverbCode）。`license: ?` `CLI/Desktop` `23 agents`
- [Agent of Empires](https://github.com/njbrake/agent-of-empires) [![★](https://img.shields.io/github/stars/njbrake/agent-of-empires?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/njbrake/agent-of-empires/stargazers) 🔓 — Linux/macOS 上のエージェントセッションマネージャ。ターミナル TUI とブラウザ／PWA ダッシュボードから操作。`MIT` `CLI/TUI/Web/PWA` `ACP` `13 agents`
- [Antfarm](https://www.antfarm.cool/) [![★](https://img.shields.io/github/stars/snarktank/antfarm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/snarktank/antfarm/stargazers) 🔓 — 決定論的な YAML ワークフローで専門エージェントのチームを動かす TypeScript 製 CLI。`MIT` `CLI/Web` `OpenClaw`
- [Supacode](https://supacode.sh/) [![★](https://img.shields.io/github/stars/supabitapp/supacode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/supabitapp/supacode/stargazers) 🟡 — 50以上の CLI エージェントを並列実行、各々を専用 worktree に隔離する libghostty ベースのネイティブ macOS コマンドセンター。`FSL→Apache-2.0` `mac` `50+ agents`
- [Scion](https://googlecloudplatform.github.io/scion/) [![★](https://img.shields.io/github/stars/GoogleCloudPlatform/scion?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/GoogleCloudPlatform/scion/stargazers) 🔓 — エージェントを隔離コンテナで動かし、各々に専用 worktree と認証情報を持たせる実験的なホスト側 CLI＋ハブ（Google Cloud）。`Apache-2.0` `CLI/Web/Linux/Cloud` `Claude Code/Gemini/Codex/OpenCode`
- [TAKT](https://github.com/nrslib/takt) [![★](https://img.shields.io/github/stars/nrslib/takt?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/nrslib/takt/stargazers) 🔓 — コーディングエージェントを再現可能な YAML ワークフロー（plan→implement→review→fix）に落とす OSS CLI。隔離 worktree 付き。`MIT` `CLI` `6 agents`
- [Bernstein](https://bernstein.run/) [![★](https://img.shields.io/github/stars/chernistry/bernstein?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/chernistry/bernstein/stargazers) 🔓 — ゴールを分解し、CLI エージェントを並列 worktree で走らせ、検証してからマージする決定論的な Python 製オーケストレーター。`Apache-2.0` `CLI/Web/VSCode/Cloud` `MCP` `44 agents`
- [Agent Deck](https://github.com/asheshgoplani/agent-deck) [![★](https://img.shields.io/github/stars/asheshgoplani/agent-deck?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/asheshgoplani/agent-deck/stargazers) 🔓 — 多数のエージェントセッションを実行・整理・フォーク・自律監視するターミナル版「司令室」。`MIT` `TUI/CLI/Web` `MCP` `6 agents`
- [ntm](https://github.com/Dicklesworthstone/ntm) [![★](https://img.shields.io/github/stars/Dicklesworthstone/ntm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dicklesworthstone/ntm/stargazers) 🔓 — tmux を、ペイン横断でエージェントを立ち上げ・並べ・連携させる司令塔に変える Go 製 CLI。`MIT` `CLI/TUI/Web` `Claude Code/Codex/Antigravity`
- [AgentBox](https://agent-box.sh/) [![★](https://img.shields.io/github/stars/madarco/agentbox?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/madarco/agentbox/stargazers) 🔓 — 複数のエージェントを並列実行、各々をローカル（Docker）やクラウドのサンドボックス VM に隔離する CLI。`MIT` `mac/Linux/CLI` `Claude Code/Codex/OpenCode`
- [amux](https://github.com/andyrewlee/amux) [![★](https://img.shields.io/github/stars/andyrewlee/amux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/andyrewlee/amux/stargazers) 🔓 — 複数のエージェントを並列実行、各々を専用 worktree と tmux セッションに隔離するターミナル UI。`MIT` `mac/Linux/TUI` `6 agents`
- [OpenKanban](https://github.com/TechDufus/openkanban) [![★](https://img.shields.io/github/stars/TechDufus/openkanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/TechDufus/openkanban/stargazers) 🔓 — チケットごとに専用 worktree と組み込みエージェントターミナルが立つ、ターミナル UI の kanban ボード。`AGPL-3.0` `mac/Linux/TUI` `5 agents`
- [dux](https://getdux.app/) [![★](https://img.shields.io/github/stars/patrickdappollonio/dux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/patrickdappollonio/dux/stargazers) 🔓 — エージェント CLI を並列実行、各々を専用 worktree に置く 3 ペイン TUI。git ステージングをその場で扱える。`MIT` `mac/Linux/TUI` `Claude Code/Codex/OpenCode/+`

<a id="ide"></a>
## IDE／エディタプラグイン

エディタの中に住むエージェント／オーケストレーター。

- [CodeCompanion.nvim](https://codecompanion.olimorris.dev/) [![★](https://img.shields.io/github/stars/olimorris/codecompanion.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/olimorris/codecompanion.nvim/stargazers) 🔓 — LLM プロバイダや ACP 経由の外部エージェントにチャットバッファからつなぐ Neovim プラグイン。`Apache-2.0` `Neovim` `MCP+ACP` `9 agents`
- [CC GUI (Claude or Codex)](https://plugins.jetbrains.com/plugin/29342-cc-gui-claude-or-codex-) [![★](https://img.shields.io/github/stars/zhukunpenglinyutong/jetbrains-cc-gui?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/zhukunpenglinyutong/jetbrains-cc-gui/stargazers) 🔓 — Claude Code と Codex の CLI に 2 エンジン構成の GUI をかぶせる JetBrains プラグイン。`MIT` `JetBrains` `MCP` `Claude Code/Codex`
- [Obsidian Agent Client](https://rait-09.github.io/obsidian-agent-client/) [![★](https://img.shields.io/github/stars/RAIT-09/obsidian-agent-client?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/RAIT-09/obsidian-agent-client/stargazers) 🔓 — 外部のコーディングエージェントを ACP 経由で Obsidian の vault に取り込むプラグイン。`Apache-2.0` `Desktop (Obsidian)` `ACP+MCP` `7 agents`
- [Agentic.nvim](https://github.com/carlos-algms/agentic.nvim) [![★](https://img.shields.io/github/stars/carlos-algms/agentic.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/carlos-algms/agentic.nvim/stargazers) 🔓 — ACP 対応エージェントなら何でもエディタ内チャットからつなげる Neovim プラグイン。`MIT` `Neovim` `ACP` `8+ agents`
- [Claude Code Plus](https://plugins.jetbrains.com/plugin/28343-claude-code-plus) [![★](https://img.shields.io/github/stars/touwaeriol/claude-code-plus?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/touwaeriol/claude-code-plus/stargazers) 🔓 — IntelliJ 系 IDE 内で CLI コーディングエージェントを GUI から扱える JetBrains プラグイン。`MIT` `JetBrains` `MCP` `Claude Code/Codex/Gemini`

<a id="web"></a>
## Web／セルフホスト型ダッシュボード

ローカルで動かす、あるいはセルフホストするブラウザ中心のオーケストレーター。

- [Multica](https://multica.ai/) [![★](https://img.shields.io/github/stars/multica-ai/multica?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/multica-ai/multica/stargazers) 🟡 — コーディングエージェントを、issue を割り振れるボード管理のチームメイトに変える OSS の managed-agents プラットフォーム。`Apache-2.0 (mod.)` `Web/self-hosted/Cloud` `12 agents`
- [Vibe Kanban](https://www.vibekanban.com/) [![★](https://img.shields.io/github/stars/BloopAI/vibe-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/BloopAI/vibe-kanban/stargazers) 🔓 — 多数のエージェント CLI でタスクを計画・実行・レビューする kanban。各タスクは隔離 worktree で動く。`Apache-2.0` `mac/Web/CLI` `10 agents`
- [T3 Code](https://t3.codes/) [![★](https://img.shields.io/github/stars/pingdotgg/t3code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/pingdotgg/t3code/stargazers) 🔓 — Codex・Claude Code・Cursor・OpenCode を1画面からさばく OSS の Web／デスクトップ制御プレーン（Theo/Ping）。`MIT` `mac/Win/Linux/Web/CLI` `4 agents`
- [Catnip](https://github.com/wandb/catnip) [![★](https://img.shields.io/github/stars/wandb/catnip?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/wandb/catnip/stargazers) 🔓 — Claude Code をコンテナ化 worktree サンドボックスで動かすセルフホスト可能な Web サービス（W&B）。iOS アプリ付き。`Apache-2.0` `Web/CLI/iOS/Cloud` `Claude Code`
- [Agent Viewer](https://github.com/hallucinogen/agent-viewer) [![★](https://img.shields.io/github/stars/hallucinogen/agent-viewer?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hallucinogen/agent-viewer/stargazers) 🔓 — tmux で動く複数の Claude Code エージェントを起動・監視・メッセージする Web kanban ボード。`license: ?` `mac/Linux/Web/mobile` `Claude Code`
- [Agent Kanban](https://agent-kanban.dev/) [![★](https://img.shields.io/github/stars/saltbo/agent-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/saltbo/agent-kanban/stargazers) 🟡 — エージェントを暗号鍵で識別するメンバーとして扱い、タスクを取らせ PR まで出させる kanban ボード。`FSL→Apache-2.0` `CLI/Web` `ACP` `5 agents`
- [OpenGoat](https://github.com/marian2js/opengoat) [![★](https://img.shields.io/github/stars/marian2js/opengoat?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/marian2js/opengoat/stargazers) 🔓 — 多数のプロバイダをまたいで作業を連携する、エージェントの階層型組織を組み立てるプラットフォーム。`MIT` `Web/CLI` `5 agents`
- [Kanban Code](https://github.com/langwatch/kanban-code) [![★](https://img.shields.io/github/stars/langwatch/kanban-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/langwatch/kanban-code/stargazers) 🔓 — kanban ボードで複数の Claude Code セッションを束ねるネイティブデスクトップアプリ＋CLI（LangWatch）。`AGPL-3.0` `mac/Win/CLI` `Claude Code`

<a id="cloud"></a>
## クラウド／ホスト型コントロールプレーン

エージェントの群れをクラウドで動かす、ホスト型（セルフホストも可）のコントロールプレーン。

- [Oz](https://www.warp.dev/oz) [![★](https://img.shields.io/github/stars/warpdotdev/warp?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/warpdotdev/warp/stargazers) 🟡 — 複数ハーネスをまたいでクラウドのコーディングエージェント群を走らせ・見張る Warp 製プラットフォーム。`MIT/AGPLv3` `Cloud/Web/Desktop/CLI` `MCP` `4 agents` *(★は Warp クライアント全体)*
- [Centaur](https://centaur.run/) [![★](https://img.shields.io/github/stars/paradigmxyz/centaur?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/paradigmxyz/centaur/stargazers) 🔓 — CLI エージェントハーネスを隔離 K8s サンドボックスで動かし、Slack/API から操作する Paradigm 製のセルフホスト制御プレーン。`Apache-2.0/MIT` `Cloud/CLI/Slack` `Claude Code/Codex/Amp`

<a id="viewers"></a>
## セッションビューア／コンパニオンツール

エージェントのセッションを眺めて分析するためのツール（起動や操作はしない）。上のツールと組み合わせて使う。

- [AgentsView](https://www.agentsview.io/) [![★](https://img.shields.io/github/stars/kenn-io/agentsview?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/kenn-io/agentsview/stargazers) 🔓 — コーディングエージェントのセッションログを索引化し、検索・コスト分析・傾向を見せるローカルファーストのツール（観測専用）。`MIT` `mac/Win/Linux/CLI/Web` `reads 20+ agents`
- [Claude Code Agent Monitor](https://hoangsonww.github.io/Claude-Code-Agent-Monitor/) [![★](https://img.shields.io/github/stars/hoangsonww/Claude-Code-Agent-Monitor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hoangsonww/Claude-Code-Agent-Monitor/stargazers) 🔓 — Claude Code のセッション・ツール使用・コスト・サブエージェントを可視化するセルフホストのリアルタイムダッシュボード（観測）。`MIT` `Web/mac/Win/VSCode/CLI` `MCP` `reads Claude Code`

<a id="archived"></a>
## アーカイブ／注目プロジェクト

もう活発には保守されていないものの、振り返る価値のあるプロジェクト。

- [Crystal](https://github.com/stravu/crystal) [![★](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/stravu/crystal/stargazers) — 複数の Claude Code/Codex セッションを並列実行、各々を専用 worktree で動かした Electron アプリ。`MIT` `mac/Win/Linux` **提供終了 → 現在は [Nimbalyst](https://nimbalyst.com/)**
- [Terragon](https://github.com/terragon-labs/terragon-oss) [![★](https://img.shields.io/github/stars/terragon-labs/terragon-oss?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/terragon-labs/terragon-oss/stargazers) — ホスト型のバックグラウンドエージェント群オーケストレーター。`Apache-2.0` **サービス終了 2026-01-16・保守なしのスナップショット**
- [Claude Code Board](https://cc-board.cablate.com/) [![★](https://img.shields.io/github/stars/cablate/Claude-Code-Board?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/cablate/Claude-Code-Board/stargazers) — 複数の Claude Code CLI セッションを束ねる Web の kanban 風マネージャ。`MIT` **保守終了（2026-01）**

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
- [Symphony](https://github.com/openai/symphony) — トラッカーの issue ごとに Codex セッションを走らせる OpenAI のオーケストレーション仕様＋Elixir リファレンス実装。
- [FleetQ](https://github.com/escapeboy/agent-fleet-o) — ネイティブ MCP サーバーを備えた汎用マルチエージェント DAG／ワークフロープラットフォーム。
- [AgentTier](https://github.com/agenttier/agenttier) — エージェントを動かすための Kubernetes ネイティブなサンドボックス as a service（インフラ層）。

**プロトコル**
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) — エージェントをツールやデータにつなぐ。このリストでいちばん広く使われている統合プロトコル。
- [Agent Client Protocol (ACP)](https://agentclientprotocol.com) — エージェントをエディタやホストクライアントに埋め込む Zed のプロトコル。Obsidian Agent Client・CodeCompanion.nvim・Agentic.nvim・Agent of Empires・Agent Kanban が利用。

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
