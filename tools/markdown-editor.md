---
layout: page
title: "Free Markdown Editor — Live Preview, Export HTML & PDF | Zovo"
description: "Write and preview Markdown in real-time. Supports GFM tables, code blocks, task lists, and math. Export as HTML, copy rendered output, or download your document."
permalink: /tools/markdown-editor/
keywords: "markdown editor, markdown preview, markdown to html, online markdown editor, markdown renderer, gfm editor, markdown viewer, markdown converter"
date: 2026-03-19
categories: [tools]
tags: [markdown, editor, preview, html, gfm, writing, developer]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  body {
    margin: 0;
    padding: 0;
    background: #0a0a0f !important;
  }

  :root {
    --md-primary: #6C5CE7;
    --md-primary-dark: #5A4BD1;
    --md-primary-light: #A29BFE;
    --md-bg: #0a0a0f;
    --md-surface: #12121a;
    --md-surface-alt: #181824;
    --md-border: #1e1e2e;
    --md-border-light: #2a2a3e;
    --md-text: #e0e0e0;
    --md-text-muted: #8888aa;
    --md-green: #00ff88;
    --md-green-dark: #00cc6a;
    --md-yellow: #ffaa00;
    --md-red: #ff4466;
    --md-blue: #4fc3f7;
    --md-radius: 12px;
  }

  .md-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--md-text);
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px;
    line-height: 1.6;
  }

  .md-wrapper * {
    box-sizing: border-box;
  }

  /* Hero */
  .md-hero {
    text-align: center;
    padding: 48px 0 28px;
  }

  .md-hero h1 {
    font-size: 2.4rem;
    font-weight: 800;
    color: #ffffff;
    margin: 0 0 16px;
    line-height: 1.15;
    letter-spacing: -0.02em;
  }

  .md-hero h1 span {
    background: linear-gradient(135deg, var(--md-primary), var(--md-primary-light));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .md-hero-intro {
    font-size: 1.05rem;
    color: var(--md-text-muted);
    max-width: 680px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .md-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--md-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--md-border);
    border-radius: 20px;
  }

  /* Toolbar */
  .md-toolbar {
    display: flex;
    align-items: center;
    gap: 4px;
    padding: 8px 12px;
    background: var(--md-surface);
    border: 1px solid var(--md-border);
    border-radius: 10px 10px 0 0;
    flex-wrap: wrap;
  }

  .md-tool-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    background: transparent;
    border: 1px solid transparent;
    border-radius: 6px;
    color: var(--md-text-muted);
    cursor: pointer;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    font-weight: 600;
    transition: all 0.15s;
    padding: 0;
  }

  .md-tool-btn:hover {
    background: var(--md-surface-alt);
    border-color: var(--md-border);
    color: var(--md-text);
  }

  .md-tool-btn.active {
    background: rgba(108, 92, 231, 0.15);
    border-color: var(--md-primary);
    color: var(--md-primary-light);
  }

  .md-tool-sep {
    width: 1px;
    height: 20px;
    background: var(--md-border);
    margin: 0 4px;
  }

  .md-toolbar-right {
    margin-left: auto;
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .md-stats {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--md-text-muted);
    margin-right: 8px;
    white-space: nowrap;
  }

  /* Editor Layout */
  .md-editor-container {
    display: flex;
    border: 1px solid var(--md-border);
    border-top: none;
    border-radius: 0 0 10px 10px;
    overflow: hidden;
    min-height: 520px;
    background: var(--md-surface);
    box-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .md-editor-pane {
    flex: 1;
    display: flex;
    flex-direction: column;
    min-width: 0;
  }

  .md-editor-pane.hidden-pane {
    display: none;
  }

  .md-pane-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 8px 16px;
    border-bottom: 1px solid var(--md-border);
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--md-text-muted);
  }

  .md-divider {
    width: 4px;
    background: var(--md-border);
    cursor: col-resize;
    flex-shrink: 0;
    transition: background 0.2s;
  }

  .md-divider:hover {
    background: var(--md-primary);
  }

  /* Editor textarea */
  .md-editor-area {
    flex: 1;
    width: 100%;
    border: none;
    padding: 16px 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.88rem;
    line-height: 1.7;
    color: var(--md-text);
    background: var(--md-bg);
    resize: none;
    outline: none;
    tab-size: 2;
    -moz-tab-size: 2;
  }

  .md-editor-area::placeholder {
    color: #444460;
  }

  /* Preview pane */
  .md-preview-area {
    flex: 1;
    padding: 16px 24px;
    overflow-y: auto;
    font-family: 'Inter', sans-serif;
    font-size: 0.92rem;
    line-height: 1.7;
    color: var(--md-text);
    background: var(--md-bg);
  }

  .md-preview-area.light-preview {
    background: #ffffff;
    color: #1a1a2e;
  }

  /* Preview typography */
  .md-preview-area h1 {
    font-size: 1.8rem;
    font-weight: 800;
    color: #ffffff;
    margin: 0 0 16px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--md-border);
    line-height: 1.25;
  }

  .md-preview-area h2 {
    font-size: 1.45rem;
    font-weight: 700;
    color: #ffffff;
    margin: 28px 0 12px;
    padding-bottom: 6px;
    border-bottom: 1px solid var(--md-border);
    line-height: 1.3;
  }

  .md-preview-area h3 {
    font-size: 1.2rem;
    font-weight: 700;
    color: #ffffff;
    margin: 24px 0 10px;
  }

  .md-preview-area h4 {
    font-size: 1.05rem;
    font-weight: 600;
    color: var(--md-text);
    margin: 20px 0 8px;
  }

  .md-preview-area h5 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--md-text);
    margin: 16px 0 6px;
  }

  .md-preview-area h6 {
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--md-text-muted);
    margin: 16px 0 6px;
  }

  .md-preview-area p {
    margin: 0 0 14px;
    line-height: 1.75;
  }

  .md-preview-area a {
    color: var(--md-primary-light);
    text-decoration: none;
  }

  .md-preview-area a:hover {
    text-decoration: underline;
  }

  .md-preview-area strong {
    font-weight: 700;
    color: #ffffff;
  }

  .md-preview-area em {
    font-style: italic;
  }

  .md-preview-area del {
    text-decoration: line-through;
    color: var(--md-text-muted);
  }

  .md-preview-area code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.84rem;
    background: var(--md-surface-alt);
    border: 1px solid var(--md-border);
    border-radius: 4px;
    padding: 2px 6px;
    color: var(--md-green);
  }

  .md-preview-area pre {
    background: var(--md-surface);
    border: 1px solid var(--md-border);
    border-radius: 8px;
    padding: 16px 20px;
    overflow-x: auto;
    margin: 12px 0 16px;
    position: relative;
  }

  .md-preview-area pre code {
    background: none;
    border: none;
    padding: 0;
    font-size: 0.84rem;
    line-height: 1.6;
    color: var(--md-text);
  }

  .md-preview-area pre .md-lang-badge {
    position: absolute;
    top: 6px;
    right: 10px;
    font-size: 0.65rem;
    color: var(--md-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    font-family: 'JetBrains Mono', monospace;
  }

  /* Syntax highlighting classes */
  .md-preview-area pre .md-kw { color: var(--md-primary-light); }
  .md-preview-area pre .md-str { color: var(--md-green); }
  .md-preview-area pre .md-cm { color: #555570; font-style: italic; }
  .md-preview-area pre .md-num { color: var(--md-yellow); }
  .md-preview-area pre .md-fn { color: var(--md-blue); }

  .md-preview-area blockquote {
    margin: 12px 0 16px;
    padding: 10px 20px;
    border-left: 3px solid var(--md-primary);
    background: rgba(108, 92, 231, 0.06);
    border-radius: 0 6px 6px 0;
    color: var(--md-text-muted);
  }

  .md-preview-area blockquote p {
    margin: 0;
  }

  .md-preview-area ul,
  .md-preview-area ol {
    margin: 8px 0 16px;
    padding-left: 24px;
  }

  .md-preview-area li {
    margin-bottom: 4px;
    line-height: 1.65;
  }

  .md-preview-area li input[type="checkbox"] {
    margin-right: 8px;
    accent-color: var(--md-primary);
  }

  .md-preview-area table {
    width: 100%;
    border-collapse: collapse;
    margin: 12px 0 16px;
    font-size: 0.88rem;
  }

  .md-preview-area th,
  .md-preview-area td {
    padding: 8px 14px;
    border: 1px solid var(--md-border);
    text-align: left;
  }

  .md-preview-area th {
    background: var(--md-surface);
    color: var(--md-text-muted);
    font-weight: 600;
    text-transform: uppercase;
    font-size: 0.75rem;
    letter-spacing: 0.04em;
  }

  .md-preview-area td {
    background: var(--md-surface-alt);
  }

  .md-preview-area hr {
    border: none;
    height: 1px;
    background: var(--md-border);
    margin: 24px 0;
  }

  .md-preview-area img {
    max-width: 100%;
    border-radius: 8px;
    margin: 8px 0;
  }

  /* Light preview overrides */
  .md-preview-area.light-preview h1,
  .md-preview-area.light-preview h2,
  .md-preview-area.light-preview h3,
  .md-preview-area.light-preview strong {
    color: #1a1a2e;
  }

  .md-preview-area.light-preview h1,
  .md-preview-area.light-preview h2 {
    border-bottom-color: #e0e0e8;
  }

  .md-preview-area.light-preview h4,
  .md-preview-area.light-preview h5 {
    color: #2d2d44;
  }

  .md-preview-area.light-preview h6 {
    color: #666688;
  }

  .md-preview-area.light-preview code {
    background: #f0f0f8;
    border-color: #e0e0e8;
    color: #c0392b;
  }

  .md-preview-area.light-preview pre {
    background: #f8f8fc;
    border-color: #e0e0e8;
  }

  .md-preview-area.light-preview pre code {
    color: #2d2d44;
  }

  .md-preview-area.light-preview blockquote {
    background: rgba(108, 92, 231, 0.04);
    color: #555577;
  }

  .md-preview-area.light-preview th {
    background: #f0f0f8;
    color: #555577;
  }

  .md-preview-area.light-preview td {
    background: #ffffff;
    border-color: #e0e0e8;
  }

  .md-preview-area.light-preview hr {
    background: #e0e0e8;
  }

  .md-preview-area.light-preview a {
    color: var(--md-primary);
  }

  .md-preview-area.light-preview del {
    color: #888899;
  }

  /* Export bar */
  .md-export-bar {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-top: 12px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .md-export-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 10px 20px;
    border: 1px solid var(--md-border);
    border-radius: 8px;
    background: var(--md-surface);
    color: var(--md-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
  }

  .md-export-btn:hover {
    border-color: var(--md-primary);
    color: var(--md-primary-light);
    background: rgba(108, 92, 231, 0.06);
  }

  .md-export-btn.md-export-primary {
    background: var(--md-primary);
    border-color: var(--md-primary);
    color: #ffffff;
  }

  .md-export-btn.md-export-primary:hover {
    background: var(--md-primary-dark);
  }

  .md-autosave-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--md-text-muted);
    margin-left: auto;
  }

  .md-autosave-badge.saved {
    color: var(--md-green);
  }

  /* Cross-links */
  .md-cross-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin: 28px 0;
    padding: 20px;
    background: var(--md-surface);
    border: 1px solid var(--md-border);
    border-radius: var(--md-radius);
  }

  .md-cross-links a {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--md-surface-alt);
    border: 1px solid var(--md-border);
    border-radius: 8px;
    color: var(--md-text-muted);
    text-decoration: none;
    font-size: 0.82rem;
    font-weight: 500;
    transition: all 0.2s;
  }

  .md-cross-links a:hover {
    border-color: var(--md-primary);
    color: var(--md-primary-light);
    background: rgba(108, 92, 231, 0.06);
  }

  /* Content */
  .md-content {
    padding: 20px 0;
    max-width: 780px;
  }

  .md-content h2 {
    font-size: 1.45rem;
    font-weight: 700;
    color: #ffffff;
    margin: 36px 0 14px;
    line-height: 1.25;
  }

  .md-content p {
    font-size: 0.95rem;
    color: var(--md-text);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .md-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.84rem;
    background: var(--md-surface-alt);
    border: 1px solid var(--md-border);
    border-radius: 4px;
    padding: 2px 6px;
    color: var(--md-green);
  }

  .md-content table {
    width: 100%;
    border-collapse: collapse;
    margin: 16px 0 20px;
    font-size: 0.88rem;
  }

  .md-content th,
  .md-content td {
    padding: 10px 14px;
    border: 1px solid var(--md-border);
    text-align: left;
  }

  .md-content th {
    background: var(--md-surface);
    color: var(--md-text-muted);
    font-weight: 600;
    text-transform: uppercase;
    font-size: 0.75rem;
    letter-spacing: 0.05em;
  }

  .md-content td {
    background: var(--md-surface-alt);
  }

  /* FAQ */
  .md-faq {
    padding: 20px 0;
    max-width: 780px;
  }

  .md-faq h2 {
    font-size: 1.45rem;
    font-weight: 700;
    color: #ffffff;
    margin: 0 0 20px;
  }

  .md-faq-item {
    background: var(--md-surface);
    border: 1px solid var(--md-border);
    border-radius: 10px;
    margin-bottom: 10px;
    overflow: hidden;
  }

  .md-faq-item h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--md-text);
    margin: 0;
    padding: 16px 20px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: color 0.2s;
  }

  .md-faq-item h3:hover {
    color: var(--md-primary-light);
  }

  .md-faq-item h3::after {
    content: "+";
    font-size: 1.2rem;
    color: var(--md-text-muted);
    font-weight: 400;
    transition: transform 0.2s;
  }

  .md-faq-item.open h3::after {
    content: "-";
  }

  .md-faq-answer {
    display: none;
    padding: 0 20px 16px;
  }

  .md-faq-item.open .md-faq-answer {
    display: block;
  }

  .md-faq-answer p {
    font-size: 0.9rem;
    color: var(--md-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Author Box */
  .md-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    background: var(--md-surface);
    border: 1px solid var(--md-border);
    border-radius: var(--md-radius);
    padding: 20px 24px;
    margin: 32px 0 20px;
    max-width: 780px;
  }

  .md-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--md-primary), var(--md-primary-light));
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 0.9rem;
    color: #fff;
    flex-shrink: 0;
  }

  .md-author-info {
    flex: 1;
  }

  .md-author-name {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--md-text);
    margin: 0 0 4px;
  }

  .md-author-bio {
    font-size: 0.82rem;
    color: var(--md-text-muted);
    margin: 0;
    line-height: 1.5;
  }

  /* Footer */
  .md-footer {
    text-align: center;
    padding: 24px 0 40px;
    font-size: 0.82rem;
    color: var(--md-text-muted);
    border-top: 1px solid var(--md-border);
    margin-top: 20px;
  }

  .md-footer a {
    color: var(--md-primary-light);
    text-decoration: none;
  }

  .md-footer a:hover {
    text-decoration: underline;
  }

  /* Scrollbar */
  .md-wrapper ::-webkit-scrollbar {
    width: 6px;
  }

  .md-wrapper ::-webkit-scrollbar-track {
    background: var(--md-surface);
  }

  .md-wrapper ::-webkit-scrollbar-thumb {
    background: var(--md-border-light);
    border-radius: 3px;
  }

  /* Mobile */
  @media (max-width: 768px) {
    .md-hero h1 {
      font-size: 1.7rem;
    }

    .md-hero {
      padding: 32px 0 24px;
    }

    .md-editor-container {
      flex-direction: column;
      min-height: auto;
    }

    .md-divider {
      width: 100%;
      height: 4px;
      cursor: row-resize;
    }

    .md-editor-area {
      min-height: 280px;
    }

    .md-preview-area {
      min-height: 280px;
    }

    .md-toolbar {
      gap: 2px;
      padding: 6px 8px;
    }

    .md-tool-btn {
      width: 30px;
      height: 30px;
      font-size: 0.72rem;
    }

    .md-export-bar {
      flex-direction: column;
      align-items: stretch;
    }

    .md-cross-links {
      flex-direction: column;
    }

    .md-author-box {
      flex-direction: column;
      text-align: center;
    }
  }

  @media (max-width: 480px) {
    .md-stats {
      display: none;
    }

    .md-toolbar-right {
      margin-left: 0;
    }
  }
</style>

<div class="md-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Free Markdown Editor">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <!-- Hero -->
  <div class="md-hero">
    <h1>Free <span>Markdown Editor</span></h1>
    <p class="md-hero-intro">Write Markdown on the left, see the rendered output on the right. Supports headings, bold, italic, links, images, code blocks, tables, task lists, and more. Export as HTML or download your file. Everything runs in your browser.</p>
    <span class="md-updated">Last updated: March 19, 2026</span>
  </div>

  <!-- Toolbar -->
  <div class="md-toolbar">
    <button class="md-tool-btn" title="Bold (Ctrl+B)" onclick="mdInsert('**','**')">B</button>
    <button class="md-tool-btn" title="Italic (Ctrl+I)" onclick="mdInsert('*','*')" style="font-style:italic;">I</button>
    <button class="md-tool-btn" title="Strikethrough" onclick="mdInsert('~~','~~')">S</button>
    <span class="md-tool-sep"></span>
    <button class="md-tool-btn" title="Heading 1" onclick="mdPrefix('# ')">H1</button>
    <button class="md-tool-btn" title="Heading 2" onclick="mdPrefix('## ')">H2</button>
    <button class="md-tool-btn" title="Heading 3" onclick="mdPrefix('### ')">H3</button>
    <button class="md-tool-btn" title="Heading 4" onclick="mdPrefix('#### ')">H4</button>
    <button class="md-tool-btn" title="Heading 5" onclick="mdPrefix('##### ')">H5</button>
    <button class="md-tool-btn" title="Heading 6" onclick="mdPrefix('###### ')">H6</button>
    <span class="md-tool-sep"></span>
    <button class="md-tool-btn" title="Link" onclick="mdLink()">[&nbsp;]</button>
    <button class="md-tool-btn" title="Image" onclick="mdImage()">IMG</button>
    <button class="md-tool-btn" title="Inline Code" onclick="mdInsert('`','`')">&lt;/&gt;</button>
    <button class="md-tool-btn" title="Code Block" onclick="mdCodeBlock()" style="font-size:0.68rem;">PRE</button>
    <span class="md-tool-sep"></span>
    <button class="md-tool-btn" title="Blockquote" onclick="mdPrefix('> ')">Q</button>
    <button class="md-tool-btn" title="Unordered List" onclick="mdPrefix('- ')">UL</button>
    <button class="md-tool-btn" title="Ordered List" onclick="mdPrefix('1. ')">OL</button>
    <button class="md-tool-btn" title="Task List" onclick="mdPrefix('- [ ] ')">TL</button>
    <button class="md-tool-btn" title="Table" onclick="mdTable()">TBL</button>
    <button class="md-tool-btn" title="Horizontal Rule" onclick="mdHR()">HR</button>
    <span class="md-tool-sep"></span>

    <div class="md-toolbar-right">
      <span class="md-stats" id="mdStats">0 words, 0 chars</span>
      <button class="md-tool-btn" title="Editor Only" onclick="mdSetView('editor')" id="mdViewEditor">ED</button>
      <button class="md-tool-btn active" title="Split View" onclick="mdSetView('split')" id="mdViewSplit">SP</button>
      <button class="md-tool-btn" title="Preview Only" onclick="mdSetView('preview')" id="mdViewPreview">PV</button>
      <span class="md-tool-sep"></span>
      <button class="md-tool-btn" title="Toggle Light/Dark Preview" onclick="mdToggleTheme()" id="mdThemeBtn">LT</button>
    </div>
  </div>

  <!-- Editor + Preview -->
  <div class="md-editor-container" id="mdContainer">
    <div class="md-editor-pane" id="mdEditorPane">
      <div class="md-pane-header">
        <span>Markdown</span>
      </div>
      <textarea class="md-editor-area" id="mdEditor" placeholder="# Start writing Markdown here...

## Heading 2
Some paragraph text with **bold** and *italic*.

- List item one
- List item two

```javascript
console.log('Hello');
```" spellcheck="false"></textarea>
    </div>
    <div class="md-divider" id="mdDivider"></div>
    <div class="md-editor-pane" id="mdPreviewPane">
      <div class="md-pane-header">
        <span>Preview</span>
      </div>
      <div class="md-preview-area" id="mdPreview"></div>
    </div>
  </div>

  <!-- Export Bar -->
  <div class="md-export-bar">
    <button class="md-export-btn md-export-primary" onclick="mdCopyHtml()">Copy HTML</button>
    <button class="md-export-btn" onclick="mdDownloadHtml()">Download .html</button>
    <button class="md-export-btn" onclick="mdDownloadMd()">Download .md</button>
    <span class="md-autosave-badge" id="mdAutosave">Auto-save: off</span>
  </div>

  <!-- Cross-links -->
  <div class="md-cross-links">
    <a href="/tools/html-to-markdown/">HTML to Markdown</a>
    <a href="/tools/json-formatter/">JSON Formatter</a>
    <a href="/tools/word-counter/">Word Counter</a>
    <a href="/tools/diff-checker/">Diff Checker</a>
  </div>

  <!-- SEO Content -->
  <div class="md-content">

<h2>What Is Markdown</h2>

<p>Markdown is a plain text formatting language created by John Gruber in 2004. It uses simple symbols to indicate structure and styling: hash signs for headings, asterisks for bold and italic, hyphens for lists, backticks for code. The idea is that a Markdown document is readable as plain text, but a parser can convert it to HTML (or other formats) for styled output.</p>

<p>Markdown has become the default writing format for developer documentation, README files, wikis, static site generators, chat platforms, and note-taking apps. GitHub, GitLab, Bitbucket, Stack Overflow, Reddit, Discord, and Slack all support some variant of Markdown. Learning the syntax once gives you a writing tool that works across dozens of platforms.</p>

<p>The editor on this page parses Markdown in real time and renders the preview alongside your text. There are no external dependencies. The parser is built from scratch in JavaScript and handles all standard Markdown elements plus GitHub Flavored Markdown (GFM) extensions like tables, task lists, and strikethrough.</p>

<h2>Basic Markdown Syntax</h2>

<p>Headings use one to six hash characters at the start of a line. <code># Heading 1</code> produces the largest heading, <code>###### Heading 6</code> the smallest. A space between the hash and the text is required.</p>

<p>Bold text wraps in double asterisks: <code>**bold**</code>. Italic wraps in single asterisks: <code>*italic*</code>. Strikethrough wraps in double tildes: <code>~~deleted~~</code>. These can nest, so <code>***bold italic***</code> produces text that is both.</p>

<p>Links use the format <code>[link text](url)</code>. Images use <code>![alt text](url)</code>. Inline code wraps in single backticks. Code blocks use triple backticks on their own lines, with an optional language identifier after the opening backticks for syntax highlighting.</p>

<p>Unordered lists start each line with a hyphen, plus sign, or asterisk. Ordered lists start with a number and period. Task lists start with <code>- [ ]</code> for unchecked or <code>- [x]</code> for checked items. Blockquotes start with <code>&gt;</code> at the beginning of a line.</p>

<h2>GitHub Flavored Markdown</h2>

<p>GFM extends standard Markdown with features that developers use frequently. Tables use pipe characters to separate columns and hyphens to separate the header row from body rows. The alignment of colons in the separator row controls text alignment: <code>:---</code> for left, <code>:---:</code> for center, <code>---:</code> for right.</p>

<p>Task lists add interactive checkboxes to list items. Strikethrough text uses the double tilde syntax. Autolinks convert bare URLs into clickable links. Fenced code blocks with language identifiers enable syntax highlighting. This editor supports all of these GFM features.</p>

<p>GFM also includes some behaviors that differ from standard Markdown. Line breaks within a paragraph are preserved (you do not need two trailing spaces). Single newlines between lines create a <code>&lt;br&gt;</code> rather than joining lines into one paragraph. This matches the behavior most people expect when writing in a text area.</p>

<h2>Markdown vs HTML</h2>

<p>Markdown is not a replacement for HTML. It is a subset. Anything you can write in Markdown converts to a specific set of HTML elements: paragraphs, headings, lists, links, images, code, tables, and blockquotes. If you need a <code>&lt;div&gt;</code> with a custom class, an embedded iframe, or a form element, you need raw HTML.</p>

<p>Most Markdown renderers (including this one) pass through raw HTML unchanged. So you can mix Markdown and HTML in the same document. The advantage of Markdown is speed: writing <code>## Section Title</code> is faster than writing <code>&lt;h2&gt;Section Title&lt;/h2&gt;</code>, and the source remains easier to read.</p>

<p>For blog posts, documentation, README files, and notes, Markdown covers everything you need. For full web pages with custom layouts, forms, or interactive elements, you still need HTML (and usually CSS and JavaScript). The "Copy HTML" and "Download .html" buttons in this editor make it easy to convert your Markdown to HTML when you need the output in that format.</p>

<h2>Using Markdown for Documentation</h2>

<p>Most open-source projects use Markdown for their documentation. The README.md file in a repository is the first thing visitors see on GitHub and GitLab. Contributing guides, changelogs, license files, and wiki pages all use Markdown. Static site generators like Jekyll, Hugo, Gatsby, and Astro use Markdown files as the content source for pages.</p>

<p>When writing documentation in Markdown, structure matters more than styling. Use headings consistently (H2 for main sections, H3 for subsections). Keep paragraphs short. Use code blocks for any terminal commands, configuration snippets, or API examples. Use tables for structured data like configuration options or API parameters. Use task lists for setup steps or checklists.</p>

<p>The auto-save feature in this editor stores your document in localStorage, so you do not lose work if you close the tab. The word and character count in the toolbar updates as you type, which is useful when writing to a length target.</p>

  </div>

  <!-- FAQ Section -->
  <div class="md-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="md-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Does this editor use any external libraries?</h3>
      <div class="md-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. The Markdown parser is built from scratch in JavaScript. It handles headings, bold, italic, strikethrough, links, images, inline code, fenced code blocks, blockquotes, ordered lists, unordered lists, task lists, GFM tables, horizontal rules, and line breaks. No marked.js, showdown, or any other dependency is loaded.</p>
      </div>
    </div>

    <div class="md-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Is my text saved automatically?</h3>
      <div class="md-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The editor saves your Markdown to your browser's localStorage every two seconds while you type. If you close the tab and reopen the page, your last draft is restored automatically. The auto-save badge in the export bar shows the save status. No data is sent to any server.</p>
      </div>
    </div>

    <div class="md-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">What syntax highlighting languages are supported?</h3>
      <div class="md-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The built-in syntax highlighter applies basic keyword, string, comment, and number coloring for JavaScript, TypeScript, Python, HTML, CSS, Go, Rust, Java, C, C++, PHP, Ruby, SQL, Bash, and JSON. The highlighting covers common patterns (keywords, quoted strings, line and block comments, numbers) but is not a full lexer. For production code highlighting, a dedicated library would provide more accuracy.</p>
      </div>
    </div>

    <div class="md-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Can I export to PDF?</h3>
      <div class="md-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The browser's built-in print function handles PDF export. Click Download .html, open the downloaded file in your browser, then use Ctrl+P (or Cmd+P on macOS) and select "Save as PDF" as the destination. This preserves the formatting from the preview. Alternatively, you can use the preview-only view mode and print directly from this page.</p>
      </div>
    </div>

    <div class="md-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Is my text sent to any server?</h3>
      <div class="md-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All parsing and rendering happens locally in your browser. Nothing is uploaded, tracked, or logged. The auto-save uses localStorage, which is stored on your device only. You can verify this by checking the Network tab in your browser's developer tools while using the editor.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="md-author-box">
    <div class="md-author-avatar">ML</div>
    <div class="md-author-info">
      <p class="md-author-name">Michael Lip</p>
      <p class="md-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="md-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Markdown Editor",
      "description": "Write and preview Markdown in real-time. Supports GFM tables, code blocks, task lists, and more. Export as HTML, copy rendered output, or download your document.",
      "url": "https://theluckystrike.github.io/tools/markdown-editor/",
      "applicationCategory": "UtilityApplication",
      "operatingSystem": "Any",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "USD"
      },
      "author": {
        "@type": "Person",
        "name": "Michael Lip",
        "url": "https://theluckystrike.github.io/about"
      }
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io"},
        {"@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/"},
        {"@type": "ListItem", "position": 3, "name": "Markdown Editor", "item": "https://theluckystrike.github.io/tools/markdown-editor/"}
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://theluckystrike.github.io/assets/images/zovo-logo.png"
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Does this editor use any external libraries?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. The Markdown parser is built from scratch in JavaScript with no external dependencies."
          }
        },
        {
          "@type": "Question",
          "name": "Is my text saved automatically?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. The editor saves to localStorage every two seconds. Your draft is restored when you reopen the page."
          }
        },
        {
          "@type": "Question",
          "name": "What syntax highlighting languages are supported?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Basic keyword, string, comment, and number coloring for JavaScript, TypeScript, Python, HTML, CSS, Go, Rust, Java, C, C++, PHP, Ruby, SQL, Bash, and JSON."
          }
        },
        {
          "@type": "Question",
          "name": "Can I export to PDF?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Use the browser's print function (Ctrl+P / Cmd+P) with 'Save as PDF' on the downloaded HTML file or in preview-only mode."
          }
        },
        {
          "@type": "Question",
          "name": "Is my text sent to any server?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All processing is local. Nothing is uploaded, tracked, or logged."
          }
        }
      ]
    }
  ]
}
</script>

<script>
(function() {
  "use strict";

  var elEditor = document.getElementById("mdEditor");
  var elPreview = document.getElementById("mdPreview");
  var elStats = document.getElementById("mdStats");
  var elEditorPane = document.getElementById("mdEditorPane");
  var elPreviewPane = document.getElementById("mdPreviewPane");
  var elDivider = document.getElementById("mdDivider");
  var elAutosave = document.getElementById("mdAutosave");

  var currentView = "split";
  var lightPreview = false;
  var saveTimer = null;
  var debounceTimer = null;

  // ========== MARKDOWN PARSER ==========

  function parseMd(src) {
    var lines = src.split("\n");
    var html = "";
    var i = 0;

    while (i < lines.length) {
      var line = lines[i];

      // Blank line
      if (line.trim() === "") {
        i++;
        continue;
      }

      // Fenced code block
      var codeMatch = line.match(/^```(\w*)\s*$/);
      if (codeMatch) {
        var lang = codeMatch[1] || "";
        var codeLines = [];
        i++;
        while (i < lines.length && !lines[i].match(/^```\s*$/)) {
          codeLines.push(lines[i]);
          i++;
        }
        i++; // skip closing ```
        var codeText = escapeHtml(codeLines.join("\n"));
        if (lang) {
          codeText = highlightSyntax(codeText, lang);
        }
        var badge = lang ? '<span class="md-lang-badge">' + escapeHtml(lang) + '</span>' : '';
        html += '<pre>' + badge + '<code>' + codeText + '</code></pre>\n';
        continue;
      }

      // Heading
      var headingMatch = line.match(/^(#{1,6})\s+(.+)$/);
      if (headingMatch) {
        var level = headingMatch[1].length;
        html += '<h' + level + '>' + parseInline(headingMatch[2]) + '</h' + level + '>\n';
        i++;
        continue;
      }

      // Horizontal rule
      if (line.match(/^(\-{3,}|\*{3,}|_{3,})\s*$/)) {
        html += '<hr>\n';
        i++;
        continue;
      }

      // Table
      if (i + 1 < lines.length && lines[i + 1].match(/^\|?\s*:?-+:?\s*(\|\s*:?-+:?\s*)*\|?\s*$/)) {
        var tableLines = [];
        while (i < lines.length && lines[i].trim() !== "" && lines[i].indexOf("|") !== -1) {
          tableLines.push(lines[i]);
          i++;
        }
        html += parseTable(tableLines);
        continue;
      }

      // Blockquote
      if (line.match(/^>\s?/)) {
        var quoteLines = [];
        while (i < lines.length && lines[i].match(/^>\s?/)) {
          quoteLines.push(lines[i].replace(/^>\s?/, ""));
          i++;
        }
        html += '<blockquote><p>' + parseInline(quoteLines.join("\n")) + '</p></blockquote>\n';
        continue;
      }

      // Unordered list / task list
      if (line.match(/^[\s]*[-*+]\s/)) {
        var result = parseList(lines, i, "ul");
        html += result.html;
        i = result.end;
        continue;
      }

      // Ordered list
      if (line.match(/^[\s]*\d+\.\s/)) {
        var result2 = parseList(lines, i, "ol");
        html += result2.html;
        i = result2.end;
        continue;
      }

      // Paragraph
      var paraLines = [];
      while (i < lines.length && lines[i].trim() !== "" &&
             !lines[i].match(/^#{1,6}\s/) &&
             !lines[i].match(/^```/) &&
             !lines[i].match(/^>\s?/) &&
             !lines[i].match(/^[-*+]\s/) &&
             !lines[i].match(/^\d+\.\s/) &&
             !lines[i].match(/^(\-{3,}|\*{3,}|_{3,})\s*$/) &&
             !(i + 1 < lines.length && lines[i + 1].match(/^\|?\s*:?-+:?\s*(\|\s*:?-+:?\s*)*\|?\s*$/) && lines[i].indexOf("|") !== -1)) {
        paraLines.push(lines[i]);
        i++;
      }
      if (paraLines.length > 0) {
        html += '<p>' + parseInline(paraLines.join("<br>\n")) + '</p>\n';
      }
    }

    return html;
  }

  function parseList(lines, start, type) {
    var items = [];
    var i = start;
    var pattern = type === "ul" ? /^[\s]*[-*+]\s(.*)/ : /^[\s]*\d+\.\s(.*)/;

    while (i < lines.length) {
      var m = lines[i].match(pattern);
      if (!m) break;
      var content = m[1];
      // Task list check
      var taskMatch = content.match(/^\[([ xX])\]\s?(.*)/);
      if (taskMatch) {
        var checked = taskMatch[1] !== " " ? ' checked disabled' : ' disabled';
        items.push('<li><input type="checkbox"' + checked + '> ' + parseInline(taskMatch[2]) + '</li>');
      } else {
        items.push('<li>' + parseInline(content) + '</li>');
      }
      i++;
    }

    var tag = type === "ul" ? "ul" : "ol";
    return { html: '<' + tag + '>\n' + items.join('\n') + '\n</' + tag + '>\n', end: i };
  }

  function parseTable(tableLines) {
    if (tableLines.length < 2) return "";

    function splitRow(line) {
      var cells = line.split("|");
      // Trim leading/trailing empty cells from pipe-bordered tables
      if (cells.length > 0 && cells[0].trim() === "") cells.shift();
      if (cells.length > 0 && cells[cells.length - 1].trim() === "") cells.pop();
      return cells.map(function(c) { return c.trim(); });
    }

    var headerCells = splitRow(tableLines[0]);
    var alignRow = splitRow(tableLines[1]);

    var aligns = alignRow.map(function(cell) {
      var c = cell.replace(/\s/g, "");
      if (c.match(/^:-+:$/)) return "center";
      if (c.match(/^-+:$/)) return "right";
      return "left";
    });

    var html = '<table>\n<thead>\n<tr>\n';
    for (var h = 0; h < headerCells.length; h++) {
      var a = aligns[h] || "left";
      html += '<th style="text-align:' + a + '">' + parseInline(headerCells[h]) + '</th>\n';
    }
    html += '</tr>\n</thead>\n<tbody>\n';

    for (var r = 2; r < tableLines.length; r++) {
      var cells = splitRow(tableLines[r]);
      html += '<tr>\n';
      for (var c = 0; c < headerCells.length; c++) {
        var align = aligns[c] || "left";
        var val = cells[c] || "";
        html += '<td style="text-align:' + align + '">' + parseInline(val) + '</td>\n';
      }
      html += '</tr>\n';
    }

    html += '</tbody>\n</table>\n';
    return html;
  }

  function parseInline(text) {
    // Images (before links so ![...](...) is matched first)
    text = text.replace(/!\[([^\]]*)\]\(([^)]+)\)/g, '<img src="$2" alt="$1">');
    // Links
    text = text.replace(/\[([^\]]+)\]\(([^)]+)\)/g, '<a href="$2" target="_blank" rel="noopener">$1</a>');
    // Bold + italic
    text = text.replace(/\*\*\*(.+?)\*\*\*/g, '<strong><em>$1</em></strong>');
    // Bold
    text = text.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
    // Italic
    text = text.replace(/\*(.+?)\*/g, '<em>$1</em>');
    // Strikethrough
    text = text.replace(/~~(.+?)~~/g, '<del>$1</del>');
    // Inline code
    text = text.replace(/`([^`]+)`/g, '<code>$1</code>');
    // Autolinks
    text = text.replace(/(^|[^"'>])((https?:\/\/)[^\s<]+)/g, '$1<a href="$2" target="_blank" rel="noopener">$2</a>');
    return text;
  }

  function escapeHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;");
  }

  // ========== SYNTAX HIGHLIGHTING ==========

  function highlightSyntax(code, lang) {
    lang = lang.toLowerCase();

    var keywords = [];
    var singleComment = "//";
    var multiStart = "/*";
    var multiEnd = "*/";
    var hashComment = false;

    if (lang === "javascript" || lang === "js" || lang === "typescript" || lang === "ts") {
      keywords = ["const","let","var","function","return","if","else","for","while","do","switch","case","break","continue","new","this","class","extends","import","export","default","from","async","await","try","catch","finally","throw","typeof","instanceof","of","in","null","undefined","true","false","yield","super","static","get","set","constructor"];
    } else if (lang === "python" || lang === "py") {
      keywords = ["def","class","return","if","elif","else","for","while","import","from","as","try","except","finally","raise","with","pass","break","continue","and","or","not","is","in","True","False","None","lambda","yield","global","nonlocal","del","assert","async","await"];
      singleComment = "#";
      hashComment = true;
    } else if (lang === "go") {
      keywords = ["func","package","import","var","const","type","struct","interface","map","chan","go","defer","return","if","else","for","range","switch","case","default","break","continue","select","fallthrough","nil","true","false","make","new","append","len","cap"];
    } else if (lang === "rust") {
      keywords = ["fn","let","mut","pub","struct","enum","impl","trait","use","mod","crate","self","super","return","if","else","for","while","loop","match","break","continue","move","async","await","unsafe","where","type","const","static","ref","true","false","Some","None","Ok","Err"];
    } else if (lang === "java" || lang === "c" || lang === "cpp" || lang === "c++") {
      keywords = ["public","private","protected","class","interface","extends","implements","static","final","void","int","long","double","float","char","boolean","byte","short","return","if","else","for","while","do","switch","case","break","continue","new","this","super","try","catch","finally","throw","throws","import","package","true","false","null","abstract","synchronized","volatile","const","enum","struct","typedef","sizeof","unsigned","signed","auto","register","extern","include","define","ifdef","ifndef","endif"];
    } else if (lang === "php") {
      keywords = ["function","class","public","private","protected","static","return","if","else","elseif","for","foreach","while","do","switch","case","break","continue","new","this","echo","print","require","include","use","namespace","try","catch","finally","throw","true","false","null","array","isset","unset","var"];
      hashComment = true;
    } else if (lang === "ruby" || lang === "rb") {
      keywords = ["def","class","module","end","return","if","elsif","else","unless","for","while","do","begin","rescue","ensure","raise","yield","block_given","true","false","nil","self","super","require","include","attr_accessor","attr_reader","attr_writer","puts","print"];
      singleComment = "#";
      hashComment = true;
    } else if (lang === "sql") {
      keywords = ["SELECT","FROM","WHERE","INSERT","INTO","VALUES","UPDATE","SET","DELETE","CREATE","TABLE","ALTER","DROP","INDEX","JOIN","INNER","LEFT","RIGHT","OUTER","ON","AND","OR","NOT","NULL","IS","IN","LIKE","BETWEEN","AS","ORDER","BY","GROUP","HAVING","LIMIT","OFFSET","UNION","ALL","DISTINCT","COUNT","SUM","AVG","MAX","MIN","PRIMARY","KEY","FOREIGN","REFERENCES","CASCADE","EXISTS","TRUE","FALSE"];
      singleComment = "--";
    } else if (lang === "bash" || lang === "sh" || lang === "shell" || lang === "zsh") {
      keywords = ["if","then","else","elif","fi","for","while","do","done","case","esac","function","return","exit","echo","printf","read","export","source","local","declare","unset","set","shift","trap","eval","exec","true","false","in"];
      singleComment = "#";
      hashComment = true;
    } else if (lang === "json") {
      // JSON: just strings, numbers, booleans, null
      return code
        .replace(/("(?:[^"\\]|\\.)*")\s*:/g, '<span class="md-fn">$1</span>:')
        .replace(/:(\s*"(?:[^"\\]|\\.)*")/g, ':<span class="md-str">$1</span>')
        .replace(/\b(true|false|null)\b/g, '<span class="md-kw">$1</span>')
        .replace(/\b(\d+\.?\d*)\b/g, '<span class="md-num">$1</span>');
    } else if (lang === "html" || lang === "xml") {
      return code
        .replace(/(&lt;\/?)([\w-]+)/g, '$1<span class="md-kw">$2</span>')
        .replace(/([\w-]+)(=)/g, '<span class="md-fn">$1</span>$2')
        .replace(/("(?:[^"\\]|\\.)*")/g, '<span class="md-str">$1</span>')
        .replace(/(&lt;!--[\s\S]*?--&gt;)/g, '<span class="md-cm">$1</span>');
    } else if (lang === "css") {
      return code
        .replace(/([\w-]+)\s*:/g, '<span class="md-fn">$1</span>:')
        .replace(/("(?:[^"\\]|\\.)*"|'(?:[^'\\]|\\.)*')/g, '<span class="md-str">$1</span>')
        .replace(/(\d+\.?\d*(px|em|rem|%|vh|vw|s|ms)?)\b/g, '<span class="md-num">$1</span>')
        .replace(/(\/\*[\s\S]*?\*\/)/g, '<span class="md-cm">$1</span>');
    } else {
      // Unknown language, return as-is
      return code;
    }

    // Generic highlighter for C-family and similar languages
    var result = "";
    var lines = code.split("\n");

    for (var li = 0; li < lines.length; li++) {
      if (li > 0) result += "\n";
      var ln = lines[li];
      var out = "";
      var j = 0;

      while (j < ln.length) {
        // Single-line comment
        if (hashComment && ln[j] === singleComment[0] && j + singleComment.length <= ln.length && ln.substr(j, singleComment.length) === singleComment) {
          out += '<span class="md-cm">' + ln.substring(j) + '</span>';
          j = ln.length;
          continue;
        }
        if (!hashComment && ln.substr(j, singleComment.length) === singleComment) {
          out += '<span class="md-cm">' + ln.substring(j) + '</span>';
          j = ln.length;
          continue;
        }

        // Strings
        if (ln[j] === '"' || ln[j] === "'") {
          var q = ln[j];
          var end = j + 1;
          while (end < ln.length && (ln[end] !== q || ln[end - 1] === "\\")) end++;
          end++;
          out += '<span class="md-str">' + ln.substring(j, end) + '</span>';
          j = end;
          continue;
        }

        // Template literals
        if (ln[j] === '`') {
          var endTick = j + 1;
          while (endTick < ln.length && ln[endTick] !== '`') endTick++;
          endTick++;
          out += '<span class="md-str">' + ln.substring(j, endTick) + '</span>';
          j = endTick;
          continue;
        }

        // Numbers
        if (/\d/.test(ln[j]) && (j === 0 || /[\s(,=+\-*/<>[\]{};:!&|^~%]/.test(ln[j - 1]))) {
          var numEnd = j;
          while (numEnd < ln.length && /[\d.xXa-fA-FeEoObB_]/.test(ln[numEnd])) numEnd++;
          out += '<span class="md-num">' + ln.substring(j, numEnd) + '</span>';
          j = numEnd;
          continue;
        }

        // Word (potential keyword)
        if (/[a-zA-Z_$]/.test(ln[j])) {
          var wordEnd = j;
          while (wordEnd < ln.length && /[a-zA-Z0-9_$]/.test(ln[wordEnd])) wordEnd++;
          var word = ln.substring(j, wordEnd);
          if (keywords.indexOf(word) !== -1) {
            out += '<span class="md-kw">' + word + '</span>';
          } else {
            // Check if it's a function call
            var afterWord = ln.substring(wordEnd).match(/^\s*\(/);
            if (afterWord) {
              out += '<span class="md-fn">' + word + '</span>';
            } else {
              out += word;
            }
          }
          j = wordEnd;
          continue;
        }

        out += ln[j];
        j++;
      }

      result += out;
    }

    return result;
  }

  // ========== TOOLBAR ACTIONS ==========

  window.mdInsert = function(before, after) {
    var start = elEditor.selectionStart;
    var end = elEditor.selectionEnd;
    var text = elEditor.value;
    var selected = text.substring(start, end);
    var replacement = before + (selected || "text") + after;
    elEditor.value = text.substring(0, start) + replacement + text.substring(end);
    elEditor.selectionStart = start + before.length;
    elEditor.selectionEnd = start + before.length + (selected || "text").length;
    elEditor.focus();
    triggerUpdate();
  };

  window.mdPrefix = function(prefix) {
    var start = elEditor.selectionStart;
    var text = elEditor.value;
    // Find start of current line
    var lineStart = text.lastIndexOf("\n", start - 1) + 1;
    elEditor.value = text.substring(0, lineStart) + prefix + text.substring(lineStart);
    elEditor.selectionStart = elEditor.selectionEnd = start + prefix.length;
    elEditor.focus();
    triggerUpdate();
  };

  window.mdLink = function() {
    var start = elEditor.selectionStart;
    var end = elEditor.selectionEnd;
    var text = elEditor.value;
    var selected = text.substring(start, end) || "link text";
    var insert = "[" + selected + "](url)";
    elEditor.value = text.substring(0, start) + insert + text.substring(end);
    // Select "url" for easy replacement
    elEditor.selectionStart = start + selected.length + 3;
    elEditor.selectionEnd = start + selected.length + 6;
    elEditor.focus();
    triggerUpdate();
  };

  window.mdImage = function() {
    var start = elEditor.selectionStart;
    var end = elEditor.selectionEnd;
    var text = elEditor.value;
    var selected = text.substring(start, end) || "alt text";
    var insert = "![" + selected + "](image-url)";
    elEditor.value = text.substring(0, start) + insert + text.substring(end);
    elEditor.selectionStart = start + selected.length + 4;
    elEditor.selectionEnd = start + selected.length + 13;
    elEditor.focus();
    triggerUpdate();
  };

  window.mdCodeBlock = function() {
    var start = elEditor.selectionStart;
    var text = elEditor.value;
    var insert = "\n```language\ncode here\n```\n";
    elEditor.value = text.substring(0, start) + insert + text.substring(start);
    elEditor.selectionStart = start + 4;
    elEditor.selectionEnd = start + 12;
    elEditor.focus();
    triggerUpdate();
  };

  window.mdTable = function() {
    var start = elEditor.selectionStart;
    var text = elEditor.value;
    var insert = "\n| Header 1 | Header 2 | Header 3 |\n| -------- | -------- | -------- |\n| Cell 1   | Cell 2   | Cell 3   |\n| Cell 4   | Cell 5   | Cell 6   |\n";
    elEditor.value = text.substring(0, start) + insert + text.substring(start);
    elEditor.focus();
    triggerUpdate();
  };

  window.mdHR = function() {
    var start = elEditor.selectionStart;
    var text = elEditor.value;
    var insert = "\n---\n";
    elEditor.value = text.substring(0, start) + insert + text.substring(start);
    elEditor.focus();
    triggerUpdate();
  };

  // ========== VIEW TOGGLE ==========

  window.mdSetView = function(mode) {
    currentView = mode;
    var btns = ["mdViewEditor", "mdViewSplit", "mdViewPreview"];
    btns.forEach(function(id) {
      document.getElementById(id).classList.remove("active");
    });

    if (mode === "editor") {
      document.getElementById("mdViewEditor").classList.add("active");
      elEditorPane.classList.remove("hidden-pane");
      elPreviewPane.classList.add("hidden-pane");
      elDivider.style.display = "none";
    } else if (mode === "preview") {
      document.getElementById("mdViewPreview").classList.add("active");
      elEditorPane.classList.add("hidden-pane");
      elPreviewPane.classList.remove("hidden-pane");
      elDivider.style.display = "none";
    } else {
      document.getElementById("mdViewSplit").classList.add("active");
      elEditorPane.classList.remove("hidden-pane");
      elPreviewPane.classList.remove("hidden-pane");
      elDivider.style.display = "";
    }
  };

  window.mdToggleTheme = function() {
    lightPreview = !lightPreview;
    var btn = document.getElementById("mdThemeBtn");
    if (lightPreview) {
      elPreview.classList.add("light-preview");
      btn.textContent = "DK";
      btn.classList.add("active");
    } else {
      elPreview.classList.remove("light-preview");
      btn.textContent = "LT";
      btn.classList.remove("active");
    }
  };

  // ========== EXPORT ==========

  window.mdCopyHtml = function() {
    var html = elPreview.innerHTML;
    navigator.clipboard.writeText(html).then(function() {
      var btn = event.target;
      var orig = btn.textContent;
      btn.textContent = "Copied";
      setTimeout(function() { btn.textContent = orig; }, 2000);
    });
  };

  window.mdDownloadHtml = function() {
    var html = '<!DOCTYPE html>\n<html lang="en">\n<head>\n<meta charset="UTF-8">\n<meta name="viewport" content="width=device-width, initial-scale=1.0">\n<title>Markdown Export</title>\n<style>\nbody { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; max-width: 800px; margin: 40px auto; padding: 0 20px; line-height: 1.6; color: #333; }\npre { background: #f6f8fa; padding: 16px; border-radius: 6px; overflow-x: auto; }\ncode { font-family: "SF Mono", "Fira Mono", monospace; font-size: 0.9em; }\ntable { border-collapse: collapse; width: 100%; }\nth, td { border: 1px solid #ddd; padding: 8px 12px; text-align: left; }\nth { background: #f6f8fa; }\nblockquote { border-left: 3px solid #6C5CE7; margin: 12px 0; padding: 8px 16px; color: #666; }\nhr { border: none; height: 1px; background: #ddd; margin: 24px 0; }\nimg { max-width: 100%; }\n</style>\n</head>\n<body>\n' + elPreview.innerHTML + '\n</body>\n</html>';
    downloadFile(html, "markdown-export-" + Date.now() + ".html", "text/html");
  };

  window.mdDownloadMd = function() {
    downloadFile(elEditor.value, "document-" + Date.now() + ".md", "text/markdown");
  };

  function downloadFile(content, filename, type) {
    var blob = new Blob([content], { type: type });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = filename;
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  }

  // ========== AUTO-SAVE ==========

  var STORAGE_KEY = "zovo_md_editor_content";

  function autoSave() {
    try {
      localStorage.setItem(STORAGE_KEY, elEditor.value);
      elAutosave.textContent = "Saved";
      elAutosave.classList.add("saved");
      setTimeout(function() {
        elAutosave.textContent = "Auto-save: on";
        elAutosave.classList.remove("saved");
      }, 1500);
    } catch (e) {
      elAutosave.textContent = "Auto-save: error";
    }
  }

  function loadSaved() {
    try {
      var saved = localStorage.getItem(STORAGE_KEY);
      if (saved && saved.trim()) {
        elEditor.value = saved;
        return true;
      }
    } catch (e) {}
    return false;
  }

  // ========== STATS ==========

  function updateStats() {
    var text = elEditor.value.trim();
    var words = text ? text.split(/\s+/).length : 0;
    var chars = elEditor.value.length;
    elStats.textContent = words.toLocaleString() + " word" + (words !== 1 ? "s" : "") + ", " + chars.toLocaleString() + " char" + (chars !== 1 ? "s" : "");
  }

  // ========== UPDATE LOOP ==========

  function triggerUpdate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(function() {
      renderPreview();
      updateStats();
      // Schedule auto-save
      clearTimeout(saveTimer);
      saveTimer = setTimeout(autoSave, 2000);
    }, 60);
  }

  function renderPreview() {
    var src = elEditor.value;
    elPreview.innerHTML = parseMd(src);
  }

  // ========== KEYBOARD SHORTCUTS ==========

  elEditor.addEventListener("keydown", function(e) {
    // Ctrl+B: Bold
    if ((e.ctrlKey || e.metaKey) && e.key === "b") {
      e.preventDefault();
      mdInsert("**", "**");
    }
    // Ctrl+I: Italic
    if ((e.ctrlKey || e.metaKey) && e.key === "i") {
      e.preventDefault();
      mdInsert("*", "*");
    }
    // Ctrl+K: Link
    if ((e.ctrlKey || e.metaKey) && e.key === "k") {
      e.preventDefault();
      mdLink();
    }
    // Tab: insert 2 spaces
    if (e.key === "Tab") {
      e.preventDefault();
      var start = this.selectionStart;
      var end = this.selectionEnd;
      this.value = this.value.substring(0, start) + "  " + this.value.substring(end);
      this.selectionStart = this.selectionEnd = start + 2;
      triggerUpdate();
    }
  });

  // ========== DIVIDER DRAG ==========

  var isDragging = false;

  elDivider.addEventListener("mousedown", function(e) {
    isDragging = true;
    e.preventDefault();
  });

  document.addEventListener("mousemove", function(e) {
    if (!isDragging) return;
    var container = document.getElementById("mdContainer");
    var rect = container.getBoundingClientRect();
    var pct = ((e.clientX - rect.left) / rect.width) * 100;
    pct = Math.max(20, Math.min(80, pct));
    elEditorPane.style.flex = "0 0 " + pct + "%";
    elPreviewPane.style.flex = "1";
  });

  document.addEventListener("mouseup", function() {
    isDragging = false;
  });

  // ========== INIT ==========

  elEditor.addEventListener("input", triggerUpdate);

  // Load saved content or set default
  var hadSaved = loadSaved();
  if (!hadSaved) {
    elEditor.value = "# Welcome to the Markdown Editor\n\nStart typing here to see your Markdown rendered in real time.\n\n## Features\n\n- **Bold**, *italic*, and ~~strikethrough~~ text\n- [Links](https://zovo.one) and images\n- Code blocks with syntax highlighting\n- GFM tables and task lists\n\n### Task List\n\n- [x] Write some Markdown\n- [x] See the live preview\n- [ ] Export as HTML\n\n### Code Example\n\n```javascript\nfunction greet(name) {\n  return `Hello, ${name}`;\n}\n\nconsole.log(greet(\"World\"));\n```\n\n### Table\n\n| Feature | Status | Notes |\n| ------- | :----: | ----: |\n| Headings | Done | H1-H6 |\n| Lists | Done | UL, OL, Tasks |\n| Tables | Done | GFM pipes |\n| Code | Done | Fenced + inline |\n\n> Blockquotes work too. This is a quoted paragraph.\n\n---\n\nThat horizontal rule above separates sections.";
  }

  elAutosave.textContent = "Auto-save: on";
  renderPreview();
  updateStats();

})();
</script>
