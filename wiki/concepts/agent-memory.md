---
concept: agent-memory
aliases: [Agent Memory, エージェントメモリー]
topics: [ai-llm]
first-cited: [[sources/techworld-2026-github-life-management]]
---

# Agent Memory（エージェントメモリー）

## 定義

LLM エージェントに**セッションをまたいだ永続記憶を持たせるための外部ツール／ライブラリの総称**。本wikiでは特に、動画内で言及されている「山田しさん」（詳細不明）が開発したツールを指す固有名として扱う。過去の会話・アイデア・メモを蓄積し、Claude Code 等のエージェントから参照・検索できるようにする。

## なぜ重要か

- [[hand_dot]] の運用では「Issue を立てる粒度」を人間が判断するのではなく、Agent Memory に「今まで貯めている間で1本立てられそうなのある？」と聞いて Claude が自動で Issue 化する方式をとっている。**認知負荷の削減**と **過去コンテキストの忘却防止** の両立
- 本wiki のような PKM でも、短期の Claude セッションと長期の wiki の間に **中間記憶層** を置く設計思想は参考にできる
- [[concepts/ai-over-ai]] の中核レイヤーの一つ

## 関連概念

- [[concepts/claude-skills]] — Agent Memory を呼び出す側として
- [[concepts/life-repository]] — Agent Memory が自動生成した Issue の格納先
- [[concepts/ai-over-ai]] — Gemini ＋ Claude ＋ Agent Memory の多段構成

## ソース

- [[sources/techworld-2026-github-life-management]] — Agent Memory に「1本立てられそうなものある?」と聞いてIssue化してもらうワークフローの実演、過去会話のディテール書き込みにも言及

## 実例・事例

- hand_dot が [[life-repository]] で Issue 発行に Agent Memory を使用
- （比較）本wiki は現状 Agent Memory を使わず、`index.md` + `log.md` + Claude のセッションコンテキストで代替している。今後スケール時には検討候補

## Open questions

- 「山田しさん」の Agent Memory の具体的な実装（OSS？商用？）とアクセス方法
- 他の長期記憶ソリューション（Mem0, Letta, Zep, etc.）との違い／位置付け
- wiki（本wikiのような永続ドキュメント）と Agent Memory は同居させるべきか、どちらかに寄せるべきか
