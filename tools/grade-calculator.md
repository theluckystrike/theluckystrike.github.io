---
layout: page
title: "Free Grade Calculator — Final Exam & Weighted Grade Calculator | Zovo"
description: "Calculate your final exam grade needed, weighted average, and overall course grade. Free grade calculator with assignment categories, what-if scenarios, and grade tracking."
permalink: /tools/grade-calculator/
keywords: "grade calculator, final grade calculator, final exam calculator, weighted grade calculator, what grade do i need, course grade calculator, grade average calculator"
date: 2026-03-19
categories: [tools]
tags: [grade, calculator, education, final-exam, weighted, school]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --gc-primary: #6C5CE7;
    --gc-primary-dark: #5A4BD1;
    --gc-primary-light: #A29BFE;
    --gc-bg: #0a0a0f;
    --gc-surface: #12121a;
    --gc-surface-alt: #181824;
    --gc-border: #1e1e2e;
    --gc-text: #e0e0e0;
    --gc-text-muted: #8888aa;
    --gc-green: #00ff88;
    --gc-green-dark: #00cc6a;
    --gc-red: #ff4466;
    --gc-yellow: #ffd666;
    --gc-radius: 12px;
    --gc-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .gc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--gc-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .gc-wrapper * {
    box-sizing: border-box;
  }

  .gc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .gc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--gc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .gc-hero h1 span {
    color: var(--gc-primary);
  }

  .gc-intro {
    font-size: 1.05rem;
    color: var(--gc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Tabs */
  .gc-tabs {
    display: flex;
    gap: 0;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid var(--gc-border);
    margin-bottom: 24px;
  }

  .gc-tab {
    flex: 1;
    padding: 12px 16px;
    background: var(--gc-bg);
    border: none;
    color: var(--gc-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    text-align: center;
    border-right: 1px solid var(--gc-border);
  }

  .gc-tab:last-child {
    border-right: none;
  }

  .gc-tab.active {
    background: var(--gc-primary);
    color: #fff;
  }

  .gc-tab:not(.active):hover {
    background: var(--gc-surface-alt);
    color: var(--gc-text);
  }

  .gc-tab-panel {
    display: none;
  }

  .gc-tab-panel.active {
    display: block;
  }

  /* Card */
  .gc-card {
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    padding: 24px;
    box-shadow: var(--gc-shadow);
    margin-bottom: 24px;
  }

  .gc-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--gc-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .gc-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--gc-primary);
    border-radius: 2px;
  }

  /* Fields */
  .gc-field {
    margin-bottom: 16px;
  }

  .gc-field:last-child {
    margin-bottom: 0;
  }

  .gc-label {
    display: block;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--gc-text-muted);
    margin-bottom: 6px;
  }

  .gc-input-wrap {
    position: relative;
    display: flex;
    align-items: center;
  }

  .gc-input-suffix {
    position: absolute;
    right: 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--gc-text-muted);
    pointer-events: none;
    z-index: 1;
  }

  .gc-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--gc-bg);
    border: 1px solid var(--gc-border);
    border-radius: 8px;
    color: var(--gc-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    -moz-appearance: textfield;
  }

  .gc-input::-webkit-outer-spin-button,
  .gc-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  .gc-input:focus {
    border-color: var(--gc-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .gc-input.has-suffix {
    padding-right: 36px;
  }

  .gc-select {
    width: 100%;
    padding: 10px 14px;
    background: var(--gc-bg);
    border: 1px solid var(--gc-border);
    border-radius: 8px;
    color: var(--gc-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    outline: none;
    cursor: pointer;
    transition: border-color 0.2s ease;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%238888aa' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    padding-right: 32px;
  }

  .gc-select:focus {
    border-color: var(--gc-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .gc-select option {
    background: var(--gc-surface);
    color: var(--gc-text);
  }

  /* Inline fields */
  .gc-inline-fields {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
    margin-bottom: 20px;
  }

  .gc-inline-fields-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 20px;
  }

  /* Assignment rows */
  .gc-assignment-row {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 40px;
    gap: 10px;
    align-items: end;
    margin-bottom: 10px;
  }

  .gc-row-label {
    font-size: 0.75rem;
    color: var(--gc-text-muted);
    margin-bottom: 4px;
  }

  .gc-remove-btn {
    width: 36px;
    height: 38px;
    background: transparent;
    border: 1px solid var(--gc-border);
    border-radius: 8px;
    color: var(--gc-text-muted);
    font-size: 1.1rem;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.15s ease;
  }

  .gc-remove-btn:hover {
    background: rgba(255, 68, 102, 0.15);
    border-color: var(--gc-red);
    color: var(--gc-red);
  }

  /* Category rows */
  .gc-cat-row {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 40px;
    gap: 10px;
    align-items: end;
    margin-bottom: 10px;
  }

  /* Buttons */
  .gc-actions {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 24px;
  }

  .gc-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .gc-btn-primary {
    background: var(--gc-primary);
    color: #fff;
  }

  .gc-btn-primary:hover {
    background: var(--gc-primary-dark);
  }

  .gc-btn-secondary {
    background: var(--gc-surface);
    color: var(--gc-text);
    border: 1px solid var(--gc-border);
  }

  .gc-btn-secondary:hover {
    background: var(--gc-surface-alt);
    border-color: var(--gc-primary);
  }

  .gc-btn-sm {
    padding: 7px 14px;
    font-size: 0.8rem;
  }

  .gc-actions-spacer {
    flex: 1;
  }

  /* Result display */
  .gc-result-box {
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    padding: 28px;
    text-align: center;
    margin-bottom: 24px;
    box-shadow: var(--gc-shadow);
  }

  .gc-result-box .gc-result-top-label {
    font-size: 0.85rem;
    color: var(--gc-text-muted);
    margin-bottom: 12px;
  }

  .gc-result-box .gc-result-big {
    font-family: 'JetBrains Mono', monospace;
    font-size: 2.6rem;
    font-weight: 700;
    color: var(--gc-primary-light);
    line-height: 1.2;
  }

  .gc-result-box .gc-result-letter {
    font-size: 1.2rem;
    font-weight: 600;
    color: var(--gc-text);
    margin-top: 8px;
  }

  .gc-result-box .gc-result-note {
    font-size: 0.85rem;
    color: var(--gc-text-muted);
    margin-top: 10px;
    line-height: 1.6;
  }

  /* Results grid */
  .gc-results {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-bottom: 24px;
  }

  .gc-result-card {
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    padding: 20px;
    text-align: center;
    box-shadow: var(--gc-shadow);
    transition: border-color 0.2s ease;
  }

  .gc-result-card.highlight {
    border-color: var(--gc-primary);
    background: linear-gradient(135deg, rgba(108, 92, 231, 0.08), var(--gc-surface));
  }

  .gc-result-label {
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--gc-text-muted);
    margin-bottom: 8px;
  }

  .gc-result-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--gc-text);
    line-height: 1.2;
  }

  .gc-result-card.highlight .gc-result-value {
    color: var(--gc-primary-light);
    font-size: 1.7rem;
  }

  .gc-result-sub {
    font-size: 0.75rem;
    color: var(--gc-text-muted);
    margin-top: 4px;
    font-family: 'JetBrains Mono', monospace;
  }

  /* Progress bar */
  .gc-progress-wrap {
    margin-bottom: 24px;
  }

  .gc-progress-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 8px;
  }

  .gc-progress-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--gc-text-muted);
  }

  .gc-progress-pct {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--gc-text);
  }

  .gc-progress-bar {
    width: 100%;
    height: 14px;
    background: var(--gc-bg);
    border-radius: 7px;
    border: 1px solid var(--gc-border);
    overflow: hidden;
    position: relative;
  }

  .gc-progress-fill {
    height: 100%;
    border-radius: 7px;
    transition: width 0.4s ease, background 0.4s ease;
    min-width: 0;
  }

  .gc-progress-markers {
    display: flex;
    justify-content: space-between;
    margin-top: 4px;
    font-size: 0.7rem;
    color: var(--gc-text-muted);
    font-family: 'JetBrains Mono', monospace;
  }

  /* Slider */
  .gc-slider-wrap {
    margin-bottom: 20px;
  }

  .gc-slider-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 8px;
  }

  .gc-slider-label {
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--gc-text-muted);
  }

  .gc-slider-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--gc-primary-light);
  }

  .gc-slider {
    width: 100%;
    -webkit-appearance: none;
    appearance: none;
    height: 6px;
    background: var(--gc-border);
    border-radius: 3px;
    outline: none;
    cursor: pointer;
  }

  .gc-slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--gc-primary);
    border: 3px solid var(--gc-surface);
    box-shadow: 0 2px 8px rgba(108, 92, 231, 0.4);
    cursor: pointer;
  }

  .gc-slider::-moz-range-thumb {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--gc-primary);
    border: 3px solid var(--gc-surface);
    box-shadow: 0 2px 8px rgba(108, 92, 231, 0.4);
    cursor: pointer;
  }

  .gc-whatif-result {
    font-size: 0.95rem;
    color: var(--gc-text-muted);
    text-align: center;
    padding: 16px;
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    margin-top: 12px;
  }

  .gc-whatif-result .gc-whatif-grade {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--gc-primary-light);
  }

  /* Weight indicator */
  .gc-weight-total {
    text-align: right;
    font-size: 0.85rem;
    margin-top: 8px;
    font-family: 'JetBrains Mono', monospace;
  }

  .gc-weight-ok {
    color: var(--gc-green);
  }

  .gc-weight-warn {
    color: var(--gc-yellow);
  }

  .gc-weight-bad {
    color: var(--gc-red);
  }

  /* Print */
  @media print {
    .gc-wrapper {
      color: #222;
    }

    .gc-actions, .gc-hero, .gc-tabs {
      display: none;
    }

    .gc-card, .gc-result-card, .gc-result-box {
      background: #fff;
      border-color: #ddd;
      box-shadow: none;
      break-inside: avoid;
    }

    .gc-result-value {
      color: #222;
    }

    .gc-result-card.highlight .gc-result-value {
      color: var(--gc-primary);
    }
  }

  /* Content section */
  .gc-content {
    max-width: 820px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--gc-border);
  }

  .gc-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--gc-text);
    margin: 36px 0 16px;
    line-height: 1.3;
  }

  .gc-content h2:first-child {
    margin-top: 0;
  }

  .gc-content p {
    font-size: 0.95rem;
    color: var(--gc-text-muted);
    line-height: 1.8;
    margin: 0 0 16px;
  }

  .gc-content ul, .gc-content ol {
    padding-left: 24px;
    margin: 0 0 16px;
  }

  .gc-content li {
    font-size: 0.95rem;
    color: var(--gc-text-muted);
    line-height: 1.8;
    margin-bottom: 6px;
  }

  .gc-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.88rem;
    background: var(--gc-surface);
    padding: 2px 7px;
    border-radius: 4px;
    color: var(--gc-primary-light);
    border: 1px solid var(--gc-border);
  }

  .gc-formula-block {
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    padding: 20px 24px;
    margin: 16px 0 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    color: var(--gc-primary-light);
    text-align: center;
    line-height: 1.8;
    overflow-x: auto;
  }

  /* FAQ */
  .gc-faq {
    max-width: 820px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--gc-border);
  }

  .gc-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--gc-text);
  }

  .gc-faq-item {
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--gc-surface);
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.15);
  }

  .gc-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--gc-text);
  }

  .gc-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--gc-text-muted);
    line-height: 1.7;
  }

  /* Author box */
  .gc-author {
    max-width: 820px;
    margin: 32px auto 0;
    padding: 24px;
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    display: flex;
    gap: 20px;
    align-items: center;
  }

  .gc-author-avatar {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    background: var(--gc-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    flex-shrink: 0;
  }

  .gc-author-info h4 {
    margin: 0 0 4px;
    font-size: 1rem;
    font-weight: 600;
    color: var(--gc-text);
  }

  .gc-author-info p {
    margin: 0;
    font-size: 0.85rem;
    color: var(--gc-text-muted);
    line-height: 1.6;
  }

  .gc-updated {
    text-align: center;
    font-size: 0.8rem;
    color: var(--gc-text-muted);
    margin-top: 16px;
  }

  /* Cross-links */
  .gc-related {
    max-width: 820px;
    margin: 32px auto 0;
  }

  .gc-related h3 {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--gc-text-muted);
    margin: 0 0 12px;
  }

  .gc-related-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }

  .gc-related-link {
    display: block;
    padding: 16px;
    background: var(--gc-surface);
    border: 1px solid var(--gc-border);
    border-radius: var(--gc-radius);
    text-decoration: none;
    color: var(--gc-text);
    font-size: 0.9rem;
    font-weight: 500;
    transition: all 0.2s ease;
  }

  .gc-related-link:hover {
    border-color: var(--gc-primary);
    background: var(--gc-surface-alt);
  }

  .gc-related-link span {
    display: block;
    font-size: 0.75rem;
    color: var(--gc-text-muted);
    margin-top: 4px;
    font-weight: 400;
  }

  /* Footer */
  .gc-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--gc-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--gc-border);
    margin-top: 3rem;
  }

  .gc-footer a {
    color: var(--gc-primary);
    text-decoration: none;
  }

  .gc-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .gc-hero h1 {
      font-size: 1.6rem;
    }

    .gc-tabs {
      flex-wrap: wrap;
    }

    .gc-tab {
      flex: 1 1 45%;
      font-size: 0.78rem;
      padding: 10px 8px;
    }

    .gc-inline-fields {
      grid-template-columns: 1fr;
    }

    .gc-inline-fields-2 {
      grid-template-columns: 1fr;
    }

    .gc-assignment-row {
      grid-template-columns: 1fr 1fr 1fr 36px;
    }

    .gc-cat-row {
      grid-template-columns: 1fr 1fr 1fr 36px;
    }

    .gc-results {
      grid-template-columns: 1fr 1fr;
    }

    .gc-result-card.highlight .gc-result-value {
      font-size: 1.3rem;
    }

    .gc-result-value {
      font-size: 1.2rem;
    }

    .gc-btn {
      padding: 8px 14px;
      font-size: 0.8rem;
    }

    .gc-related-grid {
      grid-template-columns: 1fr;
    }

    .gc-author {
      flex-direction: column;
      text-align: center;
    }
  }

  @media (max-width: 480px) {
    .gc-results {
      grid-template-columns: 1fr;
    }

    .gc-assignment-row {
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }

    .gc-assignment-row .gc-assign-name-col {
      grid-column: 1 / -1;
    }

    .gc-cat-row {
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }

    .gc-cat-row .gc-cat-name-col {
      grid-column: 1 / -1;
    }
  }
</style>

<div class="gc-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Grade Calculator">
  <meta itemprop="applicationCategory" content="EducationalApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="gc-hero">
    <h1><span>Grade</span> Calculator</h1>
    <p class="gc-intro">Find out what you need on your final exam, calculate weighted category averages, or compute simple score statistics. Add assignments, adjust weights, and see results update in real time. All calculations run locally in your browser.</p>
  </div>

  <!-- Tabs -->
  <div class="gc-tabs">
    <button type="button" class="gc-tab active" onclick="gcSetTab('final')">Final Grade Needed</button>
    <button type="button" class="gc-tab" onclick="gcSetTab('weighted')">Weighted Average</button>
    <button type="button" class="gc-tab" onclick="gcSetTab('simple')">Simple Average</button>
  </div>

  <!-- FINAL GRADE NEEDED TAB -->
  <div class="gc-tab-panel active" id="gcTabFinal">
    <div class="gc-card">
      <div class="gc-card-title">Final Exam Calculator</div>
      <div class="gc-inline-fields">
        <div class="gc-field">
          <label class="gc-label" for="gcFinalCurrent">Current Grade</label>
          <div class="gc-input-wrap">
            <input type="number" id="gcFinalCurrent" class="gc-input has-suffix" value="85" min="0" max="100" step="0.1">
            <span class="gc-input-suffix">%</span>
          </div>
        </div>
        <div class="gc-field">
          <label class="gc-label" for="gcFinalDesired">Desired Grade</label>
          <div class="gc-input-wrap">
            <input type="number" id="gcFinalDesired" class="gc-input has-suffix" value="90" min="0" max="100" step="0.1">
            <span class="gc-input-suffix">%</span>
          </div>
        </div>
        <div class="gc-field">
          <label class="gc-label" for="gcFinalWeight">Final Exam Weight</label>
          <div class="gc-input-wrap">
            <input type="number" id="gcFinalWeight" class="gc-input has-suffix" value="30" min="1" max="100" step="1">
            <span class="gc-input-suffix">%</span>
          </div>
        </div>
      </div>
    </div>

    <div class="gc-result-box" id="gcFinalResult">
      <div class="gc-result-top-label">You need to score at least</div>
      <div class="gc-result-big" id="gcFinalNeeded">0.0%</div>
      <div class="gc-result-letter" id="gcFinalLetter"></div>
      <div class="gc-result-note" id="gcFinalNote"></div>
    </div>

    <!-- What if slider -->
    <div class="gc-card">
      <div class="gc-card-title">What-If Scenario</div>
      <div class="gc-slider-wrap">
        <div class="gc-slider-header">
          <span class="gc-slider-label">If I score this on the final...</span>
          <span class="gc-slider-value" id="gcSliderDisplay">75%</span>
        </div>
        <input type="range" class="gc-slider" id="gcFinalSlider" min="0" max="100" value="75" step="1">
      </div>
      <div class="gc-whatif-result">
        Your overall course grade would be <span class="gc-whatif-grade" id="gcSliderResult">0.0%</span>
        <span id="gcSliderLetter"></span>
      </div>
    </div>

    <!-- Progress bar -->
    <div class="gc-progress-wrap">
      <div class="gc-progress-header">
        <span class="gc-progress-title">Current Standing</span>
        <span class="gc-progress-pct" id="gcFinalProgressPct">85%</span>
      </div>
      <div class="gc-progress-bar">
        <div class="gc-progress-fill" id="gcFinalProgressFill" style="width: 85%; background: var(--gc-green);"></div>
      </div>
      <div class="gc-progress-markers">
        <span>0%</span><span>25%</span><span>50%</span><span>75%</span><span>100%</span>
      </div>
    </div>
  </div>

  <!-- WEIGHTED AVERAGE TAB -->
  <div class="gc-tab-panel" id="gcTabWeighted">
    <div class="gc-card">
      <div class="gc-card-title">Grade Categories</div>
      <div class="gc-cat-row" style="margin-bottom: 6px;">
        <div class="gc-row-label">Category Name</div>
        <div class="gc-row-label">Weight (%)</div>
        <div class="gc-row-label">Score (%)</div>
        <div></div>
      </div>
      <div id="gcWeightedCategories"></div>
      <div class="gc-weight-total" id="gcWeightTotal">Total weight: 0%</div>
      <div style="margin-top: 12px;">
        <button type="button" class="gc-btn gc-btn-primary gc-btn-sm" onclick="gcAddCategory()">+ Add Category</button>
      </div>
    </div>

    <div class="gc-result-box">
      <div class="gc-result-top-label">Weighted Average</div>
      <div class="gc-result-big" id="gcWeightedResult">0.0%</div>
      <div class="gc-result-letter" id="gcWeightedLetter"></div>
    </div>

    <!-- Progress bar -->
    <div class="gc-progress-wrap">
      <div class="gc-progress-header">
        <span class="gc-progress-title">Current Standing</span>
        <span class="gc-progress-pct" id="gcWeightedProgressPct">0%</span>
      </div>
      <div class="gc-progress-bar">
        <div class="gc-progress-fill" id="gcWeightedProgressFill" style="width: 0%; background: var(--gc-primary);"></div>
      </div>
      <div class="gc-progress-markers">
        <span>0%</span><span>25%</span><span>50%</span><span>75%</span><span>100%</span>
      </div>
    </div>

    <div class="gc-actions">
      <button type="button" class="gc-btn gc-btn-secondary" onclick="gcExportWeighted()" id="gcWeightedExportBtn">Export as Text</button>
      <button type="button" class="gc-btn gc-btn-secondary" onclick="window.print()">Print</button>
      <div class="gc-actions-spacer"></div>
      <button type="button" class="gc-btn gc-btn-secondary" onclick="gcClearWeighted()">Clear All</button>
    </div>
  </div>

  <!-- SIMPLE AVERAGE TAB -->
  <div class="gc-tab-panel" id="gcTabSimple">
    <div class="gc-card">
      <div class="gc-card-title">Scores</div>
      <div class="gc-assignment-row" style="margin-bottom: 6px;">
        <div class="gc-row-label">Assignment Name</div>
        <div class="gc-row-label">Score</div>
        <div class="gc-row-label">Out of</div>
        <div></div>
      </div>
      <div id="gcSimpleScores"></div>
      <div style="margin-top: 12px;">
        <button type="button" class="gc-btn gc-btn-primary gc-btn-sm" onclick="gcAddScore()">+ Add Score</button>
      </div>
    </div>

    <div class="gc-results" id="gcSimpleResults">
      <div class="gc-result-card highlight">
        <div class="gc-result-label">Mean</div>
        <div class="gc-result-value" id="gcSimpleMean">0.0%</div>
        <div class="gc-result-sub" id="gcSimpleMeanLetter"></div>
      </div>
      <div class="gc-result-card">
        <div class="gc-result-label">Median</div>
        <div class="gc-result-value" id="gcSimpleMedian">0.0%</div>
      </div>
      <div class="gc-result-card">
        <div class="gc-result-label">Highest</div>
        <div class="gc-result-value" id="gcSimpleHigh">0.0%</div>
      </div>
      <div class="gc-result-card">
        <div class="gc-result-label">Lowest</div>
        <div class="gc-result-value" id="gcSimpleLow">0.0%</div>
      </div>
    </div>

    <div class="gc-results" style="grid-template-columns: 1fr 1fr;">
      <div class="gc-result-card">
        <div class="gc-result-label">Std Deviation</div>
        <div class="gc-result-value" id="gcSimpleStdDev">0.0</div>
      </div>
      <div class="gc-result-card">
        <div class="gc-result-label">Total Scores</div>
        <div class="gc-result-value" id="gcSimpleCount">0</div>
      </div>
    </div>

    <!-- Progress bar -->
    <div class="gc-progress-wrap">
      <div class="gc-progress-header">
        <span class="gc-progress-title">Average Standing</span>
        <span class="gc-progress-pct" id="gcSimpleProgressPct">0%</span>
      </div>
      <div class="gc-progress-bar">
        <div class="gc-progress-fill" id="gcSimpleProgressFill" style="width: 0%; background: var(--gc-primary);"></div>
      </div>
      <div class="gc-progress-markers">
        <span>0%</span><span>25%</span><span>50%</span><span>75%</span><span>100%</span>
      </div>
    </div>

    <div class="gc-actions">
      <button type="button" class="gc-btn gc-btn-secondary" onclick="gcExportSimple()" id="gcSimpleExportBtn">Export as Text</button>
      <button type="button" class="gc-btn gc-btn-secondary" onclick="window.print()">Print</button>
      <div class="gc-actions-spacer"></div>
      <button type="button" class="gc-btn gc-btn-secondary" onclick="gcClearSimple()">Clear All</button>
    </div>
  </div>

  <!-- SEO Content -->
  <div class="gc-content">

<h2>What Is a Grade Calculator</h2>

<p>A grade calculator is a tool that helps you determine your standing in a course, figure out what score you need on upcoming assignments, or see how different outcomes would change your final grade. Students use grade calculators throughout the semester to plan study time, set realistic goals, and reduce end-of-term surprises.</p>

<p>Most courses use some form of weighted grading, where different categories (homework, quizzes, midterms, finals) contribute different percentages to your overall grade. A grade calculator does the math for you, handling the weights and producing both a percentage and a letter grade equivalent. This tool supports three modes: calculating the final exam score you need, computing a weighted category average, and finding simple statistics across a set of scores.</p>

<h2>How Weighted Grades Work</h2>

<p>Weighted grading assigns a percentage to each category of work in a course. A typical breakdown might look like this: homework 20%, quizzes 15%, midterm 25%, final exam 40%. The percentages must add up to 100%.</p>

<div class="gc-formula-block">
Weighted Average = (Score1 x Weight1) + (Score2 x Weight2) + ... + (ScoreN x WeightN)
</div>

<p>Suppose you have 92% on homework (20% weight), 78% on quizzes (15% weight), and 85% on the midterm (25% weight). The calculation so far: (92 x 0.20) + (78 x 0.15) + (85 x 0.25) = 18.4 + 11.7 + 21.25 = 51.35 out of 60% of the course. To find your current standing, divide by the total weight accounted for: 51.35 / 0.60 = 85.6%.</p>

<p>This is why a low score on a heavily weighted category has a larger impact than a low score on a lightly weighted one. Scoring 60% on a final worth 40% of your grade costs you 16 percentage points of your overall grade. The same 60% on a quiz worth 5% only costs 2 points. Understanding weight distributions helps you prioritize where to focus your effort.</p>

<h2>How to Calculate Your Final Grade</h2>

<p>The final grade needed formula rearranges the weighted average equation. If you know your current grade (the weighted average before the final), the weight of the final exam, and your desired overall grade, you can solve for the required final exam score.</p>

<div class="gc-formula-block">
Final Score Needed = (Desired Grade - Current Grade x (1 - Final Weight)) / Final Weight
</div>

<p>For example: your current grade is 85%, the final is worth 30% of your grade, and you want a 90% overall. Plugging in: (90 - 85 x 0.70) / 0.30 = (90 - 59.5) / 0.30 = 30.5 / 0.30 = 101.7%. You would need 101.7% on the final -- which means a 90% overall is likely out of reach unless extra credit is available.</p>

<p>This formula is useful at the end of every semester. Rather than guessing, you can see exactly where you stand and make informed decisions about how much time to invest in studying for each final.</p>

<h2>Understanding Grade Scales</h2>

<p>The most common grading scale in US education converts percentages to letter grades using these approximate ranges:</p>

<ul>
  <li>A: 93-100%</li>
  <li>A-: 90-92%</li>
  <li>B+: 87-89%</li>
  <li>B: 83-86%</li>
  <li>B-: 80-82%</li>
  <li>C+: 77-79%</li>
  <li>C: 73-76%</li>
  <li>C-: 70-72%</li>
  <li>D+: 67-69%</li>
  <li>D: 63-66%</li>
  <li>D-: 60-62%</li>
  <li>F: below 60%</li>
</ul>

<p>Individual instructors and institutions may adjust these cutoffs. Some professors use a flat 90/80/70/60 scale without plus/minus distinctions. Others curve grades based on class performance. Always check your syllabus for the specific scale your professor uses.</p>

<p>The grade calculator above shows letter grade equivalents alongside percentage scores to give you immediate context. Seeing that your 79.4% is a C+ rather than a B- can motivate you to push for those extra points.</p>

<h2>Tips for Improving Your Grades</h2>

<p>Calculate early and often. Run your numbers after every major assignment rather than waiting until the end of the semester. This gives you time to adjust your approach while grades still have room to move.</p>

<p>Identify high-impact assignments. If your final exam is worth 40% of your grade, that single test has the power to shift your letter grade by two levels. Allocate study time proportionally to assignment weight.</p>

<p>Talk to your professor before the final, not after. If you are on the border between two letter grades, some professors offer extra credit or alternative assessments. These conversations work best when you come with specific numbers: "I currently have an 89.2% and need a 90% for an A-" is much more persuasive than a vague request.</p>

<p>Do not ignore small assignments. Students sometimes skip homework that is worth only 5-10% of the grade, but those points add up. Earning a perfect score on 10% of homework effectively adds a full letter grade buffer to your performance on exams.</p>

<p>Use the weighted calculator to model scenarios. Enter your actual scores for completed work, then try different final exam scores to see the range of outcomes. Knowing that anything above a 72 on the final still gets you a B can reduce stress and help you study more effectively.</p>

  </div>

  <!-- FAQ Section -->
  <div class="gc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="gc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I calculate what I need on my final exam?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Enter your current course grade (percentage), the final exam weight (percentage of the total grade), and your desired overall grade in the Final Grade Needed tab. The calculator will show exactly what score you need. The formula is: Final Needed = (Desired Grade - Current Grade x (1 - Final Weight)) / Final Weight. If the result exceeds 100%, the target grade may not be achievable without extra credit.</p>
      </div>
    </div>

    <div class="gc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What if my category weights do not add up to 100%?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">If your weights sum to less than 100%, it usually means there are categories you have not entered yet (such as a final exam that has not happened). The calculator will compute the weighted average based on the weights you have provided. If your weights exceed 100%, check your syllabus for errors. The weight total indicator below the categories shows green when weights sum to exactly 100%, yellow when under, and red when over.</p>
      </div>
    </div>

    <div class="gc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I handle extra credit in the calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">If your score on an assignment exceeds the maximum (for example, 105 out of 100 due to extra credit), simply enter the actual score you received. The calculator accepts scores above 100%. For the simple average mode, enter your actual score and the original maximum. Extra credit will raise your average above what would otherwise be possible.</p>
      </div>
    </div>

    <div class="gc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between weighted and unweighted grades?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Unweighted grades treat every assignment equally -- each score contributes the same amount to your average. Weighted grades assign different importance to different categories. A course where the final is worth 40% and homework is worth 10% is using weighted grading. Most college courses use weighted grading, which is why the Weighted Average tab exists. The Simple Average tab is for unweighted calculations.</p>
      </div>
    </div>

    <div class="gc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use this calculator for high school classes?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The grade calculation formulas are the same regardless of education level. Enter your categories, weights, and scores as listed in your class syllabus. The letter grade scale used in this calculator (A = 93-100%, B = 83-92%, etc.) is a common standard, but your school may use different cutoffs. Adjust your interpretation of the letter grade output based on your school's specific grading policy.</p>
      </div>
    </div>

    <div class="gc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data private when using this tool?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All calculations run locally in your web browser using JavaScript. No grade data is transmitted to any server, no information is stored in databases or cookies, and no personal details are collected. You can verify this by opening your browser's developer tools and monitoring the Network tab. Your scores never leave your device.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="gc-author" itemscope itemtype="https://schema.org/Person">
    <div class="gc-author-avatar">ML</div>
    <div class="gc-author-info">
      <h4 itemprop="name">Michael Lip</h4>
      <p itemprop="description">Developer and founder of <a href="https://zovo.one" style="color: var(--gc-primary); text-decoration: none;">zovo.one</a>. Building free, privacy-focused tools for students, developers, and professionals.</p>
    </div>
  </div>

  <div class="gc-updated">Last updated: March 2026</div>

  <!-- Cross-links -->
  <div class="gc-related">
    <h3>Related Tools</h3>
    <div class="gc-related-grid">
      <a href="/tools/gpa-calculator/" class="gc-related-link">GPA Calculator <span>Semester, cumulative, and target GPA</span></a>
      <a href="/tools/citation-generator/" class="gc-related-link">Citation Generator <span>APA, MLA, Chicago citations</span></a>
      <a href="/tools/compound-interest-calculator/" class="gc-related-link">Compound Interest Calculator <span>Savings and investment growth</span></a>
    </div>
  </div>

  <footer class="gc-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Grade Calculator",
      "url": "https://theluckystrike.github.io/tools/grade-calculator/",
      "applicationCategory": "EducationalApplication",
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
      "description": "Calculate your final exam grade needed, weighted average, and overall course grade. Free grade calculator with assignment categories and what-if scenarios."
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "name": "Home",
          "item": "https://theluckystrike.github.io/"
        },
        {
          "@type": "ListItem",
          "position": 2,
          "name": "Tools",
          "item": "https://theluckystrike.github.io/tools/"
        },
        {
          "@type": "ListItem",
          "position": 3,
          "name": "Grade Calculator",
          "item": "https://theluckystrike.github.io/tools/grade-calculator/"
        }
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://zovo.one/logo.png",
      "founder": {
        "@type": "Person",
        "name": "Michael Lip"
      }
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How do I calculate what I need on my final exam?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Enter your current course grade, the final exam weight, and your desired overall grade. The formula is: Final Needed = (Desired Grade - Current Grade x (1 - Final Weight)) / Final Weight."
          }
        },
        {
          "@type": "Question",
          "name": "What if my category weights do not add up to 100%?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "If weights sum to less than 100%, it means there are categories not yet entered. The calculator computes the weighted average based on entered weights. The weight total indicator shows green at exactly 100%, yellow when under, and red when over."
          }
        },
        {
          "@type": "Question",
          "name": "How do I handle extra credit in the calculator?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Enter the actual score you received, even if it exceeds the maximum. The calculator accepts scores above 100%. Extra credit will raise your average above what would otherwise be possible."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between weighted and unweighted grades?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Unweighted grades treat every assignment equally. Weighted grades assign different importance to different categories. Most college courses use weighted grading."
          }
        },
        {
          "@type": "Question",
          "name": "Can I use this calculator for high school classes?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. The grade calculation formulas are the same regardless of education level. Enter your categories, weights, and scores as listed in your class syllabus."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data private when using this tool?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All calculations run locally in your web browser using JavaScript. No grade data is transmitted to any server, no information is stored, and no personal details are collected."
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

  // --- Letter grade conversion ---
  function toLetter(pct) {
    if (pct >= 93) return "A";
    if (pct >= 90) return "A-";
    if (pct >= 87) return "B+";
    if (pct >= 83) return "B";
    if (pct >= 80) return "B-";
    if (pct >= 77) return "C+";
    if (pct >= 73) return "C";
    if (pct >= 70) return "C-";
    if (pct >= 67) return "D+";
    if (pct >= 63) return "D";
    if (pct >= 60) return "D-";
    return "F";
  }

  function progressColor(pct) {
    if (pct >= 90) return "var(--gc-green)";
    if (pct >= 80) return "var(--gc-primary)";
    if (pct >= 70) return "var(--gc-yellow)";
    return "var(--gc-red)";
  }

  var catCounter = 0;
  var scoreCounter = 0;
  var debounceTimer = null;

  // ============================
  // FINAL GRADE NEEDED
  // ============================
  function updateFinal() {
    var current = parseFloat(document.getElementById("gcFinalCurrent").value) || 0;
    var desired = parseFloat(document.getElementById("gcFinalDesired").value) || 0;
    var weight = parseFloat(document.getElementById("gcFinalWeight").value) || 0;
    var w = weight / 100;

    var needed = 0;
    if (w > 0) {
      needed = (desired - current * (1 - w)) / w;
    }

    var neededEl = document.getElementById("gcFinalNeeded");
    var letterEl = document.getElementById("gcFinalLetter");
    var noteEl = document.getElementById("gcFinalNote");

    neededEl.textContent = needed.toFixed(1) + "%";

    if (needed > 100) {
      letterEl.textContent = toLetter(needed);
      noteEl.innerHTML = '<span style="color: var(--gc-red);">This score exceeds 100%. You may not be able to reach ' + desired.toFixed(1) + '% without extra credit.</span>';
      neededEl.style.color = "var(--gc-red)";
    } else if (needed < 0) {
      neededEl.textContent = "0.0%";
      letterEl.textContent = "";
      noteEl.innerHTML = '<span style="color: var(--gc-green);">You have already secured your desired grade. Any non-negative score will keep you above ' + desired.toFixed(1) + '%.</span>';
      neededEl.style.color = "var(--gc-green)";
    } else {
      letterEl.textContent = "Letter grade: " + toLetter(needed);
      noteEl.textContent = "Score at least " + needed.toFixed(1) + "% on your final exam (worth " + weight + "% of your grade) to achieve " + desired.toFixed(1) + "% overall.";
      neededEl.style.color = "var(--gc-primary-light)";
    }

    // Progress bar
    var clampedCurrent = Math.max(0, Math.min(100, current));
    document.getElementById("gcFinalProgressPct").textContent = current.toFixed(1) + "%";
    document.getElementById("gcFinalProgressFill").style.width = clampedCurrent + "%";
    document.getElementById("gcFinalProgressFill").style.background = progressColor(current);

    // What-if slider
    updateSlider();
  }

  function updateSlider() {
    var current = parseFloat(document.getElementById("gcFinalCurrent").value) || 0;
    var weight = parseFloat(document.getElementById("gcFinalWeight").value) || 0;
    var sliderVal = parseFloat(document.getElementById("gcFinalSlider").value) || 0;
    var w = weight / 100;

    var overall = current * (1 - w) + sliderVal * w;

    document.getElementById("gcSliderDisplay").textContent = sliderVal + "%";
    document.getElementById("gcSliderResult").textContent = overall.toFixed(1) + "%";
    document.getElementById("gcSliderLetter").textContent = "(" + toLetter(overall) + ")";
  }

  // ============================
  // WEIGHTED AVERAGE
  // ============================
  window.gcAddCategory = function(name, weight, score) {
    var container = document.getElementById("gcWeightedCategories");
    catCounter++;
    var idx = catCounter;

    var nameVal = name || "Category " + idx;
    var weightVal = weight || 20;
    var scoreVal = score !== undefined ? score : 85;

    var row = document.createElement("div");
    row.className = "gc-cat-row";
    row.id = "gcCat" + idx;

    row.innerHTML =
      '<div class="gc-cat-name-col"><input type="text" class="gc-input" id="gcCatName' + idx + '" value="' + nameVal + '" placeholder="Category name"></div>' +
      '<div><div class="gc-input-wrap"><input type="number" class="gc-input has-suffix" id="gcCatWeight' + idx + '" value="' + weightVal + '" min="0" max="100" step="1"><span class="gc-input-suffix">%</span></div></div>' +
      '<div><div class="gc-input-wrap"><input type="number" class="gc-input has-suffix" id="gcCatScore' + idx + '" value="' + scoreVal + '" min="0" max="200" step="0.1"><span class="gc-input-suffix">%</span></div></div>' +
      '<button type="button" class="gc-remove-btn" onclick="gcRemoveCategory(' + idx + ')">x</button>';

    container.appendChild(row);

    // Attach listeners
    var inputs = row.querySelectorAll("input[type=number]");
    for (var i = 0; i < inputs.length; i++) {
      inputs[i].addEventListener("input", debouncedUpdate);
      inputs[i].addEventListener("change", debouncedUpdate);
    }

    gcUpdateWeighted();
  };

  window.gcRemoveCategory = function(idx) {
    var row = document.getElementById("gcCat" + idx);
    if (row) row.remove();
    gcUpdateWeighted();
  };

  function getCategories() {
    var container = document.getElementById("gcWeightedCategories");
    var rows = container.querySelectorAll(".gc-cat-row");
    var cats = [];
    for (var i = 0; i < rows.length; i++) {
      var inputs = rows[i].querySelectorAll("input");
      if (inputs.length >= 3) {
        cats.push({
          name: inputs[0].value || "Category",
          weight: parseFloat(inputs[1].value) || 0,
          score: parseFloat(inputs[2].value) || 0
        });
      }
    }
    return cats;
  }

  window.gcUpdateWeighted = function() {
    var cats = getCategories();
    var totalWeight = 0;
    var weightedSum = 0;

    for (var i = 0; i < cats.length; i++) {
      totalWeight += cats[i].weight;
      weightedSum += (cats[i].score * cats[i].weight / 100);
    }

    var avg = totalWeight > 0 ? (weightedSum / (totalWeight / 100)) : 0;

    document.getElementById("gcWeightedResult").textContent = avg.toFixed(1) + "%";
    document.getElementById("gcWeightedLetter").textContent = "Letter grade: " + toLetter(avg);

    // Weight total indicator
    var wtEl = document.getElementById("gcWeightTotal");
    wtEl.textContent = "Total weight: " + totalWeight.toFixed(0) + "%";
    if (Math.abs(totalWeight - 100) < 0.1) {
      wtEl.className = "gc-weight-total gc-weight-ok";
    } else if (totalWeight < 100) {
      wtEl.className = "gc-weight-total gc-weight-warn";
    } else {
      wtEl.className = "gc-weight-total gc-weight-bad";
    }

    // Progress bar
    var clampedAvg = Math.max(0, Math.min(100, avg));
    document.getElementById("gcWeightedProgressPct").textContent = avg.toFixed(1) + "%";
    document.getElementById("gcWeightedProgressFill").style.width = clampedAvg + "%";
    document.getElementById("gcWeightedProgressFill").style.background = progressColor(avg);
  };

  window.gcClearWeighted = function() {
    document.getElementById("gcWeightedCategories").innerHTML = "";
    catCounter = 0;
    gcAddCategory("Homework", 20, 92);
    gcAddCategory("Midterm", 30, 85);
    gcAddCategory("Final Exam", 50, 0);
  };

  window.gcExportWeighted = function() {
    var cats = getCategories();
    var text = "Weighted Grade Calculation\n";
    text += "=========================\n\n";

    var totalWeight = 0;
    var weightedSum = 0;
    for (var i = 0; i < cats.length; i++) {
      totalWeight += cats[i].weight;
      weightedSum += (cats[i].score * cats[i].weight / 100);
      text += cats[i].name + ": " + cats[i].score.toFixed(1) + "% (weight: " + cats[i].weight + "%)\n";
    }

    var avg = totalWeight > 0 ? (weightedSum / (totalWeight / 100)) : 0;
    text += "\nWeighted Average: " + avg.toFixed(1) + "% (" + toLetter(avg) + ")\n";
    text += "Total Weight: " + totalWeight.toFixed(0) + "%\n";

    copyToClipboard(text, "gcWeightedExportBtn");
  };

  // ============================
  // SIMPLE AVERAGE
  // ============================
  window.gcAddScore = function(name, score, outOf) {
    var container = document.getElementById("gcSimpleScores");
    scoreCounter++;
    var idx = scoreCounter;

    var nameVal = name || "Assignment " + idx;
    var scoreVal = score !== undefined ? score : 85;
    var outOfVal = outOf || 100;

    var row = document.createElement("div");
    row.className = "gc-assignment-row";
    row.id = "gcScore" + idx;

    row.innerHTML =
      '<div class="gc-assign-name-col"><input type="text" class="gc-input" id="gcScoreName' + idx + '" value="' + nameVal + '" placeholder="Assignment name"></div>' +
      '<div><input type="number" class="gc-input" id="gcScoreVal' + idx + '" value="' + scoreVal + '" min="0" step="0.1"></div>' +
      '<div><input type="number" class="gc-input" id="gcScoreMax' + idx + '" value="' + outOfVal + '" min="1" step="1"></div>' +
      '<button type="button" class="gc-remove-btn" onclick="gcRemoveScore(' + idx + ')">x</button>';

    container.appendChild(row);

    var inputs = row.querySelectorAll("input[type=number]");
    for (var i = 0; i < inputs.length; i++) {
      inputs[i].addEventListener("input", debouncedUpdate);
      inputs[i].addEventListener("change", debouncedUpdate);
    }

    gcUpdateSimple();
  };

  window.gcRemoveScore = function(idx) {
    var row = document.getElementById("gcScore" + idx);
    if (row) row.remove();
    gcUpdateSimple();
  };

  function getScores() {
    var container = document.getElementById("gcSimpleScores");
    var rows = container.querySelectorAll(".gc-assignment-row");
    var scores = [];
    for (var i = 0; i < rows.length; i++) {
      var inputs = rows[i].querySelectorAll("input");
      if (inputs.length >= 3) {
        var score = parseFloat(inputs[1].value) || 0;
        var outOf = parseFloat(inputs[2].value) || 100;
        var pct = outOf > 0 ? (score / outOf) * 100 : 0;
        scores.push({
          name: inputs[0].value || "Assignment",
          score: score,
          outOf: outOf,
          pct: pct
        });
      }
    }
    return scores;
  }

  window.gcUpdateSimple = function() {
    var scores = getScores();

    if (scores.length === 0) {
      document.getElementById("gcSimpleMean").textContent = "0.0%";
      document.getElementById("gcSimpleMeanLetter").textContent = "";
      document.getElementById("gcSimpleMedian").textContent = "0.0%";
      document.getElementById("gcSimpleHigh").textContent = "0.0%";
      document.getElementById("gcSimpleLow").textContent = "0.0%";
      document.getElementById("gcSimpleStdDev").textContent = "0.0";
      document.getElementById("gcSimpleCount").textContent = "0";
      document.getElementById("gcSimpleProgressPct").textContent = "0%";
      document.getElementById("gcSimpleProgressFill").style.width = "0%";
      return;
    }

    var pcts = [];
    for (var i = 0; i < scores.length; i++) {
      pcts.push(scores[i].pct);
    }

    // Mean
    var sum = 0;
    for (var i = 0; i < pcts.length; i++) sum += pcts[i];
    var mean = sum / pcts.length;

    // Median
    var sorted = pcts.slice().sort(function(a, b) { return a - b; });
    var median;
    var mid = Math.floor(sorted.length / 2);
    if (sorted.length % 2 === 0) {
      median = (sorted[mid - 1] + sorted[mid]) / 2;
    } else {
      median = sorted[mid];
    }

    // Highest / lowest
    var high = sorted[sorted.length - 1];
    var low = sorted[0];

    // Standard deviation
    var sumSqDiff = 0;
    for (var i = 0; i < pcts.length; i++) {
      sumSqDiff += Math.pow(pcts[i] - mean, 2);
    }
    var stdDev = Math.sqrt(sumSqDiff / pcts.length);

    document.getElementById("gcSimpleMean").textContent = mean.toFixed(1) + "%";
    document.getElementById("gcSimpleMeanLetter").textContent = toLetter(mean);
    document.getElementById("gcSimpleMedian").textContent = median.toFixed(1) + "%";
    document.getElementById("gcSimpleHigh").textContent = high.toFixed(1) + "%";
    document.getElementById("gcSimpleLow").textContent = low.toFixed(1) + "%";
    document.getElementById("gcSimpleStdDev").textContent = stdDev.toFixed(1);
    document.getElementById("gcSimpleCount").textContent = pcts.length;

    // Progress bar
    var clampedMean = Math.max(0, Math.min(100, mean));
    document.getElementById("gcSimpleProgressPct").textContent = mean.toFixed(1) + "%";
    document.getElementById("gcSimpleProgressFill").style.width = clampedMean + "%";
    document.getElementById("gcSimpleProgressFill").style.background = progressColor(mean);
  };

  window.gcClearSimple = function() {
    document.getElementById("gcSimpleScores").innerHTML = "";
    scoreCounter = 0;
    gcAddScore("Assignment 1", 92, 100);
    gcAddScore("Assignment 2", 78, 100);
    gcAddScore("Assignment 3", 88, 100);
    gcAddScore("Assignment 4", 95, 100);
  };

  window.gcExportSimple = function() {
    var scores = getScores();
    var text = "Simple Grade Average\n";
    text += "====================\n\n";

    for (var i = 0; i < scores.length; i++) {
      text += scores[i].name + ": " + scores[i].score + "/" + scores[i].outOf + " (" + scores[i].pct.toFixed(1) + "%)\n";
    }

    text += "\nMean: " + document.getElementById("gcSimpleMean").textContent + "\n";
    text += "Median: " + document.getElementById("gcSimpleMedian").textContent + "\n";
    text += "Highest: " + document.getElementById("gcSimpleHigh").textContent + "\n";
    text += "Lowest: " + document.getElementById("gcSimpleLow").textContent + "\n";
    text += "Std Deviation: " + document.getElementById("gcSimpleStdDev").textContent + "\n";

    copyToClipboard(text, "gcSimpleExportBtn");
  };

  // ============================
  // TAB SWITCHING
  // ============================
  window.gcSetTab = function(tabName) {
    var tabs = document.querySelectorAll(".gc-tab");
    var panels = document.querySelectorAll(".gc-tab-panel");

    for (var i = 0; i < tabs.length; i++) {
      tabs[i].classList.remove("active");
    }
    for (var i = 0; i < panels.length; i++) {
      panels[i].classList.remove("active");
    }

    var map = { final: 0, weighted: 1, simple: 2 };
    var panelMap = {
      final: "gcTabFinal",
      weighted: "gcTabWeighted",
      simple: "gcTabSimple"
    };

    tabs[map[tabName]].classList.add("active");
    document.getElementById(panelMap[tabName]).classList.add("active");
  };

  // ============================
  // UTILITIES
  // ============================
  function copyToClipboard(text, btnId) {
    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById(btnId);
      var orig = btn.textContent;
      btn.textContent = "Copied";
      btn.style.borderColor = "var(--gc-green)";
      btn.style.color = "var(--gc-green)";
      setTimeout(function() {
        btn.textContent = orig;
        btn.style.borderColor = "";
        btn.style.color = "";
      }, 2000);
    });
  }

  function updateAll() {
    updateFinal();
    gcUpdateWeighted();
    gcUpdateSimple();
  }

  function debouncedUpdate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(updateAll, 150);
  }

  // ============================
  // INITIALIZATION
  // ============================
  function init() {
    // Final grade listeners
    var finalFields = ["gcFinalCurrent", "gcFinalDesired", "gcFinalWeight"];
    for (var i = 0; i < finalFields.length; i++) {
      var el = document.getElementById(finalFields[i]);
      if (el) {
        el.addEventListener("input", debouncedUpdate);
        el.addEventListener("change", debouncedUpdate);
      }
    }

    // Slider listener
    var slider = document.getElementById("gcFinalSlider");
    if (slider) {
      slider.addEventListener("input", function() { updateSlider(); });
    }

    // Default weighted categories
    gcAddCategory("Homework", 20, 92);
    gcAddCategory("Midterm", 30, 85);
    gcAddCategory("Final Exam", 50, 0);

    // Default simple scores
    gcAddScore("Assignment 1", 92, 100);
    gcAddScore("Assignment 2", 78, 100);
    gcAddScore("Assignment 3", 88, 100);
    gcAddScore("Assignment 4", 95, 100);

    // Initial calculations
    updateAll();
  }

  init();
})();
</script>
