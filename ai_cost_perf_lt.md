---
marp: true
html: true
theme: default
paginate: true
size: 16:9
title: AI活用のコスパを最大化する方法
style: |
  @import url('https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css');

  :root {
    --brand: #1a5e2a;
    --brand-2: #2e7d32;
    --accent: #1976d2;
    --ink: #0f172a;
    --muted: #475569;
    --bg-soft: #f7faf7;
  }

  section {
    font-family: 'Noto Sans JP', 'Hiragino Sans', 'Yu Gothic', sans-serif;
    color: var(--ink);
    background:
      radial-gradient(circle at 100% 0%, #e8f5e9 0%, transparent 35%),
      radial-gradient(circle at 0% 100%, #e3f2fd 0%, transparent 32%),
      #ffffff;
    padding: 48px 56px;
    line-height: 1.35;
  }

  h1 {
    font-size: 46px;
    color: var(--brand);
    margin-bottom: 10px;
    letter-spacing: .01em;
  }

  h2 {
    font-size: 34px;
    color: var(--brand);
    margin-bottom: 12px;
  }

  h3 {
    font-size: 24px;
    color: var(--brand-2);
    margin-bottom: 8px;
  }

  p, li {
    font-size: 24px;
  }

  ul, ol {
    margin-top: 8px;
  }

  code {
    font-size: 20px;
    background: #eef6ee;
    color: #14532d;
    padding: 2px 8px;
    border-radius: 8px;
  }

  .lead h1 {
    font-size: 56px;
    line-height: 1.15;
  }

  .kicker {
    display: inline-block;
    font-size: 16px;
    font-weight: 700;
    color: #fff;
    background: linear-gradient(90deg, #1a5e2a, #2e7d32);
    border-radius: 9999px;
    padding: 6px 14px;
    letter-spacing: .04em;
    text-transform: uppercase;
  }

  .small {
    font-size: 18px;
    color: var(--muted);
  }

  .card {
    border-radius: 18px;
    border: 1px solid #dbe7db;
    background: #ffffffcc;
    box-shadow: 0 10px 30px rgba(15, 23, 42, 0.08);
    padding: 20px 22px;
  }

  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .metric {
    font-size: 42px;
    font-weight: 800;
    color: var(--brand);
    margin: 0;
  }

  .metric-label {
    margin-top: 2px;
    font-size: 17px;
    color: var(--muted);
  }

  .pill {
    display: inline-block;
    margin-right: 6px;
    margin-bottom: 6px;
    padding: 4px 10px;
    border-radius: 9999px;
    font-size: 16px;
    font-weight: 700;
    color: #14532d;
    background: #dcfce7;
  }

  .danger {
    color: #b91c1c;
    font-weight: 700;
  }

  .footer-note {
    position: absolute;
    right: 56px;
    bottom: 24px;
    font-size: 14px;
    color: #64748b;
  }
---

<!-- _class: lead -->
<span class="kicker">Lightning Talk</span>

# AI活用のコスパを最大化する方法
## トークン制約時代の依頼設計・CLI運用・共有資産化

<div class="small">2026 / Engineering Productivity</div>

<div class="footer-note">Source: Qiita記事を再構成</div>

---

## 今日のゴール

<div class="grid-3">
<div class="card">
<p class="metric">01</p>
<p class="metric-label">再試行を減らす依頼設計</p>
</div>
<div class="card">
<p class="metric">02</p>
<p class="metric-label">GUI依存からCLI運用へ</p>
</div>
<div class="card">
<p class="metric">03</p>
<p class="metric-label">個人知見を共有資産にする</p>
</div>
</div>

- キーワード: `品質の再現性` `完了までの総コスト` `チーム展開`

---

## なぜ今「コスパ設計」なのか

<div class="card">
<ul>
<li>生成AIの本質は <strong>質問回数</strong> ではなく <strong>再試行削減</strong></li>
<li>トークン/リクエスト制限下では、1回の精度が生産性を決める</li>
<li>曖昧な依頼は手戻りを生み、総コストを押し上げる</li>
</ul>
</div>

<div class="grid-3">
<div class="card"><p class="metric">↓</p><p class="metric-label">やり取り回数</p></div>
<div class="card"><p class="metric">↓</p><p class="metric-label">認知負荷</p></div>
<div class="card"><p class="metric">↑</p><p class="metric-label">完了速度</p></div>
</div>

---

## コスパは「単価」より「総コスト」で見る

<div class="grid-2">
<div class="card">
<h3>見落としがちなコスト</h3>
<ul>
<li>要件整理の時間</li>
<li>再修正の往復回数</li>
<li>レビュー差し戻し</li>
<li>セキュリティ確認工数</li>
</ul>
</div>
<div class="card">
<h3>判断基準</h3>
<p class="metric">完了までの時間 × 往復回数</p>
<p class="small">同単価でも、完了が半分なら実質コスパは大幅改善</p>
</div>
</div>

---

## まず避けるべき3つの失敗

<div class="grid-3">
<div class="card">
<h3>要件が1文</h3>
<p>「いい感じに直して」では優先順位が不明</p>
</div>
<div class="card">
<h3>制約未定義</h3>
<p>文字数・読者・形式がないと追加往復が増える</p>
</div>
<div class="card">
<h3>一括で巨大依頼</h3>
<p>調査〜検証を同時要求すると精度が落ちる</p>
</div>
</div>

<p class="danger">失敗の共通点: 「伝える」だけで「伝わる設計」になっていない</p>

---

## 伝わる依頼文の最小テンプレート

```md
# 目的
- 何を達成したいか

# 前提
- 現在の状況
- 使用環境

# 制約
- 使ってよい技術／禁止事項
- 納期・優先順位

# 期待する出力
- 形式（Markdown / JSON / コード）
- 完了条件
```

- 構造化すると、推論ミスと認識ズレを減らせる

---

## 複雑依頼は4フェーズ分割

<div class="grid-2">
<div class="card">
<p class="pill">1. 調査</p>
<p>情報整理・用語定義・前提確認</p>
<p class="pill">2. 設計</p>
<p>構成案・採用理由・非採用理由</p>
</div>
<div class="card">
<p class="pill">3. 実装</p>
<p>コード/本文の生成</p>
<p class="pill">4. レビュー</p>
<p>抜け漏れ・要件充足・品質統一</p>
</div>
</div>

<p class="small">品質が落ちた地点を切り分けやすく、結果的に最短で終わる</p>

---

## GUIよりCLIを主軸にする理由

<div class="grid-2">
<div class="card">
<h3>CLIの優位性</h3>
<ul>
<li>パフォーマンスが良いケースが多い</li>
<li>成果品質が安定しやすい</li>
<li>トークン効率が良い場面がある</li>
<li>裏で実行でき、マルチタスクしやすい</li>
</ul>
</div>
<div class="card">
<h3>運用面の価値</h3>
<ul>
<li>実行履歴を残せる</li>
<li>手順の再現性が上がる</li>
<li>チーム共有がしやすい</li>
</ul>
</div>
</div>

---

## チームで効く「AI共有資産」

<div class="card">
<span class="pill">依頼テンプレート</span>
<span class="pill">検証手順</span>
<span class="pill">レビュー観点</span>
<span class="pill">カスタムプロンプト</span>
<span class="pill">スキル定義</span>
</div>

<div class="grid-2">
<div class="card">
<h3>共通化する部分</h3>
<ul>
<li>目的・前提・制約・完了条件</li>
</ul>
</div>
<div class="card">
<h3>製品依存で調整する部分</h3>
<ul>
<li>ツール呼び出し</li>
<li>出力制約</li>
<li>コンテキスト管理</li>
</ul>
</div>
</div>

---

## セキュリティ前提の運用ルール

<div class="card">
<ul>
<li>個人情報・顧客情報・機密情報は入力しない</li>
<li>必要時は必ずマスキングして投入する</li>
<li>ログ保存範囲と公開範囲を事前確認する</li>
<li>社内ガイドラインに沿った運用フローを明文化する</li>
</ul>
</div>

<p class="small">無料版活用のメリットはあるが、情報統制を最優先する</p>

---

## まず着手する最小セット

<div class="grid-3">
<div class="card">
<p class="metric">1</p>
<p class="metric-label">依頼テンプレートを1枚作る</p>
</div>
<div class="card">
<p class="metric">2</p>
<p class="metric-label">複雑依頼を4フェーズに分割</p>
</div>
<div class="card">
<p class="metric">3</p>
<p class="metric-label">CLIで実行履歴を残す</p>
</div>
</div>

### 効果測定KPI
- 完了までのやり取り回数
- 1タスクあたり所要時間
- レビュー差し戻し件数

---

<!-- _class: lead -->
# まとめ

- AI活用の成果は、ツール単体より `運用設計` で決まる
- 3本柱: `依頼設計` `CLI運用` `共有資産化`
- 最初は小さく始めて、測って改善する

<div class="card">
<p><strong>再現可能な実務プロセス</strong> に変えることが、最も大きな投資対効果。</p>
</div>

<div class="small">参考: OpenAI Codex CLI / GitHub CLI / Qiita関連記事</div>
