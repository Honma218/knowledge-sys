---
idea: "Notion を離れて GitHub × Claude Code で「人生のOS」を組み直した話"
status: seed
target-length: 3000〜5000字
target-venue: zenn
created: 2026-04-19
updated: 2026-04-19
topics: [ai-llm, software-dev]
seeds:
  - [[sources/techworld-2026-github-life-management]]
---

# Notion を離れて GitHub × Claude Code で「人生のOS」を組み直した話

> Zenn / note 向け、3000〜5000字。**先行者 [[hand_dot]] の実践を紹介しつつ、Ryoji 自身の本wiki構築体験と重ね合わせる二層構造で書く**のが独自性の核。

## 想定読者

- Notion ヘビーユーザーで、LLM 時代のナレッジ運用にモヤモヤしている開発者
- Claude Code / Claude Skills を触り始めていて、具体的な運用パターンを探している人
- 個人の「セカンドブレイン／PKM」を次の土台に移そうと検討中の人
- 対象トピック: [[topics/ai-llm]], [[topics/software-dev]]

## 主張（Hook）

**LLM時代の個人知識管理は、「AIに優しいデータ形式（= Markdown + Git）」と「AIが動ける場所（= リポジトリ）」に寄せるほど、日々の運用が楽になる。** Notion の綺麗なUIより、GitHub の素朴さ＋ Claude Code の "なんでもやる" 能力の方が、結果として自分専用のOSに近づく。

先行事例として [[hand_dot]] の life リポジトリがあり、自分（Ryoji）もそれに触発されて本wiki を作ってみた。**2人の運用を対比しながら、共通する設計原則を抜き出す**記事にする。

## なぜ今書くか

- Claude Code / Claude Skills が一般の開発者層にも浸透しつつあるタイミング
- Notion AI の不満（API での自動化しにくさ、AIが使いづらい）が顕在化している
- 2026年1月に TECH WORLD で [[sources/techworld-2026-github-life-management|この動画]] が公開され、Xでも話題に。鮮度が残っているうちに便乗する

## 目次案

1. **導入: Notion を抜け出したくなる瞬間**（300字）
   - Notion AIへの課金ためらい、APIの使いづらさ、LLMと噛み合わない体験
2. **先行者の実例: hand_dot の life リポジトリ**（800字）
   - `Portfolio / Ideas / Publications / YouTube` 構成
   - Notion → GitHub 移行を Claude Code で36 Issueを一括化した話
   - メディアミックス（`Ideas/Daily → X → Ideas/Weekly → Publications`）
3. **自分も作ってみた: Obsidian Vault 上の Markdown wiki**（1000字）
   - 本wiki の構造（`raw/` 生ソース、`wiki/` LLM生成、`CLAUDE.md` スキーマ）
   - [[llm-wiki]] スキルを作って ingest / query / lint をオペレーション化した
   - GitHubに同期して git で履歴を残す
4. **共通する設計原則**（1000字）
   - **原則1: LLMに優しい形式（Markdown + Git）に寄せる** → [[concepts/life-repository]]
   - **原則2: Skill / CLAUDE.md は薄く保つ（300行以下）** → [[concepts/claude-skills]]
   - **原則3: 中間記憶レイヤーを置く** → [[concepts/agent-memory]]
   - **原則4: 多段AI（AI over AI）で役割分担する** → [[concepts/ai-over-ai]]
5. **まだ解けていない問題**（500字）
   - プライベート情報の分離
   - チーム共有（タグ・スコープ分け）
   - CLAUDE.md 肥大化の管理
6. **まとめ: 2ヶ月かけて育てるもの**（300字）
   - hand_dot も「2ヶ月かけて組み上げた」と言っている。自分もまだ1日目。wikiは"書く"のではなく"育てる"もの

## 素材

### 根拠／引用できるソース

- [[sources/techworld-2026-github-life-management]]
  - Chapter 2: Notion→GitHub 移行（CSV + Claude Code + `gh`）
  - Chapter 4-5: GitHub を選んだ理由、メリット／デメリット
  - Chapter 7: 管理するディレクトリ構造
  - Chapter 10: CLAUDE.md 300行ルール、2ヶ月の制作期間
  - Chapter 14: Agent Memory による Issue 自動起票

### 引用できる具体例

- hand_dot が自動音声認識ベースで語った **「これ入れれば入れるほどバカになる、平坦になる」** の引用（書き言葉に整えて使う）
- Ryoji 自身の wiki 初期設定ログ（`log.md`）を具体のスクショ候補に
- GitHub 上の `knowledge-sys` リポジトリ構造（本wiki）

### 図解ネタ

- 2枚比較図: 「Notion時代」vs「GitHub+LLM時代」のデータの流れ
- hand_dot のメディアミックスファネル図: `Daily → Weekly → Publications`
- 本wikiの三層アーキテクチャ図: `raw/` → `wiki/` → `CLAUDE.md（スキーマ）`

## 自分の立場・独自視点

- 動画は「ゲストすげぇ」で終わりがち。独自性は **「自分も追試した」** 部分に全振りする
- 技術書や論文のように "引用して終わり" ではなく、**同じ道を辿った自分の設計判断と躓き** を見せる
- [[llm-wiki]] Skillを実際に作ったことで、hand_dot が 2ヶ月かけた領域を1日で雛形まで持っていけた／それでも残る課題は何か、という **「先行事例に立つLLMネイティブ世代」** のスタンスで書く
- 反対意見として **「全部GitHubに乗せると逆に壊れるケース」**（セキュリティ、バックアップ、チーム連携）も扱う

## 関連トピック

- [[topics/ai-llm]]
- [[topics/software-dev]]
- 関連概念: [[concepts/life-repository]], [[concepts/claude-skills]], [[concepts/agent-memory]], [[concepts/ai-over-ai]]

## メモ

- hand_dot の Zenn 元記事（2021）と本動画（2026）の **4年間の変遷** も短いコラムとして挟めそう：2021 は GitHub だけ、2026 は Claude Code が主役化
- この記事を書くこと自体が、本wikiの「Ideas → Publications」ファネルのパイロットケース。書きながら wiki の運用を磨ける
- 派生アイデア:
  - **「Claude Skill の CLAUDE.md は 300行以下に抑えるべき理由」** 単体の技術記事（もっと短く、Qiita向き）
  - **「LLM時代のPKMツール比較: Notion / Obsidian / GitHub / 本wiki型」** の比較記事
