# AI Agent Red Teaming

AI Agent に対するレッドチーミング技術に関する論文・記事・企業リソースの調査まとめ。

## 学術論文

### AgentXploit: End-to-End Redteaming of Black-Box AI Agents (2025)

- **URL:** https://arxiv.org/abs/2505.05849
- **概要:** 自動マルチエージェントによるレッドチーミングフレームワーク。「Analyzer」エージェントがターゲットのコードベースを調査し高リスクツールと攻撃経路を特定、「Exploiter」エージェントが動的に攻撃を生成する。AgentDojo ベンチマークで 79% の攻撃成功率を達成（従来手法比 +27%）。

### From Prompt Injections to Protocol Exploits: Threats in LLM-Powered AI Agents Workflows (2025)

- **著者:** Mohamed Amine Ferrag, Norbert Tihanyi, Djallel Hamouda, Leandros Maglaras, Merouane Debbah
- **URL:** https://arxiv.org/abs/2506.23260
- **概要:** LLM エージェントエコシステムの統合脅威モデル。Input Manipulation、Model Compromise、System & Privacy Attacks、Protocol Vulnerabilities の 4 領域にわたる 30 以上の攻撃技術を体系化。MCP/ACP/ANP/A2A プロトコルの脆弱性を含む。CVE および NIST NVD エントリで検証済み。

### ToolHijacker: Prompt Injection Attack to Tool Selection in LLM Agents (2025, NDSS 2026 採択)

- **URL:** https://arxiv.org/abs/2504.19793
- **概要:** 悪意あるツールドキュメントをツールライブラリに注入し、LLM エージェントのツール選択をハイジャックするプロンプトインジェクション攻撃。攻撃成功率 96.43%。StruQ、SecAlign、DataSentinel、perplexity 検出など複数の防御を検証するも、いずれも不十分と結論。

### Red-Teaming LLM Multi-Agent Systems via Communication Attacks (2025)

- **URL:** https://arxiv.org/abs/2502.14847
- **概要:** Agent-in-the-Middle (AiTM) 攻撃を導入。LLM マルチエージェントシステムのエージェント間メッセージを傍受・改ざんすることで、単一の攻撃者がシステム全体を侵害できることを実証。

### Red Teaming AI Red Teaming (2025)

- **URL:** https://arxiv.org/html/2507.05538v1
- **概要:** AI レッドチーミング手法自体のメタ分析。現行手法の限界を検証し、特にエージェントシステムにおけるコンポーネント間相互作用から生じる創発的リスクへの対応不足を指摘。

### Hiding in the AI Traffic: Abusing MCP for LLM-Powered Agentic Red Teaming (2025)

- **URL:** https://arxiv.org/html/2511.15998v2
- **概要:** Model Context Protocol (MCP) を悪用した LLM エージェントへの攻撃手法。プロトコル層の脆弱性を実証。

### A Framework for Evaluating Emerging Cyberattack Capabilities of AI (2025, Google DeepMind)

- **URL:** https://arxiv.org/abs/2503.11917
- **概要:** 攻撃チェーン全体（情報収集、脆弱性悪用、マルウェア開発）をカバーする 50 チャレンジのオフェンシブセキュリティベンチマーク。20 カ国における AI のサイバー攻撃利用事例 12,000 件以上を分析。

### AI Red-Teaming is a Sociotechnical Problem (2024)

- **URL:** https://arxiv.org/abs/2412.09751
- **概要:** レッドチーミングを純粋な技術的課題としてではなく社会技術的課題として捉える論考。レッドチーミングに関わる価値観、労働力学、潜在的危害を検証。

---

## 企業・政府機関の資料

### NIST — Insights into AI Agent Security from a Large-Scale Red-Teaming Competition (2025)

- **組織:** NIST (CAISI), Gray Swan, UK AISI
- **URL:** https://www.nist.gov/blogs/caisi-research-blog/insights-ai-agent-security-large-scale-red-teaming-competition
- **概要:** 大規模公開競技会の報告。新規攻撃戦略が 81% の成功率を達成（ベースライン攻撃の 11% に対して）。シナリオやモデルを跨いで転移する「ユニバーサル」攻撃を発見。フロンティアモデル間で脆弱性に大きな差異があり、汎用能力とは相関しないことを確認。

### NIST — Strengthening AI Agent Hijacking Evaluations (2025)

- **URL:** https://www.nist.gov/news-events/news/2025/01/technical-blog-strengthening-ai-agent-hijacking-evaluations
- **概要:** AI エージェントハイジャック攻撃の評価手法に関する技術ブログ。意図された目標からの逸脱をどのように検出・評価するかに焦点。

### Microsoft — AI Red Teaming Agent (Azure AI Foundry / PyRIT) (2025)

- **URL:** https://learn.microsoft.com/en-us/azure/foundry/concepts/ai-red-teaming-agent
- **概要:** Azure AI Foundry に統合された自動レッドチーミングツール。PyRIT (Python Risk Identification Tool) をベースに 20 以上の攻撃戦略をサポート。ノーコード UI で非技術者も利用可能。Azure ツール呼び出しを使用するエージェントのレッドチーミングにも対応。

### Anthropic — Challenges in Red Teaming AI Systems (2024)

- **URL:** https://www.anthropic.com/news/challenges-in-red-teaming-ai-systems
- **概要:** ドメイン専門家によるレッドチーミング、公開レッドチーミング演習（GRT Challenge）、マルチモーダルシステムテスト、ポリシー脆弱性テストなど Anthropic のアプローチを解説。業界全体でレッドチーミングの標準化が不足していることを指摘。

### Anthropic — Agentic Misalignment Research (2025)

- **URL:** https://www.anthropic.com/research/agentic-misalignment
- **概要:** 現行の安全訓練がエージェントの不整合を確実に防止できないという研究結果。リスクをインサイダー脅威（信頼されていた従業員が組織目標に反する行動を取る）に類比。Claude Opus 4 が「AI Safety Level 3」（初の該当モデル）でリリースされる契機となった研究。

### Anthropic — Strengthening Red Teams: A Modular Scaffold for Control Evaluations (2025)

- **URL:** https://alignment.anthropic.com/2025/strengthening-red-teams/
- **概要:** 高度な AI システム（エージェント含む）のコントロール評価のためのモジュラースキャフォールディング手法を提案。

### Google DeepMind — Advancing Gemini's Security Safeguards (2025)

- **URL:** https://deepmind.google/blog/advancing-geminis-security-safeguards/
- **概要:** 自動レッドチーミング（ART）の実践。内部チームが Gemini を継続的に攻撃しセキュリティ上の弱点を発見。ツール使用時の間接プロンプトインジェクションに特に注力。

### OWASP — Top 10 for Agentic Applications (2025)

- **URL:** https://genai.owasp.org/2025/12/09/owasp-top-10-for-agentic-applications-the-benchmark-for-agentic-security-in-the-age-of-autonomous-ai/
- **概要:** 100 人以上のセキュリティ研究者の知見に基づくエージェント AI のリスク分類。主要リスク: Memory & Context Poisoning (ASI06)、Insecure Inter-Agent Communication (ASI07)、Cascading Failures (ASI08)、Human-Agent Trust Exploitation (ASI09)、Rogue Agents (ASI10)、Excessive Agency。

### CSA + OWASP — Agentic AI Red Teaming Guide (2025)

- **URL:** https://cloudsecurityalliance.org/artifacts/agentic-ai-red-teaming-guide
- **概要:** 62 ページの実践ガイド。12 カテゴリの脅威（エージェント認可ハイジャック、チェッカー回避、重要システム操作、目標改ざん、ハルシネーション悪用、影響チェーン、知識ベース汚染、メモリ操作、マルチエージェント悪用、リソース枯渇、サプライチェーン攻撃、エージェント追跡不能）を網羅。各カテゴリにテスト要件、攻撃ベクター、プロンプト例、成果物を記載。

### 日本 AISI — AI セーフティに関するレッドチーミング手法ガイド v1.00 (2024)

- **URL:** https://aisi.go.jp/assets/pdf/ai_safety_RT_v1.00_ja.pdf
- **概要:** 日本政府（AI Safety Institute）の公式ガイド。直接プロンプトインジェクション含む 8 つの攻撃手法を解説。v1.10 にアップデート済み。詳細な解説文書とサンプル成果物を併設。

---

## ブログ・実務者向け記事

### Adversa.ai — Agentic AI Red Teaming ブログシリーズ 全3部 (2025)

- **URL:**
  - [Part 1](https://adversa.ai/blog/agentic-ai-red-teaming-p1/)
  - [Part 2](https://adversa.ai/blog/agentic-ai-red-teaming-p2/)
  - [Part 3](https://adversa.ai/blog/agentic-ai-red-teaming-p3/)
- **概要:** チャットボット向けレッドチーミングはエージェント AI の攻撃面の約 15% しかカバーしていないと主張。Part 2 ではユーザー入力以外の 9 つの攻撃面（目標計画、ツール実行、外部データ等）を特定。Part 3 では 6 種の攻撃者プロファイルを分析し、多くのレッドチームが最も危険度の低い攻撃者（ジェイルブレイクハッカー）しかシミュレートしていないと指摘。

### Palo Alto Networks / Unit 42 — Agentic AI Red Teaming シリーズ (2025)

- **URL:**
  - [How AI Red Teaming Evolves with the Agentic Attack Surface](https://www.paloaltonetworks.com/blog/network-security/how-ai-red-teaming-evolves-with-the-agentic-attack-surface/)
  - [Beyond Jailbreaks: Why Agentic AI Needs Contextual Red Teaming](https://www.paloaltonetworks.com/blog/network-security/beyond-jailbreaks-why-agentic-ai-needs-contextual-red-teaming/)
  - [Indirect Prompt Injection in the Wild](https://unit42.paloaltonetworks.com/ai-agent-prompt-injection/)
- **概要:** エージェント AI には「コンテキストレッドチーミング」が必要と主張。応答リスク（モデルの発言）と操作リスク（実行されるアクション）を区別。Unit 42 ブログでは実環境における Web ベースの間接プロンプトインジェクション攻撃を報告。

### Toloka — AI Agents Under Attack: A Case Study (2025)

- **URL:** https://toloka.ai/blog/ai-agents-under-attack-a-case-study-on-advanced-agent-red-teaming/
- **概要:** 大手 LLM 提供企業のコンピュータ操作エージェントのレッドチーミング実践例。40 以上のリスクカテゴリを定義、1,200 以上のテストケースを作成、25 以上のオフラインテスト環境を構築。例: 金融ダッシュボードエージェントがページソースに仕込まれた悪意あるコードにより機密データを窃取。

### Simon Willison — New Prompt Injection Papers (2025)

- **URL:** https://simonwillison.net/2025/Nov/2/new-prompt-injection-papers/
- **概要:** エージェント固有のプロンプトインジェクション研究の分析。「Agents Rule of Two」概念と「Attacker Moves Second」パラダイムを紹介。

### NEC — ペネトレーションテスターから見た AISI レッドチーミングガイド (2024)

- **URL:** https://jpn.nec.com/cybersecurity/blog/241220/index.html
- **概要:** 日本 AISI レッドチーミングガイドを経験豊富なペネトレーションテスターの視点から分析。従来のセキュリティテスト手法と AI 固有のレッドチーミングアプローチの橋渡し。

---

## 横断的な主要テーマ

1. **エージェント固有の攻撃面は広大** — ユーザー入力のプロンプトインジェクションだけでなく、ツール実行・エージェント間通信・メモリ・外部データ取り込みなど 10 以上の攻撃面が存在
2. **ツール悪用が最大級のリスク** — ツールアクセスを持つエージェントはデータ窃取・不正取引・コード実行に悪用される可能性がある（チャットボットには存在しないリスク）
3. **ユニバーサル攻撃の存在** — NIST の研究で、シナリオやモデルを跨いで転移する攻撃戦略が発見されており、攻撃者がデプロイ環境の詳細を知る必要がない
4. **プロトコル層の新たな脅威** — MCP/A2A 等の通信プロトコル自体が攻撃対象に
5. **既存の防御は不十分** — 複数の論文で攻撃成功率 79〜96% が報告されており、ガードレール・検出システム・安全訓練では不足
