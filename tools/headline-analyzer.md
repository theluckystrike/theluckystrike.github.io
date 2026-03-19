---
layout: page
title: "Free Headline Analyzer — Score Your Titles for SEO & Engagement | Zovo"
description: "Analyze your headlines for emotional impact, power words, readability, SEO value, and character length. Free headline scoring tool for bloggers, marketers, and content creators."
permalink: /tools/headline-analyzer/
keywords: "headline analyzer, title analyzer, headline score, seo title checker, blog title analyzer, headline generator, title score, headline optimizer"
date: 2026-03-19
categories: [tools]
tags: [headline, analyzer, seo, content, marketing, title, copywriting]
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
    --ha-primary: #6C5CE7;
    --ha-primary-dark: #5A4BD1;
    --ha-primary-light: #A29BFE;
    --ha-bg: #0a0a0f;
    --ha-surface: #12121a;
    --ha-surface-alt: #181824;
    --ha-border: #1e1e2e;
    --ha-border-light: #2a2a3e;
    --ha-text: #e0e0e0;
    --ha-text-muted: #8888aa;
    --ha-green: #00ff88;
    --ha-green-dark: #00cc6a;
    --ha-yellow: #ffc107;
    --ha-red: #ff4466;
    --ha-radius: 12px;
    --ha-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .ha-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ha-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .ha-wrapper * {
    box-sizing: border-box;
  }

  .ha-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .ha-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ha-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .ha-hero h1 span {
    color: var(--ha-primary);
  }

  .ha-intro {
    font-size: 1.05rem;
    color: var(--ha-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .ha-card {
    background: var(--ha-surface);
    border: 1px solid var(--ha-border);
    border-radius: var(--ha-radius);
    padding: 24px;
    box-shadow: var(--ha-shadow);
    margin-bottom: 20px;
  }

  .ha-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--ha-text-muted);
    margin: 0 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .ha-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--ha-primary);
    border-radius: 2px;
  }

  /* Input */
  .ha-input-area {
    width: 100%;
    padding: 14px 18px;
    background: var(--ha-bg);
    border: 1px solid var(--ha-border);
    border-radius: 8px;
    color: var(--ha-text);
    font-family: 'Inter', sans-serif;
    font-size: 1.1rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    resize: none;
    min-height: 56px;
  }

  .ha-input-area:focus {
    border-color: var(--ha-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .ha-input-area::placeholder {
    color: var(--ha-text-muted);
    font-style: italic;
  }

  .ha-char-count {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    color: var(--ha-text-muted);
    text-align: right;
    margin-top: 6px;
  }

  .ha-analyze-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 32px;
    background: var(--ha-primary);
    color: #fff;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s ease, transform 0.1s ease;
    margin-top: 12px;
  }

  .ha-analyze-btn:hover {
    background: var(--ha-primary-dark);
  }

  .ha-analyze-btn:active {
    transform: scale(0.97);
  }

  /* Score Gauge */
  .ha-score-section {
    display: flex;
    align-items: center;
    gap: 40px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .ha-gauge-wrap {
    position: relative;
    width: 180px;
    height: 180px;
    flex-shrink: 0;
  }

  .ha-gauge-svg {
    transform: rotate(-90deg);
  }

  .ha-gauge-bg {
    fill: none;
    stroke: var(--ha-border);
    stroke-width: 10;
  }

  .ha-gauge-fill {
    fill: none;
    stroke-width: 10;
    stroke-linecap: round;
    transition: stroke-dashoffset 0.6s ease, stroke 0.4s ease;
  }

  .ha-gauge-text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
  }

  .ha-gauge-score {
    font-family: 'JetBrains Mono', monospace;
    font-size: 2.8rem;
    font-weight: 700;
    line-height: 1;
  }

  .ha-gauge-label {
    font-size: 0.8rem;
    color: var(--ha-text-muted);
    margin-top: 4px;
  }

  .ha-score-summary {
    flex: 1;
    min-width: 280px;
  }

  .ha-score-grade {
    font-size: 1.3rem;
    font-weight: 600;
    margin-bottom: 8px;
  }

  .ha-score-desc {
    font-size: 0.95rem;
    color: var(--ha-text-muted);
    line-height: 1.6;
  }

  /* Progress Bars */
  .ha-breakdown-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 700px) {
    .ha-breakdown-grid {
      grid-template-columns: 1fr;
    }
    .ha-score-section {
      flex-direction: column;
      gap: 20px;
    }
  }

  .ha-metric {
    background: var(--ha-surface-alt);
    border-radius: 8px;
    padding: 16px;
  }

  .ha-metric-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
  }

  .ha-metric-name {
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--ha-text-muted);
  }

  .ha-metric-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    font-weight: 600;
  }

  .ha-metric-bar {
    height: 6px;
    background: var(--ha-border);
    border-radius: 3px;
    overflow: hidden;
  }

  .ha-metric-fill {
    height: 100%;
    border-radius: 3px;
    transition: width 0.5s ease, background 0.3s ease;
  }

  .ha-metric-detail {
    font-size: 0.78rem;
    color: var(--ha-text-muted);
    margin-top: 6px;
  }

  /* Type Badge */
  .ha-type-badge {
    display: inline-block;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: 600;
    background: rgba(108, 92, 231, 0.15);
    color: var(--ha-primary-light);
    border: 1px solid rgba(108, 92, 231, 0.3);
  }

  /* Word Tags */
  .ha-word-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 8px;
  }

  .ha-word-tag {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 4px;
    font-size: 0.78rem;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 500;
  }

  .ha-word-tag.power {
    background: rgba(0, 255, 136, 0.12);
    color: var(--ha-green);
    border: 1px solid rgba(0, 255, 136, 0.25);
  }

  .ha-word-tag.emotional {
    background: rgba(255, 193, 7, 0.12);
    color: var(--ha-yellow);
    border: 1px solid rgba(255, 193, 7, 0.25);
  }

  .ha-word-tag.common {
    background: rgba(136, 136, 170, 0.1);
    color: var(--ha-text-muted);
    border: 1px solid rgba(136, 136, 170, 0.2);
  }

  .ha-word-tag.uncommon {
    background: rgba(108, 92, 231, 0.12);
    color: var(--ha-primary-light);
    border: 1px solid rgba(108, 92, 231, 0.25);
  }

  /* SERP / Social Previews */
  .ha-preview-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 700px) {
    .ha-preview-grid {
      grid-template-columns: 1fr;
    }
  }

  .ha-serp-preview {
    background: #fff;
    border-radius: 8px;
    padding: 18px;
    max-width: 600px;
  }

  .ha-serp-title {
    font-size: 1.1rem;
    color: #1a0dab;
    font-family: Arial, sans-serif;
    line-height: 1.3;
    margin-bottom: 2px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .ha-serp-url {
    font-size: 0.82rem;
    color: #006621;
    font-family: Arial, sans-serif;
    margin-bottom: 4px;
  }

  .ha-serp-desc {
    font-size: 0.85rem;
    color: #545454;
    font-family: Arial, sans-serif;
    line-height: 1.45;
  }

  .ha-serp-truncated {
    font-size: 0.75rem;
    color: var(--ha-red);
    margin-top: 6px;
    font-weight: 500;
  }

  .ha-social-preview {
    background: #1c1c1c;
    border-radius: 8px;
    overflow: hidden;
    border: 1px solid #333;
  }

  .ha-social-bar {
    padding: 12px 16px;
    border-top: 1px solid #333;
  }

  .ha-social-site {
    font-size: 0.72rem;
    color: #777;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    margin-bottom: 2px;
  }

  .ha-social-title {
    font-size: 0.95rem;
    color: #e0e0e0;
    font-weight: 600;
    line-height: 1.3;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .ha-social-desc {
    font-size: 0.8rem;
    color: #999;
    margin-top: 2px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  /* Suggestions */
  .ha-suggestions-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .ha-suggestions-list li {
    padding: 10px 14px;
    border-bottom: 1px solid var(--ha-border);
    font-size: 0.9rem;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    color: var(--ha-text-muted);
  }

  .ha-suggestions-list li:last-child {
    border-bottom: none;
  }

  .ha-sug-icon {
    flex-shrink: 0;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: 700;
    margin-top: 1px;
  }

  .ha-sug-icon.warn {
    background: rgba(255, 193, 7, 0.15);
    color: var(--ha-yellow);
  }

  .ha-sug-icon.good {
    background: rgba(0, 255, 136, 0.12);
    color: var(--ha-green);
  }

  .ha-sug-icon.bad {
    background: rgba(255, 68, 102, 0.12);
    color: var(--ha-red);
  }

  /* History */
  .ha-history-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .ha-history-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 0;
    border-bottom: 1px solid var(--ha-border);
    cursor: pointer;
    transition: background 0.15s ease;
    gap: 12px;
  }

  .ha-history-item:hover {
    background: var(--ha-surface-alt);
  }

  .ha-history-item:last-child {
    border-bottom: none;
  }

  .ha-history-text {
    font-size: 0.9rem;
    color: var(--ha-text);
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    flex: 1;
  }

  .ha-history-score {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    font-weight: 600;
    flex-shrink: 0;
    padding: 2px 10px;
    border-radius: 4px;
  }

  .ha-clear-btn {
    background: none;
    border: 1px solid var(--ha-border);
    color: var(--ha-text-muted);
    padding: 6px 14px;
    border-radius: 6px;
    font-size: 0.8rem;
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .ha-clear-btn:hover {
    border-color: var(--ha-red);
    color: var(--ha-red);
  }

  /* A/B Compare */
  .ha-ab-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 700px) {
    .ha-ab-grid {
      grid-template-columns: 1fr;
    }
  }

  .ha-ab-col {
    background: var(--ha-surface-alt);
    border-radius: 8px;
    padding: 16px;
  }

  .ha-ab-label {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--ha-text-muted);
    margin-bottom: 8px;
  }

  .ha-ab-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--ha-bg);
    border: 1px solid var(--ha-border);
    border-radius: 6px;
    color: var(--ha-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s ease;
  }

  .ha-ab-input:focus {
    border-color: var(--ha-primary);
  }

  .ha-ab-input::placeholder {
    color: var(--ha-text-muted);
    font-style: italic;
  }

  .ha-ab-score-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 12px;
    padding-top: 12px;
    border-top: 1px solid var(--ha-border);
  }

  .ha-ab-score-label {
    font-size: 0.85rem;
    color: var(--ha-text-muted);
  }

  .ha-ab-score-val {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.4rem;
    font-weight: 700;
  }

  .ha-ab-winner {
    text-align: center;
    padding: 12px;
    border-radius: 8px;
    margin-top: 16px;
    font-weight: 600;
    font-size: 0.95rem;
  }

  .ha-compare-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 20px;
    background: transparent;
    color: var(--ha-primary-light);
    border: 1px solid var(--ha-primary);
    border-radius: 6px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.2s ease;
    margin-top: 12px;
  }

  .ha-compare-btn:hover {
    background: rgba(108, 92, 231, 0.1);
  }

  /* Sentiment Bar */
  .ha-sentiment-bar {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 6px;
  }

  .ha-sentiment-track {
    flex: 1;
    height: 8px;
    background: linear-gradient(to right, var(--ha-red), var(--ha-yellow), var(--ha-green));
    border-radius: 4px;
    position: relative;
  }

  .ha-sentiment-marker {
    position: absolute;
    top: -4px;
    width: 16px;
    height: 16px;
    background: #fff;
    border-radius: 50%;
    border: 2px solid var(--ha-primary);
    transform: translateX(-50%);
    transition: left 0.4s ease;
  }

  .ha-sentiment-label {
    font-size: 0.8rem;
    font-weight: 600;
    min-width: 60px;
    text-align: right;
  }

  /* Results hidden state */
  .ha-results {
    display: none;
  }

  .ha-results.visible {
    display: block;
  }

  /* Cross-links */
  .ha-crosslinks {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 12px;
    margin-top: 8px;
  }

  .ha-crosslink {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 14px 16px;
    background: var(--ha-surface-alt);
    border: 1px solid var(--ha-border);
    border-radius: 8px;
    text-decoration: none;
    color: var(--ha-text);
    font-size: 0.88rem;
    font-weight: 500;
    transition: border-color 0.2s ease, transform 0.15s ease;
  }

  .ha-crosslink:hover {
    border-color: var(--ha-primary);
    transform: translateY(-2px);
  }

  .ha-crosslink-icon {
    font-size: 1.2rem;
    flex-shrink: 0;
  }

  /* Author Box */
  .ha-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px;
    background: var(--ha-surface-alt);
    border: 1px solid var(--ha-border);
    border-radius: var(--ha-radius);
    margin-top: 24px;
  }

  .ha-author-avatar {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    background: var(--ha-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    flex-shrink: 0;
  }

  .ha-author-info h4 {
    margin: 0 0 4px;
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--ha-text);
  }

  .ha-author-info p {
    margin: 0;
    font-size: 0.82rem;
    color: var(--ha-text-muted);
    line-height: 1.5;
  }

  /* Content */
  .ha-content {
    margin-top: 48px;
  }

  .ha-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--ha-text);
    margin: 40px 0 16px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--ha-border);
  }

  .ha-content p {
    font-size: 0.98rem;
    color: var(--ha-text-muted);
    line-height: 1.75;
    margin: 0 0 16px;
  }

  .ha-content ul, .ha-content ol {
    color: var(--ha-text-muted);
    padding-left: 20px;
    margin: 0 0 16px;
    line-height: 1.75;
  }

  .ha-content li {
    margin-bottom: 6px;
    font-size: 0.95rem;
  }

  /* FAQ */
  .ha-faq {
    margin-top: 40px;
  }

  .ha-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--ha-text);
    margin: 0 0 20px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--ha-border);
  }

  .ha-faq-item {
    border-bottom: 1px solid var(--ha-border);
    padding: 16px 0;
  }

  .ha-faq-item:last-child {
    border-bottom: none;
  }

  .ha-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--ha-text);
    margin: 0 0 8px;
  }

  .ha-faq-item p {
    font-size: 0.92rem;
    color: var(--ha-text-muted);
    margin: 0;
    line-height: 1.7;
  }

  /* Footer */
  .ha-footer {
    text-align: center;
    padding: 32px 0;
    border-top: 1px solid var(--ha-border);
    margin-top: 40px;
  }

  .ha-footer p {
    color: var(--ha-text-muted);
    font-size: 0.85rem;
    margin: 0;
  }

  .ha-footer a {
    color: var(--ha-primary-light);
    text-decoration: none;
  }

  .ha-footer a:hover {
    text-decoration: underline;
  }

  .ha-last-updated {
    font-size: 0.78rem;
    color: var(--ha-text-muted);
    text-align: center;
    margin-top: 8px;
  }
</style>

<div class="ha-wrapper">

  <!-- JSON-LD -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "WebApplication",
    "name": "Free Headline Analyzer",
    "description": "Analyze your headlines for emotional impact, power words, readability, SEO value, and character length. Free headline scoring tool for bloggers, marketers, and content creators.",
    "url": "https://theluckystrike.github.io/tools/headline-analyzer/",
    "applicationCategory": "SEO Tool",
    "operatingSystem": "Any",
    "offers": {
      "@type": "Offer",
      "price": "0",
      "priceCurrency": "USD"
    },
    "author": {
      "@type": "Person",
      "name": "Michael Lip",
      "url": "https://zovo.one"
    },
    "datePublished": "2026-03-19",
    "dateModified": "2026-03-19"
  }
  </script>

  <div class="ha-hero">
    <h1>Free <span>Headline Analyzer</span></h1>
    <p class="ha-intro">Score your titles for SEO, emotional impact, and click-through potential. Get word balance breakdowns, SERP previews, and actionable suggestions to write headlines that perform.</p>
  </div>

  <!-- Input -->
  <div class="ha-card">
    <div class="ha-card-title">Enter Your Headline</div>
    <input type="text" class="ha-input-area" id="haInput" placeholder="Type or paste your headline here..." maxlength="300" autocomplete="off">
    <div class="ha-char-count"><span id="haCharCount">0</span> characters &middot; <span id="haWordCount">0</span> words</div>
    <button class="ha-analyze-btn" id="haAnalyzeBtn" onclick="haAnalyze()">Analyze Headline</button>
  </div>

  <!-- Results -->
  <div class="ha-results" id="haResults">

    <!-- Overall Score -->
    <div class="ha-card">
      <div class="ha-card-title">Overall Score</div>
      <div class="ha-score-section">
        <div class="ha-gauge-wrap">
          <svg class="ha-gauge-svg" width="180" height="180" viewBox="0 0 180 180">
            <circle class="ha-gauge-bg" cx="90" cy="90" r="75"></circle>
            <circle class="ha-gauge-fill" id="haGaugeFill" cx="90" cy="90" r="75" stroke-dasharray="471.24" stroke-dashoffset="471.24"></circle>
          </svg>
          <div class="ha-gauge-text">
            <div class="ha-gauge-score" id="haScoreNum">0</div>
            <div class="ha-gauge-label">out of 100</div>
          </div>
        </div>
        <div class="ha-score-summary">
          <div class="ha-score-grade" id="haGrade">Enter a headline to begin</div>
          <div class="ha-score-desc" id="haGradeDesc"></div>
          <div style="margin-top: 12px;">
            <span class="ha-metric-name" style="margin-right: 8px;">Headline Type:</span>
            <span class="ha-type-badge" id="haTypeBadge">--</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Category Breakdown -->
    <div class="ha-card">
      <div class="ha-card-title">Category Breakdown</div>
      <div class="ha-breakdown-grid">
        <!-- Word Balance -->
        <div class="ha-metric">
          <div class="ha-metric-header">
            <span class="ha-metric-name">Word Balance</span>
            <span class="ha-metric-value" id="haWordBalVal">--</span>
          </div>
          <div class="ha-metric-bar"><div class="ha-metric-fill" id="haWordBalBar" style="width: 0%;"></div></div>
          <div class="ha-metric-detail" id="haWordBalDetail"></div>
        </div>
        <!-- Character Count -->
        <div class="ha-metric">
          <div class="ha-metric-header">
            <span class="ha-metric-name">Character Length</span>
            <span class="ha-metric-value" id="haCharLenVal">--</span>
          </div>
          <div class="ha-metric-bar"><div class="ha-metric-fill" id="haCharLenBar" style="width: 0%;"></div></div>
          <div class="ha-metric-detail" id="haCharLenDetail"></div>
        </div>
        <!-- Word Count -->
        <div class="ha-metric">
          <div class="ha-metric-header">
            <span class="ha-metric-name">Word Count</span>
            <span class="ha-metric-value" id="haWordCntVal">--</span>
          </div>
          <div class="ha-metric-bar"><div class="ha-metric-fill" id="haWordCntBar" style="width: 0%;"></div></div>
          <div class="ha-metric-detail" id="haWordCntDetail"></div>
        </div>
        <!-- Sentiment -->
        <div class="ha-metric">
          <div class="ha-metric-header">
            <span class="ha-metric-name">Sentiment</span>
            <span class="ha-metric-value" id="haSentimentVal">--</span>
          </div>
          <div class="ha-sentiment-bar">
            <span style="font-size:0.72rem; color: var(--ha-red);">Neg</span>
            <div class="ha-sentiment-track">
              <div class="ha-sentiment-marker" id="haSentimentMarker" style="left: 50%;"></div>
            </div>
            <span style="font-size:0.72rem; color: var(--ha-green);">Pos</span>
          </div>
          <div class="ha-metric-detail" id="haSentimentDetail"></div>
        </div>
        <!-- Reading Level -->
        <div class="ha-metric">
          <div class="ha-metric-header">
            <span class="ha-metric-name">Reading Level</span>
            <span class="ha-metric-value" id="haReadLevelVal">--</span>
          </div>
          <div class="ha-metric-bar"><div class="ha-metric-fill" id="haReadLevelBar" style="width: 0%;"></div></div>
          <div class="ha-metric-detail" id="haReadLevelDetail"></div>
        </div>
        <!-- Power / Emotional -->
        <div class="ha-metric">
          <div class="ha-metric-header">
            <span class="ha-metric-name">Power + Emotional Words</span>
            <span class="ha-metric-value" id="haPowerEmotVal">--</span>
          </div>
          <div class="ha-metric-bar"><div class="ha-metric-fill" id="haPowerEmotBar" style="width: 0%;"></div></div>
          <div class="ha-metric-detail" id="haPowerEmotDetail"></div>
        </div>
      </div>
    </div>

    <!-- Detected Words -->
    <div class="ha-card">
      <div class="ha-card-title">Word Classification</div>
      <div style="margin-bottom: 12px;">
        <span class="ha-metric-name">Power Words</span>
        <div class="ha-word-tags" id="haPowerTags"><span class="ha-metric-detail">None detected</span></div>
      </div>
      <div style="margin-bottom: 12px;">
        <span class="ha-metric-name">Emotional Words</span>
        <div class="ha-word-tags" id="haEmotionalTags"><span class="ha-metric-detail">None detected</span></div>
      </div>
      <div style="margin-bottom: 12px;">
        <span class="ha-metric-name">Uncommon Words</span>
        <div class="ha-word-tags" id="haUncommonTags"><span class="ha-metric-detail">None detected</span></div>
      </div>
      <div>
        <span class="ha-metric-name">Common Words</span>
        <div class="ha-word-tags" id="haCommonTags"><span class="ha-metric-detail">None detected</span></div>
      </div>
    </div>

    <!-- Previews -->
    <div class="ha-card">
      <div class="ha-card-title">Search &amp; Social Previews</div>
      <div class="ha-preview-grid">
        <div>
          <div class="ha-metric-name" style="margin-bottom: 8px;">Google SERP Preview</div>
          <div class="ha-serp-preview">
            <div class="ha-serp-title" id="haSerpTitle">Your Headline Here</div>
            <div class="ha-serp-url">https://example.com/your-page</div>
            <div class="ha-serp-desc">Your meta description will appear here. Google typically displays around 155-160 characters for the description snippet in search results.</div>
          </div>
          <div class="ha-serp-truncated" id="haSerpWarn" style="display: none;"></div>
        </div>
        <div>
          <div class="ha-metric-name" style="margin-bottom: 8px;">Social Media Preview</div>
          <div class="ha-social-preview">
            <div style="height: 140px; background: linear-gradient(135deg, var(--ha-surface-alt), var(--ha-border)); display:flex; align-items:center; justify-content:center;">
              <span style="color: var(--ha-text-muted); font-size: 0.85rem;">Featured Image Area</span>
            </div>
            <div class="ha-social-bar">
              <div class="ha-social-site">example.com</div>
              <div class="ha-social-title" id="haSocialTitle">Your Headline Here</div>
              <div class="ha-social-desc">Your meta description appears here in social shares</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Suggestions -->
    <div class="ha-card">
      <div class="ha-card-title">Improvement Suggestions</div>
      <ul class="ha-suggestions-list" id="haSuggestions">
        <li><span class="ha-metric-detail">Analyze a headline to get suggestions</span></li>
      </ul>
    </div>

    <!-- History -->
    <div class="ha-card">
      <div class="ha-card-title" style="justify-content: space-between;">
        <span style="display:flex; align-items:center; gap:8px;"><span style="display:inline-block; width:3px; height:14px; background:var(--ha-primary); border-radius:2px;"></span>Headline History</span>
        <button class="ha-clear-btn" onclick="haClearHistory()">Clear</button>
      </div>
      <ul class="ha-history-list" id="haHistoryList">
        <li style="padding: 10px 0;"><span class="ha-metric-detail">No headlines analyzed yet</span></li>
      </ul>
    </div>

    <!-- A/B Comparison -->
    <div class="ha-card">
      <div class="ha-card-title">A/B Headline Comparison</div>
      <div class="ha-ab-grid">
        <div class="ha-ab-col">
          <div class="ha-ab-label">Headline A</div>
          <input type="text" class="ha-ab-input" id="haAbA" placeholder="Enter first headline..." autocomplete="off">
          <div class="ha-ab-score-row">
            <span class="ha-ab-score-label">Score</span>
            <span class="ha-ab-score-val" id="haAbScoreA" style="color: var(--ha-text-muted);">--</span>
          </div>
        </div>
        <div class="ha-ab-col">
          <div class="ha-ab-label">Headline B</div>
          <input type="text" class="ha-ab-input" id="haAbB" placeholder="Enter second headline..." autocomplete="off">
          <div class="ha-ab-score-row">
            <span class="ha-ab-score-label">Score</span>
            <span class="ha-ab-score-val" id="haAbScoreB" style="color: var(--ha-text-muted);">--</span>
          </div>
        </div>
      </div>
      <div style="text-align: center;">
        <button class="ha-compare-btn" onclick="haCompareAB()">Compare Headlines</button>
      </div>
      <div class="ha-ab-winner" id="haAbWinner" style="display: none;"></div>
    </div>

  </div>

  <!-- Cross-links -->
  <div class="ha-card" style="margin-top: 24px;">
    <div class="ha-card-title">Related Tools</div>
    <div class="ha-crosslinks">
      <a href="/tools/ai-detector/" class="ha-crosslink">
        <span class="ha-crosslink-icon">&#129302;</span> AI Content Detector
      </a>
      <a href="/tools/meta-tag-generator/" class="ha-crosslink">
        <span class="ha-crosslink-icon">&#128196;</span> Meta Tag Generator
      </a>
      <a href="/tools/json-formatter/" class="ha-crosslink">
        <span class="ha-crosslink-icon">&#128230;</span> JSON Formatter
      </a>
      <a href="/tools/web-scraper/" class="ha-crosslink">
        <span class="ha-crosslink-icon">&#127760;</span> Web Scraper
      </a>
    </div>
  </div>

  <!-- E-E-A-T Author Box -->
  <div class="ha-author-box">
    <div class="ha-author-avatar">ML</div>
    <div class="ha-author-info">
      <h4>Michael Lip</h4>
      <p>SEO tools developer and content strategist building free, privacy-first web tools at <a href="https://zovo.one" style="color: var(--ha-primary-light); text-decoration: none;">zovo.one</a>. Focused on helping creators write better content through data-driven analysis.</p>
    </div>
  </div>

  <div class="ha-last-updated">Last updated: March 19, 2026</div>

  <!-- SEO Content -->
  <div class="ha-content">

<h2>What Is a Headline Analyzer</h2>

<p>A headline analyzer is a tool that evaluates the quality of a title or headline by scoring it against known engagement factors. It breaks your headline down into categories like word balance, emotional resonance, character length, and readability. The goal is to help you write titles that attract clicks, rank well in search engines, and accurately represent your content.</p>

<p>Most headline analyzers work by comparing your headline against databases of words known to trigger engagement. Power words like "proven" and "free" tend to increase click-through rates. Emotional words like "surprising" or "devastating" create curiosity. The balance between common, uncommon, emotional, and power words determines how a headline lands with readers.</p>

<p>This tool runs entirely in your browser. No data is sent to any server, no accounts are required, and your headlines stay private on your device.</p>

<h2>Why Headlines Matter for SEO</h2>

<p>Search engines use your page title (the H1 or title tag) as a primary ranking signal. Google displays it as the clickable blue link in search results. A well-crafted headline directly influences two things: whether Google considers your page relevant to a search query, and whether users decide to click on your result instead of someone else's.</p>

<p>Click-through rate (CTR) is an indirect ranking factor. If your page consistently gets more clicks than competing results at the same position, Google interprets that as a signal of quality and relevance. Over time, this can push your page higher in results. The opposite is also true: a boring or confusing title that nobody clicks will slowly lose ranking position regardless of how good the content behind it may be.</p>

<p>Google truncates titles in search results at roughly 580 pixels, which translates to about 50-60 characters depending on letter width. If your headline exceeds that limit, Google will cut it off with an ellipsis. Key words at the end get lost. This tool shows you exactly how your headline will appear in search results so you can avoid truncation.</p>

<h2>Anatomy of a High-Performing Headline</h2>

<p>Research from headline databases consistently shows patterns in titles that generate above-average engagement. The best headlines tend to share several characteristics.</p>

<p>They use a mix of word types. A headline made entirely of common words (articles, prepositions) reads as generic. A headline packed with nothing but power words reads as spam. The sweet spot is roughly 20-30% common words, 10-20% uncommon words, 10-15% emotional words, and at least one power word.</p>

<p>They match a recognizable format. List posts ("7 Ways to..."), how-to headlines ("How to Build a..."), and question headlines ("What Makes a Good...") outperform vague statements because they set clear expectations about the content. Readers know what they will get before they click.</p>

<p>They trigger an emotional response. This does not mean every headline should be sensational. A headline about retirement planning can evoke confidence or security. A headline about fitness can evoke determination. The emotion should match your topic and audience. What matters is that the headline makes the reader feel something rather than nothing.</p>

<p>They keep readability accessible. Headlines written at a 6th to 8th grade reading level reach the widest audience. Complex vocabulary and long words reduce comprehension speed. Readers scanning search results or social feeds spend fractions of a second on each title. If your headline requires mental effort to parse, they move on.</p>

<h2>Optimal Headline Length</h2>

<p>The ideal headline length depends on where it will appear. For Google search results, 50-60 characters prevents truncation. For Twitter/X, shorter headlines leave room for commentary and links. For Facebook, headlines up to 80 characters perform well because the platform displays more text.</p>

<p>Word count matters independently of character count. Headlines with 6-12 words tend to score highest in engagement studies. Fewer than 6 words often lack enough specificity to set expectations. More than 12 words start to lose focus and become harder to scan.</p>

<p>If you need to choose between character optimization for Google and word count optimization for engagement, prioritize your primary distribution channel. A blog post that gets most traffic from organic search should target the 50-60 character range. A post distributed primarily through social media has more flexibility.</p>

<h2>Power Words That Drive Clicks</h2>

<p>Power words are terms proven to increase click-through rates by triggering urgency, curiosity, or desire. They work because they make an implicit promise to the reader: "free" promises no cost, "proven" promises reliability, "secret" promises exclusive knowledge.</p>

<p>Categories of power words include urgency words (limited, deadline, hurry, now), exclusivity words (secret, exclusive, insider, private), trust words (proven, guaranteed, research-backed, certified), curiosity words (surprising, unusual, bizarre, unexpected), and value words (free, bonus, essential, ultimate).</p>

<p>Using one or two power words per headline is optimal. Overloading a headline with power words makes it read like clickbait, which can increase bounce rates even if it improves initial clicks. The best approach is to use power words that accurately describe your content. If your article genuinely reveals something surprising, use "surprising." If it does not, find a power word that fits what you actually deliver.</p>

  </div>

  <!-- FAQ -->
  <div class="ha-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="ha-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How is the headline score calculated?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The score is a weighted composite of several factors: word balance (the ratio of common, uncommon, emotional, and power words), character length relative to Google's display limit, total word count, sentiment strength, reading grade level, and headline type. Each factor is scored individually and then combined into an overall score from 0 to 100. Headlines scoring above 70 are considered strong performers.</p>
      </div>
    </div>

    <div class="ha-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is a good headline score?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Scores above 70 indicate a well-optimized headline with good word balance, appropriate length, and emotional appeal. Scores between 40 and 70 suggest room for improvement in one or more categories. Scores below 40 typically mean the headline is too short, too long, lacks emotional or power words, or uses an unengaging structure. Most first-draft headlines score between 40 and 60, so do not be discouraged by an initial result.</p>
      </div>
    </div>

    <div class="ha-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What are power words and emotional words?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Power words are terms that trigger urgency, curiosity, or desire in readers. Examples include "free," "proven," "secret," "ultimate," and "guaranteed." Emotional words evoke feelings like surprise, fear, joy, or anger. Examples include "amazing," "terrifying," "heartbreaking," and "hilarious." Both types increase click-through rates when used appropriately. This tool detects these words in your headline and highlights them.</p>
      </div>
    </div>

    <div class="ha-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why does character count matter for headlines?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Google truncates title tags in search results at approximately 580 pixels wide, which translates to roughly 50-60 characters depending on letter widths. If your headline exceeds this limit, it gets cut off with an ellipsis, and readers miss the ending. Social media platforms also have display limits. Staying within the optimal range ensures your full headline is visible across all platforms.</p>
      </div>
    </div>

    <div class="ha-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does this tool save my headlines?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The headline history feature stores your last 10 analyzed headlines in your browser's local storage for convenience. No data is sent to any server. You can clear the history at any time using the Clear button. If you use private or incognito browsing, the history will be automatically erased when you close the window.</p>
      </div>
    </div>

    <div class="ha-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use this for email subject lines?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The scoring factors that make a headline effective for blog posts and search results also apply to email subject lines. Word balance, emotional impact, and readability are relevant across all formats. The main difference is length: email subject lines perform best at 30-50 characters since many email clients truncate earlier than search engines do. Use the character count metric as your primary guide when optimizing for email.</p>
      </div>
    </div>

  </div>

  <footer class="ha-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  // --- Word Lists ---
  var POWER_WORDS = [
    "free","proven","guaranteed","ultimate","instant","exclusive","secret","limited",
    "breakthrough","powerful","essential","shocking","remarkable","incredible","revolutionary",
    "unleash","transform","discover","master","dominate","boost","skyrocket","hack",
    "crucial","vital","critical","urgent","deadline","hurry","now","today","fast",
    "effortless","simple","easy","quick","bonus","premium","elite","insider",
    "certified","official","authentic","tested","research","backed","definitive",
    "complete","comprehensive","step-by-step","blueprint","formula","framework",
    "massive","enormous","explosive","profitable","lucrative","valuable","priceless"
  ];

  var EMOTIONAL_WORDS = [
    "amazing","beautiful","terrifying","heartbreaking","inspiring","hilarious","brilliant",
    "devastating","triumphant","surprising","stunning","breathtaking","magnificent",
    "horrible","terrible","wonderful","extraordinary","phenomenal","spectacular","ridiculous",
    "outrageous","unbelievable","jaw-dropping","mind-blowing","life-changing","gut-wrenching",
    "soul-crushing","eye-opening","awe-inspiring","heart-warming","nerve-wracking",
    "love","hate","fear","joy","anger","anxiety","hope","despair","pride","shame",
    "exciting","alarming","disturbing","enchanting","captivating","haunting","moving",
    "uplifting","tragic","glorious","painful","delightful","dreadful","thrilling",
    "astonishing","bizarre","crazy","epic","genius","legendary","magical","nightmare",
    "perfect","worst","best"
  ];

  var COMMON_WORDS = [
    "the","a","an","of","in","to","for","with","on","at","is","are","was","were",
    "be","been","being","have","has","had","do","does","did","will","would","shall",
    "should","may","might","can","could","must","and","but","or","nor","not","no",
    "so","yet","both","either","neither","each","every","all","any","few","more",
    "most","other","some","such","than","too","very","just","also","about","above",
    "after","again","against","as","before","below","between","by","down","during",
    "from","further","here","how","if","into","it","its","itself","off","once",
    "only","out","over","own","same","that","their","them","then","there","these",
    "this","those","through","under","until","up","upon","what","when","where",
    "which","while","who","whom","why","your","you","we","they","i","my","me","he",
    "she","his","her","our","us"
  ];

  var POSITIVE_WORDS = [
    "amazing","awesome","beautiful","best","brilliant","captivating","delightful",
    "enchanting","exciting","extraordinary","free","genius","glorious","good","great",
    "heart-warming","hilarious","hope","incredible","inspiring","joy","legendary",
    "life-changing","love","magical","magnificent","marvelous","moving","outstanding",
    "perfect","phenomenal","powerful","premium","pride","proven","remarkable",
    "spectacular","stunning","successful","superior","thrilling","triumphant","ultimate",
    "unbelievable","uplifting","valuable","wonderful","breakthrough","essential",
    "guaranteed","profitable","easy","simple","fast","quick","effortless","boost",
    "improve","grow","gain","win","achieve","master","transform","discover"
  ];

  var NEGATIVE_WORDS = [
    "alarming","anger","anxiety","bizarre","crazy","devastating","disturbing","dreadful",
    "fear","gut-wrenching","hate","haunting","heartbreaking","horrible","jaw-dropping",
    "nerve-wracking","nightmare","outrageous","painful","ridiculous","shame","shocking",
    "soul-crushing","terrible","terrifying","tragic","worst","dangerous","deadly",
    "toxic","fail","failure","mistake","error","wrong","bad","ugly","awful",
    "disgusting","despair","catastrophe","crisis","risk","threat","warning","scam",
    "fraud","lies","never","stop","avoid","kill","destroy","ruin","waste","lose","lost"
  ];

  var headlineHistory = [];

  try {
    var stored = localStorage.getItem("ha_history");
    if (stored) headlineHistory = JSON.parse(stored);
  } catch(e) {}

  // --- Helpers ---
  function getWords(text) {
    return text.trim().split(/\s+/).filter(function(w) { return w.length > 0; });
  }

  function normalize(w) {
    return w.toLowerCase().replace(/[^a-z0-9\-]/g, "");
  }

  function countSyllables(word) {
    word = word.toLowerCase().replace(/[^a-z]/g, "");
    if (word.length <= 3) return 1;
    word = word.replace(/(?:[^laeiouy]es|ed|[^laeiouy]e)$/, "");
    word = word.replace(/^y/, "");
    var m = word.match(/[aeiouy]{1,2}/g);
    return m ? m.length : 1;
  }

  function classifyWords(words) {
    var result = { common: [], uncommon: [], emotional: [], power: [] };
    for (var i = 0; i < words.length; i++) {
      var w = normalize(words[i]);
      if (!w) continue;
      if (POWER_WORDS.indexOf(w) !== -1) {
        result.power.push(words[i]);
      } else if (EMOTIONAL_WORDS.indexOf(w) !== -1) {
        result.emotional.push(words[i]);
      } else if (COMMON_WORDS.indexOf(w) !== -1) {
        result.common.push(words[i]);
      } else {
        result.uncommon.push(words[i]);
      }
    }
    return result;
  }

  function detectType(text) {
    var lower = text.toLowerCase().trim();
    if (/^\d+\s/.test(lower) || /\btop\s+\d+\b/.test(lower)) return "List";
    if (/^how\s+to\b/.test(lower) || /^how\s+\w+\s+can\b/.test(lower)) return "How-to";
    if (/\?$/.test(text.trim()) || /^(what|why|when|where|who|which|how|is|are|do|does|can|should|will|would)\b/.test(lower)) return "Question";
    if (/^(get|stop|start|try|use|make|build|create|learn|find|grab|check|download|read|watch)\b/.test(lower)) return "Command";
    return "Statement";
  }

  function calcSentiment(words) {
    var pos = 0, neg = 0;
    for (var i = 0; i < words.length; i++) {
      var w = normalize(words[i]);
      if (POSITIVE_WORDS.indexOf(w) !== -1) pos++;
      if (NEGATIVE_WORDS.indexOf(w) !== -1) neg++;
    }
    var total = pos + neg;
    if (total === 0) return { label: "Neutral", strength: 0, pos: 0, neg: 0, pct: 50 };
    var ratio = (pos - neg) / total;
    var strength = Math.min(Math.abs(pos - neg), 3);
    var label = ratio > 0.2 ? "Positive" : (ratio < -0.2 ? "Negative" : "Neutral");
    var pct = 50 + (ratio * 50);
    return { label: label, strength: strength, pos: pos, neg: neg, pct: Math.max(5, Math.min(95, pct)) };
  }

  function calcReadingLevel(text) {
    var words = getWords(text);
    if (words.length === 0) return 0;
    var sentences = text.split(/[.!?]+/).filter(function(s) { return s.trim().length > 0; });
    if (sentences.length === 0) sentences = [text];
    var totalSyllables = 0;
    for (var i = 0; i < words.length; i++) {
      totalSyllables += countSyllables(words[i]);
    }
    var grade = 0.39 * (words.length / sentences.length) + 11.8 * (totalSyllables / words.length) - 15.59;
    return Math.max(1, Math.min(16, Math.round(grade)));
  }

  function scoreHeadline(text) {
    var words = getWords(text);
    var charCount = text.trim().length;
    var wordCount = words.length;
    var classified = classifyWords(words);
    var type = detectType(text);
    var sentiment = calcSentiment(words);
    var readLevel = calcReadingLevel(text);

    if (wordCount === 0) return null;

    var totalClassified = classified.common.length + classified.uncommon.length + classified.emotional.length + classified.power.length;
    var commonPct = totalClassified > 0 ? classified.common.length / totalClassified : 0;
    var uncommonPct = totalClassified > 0 ? classified.uncommon.length / totalClassified : 0;
    var emotionalPct = totalClassified > 0 ? classified.emotional.length / totalClassified : 0;
    var powerCount = classified.power.length;

    // --- Sub-scores (each 0-100) ---

    // Word Balance Score (25 weight)
    var balScore = 0;
    // Common: 20-30% ideal
    if (commonPct >= 0.2 && commonPct <= 0.3) balScore += 25;
    else if (commonPct >= 0.1 && commonPct <= 0.4) balScore += 15;
    else balScore += 5;
    // Uncommon: 10-20% ideal
    if (uncommonPct >= 0.1 && uncommonPct <= 0.2) balScore += 25;
    else if (uncommonPct >= 0.05 && uncommonPct <= 0.35) balScore += 15;
    else if (uncommonPct > 0) balScore += 8;
    // Emotional: 10-15% ideal
    if (emotionalPct >= 0.1 && emotionalPct <= 0.15) balScore += 25;
    else if (emotionalPct >= 0.05 && emotionalPct <= 0.25) balScore += 18;
    else if (emotionalPct > 0) balScore += 10;
    // Power: 1+ required
    if (powerCount >= 2) balScore += 25;
    else if (powerCount >= 1) balScore += 20;
    else balScore += 0;

    // Character Length Score (20 weight)
    var charScore = 0;
    if (charCount >= 50 && charCount <= 60) charScore = 100;
    else if (charCount >= 40 && charCount <= 70) charScore = 75;
    else if (charCount >= 30 && charCount <= 80) charScore = 50;
    else if (charCount >= 20 && charCount <= 100) charScore = 30;
    else charScore = 10;

    // Word Count Score (15 weight)
    var wordScore = 0;
    if (wordCount >= 6 && wordCount <= 12) wordScore = 100;
    else if (wordCount >= 4 && wordCount <= 14) wordScore = 70;
    else if (wordCount >= 3 && wordCount <= 16) wordScore = 40;
    else wordScore = 15;

    // Sentiment Score (15 weight) -- having some sentiment is better than none
    var sentScore = 0;
    if (sentiment.label === "Positive" && sentiment.strength >= 1) sentScore = 90;
    else if (sentiment.label === "Negative" && sentiment.strength >= 1) sentScore = 75;
    else if (sentiment.label === "Positive" || sentiment.label === "Negative") sentScore = 60;
    else sentScore = 30;

    // Reading Level Score (10 weight) -- 6-8 grade is ideal
    var readScore = 0;
    if (readLevel >= 6 && readLevel <= 8) readScore = 100;
    else if (readLevel >= 4 && readLevel <= 10) readScore = 70;
    else if (readLevel >= 2 && readLevel <= 12) readScore = 45;
    else readScore = 20;

    // Type Score (15 weight) -- How-to and List tend to perform best
    var typeScore = 0;
    if (type === "How-to") typeScore = 95;
    else if (type === "List") typeScore = 90;
    else if (type === "Question") typeScore = 80;
    else if (type === "Command") typeScore = 75;
    else typeScore = 50;

    var overall = Math.round(
      (balScore * 0.25) +
      (charScore * 0.20) +
      (wordScore * 0.15) +
      (sentScore * 0.15) +
      (readScore * 0.10) +
      (typeScore * 0.15)
    );

    overall = Math.max(0, Math.min(100, overall));

    return {
      overall: overall,
      charCount: charCount,
      wordCount: wordCount,
      classified: classified,
      commonPct: commonPct,
      uncommonPct: uncommonPct,
      emotionalPct: emotionalPct,
      powerCount: powerCount,
      type: type,
      sentiment: sentiment,
      readLevel: readLevel,
      balScore: balScore,
      charScore: charScore,
      wordScore: wordScore,
      sentScore: sentScore,
      readScore: readScore,
      typeScore: typeScore
    };
  }

  function getScoreColor(score) {
    if (score >= 70) return "var(--ha-green)";
    if (score >= 40) return "var(--ha-yellow)";
    return "var(--ha-red)";
  }

  function getGrade(score) {
    if (score >= 80) return { grade: "Excellent", desc: "This headline has strong word balance, appropriate length, and good emotional resonance. It should perform well in search results and social media." };
    if (score >= 70) return { grade: "Good", desc: "A solid headline that hits most engagement factors. Small adjustments to word choice or length could push it higher." };
    if (score >= 55) return { grade: "Needs Work", desc: "This headline has potential but is missing key elements. Review the suggestions below for specific improvements." };
    if (score >= 40) return { grade: "Weak", desc: "Several factors are pulling this headline down. Focus on the lowest-scoring categories first." };
    return { grade: "Poor", desc: "This headline needs significant revision. Consider changing the structure, adding power or emotional words, and adjusting the length." };
  }

  function setBar(id, pct, color) {
    var el = document.getElementById(id);
    el.style.width = Math.max(2, Math.min(100, pct)) + "%";
    el.style.background = color || "var(--ha-primary)";
  }

  function renderTags(containerId, words, cls) {
    var container = document.getElementById(containerId);
    if (words.length === 0) {
      container.innerHTML = '<span class="ha-metric-detail">None detected</span>';
      return;
    }
    var html = "";
    for (var i = 0; i < words.length; i++) {
      html += '<span class="ha-word-tag ' + cls + '">' + words[i] + '</span>';
    }
    container.innerHTML = html;
  }

  function buildSuggestions(data) {
    var sugs = [];

    if (data.charCount < 40) {
      sugs.push({ type: "warn", text: "Your headline is short at " + data.charCount + " characters. Aim for 50-60 characters for optimal Google SERP display." });
    } else if (data.charCount > 60) {
      sugs.push({ type: "bad", text: "At " + data.charCount + " characters, your headline will be truncated in Google search results. Trim it to under 60 characters." });
    } else {
      sugs.push({ type: "good", text: "Character count (" + data.charCount + ") is in the optimal range for Google search results." });
    }

    if (data.wordCount < 6) {
      sugs.push({ type: "warn", text: "With only " + data.wordCount + " words, your headline may lack enough detail to set reader expectations. Aim for 6-12 words." });
    } else if (data.wordCount > 12) {
      sugs.push({ type: "warn", text: "At " + data.wordCount + " words, your headline is getting long. Consider trimming to 12 or fewer words for better scannability." });
    } else {
      sugs.push({ type: "good", text: "Word count (" + data.wordCount + ") is in the ideal range of 6-12." });
    }

    if (data.powerCount === 0) {
      sugs.push({ type: "bad", text: "No power words detected. Add at least one (e.g., free, proven, essential, ultimate) to increase click appeal." });
    } else {
      sugs.push({ type: "good", text: data.powerCount + " power word" + (data.powerCount > 1 ? "s" : "") + " detected. Power words help drive clicks." });
    }

    if (data.emotionalPct === 0) {
      sugs.push({ type: "warn", text: "No emotional words found. Adding an emotional word can increase engagement by triggering a reader response." });
    } else {
      sugs.push({ type: "good", text: "Emotional words detected (" + Math.round(data.emotionalPct * 100) + "% of words). This adds resonance to your headline." });
    }

    if (data.readLevel > 10) {
      sugs.push({ type: "warn", text: "Reading level is grade " + data.readLevel + ". Simplify vocabulary to reach a wider audience (target grade 6-8)." });
    } else if (data.readLevel < 4) {
      sugs.push({ type: "warn", text: "Reading level is very low (grade " + data.readLevel + "). Consider using slightly more descriptive language." });
    } else {
      sugs.push({ type: "good", text: "Reading level (grade " + data.readLevel + ") is accessible to a broad audience." });
    }

    if (data.type === "Statement") {
      sugs.push({ type: "warn", text: "This reads as a plain statement. Consider restructuring as a how-to, list, question, or command for higher engagement." });
    } else {
      sugs.push({ type: "good", text: "\"" + data.type + "\" headlines tend to perform well in terms of CTR and sharing." });
    }

    if (data.commonPct > 0.5) {
      sugs.push({ type: "warn", text: "Over half your words are common (articles, prepositions). Replace some with more specific or descriptive terms." });
    }

    if (data.uncommonPct < 0.05 && data.wordCount >= 4) {
      sugs.push({ type: "warn", text: "Very few uncommon words detected. Adding specific, descriptive terms makes your headline more distinctive." });
    }

    return sugs;
  }

  // --- Main Analyze ---
  window.haAnalyze = function() {
    var input = document.getElementById("haInput");
    var text = input.value.trim();
    if (!text) return;

    var data = scoreHeadline(text);
    if (!data) return;

    // Show results
    document.getElementById("haResults").classList.add("visible");

    // Animate gauge
    var circumference = 2 * Math.PI * 75;
    var offset = circumference - (data.overall / 100) * circumference;
    var color = getScoreColor(data.overall);
    var gauge = document.getElementById("haGaugeFill");
    gauge.style.stroke = color;
    gauge.style.strokeDashoffset = offset;

    // Score number
    var scoreEl = document.getElementById("haScoreNum");
    scoreEl.style.color = color;
    scoreEl.textContent = data.overall;

    // Grade
    var gradeInfo = getGrade(data.overall);
    var gradeEl = document.getElementById("haGrade");
    gradeEl.textContent = gradeInfo.grade;
    gradeEl.style.color = color;
    document.getElementById("haGradeDesc").textContent = gradeInfo.desc;

    // Type badge
    document.getElementById("haTypeBadge").textContent = data.type;

    // Word Balance
    document.getElementById("haWordBalVal").textContent = data.balScore + "/100";
    document.getElementById("haWordBalVal").style.color = getScoreColor(data.balScore);
    setBar("haWordBalBar", data.balScore, getScoreColor(data.balScore));
    document.getElementById("haWordBalDetail").textContent =
      "Common: " + Math.round(data.commonPct * 100) + "% | Uncommon: " + Math.round(data.uncommonPct * 100) + "% | Emotional: " + Math.round(data.emotionalPct * 100) + "% | Power: " + data.powerCount;

    // Character Length
    document.getElementById("haCharLenVal").textContent = data.charCount + " chars";
    document.getElementById("haCharLenVal").style.color = getScoreColor(data.charScore);
    setBar("haCharLenBar", data.charScore, getScoreColor(data.charScore));
    var charStatus = data.charCount >= 50 && data.charCount <= 60 ? "Optimal for Google" : (data.charCount > 60 ? "Will be truncated in Google" : "Below optimal length");
    document.getElementById("haCharLenDetail").textContent = charStatus + " (ideal: 50-60)";

    // Word Count
    document.getElementById("haWordCntVal").textContent = data.wordCount + " words";
    document.getElementById("haWordCntVal").style.color = getScoreColor(data.wordScore);
    setBar("haWordCntBar", data.wordScore, getScoreColor(data.wordScore));
    var wcStatus = data.wordCount >= 6 && data.wordCount <= 12 ? "Optimal range" : (data.wordCount < 6 ? "Below optimal" : "Above optimal");
    document.getElementById("haWordCntDetail").textContent = wcStatus + " (ideal: 6-12 words)";

    // Sentiment
    document.getElementById("haSentimentVal").textContent = data.sentiment.label;
    document.getElementById("haSentimentVal").style.color =
      data.sentiment.label === "Positive" ? "var(--ha-green)" : (data.sentiment.label === "Negative" ? "var(--ha-red)" : "var(--ha-yellow)");
    document.getElementById("haSentimentMarker").style.left = data.sentiment.pct + "%";
    document.getElementById("haSentimentDetail").textContent =
      "Positive words: " + data.sentiment.pos + " | Negative words: " + data.sentiment.neg;

    // Reading Level
    document.getElementById("haReadLevelVal").textContent = "Grade " + data.readLevel;
    document.getElementById("haReadLevelVal").style.color = getScoreColor(data.readScore);
    setBar("haReadLevelBar", data.readScore, getScoreColor(data.readScore));
    var rlStatus = data.readLevel >= 6 && data.readLevel <= 8 ? "Ideal" : (data.readLevel < 6 ? "Very easy" : "Above target");
    document.getElementById("haReadLevelDetail").textContent = rlStatus + " (target: grade 6-8)";

    // Power + Emotional
    var peTotal = data.powerCount + data.classified.emotional.length;
    var peScore = Math.min(100, peTotal * 30);
    document.getElementById("haPowerEmotVal").textContent = peTotal + " found";
    document.getElementById("haPowerEmotVal").style.color = getScoreColor(peScore);
    setBar("haPowerEmotBar", peScore, getScoreColor(peScore));
    document.getElementById("haPowerEmotDetail").textContent =
      data.powerCount + " power word" + (data.powerCount !== 1 ? "s" : "") + ", " +
      data.classified.emotional.length + " emotional word" + (data.classified.emotional.length !== 1 ? "s" : "");

    // Word tags
    renderTags("haPowerTags", data.classified.power, "power");
    renderTags("haEmotionalTags", data.classified.emotional, "emotional");
    renderTags("haUncommonTags", data.classified.uncommon, "uncommon");
    renderTags("haCommonTags", data.classified.common, "common");

    // SERP Preview
    var serpTitle = text.length > 60 ? text.substring(0, 57) + "..." : text;
    document.getElementById("haSerpTitle").textContent = serpTitle;
    document.getElementById("haSocialTitle").textContent = text;

    var serpWarn = document.getElementById("haSerpWarn");
    if (text.length > 60) {
      serpWarn.style.display = "block";
      serpWarn.textContent = "Title will be truncated at ~60 characters. " + (text.length - 60) + " characters over the limit.";
    } else {
      serpWarn.style.display = "none";
    }

    // Suggestions
    var sugs = buildSuggestions(data);
    var sugHtml = "";
    for (var i = 0; i < sugs.length; i++) {
      var iconClass = sugs[i].type;
      var iconChar = sugs[i].type === "good" ? "&#10003;" : (sugs[i].type === "bad" ? "&#10007;" : "&#9888;");
      sugHtml += '<li><span class="ha-sug-icon ' + iconClass + '">' + iconChar + '</span>' + sugs[i].text + '</li>';
    }
    document.getElementById("haSuggestions").innerHTML = sugHtml;

    // History
    headlineHistory.unshift({ text: text, score: data.overall });
    if (headlineHistory.length > 10) headlineHistory.pop();
    try {
      localStorage.setItem("ha_history", JSON.stringify(headlineHistory));
    } catch(e) {}
    renderHistory();
  };

  function renderHistory() {
    var list = document.getElementById("haHistoryList");
    if (headlineHistory.length === 0) {
      list.innerHTML = '<li style="padding: 10px 0;"><span class="ha-metric-detail">No headlines analyzed yet</span></li>';
      return;
    }
    var html = "";
    for (var i = 0; i < headlineHistory.length; i++) {
      var h = headlineHistory[i];
      var col = getScoreColor(h.score);
      html += '<li class="ha-history-item" onclick="haLoadHistory(' + i + ')">';
      html += '<span class="ha-history-text">' + h.text.replace(/</g, "&lt;") + '</span>';
      html += '<span class="ha-history-score" style="color: ' + col + '; background: ' + col + '15;">' + h.score + '</span>';
      html += '</li>';
    }
    list.innerHTML = html;
  }

  window.haLoadHistory = function(index) {
    if (headlineHistory[index]) {
      document.getElementById("haInput").value = headlineHistory[index].text;
      updateCounts();
      haAnalyze();
    }
  };

  window.haClearHistory = function() {
    headlineHistory = [];
    try { localStorage.removeItem("ha_history"); } catch(e) {}
    renderHistory();
  };

  // --- A/B Compare ---
  window.haCompareAB = function() {
    var textA = document.getElementById("haAbA").value.trim();
    var textB = document.getElementById("haAbB").value.trim();
    var scoreElA = document.getElementById("haAbScoreA");
    var scoreElB = document.getElementById("haAbScoreB");
    var winnerEl = document.getElementById("haAbWinner");

    if (!textA && !textB) return;

    var dataA = textA ? scoreHeadline(textA) : null;
    var dataB = textB ? scoreHeadline(textB) : null;

    if (dataA) {
      scoreElA.textContent = dataA.overall;
      scoreElA.style.color = getScoreColor(dataA.overall);
    } else {
      scoreElA.textContent = "--";
      scoreElA.style.color = "var(--ha-text-muted)";
    }

    if (dataB) {
      scoreElB.textContent = dataB.overall;
      scoreElB.style.color = getScoreColor(dataB.overall);
    } else {
      scoreElB.textContent = "--";
      scoreElB.style.color = "var(--ha-text-muted)";
    }

    if (dataA && dataB) {
      winnerEl.style.display = "block";
      if (dataA.overall > dataB.overall) {
        winnerEl.textContent = "Headline A wins by " + (dataA.overall - dataB.overall) + " points";
        winnerEl.style.background = "rgba(0, 255, 136, 0.08)";
        winnerEl.style.color = "var(--ha-green)";
        winnerEl.style.border = "1px solid rgba(0, 255, 136, 0.2)";
      } else if (dataB.overall > dataA.overall) {
        winnerEl.textContent = "Headline B wins by " + (dataB.overall - dataA.overall) + " points";
        winnerEl.style.background = "rgba(108, 92, 231, 0.08)";
        winnerEl.style.color = "var(--ha-primary-light)";
        winnerEl.style.border = "1px solid rgba(108, 92, 231, 0.2)";
      } else {
        winnerEl.textContent = "Both headlines scored equally at " + dataA.overall;
        winnerEl.style.background = "rgba(255, 193, 7, 0.08)";
        winnerEl.style.color = "var(--ha-yellow)";
        winnerEl.style.border = "1px solid rgba(255, 193, 7, 0.2)";
      }
    } else {
      winnerEl.style.display = "none";
    }
  };

  // --- Live char/word count ---
  function updateCounts() {
    var text = document.getElementById("haInput").value;
    document.getElementById("haCharCount").textContent = text.length;
    var words = text.trim().split(/\s+/).filter(function(w) { return w.length > 0; });
    document.getElementById("haWordCount").textContent = words.length;
  }

  document.getElementById("haInput").addEventListener("input", updateCounts);

  document.getElementById("haInput").addEventListener("keydown", function(e) {
    if (e.key === "Enter") {
      e.preventDefault();
      haAnalyze();
    }
  });

  // Init history render
  renderHistory();

})();
</script>
