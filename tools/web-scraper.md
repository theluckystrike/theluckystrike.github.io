---
layout: page
title: "Free Web Scraper Tool — Extract Data from HTML, CSS Selectors & JSON | Zovo"
description: "Parse HTML with CSS selectors, extract structured data from web pages, and convert to JSON or CSV. Free online web scraping toolkit with selector tester and data extraction."
permalink: /tools/web-scraper/
keywords: "web scraper, web scraping tool, html parser, css selector tester, data extractor, scrape website, extract data from website, web scraper online"
date: 2026-03-19
categories: [tools]
tags: [web-scraper, html-parser, css-selectors, data-extraction, scraping]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --ws-bg: #0a0a0f;
    --ws-surface: #12121a;
    --ws-surface2: #1a1a28;
    --ws-border: #1e1e2e;
    --ws-border-light: #2a2a3e;
    --ws-primary: #6C5CE7;
    --ws-primary-dark: #5A4BD1;
    --ws-primary-light: #8B7CF0;
    --ws-secondary: #00ff88;
    --ws-secondary-dark: #00cc6a;
    --ws-text: #e0e0e0;
    --ws-text-muted: #8888aa;
    --ws-text-dim: #555570;
    --ws-error: #ff4757;
    --ws-warning: #ffa502;
    --ws-radius: 10px;
    --ws-radius-sm: 6px;
  }

  body {
    background: var(--ws-bg) !important;
    margin: 0;
    padding: 0;
  }

  .ws-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ws-text);
    max-width: 1280px;
    margin: 0 auto;
    padding: 0 20px;
    line-height: 1.6;
  }

  .ws-wrapper * {
    box-sizing: border-box;
  }

  /* Hero */
  .ws-hero {
    text-align: center;
    padding: 36px 0 28px;
  }

  .ws-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ws-text);
    margin: 0 0 14px;
    line-height: 1.2;
  }

  .ws-hero h1 span {
    color: var(--ws-primary);
  }

  .ws-hero-sub {
    font-size: 1.02rem;
    color: var(--ws-text-muted);
    max-width: 740px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Tabs */
  .ws-tabs {
    display: flex;
    gap: 4px;
    margin-bottom: 20px;
    border-bottom: 1px solid var(--ws-border);
    padding-bottom: 0;
    overflow-x: auto;
  }

  .ws-tab {
    padding: 10px 18px;
    border: none;
    background: transparent;
    color: var(--ws-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    border-bottom: 2px solid transparent;
    transition: all 0.15s ease;
    white-space: nowrap;
    margin-bottom: -1px;
  }

  .ws-tab:hover {
    color: var(--ws-text);
    background: var(--ws-surface);
  }

  .ws-tab.active {
    color: var(--ws-primary-light);
    border-bottom-color: var(--ws-primary);
    background: var(--ws-surface);
  }

  .ws-tab-panel {
    display: none;
  }

  .ws-tab-panel.active {
    display: block;
  }

  /* Buttons */
  .ws-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border: none;
    border-radius: var(--ws-radius-sm);
    font-family: 'Inter', sans-serif;
    font-size: 0.84rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .ws-btn-primary {
    background: var(--ws-primary);
    color: #fff;
  }

  .ws-btn-primary:hover {
    background: var(--ws-primary-dark);
  }

  .ws-btn-secondary {
    background: var(--ws-surface2);
    color: var(--ws-text);
    border: 1px solid var(--ws-border);
  }

  .ws-btn-secondary:hover {
    background: var(--ws-border);
  }

  .ws-btn-accent {
    background: var(--ws-secondary);
    color: #0a0a0f;
    font-weight: 600;
  }

  .ws-btn-accent:hover {
    background: var(--ws-secondary-dark);
  }

  .ws-btn.copied {
    background: var(--ws-secondary);
    color: #0a0a0f;
  }

  .ws-btn-sm {
    padding: 5px 10px;
    font-size: 0.78rem;
  }

  .ws-link-btn {
    background: none;
    border: none;
    color: var(--ws-primary-light);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .ws-link-btn:hover {
    color: var(--ws-primary);
  }

  /* Toolbar */
  .ws-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 14px;
  }

  .ws-toolbar-spacer {
    flex: 1;
  }

  /* Panels */
  .ws-panel {
    background: var(--ws-surface);
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }

  .ws-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 9px 14px;
    background: var(--ws-surface2);
    border-bottom: 1px solid var(--ws-border);
    font-size: 0.78rem;
    font-weight: 600;
    color: var(--ws-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .ws-textarea {
    width: 100%;
    min-height: 320px;
    border: none;
    padding: 14px;
    font-family: 'JetBrains Mono', 'Consolas', monospace;
    font-size: 0.82rem;
    line-height: 1.6;
    resize: vertical;
    color: var(--ws-text);
    background: var(--ws-surface);
    outline: none;
    tab-size: 2;
  }

  .ws-textarea::placeholder {
    color: var(--ws-text-dim);
  }

  .ws-input {
    width: 100%;
    padding: 10px 14px;
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius-sm);
    font-family: 'JetBrains Mono', 'Consolas', monospace;
    font-size: 0.84rem;
    color: var(--ws-text);
    background: var(--ws-surface);
    outline: none;
    transition: border-color 0.15s ease;
  }

  .ws-input:focus {
    border-color: var(--ws-primary);
  }

  .ws-input::placeholder {
    color: var(--ws-text-dim);
  }

  .ws-input-row {
    display: flex;
    gap: 10px;
    align-items: center;
    margin-bottom: 14px;
  }

  .ws-input-row .ws-input {
    flex: 1;
  }

  /* Results */
  .ws-results {
    background: var(--ws-surface);
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
    min-height: 200px;
    max-height: 500px;
    overflow: auto;
    padding: 14px;
    font-family: 'JetBrains Mono', 'Consolas', monospace;
    font-size: 0.82rem;
    line-height: 1.6;
    color: var(--ws-text);
    margin-top: 14px;
  }

  .ws-results:empty::before {
    content: 'Results will appear here...';
    color: var(--ws-text-dim);
  }

  .ws-match-item {
    padding: 8px 12px;
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius-sm);
    margin-bottom: 8px;
    background: var(--ws-surface2);
  }

  .ws-match-tag {
    color: var(--ws-primary-light);
    font-weight: 600;
    font-size: 0.78rem;
    margin-bottom: 3px;
  }

  .ws-match-text {
    color: var(--ws-secondary);
    font-size: 0.82rem;
    word-break: break-all;
  }

  .ws-match-attrs {
    color: var(--ws-text-muted);
    font-size: 0.76rem;
    margin-top: 3px;
  }

  .ws-match-count {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.84rem;
    font-weight: 500;
    padding: 5px 12px;
    border-radius: 16px;
    background: rgba(108, 92, 231, 0.15);
    color: var(--ws-primary-light);
    margin-top: 10px;
  }

  /* Split pane for selector tester */
  .ws-split {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-top: 14px;
  }

  .ws-split .ws-panel {
    min-height: 380px;
  }

  .ws-split .ws-textarea {
    min-height: 300px;
  }

  /* HTML preview area */
  .ws-html-preview {
    padding: 14px;
    font-family: 'JetBrains Mono', 'Consolas', monospace;
    font-size: 0.82rem;
    line-height: 1.7;
    overflow: auto;
    min-height: 300px;
    white-space: pre-wrap;
    word-break: break-all;
    color: var(--ws-text);
  }

  .ws-hl-match {
    background: rgba(108, 92, 231, 0.3);
    border: 1px solid var(--ws-primary);
    border-radius: 2px;
    padding: 0 2px;
  }

  /* Specificity display */
  .ws-specificity {
    display: inline-flex;
    gap: 4px;
    font-size: 0.78rem;
    margin-left: 10px;
  }

  .ws-spec-part {
    background: var(--ws-surface2);
    border: 1px solid var(--ws-border);
    padding: 2px 7px;
    border-radius: 4px;
    color: var(--ws-text-muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.74rem;
  }

  /* Cheatsheet */
  .ws-cheatsheet {
    margin-top: 14px;
    padding: 14px;
    background: var(--ws-surface);
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
  }

  .ws-cheatsheet h4 {
    font-size: 0.82rem;
    color: var(--ws-text-muted);
    margin: 0 0 10px;
    text-transform: uppercase;
    letter-spacing: 0.04em;
  }

  .ws-cheatsheet-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 6px;
  }

  .ws-cs-item {
    display: flex;
    gap: 10px;
    align-items: baseline;
    font-size: 0.78rem;
    padding: 5px 8px;
    border-radius: 4px;
  }

  .ws-cs-item:hover {
    background: var(--ws-surface2);
  }

  .ws-cs-sel {
    font-family: 'JetBrains Mono', monospace;
    color: var(--ws-primary-light);
    min-width: 110px;
    cursor: pointer;
  }

  .ws-cs-desc {
    color: var(--ws-text-muted);
  }

  /* Table preview */
  .ws-table-preview {
    overflow: auto;
    margin-top: 14px;
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
  }

  .ws-table-preview table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.82rem;
    font-family: 'JetBrains Mono', monospace;
  }

  .ws-table-preview th {
    background: var(--ws-surface2);
    color: var(--ws-primary-light);
    padding: 8px 12px;
    text-align: left;
    border-bottom: 1px solid var(--ws-border);
    font-weight: 600;
    font-size: 0.78rem;
    position: relative;
  }

  .ws-table-preview td {
    padding: 7px 12px;
    border-bottom: 1px solid var(--ws-border);
    color: var(--ws-text);
  }

  .ws-table-preview tr:hover td {
    background: var(--ws-surface2);
  }

  .ws-col-rename {
    width: 100%;
    padding: 3px 6px;
    border: 1px solid var(--ws-border);
    border-radius: 3px;
    background: var(--ws-surface);
    color: var(--ws-primary-light);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.76rem;
    outline: none;
    margin-top: 4px;
    display: block;
  }

  .ws-col-rename:focus {
    border-color: var(--ws-primary);
  }

  /* Status bar */
  .ws-status {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-top: 14px;
    font-size: 0.82rem;
    color: var(--ws-text-muted);
  }

  /* Additional tools section */
  .ws-extra-tools {
    margin-top: 28px;
    padding-top: 20px;
    border-top: 1px solid var(--ws-border);
  }

  .ws-extra-tools h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--ws-text);
    margin: 0 0 14px;
  }

  .ws-extra-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .ws-extra-card {
    background: var(--ws-surface);
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
    padding: 16px;
  }

  .ws-extra-card h4 {
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--ws-text);
    margin: 0 0 10px;
  }

  .ws-url-parts {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 4px 12px;
    font-size: 0.8rem;
    margin-top: 10px;
  }

  .ws-url-label {
    color: var(--ws-text-muted);
    font-weight: 500;
  }

  .ws-url-value {
    color: var(--ws-secondary);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    word-break: break-all;
  }

  .ws-regex-matches {
    margin-top: 10px;
    max-height: 200px;
    overflow: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
  }

  .ws-regex-match {
    padding: 3px 8px;
    margin-bottom: 3px;
    background: var(--ws-surface2);
    border-radius: 3px;
    color: var(--ws-secondary);
  }

  /* Content section */
  .ws-content {
    max-width: 820px;
    margin: 48px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--ws-border);
  }

  .ws-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--ws-text);
    margin: 40px 0 16px;
    line-height: 1.3;
  }

  .ws-content h2:first-child {
    margin-top: 0;
  }

  .ws-content p {
    font-size: 0.95rem;
    color: var(--ws-text-muted);
    line-height: 1.8;
    margin: 0 0 16px;
  }

  .ws-content ul, .ws-content ol {
    color: var(--ws-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 24px;
    margin: 0 0 16px;
  }

  .ws-content li {
    margin-bottom: 6px;
  }

  .ws-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.84rem;
    background: var(--ws-surface2);
    padding: 2px 6px;
    border-radius: 4px;
    color: var(--ws-primary-light);
  }

  .ws-content pre {
    background: var(--ws-surface);
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
    padding: 16px;
    overflow-x: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    line-height: 1.6;
    color: var(--ws-text);
    margin: 0 0 16px;
  }

  /* FAQ */
  .ws-faq {
    max-width: 820px;
    margin: 48px auto 0;
  }

  .ws-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--ws-text);
  }

  .ws-faq-item {
    border: 1px solid var(--ws-border);
    border-radius: var(--ws-radius);
    padding: 18px 22px;
    margin-bottom: 10px;
    background: var(--ws-surface);
  }

  .ws-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--ws-text);
  }

  .ws-faq-item p {
    margin: 0;
    font-size: 0.92rem;
    color: var(--ws-text-muted);
    line-height: 1.75;
  }

  /* Footer */
  .ws-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--ws-text-dim);
    font-size: 0.85rem;
    border-top: 1px solid var(--ws-border);
    margin-top: 48px;
  }

  .ws-footer a {
    color: var(--ws-primary);
    text-decoration: none;
  }

  .ws-footer a:hover {
    text-decoration: underline;
  }

  /* Syntax highlighting (basic) */
  .ws-syn-tag { color: #ff6b81; }
  .ws-syn-attr { color: #ffa502; }
  .ws-syn-val { color: #00ff88; }
  .ws-syn-str { color: #00ff88; }
  .ws-syn-key { color: #74b9ff; }
  .ws-syn-num { color: #6C5CE7; }
  .ws-syn-bool { color: #ff6b81; }
  .ws-syn-null { color: #636e72; font-style: italic; }
  .ws-syn-bracket { color: #8888aa; }
  .ws-syn-comment { color: #555570; }

  /* Scrollbar styling */
  .ws-wrapper ::-webkit-scrollbar {
    width: 6px;
    height: 6px;
  }

  .ws-wrapper ::-webkit-scrollbar-track {
    background: var(--ws-surface);
  }

  .ws-wrapper ::-webkit-scrollbar-thumb {
    background: var(--ws-border-light);
    border-radius: 3px;
  }

  .ws-wrapper ::-webkit-scrollbar-thumb:hover {
    background: var(--ws-text-dim);
  }

  /* Responsive */
  @media (max-width: 768px) {
    .ws-hero h1 {
      font-size: 1.5rem;
    }

    .ws-split {
      grid-template-columns: 1fr;
    }

    .ws-extra-grid {
      grid-template-columns: 1fr;
    }

    .ws-tabs {
      gap: 2px;
    }

    .ws-tab {
      padding: 8px 12px;
      font-size: 0.78rem;
    }

    .ws-btn {
      padding: 7px 11px;
      font-size: 0.78rem;
    }

    .ws-textarea {
      min-height: 220px;
    }

    .ws-cheatsheet-grid {
      grid-template-columns: 1fr;
    }

    .ws-input-row {
      flex-direction: column;
      gap: 8px;
    }

    .ws-input-row .ws-btn {
      width: 100%;
      justify-content: center;
    }
  }
</style>

<div class="ws-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Web Scraper Tool">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="ws-hero">
    <h1><span>Web Scraper</span> & Data Extractor</h1>
    <p class="ws-hero-sub">Parse HTML with CSS selectors, extract tables to JSON or CSV, test JSONPath expressions, and pull structured data from any markup. Everything runs in your browser. Nothing is sent to a server.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <!-- Tabs -->
  <div class="ws-tabs" role="tablist">
    <button class="ws-tab active" role="tab" data-tab="html-parser" onclick="wsSetTab('html-parser')">HTML Parser</button>
    <button class="ws-tab" role="tab" data-tab="selector-tester" onclick="wsSetTab('selector-tester')">CSS Selector Tester</button>
    <button class="ws-tab" role="tab" data-tab="table-extractor" onclick="wsSetTab('table-extractor')">Table Extractor</button>
    <button class="ws-tab" role="tab" data-tab="jsonpath" onclick="wsSetTab('jsonpath')">JSONPath Extractor</button>
  </div>

  <!-- Tab 1: HTML Parser -->
  <div id="panel-html-parser" class="ws-tab-panel active">
    <div class="ws-toolbar">
      <button class="ws-btn ws-btn-accent" onclick="wsHtmlExtract()">Extract</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsHtmlExportJson()">Export JSON</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsHtmlExportCsv()">Export CSV</button>
      <div class="ws-toolbar-spacer"></div>
      <button class="ws-link-btn" onclick="wsLoadSampleHtml()">Load sample HTML</button>
      <button class="ws-btn ws-btn-secondary ws-btn-sm" onclick="wsHtmlClear()">Clear</button>
    </div>

    <div class="ws-panel" style="margin-bottom: 14px;">
      <div class="ws-panel-header">
        <span>HTML Source</span>
      </div>
      <textarea id="wsHtmlInput" class="ws-textarea" placeholder="Paste HTML source code here..." spellcheck="false"></textarea>
    </div>

    <div class="ws-input-row">
      <input id="wsHtmlSelector" class="ws-input" type="text" placeholder='CSS Selector (e.g. h1, .class, #id, a[href], table tr td)' spellcheck="false">
    </div>

    <div id="wsHtmlCount" class="ws-match-count" style="display:none;"></div>
    <div id="wsHtmlResults" class="ws-results"></div>
  </div>

  <!-- Tab 2: CSS Selector Tester -->
  <div id="panel-selector-tester" class="ws-tab-panel">
    <div class="ws-toolbar">
      <button class="ws-btn ws-btn-accent" onclick="wsSelectorTest()">Test Selector</button>
      <span id="wsSelectorSpecificity" class="ws-specificity"></span>
      <div class="ws-toolbar-spacer"></div>
      <button class="ws-link-btn" onclick="wsLoadSampleSelector()">Load sample</button>
    </div>

    <div class="ws-input-row">
      <input id="wsSelectorInput" class="ws-input" type="text" placeholder='Type a CSS selector (e.g. div.container > p:first-child)' spellcheck="false" oninput="wsSelectorLive()">
    </div>

    <div class="ws-split">
      <div class="ws-panel">
        <div class="ws-panel-header">
          <span>HTML Source</span>
        </div>
        <textarea id="wsSelectorHtml" class="ws-textarea" placeholder="Paste HTML here..." spellcheck="false" oninput="wsSelectorLive()"></textarea>
      </div>
      <div class="ws-panel">
        <div class="ws-panel-header">
          <span id="wsSelectorMatchLabel">Matched Elements (0)</span>
        </div>
        <div id="wsSelectorPreview" class="ws-html-preview"></div>
      </div>
    </div>

    <div class="ws-cheatsheet">
      <h4>CSS Selector Reference</h4>
      <div class="ws-cheatsheet-grid">
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('element')">element</span><span class="ws-cs-desc">Tag name</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('.class')">.class</span><span class="ws-cs-desc">Class selector</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('#id')">#id</span><span class="ws-cs-desc">ID selector</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('[attr]')">[attr]</span><span class="ws-cs-desc">Has attribute</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('[attr=value]')">[attr=value]</span><span class="ws-cs-desc">Attribute equals</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('[attr*=value]')">[attr*=value]</span><span class="ws-cs-desc">Attribute contains</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('A > B')">A > B</span><span class="ws-cs-desc">Direct child</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('A B')">A B</span><span class="ws-cs-desc">Descendant</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('A + B')">A + B</span><span class="ws-cs-desc">Adjacent sibling</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('A ~ B')">A ~ B</span><span class="ws-cs-desc">General sibling</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector(':first-child')">:first-child</span><span class="ws-cs-desc">First child</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector(':nth-child(n)')">:nth-child(n)</span><span class="ws-cs-desc">Nth child</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector(':not(sel)')">:not(sel)</span><span class="ws-cs-desc">Negation</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector('A, B')">A, B</span><span class="ws-cs-desc">Multiple selectors</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector(':last-child')">:last-child</span><span class="ws-cs-desc">Last child</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertSelector(':empty')">:empty</span><span class="ws-cs-desc">No children</span></div>
      </div>
    </div>
  </div>

  <!-- Tab 3: Table Extractor -->
  <div id="panel-table-extractor" class="ws-tab-panel">
    <div class="ws-toolbar">
      <button class="ws-btn ws-btn-accent" onclick="wsTableExtract()">Detect Tables</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsTableExportJson()">Export JSON</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsTableExportCsv()">Export CSV</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsTableCopy()" id="wsTableCopyBtn">Copy</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsTableDownload()">Download</button>
      <div class="ws-toolbar-spacer"></div>
      <button class="ws-link-btn" onclick="wsLoadSampleTable()">Load sample</button>
      <button class="ws-btn ws-btn-secondary ws-btn-sm" onclick="wsTableClear()">Clear</button>
    </div>

    <div class="ws-panel" style="margin-bottom: 14px;">
      <div class="ws-panel-header">
        <span>HTML with Table</span>
      </div>
      <textarea id="wsTableInput" class="ws-textarea" placeholder="Paste HTML containing a <table>..." spellcheck="false"></textarea>
    </div>

    <div id="wsTableStatus" class="ws-status" style="display:none;"></div>
    <div id="wsTablePreview" class="ws-table-preview" style="display:none;"></div>
  </div>

  <!-- Tab 4: JSONPath Extractor -->
  <div id="panel-jsonpath" class="ws-tab-panel">
    <div class="ws-toolbar">
      <button class="ws-btn ws-btn-accent" onclick="wsJsonPathExtract()">Extract</button>
      <button class="ws-btn ws-btn-secondary" onclick="wsJsonPathCopy()">Copy Result</button>
      <div class="ws-toolbar-spacer"></div>
      <button class="ws-link-btn" onclick="wsLoadSampleJsonPath()">Load sample</button>
      <button class="ws-btn ws-btn-secondary ws-btn-sm" onclick="wsJsonPathClear()">Clear</button>
    </div>

    <div class="ws-input-row">
      <input id="wsJsonPathExpr" class="ws-input" type="text" placeholder='JSONPath (e.g. $.store.book[0].title, $..author, $.store.book[?(@.price<10)])' spellcheck="false">
    </div>

    <div class="ws-panel" style="margin-bottom: 14px;">
      <div class="ws-panel-header">
        <span>JSON Input</span>
      </div>
      <textarea id="wsJsonPathInput" class="ws-textarea" placeholder="Paste JSON data here..." spellcheck="false"></textarea>
    </div>

    <div id="wsJsonPathResults" class="ws-results"></div>

    <div class="ws-cheatsheet" style="margin-top: 14px;">
      <h4>JSONPath Reference</h4>
      <div class="ws-cheatsheet-grid">
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$')">$</span><span class="ws-cs-desc">Root object</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$.key')">$.key</span><span class="ws-cs-desc">Child property</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$..key')">$..key</span><span class="ws-cs-desc">Recursive descent</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$.arr[0]')">$.arr[0]</span><span class="ws-cs-desc">Array index</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$.arr[0:3]')">$.arr[0:3]</span><span class="ws-cs-desc">Array slice</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$.arr[*]')">$.arr[*]</span><span class="ws-cs-desc">All elements</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$.*')">$.*</span><span class="ws-cs-desc">All properties</span></div>
        <div class="ws-cs-item"><span class="ws-cs-sel" onclick="wsInsertJsonPath('$.arr[-1]')">$.arr[-1]</span><span class="ws-cs-desc">Last element</span></div>
      </div>
    </div>
  </div>

  <!-- Additional Tools -->
  <div class="ws-extra-tools">
    <h3>Additional Utilities</h3>
    <div class="ws-extra-grid">
      <!-- Regex Matcher -->
      <div class="ws-extra-card">
        <h4>Regex Pattern Matcher</h4>
        <input id="wsRegexPattern" class="ws-input" type="text" placeholder="Regex pattern (e.g. \d+, https?://\S+)" style="margin-bottom: 8px;" spellcheck="false">
        <textarea id="wsRegexText" class="ws-textarea" style="min-height: 100px;" placeholder="Text to search..." spellcheck="false"></textarea>
        <div style="margin-top: 8px; display: flex; gap: 6px;">
          <button class="ws-btn ws-btn-primary ws-btn-sm" onclick="wsRegexMatch()">Find Matches</button>
          <label style="display: inline-flex; align-items: center; gap: 4px; font-size: 0.78rem; color: var(--ws-text-muted);"><input type="checkbox" id="wsRegexGlobal" checked> Global</label>
          <label style="display: inline-flex; align-items: center; gap: 4px; font-size: 0.78rem; color: var(--ws-text-muted);"><input type="checkbox" id="wsRegexCase"> Case-insensitive</label>
        </div>
        <div id="wsRegexResults" class="ws-regex-matches"></div>
      </div>

      <!-- URL Parser -->
      <div class="ws-extra-card">
        <h4>URL Parser</h4>
        <input id="wsUrlInput" class="ws-input" type="text" placeholder="https://example.com/path?key=value#section" spellcheck="false">
        <div style="margin-top: 8px;">
          <button class="ws-btn ws-btn-primary ws-btn-sm" onclick="wsParseUrl()">Parse URL</button>
        </div>
        <div id="wsUrlParts" class="ws-url-parts" style="display: none;"></div>
      </div>
    </div>
  </div>

  <div style="margin-top: 20px; text-align: center; font-size: 0.78rem; color: var(--ws-text-dim);">
    All processing happens in your browser. No data is transmitted.
  </div>

  <!-- Content Section -->
  <div class="ws-content">

    <h2>What Is Web Scraping</h2>
    <p>Web scraping is the process of extracting data from websites programmatically. Instead of copying text by hand, a scraper reads the HTML structure of a page, locates the elements that contain the data you need, and pulls them into a structured format like JSON, CSV, or a database table. The technique is used across industries for price monitoring, research aggregation, lead generation, content indexing, and competitive analysis.</p>
    <p>At its core, a web scraper operates on two principles: fetching a page and parsing its content. Fetching means making an HTTP request to a URL to retrieve the raw HTML response. Parsing means walking through that HTML to find specific elements using patterns like CSS selectors or XPath expressions. This tool handles the parsing side. You paste in HTML source, define what you want to extract, and the tool returns structured output.</p>
    <p>Client-side scraping (like this tool) works on HTML you already have. Server-side scraping, by contrast, fetches pages from remote servers, which introduces CORS restrictions, rate limiting, and legal considerations. For learning, prototyping, and testing extraction logic, a client-side parser is the fastest way to iterate.</p>

    <h2>How Web Scrapers Work</h2>
    <p>A typical web scraping workflow has four stages:</p>
    <ol>
      <li>Request: the scraper sends an HTTP GET (or POST) request to a target URL and receives the HTML response body.</li>
      <li>Parse: the HTML string is loaded into a DOM parser that builds a tree structure representing the page.</li>
      <li>Select: the scraper queries the DOM tree using CSS selectors, XPath, or regex patterns to locate target elements.</li>
      <li>Extract: the matched elements yield their text content, attribute values, or inner HTML, which gets stored as structured data.</li>
    </ol>
    <p>Modern scrapers may also handle JavaScript-rendered pages using headless browsers like Puppeteer or Playwright. These tools launch a real browser engine, wait for the page to fully render, then expose the resulting DOM for extraction. This approach is necessary for single-page applications where the content is loaded via JavaScript after the initial HTML response.</p>
    <p>Scrapers also deal with pagination (following "next page" links), authentication (logging in before scraping), and throttling (adding delays between requests to avoid overwhelming target servers).</p>

    <h2>CSS Selectors for Web Scraping</h2>
    <p>CSS selectors are the primary way to target elements within HTML. They were designed for styling, but they work equally well for data extraction. Every major scraping library supports CSS selectors, including BeautifulSoup, Cheerio, Puppeteer, and Playwright.</p>
    <p>The most common selectors for scraping are:</p>
    <ul>
      <li><code>tag</code> selects all elements of that type. Example: <code>p</code> selects every paragraph.</li>
      <li><code>.classname</code> selects elements with a specific class. Example: <code>.product-title</code> targets product headings on an e-commerce page.</li>
      <li><code>#id</code> selects one element by its unique ID.</li>
      <li><code>[attribute]</code> selects elements that have a given attribute. Example: <code>a[href]</code> selects all links with an href.</li>
      <li><code>[attribute=value]</code> selects elements where the attribute matches an exact value.</li>
      <li><code>parent > child</code> selects direct children. Example: <code>ul > li</code> selects list items that are immediate children of an unordered list.</li>
      <li><code>ancestor descendant</code> selects all descendants regardless of nesting depth.</li>
    </ul>
    <p>Pseudo-selectors like <code>:first-child</code>, <code>:nth-child(2)</code>, and <code>:not(.hidden)</code> add further precision. Combining selectors with commas lets you match multiple patterns in a single query. The selector tester tab in this tool provides a live environment for experimenting with all of these.</p>

    <h2>JSONPath Expressions Explained</h2>
    <p>JSONPath is a query language for JSON data, similar to how XPath works for XML. It lets you navigate nested JSON structures and extract specific values without writing custom traversal code.</p>
    <p>The syntax starts with <code>$</code> representing the root object. Dot notation accesses properties: <code>$.store.name</code> retrieves the <code>name</code> property inside <code>store</code>. Bracket notation handles special characters or array indexing: <code>$.store.book[0]</code> gets the first book.</p>
    <p>Key operators include:</p>
    <ul>
      <li><code>$..key</code> performs recursive descent, finding every occurrence of <code>key</code> at any depth.</li>
      <li><code>[*]</code> matches all elements in an array or all properties of an object.</li>
      <li><code>[0:3]</code> returns a slice of an array (elements 0, 1, and 2).</li>
      <li><code>[-1]</code> returns the last element of an array.</li>
      <li><code>[?(@.price &lt; 10)]</code> is a filter expression that returns elements meeting a condition.</li>
    </ul>
    <p>JSONPath is supported natively by many APIs and data processing tools. It appears in AWS Step Functions, Kubernetes configurations, and various ETL platforms. Knowing JSONPath saves time when working with deeply nested API responses.</p>

    <h2>Legal Considerations for Web Scraping</h2>
    <p>Web scraping occupies a complicated legal space. The legality depends on what data you scrape, how you scrape it, what you do with the data, and the jurisdiction you operate in.</p>
    <p>In the United States, the Computer Fraud and Abuse Act (CFAA) has been applied to scraping cases. The 2022 Ninth Circuit ruling in hiQ Labs v. LinkedIn established that scraping publicly available data does not violate the CFAA. However, this does not mean all scraping is legal. Terms of service violations, copyright infringement, and privacy regulations like GDPR in Europe or CCPA in California add layers of restriction.</p>
    <p>General guidelines that reduce legal risk:</p>
    <ul>
      <li>Scrape only publicly accessible data. Avoid bypassing login walls or CAPTCHA systems.</li>
      <li>Respect robots.txt directives. Though not legally binding in all jurisdictions, ignoring them weakens your position if challenged.</li>
      <li>Do not overwhelm servers. Rate-limit your requests and honor retry-after headers.</li>
      <li>Avoid scraping personal data unless you have a lawful basis under applicable privacy laws.</li>
      <li>Do not republish copyrighted content. Extracting facts is generally permissible; copying creative works is not.</li>
      <li>Check the website's terms of service for explicit prohibitions on automated access.</li>
    </ul>
    <p>When in doubt, consult legal counsel before running scraping operations at scale.</p>

    <h2>Popular Web Scraping Languages and Tools</h2>
    <p>Python dominates the web scraping space due to its extensive library ecosystem. The standard stack includes Requests for HTTP calls and BeautifulSoup for HTML parsing. For more advanced use cases, Scrapy provides a full framework with built-in support for crawling, item pipelines, middleware, and distributed scraping via Scrapy-Redis.</p>
    <p>JavaScript scrapers use Cheerio (a server-side jQuery-like library for Node.js) for static pages and Puppeteer or Playwright for JavaScript-rendered content. Playwright is cross-browser and supports Chromium, Firefox, and WebKit.</p>
    <p>Other notable tools:</p>
    <ul>
      <li>Selenium: browser automation tool available in Python, Java, C#, and Ruby. Slower than headless options but widely supported.</li>
      <li>Colly: a Go-based scraping framework known for speed and low memory usage.</li>
      <li>Nokogiri: Ruby's primary HTML/XML parser, fast and well-maintained.</li>
      <li>jsoup: a Java library for working with real-world HTML, handling malformed markup gracefully.</li>
      <li>curl and wget: command-line tools for fetching pages, often combined with other parsers.</li>
    </ul>
    <p>Cloud-based platforms like Apify, ScrapingBee, and Bright Data handle infrastructure, proxy rotation, and CAPTCHA solving for large-scale commercial scraping operations.</p>

    <h2>Building Your First Web Scraper</h2>
    <p>A minimal Python scraper that extracts all links from a page takes about ten lines of code:</p>
    <pre>import requests
from bs4 import BeautifulSoup

url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

for link in soup.select("a[href]"):
    print(link["href"], link.get_text(strip=True))</pre>
    <p>This script sends a GET request, parses the HTML into a BeautifulSoup object, then uses the CSS selector <code>a[href]</code> to find all anchor elements with an href attribute. For each match, it prints the URL and link text.</p>
    <p>To handle JavaScript-rendered pages, swap Requests for Playwright:</p>
    <pre>from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch()
    page = browser.new_page()
    page.goto("https://example.com")
    links = page.query_selector_all("a[href]")
    for link in links:
        print(link.get_attribute("href"), link.inner_text())
    browser.close()</pre>
    <p>Before scraping any live site, test your selectors on static HTML using the tools on this page. Paste the page source into the HTML Parser tab, try different selectors, and verify the output matches what you expect. This prevents wasted requests and speeds up development.</p>

  </div>

  <!-- FAQ Section -->
  <div class="ws-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="ws-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can this tool scrape live websites?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. This tool is a client-side HTML parser and data extractor. It processes HTML, JSON, and text that you paste into the input fields. Browser security policies (CORS) prevent JavaScript running on a webpage from fetching content from other domains. To scrape live sites, you need a server-side tool like Python with BeautifulSoup, Node.js with Cheerio, or a headless browser like Puppeteer or Playwright.</p>
      </div>
    </div>

    <div class="ws-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I get the HTML source of a page to paste here?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">In most browsers, right-click on a page and select "View Page Source" or press Ctrl+U (Cmd+Option+U on Mac). This opens the raw HTML in a new tab, which you can copy and paste into this tool. For JavaScript-rendered content, use the browser's DevTools (F12), navigate to the Elements tab, right-click the html element, and choose "Copy > Copy outerHTML" to get the fully rendered DOM.</p>
      </div>
    </div>

    <div class="ws-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What CSS selectors work for scraping?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">All standard CSS selectors work, including tag names (div, p, a), class selectors (.product-name), ID selectors (#main-content), attribute selectors (a[href], img[src]), combinators (div > p, ul li), and pseudo-classes (:first-child, :nth-child(2), :not(.hidden)). The most useful for scraping are attribute selectors and class selectors because they target specific data-carrying elements. Use the CSS Selector Tester tab to experiment with selectors against your HTML.</p>
      </div>
    </div>

    <div class="ws-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is web scraping legal?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The legality of web scraping varies by jurisdiction and circumstances. Scraping publicly available data is generally permissible in the United States following the hiQ v. LinkedIn ruling. However, violating a site's terms of service, bypassing access controls, scraping personal data without consent, or republishing copyrighted content can create legal liability. Always review the target site's terms and robots.txt, avoid collecting personal information without a lawful basis, and consult a lawyer if you plan to scrape at commercial scale.</p>
      </div>
    </div>

    <div class="ws-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between CSS selectors and XPath?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Both CSS selectors and XPath are used to locate elements in HTML. CSS selectors use a compact syntax designed for styling (e.g., div.class > p) and are supported natively in browsers via querySelectorAll. XPath uses a path-like syntax (e.g., //div[@class="name"]/p) and can traverse the DOM in directions CSS cannot, such as selecting parent elements or preceding siblings. CSS selectors are simpler for most scraping tasks. XPath provides more power when you need to navigate upward in the DOM tree or use complex conditions.</p>
      </div>
    </div>

    <div class="ws-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe when using this tool?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This web scraper runs entirely in your browser using JavaScript. No data is transmitted to any server. There are no API calls, no analytics tracking on your input, and nothing is stored after you close the page. You can verify this by opening your browser's developer tools and watching the Network tab while using the tool. It is safe for processing HTML that contains sensitive or proprietary content.</p>
      </div>
    </div>

  </div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/html-to-markdown/" style="color:#00ff88;text-decoration:none;">HTML to Markdown</a> - Convert HTML to clean Markdown</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter-pro/" style="color:#00ff88;text-decoration:none;">JSON Formatter Pro</a> - Advanced JSON toolkit with diff and queries</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/csv-to-json-converter/" style="color:#00ff88;text-decoration:none;">CSV to JSON Converter</a> - Convert CSV data to JSON format</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/regex-tester/" style="color:#00ff88;text-decoration:none;">Regex Tester</a> - Test regular expressions with live highlighting</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/diff-checker/" style="color:#00ff88;text-decoration:none;">Diff Checker</a> - Compare two texts side by side</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>


  <footer class="ws-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  // ============================================================
  //  TAB SWITCHING
  // ============================================================
  window.wsSetTab = function(id) {
    var tabs = document.querySelectorAll('.ws-tab');
    var panels = document.querySelectorAll('.ws-tab-panel');
    for (var i = 0; i < tabs.length; i++) {
      tabs[i].classList.remove('active');
      if (tabs[i].getAttribute('data-tab') === id) tabs[i].classList.add('active');
    }
    for (var j = 0; j < panels.length; j++) {
      panels[j].classList.remove('active');
      if (panels[j].id === 'panel-' + id) panels[j].classList.add('active');
    }
  };

  // ============================================================
  //  HELPERS
  // ============================================================
  function escHtml(s) {
    return s.replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;').replace(/"/g, '&quot;');
  }

  function copyText(text, btnEl) {
    navigator.clipboard.writeText(text).then(function() {
      if (btnEl) {
        var orig = btnEl.textContent;
        btnEl.textContent = 'Copied';
        btnEl.classList.add('copied');
        setTimeout(function() { btnEl.textContent = orig; btnEl.classList.remove('copied'); }, 1800);
      }
    });
  }

  function downloadFile(content, filename, mime) {
    var blob = new Blob([content], { type: mime });
    var url = URL.createObjectURL(blob);
    var a = document.createElement('a');
    a.href = url;
    a.download = filename;
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  }

  function parseDom(html) {
    var parser = new DOMParser();
    return parser.parseFromString(html, 'text/html');
  }

  // ============================================================
  //  SAMPLE DATA
  // ============================================================
  var SAMPLE_HTML = '<div class="products">\n  <div class="product" data-id="1">\n    <h2 class="title">Wireless Keyboard</h2>\n    <span class="price">$49.99</span>\n    <p class="desc">Compact wireless keyboard with backlight.</p>\n    <a href="/products/keyboard" class="link">View details</a>\n  </div>\n  <div class="product" data-id="2">\n    <h2 class="title">USB-C Hub</h2>\n    <span class="price">$34.99</span>\n    <p class="desc">7-in-1 USB-C hub with HDMI and Ethernet.</p>\n    <a href="/products/usb-hub" class="link">View details</a>\n  </div>\n  <div class="product" data-id="3">\n    <h2 class="title">Mechanical Mouse</h2>\n    <span class="price">$29.99</span>\n    <p class="desc">Ergonomic mouse with adjustable DPI.</p>\n    <a href="/products/mouse" class="link">View details</a>\n  </div>\n</div>';

  var SAMPLE_TABLE_HTML = '<table id="employees">\n  <thead>\n    <tr>\n      <th>Name</th>\n      <th>Department</th>\n      <th>Email</th>\n      <th>Salary</th>\n    </tr>\n  </thead>\n  <tbody>\n    <tr>\n      <td>Alice Johnson</td>\n      <td>Engineering</td>\n      <td>alice@example.com</td>\n      <td>$95,000</td>\n    </tr>\n    <tr>\n      <td>Bob Smith</td>\n      <td>Marketing</td>\n      <td>bob@example.com</td>\n      <td>$72,000</td>\n    </tr>\n    <tr>\n      <td>Carol White</td>\n      <td>Engineering</td>\n      <td>carol@example.com</td>\n      <td>$102,000</td>\n    </tr>\n    <tr>\n      <td>Dave Brown</td>\n      <td>Sales</td>\n      <td>dave@example.com</td>\n      <td>$68,000</td>\n    </tr>\n  </tbody>\n</table>';

  var SAMPLE_JSON = '{\n  "store": {\n    "name": "Tech Shop",\n    "location": "San Francisco",\n    "book": [\n      {\n        "category": "programming",\n        "author": "Douglas Crockford",\n        "title": "JavaScript: The Good Parts",\n        "price": 29.99\n      },\n      {\n        "category": "programming",\n        "author": "Marijn Haverbeke",\n        "title": "Eloquent JavaScript",\n        "price": 24.99\n      },\n      {\n        "category": "data",\n        "author": "Wes McKinney",\n        "title": "Python for Data Analysis",\n        "price": 39.99\n      }\n    ],\n    "electronics": [\n      { "type": "laptop", "brand": "ThinkPad", "price": 1299 },\n      { "type": "monitor", "brand": "Dell", "price": 549 }\n    ]\n  }\n}';

  // ============================================================
  //  TAB 1: HTML PARSER
  // ============================================================
  var htmlMatches = [];

  window.wsHtmlExtract = function() {
    var html = document.getElementById('wsHtmlInput').value.trim();
    var selector = document.getElementById('wsHtmlSelector').value.trim();
    var resultsEl = document.getElementById('wsHtmlResults');
    var countEl = document.getElementById('wsHtmlCount');
    htmlMatches = [];

    if (!html) { resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">Paste HTML source first.</span>'; countEl.style.display = 'none'; return; }
    if (!selector) { resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">Enter a CSS selector.</span>'; countEl.style.display = 'none'; return; }

    var doc = parseDom(html);
    var elements;
    try {
      elements = doc.querySelectorAll(selector);
    } catch (e) {
      resultsEl.innerHTML = '<span style="color:var(--ws-error)">Invalid selector: ' + escHtml(e.message) + '</span>';
      countEl.style.display = 'none';
      return;
    }

    if (elements.length === 0) {
      resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">No elements matched selector "' + escHtml(selector) + '"</span>';
      countEl.style.display = 'inline-flex';
      countEl.textContent = '0 matches';
      return;
    }

    var out = '';
    for (var i = 0; i < elements.length; i++) {
      var el = elements[i];
      var tag = el.tagName.toLowerCase();
      var text = el.textContent.trim().substring(0, 300);
      var attrs = {};
      for (var a = 0; a < el.attributes.length; a++) {
        attrs[el.attributes[a].name] = el.attributes[a].value;
      }
      htmlMatches.push({ tag: tag, text: text, attributes: attrs, html: el.outerHTML.substring(0, 500) });

      out += '<div class="ws-match-item">';
      out += '<div class="ws-match-tag">&lt;' + escHtml(tag) + '&gt;';
      if (Object.keys(attrs).length > 0) {
        out += ' <span class="ws-match-attrs">';
        var attrList = [];
        for (var k in attrs) {
          if (attrs.hasOwnProperty(k)) attrList.push(escHtml(k) + '="' + escHtml(attrs[k]) + '"');
        }
        out += attrList.join(' ');
        out += '</span>';
      }
      out += '</div>';
      out += '<div class="ws-match-text">' + escHtml(text || '(empty)') + '</div>';
      out += '</div>';
    }

    resultsEl.innerHTML = out;
    countEl.style.display = 'inline-flex';
    countEl.textContent = elements.length + ' match' + (elements.length !== 1 ? 'es' : '');
  };

  window.wsHtmlExportJson = function() {
    if (htmlMatches.length === 0) return;
    var json = JSON.stringify(htmlMatches, null, 2);
    downloadFile(json, 'extracted-data.json', 'application/json');
  };

  window.wsHtmlExportCsv = function() {
    if (htmlMatches.length === 0) return;
    var allKeys = ['tag', 'text'];
    var attrKeys = {};
    for (var i = 0; i < htmlMatches.length; i++) {
      for (var k in htmlMatches[i].attributes) {
        if (htmlMatches[i].attributes.hasOwnProperty(k) && !attrKeys[k]) {
          attrKeys[k] = true;
          allKeys.push('attr_' + k);
        }
      }
    }
    var csv = allKeys.map(function(k) { return '"' + k + '"'; }).join(',') + '\n';
    for (var j = 0; j < htmlMatches.length; j++) {
      var row = [
        '"' + htmlMatches[j].tag.replace(/"/g, '""') + '"',
        '"' + htmlMatches[j].text.replace(/"/g, '""') + '"'
      ];
      for (var ak in attrKeys) {
        if (attrKeys.hasOwnProperty(ak)) {
          var val = htmlMatches[j].attributes[ak] || '';
          row.push('"' + val.replace(/"/g, '""') + '"');
        }
      }
      csv += row.join(',') + '\n';
    }
    downloadFile(csv, 'extracted-data.csv', 'text/csv');
  };

  window.wsHtmlClear = function() {
    document.getElementById('wsHtmlInput').value = '';
    document.getElementById('wsHtmlSelector').value = '';
    document.getElementById('wsHtmlResults').innerHTML = '';
    document.getElementById('wsHtmlCount').style.display = 'none';
    htmlMatches = [];
  };

  window.wsLoadSampleHtml = function() {
    document.getElementById('wsHtmlInput').value = SAMPLE_HTML;
    document.getElementById('wsHtmlSelector').value = '.product .title';
  };

  // ============================================================
  //  TAB 2: CSS SELECTOR TESTER
  // ============================================================
  function calcSpecificity(sel) {
    // Simplified specificity calculation
    var a = 0, b = 0, c = 0;
    // Remove :not() wrapper but count its contents
    var s = sel.replace(/:not\(([^)]*)\)/g, ' $1 ');
    // IDs
    var idMatch = s.match(/#[a-zA-Z_][\w-]*/g);
    if (idMatch) a = idMatch.length;
    // Classes, attributes, pseudo-classes
    var classMatch = s.match(/\.[a-zA-Z_][\w-]*/g);
    var attrMatch = s.match(/\[[^\]]+\]/g);
    var pseudoClass = s.match(/:(?!not)[a-zA-Z][\w-]*/g);
    b = (classMatch ? classMatch.length : 0) + (attrMatch ? attrMatch.length : 0) + (pseudoClass ? pseudoClass.length : 0);
    // Elements, pseudo-elements
    var temp = s.replace(/#[a-zA-Z_][\w-]*/g, '').replace(/\.[a-zA-Z_][\w-]*/g, '').replace(/\[[^\]]+\]/g, '').replace(/:(?!not)[a-zA-Z][\w-]*/g, '').replace(/::[a-zA-Z][\w-]*/g, function(m) { c++; return ''; });
    var elMatch = temp.match(/(?:^|\s|>|\+|~)([a-zA-Z][\w-]*)/g);
    if (elMatch) c += elMatch.length;
    return [a, b, c];
  }

  window.wsSelectorLive = function() {
    var html = document.getElementById('wsSelectorHtml').value.trim();
    var selector = document.getElementById('wsSelectorInput').value.trim();
    var previewEl = document.getElementById('wsSelectorPreview');
    var labelEl = document.getElementById('wsSelectorMatchLabel');
    var specEl = document.getElementById('wsSelectorSpecificity');

    if (!html) {
      previewEl.innerHTML = '<span style="color:var(--ws-text-dim)">Paste HTML on the left...</span>';
      labelEl.textContent = 'Matched Elements (0)';
      specEl.innerHTML = '';
      return;
    }

    if (!selector) {
      previewEl.innerHTML = escHtml(html);
      labelEl.textContent = 'Matched Elements (0)';
      specEl.innerHTML = '';
      return;
    }

    var doc = parseDom(html);
    var elements;
    try {
      elements = doc.querySelectorAll(selector);
    } catch (e) {
      previewEl.innerHTML = '<span style="color:var(--ws-error)">Invalid selector</span>';
      labelEl.textContent = 'Matched Elements (0)';
      specEl.innerHTML = '';
      return;
    }

    // Calculate specificity
    var spec = calcSpecificity(selector);
    specEl.innerHTML = '<span class="ws-spec-part" title="IDs">a:' + spec[0] + '</span><span class="ws-spec-part" title="Classes">b:' + spec[1] + '</span><span class="ws-spec-part" title="Elements">c:' + spec[2] + '</span>';

    labelEl.textContent = 'Matched Elements (' + elements.length + ')';

    // Show matched elements
    if (elements.length === 0) {
      previewEl.innerHTML = '<span style="color:var(--ws-text-dim)">No matches found</span>';
      return;
    }

    var out = '';
    for (var i = 0; i < elements.length; i++) {
      var el = elements[i];
      out += '<div class="ws-match-item">';
      out += '<div class="ws-match-tag">&lt;' + escHtml(el.tagName.toLowerCase()) + '&gt;</div>';
      out += '<div class="ws-match-text">' + escHtml(el.textContent.trim().substring(0, 200) || '(empty)') + '</div>';
      if (el.outerHTML) {
        out += '<div style="margin-top:4px;font-size:0.76rem;color:var(--ws-text-dim);word-break:break-all;">' + escHtml(el.outerHTML.substring(0, 200)) + '</div>';
      }
      out += '</div>';
    }
    previewEl.innerHTML = out;
  };

  window.wsSelectorTest = function() {
    wsSelectorLive();
  };

  window.wsInsertSelector = function(sel) {
    document.getElementById('wsSelectorInput').value = sel;
    wsSelectorLive();
  };

  window.wsLoadSampleSelector = function() {
    document.getElementById('wsSelectorHtml').value = SAMPLE_HTML;
    document.getElementById('wsSelectorInput').value = '.product .title';
    wsSelectorLive();
  };

  // ============================================================
  //  TAB 3: TABLE EXTRACTOR
  // ============================================================
  var tableData = { headers: [], rows: [], renamedHeaders: [] };

  window.wsTableExtract = function() {
    var html = document.getElementById('wsTableInput').value.trim();
    var statusEl = document.getElementById('wsTableStatus');
    var previewEl = document.getElementById('wsTablePreview');
    tableData = { headers: [], rows: [], renamedHeaders: [] };

    if (!html) {
      statusEl.style.display = 'block';
      statusEl.innerHTML = '<span style="color:var(--ws-text-dim)">Paste HTML containing a table.</span>';
      previewEl.style.display = 'none';
      return;
    }

    var doc = parseDom(html);
    var tables = doc.querySelectorAll('table');
    if (tables.length === 0) {
      statusEl.style.display = 'block';
      statusEl.innerHTML = '<span style="color:var(--ws-error)">No &lt;table&gt; elements found in the HTML.</span>';
      previewEl.style.display = 'none';
      return;
    }

    statusEl.style.display = 'block';
    statusEl.innerHTML = '<span style="color:var(--ws-secondary)">Found ' + tables.length + ' table' + (tables.length > 1 ? 's' : '') + '. Showing first table.</span>';

    var table = tables[0];
    var thElems = table.querySelectorAll('thead th, thead td, tr:first-child th');
    var headers = [];
    for (var h = 0; h < thElems.length; h++) {
      headers.push(thElems[h].textContent.trim());
    }

    var bodyRows = table.querySelectorAll('tbody tr');
    if (bodyRows.length === 0) {
      bodyRows = table.querySelectorAll('tr');
      // skip first row if we got headers from it
      if (headers.length > 0 && bodyRows.length > 0) {
        bodyRows = Array.prototype.slice.call(bodyRows, 1);
      }
    }

    // If no headers found, generate column names
    if (headers.length === 0 && bodyRows.length > 0) {
      var firstRowCells = bodyRows[0].querySelectorAll('td, th');
      for (var fi = 0; fi < firstRowCells.length; fi++) {
        headers.push('Column ' + (fi + 1));
      }
    }

    var rows = [];
    for (var r = 0; r < bodyRows.length; r++) {
      var cells = bodyRows[r].querySelectorAll('td, th');
      var row = [];
      for (var c = 0; c < cells.length; c++) {
        row.push(cells[c].textContent.trim());
      }
      rows.push(row);
    }

    tableData.headers = headers;
    tableData.renamedHeaders = headers.slice();
    tableData.rows = rows;

    renderTablePreview();
  };

  function renderTablePreview() {
    var previewEl = document.getElementById('wsTablePreview');
    if (tableData.rows.length === 0) { previewEl.style.display = 'none'; return; }

    previewEl.style.display = 'block';
    var out = '<table><thead><tr>';
    for (var h = 0; h < tableData.headers.length; h++) {
      out += '<th>' + escHtml(tableData.headers[h]);
      out += '<input class="ws-col-rename" type="text" value="' + escHtml(tableData.renamedHeaders[h]) + '" data-col="' + h + '" placeholder="Rename..." onchange="wsRenameCol(this)">';
      out += '</th>';
    }
    out += '</tr></thead><tbody>';
    for (var r = 0; r < tableData.rows.length; r++) {
      out += '<tr>';
      for (var c = 0; c < tableData.rows[r].length; c++) {
        out += '<td>' + escHtml(tableData.rows[r][c]) + '</td>';
      }
      out += '</tr>';
    }
    out += '</tbody></table>';
    previewEl.innerHTML = out;
  }

  window.wsRenameCol = function(el) {
    var col = parseInt(el.getAttribute('data-col'), 10);
    tableData.renamedHeaders[col] = el.value || tableData.headers[col];
  };

  function getTableJson() {
    var result = [];
    for (var r = 0; r < tableData.rows.length; r++) {
      var obj = {};
      for (var c = 0; c < tableData.renamedHeaders.length; c++) {
        obj[tableData.renamedHeaders[c]] = tableData.rows[r][c] || '';
      }
      result.push(obj);
    }
    return result;
  }

  function getTableCsv() {
    var csv = tableData.renamedHeaders.map(function(h) { return '"' + h.replace(/"/g, '""') + '"'; }).join(',') + '\n';
    for (var r = 0; r < tableData.rows.length; r++) {
      csv += tableData.rows[r].map(function(v) { return '"' + (v || '').replace(/"/g, '""') + '"'; }).join(',') + '\n';
    }
    return csv;
  }

  window.wsTableExportJson = function() {
    if (tableData.rows.length === 0) return;
    var json = JSON.stringify(getTableJson(), null, 2);
    downloadFile(json, 'table-data.json', 'application/json');
  };

  window.wsTableExportCsv = function() {
    if (tableData.rows.length === 0) return;
    downloadFile(getTableCsv(), 'table-data.csv', 'text/csv');
  };

  window.wsTableCopy = function() {
    if (tableData.rows.length === 0) return;
    var json = JSON.stringify(getTableJson(), null, 2);
    copyText(json, document.getElementById('wsTableCopyBtn'));
  };

  window.wsTableDownload = function() {
    if (tableData.rows.length === 0) return;
    var json = JSON.stringify(getTableJson(), null, 2);
    downloadFile(json, 'table-data.json', 'application/json');
  };

  window.wsTableClear = function() {
    document.getElementById('wsTableInput').value = '';
    document.getElementById('wsTableStatus').style.display = 'none';
    document.getElementById('wsTablePreview').style.display = 'none';
    tableData = { headers: [], rows: [], renamedHeaders: [] };
  };

  window.wsLoadSampleTable = function() {
    document.getElementById('wsTableInput').value = SAMPLE_TABLE_HTML;
  };

  // ============================================================
  //  TAB 4: JSONPATH EXTRACTOR
  // ============================================================
  function jsonPathQuery(obj, path) {
    // Lightweight JSONPath implementation
    var results = [];

    if (!path || path === '$') return [obj];

    // Normalize path
    var tokens = [];
    var normalized = path.replace(/^\$\.?/, '');

    // Tokenize
    var i = 0;
    while (i < normalized.length) {
      if (normalized[i] === '.') {
        if (normalized[i + 1] === '.') {
          tokens.push({ type: 'recurse' });
          i += 2;
        } else {
          i++;
        }
      } else if (normalized[i] === '[') {
        var end = normalized.indexOf(']', i);
        if (end === -1) break;
        var inner = normalized.substring(i + 1, end).trim();
        if (inner === '*') {
          tokens.push({ type: 'wildcard' });
        } else if (inner.indexOf(':') !== -1) {
          var parts = inner.split(':');
          tokens.push({ type: 'slice', start: parts[0] ? parseInt(parts[0], 10) : 0, end: parts[1] ? parseInt(parts[1], 10) : undefined });
        } else if (/^-?\d+$/.test(inner)) {
          tokens.push({ type: 'index', value: parseInt(inner, 10) });
        } else if (inner.charAt(0) === "'" || inner.charAt(0) === '"') {
          tokens.push({ type: 'key', value: inner.replace(/^['"]|['"]$/g, '') });
        } else {
          tokens.push({ type: 'key', value: inner });
        }
        i = end + 1;
      } else if (normalized[i] === '*') {
        tokens.push({ type: 'wildcard' });
        i++;
      } else {
        var next = normalized.length;
        var dotPos = normalized.indexOf('.', i);
        var brackPos = normalized.indexOf('[', i);
        if (dotPos !== -1 && dotPos < next) next = dotPos;
        if (brackPos !== -1 && brackPos < next) next = brackPos;
        var key = normalized.substring(i, next);
        if (key) tokens.push({ type: 'key', value: key });
        i = next;
      }
    }

    function walk(current, tokenIdx) {
      if (tokenIdx >= tokens.length) {
        results.push(current);
        return;
      }
      var token = tokens[tokenIdx];

      if (token.type === 'key') {
        if (current !== null && typeof current === 'object' && token.value in current) {
          walk(current[token.value], tokenIdx + 1);
        }
      } else if (token.type === 'index') {
        if (Array.isArray(current)) {
          var idx = token.value < 0 ? current.length + token.value : token.value;
          if (idx >= 0 && idx < current.length) {
            walk(current[idx], tokenIdx + 1);
          }
        }
      } else if (token.type === 'wildcard') {
        if (current !== null && typeof current === 'object') {
          var keys = Array.isArray(current) ? current.map(function(_, i) { return i; }) : Object.keys(current);
          for (var k = 0; k < keys.length; k++) {
            walk(current[keys[k]], tokenIdx + 1);
          }
        }
      } else if (token.type === 'slice') {
        if (Array.isArray(current)) {
          var s = token.start < 0 ? current.length + token.start : token.start;
          var e = token.end === undefined ? current.length : (token.end < 0 ? current.length + token.end : token.end);
          for (var si = Math.max(0, s); si < Math.min(current.length, e); si++) {
            walk(current[si], tokenIdx + 1);
          }
        }
      } else if (token.type === 'recurse') {
        // Apply remaining tokens at every level
        walk(current, tokenIdx + 1);
        if (current !== null && typeof current === 'object') {
          var vals = Array.isArray(current) ? current : Object.keys(current).map(function(k) { return current[k]; });
          for (var v = 0; v < vals.length; v++) {
            walk(vals[v], tokenIdx);
          }
        }
      }
    }

    walk(obj, 0);
    return results;
  }

  window.wsJsonPathExtract = function() {
    var input = document.getElementById('wsJsonPathInput').value.trim();
    var expr = document.getElementById('wsJsonPathExpr').value.trim();
    var resultsEl = document.getElementById('wsJsonPathResults');

    if (!input) { resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">Paste JSON data first.</span>'; return; }
    if (!expr) { resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">Enter a JSONPath expression.</span>'; return; }

    var data;
    try {
      data = JSON.parse(input);
    } catch (e) {
      resultsEl.innerHTML = '<span style="color:var(--ws-error)">Invalid JSON: ' + escHtml(e.message) + '</span>';
      return;
    }

    try {
      var results = jsonPathQuery(data, expr);
      if (results.length === 0) {
        resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">No results for "' + escHtml(expr) + '"</span>';
        return;
      }

      var out = '<div class="ws-match-count" style="margin-bottom:10px;">' + results.length + ' result' + (results.length !== 1 ? 's' : '') + '</div>';
      for (var i = 0; i < results.length; i++) {
        var val = results[i];
        var display = typeof val === 'object' ? JSON.stringify(val, null, 2) : String(val);
        out += '<div class="ws-match-item"><div class="ws-match-text" style="white-space:pre-wrap;">' + escHtml(display) + '</div></div>';
      }
      resultsEl.innerHTML = out;
    } catch (e) {
      resultsEl.innerHTML = '<span style="color:var(--ws-error)">JSONPath error: ' + escHtml(e.message) + '</span>';
    }
  };

  window.wsJsonPathCopy = function() {
    var resultsEl = document.getElementById('wsJsonPathResults');
    var items = resultsEl.querySelectorAll('.ws-match-text');
    if (items.length === 0) return;
    var texts = [];
    for (var i = 0; i < items.length; i++) {
      texts.push(items[i].textContent);
    }
    copyText(texts.join('\n'));
  };

  window.wsJsonPathClear = function() {
    document.getElementById('wsJsonPathInput').value = '';
    document.getElementById('wsJsonPathExpr').value = '';
    document.getElementById('wsJsonPathResults').innerHTML = '';
  };

  window.wsLoadSampleJsonPath = function() {
    document.getElementById('wsJsonPathInput').value = SAMPLE_JSON;
    document.getElementById('wsJsonPathExpr').value = '$.store.book[*].title';
  };

  window.wsInsertJsonPath = function(expr) {
    document.getElementById('wsJsonPathExpr').value = expr;
  };

  // ============================================================
  //  REGEX MATCHER
  // ============================================================
  window.wsRegexMatch = function() {
    var pattern = document.getElementById('wsRegexPattern').value;
    var text = document.getElementById('wsRegexText').value;
    var resultsEl = document.getElementById('wsRegexResults');
    var isGlobal = document.getElementById('wsRegexGlobal').checked;
    var isCase = document.getElementById('wsRegexCase').checked;

    if (!pattern || !text) { resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">Enter a pattern and text.</span>'; return; }

    var flags = '';
    if (isGlobal) flags += 'g';
    if (isCase) flags += 'i';

    var regex;
    try {
      regex = new RegExp(pattern, flags);
    } catch (e) {
      resultsEl.innerHTML = '<span style="color:var(--ws-error)">Invalid regex: ' + escHtml(e.message) + '</span>';
      return;
    }

    var matches = [];
    var match;
    if (isGlobal) {
      while ((match = regex.exec(text)) !== null) {
        matches.push(match[0]);
        if (matches.length > 500) break;
      }
    } else {
      match = regex.exec(text);
      if (match) matches.push(match[0]);
    }

    if (matches.length === 0) {
      resultsEl.innerHTML = '<span style="color:var(--ws-text-dim)">No matches found.</span>';
      return;
    }

    var out = '<div style="margin-bottom:6px;font-size:0.78rem;color:var(--ws-text-muted);">' + matches.length + ' match' + (matches.length !== 1 ? 'es' : '') + '</div>';
    for (var i = 0; i < matches.length; i++) {
      out += '<div class="ws-regex-match">' + escHtml(matches[i]) + '</div>';
    }
    resultsEl.innerHTML = out;
  };

  // ============================================================
  //  URL PARSER
  // ============================================================
  window.wsParseUrl = function() {
    var input = document.getElementById('wsUrlInput').value.trim();
    var partsEl = document.getElementById('wsUrlParts');

    if (!input) { partsEl.style.display = 'none'; return; }

    var url;
    try {
      url = new URL(input);
    } catch (e) {
      partsEl.style.display = 'grid';
      partsEl.innerHTML = '<span class="ws-url-label">Error</span><span class="ws-url-value" style="color:var(--ws-error);">Invalid URL format</span>';
      return;
    }

    partsEl.style.display = 'grid';
    var parts = [
      ['Protocol', url.protocol],
      ['Host', url.hostname],
      ['Port', url.port || '(default)'],
      ['Path', url.pathname],
      ['Search', url.search || '(none)'],
      ['Hash', url.hash || '(none)'],
      ['Origin', url.origin]
    ];

    // Parse query params
    var params = url.searchParams;
    var paramList = [];
    params.forEach(function(val, key) {
      paramList.push([key, val]);
    });

    var out = '';
    for (var i = 0; i < parts.length; i++) {
      out += '<span class="ws-url-label">' + parts[i][0] + '</span><span class="ws-url-value">' + escHtml(parts[i][1]) + '</span>';
    }

    if (paramList.length > 0) {
      out += '<span class="ws-url-label" style="grid-column:1/-1;margin-top:8px;color:var(--ws-primary-light);font-weight:600;">Query Parameters</span><span></span>';
      for (var p = 0; p < paramList.length; p++) {
        out += '<span class="ws-url-label">' + escHtml(paramList[p][0]) + '</span><span class="ws-url-value">' + escHtml(paramList[p][1]) + '</span>';
      }
    }

    partsEl.innerHTML = out;
  };

  // ============================================================
  //  KEYBOARD SHORTCUTS
  // ============================================================
  document.addEventListener('keydown', function(e) {
    if (e.key === 'Enter' && (e.ctrlKey || e.metaKey)) {
      var activeTab = document.querySelector('.ws-tab.active');
      if (!activeTab) return;
      var tabId = activeTab.getAttribute('data-tab');
      if (tabId === 'html-parser') wsHtmlExtract();
      else if (tabId === 'selector-tester') wsSelectorTest();
      else if (tabId === 'table-extractor') wsTableExtract();
      else if (tabId === 'jsonpath') wsJsonPathExtract();
    }
  });

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Web Scraper & Data Extractor",
      "url": "https://theluckystrike.github.io/tools/web-scraper/",
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
        { "@type": "ListItem", "position": 3, "name": "Web Scraper & Data Extractor", "item": "https://theluckystrike.github.io/tools/web-scraper/" }
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
