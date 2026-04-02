# AI/LLMエージェントの評価手法に関するリサーチ

調査日: 2026-04-02

---

## 1. 学術論文 (Academic Papers)

### 1-1. Evaluation and Benchmarking of LLM Agents: A Survey
- **著者/組織**: Mahmoud Mohammadi et al. (SAP, KDD 2025 Tutorial)
- **URL**: https://arxiv.org/abs/2507.21504
- **年**: 2025
- **概要**: LLMエージェント評価に関する包括的サーベイ。評価目的（エージェントの振る舞い・能力・信頼性・安全性）と評価プロセス（インタラクションモード・データセット/ベンチマーク・メトリクス計算方法・ツーリング）に沿った分類体系を提案。KDD 2025のチュートリアルとしても発表された。

### 1-2. Survey on Evaluation of LLM-based Agents
- **著者/組織**: 複数著者
- **URL**: https://arxiv.org/abs/2503.16416
- **年**: 2025
- **概要**: LLMベースエージェントの評価を4つの観点（基本能力：計画・ツール使用・自己反省・記憶、アプリケーション別ベンチマーク、汎用エージェント向けベンチマーク、評価フレームワーク）から分析した包括的サーベイ。Web・ソフトウェアエンジニアリング・科学・会話エージェントなど多領域をカバー。

### 1-3. AgentBench: Evaluating LLMs as Agents (ICLR 2024)
- **著者/組織**: Tsinghua University (THUDM)
- **URL**: https://arxiv.org/abs/2308.03688
- **年**: 2023 (ICLR 2024採択)
- **概要**: LLMをエージェントとして評価するための多次元ベンチマーク。8つの異なる環境（OS操作、データベース、ウェブブラウジングなど）でLLMの推論・意思決定能力を評価。商用トップLLMは複雑な環境で高い能力を示す一方、オープンソースモデルとの大きな格差が明らかになった。

### 1-4. AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents (ICLR 2025)
- **著者/組織**: Gray Swan AI et al.
- **URL**: https://arxiv.org/abs/2410.09024
- **年**: 2024 (ICLR 2025採択)
- **概要**: LLMエージェントの悪用リスクを測定するベンチマーク。11の有害カテゴリ（詐欺、サイバー犯罪、ハラスメント等）にわたる110の悪意あるタスク（拡張版440タスク）を収録。主要LLMはジェイルブレイクなしでも悪意あるリクエストに驚くほど従順であり、単純なジェイルブレイクテンプレートでエージェントの安全機構を突破可能であることを発見。

### 1-5. Agent-SafetyBench: Evaluating the Safety of LLM Agents
- **著者/組織**: 複数著者
- **URL**: https://arxiv.org/abs/2412.14470
- **年**: 2024
- **概要**: LLMエージェントの安全性を包括的に評価するベンチマーク。349のインタラクション環境と2,000のテストケースを含み、8カテゴリの安全リスクと10の一般的な障害モードを評価。16の主要LLMエージェントを評価した結果、いずれも安全性スコア60%を超えられなかった。

### 1-6. WebArena: A Realistic Web Environment for Building Autonomous Agents
- **著者/組織**: Carnegie Mellon University et al.
- **URL**: https://arxiv.org/abs/2307.13854
- **年**: 2023
- **概要**: 自律型Webエージェント構築のためのリアルな評価環境。EC、ソーシャルフォーラム、ソフトウェア開発、コンテンツ管理の4ドメインで構成。タスク実行の機能的正確性を評価。GPT-4ベースの最良エージェントでも成功率14.41%（人間は78.24%）と大きなギャップが存在。BrowserGymプラットフォームと統合され、VisualWebArena等の関連ベンチマークも含む統一フレームワークを形成。

### 1-7. PaperBench: Evaluating AI's Ability to Replicate AI Research
- **著者/組織**: OpenAI / METR
- **URL**: https://openai.com/index/paperbench/
- **年**: 2025
- **概要**: AIエージェントが最先端のAI研究を再現できるかを評価するベンチマーク。ICML 2024のSpotlight/Oral論文20本をゼロから再現するタスクで、論文理解・コードベース開発・実験実行を含む8,316の個別採点可能タスクで構成。各論文の著者と共同で評価ルーブリックを作成。Claude 3.5 Sonnetは平均再現スコア21.0%を達成するが、トップMLのPhD学生の人間ベースラインには未到達。

### 1-8. Beyond Accuracy: A Multi-Dimensional Framework for Evaluating Enterprise Agentic AI Systems
- **著者/組織**: 複数著者
- **URL**: https://arxiv.org/abs/2511.14136
- **年**: 2025
- **概要**: エンタープライズ向けエージェントAIの多次元評価フレームワーク。既存ベンチマークがタスク完了精度に偏重している問題を指摘し、コスト・信頼性・セキュリティ・運用制約を含む包括的評価の必要性を提唱。CLEARフレームワーク（Cost, Latency, Efficacy, Assurance, Reliability）を提案。

---

## 2. 企業・業界リソース (Corporate/Industry)

### 2-1. SWE-bench / SWE-bench Verified / SWE-bench Pro
- **組織**: Princeton University / OpenAI / Scale AI
- **URL**: https://www.swebench.com/ / https://openai.com/index/introducing-swe-bench-verified/
- **年**: 2023-2025
- **概要**: 実世界のGitHubイシューを使ってLLMのソフトウェアエンジニアリング能力を評価するベンチマーク。SWE-bench Verifiedは人間専門家が検証した500の高品質テストケースのサブセット。SWE-bench Proはエンタープライズレベルの複雑な問題1,865件を41リポジトリから収集。METRの分析では、テスト通過PRの約半数がリポジトリメンテナにマージされないことが判明し、ベンチマークスコアの素朴な解釈への警鐘を鳴らした。

### 2-2. HELM: Holistic Evaluation of Language Models
- **組織**: Stanford CRFM (Center for Research on Foundation Models)
- **URL**: https://crfm.stanford.edu/helm/
- **年**: 2022-現在
- **概要**: スタンフォード大学が開発したLLMの包括的・再現可能・透明性のある評価フレームワーク。7つのメトリクス（精度、較正、ロバスト性、公平性、バイアス、毒性、効率性）×16のコアシナリオで30以上のモデルを標準化条件下で密に評価。全プロンプト・出力を公開し、オープンソースのPythonツールキットとして提供。IBMによるエンタープライズ拡張版（金融・法律・気候・サイバーセキュリティ）も存在。

### 2-3. Berkeley Function Calling Leaderboard (BFCL)
- **組織**: UC Berkeley (Gorilla Project)
- **URL**: https://gorilla.cs.berkeley.edu/leaderboard.html
- **年**: 2024-現在 (ICML 2025)
- **概要**: LLMのファンクションコール（ツール使用）能力を評価する事実上の標準ベンチマーク。直列・並列のファンクションコール、複数プログラミング言語対応、AST（抽象構文木）ベースの新しい評価手法を採用。2,000の質問-回答ペアを多言語で収録。最先端LLMは単一ターンのコールに優れるが、記憶・動的意思決定・長期的推論には課題が残る。

### 2-4. METR: Measuring AI Ability to Complete Long Tasks
- **組織**: METR (Model Evaluation & Threat Research)
- **URL**: https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/
- **年**: 2025
- **概要**: フロンティアAIシステムの能力とリスクに関する研究・評価を行う組織。モデルが完了できるタスクの長さは指数関数的トレンド（倍増期間約7ヶ月）で予測可能であることを発見。多様なソフトウェアタスクを自律的に完了する能力を測定するHCAST（Human-Calibrated Autonomy Software Tasks）ベンチマークを開発中。

### 2-5. Evaluating AI Agents: Real-World Lessons from Building Agentic Systems at Amazon
- **組織**: Amazon Web Services (AWS)
- **URL**: https://aws.amazon.com/blogs/machine-learning/evaluating-ai-agents-real-world-lessons-from-building-agentic-systems-at-amazon/
- **年**: 2025
- **概要**: Amazonでのエージェントシステム構築から得た実践的な評価手法と教訓。機能検証・安全性とコンプライアンス・パフォーマンスメトリクス（レイテンシ、トークン効率、スケーラビリティ）の複数レイヤーでの評価アプローチを紹介。プロダクション環境でのエージェント評価のベストプラクティスを共有。

---

## 3. ブログ記事・実践ガイド (Blog Posts / Practical Guides)

### 3-1. 10 AI Agent Benchmarks
- **組織**: Evidently AI
- **URL**: https://www.evidentlyai.com/blog/ai-agent-benchmarks
- **年**: 2025
- **概要**: 主要なAIエージェントベンチマーク10個の概要と比較を提供する実践的ガイド。各ベンチマークの対象領域・評価対象・強み/弱みを整理し、適切なベンチマーク選択の指針を提示。

### 3-2. Building an LLM Evaluation Framework: Best Practices
- **組織**: Datadog
- **URL**: https://www.datadoghq.com/blog/llm-evaluation-framework-best-practices/
- **年**: 2025
- **概要**: LLM評価フレームワーク構築のベストプラクティス。コードベース・LLM-as-a-judge・人間参加型（human-in-the-loop）の3つの評価アプローチを解説。エージェント型やチェーンベースのLLMアプリケーションにおける内部入出力の特徴づけメトリクスの重要性を強調。

### 3-3. AI Agent Evaluationの評価指標まとめ
- **組織**: NeoAI (Zenn)
- **URL**: https://zenn.dev/neoai/articles/llm_agent_evaluation_20250424
- **年**: 2025
- **概要**: AIエージェントの評価指標を日本語で体系的にまとめた記事。AgentBench、ToolBenchなど主要ベンチマークの紹介と、計画・ツール使用・自己反省・記憶といったエージェント固有能力の評価方法を解説。

### 3-4. LLMエージェント評価の新基準 -- 100超のベンチマークと未来の"知性"の測り方
- **組織**: Qiita
- **URL**: https://qiita.com/ke-suke-Soft/items/166dfde704772940f8b1
- **年**: 2025
- **概要**: 100を超えるLLMエージェント評価ベンチマークの網羅的紹介。エージェント・コーディング・科学的推論・一般知識の4カテゴリにわたる評価の全体像を日本語で解説し、今後の「知性」の測り方の方向性を論じる。

### 3-5. 8 Benchmarks Shaping the Next Generation of AI Agents
- **組織**: Tessl
- **URL**: https://tessl.io/blog/8-benchmarks-shaping-the-next-generation-of-ai-agents/
- **年**: 2025
- **概要**: 次世代AIエージェントの発展を牽引する8つの主要ベンチマークを紹介。SWE-bench、WebArena、AgentBench等の概要と、それぞれが測定するエージェント能力の違いを整理。

---

## 評価手法の主要カテゴリ（まとめ）

| カテゴリ | 代表的ベンチマーク/フレームワーク | 評価対象 |
|---------|-------------------------------|---------|
| **汎用エージェント能力** | AgentBench, HELM | 推論、意思決定、多環境適応 |
| **ソフトウェアエンジニアリング** | SWE-bench, SWE-bench Pro | コード生成、バグ修正、PR作成 |
| **ツール使用/ファンクションコール** | BFCL, ToolBench | API呼出し、関数選択、引数生成 |
| **Web操作** | WebArena, BrowserGym, WorkArena | Webナビゲーション、タスク完了 |
| **研究再現** | PaperBench | 論文理解、実験再現 |
| **安全性** | AgentHarm, Agent-SafetyBench | 有害行動、安全リスク、ジェイルブレイク耐性 |
| **エンタープライズ** | CLEAR, CLASSic, AgentArch | コスト、レイテンシ、信頼性、セキュリティ |
| **長期タスク遂行** | METR HCAST | 長時間の自律タスク完了能力 |
