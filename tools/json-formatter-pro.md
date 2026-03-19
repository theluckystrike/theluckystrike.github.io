---
layout: page
title: "JSON Formatter Pro — Validate, Compare, Transform & Query JSON | Zovo"
description: "Advanced JSON formatter with diff comparison, JSONPath queries, schema validation, tree viewer, and data transformation. Free professional JSON toolkit for developers."
permalink: /tools/json-formatter-pro/
keywords: "json formatter, json validator, json compare, json diff, json viewer, json editor, jsonpath, json schema validator, json to csv, json beautifier"
date: 2026-03-19
categories: [tools]
tags: [json, formatter, validator, diff, jsonpath, schema, developer-tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root {
  --jp-bg: #0a0a0f;
  --jp-surface: #12121a;
  --jp-surface2: #1a1a28;
  --jp-border: #1e1e2e;
  --jp-border-hover: #2e2e44;
  --jp-primary: #6C5CE7;
  --jp-primary-dark: #5A4BD1;
  --jp-primary-light: #8B7CF7;
  --jp-secondary: #00ff88;
  --jp-secondary-dark: #00cc6e;
  --jp-text: #e0e0e0;
  --jp-text-muted: #8888aa;
  --jp-text-dim: #555570;
  --jp-error: #ff4757;
  --jp-error-bg: rgba(255,71,87,0.08);
  --jp-success: #00ff88;
  --jp-success-bg: rgba(0,255,136,0.08);
  --jp-warning: #ffa502;
  --jp-warning-bg: rgba(255,165,2,0.08);
  --jp-add: #00ff88;
  --jp-add-bg: rgba(0,255,136,0.06);
  --jp-del: #ff4757;
  --jp-del-bg: rgba(255,71,87,0.06);
  --jp-mod: #ffa502;
  --jp-mod-bg: rgba(255,165,2,0.06);
  --jp-radius: 10px;
  --jp-radius-sm: 6px;
  --jp-font: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --jp-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --jp-syn-key: #7dd3fc;
  --jp-syn-string: #4ade80;
  --jp-syn-number: #c084fc;
  --jp-syn-bool: #fb923c;
  --jp-syn-null: #f87171;
  --jp-syn-bracket: #555570;
}

.jp-light {
  --jp-bg: #f4f4f8;
  --jp-surface: #ffffff;
  --jp-surface2: #f0f0f5;
  --jp-border: #dddde8;
  --jp-border-hover: #ccccdd;
  --jp-text: #1a1a2e;
  --jp-text-muted: #6666888;
  --jp-text-dim: #9999aa;
  --jp-syn-key: #0369a1;
  --jp-syn-string: #15803d;
  --jp-syn-number: #7c3aed;
  --jp-syn-bool: #c2410c;
  --jp-syn-null: #dc2626;
  --jp-syn-bracket: #9999aa;
  --jp-error-bg: rgba(255,71,87,0.06);
  --jp-success-bg: rgba(0,180,100,0.06);
  --jp-warning-bg: rgba(255,165,2,0.06);
  --jp-add-bg: rgba(0,180,100,0.08);
  --jp-del-bg: rgba(255,71,87,0.08);
  --jp-mod-bg: rgba(255,165,2,0.08);
}

.jp-wrap {
  font-family: var(--jp-font);
  color: var(--jp-text);
  max-width: 1320px;
  margin: 0 auto;
  padding: 0 16px;
  line-height: 1.6;
}
.jp-wrap *, .jp-wrap *::before, .jp-wrap *::after { box-sizing: border-box; }

/* Hero */
.jp-hero { text-align: center; padding: 32px 0 24px; }
.jp-hero h1 { font-size: 2rem; font-weight: 700; margin: 0 0 12px; line-height: 1.2; color: var(--jp-text); }
.jp-hero h1 span { color: var(--jp-primary); }
.jp-hero p { font-size: 0.95rem; color: var(--jp-text-muted); max-width: 700px; margin: 0 auto; line-height: 1.7; }

/* Top bar */
.jp-topbar {
  display: flex; align-items: center; gap: 8px; flex-wrap: wrap;
  margin-bottom: 12px; padding: 8px 0;
}
.jp-topbar-right { margin-left: auto; display: flex; gap: 8px; align-items: center; }

/* Tabs */
.jp-tabs {
  display: flex; gap: 2px; background: var(--jp-surface); border: 1px solid var(--jp-border);
  border-radius: var(--jp-radius); padding: 4px; margin-bottom: 16px; overflow-x: auto;
}
.jp-tab {
  padding: 8px 16px; border: none; background: transparent; color: var(--jp-text-muted);
  font-family: var(--jp-font); font-size: 0.82rem; font-weight: 500; cursor: pointer;
  border-radius: var(--jp-radius-sm); transition: all 0.15s; white-space: nowrap;
}
.jp-tab:hover { color: var(--jp-text); background: var(--jp-surface2); }
.jp-tab.active { background: var(--jp-primary); color: #fff; }

/* Tab panels */
.jp-panel { display: none; }
.jp-panel.active { display: block; }

/* Buttons */
.jp-btn {
  display: inline-flex; align-items: center; gap: 5px; padding: 7px 14px;
  border: 1px solid var(--jp-border); border-radius: var(--jp-radius-sm);
  font-family: var(--jp-font); font-size: 0.8rem; font-weight: 500;
  cursor: pointer; transition: all 0.15s; white-space: nowrap;
  background: var(--jp-surface); color: var(--jp-text);
}
.jp-btn:hover { border-color: var(--jp-border-hover); background: var(--jp-surface2); }
.jp-btn-primary { background: var(--jp-primary); color: #fff; border-color: var(--jp-primary); }
.jp-btn-primary:hover { background: var(--jp-primary-dark); border-color: var(--jp-primary-dark); }
.jp-btn-sm { padding: 5px 10px; font-size: 0.75rem; }
.jp-btn.copied { background: var(--jp-secondary-dark); border-color: var(--jp-secondary-dark); color: #000; }

.jp-select {
  padding: 7px 10px; border: 1px solid var(--jp-border); border-radius: var(--jp-radius-sm);
  font-family: var(--jp-font); font-size: 0.8rem; background: var(--jp-surface);
  color: var(--jp-text); cursor: pointer;
}

/* Editor box */
.jp-editor-box {
  border: 1px solid var(--jp-border); border-radius: var(--jp-radius);
  overflow: hidden; background: var(--jp-surface); margin-bottom: 12px;
}
.jp-editor-header {
  display: flex; align-items: center; justify-content: space-between;
  padding: 8px 14px; border-bottom: 1px solid var(--jp-border);
  font-size: 0.72rem; font-weight: 600; color: var(--jp-text-muted);
  text-transform: uppercase; letter-spacing: 0.06em; background: var(--jp-surface2);
}
.jp-editor-header-actions { display: flex; gap: 6px; align-items: center; }
.jp-textarea {
  width: 100%; min-height: 340px; border: none; padding: 12px 14px;
  font-family: var(--jp-mono); font-size: 0.82rem; line-height: 1.65;
  resize: vertical; color: var(--jp-text); background: var(--jp-surface);
  outline: none; tab-size: 2;
}
.jp-textarea::placeholder { color: var(--jp-text-dim); }
.jp-output {
  width: 100%; min-height: 340px; padding: 12px 14px;
  font-family: var(--jp-mono); font-size: 0.82rem; line-height: 1.65;
  overflow: auto; white-space: pre; background: var(--jp-surface); color: var(--jp-text);
}

/* Syntax highlighting */
.jps-key { color: var(--jp-syn-key); }
.jps-str { color: var(--jp-syn-string); }
.jps-num { color: var(--jp-syn-number); }
.jps-bool { color: var(--jp-syn-bool); }
.jps-null { color: var(--jp-syn-null); font-style: italic; }
.jps-bracket { color: var(--jp-syn-bracket); }

/* Status bar */
.jp-status {
  display: flex; align-items: center; justify-content: space-between;
  flex-wrap: wrap; gap: 10px; margin-bottom: 16px; font-size: 0.82rem;
}
.jp-status-msg {
  display: inline-flex; align-items: center; gap: 5px; padding: 5px 12px;
  border-radius: 16px; font-weight: 500; font-size: 0.8rem;
}
.jp-status-valid { background: var(--jp-success-bg); color: var(--jp-success); }
.jp-status-invalid { background: var(--jp-error-bg); color: var(--jp-error); }
.jp-status-empty { background: var(--jp-surface2); color: var(--jp-text-muted); }
.jp-stats { display: flex; gap: 14px; color: var(--jp-text-muted); font-size: 0.78rem; }
.jp-stats strong { color: var(--jp-text); font-weight: 600; }
.jp-error-detail {
  font-size: 0.8rem; color: var(--jp-error); padding: 8px 14px;
  background: var(--jp-error-bg); border-radius: var(--jp-radius-sm);
  font-family: var(--jp-mono); margin-bottom: 12px; display: none; word-break: break-word;
}

/* Grid layouts */
.jp-grid2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.jp-grid-side { display: grid; grid-template-columns: 1fr 300px; gap: 12px; }

/* Tree viewer */
.jp-tree {
  font-family: var(--jp-mono); font-size: 0.82rem; padding: 12px 14px;
  min-height: 340px; max-height: 600px; overflow: auto; background: var(--jp-surface);
}
.jp-tree-node { padding-left: 20px; }
.jp-tree-toggle {
  cursor: pointer; user-select: none; display: inline-block; width: 16px;
  color: var(--jp-text-dim); font-size: 0.7rem;
}
.jp-tree-toggle:hover { color: var(--jp-primary-light); }
.jp-tree-key { color: var(--jp-syn-key); cursor: pointer; }
.jp-tree-key:hover { text-decoration: underline; }
.jp-tree-str { color: var(--jp-syn-string); }
.jp-tree-num { color: var(--jp-syn-number); }
.jp-tree-bool { color: var(--jp-syn-bool); }
.jp-tree-null { color: var(--jp-syn-null); font-style: italic; }
.jp-tree-type { color: var(--jp-text-dim); font-size: 0.7rem; margin-left: 6px; }
.jp-tree-search {
  width: 100%; padding: 8px 12px; border: 1px solid var(--jp-border);
  border-radius: var(--jp-radius-sm); font-family: var(--jp-font); font-size: 0.82rem;
  background: var(--jp-surface); color: var(--jp-text); outline: none; margin-bottom: 10px;
}
.jp-tree-search:focus { border-color: var(--jp-primary); }
.jp-tree-path {
  padding: 6px 12px; background: var(--jp-surface2); border-radius: var(--jp-radius-sm);
  font-family: var(--jp-mono); font-size: 0.78rem; color: var(--jp-primary-light);
  margin-bottom: 10px; min-height: 30px; word-break: break-all;
}
.jp-tree-highlight { background: rgba(108,92,231,0.25); border-radius: 2px; }

/* Diff */
.jp-diff-line { padding: 1px 10px; font-family: var(--jp-mono); font-size: 0.8rem; white-space: pre; }
.jp-diff-add { background: var(--jp-add-bg); color: var(--jp-add); }
.jp-diff-del { background: var(--jp-del-bg); color: var(--jp-del); }
.jp-diff-mod { background: var(--jp-mod-bg); color: var(--jp-mod); }
.jp-diff-ctx { color: var(--jp-text-dim); }
.jp-diff-summary {
  display: flex; gap: 16px; padding: 10px 14px; font-size: 0.8rem; font-weight: 500;
  background: var(--jp-surface2); border-radius: var(--jp-radius-sm); margin-bottom: 10px;
}
.jp-diff-summary span { display: inline-flex; align-items: center; gap: 4px; }
.jp-diff-nav { display: flex; gap: 6px; align-items: center; }
.jp-diff-output { max-height: 500px; overflow: auto; border: 1px solid var(--jp-border); border-radius: var(--jp-radius); }

/* JSONPath reference */
.jp-ref-table {
  width: 100%; font-size: 0.78rem; border-collapse: collapse;
}
.jp-ref-table th {
  text-align: left; padding: 6px 8px; border-bottom: 1px solid var(--jp-border);
  color: var(--jp-text-muted); font-weight: 600; font-size: 0.72rem; text-transform: uppercase;
}
.jp-ref-table td { padding: 5px 8px; border-bottom: 1px solid var(--jp-border); }
.jp-ref-table code {
  font-family: var(--jp-mono); font-size: 0.75rem; color: var(--jp-primary-light);
  background: var(--jp-surface2); padding: 1px 5px; border-radius: 3px;
}

/* Transform */
.jp-transform-btns { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 12px; }
.jp-transform-out {
  width: 100%; min-height: 300px; padding: 12px 14px;
  font-family: var(--jp-mono); font-size: 0.82rem; line-height: 1.65;
  overflow: auto; white-space: pre; background: var(--jp-surface);
  border: 1px solid var(--jp-border); border-radius: var(--jp-radius); color: var(--jp-text);
}
.jp-table-view { width: 100%; overflow-x: auto; margin-bottom: 12px; }
.jp-table-view table {
  width: 100%; border-collapse: collapse; font-size: 0.8rem;
  font-family: var(--jp-mono);
}
.jp-table-view th {
  padding: 8px 10px; text-align: left; border-bottom: 2px solid var(--jp-border);
  color: var(--jp-primary-light); font-weight: 600; background: var(--jp-surface2);
}
.jp-table-view td {
  padding: 6px 10px; border-bottom: 1px solid var(--jp-border); color: var(--jp-text);
}

/* Schema */
.jp-schema-errors {
  padding: 12px 14px; background: var(--jp-surface); border: 1px solid var(--jp-border);
  border-radius: var(--jp-radius); min-height: 120px; max-height: 300px; overflow: auto;
  font-family: var(--jp-mono); font-size: 0.8rem;
}
.jp-schema-err-item { padding: 4px 0; color: var(--jp-error); }
.jp-schema-err-item .jp-schema-err-path { color: var(--jp-primary-light); margin-right: 8px; }
.jp-schema-ok { color: var(--jp-success); font-weight: 500; }

/* History */
.jp-history-list {
  position: absolute; top: 100%; left: 0; right: 0; background: var(--jp-surface);
  border: 1px solid var(--jp-border); border-radius: var(--jp-radius-sm);
  max-height: 200px; overflow: auto; z-index: 100; display: none;
}
.jp-history-item {
  padding: 6px 12px; font-size: 0.78rem; color: var(--jp-text-muted);
  cursor: pointer; font-family: var(--jp-mono); white-space: nowrap;
  overflow: hidden; text-overflow: ellipsis; border-bottom: 1px solid var(--jp-border);
}
.jp-history-item:hover { background: var(--jp-surface2); color: var(--jp-text); }

/* Responsive */
@media (max-width: 900px) {
  .jp-grid2 { grid-template-columns: 1fr; }
  .jp-grid-side { grid-template-columns: 1fr; }
}
@media (max-width: 600px) {
  .jp-hero h1 { font-size: 1.5rem; }
  .jp-tabs { gap: 1px; padding: 3px; }
  .jp-tab { padding: 6px 10px; font-size: 0.75rem; }
  .jp-textarea, .jp-output, .jp-tree { min-height: 220px; }
  .jp-topbar { gap: 4px; }
  .jp-btn { padding: 6px 10px; font-size: 0.75rem; }
}

/* Content section */
.jp-content { max-width: 820px; margin: 40px auto 0; }
.jp-content h2 {
  font-size: 1.35rem; font-weight: 700; color: var(--jp-text);
  margin: 36px 0 14px; padding-top: 12px;
}
.jp-content p {
  font-size: 0.95rem; color: var(--jp-text-muted); line-height: 1.8;
  margin: 0 0 14px;
}
.jp-content code {
  font-family: var(--jp-mono); font-size: 0.85rem; background: var(--jp-surface2);
  padding: 1px 5px; border-radius: 3px; color: var(--jp-primary-light);
}
.jp-content ul { color: var(--jp-text-muted); padding-left: 20px; margin: 0 0 14px; }
.jp-content li { margin-bottom: 6px; font-size: 0.95rem; line-height: 1.7; }

/* FAQ */
.jp-faq { max-width: 820px; margin: 40px auto 50px; }
.jp-faq h2 { font-size: 1.35rem; font-weight: 700; margin: 0 0 20px; text-align: center; color: var(--jp-text); }
.jp-faq-item {
  border: 1px solid var(--jp-border); border-radius: var(--jp-radius);
  padding: 18px 22px; margin-bottom: 10px; background: var(--jp-surface);
}
.jp-faq-item h3 { font-size: 1rem; font-weight: 600; margin: 0 0 8px; color: var(--jp-text); }
.jp-faq-item p { margin: 0; font-size: 0.92rem; color: var(--jp-text-muted); line-height: 1.7; }

.jp-footer {
  text-align: center; padding: 2rem 0; color: var(--jp-text-dim);
  font-size: 0.82rem; border-top: 1px solid var(--jp-border); margin-top: 3rem;
}
.jp-footer a { color: var(--jp-primary); text-decoration: none; }
.jp-footer a:hover { text-decoration: underline; }

/* Keyboard shortcut hint */
.jp-kbd {
  display: inline-block; padding: 1px 5px; font-size: 0.68rem;
  border: 1px solid var(--jp-border); border-radius: 3px;
  font-family: var(--jp-mono); color: var(--jp-text-dim); background: var(--jp-surface2);
  margin-left: 4px;
}
</style>

<div class="jp-wrap" id="jpApp" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="JSON Formatter Pro">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="jp-hero">
    <h1><span>JSON Formatter</span> Pro</h1>
    <p>Format, validate, compare, query, transform, and schema-validate JSON -- all in your browser. Six professional tools in one page, no data leaves your device.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <!-- Top bar -->
  <div class="jp-topbar">
    <button class="jp-btn jp-btn-sm" onclick="JP.paste()" title="Paste from clipboard">Paste</button>
    <button class="jp-btn jp-btn-sm" onclick="JP.loadSample()" title="Load sample JSON">Sample</button>
    <button class="jp-btn jp-btn-sm" onclick="JP.importUrl()" title="Fetch JSON from URL">URL Import</button>
    <div style="position:relative">
      <button class="jp-btn jp-btn-sm" onclick="JP.toggleHistory()" title="Recent inputs">History</button>
      <div id="jpHistoryList" class="jp-history-list"></div>
    </div>
    <div class="jp-topbar-right">
      <span style="font-size:0.72rem;color:var(--jp-text-dim)">Ctrl+Enter: Format &middot; Ctrl+Shift+M: Minify</span>
      <button class="jp-btn jp-btn-sm" onclick="JP.toggleTheme()" id="jpThemeBtn" title="Toggle dark/light theme">Light</button>
    </div>
  </div>

  <!-- Tab bar -->
  <div class="jp-tabs" id="jpTabs">
    <button class="jp-tab active" data-tab="format">Format &amp; Validate</button>
    <button class="jp-tab" data-tab="tree">Tree Viewer</button>
    <button class="jp-tab" data-tab="diff">JSON Diff</button>
    <button class="jp-tab" data-tab="query">JSONPath Query</button>
    <button class="jp-tab" data-tab="transform">Transform</button>
    <button class="jp-tab" data-tab="schema">Schema Validator</button>
  </div>

  <!-- ====== TAB 1: Format & Validate ====== -->
  <div class="jp-panel active" id="jpPanelFormat">
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:12px">
      <button class="jp-btn jp-btn-primary" onclick="JP.format()">Format</button>
      <button class="jp-btn" onclick="JP.minify()">Minify</button>
      <select id="jpIndent" class="jp-select" title="Indent size">
        <option value="2">2 spaces</option>
        <option value="4">4 spaces</option>
        <option value="tab">Tab</option>
      </select>
      <label style="font-size:0.8rem;color:var(--jp-text-muted);display:inline-flex;align-items:center;gap:4px;cursor:pointer">
        <input type="checkbox" id="jpSortKeys"> Sort keys
      </label>
      <button class="jp-btn" onclick="JP.copyOutput('jpFmtOutput')" id="jpFmtCopyBtn">Copy</button>
      <div style="flex:1"></div>
      <button class="jp-btn jp-btn-sm" onclick="JP.clearFormat()">Clear</button>
    </div>
    <div id="jpFmtError" class="jp-error-detail"></div>
    <div class="jp-grid2">
      <div class="jp-editor-box">
        <div class="jp-editor-header">
          <span>Input</span>
          <span id="jpFmtInputSize">0 B</span>
        </div>
        <textarea id="jpFmtInput" class="jp-textarea" placeholder='Paste JSON here...' spellcheck="false"></textarea>
      </div>
      <div class="jp-editor-box">
        <div class="jp-editor-header">
          <span>Output</span>
          <span id="jpFmtOutputSize">0 B</span>
        </div>
        <div id="jpFmtOutput" class="jp-output"></div>
      </div>
    </div>
    <div class="jp-status">
      <div id="jpFmtStatus" class="jp-status-msg jp-status-empty">Paste JSON and format</div>
      <div class="jp-stats">
        <span>Chars: <strong id="jpFmtChars">0</strong></span>
        <span>Lines: <strong id="jpFmtLines">0</strong></span>
        <span>Keys: <strong id="jpFmtKeys">0</strong></span>
        <span>Depth: <strong id="jpFmtDepth">0</strong></span>
        <span>Size: <strong id="jpFmtBytes">0 B</strong></span>
      </div>
    </div>
  </div>

  <!-- ====== TAB 2: Tree Viewer ====== -->
  <div class="jp-panel" id="jpPanelTree">
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:12px">
      <button class="jp-btn jp-btn-primary" onclick="JP.buildTree()">Build Tree</button>
      <button class="jp-btn" onclick="JP.expandAll()">Expand All</button>
      <button class="jp-btn" onclick="JP.collapseAll()">Collapse All</button>
      <div style="flex:1"></div>
      <button class="jp-btn jp-btn-sm" onclick="JP.clearTree()">Clear</button>
    </div>
    <div class="jp-grid-side">
      <div>
        <div class="jp-editor-box">
          <div class="jp-editor-header"><span>Input JSON</span></div>
          <textarea id="jpTreeInput" class="jp-textarea" placeholder="Paste JSON here..." spellcheck="false" style="min-height:200px"></textarea>
        </div>
        <input type="text" id="jpTreeSearch" class="jp-tree-search" placeholder="Search in tree...">
        <div id="jpTreePath" class="jp-tree-path">Click a node to see its path</div>
        <div class="jp-editor-box">
          <div class="jp-editor-header"><span>Tree View</span></div>
          <div id="jpTreeOutput" class="jp-tree">Parse JSON to view tree</div>
        </div>
      </div>
      <div>
        <div class="jp-editor-box" style="position:sticky;top:16px">
          <div class="jp-editor-header"><span>Node Value</span>
            <button class="jp-btn jp-btn-sm" onclick="JP.copyOutput('jpTreeValue')">Copy</button>
          </div>
          <div id="jpTreeValue" class="jp-output" style="min-height:200px;font-size:0.78rem"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- ====== TAB 3: JSON Diff ====== -->
  <div class="jp-panel" id="jpPanelDiff">
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:12px">
      <button class="jp-btn jp-btn-primary" onclick="JP.runDiff()">Compare</button>
      <div class="jp-diff-nav">
        <button class="jp-btn jp-btn-sm" onclick="JP.diffNav(-1)">Prev</button>
        <span id="jpDiffPos" style="font-size:0.78rem;color:var(--jp-text-muted)">0/0</span>
        <button class="jp-btn jp-btn-sm" onclick="JP.diffNav(1)">Next</button>
      </div>
      <button class="jp-btn" onclick="JP.swapDiff()">Swap</button>
      <div style="flex:1"></div>
      <button class="jp-btn jp-btn-sm" onclick="JP.clearDiff()">Clear</button>
    </div>
    <div class="jp-grid2" style="margin-bottom:12px">
      <div class="jp-editor-box">
        <div class="jp-editor-header"><span>Left (Original)</span></div>
        <textarea id="jpDiffLeft" class="jp-textarea" placeholder="Paste original JSON..." spellcheck="false" style="min-height:240px"></textarea>
      </div>
      <div class="jp-editor-box">
        <div class="jp-editor-header"><span>Right (Modified)</span></div>
        <textarea id="jpDiffRight" class="jp-textarea" placeholder="Paste modified JSON..." spellcheck="false" style="min-height:240px"></textarea>
      </div>
    </div>
    <div id="jpDiffSummary" class="jp-diff-summary" style="display:none">
      <span style="color:var(--jp-add)">+<strong id="jpDiffAdds">0</strong> additions</span>
      <span style="color:var(--jp-del)">-<strong id="jpDiffDels">0</strong> deletions</span>
      <span style="color:var(--jp-mod)">~<strong id="jpDiffMods">0</strong> modifications</span>
    </div>
    <div id="jpDiffOutput" class="jp-diff-output" style="min-height:100px"></div>
  </div>

  <!-- ====== TAB 4: JSONPath Query ====== -->
  <div class="jp-panel" id="jpPanelQuery">
    <div class="jp-grid-side">
      <div>
        <div class="jp-editor-box">
          <div class="jp-editor-header"><span>Input JSON</span></div>
          <textarea id="jpQueryInput" class="jp-textarea" placeholder="Paste JSON here..." spellcheck="false" style="min-height:220px"></textarea>
        </div>
        <div style="margin-bottom:12px">
          <label style="font-size:0.78rem;color:var(--jp-text-muted);display:block;margin-bottom:4px">JSONPath Expression</label>
          <input type="text" id="jpQueryExpr" style="width:100%;padding:9px 12px;border:1px solid var(--jp-border);border-radius:var(--jp-radius-sm);font-family:var(--jp-mono);font-size:0.85rem;background:var(--jp-surface);color:var(--jp-text);outline:none" placeholder="$.store.book[*].author" spellcheck="false">
        </div>
        <div class="jp-editor-box">
          <div class="jp-editor-header"><span>Results</span>
            <button class="jp-btn jp-btn-sm" onclick="JP.copyOutput('jpQueryResult')">Copy</button>
          </div>
          <div id="jpQueryResult" class="jp-output" style="min-height:200px"></div>
        </div>
      </div>
      <div>
        <div class="jp-editor-box" style="position:sticky;top:16px">
          <div class="jp-editor-header"><span>JSONPath Reference</span></div>
          <div style="padding:10px;overflow:auto;max-height:600px">
            <table class="jp-ref-table">
              <tr><th>Expression</th><th>Description</th></tr>
              <tr><td><code>$</code></td><td>Root object</td></tr>
              <tr><td><code>.key</code></td><td>Child property</td></tr>
              <tr><td><code>['key']</code></td><td>Child (bracket)</td></tr>
              <tr><td><code>[0]</code></td><td>Array index</td></tr>
              <tr><td><code>[*]</code></td><td>All elements</td></tr>
              <tr><td><code>..</code></td><td>Recursive descent</td></tr>
              <tr><td><code>[0,1]</code></td><td>Multiple indices</td></tr>
              <tr><td><code>[0:3]</code></td><td>Array slice</td></tr>
              <tr><td><code>[?()]</code></td><td>Filter expression</td></tr>
              <tr><td><code>@</code></td><td>Current node (in filter)</td></tr>
            </table>
            <div style="margin-top:14px;font-size:0.75rem;color:var(--jp-text-muted)">
              <div style="font-weight:600;margin-bottom:6px;color:var(--jp-text)">Examples</div>
              <div style="margin-bottom:3px;cursor:pointer;color:var(--jp-primary-light)" onclick="document.getElementById('jpQueryExpr').value='$.store.book[*].author';JP.runQuery()"><code>$.store.book[*].author</code></div>
              <div style="margin-bottom:3px;cursor:pointer;color:var(--jp-primary-light)" onclick="document.getElementById('jpQueryExpr').value='$..price';JP.runQuery()"><code>$..price</code></div>
              <div style="margin-bottom:3px;cursor:pointer;color:var(--jp-primary-light)" onclick="document.getElementById('jpQueryExpr').value='$.store.book[?(@.price<10)]';JP.runQuery()"><code>$.store.book[?(@.price&lt;10)]</code></div>
              <div style="margin-bottom:3px;cursor:pointer;color:var(--jp-primary-light)" onclick="document.getElementById('jpQueryExpr').value='$.store.book[0:2]';JP.runQuery()"><code>$.store.book[0:2]</code></div>
              <div style="margin-bottom:3px;cursor:pointer;color:var(--jp-primary-light)" onclick="document.getElementById('jpQueryExpr').value='$..book[?(@.isbn)]';JP.runQuery()"><code>$..book[?(@.isbn)]</code></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ====== TAB 5: Transform ====== -->
  <div class="jp-panel" id="jpPanelTransform">
    <div class="jp-editor-box" style="margin-bottom:12px">
      <div class="jp-editor-header"><span>Input JSON</span></div>
      <textarea id="jpTransInput" class="jp-textarea" placeholder="Paste JSON here..." spellcheck="false" style="min-height:200px"></textarea>
    </div>
    <div class="jp-transform-btns">
      <button class="jp-btn jp-btn-primary" onclick="JP.toCsv()">To CSV</button>
      <button class="jp-btn" onclick="JP.toYaml()">To YAML</button>
      <button class="jp-btn" onclick="JP.toXml()">To XML</button>
      <button class="jp-btn" onclick="JP.toTypescript()">To TypeScript</button>
      <button class="jp-btn" onclick="JP.toTable()">To Table</button>
      <button class="jp-btn" onclick="JP.flattenJson()">Flatten</button>
      <button class="jp-btn" onclick="JP.pickKeys()">Pick Keys</button>
      <button class="jp-btn" onclick="JP.omitKeys()">Omit Keys</button>
      <div style="flex:1"></div>
      <button class="jp-btn jp-btn-sm" onclick="JP.copyOutput('jpTransOutput')">Copy</button>
    </div>
    <div id="jpTransTable" class="jp-table-view" style="display:none"></div>
    <div id="jpTransOutput" class="jp-transform-out"></div>
  </div>

  <!-- ====== TAB 6: Schema Validator ====== -->
  <div class="jp-panel" id="jpPanelSchema">
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:12px">
      <button class="jp-btn jp-btn-primary" onclick="JP.validateSchema()">Validate</button>
      <button class="jp-btn" onclick="JP.loadSampleSchema()">Load Sample Schema</button>
      <div style="flex:1"></div>
      <button class="jp-btn jp-btn-sm" onclick="JP.clearSchema()">Clear</button>
    </div>
    <div class="jp-grid2" style="margin-bottom:12px">
      <div class="jp-editor-box">
        <div class="jp-editor-header"><span>JSON Data</span></div>
        <textarea id="jpSchemaData" class="jp-textarea" placeholder="Paste JSON data to validate..." spellcheck="false" style="min-height:260px"></textarea>
      </div>
      <div class="jp-editor-box">
        <div class="jp-editor-header"><span>JSON Schema</span></div>
        <textarea id="jpSchemaInput" class="jp-textarea" placeholder="Paste JSON Schema (draft-07)..." spellcheck="false" style="min-height:260px"></textarea>
      </div>
    </div>
    <div class="jp-editor-box">
      <div class="jp-editor-header"><span>Validation Results</span></div>
      <div id="jpSchemaResults" class="jp-schema-errors">Run validation to see results</div>
    </div>
  </div>

</div>

<!-- Content Section -->
<div class="jp-wrap">
  <div class="jp-content">

<h2>What Is JSON</h2>

<p>JSON (JavaScript Object Notation) is a lightweight text format for structuring data. It uses key-value pairs inside curly braces for objects, square brackets for arrays, and supports strings, numbers, booleans, and null as primitive values. Despite the name, JSON is language-independent. Almost every programming language has built-in or standard-library support for reading and writing it.</p>

<p>JSON became the default data interchange format for web APIs because it is smaller than XML, easier to read than binary protocols, and maps directly to native data structures in most languages. Configuration files, database exports, log events, and message queues all commonly use JSON. A typical REST API request or response body is JSON, and frontend frameworks like React, Vue, and Angular all consume JSON endpoints. Package managers (npm, pip, Cargo) use JSON for manifest files. Infrastructure tools like Terraform output JSON plans. Even NoSQL databases like MongoDB store documents in a JSON-like format called BSON.</p>

<p>The format has a few strict rules that trip people up. Keys must be double-quoted strings. Trailing commas after the last element in an array or object are not allowed. Single quotes are invalid. Comments are not part of the specification (though JSONC, a superset used by VS Code and TypeScript configs, permits them). This formatter strips comments automatically so you can paste JSONC content and get valid JSON output.</p>

<h2>JSON Formatting and Validation</h2>

<p>Formatting (also called pretty-printing or beautifying) takes compressed JSON and adds consistent indentation and line breaks. The result is the same data, just structured for human eyes. Developers format JSON when debugging API responses, reviewing configuration, or preparing documentation examples.</p>

<p>Validation is the process of checking whether a string is legal JSON. The most common errors are missing commas between elements, trailing commas after the last element, unquoted keys, single-quoted strings, and mismatched brackets. This tool reports the exact line and column of the first syntax error so you can fix it quickly.</p>

<p>Minification is the inverse of formatting. It strips all whitespace that is not inside string values, producing the smallest possible representation. Minified JSON reduces payload size for API responses, configuration files, and stored data. On deeply nested documents the savings can reach 40-60 percent.</p>

<p>The Format and Validate tab in this tool handles all three operations. Choose your indentation (2 spaces, 4 spaces, or tabs), optionally sort keys alphabetically for consistent ordering, and get syntax-highlighted output with character, line, and byte counts. Sorting keys is particularly useful when you need to compare two JSON objects visually or when storing JSON in version control where consistent key order reduces diff noise.</p>

<p>The syntax highlighting follows a color scheme inspired by popular code editors: keys appear in cyan, strings in green, numbers in purple, booleans in orange, and null values in red. This color coding makes it much easier to scan a large document and spot the values you are looking for without reading every line.</p>

<h2>Comparing JSON Documents</h2>

<p>Comparing two JSON documents by eye is tedious and error-prone, especially when the documents are large or deeply nested. The JSON Diff tab solves this by parsing both inputs and performing a structural comparison. It identifies three types of changes: additions (keys or values present only in the right document), deletions (present only in the left), and modifications (same key, different value).</p>

<p>The diff output uses color coding: green for additions, red for deletions, and yellow for modifications. A summary bar shows the count of each type, and navigation buttons let you jump between changes without scrolling. This is useful for comparing API response versions, reviewing configuration changes, or verifying that a data migration preserved the right values.</p>

<p>The comparison works on the parsed structure, not the raw text. That means differences in whitespace, key ordering, or formatting do not produce false positives. Two documents that contain the same data in different orders will show zero differences. The swap button lets you reverse the left and right inputs without copy-pasting, which is handy when you want to view the same changes from the opposite direction.</p>

<h2>JSONPath Query Language</h2>

<p>JSONPath is a query language for extracting data from JSON documents, similar to how XPath works for XML. The root element is referenced with <code>$</code>, dot notation accesses child properties, bracket notation handles special characters in keys, and recursive descent (<code>..</code>) searches at all levels of nesting.</p>

<p>Common use cases include extracting all values of a specific field from an array of objects (<code>$.users[*].email</code>), filtering array elements by a condition (<code>$.products[?(@.price &lt; 50)]</code>), and reaching deeply nested values without spelling out the full path (<code>$..id</code>).</p>

<p>The JSONPath Query tab evaluates expressions against your JSON in real time as you type. A reference sidebar lists the supported syntax, and clickable examples fill in the expression field so you can experiment immediately. The implementation supports dot notation, bracket notation, wildcards, array slicing, recursive descent, and filter expressions with comparison operators.</p>

<h2>JSON Schema Validation</h2>

<p>JSON Schema is a vocabulary for describing the structure and constraints of JSON documents. It defines what keys are allowed, what types each value should be, which fields are required, and what ranges or patterns values must match. Schemas are themselves written in JSON.</p>

<p>The Schema Validator tab supports the most commonly used keywords from JSON Schema draft-07: <code>type</code>, <code>properties</code>, <code>required</code>, <code>items</code>, <code>enum</code>, <code>minimum</code>, <code>maximum</code>, <code>minLength</code>, <code>maxLength</code>, and <code>pattern</code>. When validation fails, it lists every error with the path to the offending value, making it straightforward to fix problems one by one.</p>

<p>Schema validation is valuable during API development (verify request and response bodies match the contract), configuration management (catch typos and invalid values before deployment), and data pipeline processing (reject malformed records at ingestion). Writing a schema once saves hours of debugging later.</p>

<h2>Converting JSON to Other Formats</h2>

<p>JSON is convenient for machines but not always the best format for every situation. The Transform tab converts JSON to five other formats.</p>

<ul>
<li>CSV conversion takes an array of objects and produces comma-separated values with a header row. This is the fastest way to get API data into a spreadsheet.</li>
<li>YAML conversion produces a human-friendly format often used for configuration files in Docker, Kubernetes, and CI/CD pipelines.</li>
<li>XML conversion wraps values in element tags, useful when integrating with legacy systems or SOAP APIs that require XML.</li>
<li>TypeScript interface generation reads the structure and types of a JSON object and produces a TypeScript interface definition, saving manual typing when defining API response types.</li>
<li>Table view renders arrays of objects as an HTML table for quick visual inspection.</li>
</ul>

<p>Additional utilities include flattening nested JSON into a single-level object with dot-notation keys, and picking or omitting specific keys from objects. Flattening is useful when you need to index nested data into a flat database table or when building search indices that require single-level documents. The pick and omit operations let you strip sensitive fields (like passwords or tokens) from JSON before sharing it, or extract just the fields you need from a large API response.</p>

<p>All transformations happen locally in your browser. The output appears in a code block that you can copy with one click. For CSV and table conversions, the input should be an array of objects with consistent keys across rows. For YAML, XML, and TypeScript generation, any valid JSON structure works as input.</p>

  </div>

  <!-- FAQ -->
  <div class="jp-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="jp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is this JSON formatter safe to use with sensitive data?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All processing happens in your browser using JavaScript. No data is sent to any server, stored in any database, or logged anywhere. You can verify this by opening your browser's developer tools and watching the Network tab while using the tool. This makes it safe for API keys, tokens, credentials, and any other confidential payloads.</p>
      </div>
    </div>

    <div class="jp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between JSON and JSONC?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">JSONC (JSON with Comments) is a superset of JSON that allows single-line comments (// ...) and multi-line comments (/* ... */). VS Code settings files and TypeScript configuration files use JSONC. Standard JSON parsers reject comments, so this tool strips them before parsing, letting you paste JSONC content directly and get valid JSON output.</p>
      </div>
    </div>

    <div class="jp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does the JSON diff comparison work?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The diff tool parses both JSON inputs into objects, then walks their structures recursively. It identifies additions (keys present only on the right), deletions (only on the left), and modifications (same key, different value). Because it compares parsed structures rather than raw text, differences in whitespace or key ordering do not trigger false positives.</p>
      </div>
    </div>

    <div class="jp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What JSONPath expressions are supported?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool supports root access ($), dot notation ($.key), bracket notation ($['key']), array indexing ([0]), wildcards ([*]), recursive descent (..), array slicing ([0:3]), union ([0,1]), and filter expressions ([?(@.price &lt; 10)]). Filter expressions support comparison operators (&lt;, &gt;, &lt;=, &gt;=, ==, !=) and the current-node reference (@).</p>
      </div>
    </div>

    <div class="jp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Which JSON Schema keywords does the validator support?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The schema validator supports the most commonly used draft-07 keywords: type (string, number, integer, boolean, null, array, object), properties, required, items, enum, minimum, maximum, minLength, maxLength, and pattern. These cover the vast majority of real-world schema validation needs for API contracts and configuration files.</p>
      </div>
    </div>

    <div class="jp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can this tool handle large JSON files?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool works well with files up to about 5-10 MB, depending on your browser and device. Beyond that, the browser's JSON parser and DOM rendering may become slow. For very large files, consider using a command-line tool like jq. For typical API responses, configuration files, and data exports under a few megabytes, this formatter handles them without issues.</p>
      </div>
    </div>

  </div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter/" style="color:#00ff88;text-decoration:none;">JSON Formatter</a> - Format and validate JSON data</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/csv-to-json-converter/" style="color:#00ff88;text-decoration:none;">CSV to JSON Converter</a> - Convert CSV data to JSON format</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/diff-checker/" style="color:#00ff88;text-decoration:none;">Diff Checker</a> - Compare two texts side by side</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/jwt-decoder/" style="color:#00ff88;text-decoration:none;">JWT Decoder</a> - Decode and inspect JSON Web Tokens</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/regex-tester/" style="color:#00ff88;text-decoration:none;">Regex Tester</a> - Test regular expressions with live highlighting</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>


  <footer class="jp-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>
</div>

<script>
(function() {
"use strict";

var SAMPLE = JSON.stringify({
  store: {
    name: "TechBooks Central",
    location: { city: "San Francisco", state: "CA", zip: "94102" },
    book: [
      { title: "Clean Code", author: "Robert C. Martin", category: "programming", price: 32.99, isbn: "978-0132350884", inStock: true },
      { title: "The Pragmatic Programmer", author: "David Thomas", category: "programming", price: 44.95, isbn: "978-0135957059", inStock: true },
      { title: "Designing Data-Intensive Applications", author: "Martin Kleppmann", category: "systems", price: 38.49, isbn: "978-1449373320", inStock: false },
      { title: "Refactoring", author: "Martin Fowler", category: "programming", price: 41.99, inStock: true }
    ],
    magazine: [
      { title: "IEEE Software", price: 12.99, monthly: true },
      { title: "ACM Queue", price: 0, monthly: false }
    ]
  },
  metadata: { version: 3, generated: "2026-03-19T10:30:00Z", count: 6 }
}, null, 2);

var SAMPLE_SCHEMA = JSON.stringify({
  type: "object",
  required: ["name", "email", "age"],
  properties: {
    name: { type: "string", minLength: 1, maxLength: 100 },
    email: { type: "string", pattern: "^[^@]+@[^@]+\\.[^@]+$" },
    age: { type: "integer", minimum: 0, maximum: 150 },
    role: { type: "string", enum: ["admin", "user", "editor"] },
    tags: { type: "array", items: { type: "string" } },
    address: {
      type: "object",
      properties: {
        street: { type: "string" },
        city: { type: "string" },
        zip: { type: "string", pattern: "^\\d{5}$" }
      },
      required: ["street", "city"]
    }
  }
}, null, 2);

var SAMPLE_SCHEMA_DATA = JSON.stringify({
  name: "Jane Smith",
  email: "jane@example.com",
  age: 29,
  role: "admin",
  tags: ["developer", "lead"],
  address: { street: "123 Main St", city: "Portland", zip: "97201" }
}, null, 2);

var history = [];
try { history = JSON.parse(localStorage.getItem('jp_history') || '[]'); } catch(e) {}

// --- Utility ---
function $(id) { return document.getElementById(id); }
function esc(s) { return s.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }
function byteSize(s) { return new Blob([s]).size; }
function fmtBytes(b) {
  if (b===0) return '0 B';
  if (b<1024) return b+' B';
  if (b<1048576) return (b/1024).toFixed(1)+' KB';
  return (b/1048576).toFixed(2)+' MB';
}
function countKeys(o) {
  var c=0;
  if (o && typeof o==='object') {
    if (Array.isArray(o)) { for(var i=0;i<o.length;i++) c+=countKeys(o[i]); }
    else { var ks=Object.keys(o); c+=ks.length; for(var j=0;j<ks.length;j++) c+=countKeys(o[ks[j]]); }
  }
  return c;
}
function maxDepth(o) {
  if (o===null||typeof o!=='object') return 0;
  var m=0, vals=Array.isArray(o)?o:Object.keys(o).map(function(k){return o[k]});
  for (var i=0;i<vals.length;i++) { var d=maxDepth(vals[i]); if(d>m) m=d; }
  return 1+m;
}
function posToLine(s,p) {
  var l=1,c=1;
  for(var i=0;i<p&&i<s.length;i++){if(s[i]==='\n'){l++;c=1}else c++}
  return {line:l,col:c};
}
function parseErr(e,s) {
  var msg=e.message||'Unknown error', r={message:msg,line:null,col:null};
  var pm=msg.match(/position\s+(\d+)/i)||msg.match(/column\s+(\d+)/i);
  var lm=msg.match(/line\s+(\d+)/i);
  if(pm){var loc=posToLine(s,parseInt(pm[1],10));r.line=loc.line;r.col=loc.col}
  else if(lm) r.line=parseInt(lm[1],10);
  return r;
}
function stripComments(s) {
  return s.replace(/\/\/.*$/gm,'').replace(/\/\*[\s\S]*?\*\//g,'');
}
function sortKeysDeep(o) {
  if(o===null||typeof o!=='object') return o;
  if(Array.isArray(o)) return o.map(sortKeysDeep);
  var sorted={};
  Object.keys(o).sort().forEach(function(k){sorted[k]=sortKeysDeep(o[k])});
  return sorted;
}
function syntaxHL(s) {
  s = s.replace(/("(?:[^"\\]|\\.)*")\s*:/g, '<span class="jps-key">$1</span>:');
  s = s.replace(/:\s*("(?:[^"\\]|\\.)*")/g, ': <span class="jps-str">$1</span>');
  s = s.replace(/([\[,\n]\s*)("(?:[^"\\]|\\.)*")(\s*[,\]\n])/g, '$1<span class="jps-str">$2</span>$3');
  s = s.replace(/:\s*(-?\d+(?:\.\d+)?(?:[eE][+-]?\d+)?)/g, ': <span class="jps-num">$1</span>');
  s = s.replace(/([\[,\n]\s*)(-?\d+(?:\.\d+)?(?:[eE][+-]?\d+)?)(\s*[,\]\n])/g, '$1<span class="jps-num">$2</span>$3');
  s = s.replace(/:\s*(true|false)/g, ': <span class="jps-bool">$1</span>');
  s = s.replace(/([\[,\n]\s*)(true|false)(\s*[,\]\n])/g, '$1<span class="jps-bool">$2</span>$3');
  s = s.replace(/:\s*(null)/g, ': <span class="jps-null">$1</span>');
  s = s.replace(/([\[,\n]\s*)(null)(\s*[,\]\n])/g, '$1<span class="jps-null">$2</span>$3');
  return s;
}
function safeParse(raw) {
  var cleaned = stripComments(raw.trim());
  return JSON.parse(cleaned);
}
function addHistory(s) {
  if(!s||s.length<3) return;
  var preview = s.substring(0,120);
  history = history.filter(function(h){return h!==preview});
  history.unshift(preview);
  if(history.length>5) history=history.slice(0,5);
  try{localStorage.setItem('jp_history',JSON.stringify(history))}catch(e){}
}

// --- Tab switching ---
var tabs = document.querySelectorAll('.jp-tab');
var panels = {
  format: $('jpPanelFormat'), tree: $('jpPanelTree'), diff: $('jpPanelDiff'),
  query: $('jpPanelQuery'), transform: $('jpPanelTransform'), schema: $('jpPanelSchema')
};
tabs.forEach(function(t) {
  t.addEventListener('click', function() {
    tabs.forEach(function(x){x.classList.remove('active')});
    t.classList.add('active');
    Object.keys(panels).forEach(function(k){panels[k].classList.remove('active')});
    panels[t.getAttribute('data-tab')].classList.add('active');
  });
});

// --- Format & Validate ---
window.JP = {};

JP.format = function() {
  var raw=$('jpFmtInput').value;
  $('jpFmtError').style.display='none';
  if(!raw.trim()){JP._fmtStatus('empty','Paste JSON and format');$('jpFmtOutput').textContent='';JP._fmtStats(null,'');return}
  try {
    var ind=$('jpIndent').value;
    var indent = ind==='tab' ? '\t' : parseInt(ind,10);
    var parsed=safeParse(raw);
    if($('jpSortKeys').checked) parsed=sortKeysDeep(parsed);
    var out=JSON.stringify(parsed,null,indent);
    $('jpFmtOutput').innerHTML=syntaxHL(esc(out));
    $('jpFmtOutput').setAttribute('data-text',out);
    JP._fmtStatus('valid','Valid JSON -- formatted');
    JP._fmtStats(parsed,out);
    addHistory(raw);
  } catch(e) {
    var info=parseErr(e,raw);
    JP._fmtStatus('invalid','Invalid JSON');
    var parts=[];
    if(info.line)parts.push('Line '+info.line);
    if(info.col)parts.push('Col '+info.col);
    $('jpFmtError').textContent=(parts.length?parts.join(', ')+': ':'')+info.message;
    $('jpFmtError').style.display='block';
    $('jpFmtOutput').textContent='';
    JP._fmtStats(null,'');
  }
  $('jpFmtInputSize').textContent=fmtBytes(byteSize(raw));
};
JP.minify = function() {
  var raw=$('jpFmtInput').value;
  $('jpFmtError').style.display='none';
  if(!raw.trim()){JP._fmtStatus('empty','Paste JSON and minify');$('jpFmtOutput').textContent='';JP._fmtStats(null,'');return}
  try {
    var parsed=safeParse(raw);
    var out=JSON.stringify(parsed);
    $('jpFmtOutput').innerHTML=syntaxHL(esc(out));
    $('jpFmtOutput').setAttribute('data-text',out);
    JP._fmtStatus('valid','Valid JSON -- minified');
    JP._fmtStats(parsed,out);
    addHistory(raw);
  } catch(e) {
    var info=parseErr(e,raw);
    JP._fmtStatus('invalid','Invalid JSON');
    var parts=[];
    if(info.line)parts.push('Line '+info.line);
    if(info.col)parts.push('Col '+info.col);
    $('jpFmtError').textContent=(parts.length?parts.join(', ')+': ':'')+info.message;
    $('jpFmtError').style.display='block';
    $('jpFmtOutput').textContent='';
    JP._fmtStats(null,'');
  }
  $('jpFmtInputSize').textContent=fmtBytes(byteSize(raw));
};
JP._fmtStatus = function(t,m) {
  var el=$('jpFmtStatus');
  el.className='jp-status-msg';
  if(t==='valid'){el.classList.add('jp-status-valid');el.textContent='\u2713 '+m}
  else if(t==='invalid'){el.classList.add('jp-status-invalid');el.textContent='\u2717 '+m}
  else{el.classList.add('jp-status-empty');el.textContent=m}
};
JP._fmtStats = function(parsed,out) {
  if(!parsed){$('jpFmtChars').textContent='0';$('jpFmtLines').textContent='0';$('jpFmtKeys').textContent='0';$('jpFmtDepth').textContent='0';$('jpFmtBytes').textContent='0 B';$('jpFmtOutputSize').textContent='0 B';return}
  $('jpFmtChars').textContent=out.length;
  $('jpFmtLines').textContent=out.split('\n').length;
  $('jpFmtKeys').textContent=countKeys(parsed);
  $('jpFmtDepth').textContent=maxDepth(parsed);
  $('jpFmtBytes').textContent=fmtBytes(byteSize(out));
  $('jpFmtOutputSize').textContent=fmtBytes(byteSize(out));
};
JP.clearFormat = function() {
  $('jpFmtInput').value='';$('jpFmtOutput').innerHTML='';$('jpFmtOutput').removeAttribute('data-text');
  $('jpFmtError').style.display='none';JP._fmtStatus('empty','Paste JSON and format');JP._fmtStats(null,'');
  $('jpFmtInputSize').textContent='0 B';
};

// --- Tree Viewer ---
JP.buildTree = function() {
  var raw=$('jpTreeInput').value;
  if(!raw.trim()){$('jpTreeOutput').textContent='Paste JSON and click Build Tree';return}
  try {
    var parsed=safeParse(raw);
    $('jpTreeOutput').innerHTML='';
    JP._treeData=parsed;
    JP._renderTree(parsed,'$',$('jpTreeOutput'),true);
    addHistory(raw);
  } catch(e) {
    $('jpTreeOutput').textContent='Error: '+e.message;
  }
};
JP._treeData=null;
JP._renderTree = function(val,path,parent,open) {
  if(val===null) {
    var sp=document.createElement('div');
    sp.innerHTML='<span class="jp-tree-null">null</span><span class="jp-tree-type">null</span>';
    sp.style.cursor='pointer';
    sp.onclick=function(e){e.stopPropagation();JP._treeSel(path,val)};
    parent.appendChild(sp);
    return;
  }
  if(typeof val!=='object') {
    var sp=document.createElement('div');
    var cls=typeof val==='string'?'jp-tree-str':typeof val==='number'?'jp-tree-num':'jp-tree-bool';
    var display=typeof val==='string'?'"'+esc(val)+'"':String(val);
    sp.innerHTML='<span class="'+cls+'">'+display+'</span><span class="jp-tree-type">'+typeof val+'</span>';
    sp.style.cursor='pointer';
    sp.onclick=function(e){e.stopPropagation();JP._treeSel(path,val)};
    parent.appendChild(sp);
    return;
  }
  var isArr=Array.isArray(val);
  var keys=isArr?val:Object.keys(val);
  var len=isArr?val.length:Object.keys(val).length;
  var wrap=document.createElement('div');
  var tog=document.createElement('span');
  tog.className='jp-tree-toggle';
  tog.textContent=open?'\u25BC':'\u25B6';
  wrap.appendChild(tog);
  var label=document.createElement('span');
  label.style.color='var(--jp-text-muted)';
  label.style.fontSize='0.78rem';
  label.textContent=(isArr?'Array':'Object')+'('+len+')';
  label.style.cursor='pointer';
  label.onclick=function(e){e.stopPropagation();JP._treeSel(path,val)};
  wrap.appendChild(label);
  parent.appendChild(wrap);
  var children=document.createElement('div');
  children.className='jp-tree-node';
  children.style.display=open?'block':'none';
  var kk=isArr?val.map(function(_,i){return i}):Object.keys(val);
  kk.forEach(function(k) {
    var row=document.createElement('div');
    var keySpan=document.createElement('span');
    keySpan.className='jp-tree-key';
    keySpan.textContent=isArr?'['+k+']':k+': ';
    var childPath=isArr?path+'['+k+']':path+'.'+k;
    keySpan.onclick=function(e){e.stopPropagation();JP._treeSel(childPath,isArr?val[k]:val[k])};
    row.appendChild(keySpan);
    var childVal=isArr?val[k]:val[k];
    if(childVal!==null&&typeof childVal==='object') {
      JP._renderTree(childVal,childPath,row,false);
    } else {
      var inline=document.createElement('span');
      if(childVal===null){inline.className='jp-tree-null';inline.textContent='null'}
      else if(typeof childVal==='string'){inline.className='jp-tree-str';inline.textContent='"'+esc(childVal)+'"'}
      else if(typeof childVal==='number'){inline.className='jp-tree-num';inline.textContent=childVal}
      else if(typeof childVal==='boolean'){inline.className='jp-tree-bool';inline.textContent=childVal}
      inline.style.cursor='pointer';
      inline.onclick=function(e){e.stopPropagation();JP._treeSel(childPath,childVal)};
      row.appendChild(inline);
    }
    children.appendChild(row);
  });
  parent.appendChild(children);
  tog.onclick=function(e) {
    e.stopPropagation();
    var shown=children.style.display!=='none';
    children.style.display=shown?'none':'block';
    tog.textContent=shown?'\u25B6':'\u25BC';
  };
};
JP._treeSel = function(path,val) {
  $('jpTreePath').textContent=path;
  var display = typeof val==='object'?JSON.stringify(val,null,2):String(val);
  $('jpTreeValue').textContent=display;
  $('jpTreeValue').setAttribute('data-text',display);
};
JP.expandAll = function() {
  var nodes=$('jpTreeOutput').querySelectorAll('.jp-tree-node');
  nodes.forEach(function(n){n.style.display='block'});
  var togs=$('jpTreeOutput').querySelectorAll('.jp-tree-toggle');
  togs.forEach(function(t){t.textContent='\u25BC'});
};
JP.collapseAll = function() {
  var nodes=$('jpTreeOutput').querySelectorAll('.jp-tree-node');
  nodes.forEach(function(n){n.style.display='none'});
  var togs=$('jpTreeOutput').querySelectorAll('.jp-tree-toggle');
  togs.forEach(function(t){t.textContent='\u25B6'});
};
JP.clearTree = function() {
  $('jpTreeInput').value='';$('jpTreeOutput').textContent='Parse JSON to view tree';
  $('jpTreePath').textContent='Click a node to see its path';$('jpTreeValue').textContent='';
  $('jpTreeSearch').value='';
};
// Tree search
$('jpTreeSearch').addEventListener('input',function() {
  var q=this.value.toLowerCase();
  var tree=$('jpTreeOutput');
  // remove old highlights
  tree.querySelectorAll('.jp-tree-highlight').forEach(function(el){
    el.classList.remove('jp-tree-highlight');
  });
  if(!q) return;
  // expand all first
  JP.expandAll();
  // highlight matching text nodes
  var walk=document.createTreeWalker(tree,NodeFilter.SHOW_TEXT,null,false);
  while(walk.nextNode()) {
    var n=walk.currentNode;
    if(n.textContent.toLowerCase().indexOf(q)!==-1 && n.parentElement) {
      n.parentElement.classList.add('jp-tree-highlight');
    }
  }
});

// --- JSON Diff ---
var diffChanges=[], diffIdx=-1;
JP.runDiff = function() {
  var lRaw=$('jpDiffLeft').value, rRaw=$('jpDiffRight').value;
  if(!lRaw.trim()||!rRaw.trim()){$('jpDiffOutput').innerHTML='<div style="padding:14px;color:var(--jp-text-muted)">Paste JSON into both editors and click Compare</div>';$('jpDiffSummary').style.display='none';return}
  try {
    var left=safeParse(lRaw), right=safeParse(rRaw);
  } catch(e) {
    $('jpDiffOutput').innerHTML='<div style="padding:14px;color:var(--jp-error)">Parse error: '+esc(e.message)+'</div>';
    return;
  }
  diffChanges=[];diffIdx=-1;
  var diffs=[];
  JP._diffObj(left,right,'$',diffs);
  var adds=0,dels=0,mods=0;
  diffs.forEach(function(d){if(d.type==='add')adds++;else if(d.type==='del')dels++;else mods++});
  $('jpDiffAdds').textContent=adds;
  $('jpDiffDels').textContent=dels;
  $('jpDiffMods').textContent=mods;
  $('jpDiffSummary').style.display='flex';
  var html='';
  if(diffs.length===0) {
    html='<div style="padding:14px;color:var(--jp-success)">Documents are identical</div>';
  } else {
    diffs.forEach(function(d,i) {
      var cls=d.type==='add'?'jp-diff-add':d.type==='del'?'jp-diff-del':'jp-diff-mod';
      var prefix=d.type==='add'?'+ ':d.type==='del'?'- ':'~ ';
      html+='<div class="jp-diff-line '+cls+'" data-diff-idx="'+i+'">'+prefix+esc(d.path)+': '+esc(d.desc)+'</div>';
    });
  }
  $('jpDiffOutput').innerHTML=html;
  diffChanges=diffs;
  JP._updateDiffNav();
};
JP._diffObj = function(a,b,path,out) {
  if(a===b) return;
  if(a===null||b===null||typeof a!==typeof b||Array.isArray(a)!==Array.isArray(b)) {
    out.push({type:'mod',path:path,desc:JSON.stringify(a)+' -> '+JSON.stringify(b)});
    return;
  }
  if(typeof a!=='object') {
    if(a!==b) out.push({type:'mod',path:path,desc:JSON.stringify(a)+' -> '+JSON.stringify(b)});
    return;
  }
  if(Array.isArray(a)) {
    var maxLen=Math.max(a.length,b.length);
    for(var i=0;i<maxLen;i++) {
      var p=path+'['+i+']';
      if(i>=a.length) out.push({type:'add',path:p,desc:JSON.stringify(b[i])});
      else if(i>=b.length) out.push({type:'del',path:p,desc:JSON.stringify(a[i])});
      else JP._diffObj(a[i],b[i],p,out);
    }
    return;
  }
  var aKeys=Object.keys(a),bKeys=Object.keys(b);
  var allKeys={};
  aKeys.forEach(function(k){allKeys[k]=true});
  bKeys.forEach(function(k){allKeys[k]=true});
  Object.keys(allKeys).sort().forEach(function(k) {
    var p=path+'.'+k;
    if(!(k in a)) out.push({type:'add',path:p,desc:JSON.stringify(b[k])});
    else if(!(k in b)) out.push({type:'del',path:p,desc:JSON.stringify(a[k])});
    else JP._diffObj(a[k],b[k],p,out);
  });
};
JP.diffNav = function(dir) {
  if(diffChanges.length===0) return;
  diffIdx+=dir;
  if(diffIdx<0) diffIdx=diffChanges.length-1;
  if(diffIdx>=diffChanges.length) diffIdx=0;
  JP._updateDiffNav();
  var lines=$('jpDiffOutput').querySelectorAll('.jp-diff-line');
  if(lines[diffIdx]) lines[diffIdx].scrollIntoView({block:'center',behavior:'smooth'});
};
JP._updateDiffNav = function() {
  $('jpDiffPos').textContent=diffChanges.length>0?(diffIdx+1)+'/'+diffChanges.length:'0/0';
};
JP.swapDiff = function() {
  var l=$('jpDiffLeft').value,r=$('jpDiffRight').value;
  $('jpDiffLeft').value=r;$('jpDiffRight').value=l;
};
JP.clearDiff = function() {
  $('jpDiffLeft').value='';$('jpDiffRight').value='';$('jpDiffOutput').innerHTML='';
  $('jpDiffSummary').style.display='none';diffChanges=[];diffIdx=-1;JP._updateDiffNav();
};

// --- JSONPath Query ---
JP.runQuery = function() {
  var raw=$('jpQueryInput').value, expr=$('jpQueryExpr').value.trim();
  if(!raw.trim()){$('jpQueryResult').textContent='Paste JSON first';return}
  if(!expr){$('jpQueryResult').textContent='Enter a JSONPath expression';return}
  try {
    var data=safeParse(raw);
    var results=JP._jsonPath(data,expr);
    if(results===false||results===undefined) {
      $('jpQueryResult').textContent='No matches found';
    } else {
      var out=JSON.stringify(results,null,2);
      $('jpQueryResult').innerHTML=syntaxHL(esc(out));
      $('jpQueryResult').setAttribute('data-text',out);
    }
  } catch(e) {
    $('jpQueryResult').textContent='Error: '+e.message;
  }
};
// Minimal JSONPath implementation
JP._jsonPath = function(obj,expr) {
  if(!expr||expr[0]!=='$') return false;
  var results=[];
  JP._jpWalk(expr.substring(1),obj,results);
  if(results.length===0) return false;
  if(results.length===1) return results[0];
  return results;
};
JP._jpWalk = function(expr,val,results) {
  if(!expr||expr==='') { results.push(val); return; }
  // Recursive descent ..
  if(expr.substring(0,2)==='..') {
    var rest=expr.substring(2);
    // Extract next segment name
    var seg='',after='';
    if(rest[0]==='[') {
      var cb=rest.indexOf(']');
      if(cb!==-1){seg=rest.substring(0,cb+1);after=rest.substring(cb+1)}
    } else {
      var m=rest.match(/^([a-zA-Z_$][a-zA-Z0-9_$]*)(.*)/);
      if(m){seg=m[1];after=m[2]}
    }
    if(seg) {
      JP._jpApplySeg(seg+after,val,results,true);
    }
    return;
  }
  // Dot notation
  if(expr[0]==='.') {
    JP._jpWalk(expr.substring(1),val,results);
    return;
  }
  // Bracket notation
  if(expr[0]==='[') {
    var cb=JP._findClosingBracket(expr);
    if(cb===-1) return;
    var inside=expr.substring(1,cb);
    var rest=expr.substring(cb+1);
    // Filter ?()
    if(inside[0]==='?'&&inside[1]==='(') {
      var filterExpr=inside.substring(2,inside.length-1);
      if(Array.isArray(val)) {
        for(var i=0;i<val.length;i++) {
          if(JP._evalFilter(filterExpr,val[i])) {
            JP._jpWalk(rest,val[i],results);
          }
        }
      }
      return;
    }
    // Wildcard [*]
    if(inside==='*') {
      if(Array.isArray(val)){for(var i=0;i<val.length;i++) JP._jpWalk(rest,val[i],results)}
      else if(val&&typeof val==='object'){Object.keys(val).forEach(function(k){JP._jpWalk(rest,val[k],results)})}
      return;
    }
    // Slice [start:end]
    if(inside.indexOf(':')!==-1) {
      var parts=inside.split(':');
      if(Array.isArray(val)) {
        var start=parts[0]?parseInt(parts[0],10):0;
        var end=parts[1]?parseInt(parts[1],10):val.length;
        if(start<0) start=val.length+start;
        if(end<0) end=val.length+end;
        for(var i=start;i<end&&i<val.length;i++) {
          if(i>=0) JP._jpWalk(rest,val[i],results);
        }
      }
      return;
    }
    // Union [0,1,2]
    if(inside.indexOf(',')!==-1) {
      var indices=inside.split(',');
      for(var j=0;j<indices.length;j++) {
        var idx=indices[j].trim();
        if(idx[0]==="'"||idx[0]==='"') idx=idx.slice(1,-1);
        else idx=parseInt(idx,10);
        if(val&&typeof val==='object') {
          var cv=Array.isArray(val)?val[idx]:val[idx];
          if(cv!==undefined) JP._jpWalk(rest,cv,results);
        }
      }
      return;
    }
    // Quoted key ['key']
    if((inside[0]==="'"||inside[0]==='"')&&inside[inside.length-1]===inside[0]) {
      var key=inside.slice(1,-1);
      if(val&&typeof val==='object'&&val[key]!==undefined) JP._jpWalk(rest,val[key],results);
      return;
    }
    // Numeric index
    var idx=parseInt(inside,10);
    if(!isNaN(idx)&&Array.isArray(val)&&val[idx]!==undefined) {
      JP._jpWalk(rest,val[idx],results);
    }
    return;
  }
  // Property name
  var m=expr.match(/^([a-zA-Z_$][a-zA-Z0-9_$]*)(.*)/);
  if(m) {
    var prop=m[1],rest=m[2];
    if(val&&typeof val==='object'&&!Array.isArray(val)&&val[prop]!==undefined) {
      JP._jpWalk(rest,val[prop],results);
    }
  }
};
JP._jpApplySeg = function(expr,val,results,recurse) {
  JP._jpWalk(expr.match(/^\./)? expr : '.'+expr, val, results);
  if(recurse&&val&&typeof val==='object') {
    var items=Array.isArray(val)?val:Object.keys(val).map(function(k){return val[k]});
    for(var i=0;i<items.length;i++) {
      if(items[i]&&typeof items[i]==='object') JP._jpApplySeg(expr,items[i],results,true);
    }
  }
};
JP._findClosingBracket = function(s) {
  var depth=0;
  for(var i=0;i<s.length;i++) {
    if(s[i]==='[') depth++;
    else if(s[i]===']'){depth--;if(depth===0)return i}
  }
  return -1;
};
JP._evalFilter = function(expr,item) {
  // Simple filter: @.prop op value
  var m=expr.match(/@\.([a-zA-Z_$][a-zA-Z0-9_$]*)\s*(==|!=|<=|>=|<|>)\s*(.+)/);
  if(!m) return false;
  var prop=m[1],op=m[2],rhs=m[3].trim();
  if(!(prop in item)) return false;
  var lv=item[prop],rv;
  // Parse rhs
  if(rhs[0]==="'"||rhs[0]==='"') rv=rhs.slice(1,-1);
  else if(rhs==='true') rv=true;
  else if(rhs==='false') rv=false;
  else if(rhs==='null') rv=null;
  else rv=parseFloat(rhs);
  switch(op) {
    case '==': return lv==rv;
    case '!=': return lv!=rv;
    case '<': return lv<rv;
    case '>': return lv>rv;
    case '<=': return lv<=rv;
    case '>=': return lv>=rv;
  }
  return false;
};
// Also handle existence filter like ?(@.isbn)
var origEvalFilter = JP._evalFilter;
JP._evalFilter = function(expr, item) {
  // existence: @.prop (no operator)
  var existMatch = expr.match(/^@\.([a-zA-Z_$][a-zA-Z0-9_$]*)$/);
  if(existMatch) {
    return existMatch[1] in item;
  }
  return origEvalFilter(expr, item);
};

// Live query
$('jpQueryExpr').addEventListener('input', function() {
  if($('jpQueryInput').value.trim()) JP.runQuery();
});

// --- Transform ---
JP._getTransData = function() {
  var raw=$('jpTransInput').value;
  if(!raw.trim()) return null;
  return safeParse(raw);
};
JP.toCsv = function() {
  $('jpTransTable').style.display='none';
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var arr=Array.isArray(data)?data:[data];
    if(arr.length===0||typeof arr[0]!=='object'){$('jpTransOutput').textContent='Input must be an array of objects';return}
    var headers=[];
    arr.forEach(function(row){
      if(row&&typeof row==='object'&&!Array.isArray(row)){
        Object.keys(row).forEach(function(k){if(headers.indexOf(k)===-1)headers.push(k)});
      }
    });
    var csvEsc=function(v){
      var s=v===null||v===undefined?'':typeof v==='object'?JSON.stringify(v):String(v);
      if(s.indexOf(',')!==-1||s.indexOf('"')!==-1||s.indexOf('\n')!==-1) return '"'+s.replace(/"/g,'""')+'"';
      return s;
    };
    var lines=[headers.map(csvEsc).join(',')];
    arr.forEach(function(row){
      if(!row||typeof row!=='object') return;
      lines.push(headers.map(function(h){return csvEsc(row[h])}).join(','));
    });
    var out=lines.join('\n');
    $('jpTransOutput').textContent=out;
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP.toYaml = function() {
  $('jpTransTable').style.display='none';
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var out=JP._toYaml(data,0);
    $('jpTransOutput').textContent=out;
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP._toYaml = function(val,indent) {
  var pad='  '.repeat(indent);
  if(val===null) return 'null';
  if(typeof val==='string') {
    if(val.indexOf('\n')!==-1||val.indexOf(':')!==-1||val.indexOf('#')!==-1||val===''||val==='true'||val==='false'||val==='null'||!isNaN(Number(val)))
      return '"'+val.replace(/\\/g,'\\\\').replace(/"/g,'\\"')+'"';
    return val;
  }
  if(typeof val==='number'||typeof val==='boolean') return String(val);
  if(Array.isArray(val)) {
    if(val.length===0) return '[]';
    var lines=[];
    val.forEach(function(item) {
      if(item&&typeof item==='object') {
        var sub=JP._toYaml(item,indent+1);
        var first=true;
        sub.split('\n').forEach(function(line) {
          if(first){lines.push(pad+'- '+line);first=false}
          else lines.push(pad+'  '+line);
        });
      } else {
        lines.push(pad+'- '+JP._toYaml(item,indent+1));
      }
    });
    return lines.join('\n');
  }
  if(typeof val==='object') {
    var keys=Object.keys(val);
    if(keys.length===0) return '{}';
    var lines=[];
    keys.forEach(function(k) {
      var v=val[k];
      if(v&&typeof v==='object') {
        lines.push(pad+k+':');
        lines.push(JP._toYaml(v,indent+1));
      } else {
        lines.push(pad+k+': '+JP._toYaml(v,indent+1));
      }
    });
    return lines.join('\n');
  }
  return String(val);
};
JP.toXml = function() {
  $('jpTransTable').style.display='none';
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var out='<?xml version="1.0" encoding="UTF-8"?>\n'+JP._toXml(data,'root',0);
    $('jpTransOutput').textContent=out;
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP._toXml = function(val,tag,indent) {
  var pad='  '.repeat(indent);
  tag=tag.replace(/[^a-zA-Z0-9_-]/g,'_');
  if(val===null) return pad+'<'+tag+' />';
  if(typeof val!=='object') return pad+'<'+tag+'>'+esc(String(val))+'</'+tag+'>';
  if(Array.isArray(val)) {
    return val.map(function(item){return JP._toXml(item,'item',indent)}).join('\n');
  }
  var lines=[pad+'<'+tag+'>'];
  Object.keys(val).forEach(function(k){
    if(Array.isArray(val[k])) {
      lines.push(pad+'  <'+k.replace(/[^a-zA-Z0-9_-]/g,'_')+'>');
      val[k].forEach(function(item){lines.push(JP._toXml(item,'item',indent+2))});
      lines.push(pad+'  </'+k.replace(/[^a-zA-Z0-9_-]/g,'_')+'>');
    } else {
      lines.push(JP._toXml(val[k],k,indent+1));
    }
  });
  lines.push(pad+'</'+tag+'>');
  return lines.join('\n');
};
JP.toTypescript = function() {
  $('jpTransTable').style.display='none';
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var out=JP._toTS(data,'Root',0);
    $('jpTransOutput').textContent=out;
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP._toTS = function(val,name,depth) {
  if(typeof val!=='object'||val===null) return 'type '+name+' = '+JP._tsType(val)+';';
  var interfaces=[];
  var lines=['interface '+name+' {'];
  if(Array.isArray(val)) {
    if(val.length>0&&typeof val[0]==='object'&&val[0]!==null) {
      var sub=JP._toTS(val[0],name+'Item',depth+1);
      interfaces.push(sub);
      return interfaces.join('\n\n')+'\n\ntype '+name+' = '+name+'Item[];';
    }
    return 'type '+name+' = '+JP._tsType(val[0])+'[];';
  }
  Object.keys(val).forEach(function(k) {
    var v=val[k];
    if(v&&typeof v==='object'&&!Array.isArray(v)) {
      var subName=name+k.charAt(0).toUpperCase()+k.slice(1);
      interfaces.push(JP._toTS(v,subName,depth+1));
      lines.push('  '+k+': '+subName+';');
    } else if(Array.isArray(v)) {
      if(v.length>0&&typeof v[0]==='object'&&v[0]!==null) {
        var subName=name+k.charAt(0).toUpperCase()+k.slice(1)+'Item';
        interfaces.push(JP._toTS(v[0],subName,depth+1));
        lines.push('  '+k+': '+subName+'[];');
      } else {
        lines.push('  '+k+': '+(v.length>0?JP._tsType(v[0]):'unknown')+'[];');
      }
    } else {
      lines.push('  '+k+': '+JP._tsType(v)+';');
    }
  });
  lines.push('}');
  if(interfaces.length) return interfaces.join('\n\n')+'\n\n'+lines.join('\n');
  return lines.join('\n');
};
JP._tsType = function(v) {
  if(v===null) return 'null';
  if(typeof v==='string') return 'string';
  if(typeof v==='number') return Number.isInteger(v)?'number':'number';
  if(typeof v==='boolean') return 'boolean';
  return 'unknown';
};
JP.toTable = function() {
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';$('jpTransTable').style.display='none';return}
    var arr=Array.isArray(data)?data:[data];
    if(arr.length===0||typeof arr[0]!=='object'){$('jpTransOutput').textContent='Input must be an array of objects for table view';$('jpTransTable').style.display='none';return}
    var headers=[];
    arr.forEach(function(row){
      if(row&&typeof row==='object'&&!Array.isArray(row))
        Object.keys(row).forEach(function(k){if(headers.indexOf(k)===-1)headers.push(k)});
    });
    var html='<table><thead><tr>'+headers.map(function(h){return '<th>'+esc(h)+'</th>'}).join('')+'</tr></thead><tbody>';
    arr.forEach(function(row) {
      if(!row||typeof row!=='object') return;
      html+='<tr>'+headers.map(function(h){
        var v=row[h];
        var display=v===undefined?'':v===null?'null':typeof v==='object'?JSON.stringify(v):String(v);
        return '<td>'+esc(display)+'</td>';
      }).join('')+'</tr>';
    });
    html+='</tbody></table>';
    $('jpTransTable').innerHTML=html;
    $('jpTransTable').style.display='block';
    $('jpTransOutput').textContent='Table rendered above';
    $('jpTransOutput').removeAttribute('data-text');
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message;$('jpTransTable').style.display='none'}
};
JP.flattenJson = function() {
  $('jpTransTable').style.display='none';
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var flat={};
    JP._flatten(data,'',flat);
    var out=JSON.stringify(flat,null,2);
    $('jpTransOutput').innerHTML=syntaxHL(esc(out));
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP._flatten = function(obj,prefix,result) {
  if(obj===null||typeof obj!=='object') {
    result[prefix||'$']=obj;
    return;
  }
  if(Array.isArray(obj)) {
    if(obj.length===0) result[prefix||'$']=[];
    obj.forEach(function(v,i){JP._flatten(v,(prefix?prefix:'')+('['+i+']'),result)});
  } else {
    var keys=Object.keys(obj);
    if(keys.length===0) result[prefix||'$']={};
    keys.forEach(function(k){JP._flatten(obj[k],(prefix?prefix+'.':'')+k,result)});
  }
};
JP.pickKeys = function() {
  $('jpTransTable').style.display='none';
  var keys=prompt('Enter comma-separated key names to pick:');
  if(!keys) return;
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var picks=keys.split(',').map(function(k){return k.trim()});
    var result=JP._pickOmit(data,picks,true);
    var out=JSON.stringify(result,null,2);
    $('jpTransOutput').innerHTML=syntaxHL(esc(out));
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP.omitKeys = function() {
  $('jpTransTable').style.display='none';
  var keys=prompt('Enter comma-separated key names to omit:');
  if(!keys) return;
  try {
    var data=JP._getTransData();
    if(!data){$('jpTransOutput').textContent='Paste JSON first';return}
    var omits=keys.split(',').map(function(k){return k.trim()});
    var result=JP._pickOmit(data,omits,false);
    var out=JSON.stringify(result,null,2);
    $('jpTransOutput').innerHTML=syntaxHL(esc(out));
    $('jpTransOutput').setAttribute('data-text',out);
  } catch(e){$('jpTransOutput').textContent='Error: '+e.message}
};
JP._pickOmit = function(data,keys,isPick) {
  if(Array.isArray(data)) return data.map(function(item){return JP._pickOmit(item,keys,isPick)});
  if(!data||typeof data!=='object') return data;
  var result={};
  Object.keys(data).forEach(function(k) {
    var inList=keys.indexOf(k)!==-1;
    if(isPick?inList:!inList) result[k]=data[k];
  });
  return result;
};

// --- Schema Validator ---
JP.validateSchema = function() {
  var dataRaw=$('jpSchemaData').value, schemaRaw=$('jpSchemaInput').value;
  if(!dataRaw.trim()||!schemaRaw.trim()){
    $('jpSchemaResults').innerHTML='<span style="color:var(--jp-text-muted)">Paste JSON data and schema, then click Validate</span>';
    return;
  }
  try { var data=safeParse(dataRaw); } catch(e) {
    $('jpSchemaResults').innerHTML='<div class="jp-schema-err-item">JSON data parse error: '+esc(e.message)+'</div>';
    return;
  }
  try { var schema=safeParse(schemaRaw); } catch(e) {
    $('jpSchemaResults').innerHTML='<div class="jp-schema-err-item">Schema parse error: '+esc(e.message)+'</div>';
    return;
  }
  var errors=[];
  JP._validateSchema(data,schema,'$',errors);
  if(errors.length===0) {
    $('jpSchemaResults').innerHTML='<div class="jp-schema-ok">\u2713 Validation passed -- JSON matches the schema</div>';
  } else {
    var html=errors.map(function(e){
      return '<div class="jp-schema-err-item"><span class="jp-schema-err-path">'+esc(e.path)+'</span>'+esc(e.message)+'</div>';
    }).join('');
    $('jpSchemaResults').innerHTML=html;
  }
};
JP._validateSchema = function(data,schema,path,errors) {
  if(!schema||typeof schema!=='object') return;
  // type
  if(schema.type) {
    var types=Array.isArray(schema.type)?schema.type:[schema.type];
    var actual=data===null?'null':Array.isArray(data)?'array':typeof data;
    if(actual==='number'&&Number.isInteger(data)&&types.indexOf('integer')!==-1) {/* ok */}
    else if(types.indexOf(actual)===-1) {
      errors.push({path:path,message:'Expected type '+types.join('|')+', got '+actual});
    }
  }
  // enum
  if(schema.enum) {
    var found=false;
    for(var i=0;i<schema.enum.length;i++){
      if(JSON.stringify(data)===JSON.stringify(schema.enum[i])){found=true;break}
    }
    if(!found) errors.push({path:path,message:'Value not in enum: ['+schema.enum.map(function(v){return JSON.stringify(v)}).join(', ')+']'});
  }
  // string checks
  if(typeof data==='string') {
    if(schema.minLength!==undefined&&data.length<schema.minLength)
      errors.push({path:path,message:'String length '+data.length+' is less than minLength '+schema.minLength});
    if(schema.maxLength!==undefined&&data.length>schema.maxLength)
      errors.push({path:path,message:'String length '+data.length+' exceeds maxLength '+schema.maxLength});
    if(schema.pattern) {
      try {
        if(!new RegExp(schema.pattern).test(data))
          errors.push({path:path,message:'String does not match pattern: '+schema.pattern});
      } catch(e) {}
    }
  }
  // number checks
  if(typeof data==='number') {
    if(schema.minimum!==undefined&&data<schema.minimum)
      errors.push({path:path,message:'Value '+data+' is less than minimum '+schema.minimum});
    if(schema.maximum!==undefined&&data>schema.maximum)
      errors.push({path:path,message:'Value '+data+' exceeds maximum '+schema.maximum});
  }
  // object checks
  if(data&&typeof data==='object'&&!Array.isArray(data)) {
    if(schema.required) {
      schema.required.forEach(function(k) {
        if(!(k in data)) errors.push({path:path,message:'Missing required property: '+k});
      });
    }
    if(schema.properties) {
      Object.keys(schema.properties).forEach(function(k) {
        if(k in data) JP._validateSchema(data[k],schema.properties[k],path+'.'+k,errors);
      });
    }
  }
  // array checks
  if(Array.isArray(data)&&schema.items) {
    data.forEach(function(item,i) {
      JP._validateSchema(item,schema.items,path+'['+i+']',errors);
    });
  }
};
JP.loadSampleSchema = function() {
  $('jpSchemaData').value=SAMPLE_SCHEMA_DATA;
  $('jpSchemaInput').value=SAMPLE_SCHEMA;
};
JP.clearSchema = function() {
  $('jpSchemaData').value='';$('jpSchemaInput').value='';
  $('jpSchemaResults').innerHTML='Run validation to see results';
};

// --- Common actions ---
JP.paste = function() {
  navigator.clipboard.readText().then(function(text) {
    var active=document.querySelector('.jp-tab.active').getAttribute('data-tab');
    if(active==='format') $('jpFmtInput').value=text;
    else if(active==='tree') $('jpTreeInput').value=text;
    else if(active==='query') $('jpQueryInput').value=text;
    else if(active==='transform') $('jpTransInput').value=text;
    else if(active==='schema') $('jpSchemaData').value=text;
    else if(active==='diff') {
      if(!$('jpDiffLeft').value.trim()) $('jpDiffLeft').value=text;
      else $('jpDiffRight').value=text;
    }
  }).catch(function(){alert('Clipboard access denied. Paste manually with Ctrl+V.')});
};
JP.loadSample = function() {
  var active=document.querySelector('.jp-tab.active').getAttribute('data-tab');
  if(active==='format'){$('jpFmtInput').value=SAMPLE;JP.format()}
  else if(active==='tree'){$('jpTreeInput').value=SAMPLE;JP.buildTree()}
  else if(active==='query'){$('jpQueryInput').value=SAMPLE;JP.runQuery()}
  else if(active==='transform'){$('jpTransInput').value=SAMPLE}
  else if(active==='schema'){JP.loadSampleSchema()}
  else if(active==='diff'){$('jpDiffLeft').value=SAMPLE}
};
JP.importUrl = function() {
  var url=prompt('Enter URL to fetch JSON from:');
  if(!url) return;
  fetch(url).then(function(r){return r.text()}).then(function(text) {
    var active=document.querySelector('.jp-tab.active').getAttribute('data-tab');
    if(active==='format'){$('jpFmtInput').value=text;JP.format()}
    else if(active==='tree'){$('jpTreeInput').value=text;JP.buildTree()}
    else if(active==='query'){$('jpQueryInput').value=text}
    else if(active==='transform'){$('jpTransInput').value=text}
    else if(active==='schema'){$('jpSchemaData').value=text}
    else if(active==='diff'){$('jpDiffLeft').value=text}
  }).catch(function(e){alert('Fetch failed: '+e.message+'. The URL may not support CORS.')});
};
JP.copyOutput = function(id) {
  var el=$(id);
  var text=el.getAttribute('data-text')||el.textContent;
  if(!text) return;
  navigator.clipboard.writeText(text).then(function() {
    // Find the copy button that was near this
    var btn=event&&event.target;
    if(btn){var orig=btn.textContent;btn.textContent='Copied';btn.classList.add('copied');setTimeout(function(){btn.textContent=orig;btn.classList.remove('copied')},1500)}
  });
};
JP.toggleHistory = function() {
  var list=$('jpHistoryList');
  if(list.style.display==='block'){list.style.display='none';return}
  if(history.length===0){list.innerHTML='<div class="jp-history-item" style="color:var(--jp-text-dim)">No history yet</div>';list.style.display='block';return}
  list.innerHTML=history.map(function(h,i){return '<div class="jp-history-item" data-idx="'+i+'">'+esc(h)+'</div>'}).join('');
  list.style.display='block';
  list.querySelectorAll('.jp-history-item').forEach(function(item) {
    item.addEventListener('click',function() {
      // Try to restore. The history stores preview only, but try to find full from localStorage
      var text=this.textContent;
      var active=document.querySelector('.jp-tab.active').getAttribute('data-tab');
      if(active==='format') $('jpFmtInput').value=text;
      else if(active==='tree') $('jpTreeInput').value=text;
      list.style.display='none';
    });
  });
};
// Close history on outside click
document.addEventListener('click',function(e) {
  if(!e.target.closest('#jpHistoryList')&&!e.target.closest('[onclick*="toggleHistory"]'))
    $('jpHistoryList').style.display='none';
});

// --- Theme toggle ---
var isDark=true;
JP.toggleTheme = function() {
  isDark=!isDark;
  if(isDark){
    $('jpApp').classList.remove('jp-light');
    $('jpThemeBtn').textContent='Light';
  } else {
    $('jpApp').classList.add('jp-light');
    $('jpThemeBtn').textContent='Dark';
  }
};

// --- Keyboard shortcuts ---
document.addEventListener('keydown',function(e) {
  // Ctrl+Enter to format
  if(e.key==='Enter'&&(e.ctrlKey||e.metaKey)) {
    e.preventDefault();
    var active=document.querySelector('.jp-tab.active').getAttribute('data-tab');
    if(active==='format') JP.format();
    else if(active==='tree') JP.buildTree();
    else if(active==='diff') JP.runDiff();
    else if(active==='query') JP.runQuery();
    else if(active==='schema') JP.validateSchema();
  }
  // Ctrl+Shift+M to minify
  if(e.key==='M'&&(e.ctrlKey||e.metaKey)&&e.shiftKey) {
    e.preventDefault();
    JP.minify();
  }
});

// Allow Tab in all textareas
document.querySelectorAll('.jp-textarea').forEach(function(ta) {
  ta.addEventListener('keydown',function(e) {
    if(e.key==='Tab') {
      e.preventDefault();
      var s=this.selectionStart,end=this.selectionEnd;
      this.value=this.value.substring(0,s)+'  '+this.value.substring(end);
      this.selectionStart=this.selectionEnd=s+2;
    }
  });
});

// Input size tracking for format tab
$('jpFmtInput').addEventListener('input',function(){$('jpFmtInputSize').textContent=fmtBytes(byteSize(this.value))});

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "JSON Formatter Pro",
      "url": "https://theluckystrike.github.io/tools/json-formatter-pro/",
      "applicationCategory": "DeveloperApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "JSON Formatter Pro", "item": "https://theluckystrike.github.io/tools/json-formatter-pro/" }
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://zovo.one/favicon.ico"
    }
  ]
}
</script>
