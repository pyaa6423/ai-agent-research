---
marp: true
theme: default
paginate: true
header: ""
footer: ""
style: |
  :root {
    --color-primary: #2563eb;
    --color-primary-dark: #1e40af;
    --color-primary-light: #3b82f6;
    --color-primary-bg: #dbeafe;
    --color-primary-bg-light: #eff6ff;
    --color-accent: #059669;
    --color-accent-dark: #065f46;
    --color-warning: #f59e0b;
    --color-danger: #ef4444;
    --color-text: #1e293b;
    --color-text-light: #64748b;
    --color-bg: #ffffff;
    --color-border: #e2e8f0;
  }
  section {
    font-family: 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', 'Noto Sans JP', 'Yu Gothic', sans-serif;
    background-color: var(--color-bg);
    color: var(--color-text);
    padding: 40px 60px;
  }
  h1 { color: var(--color-primary); font-size: 2.0em; border-bottom: 3px solid var(--color-primary); padding-bottom: 0.3em; margin-bottom: 0.6em; }
  h2 { color: var(--color-primary-dark); font-size: 1.5em; margin-bottom: 0.5em; }
  h3 { color: var(--color-primary-light); font-size: 1.15em; margin-bottom: 0.4em; }
  strong { color: var(--color-primary-dark); }
  ul, ol { line-height: 1.8; }
  table { font-size: 0.85em; border-collapse: collapse; width: 100%; margin-top: 0.5em; }
  th { background-color: var(--color-primary); color: #ffffff; padding: 10px 14px; text-align: left; }
  td { padding: 10px 14px; border-bottom: 1px solid var(--color-border); }
  tr:nth-child(even) { background-color: var(--color-primary-bg-light); }
  code { background-color: #f1f5f9; padding: 2px 6px; border-radius: 4px; font-size: 0.9em; }
  blockquote { border-left: 4px solid var(--color-primary); padding-left: 1em; color: var(--color-text-light); font-style: italic; margin: 1em 0; }
  section.title { display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%); color: #ffffff; padding: 60px; }
  section.title h1 { color: #ffffff; border-bottom: 3px solid #93c5fd; font-size: 2.6em; margin-bottom: 0.3em; }
  section.title h2 { color: #bfdbfe; font-size: 1.3em; font-weight: normal; margin-bottom: 0.2em; }
  section.title p { color: #93c5fd; font-size: 1.0em; }
  section.section-divider { display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; background: linear-gradient(135deg, #1e40af 0%, #2563eb 100%); color: #ffffff; }
  section.section-divider h1 { color: #ffffff; border-bottom: none; font-size: 2.4em; }
  section.section-divider p { color: #bfdbfe; font-size: 1.1em; }
  section.quote { display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; background-color: var(--color-primary-bg-light); }
  section.quote blockquote { border-left: none; font-size: 1.6em; font-style: italic; color: var(--color-primary-dark); max-width: 80%; }
  section.quote p { color: var(--color-text-light); font-size: 1.0em; }
  section.summary { background: linear-gradient(180deg, #ffffff 0%, var(--color-primary-bg-light) 100%); }
  section.cta { display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; background: linear-gradient(135deg, #1e3a8a 0%, #2563eb 50%, #059669 100%); color: #ffffff; }
  section.cta h1 { color: #ffffff; border-bottom: none; font-size: 2.2em; }
  section.cta p { color: #bfdbfe; font-size: 1.1em; }
  .columns { display: grid; grid-template-columns: 1fr 1fr; gap: 2em; }
  .columns-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; }
  .card { background: #f8fafc; border: 1px solid var(--color-border); border-radius: 8px; padding: 1.2em; }
  .highlight-box { background: var(--color-primary-bg-light); border-left: 4px solid var(--color-primary); padding: 0.8em 1em; border-radius: 0 8px 8px 0; margin: 0.8em 0; }
  .badge { display: inline-block; background: var(--color-primary); color: white; padding: 0.15em 0.7em; border-radius: 999px; font-size: 0.8em; }
  .text-center { text-align: center; }
  .text-small { font-size: 0.85em; }
  .text-muted { color: var(--color-text-light); }
  .mt-1 { margin-top: 0.5em; }
  .mt-2 { margin-top: 1em; }
  .mt-3 { margin-top: 1.5em; }
---

<!-- _class: title -->
<!-- _paginate: false -->

# CAI — Cybersecurity AI

## サイバーセキュリティ特化AIエージェントフレームワークの全貌

aliasrobotics | 2026-04-02

<!--
スピーカーノート: CAIはaliasrobotics社が開発するOSSのサイバーセキュリティAIフレームワーク。今日はその設計思想から実績までを15分で紹介する。
-->

---

# アジェンダ

1. **CAIとは何か** — 概要とポジショニング
2. **3層アーキテクチャ** — SDK・エージェント・ツール
3. **28種のセキュリティエージェント** — 攻撃・防御・分析
4. **2層プロンプト設計の工夫** — 動的プロンプト生成
5. **OT/ICS特化と実績** — Dragos CTF 1位の裏側

<!--
スピーカーノート: 全5セクション構成。前半でアーキテクチャを理解し、後半で実践的な設計の工夫と実績を紹介する。
-->

---

<!-- _class: section-divider -->
<!-- _paginate: false -->

# CAIとは何か

概要とポジショニング

<!--
スピーカーノート: まずCAIの全体像を掴む。何を目的としたフレームワークなのか。
-->

---

# CAI の概要

- **aliasrobotics社**が開発するOSSのサイバーセキュリティAIフレームワーク
- ペネトレーションテスト、CTF、バグバウンティをAIエージェントで自動化
- **300以上のLLMモデル**に対応（litellm経由）
- 「ペネトレーションテスターのための Claude Code」的な位置づけ

<div class="highlight-box">

セキュリティ専門知識 + AIエージェント基盤 = **攻撃的セキュリティの自動化**

</div>

<!--
スピーカーノート: 従来のペンテストツール（Metasploit等）とは異なり、LLMが判断・計画・実行を自律的に行う。対話型REPLで操作し、エージェントがツールを選んで攻撃を進める。
-->

---

<!-- _class: quote -->
<!-- _paginate: false -->

> セキュリティの専門知識を持つAIエージェントが、人間のペンテスターと同等以上のスピードで脆弱性を発見する時代

<!--
スピーカーノート: Dragos OT CTF 2025で人間チーム比37%高速という結果が出ている。これは単なるビジョンではなく、既に実証されたファクト。
-->

---

<!-- _class: section-divider -->
<!-- _paginate: false -->

# 3層アーキテクチャ

SDK・エージェント・ツールの設計

<!--
スピーカーノート: CAIの設計の根幹。汎用的なSDK層の上にセキュリティ特化のレイヤーを重ねる構造。
-->

---

# CAI の3層構造

<div style="text-align:center; margin-top:0.5em;">
  <div style="background:linear-gradient(135deg,#1e40af,#2563eb); color:#fff; border-radius:12px; padding:20px 40px; margin:8px auto; max-width:80%;">
    <strong style="color:#93c5fd; font-size:0.85em;">LAYER 1</strong><br>
    <span style="font-size:1.3em; font-weight:bold;">SDK層</span><br>
    <span style="font-size:0.85em;">Agent基底クラス / Runner実行ループ / Handoff</span>
  </div>
  <div style="font-size:1.4em; color:#2563eb;">▼</div>
  <div style="background:linear-gradient(135deg,#059669,#34d399); color:#fff; border-radius:12px; padding:20px 40px; margin:8px auto; max-width:80%;">
    <strong style="color:#d1fae5; font-size:0.85em;">LAYER 2</strong><br>
    <span style="font-size:1.3em; font-weight:bold;">エージェント層</span><br>
    <span style="font-size:0.85em;">28種の特化エージェント（偵察・攻撃・報告 etc.）</span>
  </div>
  <div style="font-size:1.4em; color:#059669;">▼</div>
  <div style="background:linear-gradient(135deg,#b45309,#f59e0b); color:#fff; border-radius:12px; padding:20px 40px; margin:8px auto; max-width:80%;">
    <strong style="color:#fef3c7; font-size:0.85em;">LAYER 3</strong><br>
    <span style="font-size:1.3em; font-weight:bold;">ツール層</span><br>
    <span style="font-size:0.85em;">MITRE ATT&CK準拠のセキュリティツール群</span>
  </div>
</div>

<!--
スピーカーノート: SDK層は汎用エージェントフレームワークとして独立しており、その上にセキュリティ特化のエージェントとツールが載る。この分離により、新しいエージェントの追加が容易。
-->

---

# SDK層 — コアエンジン

- **Agent クラス**: `name`, `instructions`, `tools`, `handoffs` で構成
- **Runner**: `while True` ループで「LLM呼出 → ツール実行 → 判断」を反復
- **Handoff**: エージェント間の動的な委譲（Swarmパターン）

### 5種のオーケストレーション

<div class="columns" style="margin-top:0.5em;">
<div>

- **Parallel** — 並列実行
- **Swarm** — 自律的委譲
- **Hierarchical** — 階層型指揮

</div>
<div>

- **Sequential** — 逐次パイプライン
- **Conditional** — 条件分岐

</div>
</div>

<!--
スピーカーノート: Runnerのwhileループが核心。LLMを呼び出し、ツール実行かHandoffか最終出力かを判断する。Swarmパターンではエージェント同士が動的に会話を引き継ぐ。
-->

---

<!-- _class: section-divider -->

# 28種のセキュリティエージェント

攻撃・防御・分析の専門家集団

<!--
スピーカーノート: SDK層の上に載る具体的なエージェント群。各エージェントが専用のプロンプトとツールセットを持つ。
-->

---

# エージェント一覧（攻撃系）

| エージェント | 役割 | 主要ツール |
|---|---|---|
| **red_teamer** | ペネトレーションテスト全般 | Linux cmd, code exec |
| **web_pentester** | Webアプリ脆弱性診断 | curl, ffuf, JS解析 |
| **bug_bounter** | バグバウンティハンティング | Shodan, Google検索 |
| **replay_attack** | リプレイ攻撃シミュレーション | Scapy, tcpreplay |

<div class="highlight-box">

各エージェントが専用ツールセットを保持し、Thought Router が適切なエージェントを選択

</div>

<!--
スピーカーノート: 攻撃系エージェントは偵察からエクスプロイトまでの各フェーズに対応。web_pentesterは7段階の方法論（Clarification→Recon→Threat Modeling→Testing→Exploitation→Validation→Reporting）を持つ。
-->

---

# エージェント一覧（防御・分析系）

| エージェント | 役割 | 特徴 |
|---|---|---|
| **blue_teamer** | 防御的セキュリティ | 可用性維持を最優先 |
| **dfir** | フォレンジック・IR | 証拠改変禁止の制約 |
| **reverse_engineering** | バイナリ・ファームウェア解析 | ARM/MIPS対応 |
| **memory_analysis** | ランタイムメモリ検査 | プロセスフック |

<div class="highlight-box">

防御系エージェントには「破壊禁止」「証拠保全」など固有の制約をプロンプトで付与

</div>

<!--
スピーカーノート: 防御系の特徴は制約の厳しさ。dfirエージェントは「コピーで作業」「ハッシュ検証」「読み取り専用マウント」がプロンプトで義務付けられている。
-->

---

# Thought Router — 思考と行動の分離

<div class="columns">
<div>

### 思考（Thought）

- **breakdowns** — 問題の分解
- **reflection** — 結果の振り返り
- **key_clues** — 手がかりの抽出

</div>
<div>

### 行動（Action）

- 他エージェントへの**委譲**
- **ツール実行**（コマンド・API）
- 結果の収集と返却

</div>
</div>

```
Thought() → Agent() → Thought() → Agent() → ...
```

思考と行動を明示的に分離し、無計画なツール連打を抑止

<!--
スピーカーノート: Thought Routerは「考えてから動く」を構造的に強制する仕組み。出力フィールドを固定（breakdowns/reflection/action/next_step/key_clues）することで推論の飛躍を防ぐ。
-->

---

<!-- _class: section-divider -->

# 2層プロンプト設計

マスターテンプレート + エージェント固有プロンプト

<!--
スピーカーノート: CAIの最も独創的な部分。プロンプトが静的な文字列ではなく、実行時に動的に組み立てられる。
-->

---

# プロンプト組み立てフロー

<div style="text-align: center; font-size: 0.85em;">

```
┌─────────────────────────────────┐
│   マスターテンプレート（Mako）    │
└───────────────┬─────────────────┘
                │ 動的注入
    ┌───────────┼───────────┐
    ▼           ▼           ▼
┌────────┐ ┌────────┐ ┌────────────┐
│エージェ │ │圧縮コン│ │ RAG記憶    │
│ント固有 │ │テキスト│ │(ベクトルDB)│
│プロンプト│ │(会話要約)│ │            │
└────────┘ └────────┘ └────────────┘
    ┌───────────┼───────────┐
    ▼           ▼           ▼
┌────────┐ ┌────────┐ ┌────────────┐
│環境情報 │ │CTFアー │ │ 最終プロン │
│OS, IP,  │ │ティファ│ │ プト出力   │
│wordlists│ │クト    │ │            │
└────────┘ └────────┘ └────────────┘
```

</div>

Makoテンプレートが実行時に全要素を結合し、最適化されたプロンプトを生成

<!--
スピーカーノート: 6つの情報源を動的に統合。圧縮コンテキストは過去の会話をAIが要約したもの。RAG記憶は過去セッションの知見で、同じ偵察の繰り返しを防ぐ。
-->

---

# プロンプトの6つの工夫

- **非対話コマンド強制** — エージェントのハングを防止
- **構造化思考の強制** — breakdowns / reflection / action / next_step
- **仮説駆動テスト** — BLAB（Business Logic Abuse Backlog）
- **ペルソナ付与** — 「脆弱性がない」という結論を禁止
- **フォレンジック整合性** — コピーで作業・ハッシュ検証
- **純粋分析ロール** — ツールを使わず思考のみ行うエージェント

<!--
スピーカーノート: 特に重要なのは「非対話コマンド強制」と「構造化思考」。前者はvimやpasswd等でハングするのを防ぎ、後者は無計画なツール実行を防止する。ペルソナ付与では「安全宣言」を禁止し、常に脆弱性を探し続ける姿勢を維持させる。
-->

---

# callable instructions — 動的プロンプト生成

`instructions` を **callable（関数）** として設定し、毎回最新環境を反映

```python
agent = Agent(
    name="web_pentester",
    instructions=build_instructions,  # 文字列ではなく関数
    tools=[...],
)

def build_instructions(context):
    template = MakoTemplate("system_web_pentester.md")
    return template.render(
        target_ip=context.env.get("TARGET_IP"),
        wordlists=context.env.get("WORDLIST_PATH"),
        compressed_history=context.memory.summarize(),
        rag_results=context.rag.query(context.current_task),
    )
```

> 静的プロンプトでは不可能な **環境適応型の指示生成** を実現

<!--
スピーカーノート: instructionsフィールドがstrではなくCallableを受け取る設計。Makoテンプレートの条件分岐でCTFモードの有無、メモリの有無に応じてプロンプトが変化する。
-->

---

<!-- _class: section-divider -->

# OT/ICS特化と実績

実環境で検証されたセキュリティ能力

<!--
スピーカーノート: CAIがIT領域だけでなくOT/ICS領域でも成果を出していることを紹介する。
-->

---

# OT特化の実態

- **コードレベル**: OT専用プロトコル実装はなし（Modbus等のパーサー未搭載）
- **プロンプトレベル**: Sub-GHz, リプレイ攻撃, REエージェントにOT文脈の記述
- **ベンチマーク**: SCADAマシン、ロボティクスCTF、MiR-100データセットで検証
- **強みの本質**: 汎用ツール + OTドメイン知識プロンプト + 実績ベースの検証

<!--
スピーカーノート: OT専用コードを書くのではなく、汎用エージェントにOTドメイン知識をプロンプトで注入するアプローチ。新たなOTプロトコルにもプロンプト更新だけで対応可能という利点がある。
-->

---

# ケーススタディ — 実績

| 案件 | 対象 | 結果 |
|---|---|---|
| **Dragos OT CTF 2025** | OT/ICS | 1位（7-8h目）、34中32問達成 |
| **Ecoforest ヒートポンプ** | OT機器 | 認証バイパス、DES脆弱性発見 |
| **MiR-100 ロボット** | 産業ロボット | ROSメッセージインジェクション |
| **MQTTブローカー** | OTネットワーク | 認証なしMQTT、偽値注入 |

<div class="highlight-box">

Dragos CTFでは人間トップチーム比 **37%高速** で課題を攻略

</div>

<!--
スピーカーノート: 特にDragos CTFでは人間チームと同等以上の成績を収めた。Ecoforest、MiRは実機に対する脆弱性発見でCVE取得レベルの成果。
-->

---

# 従来のペンテスト vs CAI

<div class="columns">
<div class="card">

### 従来のペンテスト

- 手動での偵察・列挙に数時間
- ツールの切替に認知負荷
- 知見の属人化

</div>
<div class="card">

### CAI

- AIが偵察→攻撃を自律的に反復
- 28エージェントが適材適所で連携
- RAG記憶で知見を蓄積・再利用

</div>
</div>

<!--
スピーカーノート: CAIは人間の専門家を置き換えるものではなく、反復的な作業を自動化し、専門家がより高度な判断に集中できる環境を提供する。
-->

---

# 安全機構

- **ガードレール**: 入出力の検証（50以上のプロンプトインジェクションパターン検出）
- **Unicodeホモグラフ正規化**: 視覚的攻撃対策
- **コスト上限**: `CAI_PRICE_LIMIT` でトークン暴走を防止
- **コマンドバリデーション**: 対話的コマンドのブロック

<!--
スピーカーノート: 攻撃ツールであるがゆえに、自身が攻撃されるリスクも想定している。多層的な安全機構で意図しない動作を抑止。プロンプトインジェクション検出は50以上のパターンに対応。
-->

---

<!-- _class: section-divider -->

# まとめ

CAIの本質と今後

<!--
スピーカーノート: 最後にCAIの3つの要点を振り返る。
-->

---

<!-- _class: summary -->

# まとめ

### 3層アーキテクチャ
SDK + 28エージェント + MITRE準拠ツールで柔軟かつ専門的

### 2層プロンプト設計
マスターテンプレート + callable instructionsで動的に環境適応

### OT/ICS領域で実績を証明
Dragos CTF 1位、実機脆弱性発見（Ecoforest, MiR-100）

<!--
スピーカーノート: 汎用AIフレームワークとドメイン特化プロンプトの組み合わせが、実環境での成果を生み出す鍵。セキュリティAIエージェントの設計パターンとして参考になるはず。
-->

---

<!-- _class: cta -->
<!-- _paginate: false -->

# Try CAI

**GitHub**: github.com/aliasrobotics/cai

`pip install cai-framework`

ご質問はお気軽に

<!--
スピーカーノート: OSSとして公開されているので、ぜひ試してみてほしい。質疑応答へ。
-->
