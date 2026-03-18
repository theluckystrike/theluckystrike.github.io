---
layout: page
title: "Diff Checker Online - Compare Text Side by Side | Zovo"
description: "Free online diff checker -- compare two texts side by side with highlighted differences. See added, removed, and changed lines instantly. Runs in your browser."
permalink: /tools/diff-checker/
keywords: "diff checker online, diff checker, compare text online, text comparison tool, online diff tool, side by side diff, compare two texts"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [diff checker, text comparison, compare text, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --dc-primary: #6C5CE7;
    --dc-primary-dark: #5A4BD1;
    --dc-primary-light: #A29BFE;
    --dc-bg: #F8F9FE;
    --dc-surface: #FFFFFF;
    --dc-text: #2D3436;
    --dc-text-muted: #636E72;
    --dc-border: #DFE6E9;
    --dc-added: #00B894;
    --dc-added-bg: #E8FFF7;
    --dc-removed: #D63031;
    --dc-removed-bg: #FFEAEA;
    --dc-changed: #E17055;
    --dc-changed-bg: #FFF3E0;
    --dc-radius: 12px;
  }

  .dc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--dc-text);
    max-width: 1280px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .dc-wrapper * {
    box-sizing: border-box;
  }

  .dc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .dc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--dc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .dc-hero h1 span {
    color: var(--dc-primary);
  }

  .dc-intro {
    font-size: 1.05rem;
    color: var(--dc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Toolbar */
  .dc-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .dc-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border-radius: 8px;
    font-size: 0.88rem;
    font-weight: 500;
    cursor: pointer;
    border: none;
    font-family: inherit;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .dc-btn-primary {
    background: var(--dc-primary);
    color: #fff;
  }

  .dc-btn-primary:hover {
    background: var(--dc-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3);
  }

  .dc-btn-secondary {
    background: var(--dc-bg);
    color: var(--dc-text);
    border: 1px solid var(--dc-border);
  }

  .dc-btn-secondary:hover {
    background: #EEF0FB;
    border-color: var(--dc-primary-light);
  }

  .dc-btn-secondary.active {
    background: #EEF0FB;
    border-color: var(--dc-primary);
    color: var(--dc-primary);
  }

  .dc-toolbar-spacer {
    flex: 1;
  }

  .dc-link-btn {
    background: none;
    border: none;
    color: var(--dc-primary);
    font-size: 0.85rem;
    cursor: pointer;
    font-family: inherit;
    text-decoration: underline;
    text-underline-offset: 2px;
    padding: 4px 8px;
  }

  .dc-link-btn:hover {
    color: var(--dc-primary-dark);
  }

  /* Input panels */
  .dc-inputs {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .dc-panel {
    background: var(--dc-surface);
    border: 1px solid var(--dc-border);
    border-radius: var(--dc-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }

  .dc-panel-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 16px;
    background: var(--dc-bg);
    border-bottom: 1px solid var(--dc-border);
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--dc-text-muted);
  }

  .dc-input-area {
    width: 100%;
    min-height: 260px;
    padding: 12px 16px;
    border: none;
    outline: none;
    resize: vertical;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    line-height: 1.7;
    color: var(--dc-text);
    background: var(--dc-surface);
  }

  .dc-input-area::placeholder {
    color: #B2BEC3;
  }

  /* Diff output */
  .dc-output-wrap {
    background: var(--dc-surface);
    border: 1px solid var(--dc-border);
    border-radius: var(--dc-radius);
    overflow: hidden;
    display: none;
  }

  .dc-output-wrap.visible {
    display: block;
  }

  .dc-output-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 16px;
    background: var(--dc-bg);
    border-bottom: 1px solid var(--dc-border);
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--dc-text-muted);
  }

  .dc-output-header-actions {
    display: flex;
    gap: 8px;
    align-items: center;
  }

  .dc-diff-table {
    width: 100%;
    border-collapse: collapse;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    line-height: 1.65;
    table-layout: fixed;
  }

  .dc-diff-table td {
    padding: 1px 12px;
    vertical-align: top;
    white-space: pre-wrap;
    word-break: break-all;
  }

  .dc-ln {
    width: 48px;
    min-width: 48px;
    text-align: right;
    color: #B2BEC3;
    user-select: none;
    padding-right: 8px;
    border-right: 1px solid var(--dc-border);
    font-size: 0.75rem;
  }

  .dc-op {
    width: 24px;
    min-width: 24px;
    text-align: center;
    font-weight: 600;
    user-select: none;
  }

  .dc-line-content {
    padding-left: 12px;
  }

  /* Side-by-side specific */
  .dc-sbs-table {
    width: 100%;
    border-collapse: collapse;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    line-height: 1.65;
    table-layout: fixed;
  }

  .dc-sbs-table td {
    padding: 1px 12px;
    vertical-align: top;
    white-space: pre-wrap;
    word-break: break-all;
  }

  .dc-sbs-divider {
    width: 1px;
    min-width: 1px;
    padding: 0;
    background: var(--dc-border);
  }

  .dc-sbs-content {
    padding-left: 12px;
  }

  /* Diff line colors */
  .dc-row-added {
    background: var(--dc-added-bg);
  }

  .dc-row-added .dc-op {
    color: var(--dc-added);
  }

  .dc-row-removed {
    background: var(--dc-removed-bg);
  }

  .dc-row-removed .dc-op {
    color: var(--dc-removed);
  }

  .dc-row-changed {
    background: var(--dc-changed-bg);
  }

  .dc-row-changed .dc-op {
    color: var(--dc-changed);
  }

  .dc-row-equal td {
    color: var(--dc-text-muted);
  }

  .dc-row-empty {
    background: #F5F5F5;
  }

  .dc-row-empty td {
    color: transparent;
  }

  /* Status bar */
  .dc-status {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px 0;
    flex-wrap: wrap;
    gap: 8px;
  }

  .dc-status-msg {
    font-size: 0.85rem;
    font-weight: 500;
  }

  .dc-status-empty { color: var(--dc-text-muted); }
  .dc-status-match { color: var(--dc-added); }
  .dc-status-diff { color: var(--dc-primary); }

  .dc-stats {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }

  .dc-stat {
    font-size: 0.82rem;
    color: var(--dc-text-muted);
  }

  .dc-stat strong {
    color: var(--dc-text);
  }

  .dc-stat-added strong { color: var(--dc-added); }
  .dc-stat-removed strong { color: var(--dc-removed); }
  .dc-stat-changed strong { color: var(--dc-changed); }

  .dc-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.78rem;
    color: var(--dc-text-muted);
    padding: 16px 0 8px;
    border-top: 1px solid var(--dc-border);
    margin-top: 8px;
  }

  /* Content section */
  .dc-content {
    margin-top: 48px;
    max-width: 800px;
  }

  .dc-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--dc-text);
  }

  .dc-content p {
    color: var(--dc-text-muted);
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .dc-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 10px;
    color: var(--dc-text);
  }

  .dc-content ul {
    color: var(--dc-text-muted);
    padding-left: 24px;
    margin: 0 0 16px;
    line-height: 1.8;
  }

  /* FAQ */
  .dc-faq {
    margin-top: 48px;
    max-width: 800px;
    padding-bottom: 48px;
  }

  .dc-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    color: var(--dc-text);
  }

  .dc-faq-item {
    border-bottom: 1px solid var(--dc-border);
    padding: 20px 0;
  }

  .dc-faq-item:first-of-type {
    border-top: 1px solid var(--dc-border);
  }

  .dc-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--dc-text);
  }

  .dc-faq-item p {
    margin: 0;
    color: var(--dc-text-muted);
    line-height: 1.7;
    font-size: 0.95rem;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .dc-hero h1 { font-size: 1.6rem; }

    .dc-inputs {
      grid-template-columns: 1fr;
    }

    .dc-input-area {
      min-height: 180px;
    }

    .dc-toolbar {
      gap: 6px;
    }

    .dc-btn {
      padding: 7px 12px;
      font-size: 0.82rem;
    }

    .dc-sbs-table .dc-ln,
    .dc-diff-table .dc-ln {
      width: 36px;
      min-width: 36px;
      font-size: 0.7rem;
    }

    .dc-diff-table td,
    .dc-sbs-table td {
      padding: 1px 6px;
      font-size: 0.75rem;
    }
  }
</style>

<div class="dc-wrapper">

  <div class="dc-hero">
    <h1><span>Diff Checker</span> Online</h1>
    <p class="dc-intro">Compare two blocks of text side by side and see every difference highlighted. Added, removed, and changed lines are color-coded so you can spot changes at a glance. Runs entirely in your browser -- nothing is uploaded.</p>
  </div>

  <!-- Toolbar -->
  <div class="dc-toolbar">
    <button class="dc-btn dc-btn-primary" onclick="dcCompare()" title="Compare the two texts">&#9654; Compare</button>
    <button class="dc-btn dc-btn-secondary" id="dcViewSbs" onclick="dcSetView('sbs')" title="Side-by-side diff view">Side by Side</button>
    <button class="dc-btn dc-btn-secondary active" id="dcViewUnified" onclick="dcSetView('unified')" title="Unified diff view">Unified</button>
    <div class="dc-toolbar-spacer"></div>
    <button class="dc-link-btn" onclick="dcLoadSample()" title="Load example text">Load sample</button>
    <button class="dc-btn dc-btn-secondary" id="dcCopyBtn" onclick="dcCopyDiff()" title="Copy diff output">&#128203; <span id="dcCopyLabel">Copy Diff</span></button>
    <button class="dc-btn dc-btn-secondary" onclick="dcSwap()" title="Swap left and right text">&#8644; Swap</button>
    <button class="dc-btn dc-btn-secondary" onclick="dcClear()" title="Clear all inputs and output">&#10005; Clear</button>
  </div>

  <!-- Input panels -->
  <div class="dc-inputs">
    <div class="dc-panel">
      <div class="dc-panel-header">
        <span>&#9998; Original Text</span>
        <span id="dcLeftSize">0 bytes</span>
      </div>
      <textarea id="dcLeft" class="dc-input-area" placeholder="Paste original text here..." spellcheck="false"></textarea>
    </div>
    <div class="dc-panel">
      <div class="dc-panel-header">
        <span>&#9998; Modified Text</span>
        <span id="dcRightSize">0 bytes</span>
      </div>
      <textarea id="dcRight" class="dc-input-area" placeholder="Paste modified text here..." spellcheck="false"></textarea>
    </div>
  </div>

  <!-- Diff output -->
  <div class="dc-output-wrap" id="dcOutput">
    <div class="dc-output-header">
      <span>Diff Result</span>
      <div class="dc-output-header-actions">
        <span id="dcDiffSummary"></span>
      </div>
    </div>
    <div id="dcDiffContent" style="overflow-x:auto;"></div>
  </div>

  <!-- Status bar -->
  <div class="dc-status">
    <div id="dcStatusMsg" class="dc-status-msg dc-status-empty">Paste text and click Compare</div>
    <div class="dc-stats">
      <span class="dc-stat dc-stat-added">Added: <strong id="dcAdded">0</strong></span>
      <span class="dc-stat dc-stat-removed">Removed: <strong id="dcRemoved">0</strong></span>
      <span class="dc-stat dc-stat-changed">Changed: <strong id="dcChanged">0</strong></span>
    </div>
  </div>

  <div class="dc-meta">
    <span>Processing happens entirely in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO content -->
  <div class="dc-content">
    <h2>How the Diff Checker Works</h2>
    <p>This diff checker compares two pieces of text line by line using a longest common subsequence (LCS) algorithm. It identifies which lines are identical, which were added, which were removed, and which were modified. The result is a clear, color-coded view of every change between the original and modified text.</p>

    <h3>Key Features</h3>
    <ul>
      <li>Side-by-side and unified diff view modes</li>
      <li>Color-coded differences -- green for added, red for removed, orange for changed</li>
      <li>Line numbers on both panels for easy reference</li>
      <li>Statistics showing the count of added, removed, and changed lines</li>
      <li>Copy the diff output for sharing or documentation</li>
      <li>Swap original and modified text with one click</li>
      <li>No data leaves your browser -- fully client-side processing</li>
    </ul>

    <h3>Common Use Cases</h3>
    <p>Developers use diff checkers to review code changes before committing, compare configuration files across environments, or verify that automated edits applied correctly. Writers and editors rely on them to track revisions between drafts. System administrators compare log files or server outputs to spot unexpected changes. Any time you need to understand exactly what changed between two versions of a text, a diff checker gives you the answer in seconds.</p>
  </div>

  <!-- FAQ with Schema.org markup -->
  <div class="dc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="dc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is a diff checker?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A diff checker is a tool that compares two blocks of text and highlights the differences between them. It shows which lines were added, removed, or changed, using color-coded markers so you can quickly see every modification. Diff checkers are essential for code reviews, document editing, and any task where you need to track changes between two versions of a file.</p>
      </div>
    </div>

    <div class="dc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does the side-by-side diff view differ from the unified view?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The side-by-side view places the original text on the left and the modified text on the right, with matching lines aligned horizontally. This makes it easy to compare corresponding sections visually. The unified view combines both texts into a single column, prefixing removed lines with a minus sign and added lines with a plus sign. Unified view is more compact and is the standard format used by version control systems like Git.</p>
      </div>
    </div>

    <div class="dc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe when using this online diff checker?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This diff checker runs entirely inside your browser using JavaScript. Your text is never sent to a server, stored, or logged anywhere. You can verify this by opening your browser developer tools and monitoring the Network tab while comparing text. This makes it safe for comparing sensitive documents, source code with credentials, and confidential content.</p>
      </div>
    </div>

    <div class="dc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What algorithm does this diff checker use?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool uses a longest common subsequence (LCS) algorithm, the same foundational approach used by Unix diff and Git. It finds the longest sequence of lines that appear in both texts in the same order, then classifies every other line as either added or removed. Lines that exist at the same position but with different content are marked as changed. This produces accurate, minimal diffs for texts of any size.</p>
      </div>
    </div>

    <div class="dc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I compare code files with this tool?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Absolutely. This diff checker works with any plain text, including source code in any programming language, configuration files such as JSON or YAML, SQL queries, shell scripts, and markup languages like HTML or Markdown. The monospace font and line numbers make it well-suited for code comparison. Simply paste your original code on the left and the updated version on the right, then click Compare.</p>
      </div>
    </div>

  </div>

  <div style="margin: 2rem 0; padding: 1rem 1.25rem; background: #f3f0ff; border: 1px solid #6C5CE7; border-radius: 8px;">
<div style="font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.1em; color: #6C5CE7; margin-bottom: 0.5rem; font-weight: 600;">Related Guide</div>
<a href="/guides/creating-a-chrome-extension/" style="color: #1d1d1f; text-decoration: none; font-size: 0.95rem; font-weight: 500;">How to Create a Chrome Extension &rarr;</a>
</div>

  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid #2a2a3a; margin-top: 3rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var leftEl = document.getElementById("dcLeft");
  var rightEl = document.getElementById("dcRight");
  var outputWrap = document.getElementById("dcOutput");
  var diffContent = document.getElementById("dcDiffContent");
  var statusEl = document.getElementById("dcStatusMsg");
  var viewMode = "unified";
  var lastDiff = null;

  var SAMPLE_LEFT = "function greet(name) {\n  console.log(\"Hello, \" + name);\n  return true;\n}\n\nvar users = [\"Alice\", \"Bob\"];\n\nfor (var i = 0; i < users.length; i++) {\n  greet(users[i]);\n}\n\nconsole.log(\"Done.\");";
  var SAMPLE_RIGHT = "function greet(name, greeting) {\n  var msg = greeting + \", \" + name + \"!\";\n  console.log(msg);\n  return msg;\n}\n\nvar users = [\"Alice\", \"Bob\", \"Charlie\"];\n\nfor (var i = 0; i < users.length; i++) {\n  greet(users[i], \"Hi\");\n}\n\nconsole.log(\"All done.\");";

  // --- Helpers ---

  function byteSize(str) {
    return new Blob([str]).size;
  }

  function formatBytes(bytes) {
    if (bytes === 0) return "0 bytes";
    if (bytes < 1024) return bytes + " bytes";
    if (bytes < 1048576) return (bytes / 1024).toFixed(1) + " KB";
    return (bytes / 1048576).toFixed(2) + " MB";
  }

  function escapeHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  function updateSizes() {
    document.getElementById("dcLeftSize").textContent = formatBytes(byteSize(leftEl.value));
    document.getElementById("dcRightSize").textContent = formatBytes(byteSize(rightEl.value));
  }

  leftEl.addEventListener("input", updateSizes);
  rightEl.addEventListener("input", updateSizes);

  // --- LCS Diff Algorithm ---

  function lcs(a, b) {
    var m = a.length;
    var n = b.length;
    // Build LCS table
    var dp = new Array(m + 1);
    for (var i = 0; i <= m; i++) {
      dp[i] = new Array(n + 1);
      for (var j = 0; j <= n; j++) {
        dp[i][j] = 0;
      }
    }
    for (var i = 1; i <= m; i++) {
      for (var j = 1; j <= n; j++) {
        if (a[i - 1] === b[j - 1]) {
          dp[i][j] = dp[i - 1][j - 1] + 1;
        } else {
          dp[i][j] = dp[i - 1][j] > dp[i][j - 1] ? dp[i - 1][j] : dp[i][j - 1];
        }
      }
    }
    return dp;
  }

  function buildDiff(a, b) {
    var dp = lcs(a, b);
    var ops = [];
    var i = a.length;
    var j = b.length;

    while (i > 0 || j > 0) {
      if (i > 0 && j > 0 && a[i - 1] === b[j - 1]) {
        ops.push({ type: "equal", left: i, right: j, text: a[i - 1] });
        i--; j--;
      } else if (j > 0 && (i === 0 || dp[i][j - 1] >= dp[i - 1][j])) {
        ops.push({ type: "added", right: j, text: b[j - 1] });
        j--;
      } else {
        ops.push({ type: "removed", left: i, text: a[i - 1] });
        i--;
      }
    }

    ops.reverse();

    // Detect "changed" lines: consecutive remove+add pairs
    var result = [];
    var idx = 0;
    while (idx < ops.length) {
      if (idx + 1 < ops.length && ops[idx].type === "removed" && ops[idx + 1].type === "added") {
        result.push({
          type: "changed",
          left: ops[idx].left,
          right: ops[idx + 1].right,
          oldText: ops[idx].text,
          newText: ops[idx + 1].text
        });
        idx += 2;
      } else {
        result.push(ops[idx]);
        idx++;
      }
    }

    return result;
  }

  // --- Render Unified View ---

  function renderUnified(ops) {
    var html = '<table class="dc-diff-table">';
    for (var i = 0; i < ops.length; i++) {
      var op = ops[i];
      if (op.type === "equal") {
        html += '<tr class="dc-row-equal">';
        html += '<td class="dc-ln">' + op.left + '</td>';
        html += '<td class="dc-ln">' + op.right + '</td>';
        html += '<td class="dc-op">&nbsp;</td>';
        html += '<td class="dc-line-content">' + escapeHtml(op.text) + '</td>';
        html += '</tr>';
      } else if (op.type === "removed") {
        html += '<tr class="dc-row-removed">';
        html += '<td class="dc-ln">' + op.left + '</td>';
        html += '<td class="dc-ln"></td>';
        html += '<td class="dc-op">&minus;</td>';
        html += '<td class="dc-line-content">' + escapeHtml(op.text) + '</td>';
        html += '</tr>';
      } else if (op.type === "added") {
        html += '<tr class="dc-row-added">';
        html += '<td class="dc-ln"></td>';
        html += '<td class="dc-ln">' + op.right + '</td>';
        html += '<td class="dc-op">+</td>';
        html += '<td class="dc-line-content">' + escapeHtml(op.text) + '</td>';
        html += '</tr>';
      } else if (op.type === "changed") {
        html += '<tr class="dc-row-removed">';
        html += '<td class="dc-ln">' + op.left + '</td>';
        html += '<td class="dc-ln"></td>';
        html += '<td class="dc-op">&minus;</td>';
        html += '<td class="dc-line-content">' + escapeHtml(op.oldText) + '</td>';
        html += '</tr>';
        html += '<tr class="dc-row-added">';
        html += '<td class="dc-ln"></td>';
        html += '<td class="dc-ln">' + op.right + '</td>';
        html += '<td class="dc-op">+</td>';
        html += '<td class="dc-line-content">' + escapeHtml(op.newText) + '</td>';
        html += '</tr>';
      }
    }
    html += '</table>';
    return html;
  }

  // --- Render Side-by-Side View ---

  function renderSideBySide(ops) {
    var html = '<table class="dc-sbs-table">';
    for (var i = 0; i < ops.length; i++) {
      var op = ops[i];
      if (op.type === "equal") {
        html += '<tr class="dc-row-equal">';
        html += '<td class="dc-ln">' + op.left + '</td>';
        html += '<td class="dc-sbs-content">' + escapeHtml(op.text) + '</td>';
        html += '<td class="dc-sbs-divider"></td>';
        html += '<td class="dc-ln">' + op.right + '</td>';
        html += '<td class="dc-sbs-content">' + escapeHtml(op.text) + '</td>';
        html += '</tr>';
      } else if (op.type === "removed") {
        html += '<tr>';
        html += '<td class="dc-ln dc-row-removed">' + op.left + '</td>';
        html += '<td class="dc-sbs-content dc-row-removed">' + escapeHtml(op.text) + '</td>';
        html += '<td class="dc-sbs-divider"></td>';
        html += '<td class="dc-ln dc-row-empty">&nbsp;</td>';
        html += '<td class="dc-sbs-content dc-row-empty">&nbsp;</td>';
        html += '</tr>';
      } else if (op.type === "added") {
        html += '<tr>';
        html += '<td class="dc-ln dc-row-empty">&nbsp;</td>';
        html += '<td class="dc-sbs-content dc-row-empty">&nbsp;</td>';
        html += '<td class="dc-sbs-divider"></td>';
        html += '<td class="dc-ln dc-row-added">' + op.right + '</td>';
        html += '<td class="dc-sbs-content dc-row-added">' + escapeHtml(op.newText || op.text) + '</td>';
        html += '</tr>';
      } else if (op.type === "changed") {
        html += '<tr>';
        html += '<td class="dc-ln dc-row-changed">' + op.left + '</td>';
        html += '<td class="dc-sbs-content dc-row-changed">' + escapeHtml(op.oldText) + '</td>';
        html += '<td class="dc-sbs-divider"></td>';
        html += '<td class="dc-ln dc-row-changed">' + op.right + '</td>';
        html += '<td class="dc-sbs-content dc-row-changed">' + escapeHtml(op.newText) + '</td>';
        html += '</tr>';
      }
    }
    html += '</table>';
    return html;
  }

  // --- Stats ---

  function computeStats(ops) {
    var added = 0, removed = 0, changed = 0;
    for (var i = 0; i < ops.length; i++) {
      if (ops[i].type === "added") added++;
      else if (ops[i].type === "removed") removed++;
      else if (ops[i].type === "changed") changed++;
    }
    return { added: added, removed: removed, changed: changed };
  }

  function updateStats(stats) {
    document.getElementById("dcAdded").textContent = stats.added;
    document.getElementById("dcRemoved").textContent = stats.removed;
    document.getElementById("dcChanged").textContent = stats.changed;
  }

  function clearStats() {
    document.getElementById("dcAdded").textContent = "0";
    document.getElementById("dcRemoved").textContent = "0";
    document.getElementById("dcChanged").textContent = "0";
  }

  function setStatus(type, msg) {
    statusEl.className = "dc-status-msg";
    if (type === "match") {
      statusEl.classList.add("dc-status-match");
      statusEl.innerHTML = "&#10004; " + msg;
    } else if (type === "diff") {
      statusEl.classList.add("dc-status-diff");
      statusEl.innerHTML = "&#8800; " + msg;
    } else {
      statusEl.classList.add("dc-status-empty");
      statusEl.textContent = msg;
    }
  }

  // --- Generate plain text diff for copying ---

  function generatePlainDiff(ops) {
    var lines = [];
    for (var i = 0; i < ops.length; i++) {
      var op = ops[i];
      if (op.type === "equal") {
        lines.push("  " + op.text);
      } else if (op.type === "removed") {
        lines.push("- " + op.text);
      } else if (op.type === "added") {
        lines.push("+ " + op.text);
      } else if (op.type === "changed") {
        lines.push("- " + op.oldText);
        lines.push("+ " + op.newText);
      }
    }
    return lines.join("\n");
  }

  // --- Public functions ---

  window.dcCompare = function() {
    var leftText = leftEl.value;
    var rightText = rightEl.value;
    updateSizes();

    if (!leftText && !rightText) {
      setStatus("empty", "Paste text and click Compare");
      outputWrap.classList.remove("visible");
      clearStats();
      lastDiff = null;
      return;
    }

    var leftLines = leftText.split("\n");
    var rightLines = rightText.split("\n");
    var ops = buildDiff(leftLines, rightLines);
    lastDiff = ops;

    var stats = computeStats(ops);
    updateStats(stats);

    var total = stats.added + stats.removed + stats.changed;
    if (total === 0) {
      setStatus("match", "Texts are identical");
      document.getElementById("dcDiffSummary").textContent = "No differences";
    } else {
      setStatus("diff", total + " difference" + (total === 1 ? "" : "s") + " found");
      var parts = [];
      if (stats.added) parts.push(stats.added + " added");
      if (stats.removed) parts.push(stats.removed + " removed");
      if (stats.changed) parts.push(stats.changed + " changed");
      document.getElementById("dcDiffSummary").textContent = parts.join(", ");
    }

    renderCurrentView();
    outputWrap.classList.add("visible");
  };

  function renderCurrentView() {
    if (!lastDiff) return;
    if (viewMode === "sbs") {
      diffContent.innerHTML = renderSideBySide(lastDiff);
    } else {
      diffContent.innerHTML = renderUnified(lastDiff);
    }
  }

  window.dcSetView = function(mode) {
    viewMode = mode;
    document.getElementById("dcViewSbs").classList.toggle("active", mode === "sbs");
    document.getElementById("dcViewUnified").classList.toggle("active", mode === "unified");
    renderCurrentView();
  };

  window.dcCopyDiff = function() {
    if (!lastDiff) return;
    var text = generatePlainDiff(lastDiff);
    navigator.clipboard.writeText(text).then(function() {
      var label = document.getElementById("dcCopyLabel");
      label.textContent = "Copied!";
      setTimeout(function() {
        label.textContent = "Copy Diff";
      }, 2000);
    });
  };

  window.dcSwap = function() {
    var tmp = leftEl.value;
    leftEl.value = rightEl.value;
    rightEl.value = tmp;
    updateSizes();
    if (lastDiff) dcCompare();
  };

  window.dcClear = function() {
    leftEl.value = "";
    rightEl.value = "";
    outputWrap.classList.remove("visible");
    diffContent.innerHTML = "";
    lastDiff = null;
    setStatus("empty", "Paste text and click Compare");
    clearStats();
    updateSizes();
    document.getElementById("dcDiffSummary").textContent = "";
  };

  window.dcLoadSample = function() {
    leftEl.value = SAMPLE_LEFT;
    rightEl.value = SAMPLE_RIGHT;
    updateSizes();
    dcCompare();
  };

  // Keyboard shortcut: Ctrl/Cmd + Enter to compare
  document.addEventListener("keydown", function(e) {
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      dcCompare();
    }
  });

})();
</script>
