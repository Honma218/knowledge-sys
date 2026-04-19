---
concept: ai-over-ai
aliases: [AI over AI, AIオーバーAI]
topics: [ai-llm]
first-cited: [[sources/techworld-2026-github-life-management]]
---

# AI over AI

## 定義

**あるAIの出力をもう一つのAIの入力として使い、LLM同士を多段階でパイプライン化して作業を自動化するパターン**の呼称。[[hand_dot]] が対談中で `「AI オーバー AI みたいな」` と呼んだのが直接の出典。特定のフレームワーク名ではなく、運用上の発想を指すフレーズ。

## なぜ重要か

- 単一LLMに「情報収集から整理・Issue化・記事化まで」全部やらせると、どこかで破綻する（コンテキスト長・ハルシネーション・コスト）
- **役割分担**: 下位のAI（例: Gemini）に情報の収集・スクレイピング・生データ処理をさせ、上位のAI（例: Claude Code）に解釈・判断・生成を任せる
- **検証レイヤーの挿入**: 一方のAIの出力を別のAIにレビューさせることで、品質を底上げする運用も含まれる（動画では明示されていないが、同パターンの派生）

## hand_dot の具体例

- **過去の YouTube 発言の全取り込み**: Claude Code に Gemini を呼び出させ、過去動画のテキストを全部取らせる。出力された素材を Portfolio/YouTube ディレクトリに格納し、そこから他のSkill（記事化、企画考案など）が参照する
- **Agent Memory → Issue 自動発行**: Agent Memoryが過去の会話・壁打ちを保持 → Claude が「Issue化できそうなもの」を判断 → [[life-repository]] に実際のIssueとして起票

## 関連概念

- [[concepts/claude-skills]] — AI over AI の各段を Skill 化することで再利用可能に
- [[concepts/agent-memory]] — 中間記憶レイヤーとして AI over AI を成立させる要素
- [[concepts/life-repository]] — AI over AI が生成する成果物の格納先

## ソース

- [[sources/techworld-2026-github-life-management]] — 26分台、Gemini に情報取得させてClaude Codeに処理させる文脈で言及

## 実例・事例

- hand_dot: Claude Code × Gemini × Agent Memory の三段構成
- （類推）本wikiでも、WebFetchが失敗したときに Claude in Chrome（別LLM／ブラウザエージェント）で取得し、Claudeが処理する構図は同じパターンに該当

## Open questions

- 「AI over AI」の信頼性低下ケース（誤りが増幅する／下位AIのバイアスが上位AIに伝播する）をどう検出・抑制するか
- 多段構成のコスト／レイテンシのトレードオフと、どの段を「キャッシュ化」すべきかのパターン
- 専門フレームワーク（LangChain, CrewAI, Agno, etc.）との対応関係
