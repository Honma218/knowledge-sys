---
concept: life-repository
aliases: [lifeリポジトリ, GitHubで人生を管理する, GitHub for Life Management]
topics: [ai-llm, software-dev, pm-business]
first-cited: [[sources/techworld-2026-github-life-management]]
---

# Life Repository（ライフリポジトリ）

## 定義

**仕事・家庭・発信活動・学習・タスク・イベントなど、人生のあらゆる対象を単一の GitHub リポジトリとそのIssues/Projectsで一元管理する運用パターン**。元々は [[hand_dot]] が2021年ごろにZennで提唱（[原記事](https://zenn.dev/hand_dot/articles/85c9640b7dcc66)）。単なる To-Do 管理ではなく、ポートフォリオ・執筆台本・情報収集ログ・発信ネタまでを包含する「人生のOS」としてのリポジトリ設計を指す。

## なぜ重要か

- **コンテキストスイッチングの排除**: 仕事リポジトリだけ見ていると他プロジェクト（副業・家庭・学習）への注意が落ちるが、同じレイヤーに全部乗せることで注意配分が均等化される
- **LLMと相性がいい**: Markdown + Issue + ファイル構造という素朴な形式が [[Claude Code]] やClaude Skillsとの親和性が高く、Notion 等のクローズドなDBより LLM に操作させやすい
- **資産化**: 4年単位の履歴が残り、自分自身についての「誰よりも詳しいデータベース」として問い合わせ対応・自己紹介・執筆ネタに使える

## 構成パターン（hand_dot 版）

主要ディレクトリ：

- **Portfolio** — 職歴・登壇履歴・制作物リスト。問い合わせ対応の一次ソース
- **技術書** — 執筆中の技術書の台本・参考資料
- **Ideas/Daily** — 日々のアイデアメモ、X投稿候補
- **Ideas/Weekly** — 1週間の投稿・反応を集約して次のアクションにつなぐバッファ
- **Publications** — ホームページ・note・YouTube に発信したものの管理
- **YouTube** — 過去の動画で話した内容を Gemini ＋ Claude Code で全テキスト化した資産

## 関連概念

- [[concepts/claude-skills]] — life リポジトリを「動かす」のは自作の Claude Skill 群
- [[concepts/agent-memory]] — Issue 発行の判断は Agent Memory に委ねる
- [[concepts/ai-over-ai]] — 多段AI自動化で情報を回すレイヤーの話
- [[メディアミックス]] — Ideas → X → Publications → 動画／記事 の循環構造（_将来独立ページにする候補_）

## ソース

- [[sources/techworld-2026-github-life-management]] — 実運用の具体像、Notion移行の手順、CLAUDE.md 300行ルール、Issue粒度の判断基準など

## 実例・事例

- [[hand_dot]] の `life` リポジトリ（4年以上運用）
- Ryoji の本wiki — 同じ発想を Obsidian Vault 上で再実装している

## Open questions

- プライベート／機密の扱い（OneDrive/Obsidian/private GitHub/ローカル の使い分け）
- チームプレイへの拡張（現状は個人運用が前提）
- 「300行上限」の根拠と、大規模化時のCLAUDE.md 分割パターン
