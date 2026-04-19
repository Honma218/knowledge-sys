---
title: 【Notion脱却】外資ITエンジニアが実践するGitHubで人生を管理する方法
authors: [TECH WORLD, 市川達大, 京平 (hand_dot)]
year: 2026
type: talk
venue: YouTube / TECH WORLD チャンネル
url: https://www.youtube.com/watch?v=KHiq6nf0Jio
raw: raw/talks/techworld-2026-github-life-management.md
ingested: 2026-04-19
topics: [ai-llm, software-dev]
tags: [github, notion, claude-code, claude-skills, life-management, note-taking, knowledge-management, pkm, obsidian-alternative]
duration: 27m22s
related:
  - https://zenn.dev/hand_dot/articles/85c9640b7dcc66
  - https://youtu.be/wNLE7rQDLN0
---

# 【Notion脱却】外資ITエンジニアが実践するGitHubで人生を管理する方法

## 一行サマリー

外資ITエンジニア [[hand_dot]] が Notion を離れて、自分専用の "life" GitHub リポジトリ＋ [[Claude Code]] ＋ [[Claude Skills]] の組み合わせで、人生のタスク・情報収集・発信活動をすべて一元管理しているワークフローを、[[TECH WORLD]] の聞き手 [[市川達大]] との対談形式で具体的に実演した動画。

## 要約

[[hand_dot]]（Zennで2021年に「GitHubで人生を管理する」を公開）は、Notion に一時移行したものの最近 GitHub に出戻り、`life` リポジトリを4年以上運用している。移行は Notion のカンバンビューから CSV をエクスポートし、[[Claude Code]] に `gh` コマンドで Issue 36個を一括生成させて完了した。管理する情報は仕事タスク・登壇履歴・ポートフォリオ・技術書執筆の台本・X の投稿集約・noteの記事ネタなど多岐にわたり、ディレクトリが `Portfolio / 技術書 / Ideas / Publications / YouTube` に分かれている。情報収集は `/ネタトレンド-デイリー` という自作 [[Claude Skills]] で毎朝取り込み、Xで呟き→反応→まとめ→publications と [[メディアミックス]] で循環させる。Issue 化は [[Agent Memory]]（山田しさん開発）に「貯まってる話題で1本立てられそうなのある？」と聞き、Claude が自動で Issue 化する [[AI over AI]] 運用。CLAUDE.md（Skillの指示書）は **300行以下に抑えるべき**、入れすぎると「平坦になる／発散する／コンテキストを読めない」と明言。Notion 移行の動機は「AIが使いづらい（金を払ってまで使いたくない）」「使うツールを狭くしたい／断捨離」。

## キーポイント

- **"life" リポジトリ** が中心概念。[[ライフリポジトリ]] に人生のタスク・イベント・情報すべてを集約する
- **Notion → GitHub 移行は Claude Code + `gh` で一括**。カンバンのCSVを渡して「Issue化して」と言うだけ。36 Issue を一気に作成
- **コンテキストスイッチングの排除**がGitHub採用の最大メリット。仕事・副業・家庭・発信を別ツールに分けない
- **メディアミックス構造**: `Ideas/Daily → X投稿 → 反応集約 → Ideas/Weekly → note/YouTube → Publications` という発信ファネル
- **[[Claude Skills]] の CLAUDE.md は 300行以下**。「これ入れれば入れるほどバカになる、平坦になる、発散する、コンテキスト読めない」
- **[[Agent Memory]] に Issue 発行を委ねる** — 人間が粒度に悩まず、AIが過去の文脈込みで Issue を起票
- **[[AI over AI]]** — Gemini に情報収集させ、Claude Code にそれを処理させる多段構造
- **デメリット**: チームプレイは未解決。「スコープを分けて共有」（タグ・ラベル運用）が理想だが現状は個人運用
- CLAUDE.md 整備には **2ヶ月**かけた、誰かのテンプレを真似しても合わないので自分で育てるべき

## 実務への示唆

- **Ryoji の知識wiki（本wikiそのもの）との強い類似性**: 本wikiの CLAUDE.md も同じ発想で「LLMが維持する長期記憶」を目指している。この動画の knowhow（特に 300行上限、メディアミックス構造、Agent Memory でIssue化）は本wikiの運用改善にそのまま効く
- **ネタ帳運用のプラクティス**として、本wikiの `wiki/ideas/` は hand_dot の `Ideas/Daily` → `Ideas/Weekly` → `Publications` ファネルを参考にできる
- **Claude Skills 活用の具体例**として貴重。本wikiの `llm-wiki` スキル自身と同じ土俵の話
- 「GitHub で人生を管理する」というコンセプト自体が記事ネタとして強い（[[ideas/github-for-life-notebook]] へ展開）

## 引用

> "これ入れれば入れるほどバカになるっていうか、平坦になる。発散、うまくコンテキスト読み込めない" — 19分台、CLAUDE.md の肥大化について（自動音声認識からの書き起こし、ただし趣旨は正確）

> "これを組み上げんのに俺2ヶ月ぐらい要してるから" — 20分台、Skillの設計にかかる時間

> "AIオーバーAIみたいな" — 26分台、Gemini ＋ Claude Code の多段自動化を指して

## Connections

- **トピック**: [[topics/ai-llm]] — Claude Code / Claude Skills の実運用例、[[topics/software-dev]] — GitHub と gh CLI の開発者向け活用
- **補強する概念**: [[concepts/life-repository]], [[concepts/claude-skills]], [[concepts/agent-memory]], [[concepts/ai-over-ai]]
- **関連人物・チャンネル**: [[entities/hand_dot]], [[entities/tech-world]]
- **矛盾する主張**: まだ他ソースなし（本wiki最初のソース）
- **Open Questions**:
  - プライベート情報を含むGitHub運用でのセキュリティ・バックアップ戦略は？
  - チームプレイでの「スコープ分け共有」の現実的な実装（タグ・ラベル・フォークの運用）はどうあるべきか？
  - hand_dot の `/ネタトレンド-デイリー` スキルの中身・再現実装は？（動画後半で公開予定と言及あり）

## 記事ネタ候補

- [[ideas/github-for-life-notebook]] — 主要アウトプット候補。本wiki自身との類似体験記として書ける
- （派生）「Notion から脱出して LLM 時代のPKMを作る」系の比較記事
- （派生）「Claude Skills の CLAUDE.md は 300行以下、2ヶ月かけて育てる」系のSkill設計論
