---
layout: page
title: "Free Word Counter — Character Count, Reading Time & Keyword Density | Zovo"
description: "Count words, characters, sentences, paragraphs, and pages. Get reading time, speaking time, keyword density, and readability scores. Free online word counter for writers and students."
permalink: /tools/word-counter/
keywords: "word counter, character counter, word count, character count, reading time calculator, keyword density checker, readability score, text analyzer"
date: 2026-03-19
categories: [tools]
tags: [word-counter, character-counter, text-analysis, writing, readability, seo]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --wc-primary: #6C5CE7;
    --wc-primary-dark: #5A4BD1;
    --wc-primary-light: #A29BFE;
    --wc-bg: #0a0a0f;
    --wc-surface: #12121a;
    --wc-surface-alt: #181824;
    --wc-border: #1e1e2e;
    --wc-text: #e0e0e0;
    --wc-text-muted: #8888aa;
    --wc-green: #00ff88;
    --wc-green-dark: #00cc6a;
    --wc-red: #ff4466;
    --wc-yellow: #ffaa00;
    --wc-radius: 12px;
    --wc-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .wc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--wc-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .wc-wrapper * {
    box-sizing: border-box;
  }

  .wc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .wc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--wc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .wc-hero h1 span {
    color: var(--wc-primary);
  }

  .wc-intro {
    font-size: 1.05rem;
    color: var(--wc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .wc-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--wc-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--wc-border);
    border-radius: 20px;
  }

  /* Stats Bar */
  .wc-stats-bar {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 8px;
    margin-bottom: 16px;
  }

  .wc-stat {
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: 8px;
    padding: 10px 12px;
    text-align: center;
  }

  .wc-stat-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.3rem;
    font-weight: 600;
    color: var(--wc-green);
    display: block;
  }

  .wc-stat-label {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--wc-text-muted);
    margin-top: 2px;
    display: block;
  }

  /* Limit Bar */
  .wc-limit-section {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
    padding: 10px 14px;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: 8px;
  }

  .wc-limit-section label {
    font-size: 0.82rem;
    font-weight: 500;
    color: var(--wc-text-muted);
    white-space: nowrap;
  }

  .wc-limit-select {
    padding: 5px 8px;
    background: var(--wc-bg);
    border: 1px solid var(--wc-border);
    border-radius: 6px;
    color: var(--wc-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.82rem;
    outline: none;
    cursor: pointer;
  }

  .wc-limit-input {
    width: 80px;
    padding: 5px 8px;
    background: var(--wc-bg);
    border: 1px solid var(--wc-border);
    border-radius: 6px;
    color: var(--wc-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    outline: none;
    -moz-appearance: textfield;
  }

  .wc-limit-input::-webkit-outer-spin-button,
  .wc-limit-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
  }

  .wc-limit-input:focus,
  .wc-limit-select:focus {
    border-color: var(--wc-primary);
  }

  .wc-limit-progress {
    flex: 1;
    height: 6px;
    background: var(--wc-bg);
    border-radius: 3px;
    overflow: hidden;
  }

  .wc-limit-fill {
    height: 100%;
    background: var(--wc-primary);
    border-radius: 3px;
    transition: width 0.2s ease, background-color 0.2s ease;
  }

  .wc-limit-fill.warning {
    background: var(--wc-yellow);
  }

  .wc-limit-fill.exceeded {
    background: var(--wc-red);
  }

  .wc-limit-remaining {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    color: var(--wc-text-muted);
    white-space: nowrap;
    min-width: 60px;
    text-align: right;
  }

  .wc-limit-remaining.exceeded {
    color: var(--wc-red);
  }

  /* Toolbar */
  .wc-toolbar {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 12px;
  }

  .wc-btn {
    padding: 6px 12px;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: 6px;
    color: var(--wc-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
    font-weight: 500;
    cursor: pointer;
    transition: border-color 0.2s ease, color 0.2s ease, background 0.2s ease;
    white-space: nowrap;
  }

  .wc-btn:hover {
    border-color: var(--wc-primary);
    color: var(--wc-text);
  }

  .wc-btn.active {
    background: var(--wc-primary);
    border-color: var(--wc-primary);
    color: white;
  }

  .wc-toolbar-sep {
    width: 1px;
    background: var(--wc-border);
    margin: 0 4px;
    align-self: stretch;
  }

  /* Find/Replace */
  .wc-find-replace {
    display: none;
    gap: 8px;
    align-items: center;
    padding: 10px 14px;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: 8px;
    margin-bottom: 12px;
    flex-wrap: wrap;
  }

  .wc-find-replace.visible {
    display: flex;
  }

  .wc-find-input {
    flex: 1;
    min-width: 120px;
    padding: 6px 10px;
    background: var(--wc-bg);
    border: 1px solid var(--wc-border);
    border-radius: 6px;
    color: var(--wc-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    outline: none;
  }

  .wc-find-input:focus {
    border-color: var(--wc-primary);
  }

  .wc-find-count {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    color: var(--wc-text-muted);
    white-space: nowrap;
  }

  /* Textarea */
  .wc-textarea-wrap {
    position: relative;
    margin-bottom: 16px;
  }

  .wc-textarea {
    width: 100%;
    min-height: 280px;
    padding: 16px;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: var(--wc-radius);
    color: var(--wc-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    line-height: 1.8;
    resize: vertical;
    outline: none;
    transition: border-color 0.2s ease;
    overflow-y: auto;
  }

  .wc-textarea:focus {
    border-color: var(--wc-primary);
  }

  .wc-textarea::placeholder {
    color: var(--wc-text-muted);
    opacity: 0.6;
  }

  /* Time Estimates */
  .wc-time-row {
    display: flex;
    gap: 16px;
    margin-bottom: 16px;
  }

  .wc-time-card {
    flex: 1;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: 8px;
    padding: 12px 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .wc-time-icon {
    font-size: 1.2rem;
    opacity: 0.6;
  }

  .wc-time-info {
    flex: 1;
  }

  .wc-time-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1rem;
    font-weight: 600;
    color: var(--wc-primary-light);
  }

  .wc-time-label {
    font-size: 0.75rem;
    color: var(--wc-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  /* Panels */
  .wc-panels {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 32px;
  }

  .wc-panel {
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: var(--wc-radius);
    padding: 16px;
  }

  .wc-panel-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--wc-text-muted);
    margin: 0 0 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .wc-panel-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--wc-primary);
    border-radius: 2px;
  }

  /* Keywords */
  .wc-keyword-tabs {
    display: flex;
    gap: 4px;
    margin-bottom: 10px;
  }

  .wc-kw-tab {
    padding: 4px 10px;
    background: transparent;
    border: 1px solid var(--wc-border);
    border-radius: 4px;
    color: var(--wc-text-muted);
    font-size: 0.75rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .wc-kw-tab.active {
    background: var(--wc-primary);
    border-color: var(--wc-primary);
    color: white;
  }

  .wc-keyword-list {
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .wc-keyword-item {
    display: flex;
    align-items: center;
    padding: 5px 0;
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
    font-size: 0.85rem;
  }

  .wc-keyword-item:last-child {
    border-bottom: none;
  }

  .wc-kw-rank {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    color: var(--wc-text-muted);
    width: 22px;
    text-align: center;
    flex-shrink: 0;
  }

  .wc-kw-word {
    flex: 1;
    color: var(--wc-text);
    font-weight: 500;
    padding: 0 8px;
  }

  .wc-kw-count {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    color: var(--wc-primary-light);
    width: 28px;
    text-align: right;
    flex-shrink: 0;
  }

  .wc-kw-density {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--wc-text-muted);
    width: 50px;
    text-align: right;
    flex-shrink: 0;
  }

  .wc-kw-empty {
    font-size: 0.85rem;
    color: var(--wc-text-muted);
    padding: 12px 0;
    text-align: center;
  }

  /* Readability */
  .wc-readability-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px 0;
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
  }

  .wc-readability-item:last-child {
    border-bottom: none;
  }

  .wc-read-label {
    font-size: 0.85rem;
    color: var(--wc-text-muted);
  }

  .wc-read-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--wc-green);
  }

  .wc-read-badge {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 0.7rem;
    font-weight: 600;
    margin-left: 6px;
  }

  .wc-read-badge.very-easy { background: rgba(0, 255, 136, 0.15); color: var(--wc-green); }
  .wc-read-badge.easy { background: rgba(0, 255, 136, 0.1); color: #66ffbb; }
  .wc-read-badge.standard { background: rgba(108, 92, 231, 0.15); color: var(--wc-primary-light); }
  .wc-read-badge.difficult { background: rgba(255, 170, 0, 0.15); color: var(--wc-yellow); }
  .wc-read-badge.very-difficult { background: rgba(255, 68, 102, 0.12); color: var(--wc-red); }

  /* Cross Links */
  .wc-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .wc-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: 8px;
    color: var(--wc-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .wc-cross-link:hover {
    border-color: var(--wc-primary);
    color: var(--wc-text);
  }

  /* Content */
  .wc-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .wc-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 2.5rem 0 1rem;
    color: var(--wc-text);
  }

  .wc-content p {
    font-size: 0.95rem;
    color: var(--wc-text-muted);
    line-height: 1.8;
    margin: 0 0 1rem;
  }

  .wc-content ul, .wc-content ol {
    color: var(--wc-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 1.5rem;
    margin: 0 0 1rem;
  }

  .wc-content li {
    margin-bottom: 0.4rem;
  }

  .wc-content table {
    width: 100%;
    border-collapse: collapse;
    margin: 1rem 0;
    font-size: 0.9rem;
  }

  .wc-content th, .wc-content td {
    padding: 8px 12px;
    border: 1px solid var(--wc-border);
    text-align: left;
  }

  .wc-content th {
    background: var(--wc-surface);
    color: var(--wc-text);
    font-weight: 600;
  }

  .wc-content td {
    color: var(--wc-text-muted);
  }

  /* Author Box */
  .wc-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--wc-surface);
    border: 1px solid var(--wc-border);
    border-radius: var(--wc-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .wc-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--wc-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .wc-author-info {
    flex: 1;
  }

  .wc-author-name {
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--wc-text);
    margin: 0 0 4px;
  }

  .wc-author-bio {
    font-size: 0.82rem;
    color: var(--wc-text-muted);
    line-height: 1.6;
    margin: 0;
  }

  /* FAQ */
  .wc-faq {
    max-width: 780px;
    margin: 2.5rem auto 0;
  }

  .wc-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 1.2rem;
    color: var(--wc-text);
  }

  .wc-faq-item {
    padding: 16px 0;
    border-bottom: 1px solid var(--wc-border);
  }

  .wc-faq-item:last-child {
    border-bottom: none;
  }

  .wc-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--wc-text);
  }

  .wc-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--wc-text-muted);
    line-height: 1.7;
  }

  /* Footer */
  .wc-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--wc-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--wc-border);
    margin-top: 3rem;
  }

  .wc-footer a {
    color: var(--wc-primary);
    text-decoration: none;
  }

  .wc-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .wc-hero h1 {
      font-size: 1.6rem;
    }

    .wc-stats-bar {
      grid-template-columns: repeat(3, 1fr);
    }

    .wc-time-row {
      flex-direction: column;
      gap: 8px;
    }

    .wc-panels {
      grid-template-columns: 1fr;
    }

    .wc-toolbar {
      gap: 4px;
    }

    .wc-btn {
      padding: 5px 8px;
      font-size: 0.72rem;
    }

    .wc-limit-section {
      flex-wrap: wrap;
    }

    .wc-find-replace {
      flex-direction: column;
      align-items: stretch;
    }

    .wc-author-box {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
  }

  @media (max-width: 480px) {
    .wc-stats-bar {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>

<div class="wc-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Word Counter">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="wc-hero">
    <h1><span>Word</span> Counter</h1>
    <p class="wc-intro">Count words, characters, sentences, and paragraphs in real time. Get reading and speaking time estimates, keyword density analysis, and readability scores. Everything runs locally in your browser.</p>
    <div class="wc-updated">Last updated: March 19, 2026</div>
  </div>

  <!-- Stats Bar -->
  <div class="wc-stats-bar">
    <div class="wc-stat">
      <span class="wc-stat-value" id="wcWords">0</span>
      <span class="wc-stat-label">Words</span>
    </div>
    <div class="wc-stat">
      <span class="wc-stat-value" id="wcChars">0</span>
      <span class="wc-stat-label">Characters</span>
    </div>
    <div class="wc-stat">
      <span class="wc-stat-value" id="wcCharsNoSpace">0</span>
      <span class="wc-stat-label">No Spaces</span>
    </div>
    <div class="wc-stat">
      <span class="wc-stat-value" id="wcSentences">0</span>
      <span class="wc-stat-label">Sentences</span>
    </div>
    <div class="wc-stat">
      <span class="wc-stat-value" id="wcParagraphs">0</span>
      <span class="wc-stat-label">Paragraphs</span>
    </div>
    <div class="wc-stat">
      <span class="wc-stat-value" id="wcPages">0</span>
      <span class="wc-stat-label">Pages</span>
    </div>
  </div>

  <!-- Limit Bar -->
  <div class="wc-limit-section">
    <label>Limit:</label>
    <select id="wcLimitType" class="wc-limit-select">
      <option value="none">None</option>
      <option value="words">Words</option>
      <option value="chars">Characters</option>
    </select>
    <input type="number" id="wcLimitValue" class="wc-limit-input" value="500" min="1" style="display:none;">
    <div class="wc-limit-progress" id="wcLimitBar" style="display:none;">
      <div class="wc-limit-fill" id="wcLimitFill" style="width:0%"></div>
    </div>
    <span class="wc-limit-remaining" id="wcLimitRemaining" style="display:none;">500 left</span>
  </div>

  <!-- Toolbar -->
  <div class="wc-toolbar">
    <button type="button" class="wc-btn" onclick="wcClear()">Clear</button>
    <button type="button" class="wc-btn" onclick="wcCopy()" id="wcCopyBtn">Copy</button>
    <button type="button" class="wc-btn" onclick="wcDownload()">Download .txt</button>
    <div class="wc-toolbar-sep"></div>
    <button type="button" class="wc-btn" onclick="wcToggleFindReplace()" id="wcFindBtn">Find & Replace</button>
    <div class="wc-toolbar-sep"></div>
    <button type="button" class="wc-btn" onclick="wcCase('upper')">UPPER</button>
    <button type="button" class="wc-btn" onclick="wcCase('lower')">lower</button>
    <button type="button" class="wc-btn" onclick="wcCase('title')">Title</button>
    <button type="button" class="wc-btn" onclick="wcCase('sentence')">Sentence</button>
  </div>

  <!-- Find & Replace -->
  <div class="wc-find-replace" id="wcFindReplace">
    <input type="text" class="wc-find-input" id="wcFindInput" placeholder="Find...">
    <input type="text" class="wc-find-input" id="wcReplaceInput" placeholder="Replace with...">
    <span class="wc-find-count" id="wcFindCount">0 matches</span>
    <button type="button" class="wc-btn" onclick="wcReplaceAll()">Replace All</button>
    <button type="button" class="wc-btn" onclick="wcToggleFindReplace()">Close</button>
  </div>

  <!-- Textarea -->
  <div class="wc-textarea-wrap">
    <textarea id="wcText" class="wc-textarea" placeholder="Start typing or paste your text here..."></textarea>
  </div>

  <!-- Time Estimates -->
  <div class="wc-time-row">
    <div class="wc-time-card">
      <div class="wc-time-info">
        <div class="wc-time-value" id="wcReadTime">0 sec</div>
        <div class="wc-time-label">Reading Time (238 wpm)</div>
      </div>
    </div>
    <div class="wc-time-card">
      <div class="wc-time-info">
        <div class="wc-time-value" id="wcSpeakTime">0 sec</div>
        <div class="wc-time-label">Speaking Time (150 wpm)</div>
      </div>
    </div>
  </div>

  <!-- Keyword Density & Readability Panels -->
  <div class="wc-panels">
    <div class="wc-panel">
      <div class="wc-panel-title">Top Keywords</div>
      <div class="wc-keyword-tabs">
        <button type="button" class="wc-kw-tab active" onclick="wcSetNgram(1, this)">1-word</button>
        <button type="button" class="wc-kw-tab" onclick="wcSetNgram(2, this)">2-word</button>
        <button type="button" class="wc-kw-tab" onclick="wcSetNgram(3, this)">3-word</button>
      </div>
      <ul class="wc-keyword-list" id="wcKeywords">
        <li class="wc-kw-empty">Type something to see keywords</li>
      </ul>
    </div>

    <div class="wc-panel">
      <div class="wc-panel-title">Readability</div>
      <div id="wcReadability">
        <div class="wc-readability-item">
          <span class="wc-read-label">Flesch Reading Ease</span>
          <span class="wc-read-value" id="wcFlesch">---</span>
        </div>
        <div class="wc-readability-item">
          <span class="wc-read-label">Flesch-Kincaid Grade</span>
          <span class="wc-read-value" id="wcFK">---</span>
        </div>
        <div class="wc-readability-item">
          <span class="wc-read-label">Avg Words/Sentence</span>
          <span class="wc-read-value" id="wcAvgWPS">---</span>
        </div>
        <div class="wc-readability-item">
          <span class="wc-read-label">Avg Syllables/Word</span>
          <span class="wc-read-value" id="wcAvgSPW">---</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Cross Links -->
  <div class="wc-cross-links">
    <a href="/tools/ai-detector/" class="wc-cross-link">AI Detector</a>
    <a href="/tools/citation-generator/" class="wc-cross-link">Citation Generator</a>
    <a href="/tools/lorem-ipsum-generator/" class="wc-cross-link">Lorem Ipsum Generator</a>
  </div>

  <!-- SEO Content -->
  <div class="wc-content">

<h2>What Is a Word Counter</h2>

<p>A word counter is a tool that takes a block of text and returns a set of statistics about it: word count, character count, sentence count, paragraph count, and often additional metrics like reading time and readability. Writers, students, editors, and marketers all rely on word counters for different reasons, but the underlying function is the same: measure the text.</p>

<p>This tool goes beyond basic counting. It analyzes keyword density so you can see which terms appear most frequently, calculates two standard readability formulas (Flesch Reading Ease and Flesch-Kincaid Grade Level), estimates reading and speaking time, and supports character or word limits with visual progress tracking. Everything updates as you type.</p>

<p>All processing happens in your browser. No text is transmitted to any server, no accounts are required, and nothing is logged. The tool works equally well on a phone, tablet, or desktop.</p>

<h2>Why Word Count Matters</h2>

<p>Word count requirements exist across nearly every form of writing. College essays have target lengths set by professors. Journal articles must fit within publisher limits. Blog posts perform best within certain ranges for search engines. Ad copy platforms impose character limits. Social media bios cap at specific numbers. Understanding how long your text is lets you plan, edit, and comply with requirements.</p>

<p>Beyond compliance, word count serves as a rough proxy for reading time. A 1,000-word article takes about 4 minutes to read at the average adult reading speed of 238 words per minute. A 3,000-word guide takes about 13 minutes. Knowing these numbers helps you set reader expectations and match content length to audience attention spans.</p>

<p>Character count matters in different contexts. Tweet length, meta descriptions for SEO (recommended 150-160 characters), SMS messages (160 characters), and push notifications all have character-based limits. The stats bar above shows both character count (with spaces) and character count (without spaces) because different platforms define "character" differently.</p>

<h2>Understanding Readability Scores</h2>

<p>Readability formulas estimate how difficult a text is to read based on measurable properties: sentence length and word complexity (approximated by syllable count). They do not evaluate content quality, accuracy, or style. Two texts with identical readability scores can differ enormously in how engaging or useful they are.</p>

<p>The Flesch Reading Ease score ranges from 0 to 100. Higher scores mean easier text. A score of 60-70 corresponds to standard reading level, suitable for most audiences. Scores above 70 are considered easy to read. Below 30 indicates very difficult academic or legal writing. Most popular web content scores between 60 and 80.</p>

<p>The Flesch-Kincaid Grade Level translates the same inputs into a US school grade level. A score of 8 means an average eighth grader should be able to understand the text. Most general-audience writing targets grade 7-9. Technical documentation often lands at grade 12 or higher. Lower is not always better; it depends on your audience.</p>

<p>Both formulas use the same two variables: average sentence length (words per sentence) and average syllable count per word. To improve readability scores, shorten sentences and choose simpler words where possible. Replacing "utilize" with "use" or "approximately" with "about" nudges the score upward without changing meaning.</p>

<h2>Keyword Density for SEO</h2>

<p>Keyword density is the percentage of times a specific word or phrase appears relative to the total word count. If a 500-word article contains the phrase "project management" 5 times, the density for that phrase is 1%.</p>

<p>In the early days of search engine optimization, stuffing a page with keywords was a viable strategy. Modern search engines penalize this. There is no universally agreed "ideal" keyword density, but most SEO practitioners target 1-2% for primary keywords and use related terms naturally throughout the text. The keyword density panel on this page helps you check whether you are overusing or underusing specific terms.</p>

<p>The n-gram toggle (1-word, 2-word, 3-word phrases) lets you analyze at different levels. Single-word analysis shows which individual terms dominate. Two-word and three-word phrase analysis reveals recurring multi-word expressions, which are often more relevant to SEO because search queries frequently contain multiple words.</p>

<p>Stop words (the, is, and, of, to, etc.) are excluded from the keyword analysis because they appear in every text and carry no topical signal. The tool filters them automatically so you see only content-bearing words.</p>

<h2>Writing Length Guidelines by Format</h2>

<table>
  <thead>
    <tr>
      <th>Format</th>
      <th>Typical Length</th>
      <th>Approx. Reading Time</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Tweet / X post</td>
      <td>280 characters</td>
      <td>2-3 seconds</td>
    </tr>
    <tr>
      <td>Meta description</td>
      <td>150-160 characters</td>
      <td>3-4 seconds</td>
    </tr>
    <tr>
      <td>Email subject line</td>
      <td>40-60 characters</td>
      <td>1-2 seconds</td>
    </tr>
    <tr>
      <td>Short blog post</td>
      <td>600-800 words</td>
      <td>2-3 minutes</td>
    </tr>
    <tr>
      <td>Standard blog post</td>
      <td>1,200-1,800 words</td>
      <td>5-8 minutes</td>
    </tr>
    <tr>
      <td>Long-form article</td>
      <td>2,500-4,000 words</td>
      <td>10-17 minutes</td>
    </tr>
    <tr>
      <td>College essay</td>
      <td>500-2,500 words</td>
      <td>2-10 minutes</td>
    </tr>
    <tr>
      <td>White paper</td>
      <td>3,000-6,000 words</td>
      <td>12-25 minutes</td>
    </tr>
    <tr>
      <td>Novel chapter</td>
      <td>3,000-5,000 words</td>
      <td>12-21 minutes</td>
    </tr>
  </tbody>
</table>

<p>These are guidelines, not rules. The right length for any piece of writing is the length it needs to cover the topic thoroughly without padding or leaving gaps. Use the page estimate (250 words per page, standard double-spaced format) when you need to convert between word counts and physical pages.</p>

  </div>

  <!-- FAQ Section -->
  <div class="wc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="wc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does this tool count words?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool splits the text on whitespace boundaries (spaces, tabs, line breaks) and counts the resulting segments, filtering out empty strings. Hyphenated words like "well-known" count as a single word. Numbers and abbreviations count as words. This matches the behavior of standard word processors like Microsoft Word and Google Docs.</p>
      </div>
    </div>

    <div class="wc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What reading speed does the reading time estimate use?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Reading time uses 238 words per minute, which is the average silent reading speed for adults reading English text, based on a 2019 meta-analysis by Brysbaert. Speaking time uses 150 words per minute, which reflects a comfortable presentation pace. Actual speeds vary by individual and by text complexity.</p>
      </div>
    </div>

    <div class="wc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How are syllables counted for readability scores?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool uses a heuristic algorithm that counts vowel groups (consecutive vowels count as one syllable), subtracts one for silent trailing "e" endings, and enforces a minimum of one syllable per word. This approach is not 100% accurate for every English word (English spelling is inconsistent), but it produces reliable readability scores that closely match those from established tools.</p>
      </div>
    </div>

    <div class="wc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What stop words are excluded from keyword analysis?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool excludes the most common English function words: articles (the, a, an), prepositions (in, on, at, to, for, with, from, by, of), conjunctions (and, but, or, nor, so, yet), pronouns (I, you, he, she, it, we, they, this, that), and common verbs (is, are, was, were, be, been, have, has, had, do, does, did, will, would, can, could, should, may, might). About 175 words are filtered.</p>
      </div>
    </div>

    <div class="wc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I set a character or word limit?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Use the Limit dropdown above the toolbar to select "Words" or "Characters," then enter your target number. A progress bar appears showing how much of your limit you have used. The bar turns yellow at 90% and red when you exceed the limit. The remaining count updates in real time as you type.</p>
      </div>
    </div>

    <div class="wc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my text stored or sent anywhere?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All processing happens entirely in your web browser using JavaScript. No data is transmitted to any server, no information is stored in cookies or local storage, and no analytics track your input. You can verify this by opening your browser's developer tools and monitoring the Network tab while using the tool. Your text never leaves your device.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="wc-author-box">
    <div class="wc-author-avatar">ML</div>
    <div class="wc-author-info">
      <p class="wc-author-name">Michael Lip</p>
      <p class="wc-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="wc-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Word Counter",
      "description": "Count words, characters, sentences, paragraphs, and pages. Get reading time, speaking time, keyword density, and readability scores.",
      "url": "https://theluckystrike.github.io/tools/word-counter/",
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
        {"@type": "ListItem", "position": 3, "name": "Word Counter", "item": "https://theluckystrike.github.io/tools/word-counter/"}
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
          "name": "How does this tool count words?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The tool splits the text on whitespace boundaries and counts the resulting segments, filtering out empty strings. Hyphenated words count as a single word. Numbers and abbreviations count as words."
          }
        },
        {
          "@type": "Question",
          "name": "What reading speed does the reading time estimate use?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Reading time uses 238 words per minute, the average silent reading speed for adults. Speaking time uses 150 words per minute, reflecting a comfortable presentation pace."
          }
        },
        {
          "@type": "Question",
          "name": "How are syllables counted for readability scores?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The tool counts vowel groups, subtracts one for silent trailing e endings, and enforces a minimum of one syllable per word."
          }
        },
        {
          "@type": "Question",
          "name": "What stop words are excluded from keyword analysis?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "About 175 common English function words are excluded: articles, prepositions, conjunctions, pronouns, and common auxiliary verbs."
          }
        },
        {
          "@type": "Question",
          "name": "Can I set a character or word limit?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Use the Limit dropdown to select Words or Characters, enter your target, and a progress bar tracks usage in real time."
          }
        },
        {
          "@type": "Question",
          "name": "Is my text stored or sent anywhere?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All processing happens entirely in your browser. No data is transmitted to any server or stored anywhere."
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

  // --- DOM refs ---
  var elText = document.getElementById("wcText");
  var elWords = document.getElementById("wcWords");
  var elChars = document.getElementById("wcChars");
  var elCharsNoSpace = document.getElementById("wcCharsNoSpace");
  var elSentences = document.getElementById("wcSentences");
  var elParagraphs = document.getElementById("wcParagraphs");
  var elPages = document.getElementById("wcPages");
  var elReadTime = document.getElementById("wcReadTime");
  var elSpeakTime = document.getElementById("wcSpeakTime");
  var elKeywords = document.getElementById("wcKeywords");
  var elFlesch = document.getElementById("wcFlesch");
  var elFK = document.getElementById("wcFK");
  var elAvgWPS = document.getElementById("wcAvgWPS");
  var elAvgSPW = document.getElementById("wcAvgSPW");
  var elLimitType = document.getElementById("wcLimitType");
  var elLimitValue = document.getElementById("wcLimitValue");
  var elLimitBar = document.getElementById("wcLimitBar");
  var elLimitFill = document.getElementById("wcLimitFill");
  var elLimitRemaining = document.getElementById("wcLimitRemaining");
  var elFindInput = document.getElementById("wcFindInput");
  var elReplaceInput = document.getElementById("wcReplaceInput");
  var elFindCount = document.getElementById("wcFindCount");
  var elFindReplace = document.getElementById("wcFindReplace");

  var currentNgram = 1;
  var debounceTimer = null;

  // --- Stop words ---
  var STOP_WORDS = new Set([
    "a","an","the","and","but","or","nor","so","yet","for","in","on","at","to","from","by",
    "with","of","about","above","after","again","against","all","am","are","as","be","because",
    "been","before","being","below","between","both","can","could","did","do","does","doing",
    "down","during","each","few","get","got","had","has","have","having","he","her","here",
    "hers","herself","him","himself","his","how","i","if","into","is","it","its","itself",
    "just","let","ll","may","me","might","more","most","must","my","myself","no","not","now",
    "of","off","once","only","other","our","ours","ourselves","out","over","own","re","s","same",
    "shall","she","should","some","such","t","than","that","their","theirs","them","themselves",
    "then","there","these","they","this","those","through","too","under","until","up","us","ve",
    "very","was","we","were","what","when","where","which","while","who","whom","why","will",
    "with","would","you","your","yours","yourself","yourselves","also","another","any","anything",
    "anywhere","every","everything","everywhere","many","much","neither","nothing","nowhere",
    "several","something","somewhere","still","well","d","m","re","don","doesn","didn","won",
    "wouldn","shouldn","couldn","isn","aren","wasn","weren","hasn","haven","hadn"
  ]);

  // --- Syllable counting ---
  function countSyllables(word) {
    word = word.toLowerCase().replace(/[^a-z]/g, "");
    if (word.length <= 2) return 1;

    // Remove trailing silent e
    var trimmed = word;
    if (trimmed.endsWith("e") && !trimmed.endsWith("le") && trimmed.length > 2) {
      trimmed = trimmed.slice(0, -1);
    }

    // Count vowel groups
    var matches = trimmed.match(/[aeiouy]+/g);
    var count = matches ? matches.length : 1;

    return Math.max(1, count);
  }

  // --- Text analysis ---
  function getWords(text) {
    var trimmed = text.trim();
    if (!trimmed) return [];
    return trimmed.split(/\s+/).filter(function(w) { return w.length > 0; });
  }

  function getSentences(text) {
    var trimmed = text.trim();
    if (!trimmed) return [];
    // Split on sentence-ending punctuation followed by space or end
    var sents = trimmed.split(/[.!?]+(?:\s|$)/).filter(function(s) { return s.trim().length > 0; });
    return sents;
  }

  function getParagraphs(text) {
    var trimmed = text.trim();
    if (!trimmed) return [];
    return trimmed.split(/\n\s*\n|\r\n\s*\r\n/).filter(function(p) { return p.trim().length > 0; });
  }

  function formatTime(minutes) {
    if (minutes < 1) {
      var secs = Math.round(minutes * 60);
      return secs + " sec";
    }
    var m = Math.floor(minutes);
    var s = Math.round((minutes - m) * 60);
    if (s === 60) { m++; s = 0; }
    if (s === 0) return m + " min";
    return m + " min " + s + " sec";
  }

  // --- Keyword extraction ---
  function extractNgrams(words, n) {
    var cleanWords = words.map(function(w) {
      return w.toLowerCase().replace(/[^a-z0-9'-]/g, "");
    }).filter(function(w) { return w.length > 1; });

    var freq = {};
    var totalPhrases = 0;

    for (var i = 0; i <= cleanWords.length - n; i++) {
      var phrase = [];
      var hasContent = false;
      for (var j = 0; j < n; j++) {
        var w = cleanWords[i + j];
        phrase.push(w);
        if (!STOP_WORDS.has(w)) hasContent = true;
      }
      if (!hasContent) continue;

      // For single words, skip stop words entirely
      if (n === 1 && STOP_WORDS.has(phrase[0])) continue;

      var key = phrase.join(" ");
      freq[key] = (freq[key] || 0) + 1;
      totalPhrases++;
    }

    // Sort by frequency
    var entries = [];
    for (var k in freq) {
      if (freq.hasOwnProperty(k)) {
        entries.push({ phrase: k, count: freq[k], density: (freq[k] / Math.max(1, words.length)) * 100 });
      }
    }

    entries.sort(function(a, b) { return b.count - a.count; });
    return entries.slice(0, 10);
  }

  // --- Readability ---
  function calcReadability(words, sentences) {
    if (words.length < 5 || sentences.length < 1) return null;

    var totalSyllables = 0;
    for (var i = 0; i < words.length; i++) {
      totalSyllables += countSyllables(words[i]);
    }

    var avgWPS = words.length / sentences.length;
    var avgSPW = totalSyllables / words.length;

    var flesch = 206.835 - 1.015 * avgWPS - 84.6 * avgSPW;
    var fk = 0.39 * avgWPS + 11.8 * avgSPW - 15.59;

    return {
      flesch: Math.max(0, Math.min(100, flesch)),
      fk: Math.max(0, fk),
      avgWPS: avgWPS,
      avgSPW: avgSPW
    };
  }

  function fleschLabel(score) {
    if (score >= 80) return { text: "Very Easy", cls: "very-easy" };
    if (score >= 60) return { text: "Easy", cls: "easy" };
    if (score >= 40) return { text: "Standard", cls: "standard" };
    if (score >= 20) return { text: "Difficult", cls: "difficult" };
    return { text: "Very Difficult", cls: "very-difficult" };
  }

  // --- Main update ---
  function update() {
    var text = elText.value;
    var words = getWords(text);
    var sentences = getSentences(text);
    var paragraphs = getParagraphs(text);

    var wordCount = words.length;
    var charCount = text.length;
    var charNoSpace = text.replace(/\s/g, "").length;
    var sentenceCount = sentences.length;
    var paraCount = paragraphs.length;
    var pageCount = (wordCount / 250).toFixed(1);

    // Stats
    elWords.textContent = wordCount.toLocaleString();
    elChars.textContent = charCount.toLocaleString();
    elCharsNoSpace.textContent = charNoSpace.toLocaleString();
    elSentences.textContent = sentenceCount.toLocaleString();
    elParagraphs.textContent = paraCount.toLocaleString();
    elPages.textContent = pageCount;

    // Time
    elReadTime.textContent = formatTime(wordCount / 238);
    elSpeakTime.textContent = formatTime(wordCount / 150);

    // Keywords
    var ngrams = extractNgrams(words, currentNgram);
    if (ngrams.length === 0) {
      elKeywords.innerHTML = '<li class="wc-kw-empty">Type something to see keywords</li>';
    } else {
      var html = "";
      for (var i = 0; i < ngrams.length; i++) {
        var ng = ngrams[i];
        html += '<li class="wc-keyword-item">';
        html += '<span class="wc-kw-rank">' + (i + 1) + '</span>';
        html += '<span class="wc-kw-word">' + escapeHtml(ng.phrase) + '</span>';
        html += '<span class="wc-kw-count">' + ng.count + '</span>';
        html += '<span class="wc-kw-density">' + ng.density.toFixed(1) + '%</span>';
        html += '</li>';
      }
      elKeywords.innerHTML = html;
    }

    // Readability
    var readability = calcReadability(words, sentences);
    if (!readability) {
      elFlesch.innerHTML = "---";
      elFK.textContent = "---";
      elAvgWPS.textContent = "---";
      elAvgSPW.textContent = "---";
    } else {
      var label = fleschLabel(readability.flesch);
      elFlesch.innerHTML = readability.flesch.toFixed(1) + '<span class="wc-read-badge ' + label.cls + '">' + label.text + '</span>';
      elFK.textContent = readability.fk.toFixed(1);
      elAvgWPS.textContent = readability.avgWPS.toFixed(1);
      elAvgSPW.textContent = readability.avgSPW.toFixed(2);
    }

    // Limit
    updateLimit(wordCount, charCount);

    // Find count
    updateFindCount();
  }

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.textContent = str;
    return div.innerHTML;
  }

  // --- Limit ---
  function updateLimit(wordCount, charCount) {
    var type = elLimitType.value;
    if (type === "none") {
      elLimitValue.style.display = "none";
      elLimitBar.style.display = "none";
      elLimitRemaining.style.display = "none";
      return;
    }

    elLimitValue.style.display = "";
    elLimitBar.style.display = "";
    elLimitRemaining.style.display = "";

    var limit = parseInt(elLimitValue.value) || 0;
    var current = type === "words" ? wordCount : charCount;
    var pct = limit > 0 ? (current / limit) * 100 : 0;
    var remaining = limit - current;

    elLimitFill.style.width = Math.min(pct, 100) + "%";
    elLimitFill.className = "wc-limit-fill";
    elLimitRemaining.className = "wc-limit-remaining";

    if (pct > 100) {
      elLimitFill.classList.add("exceeded");
      elLimitRemaining.classList.add("exceeded");
    } else if (pct > 90) {
      elLimitFill.classList.add("warning");
    }

    if (remaining >= 0) {
      elLimitRemaining.textContent = remaining.toLocaleString() + " left";
    } else {
      elLimitRemaining.textContent = Math.abs(remaining).toLocaleString() + " over";
    }
  }

  // --- Find & Replace ---
  function updateFindCount() {
    var query = elFindInput.value;
    if (!query) { elFindCount.textContent = "0 matches"; return; }
    var text = elText.value;
    var count = 0;
    var idx = 0;
    var lowerText = text.toLowerCase();
    var lowerQuery = query.toLowerCase();
    while ((idx = lowerText.indexOf(lowerQuery, idx)) !== -1) {
      count++;
      idx += lowerQuery.length;
    }
    elFindCount.textContent = count + " match" + (count !== 1 ? "es" : "");
  }

  window.wcReplaceAll = function() {
    var query = elFindInput.value;
    var replacement = elReplaceInput.value;
    if (!query) return;

    var text = elText.value;
    // Case-insensitive replace all
    var escaped = query.replace(/[.*+?^${}()|[\]\\]/g, "\\$&");
    var regex = new RegExp(escaped, "gi");
    elText.value = text.replace(regex, replacement);
    update();
  };

  window.wcToggleFindReplace = function() {
    var el = elFindReplace;
    var btn = document.getElementById("wcFindBtn");
    if (el.classList.contains("visible")) {
      el.classList.remove("visible");
      btn.classList.remove("active");
    } else {
      el.classList.add("visible");
      btn.classList.add("active");
      elFindInput.focus();
    }
  };

  // --- Case conversion ---
  window.wcCase = function(mode) {
    var text = elText.value;
    if (!text) return;

    switch (mode) {
      case "upper":
        elText.value = text.toUpperCase();
        break;
      case "lower":
        elText.value = text.toLowerCase();
        break;
      case "title":
        elText.value = text.replace(/\b\w/g, function(c) { return c.toUpperCase(); });
        break;
      case "sentence":
        elText.value = text.toLowerCase().replace(/(^|[.!?]\s+)(\w)/g, function(match, p1, p2) {
          return p1 + p2.toUpperCase();
        });
        break;
    }
    update();
  };

  // --- Clear, Copy, Download ---
  window.wcClear = function() {
    elText.value = "";
    update();
    elText.focus();
  };

  window.wcCopy = function() {
    navigator.clipboard.writeText(elText.value).then(function() {
      var btn = document.getElementById("wcCopyBtn");
      var orig = btn.textContent;
      btn.textContent = "Copied";
      btn.style.borderColor = "var(--wc-green)";
      btn.style.color = "var(--wc-green)";
      setTimeout(function() {
        btn.textContent = orig;
        btn.style.borderColor = "";
        btn.style.color = "";
      }, 2000);
    });
  };

  window.wcDownload = function() {
    var text = elText.value;
    if (!text) return;
    var blob = new Blob([text], { type: "text/plain" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "text-" + Date.now() + ".txt";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  // --- Ngram toggle ---
  window.wcSetNgram = function(n, btn) {
    currentNgram = n;
    var tabs = btn.parentElement.querySelectorAll(".wc-kw-tab");
    for (var i = 0; i < tabs.length; i++) tabs[i].classList.remove("active");
    btn.classList.add("active");
    update();
  };

  // --- Event listeners ---
  function debouncedUpdate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(update, 80);
  }

  elText.addEventListener("input", debouncedUpdate);
  elLimitType.addEventListener("change", function() {
    update();
  });
  elLimitValue.addEventListener("input", debouncedUpdate);
  elFindInput.addEventListener("input", function() { updateFindCount(); });

  // Ctrl+H keyboard shortcut for find/replace
  document.addEventListener("keydown", function(e) {
    if ((e.ctrlKey || e.metaKey) && e.key === "h") {
      e.preventDefault();
      wcToggleFindReplace();
    }
  });

  // Auto-expand textarea
  elText.addEventListener("input", function() {
    this.style.height = "auto";
    var newHeight = Math.max(280, this.scrollHeight);
    this.style.height = newHeight + "px";
  });

  // --- Initial ---
  update();

})();
</script>
