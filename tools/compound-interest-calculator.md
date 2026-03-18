---
layout: page
title: "Free Compound Interest Calculator — Daily, Monthly & Yearly | Zovo"
description: "Calculate compound interest with contributions, visualize growth over time, and compare compounding frequencies. Free online compound interest calculator with charts and breakdown tables."
permalink: /tools/compound-interest-calculator/
keywords: "compound interest calculator, compound interest formula, interest calculator, savings calculator, investment calculator, daily compound interest, monthly compound interest, compound growth calculator"
date: 2026-03-19
categories: [tools]
tags: [compound-interest, calculator, finance, investment, savings, interest-rate, money]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --ci-primary: #6C5CE7;
    --ci-primary-dark: #5A4BD1;
    --ci-primary-light: #A29BFE;
    --ci-bg: #0a0a0f;
    --ci-surface: #12121a;
    --ci-surface-alt: #181824;
    --ci-border: #1e1e2e;
    --ci-text: #e0e0e0;
    --ci-text-muted: #8888aa;
    --ci-green: #00ff88;
    --ci-green-dark: #00cc6a;
    --ci-red: #ff4466;
    --ci-radius: 12px;
    --ci-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .ci-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ci-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .ci-wrapper * {
    box-sizing: border-box;
  }

  .ci-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .ci-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ci-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .ci-hero h1 span {
    color: var(--ci-primary);
  }

  .ci-intro {
    font-size: 1.05rem;
    color: var(--ci-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Input Panel */
  .ci-input-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 24px;
  }

  .ci-card {
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    padding: 24px;
    box-shadow: var(--ci-shadow);
  }

  .ci-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--ci-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .ci-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--ci-primary);
    border-radius: 2px;
  }

  .ci-field {
    margin-bottom: 16px;
  }

  .ci-field:last-child {
    margin-bottom: 0;
  }

  .ci-label {
    display: block;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--ci-text-muted);
    margin-bottom: 6px;
  }

  .ci-input-wrap {
    position: relative;
    display: flex;
    align-items: center;
  }

  .ci-input-prefix,
  .ci-input-suffix {
    position: absolute;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--ci-text-muted);
    pointer-events: none;
    z-index: 1;
  }

  .ci-input-prefix {
    left: 14px;
  }

  .ci-input-suffix {
    right: 14px;
  }

  .ci-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--ci-bg);
    border: 1px solid var(--ci-border);
    border-radius: 8px;
    color: var(--ci-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    -moz-appearance: textfield;
  }

  .ci-input::-webkit-outer-spin-button,
  .ci-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  .ci-input:focus {
    border-color: var(--ci-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .ci-input.has-prefix {
    padding-left: 32px;
  }

  .ci-input.has-suffix {
    padding-right: 32px;
  }

  .ci-select {
    width: 100%;
    padding: 10px 14px;
    background: var(--ci-bg);
    border: 1px solid var(--ci-border);
    border-radius: 8px;
    color: var(--ci-text);
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

  .ci-select:focus {
    border-color: var(--ci-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .ci-select option {
    background: var(--ci-surface);
    color: var(--ci-text);
  }

  .ci-time-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .ci-toggle-row {
    display: flex;
    gap: 0;
    border-radius: 8px;
    overflow: hidden;
    border: 1px solid var(--ci-border);
  }

  .ci-toggle-btn {
    flex: 1;
    padding: 9px 12px;
    background: var(--ci-bg);
    border: none;
    color: var(--ci-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .ci-toggle-btn.active {
    background: var(--ci-primary);
    color: #fff;
  }

  .ci-toggle-btn:not(.active):hover {
    background: var(--ci-surface-alt);
    color: var(--ci-text);
  }

  /* Action bar */
  .ci-actions {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 24px;
  }

  .ci-btn {
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

  .ci-btn-primary {
    background: var(--ci-primary);
    color: #fff;
  }

  .ci-btn-primary:hover {
    background: var(--ci-primary-dark);
  }

  .ci-btn-secondary {
    background: var(--ci-surface);
    color: var(--ci-text);
    border: 1px solid var(--ci-border);
  }

  .ci-btn-secondary:hover {
    background: var(--ci-surface-alt);
    border-color: var(--ci-primary);
  }

  .ci-btn-secondary.active {
    background: rgba(108, 92, 231, 0.15);
    border-color: var(--ci-primary);
    color: var(--ci-primary-light);
  }

  .ci-actions-spacer {
    flex: 1;
  }

  /* Results Summary */
  .ci-results {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-bottom: 24px;
  }

  .ci-result-card {
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    padding: 20px;
    text-align: center;
    box-shadow: var(--ci-shadow);
    transition: border-color 0.2s ease;
  }

  .ci-result-card.highlight {
    border-color: var(--ci-primary);
    background: linear-gradient(135deg, rgba(108, 92, 231, 0.08), var(--ci-surface));
  }

  .ci-result-label {
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--ci-text-muted);
    margin-bottom: 8px;
  }

  .ci-result-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--ci-text);
    line-height: 1.2;
  }

  .ci-result-card.highlight .ci-result-value {
    color: var(--ci-primary-light);
    font-size: 1.7rem;
  }

  .ci-result-sub {
    font-size: 0.75rem;
    color: var(--ci-text-muted);
    margin-top: 4px;
    font-family: 'JetBrains Mono', monospace;
  }

  /* Chart */
  .ci-chart-container {
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    padding: 24px;
    margin-bottom: 24px;
    box-shadow: var(--ci-shadow);
  }

  .ci-chart-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 16px;
  }

  .ci-chart-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--ci-text-muted);
  }

  .ci-chart-legend {
    display: flex;
    gap: 16px;
    font-size: 0.8rem;
    color: var(--ci-text-muted);
  }

  .ci-legend-dot {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 3px;
    margin-right: 6px;
    vertical-align: middle;
  }

  .ci-canvas-wrap {
    position: relative;
    width: 100%;
    height: 360px;
  }

  .ci-canvas-wrap canvas {
    width: 100%;
    height: 100%;
    display: block;
  }

  /* Table */
  .ci-table-container {
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    overflow: hidden;
    margin-bottom: 24px;
    box-shadow: var(--ci-shadow);
  }

  .ci-table-header {
    padding: 16px 20px;
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--ci-text-muted);
    border-bottom: 1px solid var(--ci-border);
  }

  .ci-table-scroll {
    max-height: 480px;
    overflow-y: auto;
  }

  .ci-table-scroll::-webkit-scrollbar {
    width: 6px;
  }

  .ci-table-scroll::-webkit-scrollbar-track {
    background: var(--ci-surface);
  }

  .ci-table-scroll::-webkit-scrollbar-thumb {
    background: var(--ci-border);
    border-radius: 3px;
  }

  .ci-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.875rem;
  }

  .ci-table thead {
    position: sticky;
    top: 0;
    z-index: 2;
  }

  .ci-table th {
    padding: 12px 16px;
    text-align: right;
    font-weight: 600;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--ci-text-muted);
    background: var(--ci-surface-alt);
    border-bottom: 1px solid var(--ci-border);
  }

  .ci-table th:first-child {
    text-align: center;
    width: 60px;
  }

  .ci-table td {
    padding: 11px 16px;
    text-align: right;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--ci-text);
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
  }

  .ci-table td:first-child {
    text-align: center;
    color: var(--ci-text-muted);
    font-weight: 600;
  }

  .ci-table tbody tr:nth-child(even) {
    background: rgba(18, 18, 26, 0.5);
  }

  .ci-table tbody tr:nth-child(odd) {
    background: var(--ci-surface);
  }

  .ci-table tbody tr:hover {
    background: rgba(108, 92, 231, 0.06);
  }

  .ci-table .ci-interest-col {
    color: var(--ci-green);
  }

  /* Compare Mode */
  .ci-compare-wrap {
    display: none;
    margin-bottom: 24px;
  }

  .ci-compare-wrap.visible {
    display: block;
  }

  .ci-compare-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .ci-compare-card {
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    padding: 20px;
    box-shadow: var(--ci-shadow);
  }

  .ci-compare-card h3 {
    font-size: 0.85rem;
    font-weight: 600;
    margin: 0 0 16px;
    color: var(--ci-primary-light);
  }

  .ci-compare-row {
    display: flex;
    justify-content: space-between;
    padding: 8px 0;
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
    font-size: 0.875rem;
  }

  .ci-compare-row:last-child {
    border-bottom: none;
  }

  .ci-compare-label {
    color: var(--ci-text-muted);
  }

  .ci-compare-value {
    font-family: 'JetBrains Mono', monospace;
    font-weight: 500;
    color: var(--ci-text);
  }

  .ci-compare-diff {
    text-align: center;
    padding: 16px;
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    margin-top: 16px;
    box-shadow: var(--ci-shadow);
  }

  .ci-compare-diff-label {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--ci-text-muted);
    margin-bottom: 6px;
  }

  .ci-compare-diff-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.3rem;
    font-weight: 600;
    color: var(--ci-green);
  }

  /* Print styles */
  @media print {
    .ci-wrapper {
      color: #222;
    }

    .ci-actions, .ci-hero, .ci-compare-wrap {
      display: none;
    }

    .ci-card, .ci-result-card, .ci-chart-container, .ci-table-container {
      background: #fff;
      border-color: #ddd;
      box-shadow: none;
      break-inside: avoid;
    }

    .ci-result-value, .ci-table td, .ci-table th {
      color: #222;
    }

    .ci-result-card.highlight .ci-result-value {
      color: var(--ci-primary);
    }
  }

  /* Content section */
  .ci-content {
    max-width: 820px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--ci-border);
  }

  .ci-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--ci-text);
    margin: 36px 0 16px;
    line-height: 1.3;
  }

  .ci-content h2:first-child {
    margin-top: 0;
  }

  .ci-content p {
    font-size: 0.95rem;
    color: var(--ci-text-muted);
    line-height: 1.8;
    margin: 0 0 16px;
  }

  .ci-content ul, .ci-content ol {
    padding-left: 24px;
    margin: 0 0 16px;
  }

  .ci-content li {
    font-size: 0.95rem;
    color: var(--ci-text-muted);
    line-height: 1.8;
    margin-bottom: 6px;
  }

  .ci-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.88rem;
    background: var(--ci-surface);
    padding: 2px 7px;
    border-radius: 4px;
    color: var(--ci-primary-light);
    border: 1px solid var(--ci-border);
  }

  .ci-formula-block {
    background: var(--ci-surface);
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    padding: 20px 24px;
    margin: 16px 0 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    color: var(--ci-primary-light);
    text-align: center;
    line-height: 1.8;
    overflow-x: auto;
  }

  /* FAQ Section */
  .ci-faq {
    max-width: 820px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--ci-border);
  }

  .ci-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--ci-text);
  }

  .ci-faq-item {
    border: 1px solid var(--ci-border);
    border-radius: var(--ci-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--ci-surface);
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.15);
  }

  .ci-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--ci-text);
  }

  .ci-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--ci-text-muted);
    line-height: 1.7;
  }

  /* Footer */
  .ci-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--ci-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--ci-border);
    margin-top: 3rem;
  }

  .ci-footer a {
    color: var(--ci-primary);
    text-decoration: none;
  }

  .ci-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .ci-hero h1 {
      font-size: 1.6rem;
    }

    .ci-input-grid {
      grid-template-columns: 1fr;
    }

    .ci-results {
      grid-template-columns: 1fr 1fr;
    }

    .ci-result-card.highlight .ci-result-value {
      font-size: 1.3rem;
    }

    .ci-result-value {
      font-size: 1.2rem;
    }

    .ci-canvas-wrap {
      height: 260px;
    }

    .ci-compare-grid {
      grid-template-columns: 1fr;
    }

    .ci-table {
      font-size: 0.8rem;
    }

    .ci-table th, .ci-table td {
      padding: 9px 10px;
    }

    .ci-btn {
      padding: 8px 14px;
      font-size: 0.8rem;
    }
  }

  @media (max-width: 480px) {
    .ci-results {
      grid-template-columns: 1fr;
    }

    .ci-time-row {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="ci-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Compound Interest Calculator">
  <meta itemprop="applicationCategory" content="FinanceApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="ci-hero">
    <h1><span>Compound Interest</span> Calculator</h1>
    <p class="ci-intro">Calculate how your savings or investments grow over time with compound interest. Add regular contributions, compare compounding frequencies, and visualize your growth with an interactive chart. Everything runs in your browser -- nothing is sent to a server.</p>
  </div>

  <!-- Input Fields -->
  <div class="ci-input-grid">
    <div class="ci-card">
      <div class="ci-card-title">Investment Details</div>

      <div class="ci-field">
        <label class="ci-label" for="ciPrincipal">Principal Amount</label>
        <div class="ci-input-wrap">
          <span class="ci-input-prefix">$</span>
          <input type="number" id="ciPrincipal" class="ci-input has-prefix" value="10000" min="0" step="100">
        </div>
      </div>

      <div class="ci-field">
        <label class="ci-label" for="ciRate">Annual Interest Rate</label>
        <div class="ci-input-wrap">
          <input type="number" id="ciRate" class="ci-input has-suffix" value="7" min="0" max="100" step="0.1">
          <span class="ci-input-suffix">%</span>
        </div>
      </div>

      <div class="ci-field">
        <label class="ci-label" for="ciCompound">Compound Frequency</label>
        <select id="ciCompound" class="ci-select">
          <option value="365">Daily (365x/year)</option>
          <option value="12" selected>Monthly (12x/year)</option>
          <option value="4">Quarterly (4x/year)</option>
          <option value="2">Semi-Annually (2x/year)</option>
          <option value="1">Annually (1x/year)</option>
        </select>
      </div>

      <div class="ci-field">
        <label class="ci-label">Time Period</label>
        <div class="ci-time-row">
          <div>
            <div class="ci-input-wrap">
              <input type="number" id="ciYears" class="ci-input has-suffix" value="10" min="0" max="100" step="1">
              <span class="ci-input-suffix">yr</span>
            </div>
          </div>
          <div>
            <div class="ci-input-wrap">
              <input type="number" id="ciMonths" class="ci-input has-suffix" value="0" min="0" max="11" step="1">
              <span class="ci-input-suffix">mo</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="ci-card">
      <div class="ci-card-title">Regular Contributions</div>

      <div class="ci-field">
        <label class="ci-label" for="ciContrib">Contribution Amount</label>
        <div class="ci-input-wrap">
          <span class="ci-input-prefix">$</span>
          <input type="number" id="ciContrib" class="ci-input has-prefix" value="200" min="0" step="50">
        </div>
      </div>

      <div class="ci-field">
        <label class="ci-label" for="ciContribFreq">Contribution Frequency</label>
        <select id="ciContribFreq" class="ci-select">
          <option value="12" selected>Monthly</option>
          <option value="4">Quarterly</option>
          <option value="1">Annually</option>
        </select>
      </div>

      <div class="ci-field">
        <label class="ci-label">Contribution Timing</label>
        <div class="ci-toggle-row">
          <button type="button" class="ci-toggle-btn active" data-timing="end" onclick="ciSetTiming(this)">End of Period</button>
          <button type="button" class="ci-toggle-btn" data-timing="beginning" onclick="ciSetTiming(this)">Beginning of Period</button>
        </div>
      </div>

      <div class="ci-field" style="margin-top: 24px;">
        <div class="ci-card-title" style="margin-bottom: 16px;">Scenario B (Compare Mode)</div>
        <label class="ci-label" for="ciRate2">Annual Interest Rate B</label>
        <div class="ci-input-wrap">
          <input type="number" id="ciRate2" class="ci-input has-suffix" value="5" min="0" max="100" step="0.1">
          <span class="ci-input-suffix">%</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Actions -->
  <div class="ci-actions">
    <button class="ci-btn ci-btn-secondary" id="ciCompareBtn" onclick="ciToggleCompare()">Compare Two Rates</button>
    <button class="ci-btn ci-btn-secondary" onclick="ciCopyResults()" id="ciCopyBtn">Copy Results</button>
    <button class="ci-btn ci-btn-secondary" onclick="window.print()">Print</button>
    <div class="ci-actions-spacer"></div>
    <button class="ci-btn ci-btn-secondary" onclick="ciReset()">Reset</button>
  </div>

  <!-- Results Summary -->
  <div class="ci-results" id="ciResults">
    <div class="ci-result-card highlight">
      <div class="ci-result-label">Total Balance</div>
      <div class="ci-result-value" id="ciTotalBalance">$0.00</div>
    </div>
    <div class="ci-result-card">
      <div class="ci-result-label">Total Contributions</div>
      <div class="ci-result-value" id="ciTotalContrib">$0.00</div>
    </div>
    <div class="ci-result-card">
      <div class="ci-result-label">Total Interest Earned</div>
      <div class="ci-result-value" id="ciTotalInterest">$0.00</div>
      <div class="ci-result-sub" id="ciInterestPct"></div>
    </div>
    <div class="ci-result-card">
      <div class="ci-result-label">Effective Annual Rate</div>
      <div class="ci-result-value" id="ciEAR">0.00%</div>
    </div>
  </div>

  <!-- Compare Mode -->
  <div class="ci-compare-wrap" id="ciCompareWrap">
    <div class="ci-compare-grid">
      <div class="ci-compare-card">
        <h3>Scenario A</h3>
        <div class="ci-compare-row">
          <span class="ci-compare-label">Interest Rate</span>
          <span class="ci-compare-value" id="cmpRateA">-</span>
        </div>
        <div class="ci-compare-row">
          <span class="ci-compare-label">Total Balance</span>
          <span class="ci-compare-value" id="cmpBalA">-</span>
        </div>
        <div class="ci-compare-row">
          <span class="ci-compare-label">Total Interest</span>
          <span class="ci-compare-value" id="cmpIntA">-</span>
        </div>
      </div>
      <div class="ci-compare-card">
        <h3>Scenario B</h3>
        <div class="ci-compare-row">
          <span class="ci-compare-label">Interest Rate</span>
          <span class="ci-compare-value" id="cmpRateB">-</span>
        </div>
        <div class="ci-compare-row">
          <span class="ci-compare-label">Total Balance</span>
          <span class="ci-compare-value" id="cmpBalB">-</span>
        </div>
        <div class="ci-compare-row">
          <span class="ci-compare-label">Total Interest</span>
          <span class="ci-compare-value" id="cmpIntB">-</span>
        </div>
      </div>
    </div>
    <div class="ci-compare-diff">
      <div class="ci-compare-diff-label">Difference (A - B)</div>
      <div class="ci-compare-diff-value" id="cmpDiff">$0.00</div>
    </div>
  </div>

  <!-- Chart -->
  <div class="ci-chart-container">
    <div class="ci-chart-header">
      <div class="ci-chart-title">Growth Over Time</div>
      <div class="ci-chart-legend">
        <span><span class="ci-legend-dot" style="background: #6C5CE7;"></span>Balance</span>
        <span><span class="ci-legend-dot" style="background: #00ff88;"></span>Contributions</span>
        <span><span class="ci-legend-dot" style="background: rgba(108,92,231,0.2);"></span>Interest</span>
      </div>
    </div>
    <div class="ci-canvas-wrap">
      <canvas id="ciChart"></canvas>
    </div>
  </div>

  <!-- Year-by-year Table -->
  <div class="ci-table-container">
    <div class="ci-table-header">Year-by-Year Breakdown</div>
    <div class="ci-table-scroll">
      <table class="ci-table">
        <thead>
          <tr>
            <th>Year</th>
            <th>Starting Balance</th>
            <th>Contributions</th>
            <th>Interest Earned</th>
            <th>Ending Balance</th>
          </tr>
        </thead>
        <tbody id="ciTableBody">
        </tbody>
      </table>
    </div>
  </div>

  <!-- SEO Content -->
  <div class="ci-content">

<h2>What Is Compound Interest</h2>

<p>Compound interest is interest calculated on both the initial principal and on the accumulated interest from previous periods. It differs from simple interest, where you only earn interest on the original amount. The key idea is that your interest earns interest, creating a snowball effect over time.</p>

<p>Say you deposit $1,000 at 5% annual interest compounded yearly. After the first year, you earn $50 in interest, bringing your total to $1,050. In the second year, you earn 5% on $1,050 instead of the original $1,000. That gives you $52.50 in interest. The extra $2.50 comes from compounding -- interest earned on the prior year's interest.</p>

<p>Over short periods the difference seems small. Over decades it becomes enormous. This is why compound interest is sometimes called the eighth wonder of the world, a phrase often attributed to Albert Einstein (though the attribution is disputed). The point stands regardless: compounding is the single most powerful force in personal finance.</p>

<h2>The Compound Interest Formula</h2>

<p>The standard compound interest formula for a lump sum investment is:</p>

<div class="ci-formula-block">
A = P(1 + r/n)^(nt)
</div>

<p>Where:</p>
<ul>
  <li>A = the future value of the investment</li>
  <li>P = the principal (initial deposit)</li>
  <li>r = the annual interest rate as a decimal (so 7% becomes 0.07)</li>
  <li>n = the number of times interest compounds per year</li>
  <li>t = the number of years</li>
</ul>

<p>When you add regular contributions (PMT), the formula extends to include the future value of an annuity:</p>

<div class="ci-formula-block">
A = P(1 + r/n)^(nt) + PMT x [((1 + r/n)^(nt) - 1) / (r/n)]
</div>

<p>This second part calculates what your recurring deposits grow to when each one also earns compound interest. The calculator above uses this complete formula, adjusted for contribution timing. If contributions happen at the beginning of each period rather than the end, each payment gets one extra compounding cycle.</p>

<h2>How Compounding Frequency Affects Growth</h2>

<p>Interest can compound at different intervals: daily, monthly, quarterly, semi-annually, or annually. The more frequently interest compounds, the more you earn, because each compounding event adds interest to the principal sooner.</p>

<p>Consider $10,000 at 6% annual interest over 10 years with no additional contributions:</p>

<ul>
  <li>Annually: $17,908.48</li>
  <li>Semi-Annually: $18,061.11</li>
  <li>Quarterly: $18,140.18</li>
  <li>Monthly: $18,193.97</li>
  <li>Daily: $18,220.44</li>
</ul>

<p>The difference between annual and daily compounding is about $312 on a $10,000 deposit. That gap grows much larger with bigger principals and longer time horizons. For a $100,000 deposit over 30 years at 6%, the difference between annual and daily compounding exceeds $14,000.</p>

<p>In practice, most savings accounts compound daily, while many bonds and CDs compound semi-annually. Knowing the compounding frequency helps you compare offers accurately. This calculator lets you switch between frequencies to see exactly how each one affects your outcome.</p>

<h2>Simple Interest vs Compound Interest</h2>

<p>Simple interest pays a fixed amount based only on the original principal. If you invest $10,000 at 5% simple interest for 10 years, you earn exactly $500 per year, totaling $5,000 in interest and $15,000 overall.</p>

<p>With compound interest at the same rate (compounded monthly), that same $10,000 grows to $16,470.09 over 10 years -- earning $6,470.09 in interest. That is nearly $1,500 more than simple interest. Over 30 years, the gap becomes massive: simple interest yields $25,000, while compound interest (monthly) yields $44,677.44.</p>

<p>The practical takeaway: always choose compound interest when saving or investing. And when borrowing, understand that compound interest works against you. Credit card debt, for example, compounds daily on unpaid balances. The same math that builds wealth on the savings side erodes it on the debt side.</p>

<h2>How to Use This Calculator</h2>

<p>Start by entering your initial deposit in the Principal Amount field. This is the money you have available right now, or the starting balance you want to project from.</p>

<p>Set the Annual Interest Rate to match your expected return. For a high-yield savings account, that might be 4-5%. For a stock market index fund, historical averages suggest around 7-10% before inflation. Be realistic - using an inflated rate will give you misleading projections.</p>

<p>Choose the Compound Frequency that matches your account. Most savings accounts use daily compounding. Bonds often use semi-annual. If you are not sure, monthly is a reasonable default.</p>

<p>Set the Time Period using years and months. Even a small change in time horizon can dramatically affect results due to the exponential nature of compounding.</p>

<p>If you plan to make regular deposits, fill in the Contribution Amount and choose the frequency. Toggle between End of Period and Beginning of Period to model when your deposits happen. Beginning-of-period contributions earn slightly more because they get compounded for one extra cycle.</p>

<p>Use the Compare Two Rates button to see how different interest rates would affect your outcome side by side. This is useful when choosing between two savings products or when modeling optimistic versus conservative return scenarios.</p>

<h2>The Rule of 72</h2>

<p>The Rule of 72 is a quick mental shortcut for estimating how long it takes an investment to double. Divide 72 by your annual interest rate, and you get the approximate number of years to double your money.</p>

<p>At 6% interest: 72 / 6 = 12 years to double. At 8%: 72 / 8 = 9 years. At 12%: 72 / 12 = 6 years.</p>

<p>This rule is surprisingly accurate for rates between 2% and 15%. It breaks down at very high or very low rates, but for typical investment returns it gives you a useful ballpark. Use it to quickly evaluate whether an investment opportunity is worth a deeper look.</p>

<p>You can also reverse the formula. Want to double your money in 5 years? You need 72 / 5 = 14.4% annual return. That immediately tells you it requires a fairly aggressive investment strategy.</p>

<h2>Real World Applications of Compound Interest</h2>

<p>Compound interest shows up everywhere in personal finance. Retirement accounts like 401(k)s and IRAs rely on decades of compounding to turn modest monthly contributions into substantial nest eggs. Someone who starts investing $500 per month at age 25 (at 7% annual return) will have over $1.2 million by age 65. Waiting until age 35 to start the same contributions yields only about $567,000. Those 10 extra years of compounding nearly double the final amount.</p>

<p>Mortgage amortization runs on compound interest too, which is why the early years of a mortgage payment go mostly toward interest rather than principal. Credit card companies use daily compounding on unpaid balances, which is part of why minimum payments barely dent the principal.</p>

<p>On the corporate side, compound interest determines bond pricing, loan structures, and the time value of money calculations that drive business decisions. Understanding it is not just useful for personal savings -- it is foundational to finance as a whole.</p>

<h2>Tips for Maximizing Compound Interest</h2>

<p>Start as early as possible. Time is the single largest factor in compound growth. Even small amounts invested in your twenties outperform larger amounts invested in your forties because of the additional compounding periods.</p>

<p>Reinvest your returns. Compounding only works when interest or dividends stay invested. If you withdraw your earnings, you are effectively converting compound interest back into simple interest. Set dividends to reinvest automatically whenever possible.</p>

<p>Make regular contributions. The formula above shows that recurring deposits dramatically increase your final balance. Set up automatic transfers so contributions happen without you having to remember.</p>

<p>Minimize fees. A 1% annual fee might seem small, but it compounds against you over time. On a $100,000 portfolio earning 7% over 30 years, a 1% annual fee costs you over $130,000 in lost growth. Choose low-cost index funds and fee-free accounts when available.</p>

<p>Choose accounts with frequent compounding. Daily compounding earns more than monthly, which earns more than annual. When comparing accounts with similar rates, the one with more frequent compounding gives a slightly better return.</p>

<p>Avoid withdrawing early. Every dollar you pull out loses all future compounding potential. Build a separate emergency fund so you never need to tap your long-term investments.</p>

  </div>

  <!-- FAQ Section -->
  <div class="ci-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How is compound interest different from simple interest?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Simple interest is calculated only on the original principal amount. Compound interest is calculated on the principal plus all previously accumulated interest. Over time, compound interest produces significantly higher returns because each interest payment becomes part of the base that earns future interest. For example, $10,000 at 5% over 20 years yields $10,000 in simple interest but $16,532.98 in compound interest (compounded monthly).</p>
      </div>
    </div>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What compounding frequency should I use?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Use the compounding frequency that matches your specific account or investment. Most savings accounts and money market accounts compound daily. CDs often compound daily or monthly. Bonds typically compound semi-annually. If you are calculating a general projection and do not know the exact frequency, monthly compounding is a reasonable middle-ground assumption.</p>
      </div>
    </div>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What interest rate should I use for stock market investments?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The S&P 500 has returned an average of about 10% annually before inflation since its inception, or roughly 7% after adjusting for inflation. Many financial planners use 7% as a reasonable long-term estimate for diversified stock portfolios. For more conservative projections, use 5-6%. Keep in mind that actual returns vary year to year, and past performance does not guarantee future results. This calculator shows a smooth growth curve, while real investments fluctuate.</p>
      </div>
    </div>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does this calculator account for taxes and inflation?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This calculator shows nominal growth without accounting for taxes or inflation. To approximate after-inflation returns, subtract the expected inflation rate (historically about 2-3% in the US) from your interest rate before calculating. For tax effects, the impact depends on your account type. Contributions to tax-advantaged accounts like 401(k)s and Roth IRAs grow tax-free or tax-deferred, so the calculator's output closely matches reality for those accounts.</p>
      </div>
    </div>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What does "beginning of period" vs "end of period" mean for contributions?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This setting controls when each contribution is added relative to the compounding period. End of period (ordinary annuity) means the deposit is made at the end of each interval, so it does not earn interest until the next period. Beginning of period (annuity due) means the deposit is made at the start, giving it one extra compounding cycle. Beginning-of-period contributions produce a slightly higher final balance because each deposit earns interest for one additional period.</p>
      </div>
    </div>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is this compound interest calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This calculator uses the standard compound interest formula with future value of annuity calculations, which is the same math used by banks and financial institutions. The results are mathematically precise for the inputs given. However, real-world returns are never perfectly constant -- stock markets fluctuate, savings rates change, and you may miss contributions. Use the results as a projection tool to understand growth potential, not as a guarantee of exact future balances.</p>
      </div>
    </div>

    <div class="ci-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my financial data safe when using this calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This calculator runs entirely in your web browser using JavaScript. No data is transmitted to any server, no information is stored, and no cookies are set. You can verify this by opening your browser's developer tools and checking the Network tab while using the calculator. Your financial inputs never leave your device.</p>
      </div>
    </div>

  </div>

  <footer class="ci-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  // --- DOM refs ---
  var elPrincipal = document.getElementById("ciPrincipal");
  var elRate = document.getElementById("ciRate");
  var elCompound = document.getElementById("ciCompound");
  var elYears = document.getElementById("ciYears");
  var elMonths = document.getElementById("ciMonths");
  var elContrib = document.getElementById("ciContrib");
  var elContribFreq = document.getElementById("ciContribFreq");
  var elRate2 = document.getElementById("ciRate2");
  var elChart = document.getElementById("ciChart");
  var elTableBody = document.getElementById("ciTableBody");

  var contributionTiming = "end"; // "end" or "beginning"
  var compareMode = false;
  var debounceTimer = null;

  // --- Formatting ---
  function formatCurrency(val) {
    if (val < 0) return "-$" + Math.abs(val).toLocaleString("en-US", { minimumFractionDigits: 2, maximumFractionDigits: 2 });
    return "$" + val.toLocaleString("en-US", { minimumFractionDigits: 2, maximumFractionDigits: 2 });
  }

  function formatPct(val) {
    return val.toFixed(2) + "%";
  }

  // --- Calculation engine ---
  function calcCompound(principal, annualRate, compoundsPerYear, totalYears, contribAmount, contribFreqPerYear, timing) {
    // Returns year-by-year data array
    var data = [];
    var balance = principal;
    var totalContribs = principal;
    var r = annualRate / 100;
    var n = compoundsPerYear;

    // We simulate month by month for precision
    var totalMonths = Math.round(totalYears * 12);
    var monthlyRate = r / 12;

    // Determine contribution interval in months
    var contribIntervalMonths = 12 / contribFreqPerYear;
    var compoundIntervalMonths = 12 / n;

    // We'll track per-year data
    var yearStart = principal;
    var yearContribs = 0;
    var currentYear = 0;

    // For chart: track monthly snapshots
    var monthlySnapshots = [{ month: 0, balance: principal, totalContribs: principal }];

    for (var m = 1; m <= totalMonths; m++) {
      // Check if a contribution is due this month
      var contribThisMonth = 0;
      if (contribAmount > 0 && contribFreqPerYear > 0) {
        // Contribution at months: contribIntervalMonths, 2*contribIntervalMonths, etc.
        var contribCheck = m / contribIntervalMonths;
        if (Math.abs(contribCheck - Math.round(contribCheck)) < 0.001) {
          contribThisMonth = contribAmount;
        }
      }

      // Check if compounding happens this month
      var compoundsThisMonth = false;
      if (n >= 12) {
        // Daily or monthly or higher: compound every month (approximation for daily: use monthly equivalent)
        compoundsThisMonth = true;
      } else {
        var compCheck = m / compoundIntervalMonths;
        if (Math.abs(compCheck - Math.round(compCheck)) < 0.001) {
          compoundsThisMonth = true;
        }
      }

      // Beginning of period contribution
      if (timing === "beginning" && contribThisMonth > 0) {
        balance += contribThisMonth;
        totalContribs += contribThisMonth;
        yearContribs += contribThisMonth;
      }

      // Apply interest
      if (compoundsThisMonth) {
        if (n >= 12) {
          // For daily compounding, calculate exact daily growth for the month (approx 30.4375 days)
          if (n === 365) {
            var daysInMonth = 30.4375;
            balance = balance * Math.pow(1 + r / 365, daysInMonth);
          } else {
            // Monthly or other: use monthly rate derived from compound frequency
            var periodicRate = Math.pow(1 + r / n, n / 12) - 1;
            balance = balance * (1 + periodicRate);
          }
        } else {
          // Compound at the proper interval
          balance = balance * (1 + r / n);
        }
      }

      // End of period contribution
      if (timing === "end" && contribThisMonth > 0) {
        balance += contribThisMonth;
        totalContribs += contribThisMonth;
        yearContribs += contribThisMonth;
      }

      monthlySnapshots.push({ month: m, balance: balance, totalContribs: totalContribs });

      // Year boundary
      if (m % 12 === 0 || m === totalMonths) {
        currentYear++;
        var yearInterest = balance - yearStart - yearContribs;
        data.push({
          year: currentYear,
          startBalance: yearStart,
          contributions: yearContribs,
          interest: yearInterest,
          endBalance: balance
        });
        yearStart = balance;
        yearContribs = 0;
      }
    }

    var totalInterest = balance - totalContribs;

    // Effective Annual Rate
    var ear = 0;
    if (n > 0 && r > 0) {
      ear = (Math.pow(1 + r / n, n) - 1) * 100;
    }

    return {
      finalBalance: balance,
      totalContributions: totalContribs,
      totalInterest: totalInterest,
      ear: ear,
      yearData: data,
      monthlySnapshots: monthlySnapshots
    };
  }

  // --- Update UI ---
  function update() {
    var principal = parseFloat(elPrincipal.value) || 0;
    var rate = parseFloat(elRate.value) || 0;
    var n = parseInt(elCompound.value) || 12;
    var years = parseInt(elYears.value) || 0;
    var months = parseInt(elMonths.value) || 0;
    var totalYears = years + months / 12;
    var contribAmount = parseFloat(elContrib.value) || 0;
    var contribFreq = parseInt(elContribFreq.value) || 12;

    if (totalYears <= 0) {
      totalYears = 0;
    }

    var result = calcCompound(principal, rate, n, totalYears, contribAmount, contribFreq, contributionTiming);

    // Update summary cards
    document.getElementById("ciTotalBalance").textContent = formatCurrency(result.finalBalance);
    document.getElementById("ciTotalContrib").textContent = formatCurrency(result.totalContributions);
    document.getElementById("ciTotalInterest").textContent = formatCurrency(result.totalInterest);

    var interestPctOfTotal = result.finalBalance > 0 ? (result.totalInterest / result.finalBalance * 100) : 0;
    document.getElementById("ciInterestPct").textContent = formatPct(interestPctOfTotal) + " of total";
    document.getElementById("ciEAR").textContent = formatPct(result.ear);

    // Update table
    renderTable(result.yearData);

    // Update chart
    renderChart(result.monthlySnapshots, totalYears);

    // Update compare mode
    if (compareMode) {
      updateCompare(principal, n, totalYears, contribAmount, contribFreq);
    }
  }

  function updateCompare(principal, n, totalYears, contribAmount, contribFreq) {
    var rateA = parseFloat(elRate.value) || 0;
    var rateB = parseFloat(elRate2.value) || 0;

    var resultA = calcCompound(principal, rateA, n, totalYears, contribAmount, contribFreq, contributionTiming);
    var resultB = calcCompound(principal, rateB, n, totalYears, contribAmount, contribFreq, contributionTiming);

    document.getElementById("cmpRateA").textContent = formatPct(rateA);
    document.getElementById("cmpBalA").textContent = formatCurrency(resultA.finalBalance);
    document.getElementById("cmpIntA").textContent = formatCurrency(resultA.totalInterest);

    document.getElementById("cmpRateB").textContent = formatPct(rateB);
    document.getElementById("cmpBalB").textContent = formatCurrency(resultB.finalBalance);
    document.getElementById("cmpIntB").textContent = formatCurrency(resultB.totalInterest);

    var diff = resultA.finalBalance - resultB.finalBalance;
    var diffEl = document.getElementById("cmpDiff");
    diffEl.textContent = (diff >= 0 ? "+" : "") + formatCurrency(diff);
    diffEl.style.color = diff >= 0 ? "var(--ci-green)" : "var(--ci-red)";
  }

  // --- Table ---
  function renderTable(yearData) {
    var html = "";
    for (var i = 0; i < yearData.length; i++) {
      var d = yearData[i];
      html += "<tr>";
      html += "<td>" + d.year + "</td>";
      html += "<td>" + formatCurrency(d.startBalance) + "</td>";
      html += "<td>" + formatCurrency(d.contributions) + "</td>";
      html += '<td class="ci-interest-col">' + formatCurrency(d.interest) + "</td>";
      html += "<td>" + formatCurrency(d.endBalance) + "</td>";
      html += "</tr>";
    }
    elTableBody.innerHTML = html;
  }

  // --- Canvas Chart ---
  function renderChart(snapshots, totalYears) {
    var canvas = elChart;
    var wrap = canvas.parentElement;
    var dpr = window.devicePixelRatio || 1;
    var w = wrap.clientWidth;
    var h = wrap.clientHeight;

    canvas.width = w * dpr;
    canvas.height = h * dpr;
    canvas.style.width = w + "px";
    canvas.style.height = h + "px";

    var ctx = canvas.getContext("2d");
    ctx.scale(dpr, dpr);

    // Clear
    ctx.clearRect(0, 0, w, h);

    if (snapshots.length < 2) {
      ctx.fillStyle = "#8888aa";
      ctx.font = "14px Inter, sans-serif";
      ctx.textAlign = "center";
      ctx.fillText("Enter values to see growth chart", w / 2, h / 2);
      return;
    }

    // Chart area with padding
    var padLeft = 80;
    var padRight = 20;
    var padTop = 20;
    var padBottom = 40;
    var chartW = w - padLeft - padRight;
    var chartH = h - padTop - padBottom;

    // Data ranges
    var maxBalance = 0;
    var maxContrib = 0;
    for (var i = 0; i < snapshots.length; i++) {
      if (snapshots[i].balance > maxBalance) maxBalance = snapshots[i].balance;
      if (snapshots[i].totalContribs > maxContrib) maxContrib = snapshots[i].totalContribs;
    }

    var maxY = maxBalance * 1.1;
    if (maxY === 0) maxY = 100;
    var totalMonths = snapshots[snapshots.length - 1].month;
    if (totalMonths === 0) totalMonths = 1;

    function xPos(month) {
      return padLeft + (month / totalMonths) * chartW;
    }

    function yPos(val) {
      return padTop + chartH - (val / maxY) * chartH;
    }

    // --- Gridlines ---
    var gridLines = 5;
    ctx.strokeStyle = "rgba(30, 30, 46, 0.8)";
    ctx.lineWidth = 1;
    ctx.setLineDash([4, 4]);

    for (var g = 0; g <= gridLines; g++) {
      var gy = padTop + (g / gridLines) * chartH;
      ctx.beginPath();
      ctx.moveTo(padLeft, gy);
      ctx.lineTo(padLeft + chartW, gy);
      ctx.stroke();
    }

    ctx.setLineDash([]);

    // Y axis labels
    ctx.fillStyle = "#8888aa";
    ctx.font = "11px JetBrains Mono, monospace";
    ctx.textAlign = "right";
    ctx.textBaseline = "middle";

    for (var g = 0; g <= gridLines; g++) {
      var yVal = maxY * (1 - g / gridLines);
      var gy = padTop + (g / gridLines) * chartH;
      var label;
      if (yVal >= 1000000) {
        label = "$" + (yVal / 1000000).toFixed(1) + "M";
      } else if (yVal >= 1000) {
        label = "$" + (yVal / 1000).toFixed(0) + "K";
      } else {
        label = "$" + yVal.toFixed(0);
      }
      ctx.fillText(label, padLeft - 10, gy);
    }

    // X axis labels (years)
    ctx.textAlign = "center";
    ctx.textBaseline = "top";
    var yearStep = Math.max(1, Math.ceil(totalYears / 10));
    for (var yr = 0; yr <= Math.ceil(totalYears); yr += yearStep) {
      var xm = yr * 12;
      if (xm > totalMonths) xm = totalMonths;
      var xx = xPos(xm);
      ctx.fillText("Yr " + yr, xx, padTop + chartH + 10);
    }

    // --- Contribution area fill ---
    ctx.beginPath();
    ctx.moveTo(xPos(0), yPos(0));
    for (var i = 0; i < snapshots.length; i++) {
      ctx.lineTo(xPos(snapshots[i].month), yPos(snapshots[i].totalContribs));
    }
    ctx.lineTo(xPos(snapshots[snapshots.length - 1].month), yPos(0));
    ctx.closePath();
    ctx.fillStyle = "rgba(0, 255, 136, 0.12)";
    ctx.fill();

    // --- Interest area fill (between balance and contributions) ---
    ctx.beginPath();
    for (var i = 0; i < snapshots.length; i++) {
      ctx.lineTo(xPos(snapshots[i].month), yPos(snapshots[i].balance));
    }
    for (var i = snapshots.length - 1; i >= 0; i--) {
      ctx.lineTo(xPos(snapshots[i].month), yPos(snapshots[i].totalContribs));
    }
    ctx.closePath();
    ctx.fillStyle = "rgba(108, 92, 231, 0.15)";
    ctx.fill();

    // --- Contribution line ---
    ctx.beginPath();
    ctx.moveTo(xPos(snapshots[0].month), yPos(snapshots[0].totalContribs));
    for (var i = 1; i < snapshots.length; i++) {
      ctx.lineTo(xPos(snapshots[i].month), yPos(snapshots[i].totalContribs));
    }
    ctx.strokeStyle = "#00ff88";
    ctx.lineWidth = 2;
    ctx.stroke();

    // --- Balance line ---
    ctx.beginPath();
    ctx.moveTo(xPos(snapshots[0].month), yPos(snapshots[0].balance));
    for (var i = 1; i < snapshots.length; i++) {
      ctx.lineTo(xPos(snapshots[i].month), yPos(snapshots[i].balance));
    }
    ctx.strokeStyle = "#6C5CE7";
    ctx.lineWidth = 2.5;
    ctx.stroke();

    // --- End point dots ---
    var last = snapshots[snapshots.length - 1];

    // Balance dot
    ctx.beginPath();
    ctx.arc(xPos(last.month), yPos(last.balance), 5, 0, Math.PI * 2);
    ctx.fillStyle = "#6C5CE7";
    ctx.fill();
    ctx.strokeStyle = "#0a0a0f";
    ctx.lineWidth = 2;
    ctx.stroke();

    // Contribution dot
    ctx.beginPath();
    ctx.arc(xPos(last.month), yPos(last.totalContribs), 4, 0, Math.PI * 2);
    ctx.fillStyle = "#00ff88";
    ctx.fill();
    ctx.strokeStyle = "#0a0a0f";
    ctx.lineWidth = 2;
    ctx.stroke();

    // End labels
    ctx.font = "11px JetBrains Mono, monospace";
    ctx.textAlign = "left";
    ctx.textBaseline = "middle";

    // Balance label
    var balLabel = formatCurrency(last.balance);
    var balY = yPos(last.balance);
    var contY = yPos(last.totalContribs);

    // Prevent overlap
    if (Math.abs(balY - contY) < 20) {
      balY = contY - 20;
    }

    ctx.fillStyle = "#A29BFE";
    ctx.fillText(balLabel, xPos(last.month) + 10, balY);

    ctx.fillStyle = "#00ff88";
    ctx.fillText(formatCurrency(last.totalContribs), xPos(last.month) + 10, contY);
  }

  // --- Timing toggle ---
  window.ciSetTiming = function(btn) {
    contributionTiming = btn.getAttribute("data-timing");
    var buttons = btn.parentElement.querySelectorAll(".ci-toggle-btn");
    for (var i = 0; i < buttons.length; i++) {
      buttons[i].classList.remove("active");
    }
    btn.classList.add("active");
    update();
  };

  // --- Compare toggle ---
  window.ciToggleCompare = function() {
    compareMode = !compareMode;
    var wrap = document.getElementById("ciCompareWrap");
    var btn = document.getElementById("ciCompareBtn");
    if (compareMode) {
      wrap.classList.add("visible");
      btn.classList.add("active");
      btn.textContent = "Hide Comparison";
    } else {
      wrap.classList.remove("visible");
      btn.classList.remove("active");
      btn.textContent = "Compare Two Rates";
    }
    update();
  };

  // --- Copy results ---
  window.ciCopyResults = function() {
    var bal = document.getElementById("ciTotalBalance").textContent;
    var contrib = document.getElementById("ciTotalContrib").textContent;
    var interest = document.getElementById("ciTotalInterest").textContent;
    var ear = document.getElementById("ciEAR").textContent;

    var text = "Compound Interest Calculation Results\n";
    text += "=====================================\n";
    text += "Principal: $" + (parseFloat(elPrincipal.value) || 0).toLocaleString() + "\n";
    text += "Annual Rate: " + (parseFloat(elRate.value) || 0) + "%\n";
    text += "Time: " + (parseInt(elYears.value) || 0) + " years " + (parseInt(elMonths.value) || 0) + " months\n";
    text += "Compound Frequency: " + elCompound.options[elCompound.selectedIndex].text + "\n";
    text += "Contribution: $" + (parseFloat(elContrib.value) || 0).toLocaleString() + " " + elContribFreq.options[elContribFreq.selectedIndex].text + "\n";
    text += "-------------------------------------\n";
    text += "Total Balance: " + bal + "\n";
    text += "Total Contributions: " + contrib + "\n";
    text += "Total Interest Earned: " + interest + "\n";
    text += "Effective Annual Rate: " + ear + "\n";

    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById("ciCopyBtn");
      var orig = btn.textContent;
      btn.textContent = "Copied";
      btn.style.borderColor = "var(--ci-green)";
      btn.style.color = "var(--ci-green)";
      setTimeout(function() {
        btn.textContent = orig;
        btn.style.borderColor = "";
        btn.style.color = "";
      }, 2000);
    });
  };

  // --- Reset ---
  window.ciReset = function() {
    elPrincipal.value = "10000";
    elRate.value = "7";
    elCompound.value = "12";
    elYears.value = "10";
    elMonths.value = "0";
    elContrib.value = "200";
    elContribFreq.value = "12";
    elRate2.value = "5";
    contributionTiming = "end";

    var toggleBtns = document.querySelectorAll(".ci-toggle-btn");
    for (var i = 0; i < toggleBtns.length; i++) {
      if (toggleBtns[i].getAttribute("data-timing") === "end") {
        toggleBtns[i].classList.add("active");
      } else {
        toggleBtns[i].classList.remove("active");
      }
    }

    if (compareMode) {
      ciToggleCompare();
    }

    update();
  };

  // --- Debounced input listeners ---
  function debouncedUpdate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(update, 150);
  }

  var inputs = [elPrincipal, elRate, elCompound, elYears, elMonths, elContrib, elContribFreq, elRate2];
  for (var i = 0; i < inputs.length; i++) {
    inputs[i].addEventListener("input", debouncedUpdate);
    inputs[i].addEventListener("change", debouncedUpdate);
  }

  // --- Resize handler ---
  var resizeTimer = null;
  window.addEventListener("resize", function() {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(update, 200);
  });

  // --- Initial calculation ---
  update();

})();
</script>
