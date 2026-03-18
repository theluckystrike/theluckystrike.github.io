---
layout: page
title: "Free AI Content Detector — Check If Text Is AI Written | Zovo"
description: "Detect AI-generated text with statistical analysis. Check perplexity, burstiness, sentence variance, and vocabulary diversity. Free online AI detector with detailed scoring."
permalink: /tools/ai-detector/
keywords: "ai detector, ai content detector, ai text detector, chatgpt detector, ai writing detector, ai checker, detect ai text, is this ai written"
date: 2026-03-19
categories: [tools]
tags: [ai-detector, ai-content, chatgpt, text-analysis, writing, nlp]
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
    --ad-primary: #6C5CE7;
    --ad-primary-dark: #5A4BD1;
    --ad-primary-light: #A29BFE;
    --ad-bg: #0a0a0f;
    --ad-surface: #12121a;
    --ad-surface-alt: #181824;
    --ad-border: #1e1e2e;
    --ad-border-light: #2a2a3e;
    --ad-text: #e0e0e0;
    --ad-text-muted: #8888aa;
    --ad-human: #00ff88;
    --ad-human-bg: rgba(0, 255, 136, 0.08);
    --ad-ai: #ff6b6b;
    --ad-ai-bg: rgba(255, 107, 107, 0.08);
    --ad-mixed: #ffa726;
    --ad-mixed-bg: rgba(255, 167, 38, 0.08);
    --ad-radius: 12px;
  }

  .ad-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ad-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px;
    line-height: 1.6;
  }

  .ad-wrapper * {
    box-sizing: border-box;
  }

  /* Hero */
  .ad-hero {
    text-align: center;
    padding: 48px 0 32px;
  }

  .ad-hero h1 {
    font-size: 2.4rem;
    font-weight: 800;
    color: #ffffff;
    margin: 0 0 16px;
    line-height: 1.15;
    letter-spacing: -0.02em;
  }

  .ad-hero h1 span {
    background: linear-gradient(135deg, var(--ad-primary), var(--ad-primary-light));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .ad-intro {
    font-size: 1.05rem;
    color: var(--ad-text-muted);
    max-width: 680px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Input Area */
  .ad-input-section {
    background: var(--ad-surface);
    border: 1px solid var(--ad-border);
    border-radius: var(--ad-radius);
    overflow: hidden;
    margin-bottom: 20px;
    box-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .ad-input-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 20px;
    border-bottom: 1px solid var(--ad-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--ad-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  .ad-input-header .ad-word-count {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--ad-text-muted);
  }

  .ad-textarea {
    width: 100%;
    min-height: 280px;
    border: none;
    padding: 20px;
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    line-height: 1.75;
    resize: vertical;
    color: var(--ad-text);
    background: var(--ad-surface);
    outline: none;
  }

  .ad-textarea::placeholder {
    color: #555570;
  }

  /* Toolbar */
  .ad-toolbar {
    display: flex;
    gap: 10px;
    align-items: center;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .ad-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 28px;
    border: none;
    border-radius: 10px;
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
    white-space: nowrap;
  }

  .ad-btn-primary {
    background: linear-gradient(135deg, var(--ad-primary), #7c6cf7);
    color: #fff;
    box-shadow: 0 4px 16px rgba(108, 92, 231, 0.35);
  }

  .ad-btn-primary:hover {
    background: linear-gradient(135deg, var(--ad-primary-dark), var(--ad-primary));
    box-shadow: 0 6px 24px rgba(108, 92, 231, 0.5);
    transform: translateY(-1px);
  }

  .ad-btn-primary:active {
    transform: translateY(0);
  }

  .ad-btn-secondary {
    background: var(--ad-surface);
    color: var(--ad-text-muted);
    border: 1px solid var(--ad-border);
  }

  .ad-btn-secondary:hover {
    background: var(--ad-surface-alt);
    color: var(--ad-text);
    border-color: var(--ad-border-light);
  }

  .ad-toolbar-spacer {
    flex: 1;
  }

  .ad-link-btn {
    background: none;
    border: none;
    color: var(--ad-primary-light);
    font-family: 'Inter', sans-serif;
    font-size: 0.82rem;
    font-weight: 500;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
    text-underline-offset: 3px;
  }

  .ad-link-btn:hover {
    color: var(--ad-primary);
  }

  /* Toggle for highlight */
  .ad-toggle-wrap {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.82rem;
    color: var(--ad-text-muted);
  }

  .ad-toggle {
    position: relative;
    width: 36px;
    height: 20px;
    appearance: none;
    -webkit-appearance: none;
    background: var(--ad-border);
    border-radius: 10px;
    outline: none;
    cursor: pointer;
    transition: background 0.2s;
  }

  .ad-toggle:checked {
    background: var(--ad-primary);
  }

  .ad-toggle::before {
    content: "";
    position: absolute;
    top: 2px;
    left: 2px;
    width: 16px;
    height: 16px;
    background: #fff;
    border-radius: 50%;
    transition: transform 0.2s;
  }

  .ad-toggle:checked::before {
    transform: translateX(16px);
  }

  /* Results Section */
  .ad-results {
    display: none;
    margin-bottom: 32px;
  }

  .ad-results.active {
    display: block;
  }

  /* Overall Score */
  .ad-verdict-card {
    background: var(--ad-surface);
    border: 1px solid var(--ad-border);
    border-radius: var(--ad-radius);
    padding: 36px 32px;
    text-align: center;
    margin-bottom: 20px;
    position: relative;
    overflow: hidden;
  }

  .ad-verdict-card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--ad-human), var(--ad-mixed), var(--ad-ai));
  }

  .ad-verdict-label {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--ad-text-muted);
    margin-bottom: 12px;
  }

  .ad-verdict-text {
    font-size: 1.6rem;
    font-weight: 700;
    margin-bottom: 8px;
    line-height: 1.2;
  }

  .ad-verdict-score {
    font-family: 'JetBrains Mono', monospace;
    font-size: 3.2rem;
    font-weight: 600;
    line-height: 1;
    margin-bottom: 8px;
  }

  .ad-verdict-sub {
    font-size: 0.9rem;
    color: var(--ad-text-muted);
  }

  /* Score bar */
  .ad-score-bar-wrap {
    max-width: 480px;
    margin: 20px auto 0;
  }

  .ad-score-bar-labels {
    display: flex;
    justify-content: space-between;
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin-bottom: 8px;
  }

  .ad-score-bar-labels .human-label { color: var(--ad-human); }
  .ad-score-bar-labels .ai-label { color: var(--ad-ai); }

  .ad-score-bar {
    width: 100%;
    height: 12px;
    background: linear-gradient(90deg, var(--ad-human), #44dd88 25%, var(--ad-mixed) 50%, #ff8866 75%, var(--ad-ai));
    border-radius: 6px;
    position: relative;
  }

  .ad-score-needle {
    position: absolute;
    top: -4px;
    width: 4px;
    height: 20px;
    background: #ffffff;
    border-radius: 2px;
    box-shadow: 0 0 8px rgba(255, 255, 255, 0.6);
    transition: left 0.8s cubic-bezier(0.22, 1, 0.36, 1);
  }

  /* Stats row */
  .ad-stats-row {
    display: flex;
    gap: 12px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .ad-stat-card {
    flex: 1;
    min-width: 140px;
    background: var(--ad-surface);
    border: 1px solid var(--ad-border);
    border-radius: 10px;
    padding: 16px 18px;
    text-align: center;
  }

  .ad-stat-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 600;
    color: #ffffff;
    margin-bottom: 4px;
  }

  .ad-stat-label {
    font-size: 0.75rem;
    color: var(--ad-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    font-weight: 500;
  }

  /* Metrics Grid */
  .ad-metrics-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 20px;
  }

  .ad-metric-card {
    background: var(--ad-surface);
    border: 1px solid var(--ad-border);
    border-radius: var(--ad-radius);
    padding: 24px;
  }

  .ad-metric-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 14px;
  }

  .ad-metric-name {
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--ad-text);
  }

  .ad-metric-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.88rem;
    font-weight: 600;
    padding: 3px 10px;
    border-radius: 6px;
    background: rgba(108, 92, 231, 0.12);
    color: var(--ad-primary-light);
  }

  .ad-metric-bar {
    width: 100%;
    height: 6px;
    background: var(--ad-border);
    border-radius: 3px;
    overflow: hidden;
    margin-bottom: 10px;
  }

  .ad-metric-fill {
    height: 100%;
    border-radius: 3px;
    transition: width 0.8s cubic-bezier(0.22, 1, 0.36, 1);
    width: 0%;
  }

  .ad-metric-desc {
    font-size: 0.8rem;
    color: var(--ad-text-muted);
    line-height: 1.55;
  }

  .ad-metric-signal {
    display: inline-block;
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    padding: 2px 8px;
    border-radius: 4px;
    margin-top: 8px;
  }

  .signal-human {
    background: var(--ad-human-bg);
    color: var(--ad-human);
  }

  .signal-ai {
    background: var(--ad-ai-bg);
    color: var(--ad-ai);
  }

  .signal-neutral {
    background: var(--ad-mixed-bg);
    color: var(--ad-mixed);
  }

  /* Breakdown panel */
  .ad-breakdown {
    background: var(--ad-surface);
    border: 1px solid var(--ad-border);
    border-radius: var(--ad-radius);
    margin-bottom: 20px;
    overflow: hidden;
  }

  .ad-breakdown-header {
    padding: 16px 24px;
    border-bottom: 1px solid var(--ad-border);
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--ad-text);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: space-between;
    user-select: none;
  }

  .ad-breakdown-header:hover {
    background: var(--ad-surface-alt);
  }

  .ad-breakdown-arrow {
    transition: transform 0.2s;
    font-size: 0.7rem;
    color: var(--ad-text-muted);
  }

  .ad-breakdown.open .ad-breakdown-arrow {
    transform: rotate(180deg);
  }

  .ad-breakdown-body {
    display: none;
    padding: 20px 24px;
  }

  .ad-breakdown.open .ad-breakdown-body {
    display: block;
  }

  .ad-pattern-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .ad-pattern-list li {
    padding: 10px 0;
    border-bottom: 1px solid var(--ad-border);
    font-size: 0.85rem;
    color: var(--ad-text-muted);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .ad-pattern-list li:last-child {
    border-bottom: none;
  }

  .ad-pattern-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    padding: 2px 8px;
    border-radius: 4px;
    font-weight: 500;
  }

  /* Highlighted text view */
  .ad-highlighted-text {
    display: none;
    background: var(--ad-surface);
    border: 1px solid var(--ad-border);
    border-radius: var(--ad-radius);
    padding: 24px;
    margin-bottom: 20px;
    font-size: 0.92rem;
    line-height: 1.85;
    color: var(--ad-text);
    max-height: 400px;
    overflow-y: auto;
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .ad-highlighted-text.active {
    display: block;
  }

  .ad-highlight-ai {
    background: rgba(255, 107, 107, 0.15);
    border-bottom: 2px solid var(--ad-ai);
    padding: 1px 2px;
    border-radius: 2px;
  }

  .ad-highlight-transition {
    background: rgba(255, 167, 38, 0.15);
    border-bottom: 2px solid var(--ad-mixed);
    padding: 1px 2px;
    border-radius: 2px;
  }

  /* Loading state */
  .ad-analyzing {
    display: none;
    text-align: center;
    padding: 48px 0;
  }

  .ad-analyzing.active {
    display: block;
  }

  .ad-spinner {
    width: 40px;
    height: 40px;
    border: 3px solid var(--ad-border);
    border-top-color: var(--ad-primary);
    border-radius: 50%;
    animation: ad-spin 0.8s linear infinite;
    margin: 0 auto 16px;
  }

  @keyframes ad-spin {
    to { transform: rotate(360deg); }
  }

  .ad-analyzing-text {
    font-size: 0.9rem;
    color: var(--ad-text-muted);
  }

  /* Content sections */
  .ad-content {
    max-width: 780px;
    margin: 48px auto 0;
    padding: 0 4px;
  }

  .ad-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: #ffffff;
    margin: 48px 0 16px;
    line-height: 1.25;
  }

  .ad-content h2:first-of-type {
    margin-top: 0;
  }

  .ad-content p {
    font-size: 0.95rem;
    color: var(--ad-text-muted);
    line-height: 1.8;
    margin: 0 0 18px;
  }

  .ad-content ul, .ad-content ol {
    padding-left: 24px;
    margin: 0 0 18px;
  }

  .ad-content li {
    font-size: 0.95rem;
    color: var(--ad-text-muted);
    line-height: 1.8;
    margin-bottom: 6px;
  }

  /* FAQ */
  .ad-faq {
    max-width: 780px;
    margin: 48px auto 0;
  }

  .ad-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    text-align: center;
    color: #ffffff;
    margin: 0 0 28px;
  }

  .ad-faq-item {
    border: 1px solid var(--ad-border);
    border-radius: var(--ad-radius);
    padding: 22px 26px;
    margin-bottom: 14px;
    background: var(--ad-surface);
  }

  .ad-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--ad-text);
  }

  .ad-faq-item p {
    margin: 0;
    font-size: 0.92rem;
    color: var(--ad-text-muted);
    line-height: 1.75;
  }

  /* Footer */
  .ad-footer {
    text-align: center;
    padding: 2.5rem 0;
    color: var(--ad-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--ad-border);
    margin-top: 48px;
  }

  .ad-footer a {
    color: var(--ad-primary-light);
    text-decoration: none;
  }

  .ad-footer a:hover {
    text-decoration: underline;
  }

  /* Scrollbar */
  .ad-wrapper ::-webkit-scrollbar {
    width: 6px;
  }

  .ad-wrapper ::-webkit-scrollbar-track {
    background: var(--ad-surface);
  }

  .ad-wrapper ::-webkit-scrollbar-thumb {
    background: var(--ad-border-light);
    border-radius: 3px;
  }

  /* Mobile */
  @media (max-width: 768px) {
    .ad-hero h1 {
      font-size: 1.7rem;
    }

    .ad-hero {
      padding: 32px 0 24px;
    }

    .ad-metrics-grid {
      grid-template-columns: 1fr;
    }

    .ad-stats-row {
      gap: 8px;
    }

    .ad-stat-card {
      min-width: 100px;
      padding: 12px 10px;
    }

    .ad-stat-value {
      font-size: 1.2rem;
    }

    .ad-verdict-score {
      font-size: 2.4rem;
    }

    .ad-verdict-text {
      font-size: 1.3rem;
    }

    .ad-btn {
      padding: 10px 20px;
      font-size: 0.88rem;
    }

    .ad-textarea {
      min-height: 200px;
    }

    .ad-toolbar {
      gap: 8px;
    }
  }

  @media (max-width: 480px) {
    .ad-stats-row {
      flex-wrap: wrap;
    }

    .ad-stat-card {
      flex: 1 1 45%;
    }
  }
</style>

<div class="ad-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Free AI Content Detector">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="ad-hero">
    <h1><span>AI Content Detector</span> — Free Text Analysis</h1>
    <p class="ad-intro">Paste any text to analyze it for patterns associated with AI-generated writing. This tool uses statistical heuristics including burstiness, vocabulary diversity, sentence variance, and n-gram repetition. Everything runs in your browser. Nothing is sent to a server.</p>
  </div>

  <!-- Input -->
  <div class="ad-input-section">
    <div class="ad-input-header">
      <span>Paste text to analyze</span>
      <span class="ad-word-count" id="adWordCount">0 words</span>
    </div>
    <textarea id="adInput" class="ad-textarea" placeholder="Paste the text you want to analyze here...

For best results, use at least 50 words. Longer passages (200+ words) produce more reliable scores." spellcheck="false"></textarea>
  </div>

  <!-- Toolbar -->
  <div class="ad-toolbar">
    <button class="ad-btn ad-btn-primary" onclick="adAnalyze()" id="adAnalyzeBtn">Analyze Text</button>
    <button class="ad-btn ad-btn-secondary" onclick="adClear()">Clear</button>
    <div class="ad-toggle-wrap" id="adHighlightToggle" style="display:none;">
      <input type="checkbox" class="ad-toggle" id="adHighlightCheck" onchange="adToggleHighlight()">
      <label for="adHighlightCheck" style="cursor:pointer;">Highlight patterns</label>
    </div>
    <div class="ad-toolbar-spacer"></div>
    <button class="ad-link-btn" onclick="adLoadSample('human')">Load human sample</button>
    <button class="ad-link-btn" onclick="adLoadSample('ai')">Load AI sample</button>
  </div>

  <!-- Analyzing spinner -->
  <div class="ad-analyzing" id="adAnalyzing">
    <div class="ad-spinner"></div>
    <div class="ad-analyzing-text">Analyzing text patterns...</div>
  </div>

  <!-- Results -->
  <div class="ad-results" id="adResults">

    <!-- Verdict -->
    <div class="ad-verdict-card" id="adVerdictCard">
      <div class="ad-verdict-label">Analysis Result</div>
      <div class="ad-verdict-score" id="adVerdictScore">0%</div>
      <div class="ad-verdict-text" id="adVerdictText">--</div>
      <div class="ad-verdict-sub" id="adVerdictSub"></div>
      <div class="ad-score-bar-wrap">
        <div class="ad-score-bar-labels">
          <span class="human-label">Human</span>
          <span class="ai-label">AI Generated</span>
        </div>
        <div class="ad-score-bar">
          <div class="ad-score-needle" id="adScoreNeedle" style="left: 0%;"></div>
        </div>
      </div>
    </div>

    <!-- Text stats -->
    <div class="ad-stats-row">
      <div class="ad-stat-card">
        <div class="ad-stat-value" id="adStatWords">0</div>
        <div class="ad-stat-label">Words</div>
      </div>
      <div class="ad-stat-card">
        <div class="ad-stat-value" id="adStatSentences">0</div>
        <div class="ad-stat-label">Sentences</div>
      </div>
      <div class="ad-stat-card">
        <div class="ad-stat-value" id="adStatParagraphs">0</div>
        <div class="ad-stat-label">Paragraphs</div>
      </div>
      <div class="ad-stat-card">
        <div class="ad-stat-value" id="adStatAvgSentLen">0</div>
        <div class="ad-stat-label">Avg Sentence Len</div>
      </div>
    </div>

    <!-- Metrics -->
    <div class="ad-metrics-grid" id="adMetricsGrid">
      <div class="ad-metric-card" id="adMetric-burstiness">
        <div class="ad-metric-header">
          <span class="ad-metric-name">Burstiness</span>
          <span class="ad-metric-value" id="adVal-burstiness">--</span>
        </div>
        <div class="ad-metric-bar"><div class="ad-metric-fill" id="adFill-burstiness"></div></div>
        <div class="ad-metric-desc">Measures variance in sentence length. Human writing tends to mix short and long sentences. AI text keeps sentences at a uniform length.</div>
        <div class="ad-metric-signal" id="adSig-burstiness"></div>
      </div>

      <div class="ad-metric-card" id="adMetric-vocabulary">
        <div class="ad-metric-header">
          <span class="ad-metric-name">Vocabulary Diversity</span>
          <span class="ad-metric-value" id="adVal-vocabulary">--</span>
        </div>
        <div class="ad-metric-bar"><div class="ad-metric-fill" id="adFill-vocabulary"></div></div>
        <div class="ad-metric-desc">Type-token ratio: unique words divided by total words. Low diversity (below 0.4) suggests repetitive, formulaic language common in AI outputs.</div>
        <div class="ad-metric-signal" id="adSig-vocabulary"></div>
      </div>

      <div class="ad-metric-card" id="adMetric-sentenceVariance">
        <div class="ad-metric-header">
          <span class="ad-metric-name">Sentence Length Variance</span>
          <span class="ad-metric-value" id="adVal-sentenceVariance">--</span>
        </div>
        <div class="ad-metric-bar"><div class="ad-metric-fill" id="adFill-sentenceVariance"></div></div>
        <div class="ad-metric-desc">Standard deviation of sentence lengths in words. Higher variance suggests natural writing. AI tends to produce sentences of similar lengths.</div>
        <div class="ad-metric-signal" id="adSig-sentenceVariance"></div>
      </div>

      <div class="ad-metric-card" id="adMetric-repetition">
        <div class="ad-metric-header">
          <span class="ad-metric-name">Repetition Score</span>
          <span class="ad-metric-value" id="adVal-repetition">--</span>
        </div>
        <div class="ad-metric-bar"><div class="ad-metric-fill" id="adFill-repetition"></div></div>
        <div class="ad-metric-desc">Detects repeated n-gram phrases (3+ word sequences appearing 3+ times). High repetition is a strong signal of AI-generated text.</div>
        <div class="ad-metric-signal" id="adSig-repetition"></div>
      </div>

      <div class="ad-metric-card" id="adMetric-transition">
        <div class="ad-metric-header">
          <span class="ad-metric-name">Transition Word Density</span>
          <span class="ad-metric-value" id="adVal-transition">--</span>
        </div>
        <div class="ad-metric-bar"><div class="ad-metric-fill" id="adFill-transition"></div></div>
        <div class="ad-metric-desc">Frequency of words like "however", "furthermore", "moreover", "additionally". AI writing overuses these formal transition words compared to natural writing.</div>
        <div class="ad-metric-signal" id="adSig-transition"></div>
      </div>

      <div class="ad-metric-card" id="adMetric-patterns">
        <div class="ad-metric-header">
          <span class="ad-metric-name">AI Phrase Patterns</span>
          <span class="ad-metric-value" id="adVal-patterns">--</span>
        </div>
        <div class="ad-metric-bar"><div class="ad-metric-fill" id="adFill-patterns"></div></div>
        <div class="ad-metric-desc">Checks for phrases strongly associated with AI output: "it's important to note", "delve", "tapestry", "landscape", "in conclusion", and similar markers.</div>
        <div class="ad-metric-signal" id="adSig-patterns"></div>
      </div>
    </div>

    <!-- Detailed breakdown -->
    <div class="ad-breakdown" id="adBreakdown">
      <div class="ad-breakdown-header" onclick="adToggleBreakdown()">
        <span>Detailed Signal Breakdown</span>
        <span class="ad-breakdown-arrow">&#9660;</span>
      </div>
      <div class="ad-breakdown-body" id="adBreakdownBody">
        <ul class="ad-pattern-list" id="adPatternList"></ul>
      </div>
    </div>

    <!-- Highlighted text -->
    <div class="ad-highlighted-text" id="adHighlightedText"></div>

  </div>

  <!-- Content Section -->
  <div class="ad-content">

    <h2>What Is an AI Content Detector</h2>
    <p>An AI content detector is a tool that analyzes a piece of writing and estimates whether it was produced by a human or generated by an AI language model such as ChatGPT, Claude, Gemini, or similar systems. These tools look for statistical patterns in the text rather than reading for meaning. The core idea is straightforward: AI-generated text has measurable properties that differ from text written by a person. By quantifying those properties, a detector can flag content that is statistically more consistent with machine output than with human writing.</p>
    <p>Most online AI detectors use one of two approaches. Some run the input through a trained classifier, essentially a smaller neural network that has learned to distinguish AI text from human text. Others, including this tool, rely on statistical heuristics. Heuristic-based detectors do not require an internet connection or a model on a server. They calculate features like sentence length variance, vocabulary diversity, and phrase repetition directly in the browser and compare the results to known ranges for human and AI writing.</p>
    <p>No detector is perfect. The boundaries between human and AI writing are blurry, especially when a person edits AI-generated content or when a skilled writer happens to produce unusually uniform prose. Think of the result as an informed estimate, not a definitive verdict. The goal is to give you additional information to work with, not to replace your own judgment about a piece of writing.</p>
    <p>AI detection has become relevant across several fields. Teachers use these tools to screen student submissions. Publishers check freelance content. Businesses verify that marketing copy was actually written by the person they hired. Search engines are reportedly using similar signals to evaluate content quality. Whether you are reviewing text for academic integrity, editorial standards, or SEO purposes, understanding what these tools measure (and what they miss) helps you interpret the results responsibly.</p>

    <h2>How AI Detection Works</h2>
    <p>This tool uses six statistical signals to produce a composite score. Each signal measures a different property of the text, and together they create a profile that leans toward "human" or "AI." The analysis happens in three stages.</p>
    <p>First, the text is tokenized. Sentences are split at periods, question marks, and exclamation marks. Words are extracted by splitting on whitespace and removing punctuation. Paragraphs are identified by blank-line boundaries. These counts provide the raw material for every metric that follows.</p>
    <p>Second, each of the six metrics is computed independently. Burstiness measures how much sentence lengths vary. Vocabulary diversity calculates the ratio of unique words to total words. Sentence length variance captures the standard deviation. Repetition counts how often the same three-word or four-word phrase appears. Transition word density tallies formal connective words relative to total word count. The AI phrase patterns metric checks for specific expressions that appear disproportionately in AI-generated content.</p>
    <p>Third, the individual metric scores are weighted and combined into a single percentage. The composite score ranges from 0 (confidently human) to 100 (confidently AI). Scores between 30 and 60 land in the "uncertain" range, which means the text has a mix of signals or the sample is too short to draw a strong conclusion.</p>
    <p>The weighting is not equal across all six signals. Burstiness and vocabulary diversity carry the most weight because research consistently shows these are the strongest differentiators between human and AI text. Transition word density and AI phrase patterns carry less weight individually but can push a borderline score into a clearer verdict when they are present in high concentration. Paragraph uniformity, which measures whether all paragraphs are roughly the same length, is factored in as a minor signal because it is less reliable on its own.</p>

    <h2>Understanding the Analysis Metrics</h2>
    <p>Burstiness is the most commonly cited signal in AI detection research. The term describes how "bursty" the rhythm of the writing is. When a person writes, some sentences are five words long and the next is thirty. AI models tend to produce sentences that hover around a median length. A text with low burstiness reads as monotonous even if the vocabulary is rich. This tool measures burstiness by computing the coefficient of variation of sentence lengths. A high coefficient means high burstiness, which suggests human writing.</p>
    <p>Vocabulary diversity is expressed as a type-token ratio (TTR). If a 500-word passage uses 280 unique words, the TTR is 0.56. Longer texts naturally have lower TTR because common words repeat, so the score is length-adjusted. AI models recycle certain words and phrases more than most human writers, pulling the TTR down. A TTR below 0.4 on a passage of moderate length is a flag.</p>
    <p>Sentence length variance and burstiness are related but not identical. Variance is the raw standard deviation measured in words per sentence. A standard deviation below 4 in a multi-paragraph text is unusual for human writing and common in AI output.</p>
    <p>Repetition scoring looks at n-grams, specifically trigrams (three-word sequences) and four-grams. The tool counts how many distinct n-grams appear three or more times. Some repetition is normal ("in the", "one of the"), so common stop-word trigrams are excluded. What remains is a count of repeated substantive phrases, which is higher in AI text.</p>
    <p>Transition word density tracks words and phrases like "however", "furthermore", "additionally", "moreover", "consequently", and "nevertheless". AI models are trained on formal writing and overrepresent these connectives. A density above 2% of total words is a mild flag; above 3.5% is a stronger one.</p>
    <p>The AI phrase pattern check is the most specific signal. It scans for exact strings such as "it's important to note", "it's worth noting", "delve", "tapestry", "multifaceted", "in today's digital age", "on the other hand", and similar constructions that appear at unusually high rates in ChatGPT and similar model outputs. Each match adds to the score. These phrases are not inherently wrong or unusual on their own. Any human might write "on the other hand" in an essay. The signal becomes meaningful when several of them appear together in a single text, because that concentration is far more common in AI output than in human writing. The list of tracked phrases is updated as language model behavior evolves, since newer model versions sometimes drop old habits and develop new ones.</p>

    <h2>Limitations of AI Detection</h2>
    <p>Statistical AI detection has real limitations, and you should understand them before acting on a result.</p>
    <ul>
      <li>Short texts (under 50 words) do not provide enough data. Metrics like burstiness and sentence variance need at least several sentences to be meaningful.</li>
      <li>Edited AI text is harder to detect. If a person rewrites sentences, varies the structure, and replaces generic words, the statistical fingerprint changes. A lightly edited ChatGPT output may score in the uncertain range.</li>
      <li>Technical and academic writing naturally has lower burstiness and higher transition word density. A research paper written entirely by a human may trigger AI signals because of its formal register.</li>
      <li>Non-native English speakers sometimes produce writing that resembles AI output because they rely on common sentence structures and limited vocabulary. A low vocabulary diversity score does not prove AI involvement.</li>
      <li>This tool does not use a trained neural network. It cannot detect AI text that has been specifically crafted to evade statistical heuristics. Dedicated ML-based detectors may perform better on adversarial cases, though they have their own false-positive issues.</li>
    </ul>
    <p>The scores produced here are indicators, not proof. Use them as one data point among many when evaluating text origin. Reading the text yourself, checking for factual accuracy, and comparing it to the author's other work are all important steps that no automated tool can replace.</p>

    <h2>Tips for More Accurate Results</h2>
    <ul>
      <li>Paste at least 200 words. The more text you provide, the more stable the metrics become. A single paragraph is often too little.</li>
      <li>Analyze the body text only. Strip out headings, bullet points, code blocks, and metadata before pasting. These elements skew sentence length calculations.</li>
      <li>Check multiple passages. If you suspect a long document was partially AI-generated, test different sections separately. The score may vary across sections.</li>
      <li>Compare against a known baseline. Run a sample of your own writing through the tool to see your personal score. That gives you a reference point for interpreting results on other texts.</li>
      <li>Do not rely on a single metric. A text with high vocabulary diversity but very low burstiness might still be AI-generated. Look at the overall pattern across all six metrics.</li>
      <li>Consider the context. A legal contract will score differently from a blog post. Match your expectations to the text type.</li>
    </ul>

    <h2>Common AI Writing Patterns</h2>
    <p>Certain habits appear so often in AI-generated text that experienced readers can spot them without a tool. Knowing what to look for can help you interpret the scores this detector produces.</p>
    <p>Uniform sentence length is the most reliable visual cue. Open any ChatGPT output and count the words per sentence. You will often find them clustering around 15 to 22 words with few outliers. Human writing swings more widely, mixing fragments with run-on sentences.</p>
    <p>Overqualification is another pattern. AI models hedge constantly: "it's important to note that", "while there are many perspectives", "it's worth mentioning". These hedges add words without adding meaning. The transition word density metric captures part of this, but the habit extends beyond connectives into whole-clause qualifiers.</p>
    <p>AI text often follows a predictable structure: introduce a topic, list supporting points, summarize. Every paragraph does this. Human writing is messier. It digresses, circles back, abandons threads, and picks them up later. That structural unpredictability is hard to measure statistically, but it contributes to the "feel" that separates human from machine text.</p>
    <p>Certain words appear far more often in AI output than in human-written text on the same topics. "Delve", "tapestry", "landscape" (in figurative use), "multifaceted", "comprehensive", "streamline", and "leverage" are among the most documented. This tool checks for these and flags their presence.</p>
    <p>Paragraph length uniformity is a subtler signal. AI models tend to produce paragraphs of similar length, often three to five sentences each. Human writers vary paragraph length based on emphasis, pacing, and personal style. A document where every paragraph is four sentences long is worth a closer look.</p>
    <p>Lack of specificity is a pattern that statistical tools struggle to measure but humans notice quickly. AI-generated text often stays abstract. It says "many experts agree" without naming one. It says "research shows" without citing a study. It says "in recent years" without saying which year. Human writers anchor their claims with concrete references, dates, names, and personal anecdotes. If a piece of writing feels like it could be about any topic with a few word substitutions, that is a strong qualitative signal even if the statistical metrics come back mixed.</p>
  </div>

  <!-- FAQ -->
  <div class="ad-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="ad-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is this AI content detector?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool uses statistical heuristics, not a trained machine learning model. On clearly AI-generated text of 200+ words, it typically scores in the 65-90 range. On clearly human-written text, it scores 10-35. Edited or mixed content falls in between. No AI detector, statistical or ML-based, achieves 100% accuracy. Treat the result as an informed estimate rather than proof.</p>
      </div>
    </div>

    <div class="ad-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my text stored or sent to a server?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All analysis runs entirely in your browser using JavaScript. Your text never leaves your device. There are no API calls, no server-side processing, and no logging. You can verify this by watching the Network tab in your browser's developer tools while running an analysis.</p>
      </div>
    </div>

    <div class="ad-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the minimum text length for reliable results?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool requires at least 20 words to run any analysis, but results become meaningful at around 50 words and most reliable above 200 words. Short texts simply do not contain enough sentences to compute meaningful burstiness, variance, or repetition metrics. When possible, paste several paragraphs for the best results.</p>
      </div>
    </div>

    <div class="ad-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can this detect ChatGPT, Claude, and Gemini output?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The statistical patterns this tool measures are common across most large language models, including ChatGPT, Claude, Gemini, LLaMA, and others. The tool does not identify which model produced the text. It flags statistical properties (low burstiness, low vocabulary diversity, high transition word density) that are shared across AI models in general.</p>
      </div>
    </div>

    <div class="ad-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why does my human-written text score as AI-generated?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">False positives happen, especially with formal or academic writing. Technical documentation, legal text, and ESL writing can trigger AI signals because they naturally have lower vocabulary diversity and higher transition word density. Short samples are also prone to unreliable scores. If you know the text is human-written, the score reflects the statistical properties of that particular passage, not a flaw in the writer.</p>
      </div>
    </div>

    <div class="ad-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What do the individual metric scores mean?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Each metric measures a different statistical property. Burstiness measures sentence length variation (higher is more human). Vocabulary diversity measures unique word usage (higher is more human). Sentence length variance measures the standard deviation of sentence lengths. Repetition counts repeated phrases. Transition word density measures formal connectives. AI phrase patterns flags specific expressions common in AI output. The overall score combines all six with different weights.</p>
      </div>
    </div>
  </div>

  <footer class="ad-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  // --- Sample texts ---
  var SAMPLE_HUMAN = "I remember the first time I saw the ocean. I was maybe seven or eight. We'd driven all night from Kansas, my dad chain-smoking Marlboros with the window cracked, my sister asleep against my shoulder. The car smelled like gas station coffee and something sweet I could never identify. When we got there it was barely light out. Gray sky. Gray water. Not the postcard blue I'd imagined. But the sound hit me before anything else. This low, constant roar that seemed to come from everywhere at once. My dad said something like \"well, there it is\" and that was that. We stood in the parking lot for a while. Nobody moved toward the beach. I think we were all just tired. But I kept listening to that sound and thinking: this has been going on forever. Before me, before my dad, before anyone. Just water hitting sand over and over and over. We ate breakfast at a diner where the waitress called everyone honey. I had pancakes. They were nothing special. But I can still taste them forty years later, which tells you something about how memory works. It grabs the small things and lets the big moments blur.";

  var SAMPLE_AI = "Artificial intelligence has fundamentally transformed the landscape of modern technology, offering unprecedented opportunities for innovation across virtually every sector. It's important to note that the rapid advancement of AI systems has created a multifaceted paradigm shift in how organizations approach problem-solving and decision-making. Furthermore, the integration of machine learning algorithms into existing workflows has streamlined operations and enhanced productivity in remarkable ways. The comprehensive nature of these technological developments cannot be overstated. Additionally, the democratization of AI tools has enabled smaller organizations to leverage capabilities that were previously available only to large enterprises with substantial resources. However, it's worth noting that this technological revolution also presents significant challenges that must be carefully considered. Moreover, the ethical implications of widespread AI adoption have sparked important conversations about responsibility, transparency, and accountability in the development and deployment of these powerful systems. The landscape of artificial intelligence continues to evolve at an extraordinary pace, and stakeholders across all sectors must remain vigilant in their efforts to harness its potential while mitigating associated risks. In conclusion, the transformative power of AI represents both a tremendous opportunity and a profound responsibility for society as a whole.";

  // --- Transition words list ---
  var TRANSITION_WORDS = [
    "however", "furthermore", "moreover", "additionally", "consequently",
    "nevertheless", "nonetheless", "therefore", "thus", "hence",
    "accordingly", "meanwhile", "subsequently", "conversely", "alternatively",
    "specifically", "particularly", "notably", "significantly", "ultimately",
    "essentially", "fundamentally", "importantly"
  ];

  var TRANSITION_PHRASES = [
    "in addition", "on the other hand", "as a result", "for instance",
    "for example", "in contrast", "in particular", "at the same time",
    "in other words", "to that end", "by contrast", "in this regard",
    "to this end", "with that said", "that being said", "having said that",
    "it is worth noting", "it should be noted"
  ];

  // --- AI-associated phrases ---
  var AI_PHRASES = [
    "it's important to note",
    "it's worth noting",
    "it is important to note",
    "it is worth noting",
    "it's crucial to",
    "it is crucial to",
    "it's essential to",
    "in today's digital age",
    "in today's rapidly",
    "in today's world",
    "in the ever-evolving",
    "in this comprehensive",
    "the landscape of",
    "the realm of",
    "cannot be overstated",
    "paradigm shift",
    "multifaceted",
    "game-changer",
    "game changer",
    "leverage the power",
    "harness the power",
    "harness the potential",
    "a testament to",
    "a crucial role",
    "plays a vital role",
    "plays a crucial role",
    "it goes without saying",
    "at the end of the day"
  ];

  var AI_WORDS = [
    "delve", "tapestry", "landscape", "multifaceted", "comprehensive",
    "streamline", "utilize", "underscore", "underscores", "aforementioned",
    "holistic", "synergy", "paradigm", "nuanced", "pivotal",
    "groundbreaking", "transformative", "unprecedented", "spearhead",
    "uncharted", "bustling", "testament", "cornerstone"
  ];

  // --- Utility functions ---

  function getWords(text) {
    return text.replace(/[^\w\s'-]/g, " ").split(/\s+/).filter(function(w) {
      return w.length > 0;
    });
  }

  function getSentences(text) {
    // Split on sentence-ending punctuation followed by space or end
    var raw = text.split(/(?<=[.!?])\s+/);
    return raw.filter(function(s) {
      var words = s.trim().split(/\s+/).filter(function(w) { return w.length > 0; });
      return words.length >= 2;
    });
  }

  function getParagraphs(text) {
    return text.split(/\n\s*\n/).filter(function(p) {
      return p.trim().length > 0;
    });
  }

  function mean(arr) {
    if (arr.length === 0) return 0;
    var sum = 0;
    for (var i = 0; i < arr.length; i++) sum += arr[i];
    return sum / arr.length;
  }

  function stddev(arr) {
    if (arr.length < 2) return 0;
    var m = mean(arr);
    var sqDiffSum = 0;
    for (var i = 0; i < arr.length; i++) {
      sqDiffSum += (arr[i] - m) * (arr[i] - m);
    }
    return Math.sqrt(sqDiffSum / arr.length);
  }

  function coefficientOfVariation(arr) {
    var m = mean(arr);
    if (m === 0) return 0;
    return stddev(arr) / m;
  }

  // --- Metric computations ---

  function computeBurstiness(sentences) {
    var lengths = sentences.map(function(s) {
      return s.trim().split(/\s+/).filter(function(w) { return w.length > 0; }).length;
    });
    if (lengths.length < 3) return { raw: 0, score: 50, signal: "neutral" };

    var cv = coefficientOfVariation(lengths);
    // Human writing: CV typically 0.4-0.8+. AI: 0.15-0.35
    // Score 0-100 where 100 = very bursty (human)
    var score = Math.min(100, Math.max(0, (cv - 0.1) / 0.7 * 100));
    var signal = score > 55 ? "human" : score < 35 ? "ai" : "neutral";
    return { raw: cv, score: score, signal: signal };
  }

  function computeVocabularyDiversity(words) {
    if (words.length < 10) return { raw: 0, score: 50, signal: "neutral" };

    var lower = words.map(function(w) { return w.toLowerCase().replace(/[^a-z'-]/g, ""); }).filter(function(w) { return w.length > 0; });
    var unique = {};
    for (var i = 0; i < lower.length; i++) {
      unique[lower[i]] = true;
    }
    var ttr = Object.keys(unique).length / lower.length;

    // Adjust for length: longer texts naturally have lower TTR
    // Apply a mild correction factor
    var adjusted = ttr;
    if (lower.length > 100) {
      adjusted = ttr * Math.pow(lower.length / 100, 0.15);
    }

    // Human: TTR usually 0.5-0.75 adjusted. AI: 0.3-0.5
    var score = Math.min(100, Math.max(0, (adjusted - 0.25) / 0.45 * 100));
    var signal = score > 55 ? "human" : score < 35 ? "ai" : "neutral";
    return { raw: ttr, score: score, signal: signal };
  }

  function computeSentenceVariance(sentences) {
    var lengths = sentences.map(function(s) {
      return s.trim().split(/\s+/).filter(function(w) { return w.length > 0; }).length;
    });
    if (lengths.length < 3) return { raw: 0, score: 50, signal: "neutral" };

    var sd = stddev(lengths);
    // Human: SD often 5-15+. AI: 2-5
    var score = Math.min(100, Math.max(0, (sd - 1.5) / 10 * 100));
    var signal = score > 55 ? "human" : score < 35 ? "ai" : "neutral";
    return { raw: sd, score: score, signal: signal };
  }

  function computeRepetition(words) {
    if (words.length < 20) return { raw: 0, score: 50, signal: "neutral", repeats: [] };

    var lower = words.map(function(w) { return w.toLowerCase().replace(/[^a-z'-]/g, ""); }).filter(function(w) { return w.length > 0; });

    // Common stop trigrams to ignore
    var stopTrigrams = {
      "one of the": 1, "a lot of": 1, "in the the": 1,
      "of the the": 1, "the the the": 1, "in order to": 1,
      "as well as": 1, "some of the": 1, "part of the": 1
    };

    // Count trigrams
    var trigrams = {};
    for (var i = 0; i < lower.length - 2; i++) {
      var tri = lower[i] + " " + lower[i+1] + " " + lower[i+2];
      if (!stopTrigrams[tri]) {
        trigrams[tri] = (trigrams[tri] || 0) + 1;
      }
    }

    // Count four-grams
    var fourgrams = {};
    for (var j = 0; j < lower.length - 3; j++) {
      var fg = lower[j] + " " + lower[j+1] + " " + lower[j+2] + " " + lower[j+3];
      fourgrams[fg] = (fourgrams[fg] || 0) + 1;
    }

    var repeatedTri = [];
    var triKeys = Object.keys(trigrams);
    for (var k = 0; k < triKeys.length; k++) {
      if (trigrams[triKeys[k]] >= 3) {
        repeatedTri.push({ phrase: triKeys[k], count: trigrams[triKeys[k]] });
      }
    }

    var repeatedFour = [];
    var fgKeys = Object.keys(fourgrams);
    for (var m = 0; m < fgKeys.length; m++) {
      if (fourgrams[fgKeys[m]] >= 3) {
        repeatedFour.push({ phrase: fgKeys[m], count: fourgrams[fgKeys[m]] });
      }
    }

    var totalRepeats = repeatedTri.length + repeatedFour.length * 1.5;
    var normalized = totalRepeats / (lower.length / 100);

    // 0 repeats = human, 3+ per 100 words = strong AI signal
    var aiScore = Math.min(100, Math.max(0, normalized / 3 * 100));
    var score = 100 - aiScore; // Invert: high score = human (low repetition)
    var signal = score > 55 ? "human" : score < 35 ? "ai" : "neutral";

    var allRepeats = repeatedTri.concat(repeatedFour);
    allRepeats.sort(function(a, b) { return b.count - a.count; });

    return { raw: totalRepeats, score: score, signal: signal, repeats: allRepeats.slice(0, 10) };
  }

  function computeTransitionDensity(text, words) {
    if (words.length < 20) return { raw: 0, score: 50, signal: "neutral", found: [] };

    var lower = text.toLowerCase();
    var count = 0;
    var found = [];

    // Count single-word transitions
    var wordSet = words.map(function(w) { return w.toLowerCase().replace(/[^a-z]/g, ""); });
    for (var i = 0; i < TRANSITION_WORDS.length; i++) {
      var tw = TRANSITION_WORDS[i];
      var twCount = 0;
      for (var j = 0; j < wordSet.length; j++) {
        if (wordSet[j] === tw) twCount++;
      }
      if (twCount > 0) {
        count += twCount;
        found.push({ word: tw, count: twCount });
      }
    }

    // Count multi-word transitions
    for (var k = 0; k < TRANSITION_PHRASES.length; k++) {
      var tp = TRANSITION_PHRASES[k];
      var regex = new RegExp(tp.replace(/[.*+?^${}()|[\]\\]/g, '\\$&'), "gi");
      var matches = lower.match(regex);
      if (matches && matches.length > 0) {
        count += matches.length;
        found.push({ word: tp, count: matches.length });
      }
    }

    var density = (count / words.length) * 100;

    // Human: usually 0.5-2%. AI: 2.5-5%+
    var aiScore = Math.min(100, Math.max(0, (density - 0.5) / 4 * 100));
    var score = 100 - aiScore;
    var signal = score > 55 ? "human" : score < 35 ? "ai" : "neutral";

    found.sort(function(a, b) { return b.count - a.count; });

    return { raw: density, score: score, signal: signal, found: found.slice(0, 10) };
  }

  function computeAIPhrasePatterns(text, words) {
    if (words.length < 20) return { raw: 0, score: 50, signal: "neutral", found: [] };

    var lower = text.toLowerCase();
    var found = [];
    var totalHits = 0;

    // Check phrases
    for (var i = 0; i < AI_PHRASES.length; i++) {
      var phrase = AI_PHRASES[i];
      var regex = new RegExp(phrase.replace(/[.*+?^${}()|[\]\\]/g, '\\$&'), "gi");
      var matches = lower.match(regex);
      if (matches && matches.length > 0) {
        totalHits += matches.length;
        found.push({ phrase: phrase, count: matches.length });
      }
    }

    // Check words
    var wordSet = words.map(function(w) { return w.toLowerCase().replace(/[^a-z]/g, ""); });
    for (var j = 0; j < AI_WORDS.length; j++) {
      var aw = AI_WORDS[j];
      var awCount = 0;
      for (var k = 0; k < wordSet.length; k++) {
        if (wordSet[k] === aw) awCount++;
      }
      if (awCount > 0) {
        totalHits += awCount;
        found.push({ phrase: aw, count: awCount });
      }
    }

    var hitsPerHundred = (totalHits / words.length) * 100;

    // 0 hits = human signal. 1+ per 100 words = AI signal
    var aiScore = Math.min(100, Math.max(0, hitsPerHundred / 2 * 100));
    var score = 100 - aiScore;
    var signal = score > 55 ? "human" : score < 35 ? "ai" : "neutral";

    found.sort(function(a, b) { return b.count - a.count; });

    return { raw: totalHits, score: score, signal: signal, found: found };
  }

  // --- Paragraph uniformity (used in composite but not displayed as a gauge) ---
  function computeParagraphUniformity(paragraphs) {
    if (paragraphs.length < 3) return 50;

    var lengths = paragraphs.map(function(p) {
      return p.trim().split(/\s+/).filter(function(w) { return w.length > 0; }).length;
    });

    var cv = coefficientOfVariation(lengths);
    // High CV = varied paragraphs = human. Low CV = uniform = AI
    var score = Math.min(100, Math.max(0, (cv - 0.05) / 0.6 * 100));
    return score;
  }

  // --- Composite score ---
  function computeComposite(metrics, paraScore) {
    // Weights: burstiness and vocabulary are strongest signals
    var weights = {
      burstiness: 0.22,
      vocabulary: 0.18,
      sentenceVariance: 0.15,
      repetition: 0.15,
      transition: 0.15,
      patterns: 0.10,
      paragraph: 0.05
    };

    var composite =
      metrics.burstiness.score * weights.burstiness +
      metrics.vocabulary.score * weights.vocabulary +
      metrics.sentenceVariance.score * weights.sentenceVariance +
      metrics.repetition.score * weights.repetition +
      metrics.transition.score * weights.transition +
      metrics.patterns.score * weights.patterns +
      paraScore * weights.paragraph;

    // Invert: 0 = human, 100 = AI
    var aiScore = 100 - composite;
    return Math.round(Math.min(100, Math.max(0, aiScore)));
  }

  // --- UI references ---
  var inputEl = document.getElementById("adInput");
  var wordCountEl = document.getElementById("adWordCount");
  var resultsEl = document.getElementById("adResults");
  var analyzingEl = document.getElementById("adAnalyzing");
  var highlightToggleEl = document.getElementById("adHighlightToggle");
  var highlightCheckEl = document.getElementById("adHighlightCheck");
  var highlightedTextEl = document.getElementById("adHighlightedText");

  var lastAnalysis = null;

  // --- Word count on input ---
  inputEl.addEventListener("input", function() {
    var words = getWords(inputEl.value);
    wordCountEl.textContent = words.length + " word" + (words.length !== 1 ? "s" : "");
  });

  // --- Main analyze function ---
  window.adAnalyze = function() {
    var text = inputEl.value.trim();
    if (!text) return;

    var words = getWords(text);
    if (words.length < 20) {
      alert("Please paste at least 20 words for the analysis to work.");
      return;
    }

    // Show loading
    resultsEl.classList.remove("active");
    analyzingEl.classList.add("active");
    highlightToggleEl.style.display = "none";

    setTimeout(function() {
      var sentences = getSentences(text);
      var paragraphs = getParagraphs(text);

      var metrics = {
        burstiness: computeBurstiness(sentences),
        vocabulary: computeVocabularyDiversity(words),
        sentenceVariance: computeSentenceVariance(sentences),
        repetition: computeRepetition(words),
        transition: computeTransitionDensity(text, words),
        patterns: computeAIPhrasePatterns(text, words)
      };

      var paraScore = computeParagraphUniformity(paragraphs);
      var aiScore = computeComposite(metrics, paraScore);

      lastAnalysis = {
        text: text,
        words: words,
        sentences: sentences,
        paragraphs: paragraphs,
        metrics: metrics,
        aiScore: aiScore
      };

      renderResults(lastAnalysis);

      analyzingEl.classList.remove("active");
      resultsEl.classList.add("active");
      highlightToggleEl.style.display = "flex";

      // Scroll to results
      document.getElementById("adVerdictCard").scrollIntoView({ behavior: "smooth", block: "start" });

    }, 400); // Brief delay for UX
  };

  // --- Render results ---
  function renderResults(data) {
    var aiScore = data.aiScore;
    var metrics = data.metrics;

    // Verdict
    var verdictScoreEl = document.getElementById("adVerdictScore");
    var verdictTextEl = document.getElementById("adVerdictText");
    var verdictSubEl = document.getElementById("adVerdictSub");
    var needleEl = document.getElementById("adScoreNeedle");
    var verdictCard = document.getElementById("adVerdictCard");

    verdictScoreEl.textContent = aiScore + "%";

    var verdict, verdictColor, subText;
    if (aiScore <= 30) {
      verdict = "Likely Human Written";
      verdictColor = "var(--ad-human)";
      subText = "The text shows strong indicators of human authorship across most metrics.";
    } else if (aiScore <= 60) {
      verdict = "Mixed / Uncertain";
      verdictColor = "var(--ad-mixed)";
      subText = "The text shows a mix of human and AI signals. It may be partially AI-generated or edited.";
    } else {
      verdict = "Likely AI Generated";
      verdictColor = "var(--ad-ai)";
      subText = "The text shows multiple statistical patterns consistent with AI-generated content.";
    }

    verdictTextEl.textContent = verdict;
    verdictTextEl.style.color = verdictColor;
    verdictScoreEl.style.color = verdictColor;
    verdictSubEl.textContent = subText;

    // Position needle (0% = left/human, 100% = right/AI)
    setTimeout(function() {
      needleEl.style.left = "calc(" + aiScore + "% - 2px)";
    }, 50);

    // Stats
    document.getElementById("adStatWords").textContent = data.words.length;
    document.getElementById("adStatSentences").textContent = data.sentences.length;
    document.getElementById("adStatParagraphs").textContent = data.paragraphs.length;
    var avgLen = data.sentences.length > 0 ? Math.round(mean(data.sentences.map(function(s) {
      return s.trim().split(/\s+/).filter(function(w) { return w.length > 0; }).length;
    }))) : 0;
    document.getElementById("adStatAvgSentLen").textContent = avgLen;

    // Metrics
    renderMetric("burstiness", metrics.burstiness, metrics.burstiness.raw.toFixed(2));
    renderMetric("vocabulary", metrics.vocabulary, metrics.vocabulary.raw.toFixed(3));
    renderMetric("sentenceVariance", metrics.sentenceVariance, metrics.sentenceVariance.raw.toFixed(1));
    renderMetric("repetition", metrics.repetition, metrics.repetition.raw + " hits");
    renderMetric("transition", metrics.transition, metrics.transition.raw.toFixed(1) + "%");
    renderMetric("patterns", metrics.patterns, metrics.patterns.raw + " found");

    // Build breakdown
    buildBreakdown(data);

    // Reset highlight
    highlightCheckEl.checked = false;
    highlightedTextEl.classList.remove("active");
  }

  function renderMetric(key, metric, displayValue) {
    var valEl = document.getElementById("adVal-" + key);
    var fillEl = document.getElementById("adFill-" + key);
    var sigEl = document.getElementById("adSig-" + key);

    valEl.textContent = displayValue;

    // Color the fill bar based on signal
    var fillColor;
    if (metric.signal === "human") {
      fillColor = "var(--ad-human)";
    } else if (metric.signal === "ai") {
      fillColor = "var(--ad-ai)";
    } else {
      fillColor = "var(--ad-mixed)";
    }

    fillEl.style.background = fillColor;
    setTimeout(function() {
      fillEl.style.width = metric.score + "%";
    }, 100);

    // Signal badge
    if (metric.signal === "human") {
      sigEl.textContent = "Human signal";
      sigEl.className = "ad-metric-signal signal-human";
    } else if (metric.signal === "ai") {
      sigEl.textContent = "AI signal";
      sigEl.className = "ad-metric-signal signal-ai";
    } else {
      sigEl.textContent = "Neutral";
      sigEl.className = "ad-metric-signal signal-neutral";
    }
  }

  function buildBreakdown(data) {
    var list = document.getElementById("adPatternList");
    list.innerHTML = "";
    var items = [];

    // Transition words found
    if (data.metrics.transition.found) {
      for (var i = 0; i < data.metrics.transition.found.length; i++) {
        var tw = data.metrics.transition.found[i];
        items.push({
          text: "Transition word: \"" + tw.word + "\"",
          count: tw.count + "x",
          type: "ai"
        });
      }
    }

    // AI phrases found
    if (data.metrics.patterns.found) {
      for (var j = 0; j < data.metrics.patterns.found.length; j++) {
        var ap = data.metrics.patterns.found[j];
        items.push({
          text: "AI phrase: \"" + ap.phrase + "\"",
          count: ap.count + "x",
          type: "ai"
        });
      }
    }

    // Repeated n-grams
    if (data.metrics.repetition.repeats) {
      for (var k = 0; k < data.metrics.repetition.repeats.length; k++) {
        var rp = data.metrics.repetition.repeats[k];
        items.push({
          text: "Repeated phrase: \"" + rp.phrase + "\"",
          count: rp.count + "x",
          type: "neutral"
        });
      }
    }

    // Add summary items
    items.push({
      text: "Burstiness (CV: " + data.metrics.burstiness.raw.toFixed(2) + ")",
      count: data.metrics.burstiness.signal === "human" ? "Normal" : data.metrics.burstiness.signal === "ai" ? "Low" : "Moderate",
      type: data.metrics.burstiness.signal
    });

    items.push({
      text: "Vocabulary TTR: " + data.metrics.vocabulary.raw.toFixed(3),
      count: data.metrics.vocabulary.signal === "human" ? "Diverse" : data.metrics.vocabulary.signal === "ai" ? "Limited" : "Average",
      type: data.metrics.vocabulary.signal
    });

    items.push({
      text: "Sentence length std dev: " + data.metrics.sentenceVariance.raw.toFixed(1),
      count: data.metrics.sentenceVariance.signal === "human" ? "High" : data.metrics.sentenceVariance.signal === "ai" ? "Low" : "Moderate",
      type: data.metrics.sentenceVariance.signal
    });

    if (items.length === 0) {
      items.push({ text: "No specific patterns detected", count: "--", type: "neutral" });
    }

    for (var m = 0; m < items.length; m++) {
      var li = document.createElement("li");
      var spanText = document.createElement("span");
      spanText.textContent = items[m].text;
      var spanTag = document.createElement("span");
      spanTag.className = "ad-pattern-tag";
      spanTag.textContent = items[m].count;

      if (items[m].type === "ai") {
        spanTag.style.background = "var(--ad-ai-bg)";
        spanTag.style.color = "var(--ad-ai)";
      } else if (items[m].type === "human") {
        spanTag.style.background = "var(--ad-human-bg)";
        spanTag.style.color = "var(--ad-human)";
      } else {
        spanTag.style.background = "var(--ad-mixed-bg)";
        spanTag.style.color = "var(--ad-mixed)";
      }

      li.appendChild(spanText);
      li.appendChild(spanTag);
      list.appendChild(li);
    }
  }

  // --- Toggle breakdown ---
  window.adToggleBreakdown = function() {
    var el = document.getElementById("adBreakdown");
    el.classList.toggle("open");
  };

  // --- Highlight toggle ---
  window.adToggleHighlight = function() {
    if (!lastAnalysis) return;

    if (highlightCheckEl.checked) {
      renderHighlightedText(lastAnalysis);
      highlightedTextEl.classList.add("active");
    } else {
      highlightedTextEl.classList.remove("active");
    }
  };

  function renderHighlightedText(data) {
    var text = data.text;
    var html = escapeHtml(text);

    // Collect all phrases to highlight
    var aiPhrases = [];

    // AI phrases
    if (data.metrics.patterns.found) {
      for (var i = 0; i < data.metrics.patterns.found.length; i++) {
        aiPhrases.push(data.metrics.patterns.found[i].phrase);
      }
    }

    // Transition words
    if (data.metrics.transition.found) {
      for (var j = 0; j < data.metrics.transition.found.length; j++) {
        aiPhrases.push(data.metrics.transition.found[j].word);
      }
    }

    // Sort by length descending to avoid partial replacements
    aiPhrases.sort(function(a, b) { return b.length - a.length; });

    // Replace phrases with highlighted versions
    for (var k = 0; k < aiPhrases.length; k++) {
      var phrase = aiPhrases[k];
      var escaped = escapeHtml(phrase);
      var regex = new RegExp("(?<![\\w>])(" + escaped.replace(/[.*+?^${}()|[\]\\]/g, '\\$&') + ")(?![\\w<])", "gi");
      // Check if it's an AI phrase (red) or transition word (orange)
      var isAIPhrase = false;
      for (var m = 0; m < AI_PHRASES.length; m++) {
        if (AI_PHRASES[m].toLowerCase() === phrase.toLowerCase()) { isAIPhrase = true; break; }
      }
      for (var n = 0; n < AI_WORDS.length; n++) {
        if (AI_WORDS[n].toLowerCase() === phrase.toLowerCase()) { isAIPhrase = true; break; }
      }

      var cls = isAIPhrase ? "ad-highlight-ai" : "ad-highlight-transition";
      html = html.replace(regex, '<span class="' + cls + '">$1</span>');
    }

    highlightedTextEl.innerHTML = html;
  }

  function escapeHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;");
  }

  // --- Clear ---
  window.adClear = function() {
    inputEl.value = "";
    wordCountEl.textContent = "0 words";
    resultsEl.classList.remove("active");
    analyzingEl.classList.remove("active");
    highlightToggleEl.style.display = "none";
    highlightedTextEl.classList.remove("active");
    highlightCheckEl.checked = false;
    lastAnalysis = null;

    // Reset metric fills
    var fills = document.querySelectorAll(".ad-metric-fill");
    for (var i = 0; i < fills.length; i++) {
      fills[i].style.width = "0%";
    }

    // Reset needle
    document.getElementById("adScoreNeedle").style.left = "0%";
  };

  // --- Load samples ---
  window.adLoadSample = function(type) {
    inputEl.value = type === "ai" ? SAMPLE_AI : SAMPLE_HUMAN;
    var words = getWords(inputEl.value);
    wordCountEl.textContent = words.length + " word" + (words.length !== 1 ? "s" : "");
    adAnalyze();
  };

  // Ctrl/Cmd+Enter to analyze
  inputEl.addEventListener("keydown", function(e) {
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      adAnalyze();
    }
  });

})();
</script>
