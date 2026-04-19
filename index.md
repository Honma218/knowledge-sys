# Index — Ryoji の仕事・実務ナレッジベース

このファイルは wiki 全体のカタログです。新しいページを作ったり大幅に更新したら、ここに反映してください。LLM は毎回まずこのファイルを読んでから作業します。

---

## Meta

- **開始日**: 2026-04-19
- **ドメイン**: Research（仕事・実務ナレッジ向けにカスタマイズ）
- **主要トピック**: AI/LLM、ソフトウェア開発・アーキテクチャ、プロダクトマネジメント・ビジネス
- **主要アウトプット**: ブログ・Zenn・Qiita 記事のネタ帳
- **スキーマ**: [[CLAUDE]]
- **取り込んだソース**: 1
- **wiki ページ総数**: 10（topic 1, entity 2, concept 4, source 1, idea 1, index/log 省く）

---

## Topics（トピックハブ）

3つの主要領域。すべてのソース・概念・人物はいずれかのトピックに紐づく。

- [[topics/ai-llm]] — AI / LLM / 生成AI（Claude Code / Skills、PKMにおけるLLM活用など）
- [[topics/software-dev]] — ソフトウェア開発・アーキテクチャ（_ハブ未作成、関連ソースが増えたら作成_）
- [[topics/pm-business]] — プロダクトマネジメント・ビジネス（_ハブ未作成、関連ソースが増えたら作成_）

---

## Ideas（記事ネタ帳） — 主要アウトプット

本 wiki の最大の価値はここに溜まる。ソースを読む中で思いついた記事アイディアを蓄積。

<!-- status: seed / drafting / ready / published -->

- **seed** [[ideas/github-for-life-notebook]] — Notion を離れて GitHub × Claude Code で人生のOSを組み直す話（Zenn向け、3000〜5000字）

---

## Sources（取り込んだソース）

### AI / LLM / 生成AI

- 2026-04-19: [[sources/techworld-2026-github-life-management]] — 【Notion脱却】外資ITエンジニアが実践するGitHubで人生を管理する方法（TECH WORLD × [[hand_dot]]、YouTube対談、27分）

### ソフトウェア開発・アーキテクチャ

_まだありません。_

### プロダクトマネジメント・ビジネス

_まだありません。_

---

## Concepts（概念・フレームワーク・パターン）

- [[concepts/life-repository]] — 人生のあらゆる対象を単一のGitHubリポジトリで管理する運用パターン
- [[concepts/claude-skills]] — Claude の再利用可能な手順書／知識パッケージ。CLAUDE.md は 300行以下が目安
- [[concepts/agent-memory]] — LLMエージェントに永続記憶を与える外部ツール（山田し氏開発と言及）
- [[concepts/ai-over-ai]] — AIの出力を別のAIの入力にする多段自動化パターン

---

## Entities（人物・企業・ツール・プロダクト）

- [[entities/hand_dot]] — 外資ITエンジニア、「GitHubで人生を管理する」2021年Zenn記事の著者、lifeリポジトリ運用者
- [[entities/tech-world]] — 株式会社テックワールド／YouTubeチャンネル（登録12.4万人）

---

## Synthesis（横断的分析・考察）

_まだありません。10本くらいソースが溜まると、横断的な分析ページを書くと有用になります。_

---

## 運用メモ

- Ingest: 新しい記事・論文などを `raw/` に置き、「これを取り込んで」と指示する
- Query: 「wikiでXについてどう語られている？」「Yに関する記事ネタある？」と問える
- Lint: 10ソースごと、または月1ペースで「健全性チェックして」と指示する
- 詳細な規約は [[CLAUDE]] を参照
