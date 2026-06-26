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

各エントリには GitHub の star 数バッジ（[shields.io](https://shields.io) で自動更新）を付けました。どれくらい使われているかのざっくりした目安です。**並び順は各セクションとも star 数の多い順。** クローズドソース製品にバッジはありません。

- 🔓 オープンソース · 🟡 ソースアベイラブル／オープンコア · 🔒 クローズドソース
- **MCP** = [Model Context Protocol](https://modelcontextprotocol.io) · **ACP** = [Agent Client Protocol](https://agentclientprotocol.com)
- 「Agents」は、そのツールが動かせる*外部の*コーディングエージェントです。
- 収録の目安: star 数が約50に満たないツールはいったん見送ります（[コントリビュート](#contributing)参照）。star はあくまで目安で、良し悪しの判定ではありません。

---

<a id="desktop"></a>
## デスクトップ／マルチプラットフォームクライアント

デスクトップで動くネイティブ／Electron アプリ。モバイルや Web のコンパニオンを持つものも多い。

- [opcode](https://github.com/winfunc/opcode) — Claude Code を GUI で扱うツールキット。セッション管理、カスタム CC エージェントの作成、バックグラウンド実行、MCP 設定、チェックポイント確認までこなす。🔓 [![★](https://img.shields.io/github/stars/winfunc/opcode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/winfunc/opcode/stargazers)
  - `winfunc/opcode` · AGPL-3.0 · macOS/Windows/Linux · Claude Code · MCP · *特徴:* カスタム CC エージェントビルダー、使用量分析、チェックポイントのタイムライン／フォーク。(Tauri アプリ。最終リリースは 2025-10 — 保守状況は要確認。)
- [Superset](https://superset.sh/) — 多数の CLI コーディングエージェントを並列で走らせ、それぞれを別々の git worktree に隔離する macOS 向けワークスペース。差分レビューとエディタ連携を内蔵。🟡 [![★](https://img.shields.io/github/stars/superset-sh/superset?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/superset-sh/superset/stargazers)
  - `superset-sh/superset` · Elastic License 2.0 · macOS · *特徴:* 10以上の CLI エージェントの並列オーケストレーション、タスクごとの git-worktree 隔離、内蔵の差分ビューア/エディタ、ワークスペースのセットアップ/破棄プリセット、ワンクリックでエディタ連携。
- [Paseo](https://paseo.sh/) — Claude Code・Codex・Copilot・OpenCode・Pi の5つを1つの画面から動かすセルフホスト型デーモン。デスクトップ・モバイル・Web・CLI のクライアントがそこへつなぐ。🟡 [![★](https://img.shields.io/github/stars/getpaseo/paseo?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/getpaseo/paseo/stargazers)
  - `getpaseo/paseo` · ソースアベイラブル（独自ライセンス）· Desktop/iOS/Android/Web/CLI · MCP · *特徴:* 自分のマシンでエージェントを並列実行、クロスデバイスのクライアント、音声操作、リモート接続用リレー、オーケストレーションスキル（`/paseo-handoff`、`/paseo-loop`、`/paseo-committee`）。
- [Orca](https://www.onorca.dev/) — 多数の CLI コーディングエージェントを横に並べて走らせ、それぞれに専用の git worktree・ターミナル・ブラウザタブを与える Agent Development Environment。🔓 [![★](https://img.shields.io/github/stars/stablyai/orca?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/stablyai/orca/stargazers)
  - `stablyai/orca` · MIT · macOS/Windows/Linux/iOS/Android/CLI · MCP · *特徴:* タスクごとの worktree ＋「Design Mode」の Chromium キャプチャ、エージェントを操作するモバイルコンパニオン、SSH リモート worktree。25 以上のエージェント（Claude Code、Codex、OpenCode、Cursor CLI…）を駆動。
- [CodePilot](https://github.com/op7418/CodePilot) — Claude Code CLI をラップしてファイル・ターミナル・git 操作をこなすクロスプラットフォームのデスクトップクライアント。モデルは複数プロバイダから選べ、メッセージアプリ越しの遠隔操作にも対応。🟡 [![★](https://img.shields.io/github/stars/op7418/CodePilot?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/op7418/CodePilot/stargazers)
  - `op7418/CodePilot` · BSL-1.1（→ Apache-2.0）· macOS/Windows/Linux · Claude Code · MCP · *特徴:* Telegram/Feishu/Discord/QQ/WeChat からの遠隔操作、17 以上のモデルプロバイダをスレッド途中で切替、MCP ランタイムダッシュボード、cron スケジューラ。
- [1code](https://1code.dev/) — Claude Code と Codex を、ローカルでもクラウドサンドボックスでも worktree 隔離して動かすオープンコアのデスクトップ／Web クライアント。🟡 [![★](https://img.shields.io/github/stars/21st-dev/1code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/21st-dev/1code/stargazers)
  - `21st-dev/1code` · Apache-2.0（オープンコア）· macOS/Windows/Linux/Web/PWA · MCP · Claude Code/Codex · *特徴:* セッションごとの worktree ＋ kanban、バックグラウンド／クラウドサンドボックス実行、任意のメッセージからのロールバック、PWA でのモバイル操作。
- [emdash](https://emdash.sh/) — Claude Code・Codex・Cursor・Gemini・Amp など複数のコーディングエージェント CLI を並列で走らせ、それぞれを別々の git worktree に隔離するデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/generalaction/emdash?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/generalaction/emdash/stargazers)
  - `generalaction/emdash` · Apache-2.0 · macOS/Windows/Linux · *特徴:* 差分レビュー、PR 作成／マージ＋CI 確認、Linear/GitHub/Jira/GitLab/Asana からの issue 取り込み、ローカル／リモート（SSH/SFTP）実行。
- [AgentsMesh](https://agentsmesh.ai/) — 複数のマシンにまたがるセルフホストのランナー群を1つのコンソールから操り、ターミナルエージェントを動かすプラットフォーム（web/desktop/iOS/CLI）。🟡 [![★](https://img.shields.io/github/stars/AgentsMesh/AgentsMesh?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/AgentsMesh/AgentsMesh/stargazers)
  - `AgentsMesh/AgentsMesh` · BSL-1.1（→ GPL-2.0）· Web/Desktop/iOS/CLI · Claude Code/Codex/Gemini CLI/Aider/OpenCode · *特徴:* マシン艦隊にまたがるポッドごとの worktree サンドボックス、「Autopilot」制御エージェント、@メンション付きのポッド間 Mesh & Channels。
- [mux](https://mux.coder.com/) — 多数のエージェントを隔離ワークスペースで並列に走らせる Coder 製のデスクトップ／ブラウザアプリ。ランタイムは Local・Worktree・SSH から選べる。🔓 [![★](https://img.shields.io/github/stars/coder/mux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/coder/mux/stargazers)
  - `coder/mux` · AGPL-3.0 · macOS/Linux/Web/VSCode · *特徴:* 独自のモデル非依存エージェントループ（マルチモデル）、Local／Worktree／SSH の隔離ワークスペースでの並列実行、git の分岐／コンフリクト可視化、サーバーモードでのモバイル対応。
- [Agent Teams AI](https://agentteams.live/) — コーディングエージェントでチームを組み、互いにメッセージを送り合いながらコードをレビューし合わせるデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/777genius/agent-teams-ai?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/777genius/agent-teams-ai/stargazers)
  - `777genius/agent-teams-ai` · AGPL-3.0 · macOS/Windows/Linux · MCP · Claude Code/Codex/OpenCode · *特徴:* エージェント間／チーム間メッセージング、hunk 単位の accept/reject 差分レビュー、5 列の kanban、エージェントごとの CPU/RAM ライブダッシュボード。
- [Cline (Kanban)](https://cline.bot/) — Cline プロジェクト（60k★ 超）のコンパニオン Kanban アプリ。並列の CLI エージェントを隔離した git worktree でさばく。🔓 [![★](https://img.shields.io/github/stars/cline/kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/cline/kanban/stargazers)
  - `cline/kanban` · Apache-2.0 · CLI/Web · インストール済み CLI エージェントを自動検出 · *特徴:* 並列エージェント用の kanban ボード、タスクごとの一時 git worktree 隔離、自動コミット付きタスク依存チェーン。(コアの [Cline](https://github.com/cline/cline) はエージェント本体。ここではオーケストレーター部分を収録。)
- [claude-code-by-agents](https://claudecode.run/) — 複数の Claude Code エージェントを、ローカルとリモートのマシンをまたいで @メンションで振り分ける Swift 製ネイティブ macOS/iOS アプリ。🔓 [![★](https://img.shields.io/github/stars/baryhuang/claude-code-by-agents?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/baryhuang/claude-code-by-agents/stargazers)
  - `baryhuang/claude-code-by-agents` · MIT · macOS/iOS · Claude Code · *特徴:* 名前付きエージェントへの @メンションルーティング、マシン間連携、iMessage 風の 2 ペインネイティブアプリ。
- [Parallel Code](https://github.com/johannesjo/parallel-code) — 複数のエージェント CLI を並列で立ち上げ、それぞれを専用 worktree に隔離して差分レビューと取捨選択マージを行うデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/johannesjo/parallel-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/johannesjo/parallel-code/stargazers)
  - `johannesjo/parallel-code` · MIT · macOS/Linux · Claude Code/Codex/Gemini CLI/Antigravity/Copilot · *特徴:* インライン差分コメント＋コミット単位ナビゲーション、PR の CI ウォッチャー、Docker サンドボックス、Wi-Fi/Tailscale 越しの QR モバイル監視。
- [AI Maestro](https://github.com/23blocks-OS/ai-maestro) — マシンをまたいでターミナルエージェントを束ねるオーケストレーションプラットフォーム。ダッシュボード、永続メモリ、エージェント同士のメッセージングを備える。🔓 [![★](https://img.shields.io/github/stars/23blocks-OS/ai-maestro?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/23blocks-OS/ai-maestro/stargazers)
  - `23blocks-OS/ai-maestro` · MIT · macOS/Linux/Windows(WSL2)/Web/CLI · *特徴:* 自動検出付きのマルチマシンピアメッシュ、署名付き Agent Messaging Protocol、コードグラフ可視化、依存関係付き kanban、Slack/Discord/WhatsApp ゲートウェイ。
- [Dorothy](https://github.com/Charlie85270/Dorothy) — Claude Code・Codex・Gemini をプロジェクト横断で並列にさばくデスクトップアプリ。kanban ボードと、束ね役のメタオーケストレーターエージェントを持つ。🔓 [![★](https://img.shields.io/github/stars/Charlie85270/Dorothy?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Charlie85270/Dorothy/stargazers)
  - `Charlie85270/Dorothy` · MIT · macOS/Linux · Claude Code/Codex/Gemini · MCP · *特徴:* 「Super Agent」メタオーケストレーター、5 つの MCP サーバー同梱、Telegram/Slack 遠隔操作、cron による自律実行。
- [Constellagent](https://constellagent.vercel.app/) — 複数の AI エージェントセッションを並列で走らせる macOS アプリ。各セッションに専用のターミナル・Monaco エディタ・隔離 worktree が付く。🔓 [![★](https://img.shields.io/github/stars/owengretzinger/constellagent?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/owengretzinger/constellagent/stargazers)
  - `owengretzinger/constellagent` · ライセンス未確認 · macOS · エージェント非依存 · *特徴:* 1 ウィンドウ内でエージェントごとの worktree、フルターミナルエミュレータ、Monaco エディタ（差分対応）、sleep/wake 復帰付き cron 自動化。
- [Sculptor](https://imbue.com/sculptor/) — エージェントを隔離コンテナの中で並列に走らせ、その成果をローカルリポジトリへ取り込む Imbue 製のデスクトップアプリ。🔓 [![★](https://img.shields.io/github/stars/imbue-ai/sculptor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/imbue-ai/sculptor/stargazers)
  - `imbue-ai/sculptor` · MIT · macOS/Linux · Claude Code/Codex · *特徴:* コンテナ隔離（worktree の代替）、IDE に同期する「Pairing Mode」、修正エージェントを起動するコード課題サジェスト。
- [Conductor](https://www.conductor.build/) — 複数のエージェントを並列に走らせ、それぞれを専用ブランチ・ターミナル・差分を持つ隔離ワークスペースで動かす macOS アプリ（Melty Labs）。🔒 *公開リポジトリなし*
  - `closed-source` · macOS · MCP · Claude Code/Codex/Cursor/OpenCode · *特徴:* 組み込みの差分レビュー＋マージ、GitHub issue から直接ワークスペースを作成。
- [AgentsRoom](https://agentsroom.dev/) — CLI エージェントをプロジェクトをまたいでネイティブのローカルプロセスとして並列にさばくデスクトップアプリ（iOS/Android のコンパニオン付き）。専門ロールとチーム間の引き継ぎを備える。🔒 *公開リポジトリなし*
  - `closed-source`（org: `AgentsRoomDev`）· macOS/Windows/Linux/iOS/Android · MCP · Claude Code/Codex/OpenCode/Gemini CLI/Aider/Grok/Mistral · *特徴:* 14 の専門エージェントロール、「Agent Teams」ハンドオフキャンバス、kanban バックログ（公開リモート投稿対応含む）、E2E 暗号化モバイル同期。

<a id="terminal"></a>
## ターミナル／CLI オーケストレーター

ペインや tmux、worktree を使ってエージェントを立ち上げ・連携させる、TUI ダッシュボードや CLI 中心のツール。

- [cmux](https://cmux.com/) — ターミナルエージェントを並列で走らせて整理する、libghostty ベースのネイティブ macOS ターミナル。画面分割と、エージェントの状態を知らせる通知を備える。🔓 [![★](https://img.shields.io/github/stars/manaflow-ai/cmux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/manaflow-ai/cmux/stargazers)
  - `manaflow-ai/cmux` · GPL-3.0-or-later · macOS（＋ iOS コンパニオン、beta）· *特徴:* OSC 9/99/777 の通知リング／バッジ、スクリプト可能な組み込みブラウザ、`cmux claude-teams` のチームメイトモード、SSH リモート。任意のターミナルエージェント（Claude Code、Codex、OpenCode、Gemini CLI、Aider、Goose…）を実行。
- [Gas Town](https://github.com/gastownhall/gastown) — Steve Yegge 作のマルチエージェントオーケストレーションシステム。並列エージェントを、git に残す作業状態と見張り役の階層でまとめる。🔓 [![★](https://img.shields.io/github/stars/gastownhall/gastown?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/gastownhall/gastown/stargazers)
  - `gastownhall/gastown` · MIT · CLI/TUI/Web · Claude Code/Copilot/Codex/Gemini/Cursor/Amp/OpenCode/Pi · *特徴:* ロール階層（Mayor → workers）、共有メモリとしての git バック issue トラッカー「beads」、bors 風の検証付きマージキュー（Go）。
- [Claude Squad](https://smtg-ai.github.io/claude-squad/) — 複数のエージェントインスタンスを並列で束ねるターミナル TUI。各インスタンスに専用の git worktree と tmux セッションが付く。🔓 [![★](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/smtg-ai/claude-squad/stargazers)
  - `smtg-ai/claude-squad` · AGPL-3.0 · macOS/Linux/TUI · Claude Code/Codex/Gemini CLI/Aider（＋カスタムプログラムで任意のローカルエージェント）· *特徴:* セッションごとの worktree＋tmux 隔離、差分タブレビュー、実験的な yolo／自動承認バックグラウンドモード。
- [Antfarm](https://www.antfarm.cool/) — 決定論的な YAML ワークフローで専門エージェントのチームを動かす TypeScript 製 CLI。🔓 [![★](https://img.shields.io/github/stars/snarktank/antfarm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/snarktank/antfarm/stargazers)
  - `snarktank/antfarm` · MIT · CLI/Web · *特徴:* feature-dev／bug-fix／security-audit のワークフロー同梱、エージェント間検証（自己承認不可）、ステップごとに新鮮なコンテキスト、Web ダッシュボード。(OpenClaw ランタイム上で動作。)
- [Supacode](https://supacode.sh/) — 50 以上の CLI エージェントを並列で走らせ、それぞれを専用 git worktree に隔離する libghostty ベースのネイティブ macOS コマンドセンター。🟡 [![★](https://img.shields.io/github/stars/supabitapp/supacode?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/supabitapp/supacode/stargazers)
  - `supabitapp/supacode` · FSL-1.1-ALv2（→ Apache-2.0）· macOS · *特徴:* ネイティブ（Electron 不使用）、ターミナルから GitHub ネイティブの PR/CI/コンフリクト解決。
- [Scion](https://googlecloudplatform.github.io/scion/) — エージェントを隔離コンテナに入れ、それぞれに専用の worktree と認証情報を持たせてさばく、実験的なホスト側 CLI＋ハブ（Google Cloud）。🔓 [![★](https://img.shields.io/github/stars/GoogleCloudPlatform/scion?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/GoogleCloudPlatform/scion/stargazers)
  - `GoogleCloudPlatform/scion` · Apache-2.0 · CLI/Web/Linux/Cloud · Claude Code/Gemini CLI/Codex/OpenCode · *特徴:* エージェントごとのコンテナ＋worktree＋認証情報の隔離、フロー追跡付きエージェント間メッセージングパイプライン、Docker/Podman/VM/Kubernetes へのデプロイ（実験的・Google 公式製品ではない）。
- [TAKT](https://github.com/nrslib/takt) — コーディングエージェントを、再現できる YAML ワークフロー（plan → implement → review → fix）に落とし込むオープンソース CLI。隔離 worktree と人手のチェックポイント付き。🔓 [![★](https://img.shields.io/github/stars/nrslib/takt?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/nrslib/takt/stargazers)
  - `nrslib/takt` · MIT · CLI · Claude Code/Codex/OpenCode/Cursor/Copilot CLI/Kiro · *特徴:* ステップごとのロール／ペルソナ／ポリシー／出力契約、サイレントにスキップできないレビューループ、タスクごとの追跡可能なログ／レポート（TypeScript）。
- [Agent Deck](https://github.com/asheshgoplani/agent-deck) — 多数のエージェントセッションをプロジェクト横断で立ち上げ・整理・フォーク・自律監視するターミナル版「司令室」。🔓 [![★](https://img.shields.io/github/stars/asheshgoplani/agent-deck?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/asheshgoplani/agent-deck/stargazers)
  - `asheshgoplani/agent-deck` · MIT · TUI/CLI/Web/macOS/Linux/Windows · MCP · Claude Code/Gemini CLI/OpenCode/Codex/Copilot/Crush · *特徴:* 自律監視／エスカレーション用の「Conductors」、worktree＋Docker 隔離、Telegram/Slack 操作、リモート SSH インスタンス。
- [ntm](https://github.com/Dicklesworthstone/ntm) — tmux を、ペインをまたいでエージェントを立ち上げ・並べ・連携させる司令塔に変える Go 製 CLI。🔓 [![★](https://img.shields.io/github/stars/Dicklesworthstone/ntm?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/Dicklesworthstone/ntm/stargazers)
  - `Dicklesworthstone/ntm` · MIT（＋追加条項）· CLI/TUI/Web · *特徴:* worktree＋ファイル予約ロック、「Agent Mail」連携、高リスク操作の 2 名承認、遠隔操作用の REST/SSE/WebSocket API。Claude Code/Codex/Antigravity を駆動。
- [amux](https://github.com/andyrewlee/amux) — 複数のエージェントを並列で走らせ、それぞれを専用 worktree と tmux セッションに隔離するターミナル UI。🔓 [![★](https://img.shields.io/github/stars/andyrewlee/amux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/andyrewlee/amux/stargazers)
  - `andyrewlee/amux` · MIT · macOS/Linux/TUI · Claude Code/Codex/Gemini CLI/Amp/OpenCode/Droid · *特徴:* エージェントごとの tmux 隔離、差分表示統合、信頼ゲート付き設定スクリプト、pprof/PTY トレース（Go）。
- [AgentBox](https://agent-box.sh/) — 複数のエージェントを並列で走らせ、それぞれをローカル（Docker）やクラウドのサンドボックス VM に隔離する CLI。🔓 [![★](https://img.shields.io/github/stars/madarco/agentbox?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/madarco/agentbox/stargazers)
  - `madarco/agentbox` · MIT · macOS/Linux/CLI · Claude Code/Codex/OpenCode · *特徴:* プロジェクトをサンドボックス VM に「テレポート」（Docker/OrbStack または Hetzner/Vercel/Daytona/E2B）、1 秒未満のチェックポイント起動、VNC＋トンネル。
- [OpenKanban](https://github.com/TechDufus/openkanban) — チケットごとに専用 git worktree と組み込みのエージェントターミナルが立ち上がる、ターミナル UI の kanban ボード。🔓 [![★](https://img.shields.io/github/stars/TechDufus/openkanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/TechDufus/openkanban/stargazers)
  - `TechDufus/openkanban` · AGPL-3.0 · macOS/Linux/TUI · OpenCode/Claude Code/Gemini CLI/Codex/Aider · *特徴:* ターミナル内 kanban、チケット＝worktree＋エージェントターミナル、複数プロジェクト統合ボード（Go）。
- [dux](https://getdux.app/) — 複数のエージェント CLI を並列で走らせ、それぞれを専用 worktree に置く 3 ペイン構成の TUI。git ステージングをその場で扱える。🔓 [![★](https://img.shields.io/github/stars/patrickdappollonio/dux?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/patrickdappollonio/dux/stargazers)
  - `patrickdappollonio/dux` · MIT · macOS/Linux/TUI · Claude Code/Codex/OpenCode/ほか · *特徴:* 実 CLI をラップするので MCP/フック/スキルが機能継続、シンタックスハイライト差分＋AI コミットメッセージ、`gh` での PR ステータス追跡、セッションフォーク（Rust）。
- [Agent Orchestrator](https://github.com/ComposioHQ/agent-orchestrator) — 多数の並列コーディングエージェントセッションをそれぞれ専用の git worktree で見張り、CI 失敗・レビューコメント・マージ衝突を担当エージェントへ差し戻す Composio 製オーケストレーター（現 ReverbCode）。🟡 [![★](https://img.shields.io/github/stars/ComposioHQ/agent-orchestrator?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/ComposioHQ/agent-orchestrator/stargazers)
  - `ComposioHQ/agent-orchestrator` · ライセンス未指定（LICENSEファイルなし）· CLI/Desktop · 23 のエージェントアダプタ（Claude Code/Codex/Cursor/OpenCode/Aider/Kimi ほか）· *特徴:* エージェント非依存のアダプタ群、zellij ランタイムでの git-worktree 隔離、GitHub PR/CI を監視して担当エージェントに通知（マージは人間）。
- [Agent of Empires](https://github.com/njbrake/agent-of-empires) — Linux/macOS 上でエージェントのセッションを束ねるマネージャ。ターミナル TUI からも、ブラウザ／PWA のダッシュボードからも操作できる。🔓 [![★](https://img.shields.io/github/stars/njbrake/agent-of-empires?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/njbrake/agent-of-empires/stargazers)
  - `njbrake/agent-of-empires` · MIT · CLI/TUI/Web/PWA · ACP · 13 エージェント（Claude Code/OpenCode/Codex/Gemini CLI/Cursor CLI/Copilot ほか）· *特徴:* tmux＋worktree＋Docker サンドボックス、ダッシュボードに ACP 由来の構造化エージェント状態を描画、QR＋パスフレーズで HTTPS 越しのスマホアクセス（Rust・Mozilla.ai 支援）。
- [Bernstein](https://bernstein.run/) — ゴールを分解し、複数の CLI エージェントを並列 worktree で走らせ、監査チェーンで検証してマージする決定論的な Python 製オーケストレーター。🔓 [![★](https://img.shields.io/github/stars/chernistry/bernstein?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/chernistry/bernstein/stargazers)
  - `chernistry/bernstein` · Apache-2.0 · CLI/Web/VSCode/Cloud · MCP · 44 のエージェントアダプタ（Claude Code/Codex/Gemini CLI/Copilot/Aider/Goose…）· *特徴:* ゼロ LLM の決定論的スケジューラ、検証ゲート（テスト/lint/型）、HMAC-SHA256 監査チェーン＋Ed25519 署名エージェントカード、Cloudflare Workers 実行オプション。

<a id="ide"></a>
## IDE／エディタプラグイン

エディタの中に住むエージェント／オーケストレーター。

- [CodeCompanion.nvim](https://codecompanion.olimorris.dev/) — LLM プロバイダや、ACP 経由の外部エージェントにチャットバッファからつなぐ Neovim プラグイン。🔓 [![★](https://img.shields.io/github/stars/olimorris/codecompanion.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/olimorris/codecompanion.nvim/stargazers)
  - `olimorris/codecompanion.nvim` · Apache-2.0 · Neovim · MCP + ACP · Claude Code/Codex/Copilot CLI/Gemini CLI/Goose/Cursor CLI/OpenCode/ほか · *特徴:* インラインバッファ変換、エディタコンテキスト変数、複数同時チャット、幅広い ACP エージェント対応。
- [CC GUI (Claude or Codex)](https://plugins.jetbrains.com/plugin/29342-cc-gui-claude-or-codex-) — Claude Code と OpenAI Codex の CLI に、2 エンジン構成の GUI をかぶせる JetBrains プラグイン。🔓 [![★](https://img.shields.io/github/stars/zhukunpenglinyutong/jetbrains-cc-gui?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/zhukunpenglinyutong/jetbrains-cc-gui/stargazers)
  - `zhukunpenglinyutong/jetbrains-cc-gui` · MIT · JetBrains · Claude Code/Codex · MCP · *特徴:* `@file` コンテキスト、画像入力、会話の巻き戻し、差分比較＋コードジャンプ、スキルのスラッシュコマンド。
- [Obsidian Agent Client](https://rait-09.github.io/obsidian-agent-client/) — Agent Client Protocol 経由で外部のコーディングエージェントを Obsidian の vault に取り込む Obsidian プラグイン。🔓 [![★](https://img.shields.io/github/stars/RAIT-09/obsidian-agent-client?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/RAIT-09/obsidian-agent-client/stargazers)
  - `RAIT-09/obsidian-agent-client` · Apache-2.0 · Desktop（Obsidian）· ACP + MCP · Claude Code/Codex/Gemini CLI/OpenCode/Qwen/Kiro/Mistral · *特徴:* コンテキストとしての `@note` メンション、複数同時エージェントセッション、Markdown へのチャットエクスポート、ACP ネイティブ。
- [Agentic.nvim](https://github.com/carlos-algms/agentic.nvim) — ACP 対応のコーディングエージェントなら何でも、エディタ内のチャットからつなげる Neovim プラグイン。🔓 [![★](https://img.shields.io/github/stars/carlos-algms/agentic.nvim?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/carlos-algms/agentic.nvim/stargazers)
  - `carlos-algms/agentic.nvim` · MIT · Neovim · ACP · Claude Code/Gemini/Codex/OpenCode/Cursor/Copilot/Cline/Goose/ほか · *特徴:* 履歴を失わないプロバイダ切替、Neovim とターミナル間のセッション復元、対話的なツール呼び出し承認。
- [Claude Code Plus](https://plugins.jetbrains.com/plugin/28343-claude-code-plus) — IntelliJ 系 IDE の中で CLI コーディングエージェントを GUI から扱える JetBrains プラグイン。🔓 [![★](https://img.shields.io/github/stars/touwaeriol/claude-code-plus?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/touwaeriol/claude-code-plus/stargazers)
  - `touwaeriol/claude-code-plus` · MIT · JetBrains · Claude Code（リポジトリ記載では Codex/Gemini CLI も）· MCP · *特徴:* Claude CLI 同梱（別途インストール不要）、`@` メンションのファイル検索、マルチセッション、ツール呼び出しの可視化、クリックで開ける差分。

<a id="web"></a>
## Web／セルフホスト型ダッシュボード

ローカルで動かす、あるいはセルフホストするブラウザ中心のオーケストレーター。

- [Multica](https://multica.ai/) — コーディングエージェントを、issue を割り振れるボード管理のチームメイトに変えるオープンソースの managed-agents プラットフォーム。🟡 [![★](https://img.shields.io/github/stars/multica-ai/multica?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/multica-ai/multica/stargazers)
  - `multica-ai/multica` · Apache-2.0（改変版）· Web/self-hosted/Cloud · Claude Code/Codex/Copilot CLI/OpenClaw/OpenCode/Hermes/Gemini/Cursor/Pi/Kimi/Kiro/Qoder · *特徴:* 同僚のように issue を割り当て、リーダーエージェントが委譲する「Squads」、再利用可能なスキルの蓄積（Go）。
- [Vibe Kanban](https://www.vibekanban.com/) — 多数のエージェント CLI でタスクを計画・実行・レビューする kanban インターフェース。タスクごとに隔離した worktree ワークスペースで動く。🔓 [![★](https://img.shields.io/github/stars/BloopAI/vibe-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/BloopAI/vibe-kanban/stargazers)
  - `BloopAI/vibe-kanban` · Apache-2.0 · macOS/Web/CLI · Claude Code/Codex/Gemini CLI/Copilot/Amp/Cursor/OpenCode/Droid/CCR/Qwen · *特徴:* kanban 計画、自動クリーンアップ付きワークスペースごと worktree、インラインコメント差分レビュー、デバイスエミュレーション付き組み込みブラウザプレビュー（Rust＋TS）。(Bloop の移行後はコミュニティ保守。)
- [T3 Code](https://t3.codes/) — Codex・Claude Code・Cursor・OpenCode を 1 つの画面からさばくオープンソースの Web／デスクトップ制御プレーン（Theo / Ping）。🔓 [![★](https://img.shields.io/github/stars/pingdotgg/t3code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/pingdotgg/t3code/stargazers)
  - `pingdotgg/t3code` · MIT · macOS/Windows/Linux/Web/CLI · *特徴:* スレッドごとの git ブランチ＋チェックポイント、タイトル／本文を自動生成する 1 ボタン commit/push/PR、`npx t3@latest`。(本人いわく「ごく初期」。)
- [Catnip](https://github.com/wandb/catnip) — Claude Code をコンテナ化した worktree サンドボックスで動かす、セルフホスト可能な Web サービス（Weights & Biases）。ネイティブ iOS アプリ付き。🔓 [![★](https://img.shields.io/github/stars/wandb/catnip?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/wandb/catnip/stargazers)
  - `wandb/catnip` · Apache-2.0 · Web/CLI/iOS/Cloud · Claude Code · *特徴:* 並列エージェント用の自動 worktree 作成、`refs/catnip/$NAME` への自動コミット、ローカルまたは GitHub Codespaces/devcontainers で実行、ネイティブ iOS 遠隔操作。
- [Agent Viewer](https://github.com/hallucinogen/agent-viewer) — tmux で動く複数の Claude Code エージェントを立ち上げ・監視し、メッセージを送れる Web kanban ボード。🔓 [![★](https://img.shields.io/github/stars/hallucinogen/agent-viewer?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hallucinogen/agent-viewer/stargazers)
  - `hallucinogen/agent-viewer` · ライセンス未確認 · macOS/Linux/Web/mobile（Tailscale）· Claude Code · *特徴:* パス＋プロンプトから tmux へエージェントを起動、Running/Idle/Completed ボード、ライブ ANSI ターミナル表示、2 ファイルの素の JS アプリ。
- [OpenGoat](https://github.com/marian2js/opengoat) — 多数のプロバイダをまたいで作業を連携させる、エージェントの階層型組織を組み立てるプラットフォーム。🔓 [![★](https://img.shields.io/github/stars/marian2js/opengoat?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/marian2js/opengoat/stargazers)
  - `marian2js/opengoat` · MIT · Web（ローカルUI）/CLI · Claude Code/Codex/Cursor/Copilot CLI/Lovable · *特徴:* マネージャ→部下の `reportsTo` 階層、ロールベースのスキル割当（OpenClaw エンジン上に構築）。
- [Agent Kanban](https://agent-kanban.dev/) — エージェントを暗号鍵で識別するチームメンバーとして扱い、タスクを取らせて PR まで出させる、エージェント前提の kanban ボード。🟡 [![★](https://img.shields.io/github/stars/saltbo/agent-kanban?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/saltbo/agent-kanban/stargazers)
  - `saltbo/agent-kanban` · FSL-1.1-ALv2（→ Apache-2.0）· CLI/Web · ACP · Claude Code/Codex/Gemini CLI/Copilot/Hermes · *特徴:* エージェントごとの Ed25519 ID、リーダーが計画・割当しワーカーが PR を出荷、人間承認前にエージェントがエージェントをレビュー、Cloudflare（D1）にデプロイ可能。
- [Kanban Code](https://github.com/langwatch/kanban-code) — kanban ボードで複数の Claude Code セッションを束ねるネイティブデスクトップアプリ＋CLI（LangWatch）。🔓 [![★](https://img.shields.io/github/stars/langwatch/kanban-code?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/langwatch/kanban-code/stargazers)
  - `langwatch/kanban-code` · AGPL-3.0 · macOS/Windows/CLI · Claude Code · *特徴:* Claude Code フックで駆動するボード、カードごとの worktree、Mutagen 同期付き SSH リモート実行、Pushover のスマホ／Watch 通知、マスターエージェントによるオーケストレーション用 `--json` CLI。

<a id="cloud"></a>
## クラウド／ホスト型コントロールプレーン

エージェントの群れをクラウドで動かす、ホスト型（セルフホストも可）のコントロールプレーン。

- [Oz](https://www.warp.dev/oz) — 複数のハーネスをまたいで、クラウド上のコーディングエージェント群を走らせ・見張る Warp 製オーケストレーションプラットフォーム。🟡 [![★](https://img.shields.io/github/stars/warpdotdev/warp?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/warpdotdev/warp/stargazers)
  - `warpdotdev/warp`（クライアント。Oz バックエンドはホスト型）· クライアントは MIT/AGPLv3 · Cloud/Web/Desktop/CLI · MCP · Claude Code/Codex/Gemini CLI/Warp Agent · *特徴:* 対話的エージェントはローカル、自律エージェントはクラウドで実行、セルフホストまたは Warp マネージド、イベント／トリガーベースの実行、マルチモデルルーティング、単一ペインの監査証跡。(★数は Warp クライアント全体のもの。)
- [Centaur](https://centaur.run/) — CLI エージェントのハーネスを隔離した Kubernetes サンドボックスで動かし、Slack や API から操作する Paradigm 製のセルフホスト制御プレーン。🔓 [![★](https://img.shields.io/github/stars/paradigmxyz/centaur?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/paradigmxyz/centaur/stargazers)
  - `paradigmxyz/centaur` · Apache-2.0 / MIT · Cloud/CLI/Slack · Claude Code/Codex/Amp · *特徴:* スレッドごとの Slack ネイティブなマルチプレイヤーエージェント、再起動を耐える Postgres 永続の durable execution、生のシークレットを露出しない認証情報注入、会話ごとの K8s サンドボックス。

<a id="viewers"></a>
## セッションビューア／コンパニオンツール

エージェントのセッションを眺めて分析するためのツール（起動や操作はしない）。上のツールと組み合わせて使う。

- [AgentsView](https://www.agentsview.io/) — コーディングエージェントのセッションログを索引化し、検索・トークン／コスト分析・アクティビティの傾向を見せるローカルファーストのデスクトップ／CLI／Web ツール。🔓 [![★](https://img.shields.io/github/stars/kenn-io/agentsview?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/kenn-io/agentsview/stargazers)
  - `kenn-io/agentsview` · MIT · macOS/Windows/Linux/CLI/Web · 20 以上のエージェントを読み取り（Claude Code、Codex、Aider、Cursor、Gemini CLI…）· *特徴:* FTS5 全文検索、モデル別コストダッシュボード、リアルタイムセッションストリーミング、任意の Postgres チーム同期。(観測のみ。)
- [Claude Code Agent Monitor](https://hoangsonww.github.io/Claude-Code-Agent-Monitor/) — フック経由で Claude Code のセッション・ツール使用・コスト・サブエージェントの動きを可視化する、セルフホストのリアルタイムダッシュボード。🔓 [![★](https://img.shields.io/github/stars/hoangsonww/Claude-Code-Agent-Monitor?style=flat-square&label=%E2%98%85&color=2ea043)](https://github.com/hoangsonww/Claude-Code-Agent-Monitor/stargazers)
  - `hoangsonww/Claude-Code-Agent-Monitor` · MIT · Web/macOS/Windows/VSCode/CLI · Claude Code を読み取り · MCP · *特徴:* D3/Sankey/Mermaid の DAG 可視化、ルールベースのアラート＋Webhook＋Web Push、kanban ステータスボード。(主に観測用。)

<a id="archived"></a>
## アーカイブ／注目プロジェクト

もう活発には保守されていないものの、振り返る価値のあるプロジェクト。

- [Crystal](https://github.com/stravu/crystal) — 複数の Claude Code/Codex セッションを並列で走らせ、それぞれを専用 worktree で動かして横並び比較と差分レビューができた Electron アプリ。🔓 [![★](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/stravu/crystal/stargazers) `stravu/crystal` · MIT · **提供終了 — 現在は [Nimbalyst](https://nimbalyst.com/)**（リポジトリ最終更新 2026-02）。worktree 隔離マルチセッション Claude Code の先駆け。
- [Terragon](https://github.com/terragon-labs/terragon-oss) — ホスト型のバックグラウンドエージェント群を束ねるオーケストレーター。🔓 [![★](https://img.shields.io/github/stars/terragon-labs/terragon-oss?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/terragon-labs/terragon-oss/stargazers) `terragon-labs/terragon-oss` · Apache-2.0 · **サービスは 2026-01-16 に終了**。リポジトリは保守されていないスナップショット。
- [Claude Code Board](https://cc-board.cablate.com/) — 複数の Claude Code CLI セッションを束ねる Web の kanban 風マネージャ。🔓 [![★](https://img.shields.io/github/stars/cablate/Claude-Code-Board?style=flat-square&label=%E2%98%85&color=lightgrey)](https://github.com/cablate/Claude-Code-Board/stargazers) `cablate/Claude-Code-Board` · MIT · **保守終了**（最終更新 2026-01）。

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
