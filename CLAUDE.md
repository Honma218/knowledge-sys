# Wiki Schema — Ryoji の仕事・実務ナレッジ

このファイルは LLM（Claude）向けの指示書です。`llm-wiki` スキルはこの wiki を更新するとき、必ず最初にこのファイルを読んでから作業を始めてください。ここに書かれた規約はテンプレートの汎用ルールより優先されます。

---

## Purpose（目的）

Ryoji の仕事・実務で得た知識を蓄積するための個人ナレッジベース。AI/LLM、ソフトウェア開発・アーキテクチャ、プロダクトマネジメント／ビジネスの3領域を横断的に扱う。読んだ記事・論文・書籍・動画を wiki に取り込み、概念・人物・ツール・パターンを交差参照しながら、**ブログや記事執筆のネタ帳**として機能させることがこの wiki の最終目的。

**これは学術研究 wiki ではなく実務ナレッジ wiki である**ことに注意。単一の "thesis" は持たず、複数トピックの横断的な知識をゆるく結び付ける形を取る。

## 対象領域（Topics）

以下の3つが主要トピック。取り込んだソースは最低1つ、できれば複数のトピックにリンクされるべき。

- **AI / LLM / 生成AI** — `wiki/topics/ai-llm.md`
- **ソフトウェア開発・アーキテクチャ** — `wiki/topics/software-dev.md`
- **プロダクトマネジメント・ビジネス** — `wiki/topics/pm-business.md`

どのトピックにもきれいに入らない場合は、まず既存トピックに寄せるか、ユーザーに相談してから新トピックを作る。軽々しく増やさない。

## Output（アウトプットの目的）

このwikiは最終的に **ブログ・Zenn・Qiita 記事のネタ帳** として機能させる。したがって：

- **`wiki/ideas/`** は本 wiki の主要アウトプット。ソースを読む中で「これは記事にできそう」「この切り口は面白い」と感じたら、即座に `wiki/ideas/<slug>.md` を作り、関連ソース・概念・目次案・想定読者を書き留める。
- ideas ページは**完成原稿ではなく、執筆のための走り書き**。粗くてよいが、いざ書き始めるときに十分な材料が揃っている状態にしておく。
- ingest のたびに「この内容は既存 idea のどれに追加されるか、新しい idea の種になるか」を意識する。

---

## Directory layout

```
knowledge/
├── CLAUDE.md          # このファイル（スキーマ・運用規約）
├── index.md           # 全ページのカタログ
├── log.md             # 時系列ログ（ingest / query / lint）
├── raw/               # 生ソース（読み取り専用・LLMは絶対に編集しない）
│   ├── articles/      # Web記事・ブログポスト
│   ├── papers/        # 論文・レポート・白書
│   ├── books/         # 書籍の章・読書メモ
│   ├── talks/         # 動画・ポッドキャスト（文字起こしまたは要約メモ）
│   └── assets/        # 図・スクリーンショット・添付画像
└── wiki/              # LLM が生成・保守するページ
    ├── sources/       # 取り込んだソースごとのサマリーページ
    ├── topics/        # トピックハブ（AI/LLM、Dev、PM）
    ├── concepts/      # 概念・フレームワーク・パターン・用語
    ├── entities/      # 人物・企業・ツール・プロダクト
    ├── ideas/         # ブログ/記事のネタ帳（本wikiの主要アウトプット）
    └── synthesis/     # 横断的な分析・考察・比較ページ
```

## Naming conventions

- **ファイル名**: kebab-case、拡張子 `.md`。日本語タイトルでも、ファイル名は半角英数ハイフンに変換する（例：「プロンプトエンジニアリング」→ `prompt-engineering.md`）。
- **ソースファイル**: `<著者かメディア>-<年>-<slug>.md`（例：`anthropic-2025-claude-agent-sdk.md`、`martin-fowler-2023-microservices.md`）。日本語ソースも同様のパターンで（例：`nikkei-2024-ai-regulation.md`）。
- **entity / concept / idea**: 単数形の kebab-case（例：`retrieval-augmented-generation.md`、`event-driven-architecture.md`）。
- **ページ内タイトル（H1）**: 原則として日本語で書く。読みやすさ重視。
- **frontmatter のキー**: 英語（title, authors, year, ingested, type, topics, tags）。

## Wiki-link style

**Obsidian 標準の `[[Page Name]]` 記法**を使う。

- リンク先は**表示名（日本語でOK）**を使ってよい。Obsidian は wiki 内で一意なファイル名に自動マッチする。例：`[[RAG]]`、`[[Claude Agent SDK]]`、`[[DDD]]`
- 曖昧さを避けたい場合はスラッシュ付きフルパス：`[[concepts/retrieval-augmented-generation|RAG]]`
- **相互リンクを厚めに**。新しいページを作ったら、既存の関連ページから逆向きリンクも張る（Obsidian のグラフビューを活かすため）。

## 言語方針

- **wiki 内の本文は日本語**が基本。
- frontmatter・ファイル名は英語（検索性とツーリング都合）。
- 英語の専門用語は日本語訳より原語を優先（例：「検索拡張生成」ではなく `RAG / Retrieval-Augmented Generation`）。初出時のみ併記。
- 引用の扱い：原文が英語の引用は原文と日本語要約の両方を残す。

---

## Page templates

### Source summary（`wiki/sources/<slug>.md`）

```markdown
---
title: <ソースタイトル>
authors: [<著者 or メディア>]
year: YYYY
type: article | paper | book-chapter | talk | podcast
venue: <出版元・媒体名>
url: <URL（あれば）>
raw: raw/articles/<filename>.md
ingested: YYYY-MM-DD
topics: [ai-llm | software-dev | pm-business]
tags: []
---

# <タイトル（日本語OK）>

## 一行サマリー
<なぜこのソースが重要か、1文で>

## 要約
<3〜8文の自然文。箇条書きではなく散文。元より十分短く。>

## キーポイント
- <ポイント1> — [[関連concept]] や [[関連entity]] へのリンク
- <ポイント2>
- ...

## 実務への示唆
<このソースから自分の仕事にどう活かせるか。idea の種になりそうなものは特に強調>

## 引用
> "<短い引用>" — (セクション or ページ)

## Connections
- 関連ソース: [[sources/...]]
- トピック: [[topics/ai-llm]]
- 補強する概念: [[concepts/...]]
- 矛盾する主張: [[sources/...]]（あれば）

## 記事ネタ候補
- [[ideas/<slug>]] への素材になるか？どう活かすか？
```

### Topic hub（`wiki/topics/<slug>.md`）

```markdown
---
topic: <topic-name>
updated: YYYY-MM-DD
---

# <Topic名>

## このトピックの問い
<今自分が追いかけている問い・関心を1〜3行で。更新可。>

## 重要概念
- [[concepts/...]] — 一言説明
- ...

## 注目している人・企業・ツール
- [[entities/...]] — 一言説明

## ソース（新しい順）
- YYYY-MM-DD: [[sources/...]] — 一行要約
- ...

## 考察・Synthesis
- [[synthesis/...]]

## 記事ネタ
- [[ideas/...]]

## Open questions
- まだ分かっていないこと、深掘りしたいこと
```

### Concept page（`wiki/concepts/<slug>.md`）

```markdown
---
concept: <name>
aliases: [<英語名、略称など>]
topics: [ai-llm | software-dev | pm-business]
first-cited: [[sources/...]]
---

# <概念名>

## 定義
<自分の言葉でまとめた1段落の定義。初出ソースを引用>

## なぜ重要か
<実務的な意義・関心。冷たい教科書的定義にしない>

## 関連概念
- [[concepts/...]] — どう違うか/どう関係するか

## ソース
- [[sources/...]] — 何を付け加えたか
- ...

## 実例・事例
- ...

## Open questions
- 未解決の論点や自分の疑問
```

### Entity page（`wiki/entities/<slug>.md`）

```markdown
---
entity: <name>
type: person | company | product | tool | lab
topics: [ai-llm | software-dev | pm-business]
---

# <Entity名>

## 概要
<どんな人・企業・ツールか1段落>

## このwikiでの位置付け
<なぜこのwikiにいるか。どんな文脈で重要か>

## 言及ソース
- [[sources/...]] — どう言及されたか
- ...

## 関連
- [[concepts/...]]
- [[entities/...]]
```

### Idea page（`wiki/ideas/<slug>.md`）**— 最重要テンプレ**

```markdown
---
idea: <記事タイトル案>
status: seed | drafting | ready | published
target-length: <想定文字数>
target-venue: blog | zenn | qiita | note | social | memo
created: YYYY-MM-DD
updated: YYYY-MM-DD
topics: [ai-llm | software-dev | pm-business]
---

# <記事タイトル案>

## 想定読者
<誰に向けて書くか。開発者、PM、経営層、一般など>

## 主張（Hook）
<記事の中核となる主張を1〜3文で>

## なぜ今書くか
<タイミング・鮮度・読者の関心>

## 目次案
1. 導入 — <...>
2. <...>
3. <...>

## 素材
- 根拠/引用できるソース: [[sources/...]]
- 引用できる具体例: <...>
- 図解ネタ: <...>

## 自分の立場・独自視点
<単なるまとめにならないための、自分の経験・切り口・反対意見>

## 関連トピック
- [[topics/...]]
- 関連概念: [[concepts/...]]

## メモ
<書き進める中で気づいたこと・未解決の論点>
```

### Synthesis page（`wiki/synthesis/<slug>.md`）

```markdown
---
type: synthesis
topics: [...]
updated: YYYY-MM-DD
---

# <テーマ>

## いまの見解（YYYY-MM-DD 時点）
<現時点でのまとめ・立場>

## 主な論点
1. ... — [[sources/...]] が支持
2. ...

## 緊張・矛盾
- <対立点>: [[source-a]] vs [[source-b]]

## 記事に発展しそうか？
- [[ideas/<slug>]] として切り出すか検討

## 変遷
- YYYY-MM-DD: <どう変わったか>
```

---

## Log entry format

`log.md` には以下の形式で追記する（`grep '^## \[' log.md` で一覧できるように）:

```markdown
## [YYYY-MM-DD] ingest | <ソースタイトル>
- Source: [[sources/<slug>]]
- Topics: [[topics/ai-llm]], ...
- 新規: [[concepts/...]], [[entities/...]]
- 更新: [[topics/...]], [[synthesis/...]]
- 記事ネタ: [[ideas/<slug>]]（新規 or 更新 or なし）
- 矛盾/論点: <あれば>
```

query を wiki に還流したときも：

```markdown
## [YYYY-MM-DD] query | <質問の短い表現>
- 生成: [[synthesis/<slug>]] or [[ideas/<slug>]]
- 参照: [[sources/...]], [[concepts/...]]
```

lint 実行時：

```markdown
## [YYYY-MM-DD] lint | <概要>
- Report: [[synthesis/lint-YYYY-MM-DD]]
- Fixed: <修正内容>
- Deferred: <保留した項目>
```

---

## Ingest workflow（この wiki 専用のカスタム版）

標準の ingest ワークフロー（`references/ingest.md`）に加えて、以下を必ず行う：

1. **Topic 判定を最初に行う**: ソースを読み始める前でも読みながらでも、`topics` frontmatter を決定する。複数可。3トピックのいずれにも該当しない場合は Ryoji に相談。
2. **`ideas/` を毎回チェック**: このソースは既存 idea を補強するか？新しい idea を立ち上げる価値があるか？を明示的に問う。idea は記事ネタ帳として wiki の主要アウトプット。
3. **Topic hub を更新**: 該当する `wiki/topics/<topic>.md` の「ソース」セクションに新しいエントリを追加。関連 concept / entity があれば hub 側のリストも更新。
4. **日本語で要約**: 英語ソースでも要約・連携情報は日本語で書く（引用は原文+訳）。
5. **Obsidian リンクを厚めに**: `[[Page Name]]` 形式で内部リンクを豊富に張る。単発のページを作ったら、必ず既存ページからも逆向きリンクを張る。

## Lint workflow（この wiki 特有）

標準ワークフローに加えて：

- **Idea 鮮度チェック**: `wiki/ideas/` で status が `seed` のまま長期間放置されているものを洗い出し、昇格 or アーカイブを提案。
- **Topic 偏りチェック**: 特定の topic にソースが集中/過疎していないか。足りない領域は追加の読書・視聴を提案。
- **引用源チェック**: 全ての `concepts/` `synthesis/` ページで「Sources」欄が空でないこと。

---

## Special notes

- **プライバシー**: 職場の機密情報（顧客名、社内プロジェクトコードネーム、個人を特定できる議論内容など）は記録しない。ソースに含まれていたら取り込み前にユーザーに確認する。
- **出典の尊重**: 記事ネタに流用するとき、必ず出典元を明記する。素材にした論文・記事がわかるように ideas ページで citations を管理。
- **git 運用**: このディレクトリは Obsidian Vault 内にある。git を使う場合はこのナレッジ用に独立リポジトリを作ることを推奨（Obsidian全体ではなく）。
- **Obsidian プラグイン想定**: Dataview（frontmatter クエリ）、Graph View、Backlinks、Web Clipper（raw/articles への取り込み）が便利。
