# Awesome Agent Clients [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[English](README.md) | **日本語**

> AI コーディングエージェントのためのクライアント／オーケストレーターを厳選したリスト — Claude Code、OpenAI Codex、Gemini CLI、OpenCode、Aider、Cursor CLI といったエージェントを**実行・管理・オーケストレーション**する、デスクトップ／ターミナル／モバイル／Web／IDE 向けアプリ群です。

この1〜2年で、AI コーディングエージェントの使い方は「1 つと会話する」ことから「多数を並列に動かす」ことへと変わりました。以下のツールは、それらを実行する場所です。エージェントを起動し、それぞれを独自の git worktree やサンドボックスに隔離し、差分をレビューし、さらにはスマホから全体を操作できるようにします。このリストは**エージェント本体ではなく、それらを動かすツール**を対象とします — エージェント本体は[関連](#related)にまとめています。

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

各エントリには、採用度のおおまかな目安として GitHub の star 数バッジ（[shields.io](https://shields.io) により自動更新）を表示しています。**各セクション内では star 数の多い順に並べています。** クローズドソース製品には star バッジはありません。

- 🔓 オープンソース · 🟡 ソースアベイラブル／オープンコア · 🔒 クローズドソース
- **MCP** = [Model Context Protocol](https://modelcontextprotocol.io) · **ACP** = [Agent Client Protocol](https://agentclientprotocol.com)
- 「Agents」はそのツールが駆動できる*外部の*コーディングエージェントを示します。
- 収録の目安: GitHub star 数が約50未満のツールは原則見送ります（[コントリビュート](#contributing)参照）。star 数は目安であり、優劣の判定ではありません。

---

<a id="desktop"></a>
## デスクトップ／マルチプラットフォームクライアント

デスクトップで動作するネイティブ／Electron アプリ。多くはモバイル／Web のコンパニオンを備えます。

- [opcode](https://github.com/winfunc/opcode) — Claude Code 向け GUI ツールキット。セッション管理、カスタム CC エージェントの作成、バックグラウンド実行、MCP 設定、チェックポイントのレビューを行う。🔓 [![★](https://img.shields.io/github/stars/winfunc/opcode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/winfunc/opcode/stargazers)
  - `winfunc/opcode` · AGPL-3.0 · macOS/Windows/Linux · Claude Code · MCP · *特徴:* カスタム CC エージェントビルダー、使用量分析、チェックポイントのタイムライン／フォーク。(Tauri アプリ。最終リリースは 2025-10 — 保守状況は要確認。)
- [Superset](https://superset.sh/) — 多数の CLI コーディングエージェントを並列実行し、各々を独自の git worktree に隔離する macOS デスクトップワークスペース。差分レビューとエディタ連携を内蔵。🟡 [![★](https://img.shields.io/github/stars/superset-sh/superset?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/superset-sh/superset/stargazers)
  - `superset-sh/superset` · Elastic License 2.0 · macOS · *特徴:* 10以上の CLI エージェントの並列オーケストレーション、タスクごとの git-worktree 隔離、内蔵の差分ビューア/エディタ、ワークスペースのセットアップ/破棄プリセット、ワンクリックでエディタ連携。
- [Paseo](https://paseo.sh/) — 5つのコーディングエージェント（Claude Code、Codex、Copilot、OpenCode、Pi）を1つのインターフェースで動かすセルフホスト型デーモン。デスクトップ／モバイル／Web／CLI のクライアントが接続する。🟡 [![★](https://img.shields.io/github/stars/getpaseo/paseo?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/getpaseo/paseo/stargazers)
  - `getpaseo/paseo` · ソースアベイラブル（独自ライセンス）· Desktop/iOS/Android/Web/CLI · MCP · *特徴:* 自分のマシンでエージェントを並列実行、クロスデバイスのクライアント、音声操作、リモート接続用リレー、オーケストレーションスキル（`/paseo-handoff`、`/paseo-loop`、`/paseo-committee`）。
- [Orca](https://www.onorca.dev/) — 多数の CLI コーディングエージェントを並べて実行し、各々が独自の git worktree・ターミナル・ブラウザタブを持つ Agent Development Environment。🔓 [![★](https://img.shields.io/github/stars/stablyai/orca?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/stablyai/orca/stargazers)
  - `stablyai/orca` · MIT · macOS/Windows/Linux/iOS/Android/CLI · MCP · *特徴:* タスクごとの worktree ＋「Design Mode」の Chromium キャプチャ、エージェントを操作するモバイルコンパニオン、SSH リモート worktree。25 以上のエージェント（Claude Code、Codex、OpenCode、Cursor CLI…）を駆動。
- [CodePilot](https://github.com/op7418/CodePilot) — Claude Code CLI をラップしてファイル／ターミナル／git 操作を行うクロスプラットフォームのデスクトップクライアント。マルチプロバイダのモデルとメッセージアプリからの遠隔操作に対応。🟡 [![★](https://img.shields.io/github/stars/op7418/CodePilot?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/op7418/CodePilot/stargazers)
  - `op7418/CodePilot` · BSL-1.1（→ Apache-2.0）· macOS/Windows/Linux · Claude Code · MCP · *特徴:* Telegram/Feishu/Discord/QQ/WeChat からの遠隔操作、17 以上のモデルプロバイダをスレッド途中で切替、MCP ランタイムダッシュボード、cron スケジューラ。
- [1code](https://1code.dev/) — Claude Code と Codex をローカルまたはクラウドサンドボックスで worktree 隔離して動かすオープンコアのデスクトップ／Web クライアント。🟡 [![★](https://img.shields.io/github/stars/21st-dev/1code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/21st-dev/1code/stargazers)
  - `21st-dev/1code` · Apache-2.0（オープンコア）· macOS/Windows/Linux/Web/PWA · MCP · Claude Code/Codex · *特徴:* セッションごとの worktree ＋ kanban、バックグラウンド／クラウドサンドボックス実行、任意のメッセージからのロールバック、PWA でのモバイル操作。
- [emdash](https://emdash.sh/) — 複数のコーディングエージェント CLI（Claude Code、Codex、Cursor、Gemini、Amp ほか）を並列実行し、各々を独自の git worktree に隔離するデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/generalaction/emdash?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/generalaction/emdash/stargazers)
  - `generalaction/emdash` · Apache-2.0 · macOS/Windows/Linux · *特徴:* 差分レビュー、PR 作成／マージ＋CI 確認、Linear/GitHub/Jira/GitLab/Asana からの issue 取り込み、ローカル／リモート（SSH/SFTP）実行。
- [AgentsMesh](https://agentsmesh.ai/) — 複数マシンにまたがってターミナルエージェントを動かすセルフホストのランナー艦隊を、1 つのコンソールから操作（web/desktop/iOS/CLI）。🟡 [![★](https://img.shields.io/github/stars/AgentsMesh/AgentsMesh?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AgentsMesh/AgentsMesh/stargazers)
  - `AgentsMesh/AgentsMesh` · BSL-1.1（→ GPL-2.0）· Web/Desktop/iOS/CLI · Claude Code/Codex/Gemini CLI/Aider/OpenCode · *特徴:* マシン艦隊にまたがるポッドごとの worktree サンドボックス、「Autopilot」制御エージェント、@メンション付きのポッド間 Mesh & Channels。
- [mux](https://mux.coder.com/) — 多数のエージェントを隔離ワークスペースで並列実行する Coder 製のデスクトップ／ブラウザアプリ。Local／Worktree／SSH ランタイムを選択可能。🔓 [![★](https://img.shields.io/github/stars/coder/mux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coder/mux/stargazers)
  - `coder/mux` · AGPL-3.0 · macOS/Linux/Web/VSCode · *特徴:* 独自のモデル非依存エージェントループ（マルチモデル）、Local／Worktree／SSH の隔離ワークスペースでの並列実行、git の分岐／コンフリクト可視化、サーバーモードでのモバイル対応。
- [Agent Teams AI](https://agentteams.live/) — 互いにメッセージし合い、コードを相互レビューするコーディングエージェントのチームを編成するデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/777genius/agent-teams-ai?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/777genius/agent-teams-ai/stargazers)
  - `777genius/agent-teams-ai` · AGPL-3.0 · macOS/Windows/Linux · MCP · Claude Code/Codex/OpenCode · *特徴:* エージェント間／チーム間メッセージング、hunk 単位の accept/reject 差分レビュー、5 列の kanban、エージェントごとの CPU/RAM ライブダッシュボード。
- [Cline (Kanban)](https://cline.bot/) — Cline プロジェクト（60k★ 超）のコンパニオン Kanban アプリで、並列 CLI エージェントを隔離 git worktree でオーケストレーションする。🔓 [![★](https://img.shields.io/github/stars/cline/kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/cline/kanban/stargazers)
  - `cline/kanban` · Apache-2.0 · CLI/Web · インストール済み CLI エージェントを自動検出 · *特徴:* 並列エージェント用の kanban ボード、タスクごとの一時 git worktree 隔離、自動コミット付きタスク依存チェーン。(コアの [Cline](https://github.com/cline/cline) はエージェント本体。ここではオーケストレーター部分を収録。)
- [claude-code-by-agents](https://claudecode.run/) — 複数の Claude Code エージェントをローカル／リモートのマシン間で @メンションルーティングにより連携する、Swift ネイティブの macOS/iOS アプリ。🔓 [![★](https://img.shields.io/github/stars/baryhuang/claude-code-by-agents?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/baryhuang/claude-code-by-agents/stargazers)
  - `baryhuang/claude-code-by-agents` · MIT · macOS/iOS · Claude Code · *特徴:* 名前付きエージェントへの @メンションルーティング、マシン間連携、iMessage 風の 2 ペインネイティブアプリ。
- [Parallel Code](https://github.com/johannesjo/parallel-code) — 複数のエージェント CLI を並列起動し、各々を独自 worktree に隔離して差分レビューと選択的マージを行うデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/johannesjo/parallel-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/johannesjo/parallel-code/stargazers)
  - `johannesjo/parallel-code` · MIT · macOS/Linux · Claude Code/Codex/Gemini CLI/Antigravity/Copilot · *特徴:* インライン差分コメント＋コミット単位ナビゲーション、PR の CI ウォッチャー、Docker サンドボックス、Wi-Fi/Tailscale 越しの QR モバイル監視。
- [AI Maestro](https://github.com/23blocks-OS/ai-maestro) — マシンをまたいでターミナルエージェントを管理するオーケストレーションプラットフォーム。ダッシュボード、永続メモリ、エージェント間メッセージングを備える。🔓 [![★](https://img.shields.io/github/stars/23blocks-OS/ai-maestro?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/23blocks-OS/ai-maestro/stargazers)
  - `23blocks-OS/ai-maestro` · MIT · macOS/Linux/Windows(WSL2)/Web/CLI · *特徴:* 自動検出付きのマルチマシンピアメッシュ、署名付き Agent Messaging Protocol、コードグラフ可視化、依存関係付き kanban、Slack/Discord/WhatsApp ゲートウェイ。
- [Dorothy](https://github.com/Charlie85270/Dorothy) — Claude Code・Codex・Gemini をプロジェクト横断で並列オーケストレーションするデスクトップアプリ。kanban ボードとメタオーケストレーターエージェントを備える。🔓 [![★](https://img.shields.io/github/stars/Charlie85270/Dorothy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Charlie85270/Dorothy/stargazers)
  - `Charlie85270/Dorothy` · MIT · macOS/Linux · Claude Code/Codex/Gemini · MCP · *特徴:* 「Super Agent」メタオーケストレーター、5 つの MCP サーバー同梱、Telegram/Slack 遠隔操作、cron による自律実行。
- [Constellagent](https://constellagent.vercel.app/) — 複数の AI エージェントセッションを並列実行する macOS アプリ。各々が独自のターミナル・Monaco エディタ・隔離 worktree を持つ。🔓 [![★](https://img.shields.io/github/stars/owengretzinger/constellagent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/owengretzinger/constellagent/stargazers)
  - `owengretzinger/constellagent` · ライセンス未確認 · macOS · エージェント非依存 · *特徴:* 1 ウィンドウ内でエージェントごとの worktree、フルターミナルエミュレータ、Monaco エディタ（差分対応）、sleep/wake 復帰付き cron 自動化。
- [Sculptor](https://imbue.com/sculptor/) — エージェントを隔離コンテナ内で並列実行し、その作業をローカルリポジトリに同期する Imbue 製デスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/imbue-ai/sculptor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/imbue-ai/sculptor/stargazers)
  - `imbue-ai/sculptor` · MIT · macOS/Linux · Claude Code/Codex · *特徴:* コンテナ隔離（worktree の代替）、IDE に同期する「Pairing Mode」、修正エージェントを起動するコード課題サジェスト。
- [Conductor](https://www.conductor.build/) — 複数のエージェントを並列実行し、各々が独自のブランチ・ターミナル・差分を持つ隔離ワークスペースで動く macOS アプリ（Melty Labs）。🔒 *公開リポジトリなし*
  - `closed-source` · macOS · MCP · Claude Code/Codex/Cursor/OpenCode · *特徴:* 組み込みの差分レビュー＋マージ、GitHub issue から直接ワークスペースを作成。
- [AgentsRoom](https://agentsroom.dev/) — CLI エージェントをプロジェクト横断でネイティブなローカルプロセスとして並列オーケストレーションするデスクトップアプリ（iOS/Android コンパニオン付き）。専門エージェントロールとチームハンドオフを備える。🔒 *公開リポジトリなし*
  - `closed-source`（org: `AgentsRoomDev`）· macOS/Windows/Linux/iOS/Android · MCP · Claude Code/Codex/OpenCode/Gemini CLI/Aider/Grok/Mistral · *特徴:* 14 の専門エージェントロール、「Agent Teams」ハンドオフキャンバス、kanban バックログ（公開リモート投稿対応含む）、E2E 暗号化モバイル同期。

<a id="terminal"></a>
## ターミナル／CLI オーケストレーター

ペイン・tmux・worktree でエージェントを起動・連携する TUI ダッシュボードと CLI 中心のツール。

- [cmux](https://cmux.com/) — ターミナルエージェントを並列実行・整理するネイティブ macOS ターミナル（libghostty）。分割表示とエージェント認識通知を備える。🔓 [![★](https://img.shields.io/github/stars/manaflow-ai/cmux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/manaflow-ai/cmux/stargazers)
  - `manaflow-ai/cmux` · GPL-3.0-or-later · macOS（＋ iOS コンパニオン、beta）· *特徴:* OSC 9/99/777 の通知リング／バッジ、スクリプト可能な組み込みブラウザ、`cmux claude-teams` のチームメイトモード、SSH リモート。任意のターミナルエージェント（Claude Code、Codex、OpenCode、Gemini CLI、Aider、Goose…）を実行。
- [Gas Town](https://github.com/gastownhall/gastown) — 並列エージェントを git バックの作業状態とウォッチドッグ階層で連携する、Steve Yegge 作のマルチエージェントオーケストレーションシステム。🔓 [![★](https://img.shields.io/github/stars/gastownhall/gastown?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/gastownhall/gastown/stargazers)
  - `gastownhall/gastown` · MIT · CLI/TUI/Web · Claude Code/Copilot/Codex/Gemini/Cursor/Amp/OpenCode/Pi · *特徴:* ロール階層（Mayor → workers）、共有メモリとしての git バック issue トラッカー「beads」、bors 風の検証付きマージキュー（Go）。
- [Claude Squad](https://smtg-ai.github.io/claude-squad/) — 複数のエージェントインスタンスを並列管理するターミナル TUI。各々が独自の git worktree と tmux セッションを持つ。🔓 [![★](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/smtg-ai/claude-squad/stargazers)
  - `smtg-ai/claude-squad` · AGPL-3.0 · macOS/Linux/TUI · Claude Code/Codex/Gemini CLI/Aider（＋カスタムプログラムで任意のローカルエージェント）· *特徴:* セッションごとの worktree＋tmux 隔離、差分タブレビュー、実験的な yolo／自動承認バックグラウンドモード。
- [Antfarm](https://www.antfarm.cool/) — 決定論的な YAML 定義ワークフローで専門エージェントのチームをオーケストレーションする TypeScript CLI。🔓 [![★](https://img.shields.io/github/stars/snarktank/antfarm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/snarktank/antfarm/stargazers)
  - `snarktank/antfarm` · MIT · CLI/Web · *特徴:* feature-dev／bug-fix／security-audit のワークフロー同梱、エージェント間検証（自己承認不可）、ステップごとに新鮮なコンテキスト、Web ダッシュボード。(OpenClaw ランタイム上で動作。)
- [Supacode](https://supacode.sh/) — 50 以上の CLI エージェントを並列実行し各々を独自 git worktree に隔離するネイティブ macOS コマンドセンター（libghostty）。🟡 [![★](https://img.shields.io/github/stars/supabitapp/supacode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/supabitapp/supacode/stargazers)
  - `supabitapp/supacode` · FSL-1.1-ALv2（→ Apache-2.0）· macOS · *特徴:* ネイティブ（Electron 不使用）、ターミナルから GitHub ネイティブの PR/CI/コンフリクト解決。
- [Scion](https://googlecloudplatform.github.io/scion/) — エージェントを隔離コンテナで各々独自の worktree と認証情報を持たせてオーケストレーションする、実験的なホスト側 CLI＋ハブ（Google Cloud）。🔓 [![★](https://img.shields.io/github/stars/GoogleCloudPlatform/scion?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/GoogleCloudPlatform/scion/stargazers)
  - `GoogleCloudPlatform/scion` · Apache-2.0 · CLI/Web/Linux/Cloud · Claude Code/Gemini CLI/Codex/OpenCode · *特徴:* エージェントごとのコンテナ＋worktree＋認証情報の隔離、フロー追跡付きエージェント間メッセージングパイプライン、Docker/Podman/VM/Kubernetes へのデプロイ（実験的・Google 公式製品ではない）。
- [TAKT](https://github.com/nrslib/takt) — コーディングエージェントを再現可能な YAML 定義ワークフロー（plan → implement → review → fix）に変えるオープンソース CLI。隔離 worktree と人間のチェックポイント付き。🔓 [![★](https://img.shields.io/github/stars/nrslib/takt?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/nrslib/takt/stargazers)
  - `nrslib/takt` · MIT · CLI · Claude Code/Codex/OpenCode/Cursor/Copilot CLI/Kiro · *特徴:* ステップごとのロール／ペルソナ／ポリシー／出力契約、サイレントにスキップできないレビューループ、タスクごとの追跡可能なログ／レポート（TypeScript）。
- [Agent Deck](https://github.com/asheshgoplani/agent-deck) — 多数のエージェントセッションをプロジェクト横断で実行・整理・フォーク・自律監視するターミナル「ミッションコントロール」。🔓 [![★](https://img.shields.io/github/stars/asheshgoplani/agent-deck?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/asheshgoplani/agent-deck/stargazers)
  - `asheshgoplani/agent-deck` · MIT · TUI/CLI/Web/macOS/Linux/Windows · MCP · Claude Code/Gemini CLI/OpenCode/Codex/Copilot/Crush · *特徴:* 自律監視／エスカレーション用の「Conductors」、worktree＋Docker 隔離、Telegram/Slack 操作、リモート SSH インスタンス。
- [ntm](https://github.com/Dicklesworthstone/ntm) — tmux を、ペインをまたいでエージェントを起動・タイル配置・連携する制御プレーンに変える Go 製 CLI。🔓 [![★](https://img.shields.io/github/stars/Dicklesworthstone/ntm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dicklesworthstone/ntm/stargazers)
  - `Dicklesworthstone/ntm` · MIT（＋追加条項）· CLI/TUI/Web · *特徴:* worktree＋ファイル予約ロック、「Agent Mail」連携、高リスク操作の 2 名承認、遠隔操作用の REST/SSE/WebSocket API。Claude Code/Codex/Antigravity を駆動。
- [amux](https://github.com/andyrewlee/amux) — 複数エージェントを並列実行し各々を独自 worktree と tmux セッションに隔離するターミナル UI。🔓 [![★](https://img.shields.io/github/stars/andyrewlee/amux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/andyrewlee/amux/stargazers)
  - `andyrewlee/amux` · MIT · macOS/Linux/TUI · Claude Code/Codex/Gemini CLI/Amp/OpenCode/Droid · *特徴:* エージェントごとの tmux 隔離、差分表示統合、信頼ゲート付き設定スクリプト、pprof/PTY トレース（Go）。
- [AgentBox](https://agent-box.sh/) — 複数エージェントを並列実行し各々をローカル（Docker）またはクラウドのサンドボックス VM に隔離する CLI。🔓 [![★](https://img.shields.io/github/stars/madarco/agentbox?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/madarco/agentbox/stargazers)
  - `madarco/agentbox` · MIT · macOS/Linux/CLI · Claude Code/Codex/OpenCode · *特徴:* プロジェクトをサンドボックス VM に「テレポート」（Docker/OrbStack または Hetzner/Vercel/Daytona/E2B）、1 秒未満のチェックポイント起動、VNC＋トンネル。
- [OpenKanban](https://github.com/TechDufus/openkanban) — 各チケットが独自 git worktree と組み込みエージェントターミナルで動く、ターミナル UI の kanban ボード。🔓 [![★](https://img.shields.io/github/stars/TechDufus/openkanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/TechDufus/openkanban/stargazers)
  - `TechDufus/openkanban` · AGPL-3.0 · macOS/Linux/TUI · OpenCode/Claude Code/Gemini CLI/Codex/Aider · *特徴:* ターミナル内 kanban、チケット＝worktree＋エージェントターミナル、複数プロジェクト統合ボード（Go）。
- [dux](https://getdux.app/) — 複数のエージェント CLI を並列実行し各々を独自 worktree に置く、ライブ git ステージングワークフロー付き 3 ペイン TUI。🔓 [![★](https://img.shields.io/github/stars/patrickdappollonio/dux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/patrickdappollonio/dux/stargazers)
  - `patrickdappollonio/dux` · MIT · macOS/Linux/TUI · Claude Code/Codex/OpenCode/ほか · *特徴:* 実 CLI をラップするので MCP/フック/スキルが機能継続、シンタックスハイライト差分＋AI コミットメッセージ、`gh` での PR ステータス追跡、セッションフォーク（Rust）。
- [Agent Orchestrator](https://github.com/ComposioHQ/agent-orchestrator) — 多数の並列コーディングエージェントセッションを各々独自 git worktree で監督し、CI 失敗・レビューコメント・マージコンフリクトを担当エージェントに差し戻す Composio 製オーケストレーター（現 ReverbCode）。🟡 [![★](https://img.shields.io/github/stars/ComposioHQ/agent-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/ComposioHQ/agent-orchestrator/stargazers)
  - `ComposioHQ/agent-orchestrator` · ライセンス未指定（LICENSEファイルなし）· CLI/Desktop · 23 のエージェントアダプタ（Claude Code/Codex/Cursor/OpenCode/Aider/Kimi ほか）· *特徴:* エージェント非依存のアダプタ群、zellij ランタイムでの git-worktree 隔離、GitHub PR/CI を監視して担当エージェントに通知（マージは人間）。
- [Agent of Empires](https://github.com/njbrake/agent-of-empires) — Linux/macOS 上のエージェントのセッションマネージャ。ターミナル TUI またはブラウザ／PWA ダッシュボードから操作する。🔓 [![★](https://img.shields.io/github/stars/njbrake/agent-of-empires?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/njbrake/agent-of-empires/stargazers)
  - `njbrake/agent-of-empires` · MIT · CLI/TUI/Web/PWA · ACP · 13 エージェント（Claude Code/OpenCode/Codex/Gemini CLI/Cursor CLI/Copilot ほか）· *特徴:* tmux＋worktree＋Docker サンドボックス、ダッシュボードに ACP 由来の構造化エージェント状態を描画、QR＋パスフレーズで HTTPS 越しのスマホアクセス（Rust・Mozilla.ai 支援）。
- [Bernstein](https://bernstein.run/) — ゴールを分解し、複数 CLI エージェントを並列 worktree で実行、監査チェーンで検証・マージする決定論的 Python オーケストレーター。🔓 [![★](https://img.shields.io/github/stars/chernistry/bernstein?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/chernistry/bernstein/stargazers)
  - `chernistry/bernstein` · Apache-2.0 · CLI/Web/VSCode/Cloud · MCP · 44 のエージェントアダプタ（Claude Code/Codex/Gemini CLI/Copilot/Aider/Goose…）· *特徴:* ゼロ LLM の決定論的スケジューラ、検証ゲート（テスト/lint/型）、HMAC-SHA256 監査チェーン＋Ed25519 署名エージェントカード、Cloudflare Workers 実行オプション。

<a id="ide"></a>
## IDE／エディタプラグイン

エディタ内に同居するエージェント／オーケストレーター。

- [CodeCompanion.nvim](https://codecompanion.olimorris.dev/) — LLM プロバイダおよび ACP 経由の外部エージェントにチャットバッファから接続する Neovim プラグイン。🔓 [![★](https://img.shields.io/github/stars/olimorris/codecompanion.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/olimorris/codecompanion.nvim/stargazers)
  - `olimorris/codecompanion.nvim` · Apache-2.0 · Neovim · MCP + ACP · Claude Code/Codex/Copilot CLI/Gemini CLI/Goose/Cursor CLI/OpenCode/ほか · *特徴:* インラインバッファ変換、エディタコンテキスト変数、複数同時チャット、幅広い ACP エージェント対応。
- [CC GUI (Claude or Codex)](https://plugins.jetbrains.com/plugin/29342-cc-gui-claude-or-codex-) — Claude Code と OpenAI Codex の CLI 向けにデュアルエンジン GUI を提供する JetBrains プラグイン。🔓 [![★](https://img.shields.io/github/stars/zhukunpenglinyutong/jetbrains-cc-gui?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/zhukunpenglinyutong/jetbrains-cc-gui/stargazers)
  - `zhukunpenglinyutong/jetbrains-cc-gui` · MIT · JetBrains · Claude Code/Codex · MCP · *特徴:* `@file` コンテキスト、画像入力、会話の巻き戻し、差分比較＋コードジャンプ、スキルのスラッシュコマンド。
- [Obsidian Agent Client](https://rait-09.github.io/obsidian-agent-client/) — Agent Client Protocol 経由で外部コーディングエージェントを Obsidian の vault 内に埋め込む Obsidian プラグイン。🔓 [![★](https://img.shields.io/github/stars/RAIT-09/obsidian-agent-client?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/RAIT-09/obsidian-agent-client/stargazers)
  - `RAIT-09/obsidian-agent-client` · Apache-2.0 · Desktop（Obsidian）· ACP + MCP · Claude Code/Codex/Gemini CLI/OpenCode/Qwen/Kiro/Mistral · *特徴:* コンテキストとしての `@note` メンション、複数同時エージェントセッション、Markdown へのチャットエクスポート、ACP ネイティブ。
- [Agentic.nvim](https://github.com/carlos-algms/agentic.nvim) — 任意の ACP 対応コーディングエージェントへのエディタ内チャットインターフェースを提供する Neovim プラグイン。🔓 [![★](https://img.shields.io/github/stars/carlos-algms/agentic.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/carlos-algms/agentic.nvim/stargazers)
  - `carlos-algms/agentic.nvim` · MIT · Neovim · ACP · Claude Code/Gemini/Codex/OpenCode/Cursor/Copilot/Cline/Goose/ほか · *特徴:* 履歴を失わないプロバイダ切替、Neovim とターミナル間のセッション復元、対話的なツール呼び出し承認。
- [Claude Code Plus](https://plugins.jetbrains.com/plugin/28343-claude-code-plus) — IntelliJ 系 IDE 内で CLI コーディングエージェントの GUI を提供する JetBrains プラグイン。🔓 [![★](https://img.shields.io/github/stars/touwaeriol/claude-code-plus?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/touwaeriol/claude-code-plus/stargazers)
  - `touwaeriol/claude-code-plus` · MIT · JetBrains · Claude Code（リポジトリ記載では Codex/Gemini CLI も）· MCP · *特徴:* Claude CLI 同梱（別途インストール不要）、`@` メンションのファイル検索、マルチセッション、ツール呼び出しの可視化、クリックで開ける差分。

<a id="web"></a>
## Web／セルフホスト型ダッシュボード

ローカル実行・セルフホストするブラウザ中心のオーケストレーター。

- [Multica](https://multica.ai/) — コーディングエージェントを、issue を割り当てられるボード管理のチームメイトに変えるオープンソースの managed-agents プラットフォーム。🟡 [![★](https://img.shields.io/github/stars/multica-ai/multica?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/multica-ai/multica/stargazers)
  - `multica-ai/multica` · Apache-2.0（改変版）· Web/self-hosted/Cloud · Claude Code/Codex/Copilot CLI/OpenClaw/OpenCode/Hermes/Gemini/Cursor/Pi/Kimi/Kiro/Qoder · *特徴:* 同僚のように issue を割り当て、リーダーエージェントが委譲する「Squads」、再利用可能なスキルの蓄積（Go）。
- [Vibe Kanban](https://www.vibekanban.com/) — 多数のエージェント CLI でタスクを計画・実行・レビューする kanban インターフェース。各タスクは隔離 worktree ワークスペースで動く。🔓 [![★](https://img.shields.io/github/stars/BloopAI/vibe-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/BloopAI/vibe-kanban/stargazers)
  - `BloopAI/vibe-kanban` · Apache-2.0 · macOS/Web/CLI · Claude Code/Codex/Gemini CLI/Copilot/Amp/Cursor/OpenCode/Droid/CCR/Qwen · *特徴:* kanban 計画、自動クリーンアップ付きワークスペースごと worktree、インラインコメント差分レビュー、デバイスエミュレーション付き組み込みブラウザプレビュー（Rust＋TS）。(Bloop の移行後はコミュニティ保守。)
- [T3 Code](https://t3.codes/) — Codex・Claude Code・Cursor・OpenCode を 1 つのインターフェースからオーケストレーションするオープンソースの Web／デスクトップ制御プレーン（Theo / Ping）。🔓 [![★](https://img.shields.io/github/stars/pingdotgg/t3code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/pingdotgg/t3code/stargazers)
  - `pingdotgg/t3code` · MIT · macOS/Windows/Linux/Web/CLI · *特徴:* スレッドごとの git ブランチ＋チェックポイント、タイトル／本文を自動生成する 1 ボタン commit/push/PR、`npx t3@latest`。(本人いわく「ごく初期」。)
- [Catnip](https://github.com/wandb/catnip) — Claude Code をコンテナ化 worktree サンドボックスで動かすセルフホスト可能な Web サービス（Weights & Biases）。ネイティブ iOS アプリ付き。🔓 [![★](https://img.shields.io/github/stars/wandb/catnip?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/wandb/catnip/stargazers)
  - `wandb/catnip` · Apache-2.0 · Web/CLI/iOS/Cloud · Claude Code · *特徴:* 並列エージェント用の自動 worktree 作成、`refs/catnip/$NAME` への自動コミット、ローカルまたは GitHub Codespaces/devcontainers で実行、ネイティブ iOS 遠隔操作。
- [Agent Viewer](https://github.com/hallucinogen/agent-viewer) — tmux で動く複数の Claude Code エージェントを起動・監視・メッセージする Web kanban ボード。🔓 [![★](https://img.shields.io/github/stars/hallucinogen/agent-viewer?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hallucinogen/agent-viewer/stargazers)
  - `hallucinogen/agent-viewer` · ライセンス未確認 · macOS/Linux/Web/mobile（Tailscale）· Claude Code · *特徴:* パス＋プロンプトから tmux へエージェントを起動、Running/Idle/Completed ボード、ライブ ANSI ターミナル表示、2 ファイルの素の JS アプリ。
- [OpenGoat](https://github.com/marian2js/opengoat) — 多数のプロバイダにまたがって作業を連携する、エージェントの階層型組織を構築するプラットフォーム。🔓 [![★](https://img.shields.io/github/stars/marian2js/opengoat?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/marian2js/opengoat/stargazers)
  - `marian2js/opengoat` · MIT · Web（ローカルUI）/CLI · Claude Code/Codex/Cursor/Copilot CLI/Lovable · *特徴:* マネージャ→部下の `reportsTo` 階層、ロールベースのスキル割当（OpenClaw エンジン上に構築）。
- [Agent Kanban](https://agent-kanban.dev/) — エージェントを暗号的に識別されるチームメンバーとして扱い、タスクを請け負い PR を出させる、エージェントファーストの kanban ボード。🟡 [![★](https://img.shields.io/github/stars/saltbo/agent-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/saltbo/agent-kanban/stargazers)
  - `saltbo/agent-kanban` · FSL-1.1-ALv2（→ Apache-2.0）· CLI/Web · ACP · Claude Code/Codex/Gemini CLI/Copilot/Hermes · *特徴:* エージェントごとの Ed25519 ID、リーダーが計画・割当しワーカーが PR を出荷、人間承認前にエージェントがエージェントをレビュー、Cloudflare（D1）にデプロイ可能。
- [Kanban Code](https://github.com/langwatch/kanban-code) — kanban ボードで複数の Claude Code セッションを管理するネイティブデスクトップアプリ＋CLI（LangWatch）。🔓 [![★](https://img.shields.io/github/stars/langwatch/kanban-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/langwatch/kanban-code/stargazers)
  - `langwatch/kanban-code` · AGPL-3.0 · macOS/Windows/CLI · Claude Code · *特徴:* Claude Code フックで駆動するボード、カードごとの worktree、Mutagen 同期付き SSH リモート実行、Pushover のスマホ／Watch 通知、マスターエージェントによるオーケストレーション用 `--json` CLI。

<a id="cloud"></a>
## クラウド／ホスト型コントロールプレーン

クラウドでエージェント艦隊を動かすホスト型（またはセルフホスト可能な）コントロールプレーン。

- [Oz](https://www.warp.dev/oz) — 複数ハーネスにまたがるクラウドコーディングエージェントの艦隊を実行・監視する Warp 製オーケストレーションプラットフォーム。🟡 [![★](https://img.shields.io/github/stars/warpdotdev/warp?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/warpdotdev/warp/stargazers)
  - `warpdotdev/warp`（クライアント。Oz バックエンドはホスト型）· クライアントは MIT/AGPLv3 · Cloud/Web/Desktop/CLI · MCP · Claude Code/Codex/Gemini CLI/Warp Agent · *特徴:* 対話的エージェントはローカル、自律エージェントはクラウドで実行、セルフホストまたは Warp マネージド、イベント／トリガーベースの実行、マルチモデルルーティング、単一ペインの監査証跡。(★数は Warp クライアント全体のもの。)
- [Centaur](https://centaur.run/) — CLI エージェントハーネスを隔離 Kubernetes サンドボックス内で動かし、Slack または API から操作する Paradigm 製のセルフホスト制御プレーン。🔓 [![★](https://img.shields.io/github/stars/paradigmxyz/centaur?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/paradigmxyz/centaur/stargazers)
  - `paradigmxyz/centaur` · Apache-2.0 / MIT · Cloud/CLI/Slack · Claude Code/Codex/Amp · *特徴:* スレッドごとの Slack ネイティブなマルチプレイヤーエージェント、再起動を耐える Postgres 永続の durable execution、生のシークレットを露出しない認証情報注入、会話ごとの K8s サンドボックス。

<a id="viewers"></a>
## セッションビューア／コンパニオンツール

エージェントのセッションを観察・分析するツール（起動・操作はしない）。上記ツールと併用すると便利です。

- [AgentsView](https://www.agentsview.io/) — コーディングエージェントのセッションログを索引化し、検索・トークン／コスト分析・アクティビティインサイトを提供するローカルファーストのデスクトップ／CLI／Web ツール。🔓 [![★](https://img.shields.io/github/stars/kenn-io/agentsview?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/kenn-io/agentsview/stargazers)
  - `kenn-io/agentsview` · MIT · macOS/Windows/Linux/CLI/Web · 20 以上のエージェントを読み取り（Claude Code、Codex、Aider、Cursor、Gemini CLI…）· *特徴:* FTS5 全文検索、モデル別コストダッシュボード、リアルタイムセッションストリーミング、任意の Postgres チーム同期。(観測のみ。)
- [Claude Code Agent Monitor](https://hoangsonww.github.io/Claude-Code-Agent-Monitor/) — フック経由で Claude Code のセッション・ツール使用・コスト・サブエージェントのオーケストレーションを可視化するセルフホストのリアルタイムダッシュボード。🔓 [![★](https://img.shields.io/github/stars/hoangsonww/Claude-Code-Agent-Monitor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hoangsonww/Claude-Code-Agent-Monitor/stargazers)
  - `hoangsonww/Claude-Code-Agent-Monitor` · MIT · Web/macOS/Windows/VSCode/CLI · Claude Code を読み取り · MCP · *特徴:* D3/Sankey/Mermaid の DAG 可視化、ルールベースのアラート＋Webhook＋Web Push、kanban ステータスボード。(主に観測用。)

<a id="archived"></a>
## アーカイブ／注目プロジェクト

すでに活発な保守はされていないが、歴史的に重要な参照点。

- [Crystal](https://github.com/stravu/crystal) — 複数の Claude Code/Codex セッションを並列実行し各々を独自 worktree で動かし、並列比較と差分レビューを行った Electron アプリ。🔓 [![★](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/stravu/crystal/stargazers) `stravu/crystal` · MIT · **提供終了 — 現在は [Nimbalyst](https://nimbalyst.com/)**（リポジトリ最終更新 2026-02）。worktree 隔離マルチセッション Claude Code の先駆け。
- [Terragon](https://github.com/terragon-labs/terragon-oss) — ホスト型のバックグラウンドエージェント艦隊オーケストレーター。🔓 [![★](https://img.shields.io/github/stars/terragon-labs/terragon-oss?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/terragon-labs/terragon-oss/stargazers) `terragon-labs/terragon-oss` · Apache-2.0 · **サービスは 2026-01-16 に終了**。リポジトリは保守されていないスナップショット。
- [Claude Code Board](https://cc-board.cablate.com/) — 複数の Claude Code CLI セッションを管理する Web kanban 風マネージャ。🔓 [![★](https://img.shields.io/github/stars/cablate/Claude-Code-Board?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/cablate/Claude-Code-Board/stargazers) `cablate/Claude-Code-Board` · MIT · **保守終了**（最終更新 2026-01）。

<a id="related"></a>
## 関連: エージェント・フレームワーク・プロトコル

クライアント／オーケストレーターそのものではないが、上記ツールが管理・連携する対象。

**コーディングエージェント（オーケストレーション対象）**
- [Claude Code](https://github.com/anthropics/claude-code) · [OpenAI Codex](https://github.com/openai/codex) · [Gemini CLI](https://github.com/google-gemini/gemini-cli) · [OpenCode](https://github.com/sst/opencode) · [Aider](https://github.com/Aider-AI/aider) · [Cursor CLI](https://cursor.com/cli) · [Amp](https://ampcode.com/) · [Pi](https://github.com/parallel-web/pi)

**デスクトップアプリも兼ねるエージェント（クライアントとしては対象外）**
- [Goose](https://github.com/block/goose) — LLM に直接接続し、ACP サーバーとしても動作する Block の拡張可能な Rust 製エージェント。Orca・Paseo・cmux などに管理される。
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) — Nous Research の汎用自己改善エージェント。Agent Kanban・AI Maestro が ACP 経由でターゲットにし、Multica でも対応エージェントとして利用できる。
- [OpenClaw](https://github.com/openclaw/openclaw) — セルフホストのパーソナルアシスタントランタイム。Antfarm と OpenGoat の基盤。

**マルチエージェントフレームワーク／インフラ（隣接領域）**
- [Symphony](https://github.com/openai/symphony) — トラッカーの issue ごとに Codex セッションを動かす OpenAI のオーケストレーション仕様＋Elixir リファレンス実装。
- [FleetQ](https://github.com/escapeboy/agent-fleet-o) — ネイティブ MCP サーバーを備えた汎用マルチエージェント DAG／ワークフロープラットフォーム。
- [AgentTier](https://github.com/agenttier/agenttier) — エージェント実行用の Kubernetes ネイティブなサンドボックス as a service（インフラ層）。

**プロトコル**
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) — エージェントをツール／データに接続。本リストで最も普及した統合プロトコル。
- [Agent Client Protocol (ACP)](https://agentclientprotocol.com) — エージェントをエディタ／ホストクライアントに埋め込む Zed のプロトコル。Obsidian Agent Client・CodeCompanion.nvim・Agentic.nvim・Agent of Empires・Agent Kanban が使用。

<a id="contributing"></a>
## コントリビュート

コントリビュート歓迎です！収録基準とエントリ形式は [CONTRIBUTING.md](CONTRIBUTING.md)（英語）を参照し、PR を送るか[ツールを提案](../../issues/new?template=suggest-a-tool.md)してください。エントリ修正は出典リンク付きの PR が最速です。

おおまかな収録目安として、GitHub star 数が約 **50 未満**のツールは、ある程度の実績が出るまで原則見送ります（真に新規性のあるものは早めに収録することがあります）。star 数は採用度の目安であり、品質の判定ではありません。

<a id="dataquality"></a>
## データ品質についての注記

本リストは **2026 年 6 月**の構造化リサーチで作成しました。全ツールの実在を GitHub API で確認し、各エントリは各プロジェクトの README／公式サイトと突き合わせて**ライセンス・プラットフォーム・対応エージェント・プロトコル（MCP/ACP）・機能の記述を検証・修正済み**です。star バッジはライブ更新され、**各セクションの並び順は作成時点の star 数を反映**します。プロジェクトの進化により細部は古くなり得るため、特定の主張に依存する前に確認のうえ、修正をお寄せください。注意点として、**Cline (Kanban)** の ★ バッジはオーケストレーターのリポジトリを指し（親プロジェクトははるかに大規模）、**Oz** のバッジは Oz 単体ではなく Warp クライアント全体を数えています。スコープ規則と来歴は [docs/awesome-agent-clients-design.md](docs/awesome-agent-clients-design.md) を参照してください。

## ライセンス

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

法律上可能な範囲で、コントリビューターは本作品に対する著作権および関連・隣接権をすべて放棄しています。[LICENSE](LICENSE)（CC0-1.0）を参照してください。
