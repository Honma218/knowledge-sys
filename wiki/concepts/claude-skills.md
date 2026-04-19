---
concept: claude-skills
aliases: [Claude Skills, スキル, Claude Skill]
topics: [ai-llm]
first-cited: [[sources/techworld-2026-github-life-management]]
---

# Claude Skills

## 定義

Anthropic Claude における **再利用可能な手順書＋リソースのパッケージ**。1つのフォルダに `SKILL.md`（YAML frontmatter と Markdown 本文）を置き、必要に応じて `references/`・`scripts/`・`assets/` を同梱する。Claude は `description` フィールドで起動判断し、必要なときだけ本文を読み込む **Progressive Disclosure** モデル。スラッシュコマンドのように `/skill-name` で呼び出せる実装もある。

## なぜ重要か

- **CLAUDE.md の "外出し" と再利用**: プロジェクト個別の指示を飛散させず、ドメイン知識＋手順を一つの単位にパッケージ化できる
- **ナレッジワーカーのワークフロー自動化**: 情報収集・記事執筆・ファイル整理など、繰り返し発生する仕事を Skill として固定化することで LLM を「毎回説明する相手」から「仕込み済みの同僚」に変えられる
- 本wiki で使っている [[llm-wiki]] Skill自身が例

## 設計上の勘所（[[hand_dot]] の主張）

- **CLAUDE.md（≒ SKILL.md 本体）は 300行以下に抑える**
  > 入れれば入れるほどバカになる。平坦になる、発散する、うまくコンテキスト読み込めない — [[sources/techworld-2026-github-life-management]]
- チューニングには時間がかかる（hand_dot は2ヶ月）
- 他人のテンプレを真似するのは出発点としては良いが、自分の用途に合わせて大幅に書き換えるべき

## 関連概念

- [[concepts/life-repository]] — Skill を実行する舞台としての GitHub リポジトリ
- [[concepts/agent-memory]] — Skill 内から呼び出す長期記憶ツール
- [[concepts/ai-over-ai]] — Skill を多段連携させる運用パターン

## ソース

- [[sources/techworld-2026-github-life-management]] — 実運用例（`/ネタトレンド-デイリー`、X週次集約、ホームページ管理スキル等）と「300行以下」ルール

## 実例・事例

- hand_dot の `/ネタトレンド-デイリー` — 毎朝トレンドネタ／記事ネタを抽出する自作Skill
- Ryoji の [[llm-wiki]] — 本wikiのインジェスト／クエリ／リントを司るSkill

## Open questions

- `/ネタトレンド-デイリー` の中身公開（動画後半で約束されているので次のソースに期待）
- 「300行以下」は経験則か、定量的に検証された閾値か
- Skillのバージョニング・チーム共有のベストプラクティス
