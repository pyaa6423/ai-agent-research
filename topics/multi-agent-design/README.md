# マルチエージェントシステム設計

LLM ベースのマルチエージェントシステムの設計・アーキテクチャに関する論文・企業リソース・ブログ記事の調査まとめ。

---

## 学術論文

### Large Language Model based Multi-Agents: A Survey of Progress and Challenges (2024, IJCAI 2024)

- **著者:** Taicheng Guo et al.
- **URL:** https://arxiv.org/abs/2402.01680
- **概要:** LLM ベースマルチエージェントシステムの包括的サーベイ。エージェントのプロファイリング、通信メカニズム、能力拡張メカニズムなどの本質的側面を体系的に分析。複雑な問題解決とワールドシミュレーションにおける MAS の成果を整理。

### A Survey on LLM-based Multi-Agent System: Recent Advances and New Frontiers in Application (2024-2025)

- **URL:** https://arxiv.org/abs/2412.17481
- **概要:** LLM ベースマルチエージェントシステムの最新動向と応用のサーベイ。ワークフロー、インフラ、課題を 5 つの主要コンポーネント（プロファイル、知覚、自己行動、相互対話、進化）に体系化。

### A Survey on LLM-based Multi-Agent Systems: Workflow, Infrastructure, and Challenges (2024)

- **URL:** https://link.springer.com/article/10.1007/s44336-024-00009-2
- **概要:** LLM ベース MAS のワークフロー、インフラストラクチャ、課題を体系的にレビュー。プロファイル・知覚・自己行動・相互対話・進化の 5 要素で一般構造を合成。

### MetaGPT: Meta Programming for A Multi-Agent Collaborative Framework (2023, ICLR 2024 Oral)

- **著者:** Sirui Hong, Mingchen Zhuge et al.
- **URL:** https://arxiv.org/abs/2308.00352
- **概要:** 人間の SOP（標準作業手順書）を LLM ベースのマルチエージェント協調に組み込むメタプログラミングフレームワーク。アセンブリラインのパラダイムで各エージェントに異なる役割を割り当て、カスケードするハルシネーションを削減。コード生成ベンチマークで Pass@1 85.9%/87.7% の SoTA を達成。

### SALLMA: A Software Architecture for LLM-Based Multi-Agent Systems (2025)

- **著者:** Roberto Verdecchia et al.
- **URL:** https://robertoverdecchia.github.io/papers/SATrends_2025.pdf
- **概要:** LLM ベースマルチエージェントシステムのためのソフトウェアアーキテクチャ。ソフトウェア工学の観点から MAS の設計原則を体系化。

---

## 企業・業界リソース

### Anthropic — Building Effective AI Agents (2024-2025)

- **URL:** https://www.anthropic.com/research/building-effective-agents
- **概要:** エージェント設計のベストプラクティスガイド。「最も成功する実装はシンプルで構成可能なパターンを使う」という原則を提示。ワークフロー（事前定義されたコードパスで LLM とツールを調整）とエージェント（LLM が自律的にプロセスを指示）を区別し、6 つの構成可能なパターンを紹介。

### Anthropic — How We Built Our Multi-Agent Research System (2025)

- **URL:** https://www.anthropic.com/engineering/multi-agent-research-system
- **概要:** Anthropic のマルチエージェントリサーチシステムの構築方法。オーケストレータ-ワーカーパターンを採用し、Claude Opus 4 をリードエージェント、Claude Sonnet 4 をサブエージェントとして使用。単一エージェントに比べ 90% 以上の性能向上を達成。トークン使用量は通常チャットの約 15 倍。

### Microsoft Azure — AI Agent Orchestration Patterns (2024-2025)

- **URL:** https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns
- **概要:** Azure アーキテクチャセンターが提供する AI エージェントオーケストレーションのデザインパターンガイド。オーケストレータ-ワーカー、シーケンシャル、階層型などの主要パターンを解説。

### Google Cloud — Choose a Design Pattern for Your Agentic AI System (2025)

- **URL:** https://docs.cloud.google.com/architecture/choose-design-pattern-agentic-ai-system
- **概要:** エージェント型 AI システムのデザインパターン選定ガイド。要件に応じた最適なアーキテクチャの選択方法を解説。

### Google — Agent2Agent Protocol (A2A) (2025)

- **URL:** https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/
- **概要:** エージェント間通信のオープンプロトコル。HTTP、SSE、JSON-RPC などの既存標準上に構築。メモリ・ツール・コンテキストを共有しないエージェント同士が自然に協調可能。Anthropic MCP と相補的な位置づけ。50 社以上のパートナーが参加し、Linux Foundation に寄贈。

### OpenAI — Swarm (2024)

- **URL:** https://github.com/openai/swarm
- **概要:** 軽量マルチエージェントオーケストレーションの教育用フレームワーク。「Agent」と「Handoff」の 2 つの抽象化に焦点を当て、エージェント間の会話の引き継ぎをシンプルに実現。ステートレス設計で Chat Completions API を基盤とする。プロダクション用ではなく概念実証・学習目的。

---

## ブログ・技術記事

### LangGraph: Multi-Agent Workflows (LangChain, 2024)

- **URL:** https://blog.langchain.com/langgraph-multi-agent-workflows/
- **概要:** LangGraph によるマルチエージェントワークフローの設計方法。各エージェントをグラフのノード、エッジで制御フローを表現する DAG ベースのオーケストレーション。Supervisor パターンによるルーティング、単一/マルチ/階層型のフロー制御を一つのフレームワークで実現。

### マルチ LLM エージェントシステム（MLAS）のアーキテクチャ 4 分類 (Zenn, 2024-2025)

- **著者:** r_kaga
- **URL:** https://zenn.dev/r_kaga/articles/ebeba0bd1385e1
- **概要:** マルチ LLM エージェントシステムを 4 つのアーキテクチャ（シーケンシャル、グラフ型等）に分類して解説。日本語で体系的に MAS の設計を学べる記事。

### マルチ AI エージェントの概念とアーキテクチャ設計の考え方 (Qiita, 2024-2025)

- **著者:** ShuAsahi
- **URL:** https://qiita.com/ShuAsahi/items/3734dae9ceddf2b9d74a
- **概要:** マルチ AI エージェントの基本概念からアーキテクチャ設計の考え方までを解説。タスク・役割の細分化による精度向上と、レスポンス時間・コストとのトレードオフについて考察。

### LLM エージェントのデザインパターン完全ガイド (OpenBridge, 2024-2025)

- **URL:** https://www.openbridge.jp/column/llm-agent-design-patterns
- **概要:** Andrew Ng 氏が提唱した Agentic Design Patterns を基に、Reflection、Tool Use、Planning、Multi-Agent Collaboration の 4 パターンを日本語で詳細に解説。

### Comparing Open-Source AI Agent Frameworks (Langfuse, 2025)

- **URL:** https://langfuse.com/blog/2025-03-19-ai-agent-comparison
- **概要:** AutoGen、CrewAI、LangGraph など主要なオープンソース AI エージェントフレームワークを比較。各フレームワークの特徴と適用場面を分析。

---

## 主要オーケストレーションパターン（まとめ）

| パターン | 説明 |
|---|---|
| **オーケストレータ-ワーカー** | 中央のオーケストレータがタスク分解・割り当て・結果集約を行う（最も一般的） |
| **シーケンシャル/パイプライン** | エージェントを直列に連鎖、前段の出力が後段の入力 |
| **階層型** | ツリー構造で委任、大規模（50+ エージェント）向き |
| **スウォーム/メッシュ** | 分散型の P2P 通信、創発的協調 |
| **スーパーバイザー** | 上位エージェントが次に行動するエージェントを動的決定 |
