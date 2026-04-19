# Log

時系列で wiki の更新履歴を記録します。`grep '^## \[' log.md | tail -N` で直近のエントリを一覧できます。

---

## [2026-04-19] setup | Wiki created

- Domain: Research（仕事・実務ナレッジ向けにカスタマイズ）
- Root: `C:\Users\ryoji\OneDrive\ドキュメント\Obsidian Vault\knowledge`
- Template: research.md（multi-topic・ideas フォルダ追加でカスタマイズ）
- 主要トピック: AI/LLM、ソフトウェア開発・アーキテクチャ、プロダクトマネジメント・ビジネス
- Link style: Obsidian 標準 `[[Page Name]]`
- 言語: 本文は日本語、frontmatter・ファイル名は英語
- 主要アウトプット: ブログ・Zenn・Qiita 記事のネタ帳（`wiki/ideas/`）
- 作成ファイル: [[CLAUDE]], [[index]], log.md
- 作成フォルダ: raw/{articles, papers, books, talks, assets}, wiki/{sources, topics, concepts, entities, ideas, synthesis}

## [2026-04-19] ingest | 【Notion脱却】外資ITエンジニアが実践するGitHubで人生を管理する方法

- Source: [[sources/techworld-2026-github-life-management]]
- Raw: raw/talks/techworld-2026-github-life-management.md（YouTube 27:22、[[TECH WORLD]] × [[hand_dot]] 対談、2026-01-30公開、ブラウザ経由で取得した自動音声認識ベースの文字起こしを収録）
- Topics: [[topics/ai-llm]]（初エントリ）, [[topics/software-dev]]
- 新規エンティティ: [[entities/hand_dot]], [[entities/tech-world]]
- 新規コンセプト: [[concepts/life-repository]], [[concepts/claude-skills]], [[concepts/agent-memory]], [[concepts/ai-over-ai]]
- 新規トピックハブ: [[topics/ai-llm]]
- 記事ネタ: [[ideas/github-for-life-notebook]]（seed、Zenn向け3000〜5000字、本wiki自身との類似性を独自視点に）
- 矛盾/論点: まだ他ソースなし（本wiki最初のingestのため）
- Follow-ups: hand_dot の `/ネタトレンド-デイリー` Skill 中身が後続動画で公開予定、要ingest。また関連動画 https://youtu.be/wNLE7rQDLN0 、原典 Zenn 記事 https://zenn.dev/hand_dot/articles/85c9640b7dcc66 も未ingest
- 取得メモ: YouTube / Zenn が egress proxy でブロックされたため Claude in Chrome 経由でブラウザ取得。文字起こしパネル（`ytd-engagement-panel-section-list-renderer`）から 16,564 文字を抽出
