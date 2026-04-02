# Tool Use / Tool Calling for AI/LLM Agents

LLMエージェントにおける外部ツール利用（Tool Use / Function Calling）に関する論文・企業リソース・ブログ記事の調査まとめ。

---

## 1. Academic Papers（学術論文）

### 1-1. サーベイ論文

| # | Title | Authors / Organization | URL | Year | Summary |
|---|-------|----------------------|-----|------|---------|
| 1 | **Tool Learning with Large Language Models: A Survey** | Qu et al. / Springer Frontiers of Computer Science | [Springer](https://link.springer.com/article/10.1007/s11704-024-40678-2) / [arXiv](https://arxiv.org/abs/2405.17935) | 2024 | LLMによるツール学習の包括的サーベイ。ツール学習が有益である理由と、その実装方法（タスク計画・ツール選択・ツール呼び出し・応答生成の4段階）を体系的に整理。ベンチマークや評価手法も網羅的にレビューしている。 |
| 2 | **LLM-Based Agents for Tool Learning: A Survey** | Various / Springer Data Science and Engineering | [Springer](https://link.springer.com/article/10.1007/s41019-025-00296-9) | 2025 | LLMとツールを統合した「ツール学習エージェント」に焦点を当てたサーベイ。ツール学習エージェントのアーキテクチャ、学習手法、評価方法を体系的に整理し、今後の研究方向を提示。 |
| 3 | **A Review of Prominent Paradigms for LLM-Based Agents: Tool Use (Including RAG), Planning, and Feedback Learning** | Xinzhel et al. / CoLing 2025 | [GitHub](https://github.com/xinzhel/LLM-Agent-Survey) | 2025 | LLMエージェントの主要パラダイムであるツール利用（RAG含む）、計画、フィードバック学習を包括的にレビュー。CoLing 2025で発表。 |
| 4 | **A Survey on Large Language Model based Autonomous Agents** | Wang et al. / Frontiers of Computer Science | [arXiv](https://arxiv.org/abs/2308.11432) / [Springer](https://link.springer.com/article/10.1007/s11704-024-40231-1) | 2023-2025 | LLMベース自律エージェントの包括的サーベイ。プロファイル、メモリ、計画、行動（ツール利用含む）の各モジュールを体系的に整理。継続的にアップデートされている。 |
| 5 | **Tool learning with language models: a comprehensive survey of methods, pipelines, and benchmarks** | Various / Springer Vicinagearth | [Springer](https://link.springer.com/article/10.1007/s44336-025-00024-x) | 2025 | 言語モデルによるツール学習の手法、パイプライン、ベンチマークを包括的に調査。方法論の分類と定量的な比較評価を提供。 |

### 1-2. 基盤的論文（Foundational Papers）

| # | Title | Authors / Organization | URL | Year | Summary |
|---|-------|----------------------|-----|------|---------|
| 6 | **Toolformer: Language Models Can Teach Themselves to Use Tools** | Timo Schick et al. / Meta AI | [arXiv](https://arxiv.org/abs/2302.04761) | 2023 | LLMが自己教師あり学習でツールの使い方を自ら学習する手法を提案。どのAPIをいつ呼び出すか、どの引数を渡すか、結果をどう活用するかをモデル自身が判断。ゼロショット性能を大幅に向上させた先駆的研究。 |
| 7 | **TALM: Tool Augmented Language Models** | Parisi et al. / Google Research | [arXiv](https://arxiv.org/abs/2205.12255) | 2022 | ツール拡張言語モデルの初期的研究。テキストのみのアプローチで非微分可能なツールとLMを組み合わせ、反復的な「セルフプレイ」技術で少数のツールデモンストレーションからブートストラップする手法を提案。 |
| 8 | **ReAct: Synergizing Reasoning and Acting in Language Models** | Shunyu Yao et al. / Princeton, Google | [arXiv](https://arxiv.org/abs/2210.03629) | 2022 (ICLR 2023) | 推論（Reasoning）と行動（Acting）を交互に生成するフレームワーク。推論トレースがアクション計画の誘導・追跡・更新を助け、アクションが知識ベースなど外部ソースとのインターフェースを提供。LLMエージェントのツール利用パターンの基盤となった重要論文。 |
| 9 | **Gorilla: Large Language Model Connected with Massive APIs** | Shishir G. Patil et al. / UC Berkeley | [arXiv](https://arxiv.org/abs/2305.15334) / [Website](https://gorilla.cs.berkeley.edu/) | 2023 (NeurIPS 2024) | 大量のAPIとLLMを接続するためにファインチューニングされたモデル。Retriever Aware Training (RAT) により、ドキュメントの変更にも柔軟に対応し、API呼び出し時のハルシネーションを大幅に軽減。APIBenchベンチマークも提供。 |
| 10 | **HuggingGPT: Solving AI Tasks with ChatGPT and its Friends in Hugging Face** | Shen et al. / Microsoft, Zhejiang University | [arXiv](https://arxiv.org/abs/2303.17580) | 2023 (NeurIPS 2023) | ChatGPTをコントローラとして、Hugging Face上の多数のAIモデルをツールとして連携させるシステム。タスク計画→モデル選択→実行→結果要約の4段階パイプラインを提案。 |
| 11 | **ART: Automatic multi-step reasoning and tool-use for large language models** | Paranjape et al. / Stanford | [arXiv](https://arxiv.org/abs/2303.09014) | 2023 | タスクライブラリから多段推論とツール利用のデモンストレーションを自動選択し、中間推論ステップをプログラムとして自動生成するフレームワーク。手作業のCoTプロンプト作成を不要にした。 |

### 1-3. ベンチマーク論文

| # | Title | Authors / Organization | URL | Year | Summary |
|---|-------|----------------------|-----|------|---------|
| 12 | **API-Bank: A Comprehensive Benchmark for Tool-Augmented LLMs** | Li et al. / Alibaba Group | [arXiv](https://arxiv.org/abs/2304.08244) / [ACL Anthology](https://aclanthology.org/2023.emnlp-main.187/) | 2023 (EMNLP 2023) | ツール拡張LLMの包括的ベンチマーク。73のAPIツール、314のツール利用対話、753のAPIコール注釈を含む評価システムを提供。計画・検索・呼び出しの各能力を評価。 |
| 13 | **ToolBench / StableToolBench** | OpenBMB et al. | [GitHub](https://github.com/OpenBMB/ToolBench) | 2023-2024 (ICLR 2024 Spotlight) | 16,000以上のAPI、3,451ツールを含む大規模ベンチマーク。自動指示生成とDFSDTベースのソリューションパス注釈を特徴とし、126,000以上の指示-ソリューションパスペアを含む。 |
| 14 | **Berkeley Function Calling Leaderboard (BFCL)** | Patil et al. / UC Berkeley | [Website](https://gorilla.cs.berkeley.edu/leaderboard.html) / [ICML 2025](https://proceedings.mlr.press/v267/patil25a.html) | 2024-2025 | LLMの関数呼び出し能力を評価するデファクト標準ベンチマーク。AST評価手法を導入し、V1（基本評価）→V2（企業向け関数）→V3（マルチターン）→V4（エージェント的評価）と進化。 |

---

## 2. Corporate / Industry Resources（企業・業界リソース）

| # | Title | Organization | URL | Year | Summary |
|---|-------|-------------|-----|------|---------|
| 15 | **Tool use with Claude** | Anthropic | [Docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview) | 2024-2025 | Claude APIにおけるツール利用の公式ドキュメント。クライアントツール（ユーザーアプリ側で実行）とサーバーツール（Anthropicインフラで実行：web_search、code_executionなど）の2種類を定義。ツール定義、並列ツール利用、プロンプトキャッシングとの統合などを解説。 |
| 16 | **Introducing the Model Context Protocol (MCP)** | Anthropic | [Blog](https://www.anthropic.com/news/model-context-protocol) / [Spec](https://modelcontextprotocol.io/specification/2025-11-25) | 2024 | AIシステムと外部ツール・データソースの統合を標準化するオープンプロトコル。N×Mのデータ統合問題を解決し、JSON-RPC 2.0上で動作。OpenAI、Google DeepMindも採用し、デファクト標準に成長。Python、TypeScript、C#、Java向けSDKを提供。 |
| 17 | **Building Effective AI Agents** | Anthropic | [Blog](https://www.anthropic.com/research/building-effective-agents) | 2024 | エージェント構築のベストプラクティスを提示。複雑なフレームワークではなく、シンプルで組み合わせ可能なパターンを推奨。各ツールは明確で独立した目的を持つべきであり、高インパクトなワークフローに焦点を当てたツール設計を提唱。 |
| 18 | **Introducing advanced tool use on the Claude Developer Console** | Anthropic | [Blog](https://www.anthropic.com/engineering/advanced-tool-use) | 2025 | Tool Search Tool（数千のツールにコンテキストウィンドウを消費せずアクセス）、Programmatic Tool Calling（コード実行環境でのツール呼び出し）、Tool Use Examples（効果的なツール使用例の標準）の3機能を紹介。 |
| 19 | **Function Calling - OpenAI API** | OpenAI | [Docs](https://developers.openai.com/api/docs/guides/function-calling) / [Using Tools](https://developers.openai.com/api/docs/guides/tools) | 2023-2025 | OpenAI APIにおけるFunction Callingの公式ガイド。2023年6月に初導入。2024年にStructured Outputs（strict: true）を追加し、JSON Schema通りの引数生成を保証。Web検索、ファイル検索、コード実行、リモートMCPサーバーなど組み込みツールも提供。 |
| 20 | **Function Callingを利用する方法 - Azure OpenAI** | Microsoft | [Learn](https://learn.microsoft.com/ja-jp/azure/ai-foundry/openai/how-to/function-calling) | 2024-2025 | Azure OpenAI ServiceにおけるFunction Callingの公式ドキュメント（日本語）。Foundry Modelsでの関数呼び出しの実装方法を解説。 |

---

## 3. Blog Posts / Technical Articles（ブログ・技術記事）

| # | Title | Author / Organization | URL | Year | Summary |
|---|-------|----------------------|-----|------|---------|
| 21 | **Function calling using LLMs** | Kiran Prakash / Martin Fowler's Blog | [Blog](https://martinfowler.com/articles/function-call-LLM.html) | 2025 | LLMがFunction Callingを通じて外部システムと連携する仕組みを解説。LLM自体は関数を実行せず、関数名と引数をJSON形式で出力し、別プログラムが実行する点を明確に説明。ショッピングエージェントの実例やセキュリティ上の考慮事項も議論。 |
| 22 | **Building Autonomous AI Agents with Function Calling** | Towards Data Science | [Blog](https://towardsdatascience.com/build-autonomous-ai-agents-with-function-calling-0bb483753975/) | 2024 | Function Callingを使った自律型AIエージェントの構築方法を実践的に解説。OpenAIのFunction Calling APIを使ったステップバイステップのチュートリアル。 |
| 23 | **Function Calling and Tool Use: Turning LLMs into Action-Taking Agents** | DEV Community | [Blog](https://dev.to/qvfagundes/function-calling-and-tool-use-turning-llms-into-action-taking-agents-30ca) | 2024 | LLMをテキスト生成だけでなく、実際にアクションを起こすエージェントに変える方法を解説。Function CallingとTool Useの概念を平易に説明。 |
| 24 | **Function Callingとは？仕組みから実装方法まで完全解説** | fullfront.co.jp | [Blog](https://fullfront.co.jp/blog/technology-development/ai-development/function-calling-implementation-guide/) | 2025 | Function Callingの仕組みから実装方法までを日本語で完全解説。LLMがユーザーの入力から意図を解析し、事前定義された関数を呼び出す一連の流れを図解付きで説明。 |
| 25 | **AIエージェントのツール呼び出し: セキュアでインテリジェントな自動化を実現** | Auth0 (Okta) | [Blog](https://auth0.com/blog/jp-genai-tool-calling-intro/) | 2025 | AIエージェントのツール呼び出しにおけるセキュリティ面に焦点を当てた解説記事（日本語）。自律的な意思決定、タスク実行の最適化、スケーラビリティ、ユーザー体験の向上などの利点と、セキュアな実装方法を議論。 |
| 26 | **A Visual Guide to LLM Agents** | Maarten Grootendorst | [Newsletter](https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-llm-agents) | 2025 | LLMエージェントの仕組みをビジュアルに解説したガイド。ツール利用、メモリ、計画などの主要コンポーネントを図解で分かりやすく説明。 |

---

## 4. 関連フレームワーク・ツール（参考）

| Name | Organization | URL | Summary |
|------|-------------|-----|---------|
| **LangChain** | LangChain Inc. | [Docs](https://docs.langchain.com/) | LLMエージェント構築の代表的フレームワーク。標準化されたTool Callingインターフェースで、Anthropic、OpenAI、Google、Mistralなど多数のプロバイダーに対応。 |
| **LlamaIndex** | LlamaIndex | [Docs](https://docs.llamaindex.ai/) | データ接続とエージェント構築フレームワーク。Function Calling Agentワークフローを提供し、OpenAI・Anthropicの両方に対応。 |
| **Awesome Tool LLM** | Community (GitHub) | [GitHub](https://github.com/zorazrw/awesome-tool-llm) | ツール利用LLMに関する論文・リソースのキュレーションリスト。 |

---

## まとめ

LLMエージェントのツール利用は、以下の流れで急速に発展している：

1. **基盤研究期（2022-2023）**: TALM、Toolformer、ReActなどが、LLMに外部ツールを使わせる基本的なアプローチを確立
2. **API化・標準化期（2023-2024）**: OpenAI Function Calling（2023年6月）の導入を皮切りに、各社がAPI レベルでのツール呼び出し機能を標準装備
3. **プロトコル標準化期（2024-2025）**: AnthropicのMCP（Model Context Protocol）がN×M統合問題を解決するオープン標準として登場し、業界標準に成長
4. **エージェント実用化期（2025-2026）**: ベンチマーク（BFCL V4等）の成熟と、Programmatic Tool Callingなどの高度機能により、実用的なエージェントシステムが普及段階へ
