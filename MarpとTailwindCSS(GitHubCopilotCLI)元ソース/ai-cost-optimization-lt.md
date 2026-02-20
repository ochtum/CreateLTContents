---
marp: true
theme: default
paginate: true
html: true
style: |
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;700;900&display=swap');

  /* ================================================================
     Tailwind CSS Design System — colors, spacing, radius, shadows
     ================================================================ */
  :root {
    /* Green palette (Tailwind green-*) */
    --green-950: #052e16;
    --green-900: #14532d;
    --green-800: #166534;
    --green-700: #15803d;
    --green-600: #16a34a;
    --green-500: #22c55e;
    --green-400: #4ade80;
    --green-300: #86efac;
    --green-200: #bbf7d0;
    --green-100: #dcfce7;
    --green-50:  #f0fdf4;
    /* Blue palette */
    --blue-600:  #2563eb;
    --blue-500:  #3b82f6;
    --blue-400:  #60a5fa;
    --blue-100:  #dbeafe;
    --blue-50:   #eff6ff;
    /* Red palette */
    --red-600:   #dc2626;
    --red-100:   #fee2e2;
    /* Amber palette */
    --amber-600: #d97706;
    --amber-500: #f59e0b;
    --amber-100: #fef3c7;
    /* Gray palette */
    --gray-900:  #111827;
    --gray-800:  #1f2937;
    --gray-700:  #374151;
    --gray-600:  #4b5563;
    --gray-500:  #6b7280;
    --gray-400:  #9ca3af;
    --gray-300:  #d1d5db;
    --gray-200:  #e5e7eb;
    --gray-100:  #f3f4f6;
    --gray-50:   #f9fafb;
    --white:     #ffffff;
    /* Tailwind shadow */
    --shadow-sm: 0 1px 2px rgba(0,0,0,.05);
    --shadow:    0 1px 3px rgba(0,0,0,.1),0 1px 2px rgba(0,0,0,.06);
    --shadow-lg: 0 10px 15px rgba(0,0,0,.1),0 4px 6px rgba(0,0,0,.05);
    /* Tailwind border-radius */
    --rounded:   0.375rem;
    --rounded-lg:0.5rem;
    --rounded-xl:0.75rem;
    --rounded-2xl:1rem;
    --rounded-full:9999px;
  }

  /* ===== Base ===== */
  section {
    font-family: 'Noto Sans JP', 'Hiragino Sans', 'Yu Gothic UI', sans-serif;
    background: var(--white);
    color: var(--gray-900);
    padding: 48px 64px;
    font-size: 19px;
    line-height: 1.75;
    position: relative;
    overflow: hidden;
    box-sizing: border-box;
  }

  /* ===== Typography ===== */
  h1 {
    font-size: 2.1rem;
    font-weight: 900;
    color: var(--green-900);
    margin: 0 0 1rem 0;
    line-height: 1.2;
    letter-spacing: -0.02em;
  }
  h2 {
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--green-800);
    margin: 0 0 0.6rem 0;
    padding-left: 0.75rem;
    border-left: 4px solid var(--green-500);
    line-height: 1.4;
  }
  h3 {
    font-size: 1rem;
    font-weight: 700;
    color: var(--green-700);
    margin: 0.4rem 0 0.2rem;
  }
  p { margin: 0.4rem 0; }
  ul, ol { margin: 0.3rem 0; padding-left: 1.4rem; }
  li { margin: 0.3rem 0; font-size: 0.95rem; }
  strong { color: var(--green-700); }

  /* ===== Code ===== */
  code {
    background: var(--gray-100);
    border-radius: var(--rounded);
    padding: 2px 7px;
    font-size: 0.82em;
    color: var(--green-800);
    font-family: 'Cascadia Code', 'Consolas', monospace;
  }
  pre {
    background: var(--gray-900);
    border-radius: var(--rounded-lg);
    padding: 1rem 1.25rem;
    border-left: 4px solid var(--green-500);
    margin: 0.5rem 0;
    box-shadow: var(--shadow);
  }
  pre code {
    background: transparent;
    color: var(--green-300);
    font-size: 0.82rem;
    padding: 0;
  }

  /* ===== Page number ===== */
  section::after {
    content: attr(data-marpit-pagination) ' / ' attr(data-marpit-pagination-total);
    position: absolute;
    bottom: 1.25rem;
    right: 2rem;
    font-size: 0.75rem;
    color: var(--gray-400);
    font-weight: 600;
  }

  /* ===== Tailwind-style utility components ===== */

  /* Cards */
  .card {
    background: var(--gray-50);
    border: 1px solid var(--gray-200);
    border-radius: var(--rounded-xl);
    padding: 0.875rem 1rem;
    margin: 0.4rem 0;
    box-shadow: var(--shadow-sm);
  }
  .card-green {
    background: var(--green-50);
    border-color: var(--green-200);
    border-left: 4px solid var(--green-500);
  }
  .card-red {
    background: var(--red-100);
    border-color: #fca5a5;
    border-left: 4px solid var(--red-600);
  }
  .card-blue {
    background: var(--blue-50);
    border-color: var(--blue-100);
    border-left: 4px solid var(--blue-500);
  }
  .card-amber {
    background: var(--amber-100);
    border-color: #fde68a;
    border-left: 4px solid var(--amber-500);
  }

  /* Highlight bar */
  .highlight {
    background: var(--green-100);
    border-left: 4px solid var(--green-600);
    border-radius: 0 var(--rounded-lg) var(--rounded-lg) 0;
    padding: 0.6rem 1rem;
    margin: 0.6rem 0;
    font-weight: 700;
    color: var(--green-900);
    font-size: 0.9rem;
  }
  .highlight-blue {
    background: var(--blue-50);
    border-left-color: var(--blue-600);
    color: var(--blue-600);
  }
  .highlight-amber {
    background: var(--amber-100);
    border-left-color: var(--amber-600);
    color: var(--amber-600);
  }

  /* Tailwind-style grid */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }
  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0.75rem;
  }

  /* Step (numbered flow item) */
  .step {
    display: flex;
    align-items: flex-start;
    gap: 0.875rem;
    padding: 0.65rem 0.875rem;
    background: var(--gray-50);
    border: 1px solid var(--gray-200);
    border-radius: var(--rounded-xl);
    margin: 0.4rem 0;
  }
  .step-num {
    background: var(--green-600);
    color: var(--white);
    border-radius: var(--rounded-full);
    width: 2rem;
    height: 2rem;
    min-width: 2rem;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 900;
    font-size: 0.95rem;
    box-shadow: var(--shadow-sm);
  }
  .step-content { flex: 1; }
  .step-title {
    font-weight: 700;
    color: var(--green-800);
    font-size: 0.97rem;
    line-height: 1.4;
  }
  .step-desc {
    font-size: 0.82rem;
    color: var(--gray-600);
    margin-top: 0.15rem;
    line-height: 1.4;
  }

  /* Big stat number */
  .big-num {
    font-size: 4.5rem;
    font-weight: 900;
    color: var(--green-500);
    line-height: 1;
    letter-spacing: -0.04em;
  }

  /* Table */
  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.88rem;
    margin: 0.5rem 0;
    border-radius: var(--rounded-lg);
    overflow: hidden;
    box-shadow: var(--shadow-sm);
  }
  th {
    background: var(--green-800);
    color: var(--white);
    padding: 0.5rem 0.75rem;
    font-weight: 700;
    text-align: left;
  }
  td {
    padding: 0.45rem 0.75rem;
    border-bottom: 1px solid var(--gray-200);
  }
  tr:nth-child(even) td { background: var(--green-50); }

  /* ================================================================
     Slide-class overrides (equivalent to Tailwind variant modifiers)
     ================================================================ */

  /* ── Title slide ── */
  section.title {
    background: linear-gradient(150deg, var(--green-950) 0%, var(--green-900) 45%, var(--green-800) 100%);
    color: var(--white);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 4rem 5rem;
  }
  section.title::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(74,222,128,.18) 0%, transparent 70%);
    border-radius: var(--rounded-full);
  }
  section.title h1 {
    color: var(--white);
    font-size: 2.4rem;
    line-height: 1.25;
    margin-bottom: 1rem;
    text-shadow: 0 2px 8px rgba(0,0,0,.35);
  }
  section.title h2 {
    color: var(--green-300);
    border-left-color: var(--green-400);
    font-size: 1rem;
    margin: 0.25rem 0;
  }
  section.title p { color: var(--green-300); font-size: 0.9rem; }
  section.title .subtitle {
    background: rgba(255,255,255,.08);
    border: 1px solid rgba(255,255,255,.15);
    border-left: 4px solid var(--green-400);
    border-radius: var(--rounded-xl);
    padding: 0.75rem 1.25rem;
    margin-top: 1.5rem;
    font-size: 1rem;
    color: var(--green-200);
    backdrop-filter: blur(4px);
  }
  section.title::after { color: var(--green-500); }

  /* ── Agenda slide ── */
  section.agenda {
    background: var(--green-950);
    color: var(--white);
  }
  section.agenda h1 { color: var(--green-400); }
  section.agenda::after { color: var(--green-600); }

  /* ── Section header slide ── */
  section.section-header {
    background: linear-gradient(135deg, var(--green-900) 0%, var(--green-700) 100%);
    color: var(--white);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 4rem 5rem;
  }
  section.section-header::before {
    content: '';
    position: absolute;
    bottom: -60px; left: -60px;
    width: 250px; height: 250px;
    background: radial-gradient(circle, rgba(74,222,128,.12) 0%, transparent 70%);
    border-radius: var(--rounded-full);
  }
  section.section-header h1 {
    color: var(--white);
    font-size: 3rem;
    margin-bottom: 0.5rem;
  }
  section.section-header h2 {
    color: var(--green-200);
    border-left-color: var(--green-400);
    font-size: 1.15rem;
    margin-top: 0.75rem;
  }
  section.section-header::after { color: var(--green-400); }

  /* ── Summary / Closing slide ── */
  section.summary {
    background: linear-gradient(150deg, var(--green-950) 0%, #1a3a2a 100%);
    color: var(--white);
  }
  section.summary h1 { color: var(--green-400); }
  section.summary h2 {
    color: var(--green-300);
    border-left-color: var(--green-500);
  }
  section.summary::after { color: var(--green-600); }
  section.summary .step {
    background: rgba(255,255,255,.07);
    border-color: rgba(255,255,255,.12);
  }

  /* ── Closing slide ── */
  section.closing {
    background: linear-gradient(150deg, var(--green-950) 0%, var(--green-900) 40%, var(--green-800) 100%);
    color: var(--white);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 4rem 5rem;
  }
  section.closing h1 { color: var(--white); font-size: 2.6rem; }
  section.closing::after { color: var(--green-500); }
  section.closing::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(74,222,128,.18) 0%, transparent 70%);
    border-radius: var(--rounded-full);
  }
---

<!-- _class: title -->

# AI活用の<br>コスパを最大化する方法

## トークン制約時代の依頼設計・CLI運用・共有資産化

<div class="subtitle">
💡 LT — 5分で押さえる「3本柱」フレームワーク
</div>

<p style="margin-top:1.5rem;">2026年2月</p>

---

<!-- _class: agenda -->

# 📋 Today's Agenda

<div class="grid-2" style="margin-top:1.25rem;">
  <div>
    <div class="card" style="background:rgba(255,255,255,.08);border-color:rgba(255,255,255,.15);color:#fff;margin-bottom:.75rem;border-left:4px solid var(--green-400);">
      <span style="font-size:1.4rem;">🎯</span><br>
      <strong style="color:var(--green-400);">柱① 依頼設計</strong><br>
      <span style="font-size:.82rem;color:var(--green-200);">伝えるではなく、伝わる文章を設計する</span>
    </div>
    <div class="card" style="background:rgba(255,255,255,.08);border-color:rgba(255,255,255,.15);color:#fff;border-left:4px solid var(--green-400);">
      <span style="font-size:1.4rem;">💻</span><br>
      <strong style="color:var(--green-400);">柱② CLI運用</strong><br>
      <span style="font-size:.82rem;color:var(--green-200);">高パフォーマンス運用を設計する</span>
    </div>
  </div>
  <div>
    <div class="card" style="background:rgba(255,255,255,.08);border-color:rgba(255,255,255,.15);color:#fff;margin-bottom:.75rem;border-left:4px solid var(--green-400);">
      <span style="font-size:1.4rem;">🤝</span><br>
      <strong style="color:var(--green-400);">柱③ 共有資産化</strong><br>
      <span style="font-size:.82rem;color:var(--green-200);">個人最適をチーム最適に変える</span>
    </div>
    <div class="card" style="background:rgba(255,255,255,.08);border-color:rgba(255,255,255,.15);color:#fff;border-left:4px solid var(--green-400);">
      <span style="font-size:1.4rem;">✅</span><br>
      <strong style="color:var(--green-400);">まとめ — 最小セット3つ</strong><br>
      <span style="font-size:.82rem;color:var(--green-200);">今日から始められること</span>
    </div>
  </div>
</div>

---

# 🔍 なぜ「コスパ設計」が生産性を左右するのか

<div class="highlight" style="margin-bottom:1.25rem;font-size:.95rem;">
⚠️ 生成AIは <strong>「無限に使える道具」ではない</strong> ― トークン制限・リクエスト制限がある
</div>

<div class="grid-3">
  <div class="card card-red" style="text-align:center;padding:1rem .875rem;">
    <div style="font-size:1.75rem;margin-bottom:.4rem;">❌</div>
    <strong style="font-size:.95rem;">曖昧な依頼</strong>
    <p style="font-size:.8rem;color:var(--gray-600);margin:.4rem 0 0;">追加指示が増えトークン消費が拡大する</p>
  </div>
  <div class="card card-amber" style="text-align:center;padding:1rem .875rem;">
    <div style="font-size:1.75rem;margin-bottom:.4rem;">⚠️</div>
    <strong style="font-size:.95rem;">品質のばらつき</strong>
    <p style="font-size:.8rem;color:var(--gray-600);margin:.4rem 0 0;">依頼者ごとに結果が変わりチーム再利用困難</p>
  </div>
  <div class="card card-green" style="text-align:center;padding:1rem .875rem;">
    <div style="font-size:1.75rem;margin-bottom:.4rem;">✅</div>
    <strong style="font-size:.95rem;">設計された依頼</strong>
    <p style="font-size:.8rem;color:var(--gray-600);margin:.4rem 0 0;">1回あたりの成功率↑ 認知負荷↓</p>
  </div>
</div>

<div class="highlight highlight-blue" style="margin-top:1rem;">
  💡 AI活用の本質 ＝ 「たくさん質問する」ではなく「<strong>再試行を減らす設計</strong>」
</div>

---

# 💸 コスパ＝「単価」でなく「完了までの総コスト」

<div class="grid-2" style="margin-top:.75rem;">
  <div>
    <h2 style="margin-bottom:.75rem;">❌ 誤った見方</h2>
    <div class="card card-red" style="font-size:.9rem;">
      1リクエストあたりの料金<strong>だけ</strong>を見る
    </div>

    <h2 style="margin:.875rem 0 .75rem;">✅ 正しい総コスト</h2>
    <div class="card card-green">
      <ul style="margin:0;font-size:.88rem;padding-left:1.1rem;">
        <li>要件整理にかかった <strong>時間</strong></li>
        <li>出力の <strong>再修正回数</strong></li>
        <li>チーム内レビューの <strong>手戻り</strong></li>
        <li>セキュリティ確認の <strong>工数</strong></li>
      </ul>
    </div>
  </div>
  <div style="display:flex;flex-direction:column;justify-content:center;align-items:center;gap:1rem;">
    <div style="text-align:center;">
      <div class="big-num">½</div>
      <p style="color:var(--gray-600);font-size:.88rem;margin:.5rem 0 0;line-height:1.5;">
        完了時間が半分になれば<br>実質コスパは <strong style="color:var(--green-700);">2倍以上</strong> 改善
      </p>
    </div>
    <div class="highlight" style="width:100%;text-align:center;font-size:.82rem;">
      安くても往復が増えれば<br>トータルで高くつく
    </div>
  </div>
</div>

---

<!-- _class: section-header -->

# 柱① 依頼設計

## 伝えるではなく、「伝わる文章」を設計する

---

# 📝 最低限の依頼テンプレート

<div class="grid-2" style="gap:.875rem;align-items:start;">
  <div>

```markdown
# 目的
- 何を達成したいか

# 前提
- 現在の状況
- 使用環境

# 制約
- 使ってよい技術 / 禁止事項
- 納期・優先順位

# 期待する出力
- 形式（Markdown / JSON / コード）
- 完了条件
```

  </div>
  <div>
    <div class="step" style="margin-bottom:.5rem;">
      <div class="step-num">🎯</div>
      <div class="step-content">
        <div class="step-title">目的 + 前提</div>
        <div class="step-desc">AIが「何のために」を理解するための軸になる</div>
      </div>
    </div>
    <div class="step" style="margin-bottom:.5rem;">
      <div class="step-num">🚧</div>
      <div class="step-content">
        <div class="step-title">制約</div>
        <div class="step-desc">禁止事項・優先順位を明示して推論ミスを防ぐ</div>
      </div>
    </div>
    <div class="step" style="margin-bottom:.75rem;">
      <div class="step-num">📤</div>
      <div class="step-content">
        <div class="step-title">期待する出力</div>
        <div class="step-desc">形式と完了条件を決めると品質が安定する</div>
      </div>
    </div>
    <div class="highlight" style="font-size:.82rem;">
      💡 自由記述より<strong>構造化された要件</strong>のほうが推論ミスが少ない
    </div>
  </div>
</div>

---

# ✂️ 複雑な依頼は「4フェーズ分割」

<div style="display:flex;flex-direction:column;gap:.55rem;margin-top:.5rem;">
  <div class="step">
    <div class="step-num">1</div>
    <div class="step-content">
      <div class="step-title">🔍 調査フェーズ</div>
      <div class="step-desc">既存情報の整理・用語定義・前提確認</div>
    </div>
  </div>
  <div class="step">
    <div class="step-num">2</div>
    <div class="step-content">
      <div class="step-title">🏗️ 設計フェーズ</div>
      <div class="step-desc">構成案・採用方針・非採用理由の整理</div>
    </div>
  </div>
  <div class="step">
    <div class="step-num">3</div>
    <div class="step-content">
      <div class="step-title">⚙️ 実装フェーズ</div>
      <div class="step-desc">コードまたは本文の生成</div>
    </div>
  </div>
  <div class="step">
    <div class="step-num">4</div>
    <div class="step-content">
      <div class="step-title">🔎 レビューフェーズ</div>
      <div class="step-desc">バグ・抜け漏れ・文体統一・要件充足の確認</div>
    </div>
  </div>
</div>

<div class="highlight highlight-blue" style="margin-top:.75rem;font-size:.88rem;">
  🚀 1回で完璧に出すより<strong>分割して精度を上げる</strong>ほうが、最終的に速く終わる
</div>

---

# 🌐 日本語 vs 英語の使い分け Tips

<div class="grid-2" style="margin-top:.75rem;">
  <div class="card card-blue">
    <h3 style="margin-top:0;color:var(--blue-600);">英語が向くケース</h3>
    <ul style="font-size:.88rem;margin:0;padding-left:1.2rem;">
      <li>英語の技術情報が豊富な領域</li>
      <li>出力の安定性を優先するとき</li>
    </ul>
  </div>
  <div class="card card-green">
    <h3 style="margin-top:0;">日本語出力が必要なら明示する</h3>

```markdown
- 調査・推論は英語情報を参照
- 最終出力は日本語で作成
- 専門用語には補足を入れる
```

  </div>
</div>

<br>

## ✅ 依頼品質チェックリスト

<div class="grid-2" style="gap:.5rem;margin-top:.25rem;">
  <div class="highlight" style="font-size:.85rem;margin:0;">✔ 「誰向けか」を書いたか</div>
  <div class="highlight" style="font-size:.85rem;margin:0;">✔ 「何をもって完了か」を書いたか</div>
  <div class="highlight" style="font-size:.85rem;margin:0;">✔ 出力形式を明示したか</div>
  <div class="highlight" style="font-size:.85rem;margin:0;">✔ 禁止事項を入れたか</div>
</div>

---

<!-- _class: section-header -->

# 柱② CLI運用

## GUIよりCLIを選ぶべき理由

---

# 💻 CLIを選ぶ4つの理由

<div class="grid-2" style="margin-top:.75rem;gap:.875rem;">
  <div class="card card-green" style="text-align:center;padding:1.25rem 1rem;">
    <span style="font-size:2.25rem;display:block;margin-bottom:.4rem;">⚡</span>
    <strong style="color:var(--green-800);font-size:1rem;">パフォーマンス</strong>
    <p style="font-size:.82rem;color:var(--gray-600);margin:.35rem 0 0;line-height:1.45;">GUI比で応答が速い場合が多い</p>
  </div>
  <div class="card card-green" style="text-align:center;padding:1.25rem 1rem;">
    <span style="font-size:2.25rem;display:block;margin-bottom:.4rem;">🎯</span>
    <strong style="color:var(--green-800);font-size:1rem;">成果の品質</strong>
    <p style="font-size:.82rem;color:var(--gray-600);margin:.35rem 0 0;line-height:1.45;">コンテキスト制御が精密で出力が安定</p>
  </div>
  <div class="card card-green" style="text-align:center;padding:1.25rem 1rem;">
    <span style="font-size:2.25rem;display:block;margin-bottom:.4rem;">💰</span>
    <strong style="color:var(--green-800);font-size:1rem;">トークン効率</strong>
    <p style="font-size:.82rem;color:var(--gray-600);margin:.35rem 0 0;line-height:1.45;">余分なUI往復なしでトークンを節約</p>
  </div>
  <div class="card card-green" style="text-align:center;padding:1.25rem 1rem;">
    <span style="font-size:2.25rem;display:block;margin-bottom:.4rem;">🙌</span>
    <strong style="color:var(--green-800);font-size:1rem;">マルチタスク化</strong>
    <p style="font-size:.82rem;color:var(--gray-600);margin:.35rem 0 0;line-height:1.45;">自分の作業の裏でAIを並行実行できる</p>
  </div>
</div>

<div class="highlight" style="margin-top:.875rem;font-size:.88rem;">
  📌 GitHub Copilot CLI・Codex CLI などがVS Code拡張より優位な場面が多い
</div>

---

<!-- _class: section-header -->

# 柱③ 共有資産化

## 個人最適をチーム最適に変える

---

# 🤝 チームのAI共有資産設計

<div class="grid-2" style="align-items:start;">
  <div>
    <h2>共有すべき資産の種類</h2>
    <ul style="font-size:.9rem;">
      <li>📄 依頼テンプレート（Markdown）</li>
      <li>✅ レビュー観点チェックリスト</li>
      <li>🔁 よく使う検証手順</li>
      <li>💬 カスタムプロンプト</li>
      <li>🤖 スキル定義・カスタムエージェント設定</li>
    </ul>
    <div class="highlight" style="font-size:.82rem;margin-top:.75rem;">
      🎓 新人でも一定品質に到達しやすくなる
    </div>
  </div>
  <div>
    <h2>エージェント差分への対応</h2>
    <table style="font-size:.84rem;">
      <tr>
        <th>共通部分（先に標準化）</th>
        <th>製品依存部分</th>
      </tr>
      <tr>
        <td>目的・前提・制約・完了条件</td>
        <td>ツール呼び出し仕様</td>
      </tr>
      <tr>
        <td>どのAIにも通用するコア</td>
        <td>出力制約・コンテキスト管理</td>
      </tr>
    </table>
    <div class="card card-blue" style="margin-top:.75rem;font-size:.84rem;">
      製品変更時は <strong>差分だけ</strong> 調整すればよい<br>
      <span style="color:var(--gray-500);">Claude / Codex / GitHub Copilot…</span>
    </div>
  </div>
</div>

---

# 🔒 セキュリティ前提の運用 & 形骸化対策

<div class="grid-2" style="gap:1rem;">
  <div>
    <h2>必須ルール</h2>
    <div class="step">
      <div class="step-num">🚫</div>
      <div class="step-content">
        <div class="step-title">機密情報は入力しない</div>
        <div class="step-desc">個人情報・顧客情報・機密情報はNG</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">🎭</div>
      <div class="step-content">
        <div class="step-title">必要ならマスキング</div>
        <div class="step-desc">匿名化・ダミー化してから投入する</div>
      </div>
    </div>
    <div class="step">
      <div class="step-num">📋</div>
      <div class="step-content">
        <div class="step-title">運用フローを明文化</div>
        <div class="step-desc">社内ガイドラインに沿った手順書を整備</div>
      </div>
    </div>
  </div>
  <div>
    <h2>形骸化しないコツ</h2>
    <div class="card card-amber" style="font-size:.84rem;margin-bottom:.6rem;">
      <strong>ルールが多すぎて使われない →</strong><br>
      最小セット（テンプレ1枚 + 観点3項目）から始める
    </div>
    <div class="card card-amber" style="font-size:.84rem;margin-bottom:.6rem;">
      <strong>更新されず古くなる →</strong><br>
      月1回・15分のメンテ時間を固定する
    </div>
    <div class="card card-amber" style="font-size:.84rem;">
      <strong>ブラックボックス化 →</strong><br>
      変更履歴と意図を短く記録する
    </div>
  </div>
</div>

---

<!-- _class: summary -->

# ✅ まとめ：今日から始める最小セット

<div style="display:flex;flex-direction:column;gap:.65rem;margin-top:1rem;">
  <div class="step">
    <div class="step-num" style="background:var(--green-500);">1</div>
    <div class="step-content">
      <div class="step-title" style="color:var(--green-300);font-size:1.05rem;">📄 依頼テンプレートを1枚作る</div>
      <div class="step-desc" style="color:var(--gray-400);">目的・前提・制約・期待出力の4項目を固定するだけでOK</div>
    </div>
  </div>
  <div class="step">
    <div class="step-num" style="background:var(--green-500);">2</div>
    <div class="step-content">
      <div class="step-title" style="color:var(--green-300);font-size:1.05rem;">✂️ 複雑依頼を4フェーズに分割する</div>
      <div class="step-desc" style="color:var(--gray-400);">調査 → 設計 → 実装 → レビュー の順で進める</div>
    </div>
  </div>
  <div class="step">
    <div class="step-num" style="background:var(--green-500);">3</div>
    <div class="step-content">
      <div class="step-title" style="color:var(--green-300);font-size:1.05rem;">💻 CLIで実行履歴を残す</div>
      <div class="step-desc" style="color:var(--gray-400);">手順の再現性を確保し、チーム共有しやすくする</div>
    </div>
  </div>
</div>

<div style="background:rgba(34,197,94,.12);border:1px solid var(--green-700);border-radius:var(--rounded-xl);padding:.75rem 1rem;margin-top:.875rem;font-size:.85rem;color:var(--green-200);">
  📊 <strong style="color:var(--green-400);">効果測定の指標：</strong>
  ① やり取り回数　② 1タスクあたりの時間　③ レビュー差し戻し件数
</div>

---

<!-- _class: closing -->

# 🙏 ご清聴ありがとうございました

<div class="subtitle" style="font-size:1rem;line-height:1.85;margin-top:1.5rem;">
  <strong style="color:var(--green-400);font-size:1.1rem;">
    依頼設計 × CLI運用 × 共有資産化
  </strong><br>
  この3本柱でAI活用を<br>
  「<em style="color:var(--green-300);font-style:normal;">属人芸</em>」 から 「<em style="color:var(--green-300);font-style:normal;">再現可能な実務プロセス</em>」へ
</div>

<div style="margin-top:2rem;">
  <p style="color:var(--green-200);font-size:.9rem;">
    📄 元記事 → Qiita「AI活用のコスパを最大化する方法」
  </p>
  <p style="color:var(--green-400);font-size:.82rem;">
    参考: GitHub CLI / OpenAI Codex CLI 公式ドキュメント
  </p>
</div>
