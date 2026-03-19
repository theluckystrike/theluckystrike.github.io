---
layout: page
title: "Free Loan Calculator — Monthly Payment, Amortization & Interest | Zovo"
description: "Calculate monthly loan payments, total interest, and view amortization schedules. Compare loan terms, see payoff dates, and plan extra payments. Free online loan calculator."
permalink: /tools/loan-calculator/
keywords: "loan calculator, mortgage calculator, loan payment calculator, amortization calculator, interest calculator, car loan calculator, personal loan calculator, loan payoff calculator"
date: 2026-03-19
categories: [tools]
tags: [loan, calculator, mortgage, amortization, interest, finance, payment]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --lc-primary: #6C5CE7;
    --lc-primary-dark: #5A4BD1;
    --lc-primary-light: #A29BFE;
    --lc-bg: #0a0a0f;
    --lc-surface: #12121a;
    --lc-surface-alt: #181824;
    --lc-border: #1e1e2e;
    --lc-text: #e0e0e0;
    --lc-text-muted: #8888aa;
    --lc-green: #00ff88;
    --lc-green-dark: #00cc6a;
    --lc-red: #ff4466;
    --lc-orange: #ffaa33;
    --lc-blue: #33aaff;
    --lc-radius: 12px;
    --lc-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .lc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--lc-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .lc-wrapper * {
    box-sizing: border-box;
  }

  .lc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .lc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--lc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .lc-hero h1 span {
    color: var(--lc-primary);
  }

  .lc-intro {
    font-size: 1.05rem;
    color: var(--lc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Input Panel */
  .lc-input-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 24px;
  }

  .lc-card {
    background: var(--lc-surface);
    border: 1px solid var(--lc-border);
    border-radius: var(--lc-radius);
    padding: 24px;
    box-shadow: var(--lc-shadow);
  }

  .lc-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--lc-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .lc-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--lc-primary);
    border-radius: 2px;
  }

  .lc-field {
    margin-bottom: 16px;
  }

  .lc-field:last-child {
    margin-bottom: 0;
  }

  .lc-label {
    display: block;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--lc-text-muted);
    margin-bottom: 6px;
  }

  .lc-input-wrap {
    position: relative;
    display: flex;
    align-items: center;
  }

  .lc-input-prefix,
  .lc-input-suffix {
    position: absolute;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--lc-text-muted);
    pointer-events: none;
    z-index: 1;
  }

  .lc-input-prefix { left: 14px; }
  .lc-input-suffix { right: 14px; }

  .lc-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--lc-bg);
    border: 1px solid var(--lc-border);
    border-radius: 8px;
    color: var(--lc-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    -moz-appearance: textfield;
  }

  .lc-input::-webkit-outer-spin-button,
  .lc-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  .lc-input:focus {
    border-color: var(--lc-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .lc-input.has-prefix { padding-left: 32px; }
  .lc-input.has-suffix { padding-right: 32px; }

  .lc-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  /* Results */
  .lc-results {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin-bottom: 24px;
  }

  .lc-result-card {
    background: var(--lc-surface);
    border: 1px solid var(--lc-border);
    border-radius: var(--lc-radius);
    padding: 20px;
    text-align: center;
    box-shadow: var(--lc-shadow);
  }

  .lc-result-label {
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--lc-text-muted);
    margin: 0 0 8px;
  }

  .lc-result-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--lc-text);
    margin: 0;
    line-height: 1.2;
  }

  .lc-result-value.green { color: var(--lc-green); }
  .lc-result-value.purple { color: var(--lc-primary-light); }
  .lc-result-value.red { color: var(--lc-red); }

  .lc-result-sub {
    font-size: 0.75rem;
    color: var(--lc-text-muted);
    margin: 4px 0 0;
  }

  /* Extra payment savings */
  .lc-savings {
    background: rgba(0, 255, 136, 0.06);
    border: 1px solid rgba(0, 255, 136, 0.2);
    border-radius: var(--lc-radius);
    padding: 16px 20px;
    margin-bottom: 24px;
    display: none;
  }

  .lc-savings.visible { display: block; }

  .lc-savings-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--lc-green);
    margin: 0 0 8px;
  }

  .lc-savings-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  .lc-savings-item-label {
    font-size: 0.75rem;
    color: var(--lc-text-muted);
    margin: 0 0 2px;
  }

  .lc-savings-item-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--lc-green);
    margin: 0;
  }

  /* Compare Mode */
  .lc-compare-toggle {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: transparent;
    border: 1px solid var(--lc-border);
    border-radius: 8px;
    color: var(--lc-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    margin-bottom: 20px;
  }

  .lc-compare-toggle:hover {
    border-color: var(--lc-primary);
    color: var(--lc-text);
  }

  .lc-compare-toggle.active {
    background: rgba(108, 92, 231, 0.1);
    border-color: var(--lc-primary);
    color: var(--lc-primary-light);
  }

  .lc-compare-wrap {
    display: none;
    margin-bottom: 24px;
  }

  .lc-compare-wrap.visible { display: block; }

  .lc-compare-inputs {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .lc-compare-table {
    width: 100%;
    border-collapse: collapse;
  }

  .lc-compare-table th {
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--lc-text-muted);
    padding: 10px 12px;
    text-align: left;
    border-bottom: 1px solid var(--lc-border);
  }

  .lc-compare-table td {
    padding: 10px 12px;
    font-size: 0.9rem;
    color: var(--lc-text);
    border-bottom: 1px solid var(--lc-border);
  }

  .lc-compare-table td:not(:first-child) {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    text-align: right;
  }

  .lc-compare-table th:not(:first-child) { text-align: right; }

  .lc-compare-better {
    color: var(--lc-green);
    font-weight: 600;
  }

  /* Charts */
  .lc-charts {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 16px;
    margin-bottom: 24px;
  }

  .lc-chart-card {
    background: var(--lc-surface);
    border: 1px solid var(--lc-border);
    border-radius: var(--lc-radius);
    padding: 20px;
    box-shadow: var(--lc-shadow);
  }

  .lc-chart-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--lc-text-muted);
    margin: 0 0 16px;
  }

  .lc-canvas-wrap {
    position: relative;
    width: 100%;
  }

  .lc-canvas-wrap canvas {
    width: 100%;
    display: block;
  }

  /* Amortization Table */
  .lc-amort-wrap {
    margin-bottom: 24px;
  }

  .lc-amort-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }

  .lc-amort-header h3 {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--lc-text-muted);
    margin: 0;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .lc-amort-header h3::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--lc-primary);
    border-radius: 2px;
  }

  .lc-export-btn {
    padding: 6px 14px;
    background: transparent;
    border: 1px solid var(--lc-border);
    border-radius: 8px;
    color: var(--lc-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .lc-export-btn:hover {
    border-color: var(--lc-primary);
    color: var(--lc-text);
  }

  .lc-amort-scroll {
    max-height: 500px;
    overflow-y: auto;
    border: 1px solid var(--lc-border);
    border-radius: var(--lc-radius);
    background: var(--lc-surface);
  }

  .lc-amort-scroll::-webkit-scrollbar {
    width: 6px;
  }

  .lc-amort-scroll::-webkit-scrollbar-track {
    background: var(--lc-surface);
  }

  .lc-amort-scroll::-webkit-scrollbar-thumb {
    background: var(--lc-border);
    border-radius: 3px;
  }

  .lc-amort-table {
    width: 100%;
    border-collapse: collapse;
  }

  .lc-amort-table thead {
    position: sticky;
    top: 0;
    z-index: 2;
  }

  .lc-amort-table th {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--lc-text-muted);
    padding: 10px 10px;
    text-align: right;
    background: var(--lc-surface-alt);
    border-bottom: 1px solid var(--lc-border);
  }

  .lc-amort-table th:first-child { text-align: center; width: 60px; }

  .lc-amort-table td {
    padding: 8px 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    color: var(--lc-text-muted);
    text-align: right;
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
  }

  .lc-amort-table td:first-child {
    text-align: center;
    color: var(--lc-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
  }

  .lc-amort-table tbody tr:hover td {
    background: var(--lc-surface-alt);
  }

  /* Donut Chart */
  .lc-donut-wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .lc-donut-legend {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-top: 16px;
  }

  .lc-legend-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.8rem;
    color: var(--lc-text-muted);
  }

  .lc-legend-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .lc-legend-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    color: var(--lc-text);
    margin-left: auto;
  }

  /* Action Buttons */
  .lc-btn-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 24px;
  }

  .lc-btn {
    padding: 10px 20px;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
    border: none;
  }

  .lc-btn-primary {
    background: var(--lc-primary);
    color: white;
  }

  .lc-btn-primary:hover {
    background: var(--lc-primary-dark);
  }

  .lc-btn-outline {
    background: transparent;
    border: 1px solid var(--lc-border);
    color: var(--lc-text-muted);
  }

  .lc-btn-outline:hover {
    border-color: var(--lc-primary);
    color: var(--lc-text);
  }

  /* Cross Links */
  .lc-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .lc-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--lc-surface);
    border: 1px solid var(--lc-border);
    border-radius: 8px;
    color: var(--lc-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .lc-cross-link:hover {
    border-color: var(--lc-primary);
    color: var(--lc-text);
  }

  /* Content */
  .lc-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .lc-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 2.5rem 0 1rem;
    color: var(--lc-text);
  }

  .lc-content p {
    font-size: 0.95rem;
    color: var(--lc-text-muted);
    line-height: 1.8;
    margin: 0 0 1rem;
  }

  .lc-content ul, .lc-content ol {
    color: var(--lc-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 1.5rem;
    margin: 0 0 1rem;
  }

  .lc-content li {
    margin-bottom: 0.4rem;
  }

  .lc-formula-block {
    background: var(--lc-surface);
    border: 1px solid var(--lc-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin: 1rem 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--lc-primary-light);
    overflow-x: auto;
  }

  /* Author Box */
  .lc-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--lc-surface);
    border: 1px solid var(--lc-border);
    border-radius: var(--lc-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .lc-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--lc-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .lc-author-info { flex: 1; }

  .lc-author-name {
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--lc-text);
    margin: 0 0 4px;
  }

  .lc-author-bio {
    font-size: 0.82rem;
    color: var(--lc-text-muted);
    line-height: 1.6;
    margin: 0;
  }

  /* FAQ */
  .lc-faq {
    max-width: 780px;
    margin: 2.5rem auto 0;
  }

  .lc-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--lc-text);
    margin: 0 0 1.2rem;
  }

  .lc-faq-item {
    border-bottom: 1px solid var(--lc-border);
    padding: 1rem 0;
  }

  .lc-faq-item:last-child { border-bottom: none; }

  .lc-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--lc-text);
    margin: 0 0 8px;
  }

  .lc-faq-item p {
    font-size: 0.9rem;
    color: var(--lc-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Updated */
  .lc-updated {
    text-align: center;
    font-size: 0.8rem;
    color: var(--lc-text-muted);
    margin-top: 16px;
  }

  /* Footer */
  .lc-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--lc-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--lc-border);
    margin-top: 3rem;
  }

  .lc-footer a {
    color: var(--lc-primary);
    text-decoration: none;
  }

  .lc-footer a:hover { text-decoration: underline; }

  /* Responsive */
  @media (max-width: 900px) {
    .lc-input-grid { grid-template-columns: 1fr; }
    .lc-results { grid-template-columns: repeat(2, 1fr); }
    .lc-charts { grid-template-columns: 1fr; }
    .lc-compare-inputs { grid-template-columns: 1fr; }
    .lc-savings-grid { grid-template-columns: 1fr; gap: 8px; }
    .lc-hero h1 { font-size: 1.6rem; }
  }

  @media (max-width: 600px) {
    .lc-hero h1 { font-size: 1.3rem; }
    .lc-results { grid-template-columns: 1fr; }
    .lc-result-value { font-size: 1.3rem; }
    .lc-card { padding: 16px; }
    .lc-row { grid-template-columns: 1fr; }
    .lc-author-box { flex-direction: column; text-align: center; align-items: center; }
    .lc-amort-table th, .lc-amort-table td { padding: 6px 6px; font-size: 0.72rem; }
  }
</style>

<div class="lc-wrapper">

  <div class="lc-hero">
    <h1>Free <span>Loan Calculator</span></h1>
    <p class="lc-intro">Calculate monthly loan payments, total interest paid, and view a full amortization schedule. See how extra payments reduce your loan term and interest costs. Compare two loan scenarios side by side. All calculations run in your browser.</p>
  </div>

  <!-- Inputs -->
  <div class="lc-input-grid">

    <div class="lc-card">
      <div class="lc-card-title">Loan Details</div>
      <div class="lc-field">
        <label class="lc-label">Loan Amount</label>
        <div class="lc-input-wrap">
          <span class="lc-input-prefix">$</span>
          <input type="number" class="lc-input has-prefix" id="lcAmount" value="250000" min="0" step="1000">
        </div>
      </div>
      <div class="lc-field">
        <label class="lc-label">Annual Interest Rate</label>
        <div class="lc-input-wrap">
          <input type="number" class="lc-input has-suffix" id="lcRate" value="6.5" min="0" max="100" step="0.01">
          <span class="lc-input-suffix">%</span>
        </div>
      </div>
      <div class="lc-row">
        <div class="lc-field">
          <label class="lc-label">Loan Term (Years)</label>
          <input type="number" class="lc-input" id="lcYears" value="30" min="0" max="50" step="1">
        </div>
        <div class="lc-field">
          <label class="lc-label">Additional Months</label>
          <input type="number" class="lc-input" id="lcMonths" value="0" min="0" max="11" step="1">
        </div>
      </div>
      <div class="lc-field">
        <label class="lc-label">Start Date</label>
        <input type="date" class="lc-input" id="lcStartDate" style="font-family:'Inter',sans-serif;font-size:0.9rem;">
      </div>
    </div>

    <div class="lc-card">
      <div class="lc-card-title">Extra Payments</div>
      <div class="lc-field">
        <label class="lc-label">Additional Monthly Payment</label>
        <div class="lc-input-wrap">
          <span class="lc-input-prefix">$</span>
          <input type="number" class="lc-input has-prefix" id="lcExtra" value="0" min="0" step="50">
        </div>
      </div>
      <p style="font-size:0.82rem;color:var(--lc-text-muted);margin:8px 0 0;line-height:1.6;">Enter an extra monthly amount to see how much interest you save and how many months earlier you pay off the loan.</p>

      <div class="lc-savings" id="lcSavings">
        <p class="lc-savings-title">Extra Payment Savings</p>
        <div class="lc-savings-grid">
          <div>
            <p class="lc-savings-item-label">Interest Saved</p>
            <p class="lc-savings-item-value" id="lcSavedInterest">$0</p>
          </div>
          <div>
            <p class="lc-savings-item-label">Time Saved</p>
            <p class="lc-savings-item-value" id="lcSavedTime">0 months</p>
          </div>
          <div>
            <p class="lc-savings-item-label">New Payoff</p>
            <p class="lc-savings-item-value" id="lcNewPayoff">-</p>
          </div>
        </div>
      </div>
    </div>

  </div>

  <!-- Results -->
  <div class="lc-results">
    <div class="lc-result-card">
      <p class="lc-result-label">Monthly Payment</p>
      <p class="lc-result-value purple" id="lcPayment">$0</p>
    </div>
    <div class="lc-result-card">
      <p class="lc-result-label">Total Payment</p>
      <p class="lc-result-value" id="lcTotalPayment">$0</p>
    </div>
    <div class="lc-result-card">
      <p class="lc-result-label">Total Interest</p>
      <p class="lc-result-value red" id="lcTotalInterest">$0</p>
    </div>
    <div class="lc-result-card">
      <p class="lc-result-label">Payoff Date</p>
      <p class="lc-result-value green" id="lcPayoffDate" style="font-size:1.2rem;">-</p>
    </div>
  </div>

  <!-- Buttons -->
  <div class="lc-btn-row">
    <button type="button" class="lc-btn lc-btn-primary" onclick="lcReset()">Reset</button>
    <button type="button" class="lc-compare-toggle" id="lcCompareBtn" onclick="lcToggleCompare()">Compare Two Loans</button>
  </div>

  <!-- Compare Mode -->
  <div class="lc-compare-wrap" id="lcCompareWrap">
    <div class="lc-compare-inputs">
      <div class="lc-card">
        <div class="lc-card-title">Scenario B</div>
        <div class="lc-field">
          <label class="lc-label">Loan Amount</label>
          <div class="lc-input-wrap">
            <span class="lc-input-prefix">$</span>
            <input type="number" class="lc-input has-prefix" id="lcAmount2" value="250000" min="0" step="1000">
          </div>
        </div>
        <div class="lc-field">
          <label class="lc-label">Annual Interest Rate</label>
          <div class="lc-input-wrap">
            <input type="number" class="lc-input has-suffix" id="lcRate2" value="5.5" min="0" max="100" step="0.01">
            <span class="lc-input-suffix">%</span>
          </div>
        </div>
        <div class="lc-row">
          <div class="lc-field">
            <label class="lc-label">Term (Years)</label>
            <input type="number" class="lc-input" id="lcYears2" value="15" min="0" max="50" step="1">
          </div>
          <div class="lc-field">
            <label class="lc-label">Extra Months</label>
            <input type="number" class="lc-input" id="lcMonths2" value="0" min="0" max="11" step="1">
          </div>
        </div>
      </div>
      <div class="lc-card" style="display:flex;align-items:center;">
        <table class="lc-compare-table" id="lcCompareTable">
          <thead>
            <tr>
              <th>Metric</th>
              <th>Scenario A</th>
              <th>Scenario B</th>
            </tr>
          </thead>
          <tbody id="lcCompareBody">
          </tbody>
        </table>
      </div>
    </div>
  </div>

  <!-- Charts -->
  <div class="lc-charts">
    <div class="lc-chart-card">
      <p class="lc-chart-title">Balance, Principal & Interest Over Time</p>
      <div class="lc-canvas-wrap">
        <canvas id="lcAreaChart" height="300"></canvas>
      </div>
    </div>
    <div class="lc-chart-card lc-donut-wrap">
      <p class="lc-chart-title">Total Cost Breakdown</p>
      <div class="lc-canvas-wrap" style="max-width:220px;">
        <canvas id="lcDonutChart" height="220" width="220"></canvas>
      </div>
      <div class="lc-donut-legend" id="lcDonutLegend">
        <div class="lc-legend-item">
          <span class="lc-legend-dot" style="background:#6C5CE7;"></span>
          <span>Principal</span>
          <span class="lc-legend-value" id="lcLegPrincipal">$0</span>
        </div>
        <div class="lc-legend-item">
          <span class="lc-legend-dot" style="background:#ff4466;"></span>
          <span>Interest</span>
          <span class="lc-legend-value" id="lcLegInterest">$0</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Payment Breakdown Donut -->
  <div class="lc-charts" style="grid-template-columns:1fr 1fr;">
    <div class="lc-chart-card lc-donut-wrap">
      <p class="lc-chart-title">First Payment Breakdown</p>
      <div class="lc-canvas-wrap" style="max-width:200px;">
        <canvas id="lcFirstPayDonut" height="200" width="200"></canvas>
      </div>
      <div class="lc-donut-legend" id="lcFirstPayLegend">
        <div class="lc-legend-item">
          <span class="lc-legend-dot" style="background:#6C5CE7;"></span>
          <span>Principal</span>
          <span class="lc-legend-value" id="lcFPPrincipal">$0</span>
        </div>
        <div class="lc-legend-item">
          <span class="lc-legend-dot" style="background:#ff4466;"></span>
          <span>Interest</span>
          <span class="lc-legend-value" id="lcFPInterest">$0</span>
        </div>
      </div>
    </div>
    <div class="lc-chart-card lc-donut-wrap">
      <p class="lc-chart-title">Last Payment Breakdown</p>
      <div class="lc-canvas-wrap" style="max-width:200px;">
        <canvas id="lcLastPayDonut" height="200" width="200"></canvas>
      </div>
      <div class="lc-donut-legend" id="lcLastPayLegend">
        <div class="lc-legend-item">
          <span class="lc-legend-dot" style="background:#6C5CE7;"></span>
          <span>Principal</span>
          <span class="lc-legend-value" id="lcLPPrincipal">$0</span>
        </div>
        <div class="lc-legend-item">
          <span class="lc-legend-dot" style="background:#ff4466;"></span>
          <span>Interest</span>
          <span class="lc-legend-value" id="lcLPInterest">$0</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Amortization Table -->
  <div class="lc-amort-wrap">
    <div class="lc-amort-header">
      <h3>Amortization Schedule</h3>
      <button type="button" class="lc-export-btn" onclick="lcExportCSV()">Export CSV</button>
    </div>
    <div class="lc-amort-scroll">
      <table class="lc-amort-table">
        <thead>
          <tr>
            <th>Month</th>
            <th>Payment</th>
            <th>Principal</th>
            <th>Interest</th>
            <th>Extra</th>
            <th>Balance</th>
          </tr>
        </thead>
        <tbody id="lcAmortBody">
        </tbody>
      </table>
    </div>
  </div>

  <div class="lc-updated">Last updated: March 2026</div>

  <!-- Cross Links -->
  <div class="lc-cross-links">
    <a href="/tools/compound-interest-calculator/" class="lc-cross-link">Compound Interest Calculator</a>
    <a href="/tools/percentage-calculator/" class="lc-cross-link">Percentage Calculator</a>
    <a href="/tools/gpa-calculator/" class="lc-cross-link">GPA Calculator</a>
    <a href="/tools/invoice-generator/" class="lc-cross-link">Invoice Generator</a>
  </div>

  <!-- SEO Content -->
  <div class="lc-content">

<h2>What Is a Loan Calculator</h2>

<p>A loan calculator is a tool that computes the monthly payment required to pay off a fixed-rate loan over a specified term. Given a principal amount, an annual interest rate, and a number of months, it applies the standard amortization formula to produce a single monthly figure that covers both principal repayment and interest charges. The result tells you what you will owe each month from the first payment to the last.</p>

<p>The formula behind it is straightforward. If P is the loan principal, r is the monthly interest rate (annual rate divided by 12), and n is the total number of monthly payments, then the monthly payment M equals:</p>

<div class="lc-formula-block">
M = P * [r(1 + r)^n] / [(1 + r)^n - 1]
</div>

<p>This formula assumes fixed-rate, fully amortizing payments. Each payment is the same amount, but the split between principal and interest shifts over time. Early payments are mostly interest because the outstanding balance is large. Later payments are mostly principal because the balance has shrunk. The calculator above shows this shift in the amortization table and in the stacked area chart.</p>

<p>Loan calculators are useful for mortgages, auto loans, personal loans, student loans, and any other installment debt with a fixed rate and term. You can use one to determine whether a monthly payment fits your budget, to compare offers from different lenders, or to evaluate the cost difference between a 15-year and 30-year mortgage.</p>

<h2>How Loan Amortization Works</h2>

<p>Amortization is the process of paying off a loan through scheduled, equal payments over time. Each payment consists of two parts: an interest charge on the current outstanding balance and a principal reduction that shrinks the balance for the next month.</p>

<p>Consider a $200,000 loan at 6% annual interest (0.5% monthly) over 30 years (360 payments). The monthly payment works out to $1,199.10. In month one, the interest charge is $200,000 times 0.005, which equals $1,000. The remaining $199.10 goes toward principal. The new balance is $199,800.90. In month two, interest is $999.00 (slightly less, because the balance decreased), and $200.10 goes to principal. This pattern continues, with the interest portion shrinking and the principal portion growing each month.</p>

<p>By month 360, nearly the entire payment goes to principal, and the final interest charge is just a few dollars. The amortization table above shows this progression for your specific loan inputs. You can scroll through every month and see exactly how the balance decreases.</p>

<p>This structure has a practical implication for borrowers: most of the interest you will pay over the life of a loan is concentrated in the early years. On a 30-year mortgage at 6%, you will have paid roughly half the total interest by year 10, even though you still have 20 years of payments remaining. This is why early extra payments have such a large impact on total interest cost.</p>

<h2>Fixed vs Variable Interest Rates</h2>

<p>A fixed-rate loan locks in the interest rate for the entire term. Your monthly payment never changes, which makes budgeting predictable. The calculator on this page models fixed-rate loans because the math is deterministic. You can see every future payment before signing the loan agreement.</p>

<p>A variable-rate loan (also called an adjustable-rate loan) ties the interest rate to a benchmark index, such as SOFR or the prime rate. The rate, and therefore the payment, can change at specified intervals (annually, for example). Variable rates often start lower than fixed rates, which reduces the initial payment. The trade-off is uncertainty: if interest rates rise, your payment increases.</p>

<p>Common hybrid products include the 5/1 ARM (adjustable rate mortgage), which fixes the rate for the first five years and then adjusts annually. Borrowers who plan to sell or refinance within five years sometimes choose this structure to benefit from the lower initial rate.</p>

<p>When comparing fixed and variable rates, consider your risk tolerance and how long you plan to hold the loan. If you intend to keep a mortgage for 25 years, a fixed rate protects you from rising rates. If you plan to move in three years, a variable rate's lower starting point may save money. Use the compare mode above to model both scenarios.</p>

<h2>How Extra Payments Save Money</h2>

<p>Making additional payments beyond the required monthly amount reduces your outstanding principal faster. Because interest is calculated on the remaining balance, a lower balance means less interest in every subsequent month. The compounding effect is significant.</p>

<p>On a $300,000 mortgage at 6.5% over 30 years, the standard monthly payment is $1,896.20. Total interest over the life of the loan is $382,633. Adding just $200 per month in extra principal payments reduces total interest to $272,937 and cuts the loan term from 30 years to about 23 years and 4 months. That $200 per month in extra payments saves $109,696 in interest and eliminates nearly 7 years of payments.</p>

<p>The earlier you start making extra payments, the greater the savings. An extra $200 per month starting in year one saves more than the same extra payment starting in year ten, because the balance is higher and there are more remaining months for the reduced interest to compound.</p>

<p>Enter your extra monthly payment amount in the calculator above to see the exact impact on your loan. The savings panel shows how much interest you avoid, how many months you shave off, and when the loan will be paid off.</p>

<h2>Understanding APR vs Interest Rate</h2>

<p>The interest rate is the cost of borrowing the principal, expressed as an annual percentage. It determines the interest portion of your monthly payment. The APR (Annual Percentage Rate) includes the interest rate plus certain fees and costs associated with the loan, spread over the loan term. APR gives a more complete picture of the total cost of borrowing.</p>

<p>Fees commonly included in APR calculations are origination fees, discount points, mortgage insurance, and certain closing costs. Fees that are typically excluded include title insurance, appraisal fees, and home inspection costs. The exact rules for what goes into APR are set by the Truth in Lending Act (TILA) in the United States.</p>

<p>When comparing two loan offers, APR is more useful than the interest rate alone. Lender A might offer 6.25% interest with $3,000 in fees, while Lender B offers 6.5% with no fees. The APR calculation reveals which option costs less over the loan term. A lower interest rate does not always mean a cheaper loan if it comes with high upfront costs.</p>

<p>The calculator on this page uses the nominal interest rate (not APR) for its calculations, because it computes payment amounts rather than total cost comparisons. If you want to model the impact of fees, add them to the loan amount or use the compare mode to evaluate different rate scenarios.</p>

<h2>Choosing the Right Loan Term</h2>

<p>The loan term is the number of months over which you repay the loan. Shorter terms mean higher monthly payments but less total interest. Longer terms mean lower monthly payments but more total interest. The choice depends on your cash flow, financial goals, and the size of the loan.</p>

<p>A 15-year mortgage at 6% on $250,000 requires a monthly payment of $2,109.64 and total interest of $129,735. The same loan over 30 years requires only $1,498.88 per month but costs $289,595 in total interest. The 30-year option is $610.76 easier on your monthly budget but costs $159,860 more over the life of the loan.</p>

<p>For auto loans, common terms range from 36 to 72 months. A 36-month term at 5% on $30,000 costs $899.13 per month with $2,368.58 in interest. Stretching to 72 months drops the payment to $483.15 but increases total interest to $4,786.90. The shorter term costs about $416 more per month but saves $2,418 in interest.</p>

<p>Use the compare mode in the calculator above to see side-by-side numbers for two different terms. The table shows monthly payment, total payment, and total interest for each scenario so you can evaluate the trade-off directly.</p>

  </div>

  <!-- FAQ Section -->
  <div class="lc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="lc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How is the monthly payment calculated?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The calculator uses the standard amortization formula: M = P[r(1+r)^n] / [(1+r)^n - 1], where P is the loan principal, r is the monthly interest rate (annual rate divided by 12), and n is the total number of payments. This produces a fixed monthly payment that fully pays off the loan by the end of the term.</p>
      </div>
    </div>

    <div class="lc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does extra payment go entirely toward principal?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Extra payments are applied directly to the outstanding principal balance. Your regular monthly payment still covers the required interest and principal. The extra amount reduces the balance further, which lowers the interest charged in all subsequent months. Over time this reduces both the total interest paid and the number of remaining payments.</p>
      </div>
    </div>

    <div class="lc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use this for mortgage, auto, and personal loans?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The formula applies to any fixed-rate, fully amortizing installment loan. Enter the loan amount, interest rate, and term for your specific loan type. Mortgages typically use 15 or 30 year terms. Auto loans usually range from 3 to 6 years. Personal loans are often 2 to 7 years.</p>
      </div>
    </div>

    <div class="lc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between principal and interest?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Principal is the original amount borrowed. Interest is the cost of borrowing that money, expressed as a percentage of the outstanding balance. Each monthly payment includes both a principal portion (which reduces your balance) and an interest portion (which is the lender's charge). Early in the loan, interest makes up most of the payment. Over time, the principal portion grows as the balance shrinks.</p>
      </div>
    </div>

    <div class="lc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is this calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The calculations match the standard amortization formula used by lenders. Actual loan payments may differ slightly due to rounding conventions, specific fee structures, escrow requirements, or variable rate adjustments. For fixed-rate loans, this calculator produces results that are accurate to the penny for the mathematical model. Always confirm final terms with your lender.</p>
      </div>
    </div>

    <div class="lc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data private?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All calculations happen in your browser using JavaScript. No data is sent to any server, no information is stored, and no cookies are set. You can verify this by monitoring the Network tab in your browser's developer tools. Your financial inputs never leave your device.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="lc-author-box">
    <div class="lc-author-avatar">ML</div>
    <div class="lc-author-info">
      <p class="lc-author-name">Michael Lip</p>
      <p class="lc-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="lc-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var elAmount = document.getElementById("lcAmount");
  var elRate = document.getElementById("lcRate");
  var elYears = document.getElementById("lcYears");
  var elMonths = document.getElementById("lcMonths");
  var elStartDate = document.getElementById("lcStartDate");
  var elExtra = document.getElementById("lcExtra");
  var elAmount2 = document.getElementById("lcAmount2");
  var elRate2 = document.getElementById("lcRate2");
  var elYears2 = document.getElementById("lcYears2");
  var elMonths2 = document.getElementById("lcMonths2");

  var compareMode = false;
  var debounceTimer = null;
  var amortData = [];

  // Set default start date
  var today = new Date();
  elStartDate.value = today.toISOString().split("T")[0];

  // --- Loan math ---
  function calcLoan(principal, annualRate, totalMonths, extraMonthly) {
    if (principal <= 0 || totalMonths <= 0) {
      return { payment: 0, totalPaid: 0, totalInterest: 0, months: 0, schedule: [] };
    }

    var r = (annualRate / 100) / 12;
    var n = totalMonths;
    var payment;

    if (r === 0) {
      payment = principal / n;
    } else {
      var rn = Math.pow(1 + r, n);
      payment = principal * (r * rn) / (rn - 1);
    }

    var balance = principal;
    var schedule = [];
    var totalPaid = 0;
    var totalInterest = 0;
    var month = 0;

    while (balance > 0.005 && month < 600) {
      month++;
      var interestPmt = balance * r;
      var principalPmt = payment - interestPmt;
      var extra = extraMonthly || 0;

      // Ensure we don't overpay
      if (principalPmt + extra > balance) {
        extra = Math.max(0, balance - principalPmt);
        if (principalPmt > balance) {
          principalPmt = balance;
          extra = 0;
        }
      }

      balance = balance - principalPmt - extra;
      if (balance < 0.005) balance = 0;

      var totalPmt = interestPmt + principalPmt + extra;
      totalPaid += totalPmt;
      totalInterest += interestPmt;

      schedule.push({
        month: month,
        payment: interestPmt + principalPmt,
        principal: principalPmt,
        interest: interestPmt,
        extra: extra,
        balance: balance
      });

      if (balance <= 0) break;
    }

    return {
      payment: payment,
      totalPaid: totalPaid,
      totalInterest: totalInterest,
      months: month,
      schedule: schedule,
      principal: principal
    };
  }

  function formatCurrency(n) {
    return "$" + n.toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ",");
  }

  function formatCurrencyShort(n) {
    if (n >= 1000000) return "$" + (n / 1000000).toFixed(1) + "M";
    if (n >= 1000) return "$" + (n / 1000).toFixed(1) + "K";
    return "$" + n.toFixed(0);
  }

  function formatDate(dateStr, addMonths) {
    var d = dateStr ? new Date(dateStr + "T00:00:00") : new Date();
    d.setMonth(d.getMonth() + addMonths);
    var months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];
    return months[d.getMonth()] + " " + d.getFullYear();
  }

  // --- Update ---
  function update() {
    var P = parseFloat(elAmount.value) || 0;
    var rate = parseFloat(elRate.value) || 0;
    var years = parseInt(elYears.value) || 0;
    var months = parseInt(elMonths.value) || 0;
    var extra = parseFloat(elExtra.value) || 0;
    var n = years * 12 + months;

    // Base loan (no extra)
    var base = calcLoan(P, rate, n, 0);
    // With extra
    var withExtra = calcLoan(P, rate, n, extra);

    amortData = withExtra.schedule;

    // Update results
    document.getElementById("lcPayment").textContent = formatCurrency(base.payment);
    document.getElementById("lcTotalPayment").textContent = formatCurrency(withExtra.totalPaid);
    document.getElementById("lcTotalInterest").textContent = formatCurrency(withExtra.totalInterest);
    document.getElementById("lcPayoffDate").textContent = formatDate(elStartDate.value, withExtra.months);

    // Extra payment savings
    var savingsEl = document.getElementById("lcSavings");
    if (extra > 0 && n > 0 && P > 0) {
      savingsEl.classList.add("visible");
      var savedInterest = base.totalInterest - withExtra.totalInterest;
      var savedMonths = base.months - withExtra.months;
      document.getElementById("lcSavedInterest").textContent = formatCurrency(savedInterest);

      var savedYrs = Math.floor(savedMonths / 12);
      var savedMos = savedMonths % 12;
      var timeStr = "";
      if (savedYrs > 0) timeStr += savedYrs + (savedYrs === 1 ? " yr " : " yrs ");
      timeStr += savedMos + (savedMos === 1 ? " mo" : " mos");
      document.getElementById("lcSavedTime").textContent = timeStr;
      document.getElementById("lcNewPayoff").textContent = formatDate(elStartDate.value, withExtra.months);
    } else {
      savingsEl.classList.remove("visible");
    }

    // Charts
    drawAreaChart(withExtra);
    drawDonut("lcDonutChart", P, withExtra.totalInterest);
    document.getElementById("lcLegPrincipal").textContent = formatCurrency(P);
    document.getElementById("lcLegInterest").textContent = formatCurrency(withExtra.totalInterest);

    // Payment breakdown donuts
    if (withExtra.schedule.length > 0) {
      var first = withExtra.schedule[0];
      var last = withExtra.schedule[withExtra.schedule.length - 1];
      drawDonut("lcFirstPayDonut", first.principal, first.interest);
      document.getElementById("lcFPPrincipal").textContent = formatCurrency(first.principal);
      document.getElementById("lcFPInterest").textContent = formatCurrency(first.interest);
      drawDonut("lcLastPayDonut", last.principal, last.interest);
      document.getElementById("lcLPPrincipal").textContent = formatCurrency(last.principal);
      document.getElementById("lcLPInterest").textContent = formatCurrency(last.interest);
    }

    // Amortization table
    renderAmort(withExtra.schedule);

    // Compare
    if (compareMode) updateCompare(base);
  }

  // --- Amortization Table ---
  function renderAmort(schedule) {
    var tbody = document.getElementById("lcAmortBody");
    var html = "";
    for (var i = 0; i < schedule.length; i++) {
      var s = schedule[i];
      html += "<tr><td>" + s.month + "</td>" +
        "<td>" + formatCurrency(s.payment + s.extra) + "</td>" +
        "<td>" + formatCurrency(s.principal) + "</td>" +
        "<td>" + formatCurrency(s.interest) + "</td>" +
        "<td>" + (s.extra > 0 ? formatCurrency(s.extra) : "-") + "</td>" +
        "<td>" + formatCurrency(s.balance) + "</td></tr>";
    }
    tbody.innerHTML = html;
  }

  // --- Area Chart ---
  function drawAreaChart(result) {
    var canvas = document.getElementById("lcAreaChart");
    var ctx = canvas.getContext("2d");
    var dpr = window.devicePixelRatio || 1;
    var rect = canvas.getBoundingClientRect();
    canvas.width = rect.width * dpr;
    canvas.height = 300 * dpr;
    ctx.scale(dpr, dpr);

    var W = rect.width;
    var H = 300;
    var pad = { top: 20, right: 20, bottom: 40, left: 60 };
    var plotW = W - pad.left - pad.right;
    var plotH = H - pad.top - pad.bottom;

    ctx.clearRect(0, 0, W, H);

    var schedule = result.schedule;
    if (schedule.length === 0) return;

    // Build cumulative data
    var data = [];
    var cumPrincipal = 0;
    var cumInterest = 0;
    for (var i = 0; i < schedule.length; i++) {
      cumPrincipal += schedule[i].principal + schedule[i].extra;
      cumInterest += schedule[i].interest;
      data.push({
        month: schedule[i].month,
        balance: schedule[i].balance,
        cumPrincipal: cumPrincipal,
        cumInterest: cumInterest
      });
    }

    var maxMonth = data[data.length - 1].month;
    var maxVal = result.principal * 1.05;
    for (var j = 0; j < data.length; j++) {
      var total = data[j].cumPrincipal + data[j].cumInterest;
      if (total > maxVal) maxVal = total;
    }

    function xPos(m) { return pad.left + (m / maxMonth) * plotW; }
    function yPos(v) { return pad.top + plotH - (v / maxVal) * plotH; }

    // Grid lines
    ctx.strokeStyle = "#1e1e2e";
    ctx.lineWidth = 1;
    for (var g = 0; g <= 5; g++) {
      var gy = pad.top + (plotH / 5) * g;
      ctx.beginPath();
      ctx.moveTo(pad.left, gy);
      ctx.lineTo(W - pad.right, gy);
      ctx.stroke();
    }

    // Y-axis labels
    ctx.font = "11px JetBrains Mono, monospace";
    ctx.fillStyle = "#8888aa";
    ctx.textAlign = "right";
    ctx.textBaseline = "middle";
    for (var y = 0; y <= 5; y++) {
      var val = (maxVal / 5) * (5 - y);
      var yy = pad.top + (plotH / 5) * y;
      ctx.fillText(formatCurrencyShort(val), pad.left - 8, yy);
    }

    // X-axis labels
    ctx.textAlign = "center";
    ctx.textBaseline = "top";
    var xSteps = Math.min(6, maxMonth);
    for (var x = 0; x <= xSteps; x++) {
      var mo = Math.round((maxMonth / xSteps) * x);
      var xx = xPos(mo);
      var yrs = Math.floor(mo / 12);
      var mos = mo % 12;
      var label = yrs > 0 ? yrs + "y" : "";
      if (mos > 0) label += (label ? " " : "") + mos + "m";
      if (mo === 0) label = "0";
      ctx.fillText(label, xx, H - pad.bottom + 8);
    }

    // Stacked area: interest (bottom) + principal (top)
    // Draw interest area
    ctx.beginPath();
    ctx.moveTo(xPos(0), yPos(0));
    for (var a = 0; a < data.length; a++) {
      ctx.lineTo(xPos(data[a].month), yPos(data[a].cumInterest));
    }
    ctx.lineTo(xPos(data[data.length - 1].month), yPos(0));
    ctx.closePath();
    ctx.fillStyle = "rgba(255, 68, 102, 0.25)";
    ctx.fill();

    // Draw principal area (stacked on top of interest)
    ctx.beginPath();
    ctx.moveTo(xPos(0), yPos(0));
    for (var b = 0; b < data.length; b++) {
      ctx.lineTo(xPos(data[b].month), yPos(data[b].cumInterest));
    }
    for (var c = data.length - 1; c >= 0; c--) {
      ctx.lineTo(xPos(data[c].month), yPos(data[c].cumPrincipal + data[c].cumInterest));
    }
    ctx.closePath();
    ctx.fillStyle = "rgba(108, 92, 231, 0.25)";
    ctx.fill();

    // Balance line
    ctx.beginPath();
    ctx.moveTo(xPos(0), yPos(result.principal));
    for (var d = 0; d < data.length; d++) {
      ctx.lineTo(xPos(data[d].month), yPos(data[d].balance));
    }
    ctx.strokeStyle = "#00ff88";
    ctx.lineWidth = 2;
    ctx.stroke();

    // Interest area border
    ctx.beginPath();
    for (var e = 0; e < data.length; e++) {
      if (e === 0) ctx.moveTo(xPos(data[e].month), yPos(data[e].cumInterest));
      else ctx.lineTo(xPos(data[e].month), yPos(data[e].cumInterest));
    }
    ctx.strokeStyle = "rgba(255, 68, 102, 0.6)";
    ctx.lineWidth = 1.5;
    ctx.stroke();

    // Principal+Interest area border
    ctx.beginPath();
    for (var f = 0; f < data.length; f++) {
      var cv = data[f].cumPrincipal + data[f].cumInterest;
      if (f === 0) ctx.moveTo(xPos(data[f].month), yPos(cv));
      else ctx.lineTo(xPos(data[f].month), yPos(cv));
    }
    ctx.strokeStyle = "rgba(108, 92, 231, 0.6)";
    ctx.lineWidth = 1.5;
    ctx.stroke();

    // Legend
    ctx.font = "11px Inter, sans-serif";
    ctx.textAlign = "left";
    ctx.textBaseline = "middle";
    var legX = pad.left + 10;
    var legY = pad.top + 10;

    // Balance
    ctx.fillStyle = "#00ff88";
    ctx.fillRect(legX, legY - 4, 12, 8);
    ctx.fillStyle = "#8888aa";
    ctx.fillText("Balance", legX + 18, legY);

    // Principal
    ctx.fillStyle = "rgba(108, 92, 231, 0.5)";
    ctx.fillRect(legX + 80, legY - 4, 12, 8);
    ctx.fillStyle = "#8888aa";
    ctx.fillText("Cum. Principal", legX + 98, legY);

    // Interest
    ctx.fillStyle = "rgba(255, 68, 102, 0.5)";
    ctx.fillRect(legX + 200, legY - 4, 12, 8);
    ctx.fillStyle = "#8888aa";
    ctx.fillText("Cum. Interest", legX + 218, legY);
  }

  // --- Donut Chart ---
  function drawDonut(canvasId, val1, val2) {
    var canvas = document.getElementById(canvasId);
    var ctx = canvas.getContext("2d");
    var dpr = window.devicePixelRatio || 1;
    var size = canvas.getBoundingClientRect().width;
    canvas.width = size * dpr;
    canvas.height = size * dpr;
    ctx.scale(dpr, dpr);

    var cx = size / 2;
    var cy = size / 2;
    var radius = size / 2 - 10;
    var innerRadius = radius * 0.6;

    ctx.clearRect(0, 0, size, size);

    var total = val1 + val2;
    if (total === 0) {
      // Empty donut
      ctx.beginPath();
      ctx.arc(cx, cy, radius, 0, Math.PI * 2);
      ctx.arc(cx, cy, innerRadius, 0, Math.PI * 2, true);
      ctx.fillStyle = "#1e1e2e";
      ctx.fill();
      return;
    }

    var angle1 = (val1 / total) * Math.PI * 2;
    var startAngle = -Math.PI / 2;

    // Principal slice
    ctx.beginPath();
    ctx.arc(cx, cy, radius, startAngle, startAngle + angle1);
    ctx.arc(cx, cy, innerRadius, startAngle + angle1, startAngle, true);
    ctx.closePath();
    ctx.fillStyle = "#6C5CE7";
    ctx.fill();

    // Interest slice
    ctx.beginPath();
    ctx.arc(cx, cy, radius, startAngle + angle1, startAngle + Math.PI * 2);
    ctx.arc(cx, cy, innerRadius, startAngle + Math.PI * 2, startAngle + angle1, true);
    ctx.closePath();
    ctx.fillStyle = "#ff4466";
    ctx.fill();

    // Center text
    var pct = Math.round((val1 / total) * 100);
    ctx.fillStyle = "#e0e0e0";
    ctx.font = "bold 16px JetBrains Mono, monospace";
    ctx.textAlign = "center";
    ctx.textBaseline = "middle";
    ctx.fillText(pct + "%", cx, cy - 6);
    ctx.font = "10px Inter, sans-serif";
    ctx.fillStyle = "#8888aa";
    ctx.fillText("Principal", cx, cy + 10);
  }

  // --- Compare Mode ---
  window.lcToggleCompare = function() {
    compareMode = !compareMode;
    var wrap = document.getElementById("lcCompareWrap");
    var btn = document.getElementById("lcCompareBtn");
    if (compareMode) {
      wrap.classList.add("visible");
      btn.classList.add("active");
      btn.textContent = "Hide Comparison";
    } else {
      wrap.classList.remove("visible");
      btn.classList.remove("active");
      btn.textContent = "Compare Two Loans";
    }
    update();
  };

  function updateCompare(baseA) {
    var P2 = parseFloat(elAmount2.value) || 0;
    var rate2 = parseFloat(elRate2.value) || 0;
    var years2 = parseInt(elYears2.value) || 0;
    var months2 = parseInt(elMonths2.value) || 0;
    var n2 = years2 * 12 + months2;

    var loanB = calcLoan(P2, rate2, n2, 0);

    var rows = [
      ["Monthly Payment", baseA.payment, loanB.payment, "lower"],
      ["Total Payment", baseA.totalPaid, loanB.totalPaid, "lower"],
      ["Total Interest", baseA.totalInterest, loanB.totalInterest, "lower"],
      ["Loan Term", baseA.months, loanB.months, "lower"],
      ["Principal", baseA.principal || 0, loanB.principal || 0, "none"]
    ];

    var tbody = document.getElementById("lcCompareBody");
    var html = "";
    for (var i = 0; i < rows.length; i++) {
      var label = rows[i][0];
      var aVal = rows[i][1];
      var bVal = rows[i][2];
      var better = rows[i][3];

      var aStr, bStr;
      if (label === "Loan Term") {
        aStr = Math.floor(aVal / 12) + "y " + (aVal % 12) + "m";
        bStr = Math.floor(bVal / 12) + "y " + (bVal % 12) + "m";
      } else {
        aStr = formatCurrency(aVal);
        bStr = formatCurrency(bVal);
      }

      var aClass = "", bClass = "";
      if (better === "lower") {
        if (aVal < bVal) aClass = "lc-compare-better";
        else if (bVal < aVal) bClass = "lc-compare-better";
      }

      html += "<tr><td>" + label + "</td>" +
        "<td class='" + aClass + "'>" + aStr + "</td>" +
        "<td class='" + bClass + "'>" + bStr + "</td></tr>";
    }
    tbody.innerHTML = html;
  }

  // --- Export CSV ---
  window.lcExportCSV = function() {
    if (amortData.length === 0) return;
    var csv = "Month,Payment,Principal,Interest,Extra Payment,Balance\n";
    for (var i = 0; i < amortData.length; i++) {
      var s = amortData[i];
      csv += s.month + "," +
        (s.payment + s.extra).toFixed(2) + "," +
        s.principal.toFixed(2) + "," +
        s.interest.toFixed(2) + "," +
        s.extra.toFixed(2) + "," +
        s.balance.toFixed(2) + "\n";
    }

    var blob = new Blob([csv], { type: "text/csv" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "amortization-schedule.csv";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  // --- Reset ---
  window.lcReset = function() {
    elAmount.value = "250000";
    elRate.value = "6.5";
    elYears.value = "30";
    elMonths.value = "0";
    elExtra.value = "0";
    elStartDate.value = today.toISOString().split("T")[0];
    elAmount2.value = "250000";
    elRate2.value = "5.5";
    elYears2.value = "15";
    elMonths2.value = "0";
    if (compareMode) lcToggleCompare();
    update();
  };

  // --- Debounced input ---
  function debouncedUpdate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(update, 150);
  }

  var allInputs = [elAmount, elRate, elYears, elMonths, elStartDate, elExtra, elAmount2, elRate2, elYears2, elMonths2];
  for (var i = 0; i < allInputs.length; i++) {
    allInputs[i].addEventListener("input", debouncedUpdate);
    allInputs[i].addEventListener("change", debouncedUpdate);
  }

  // --- Resize ---
  var resizeTimer = null;
  window.addEventListener("resize", function() {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(update, 200);
  });

  // --- Initial ---
  update();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Loan Calculator",
      "description": "Calculate monthly loan payments, total interest, and view amortization schedules. Compare loan terms, see payoff dates, and plan extra payments.",
      "url": "https://theluckystrike.github.io/tools/loan-calculator/",
      "applicationCategory": "FinanceApplication",
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
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/"},
        {"@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/"},
        {"@type": "ListItem", "position": 3, "name": "Loan Calculator", "item": "https://theluckystrike.github.io/tools/loan-calculator/"}
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
          "name": "How is the monthly payment calculated?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The calculator uses the standard amortization formula: M = P[r(1+r)^n] / [(1+r)^n - 1], where P is the loan principal, r is the monthly interest rate, and n is the total number of payments."
          }
        },
        {
          "@type": "Question",
          "name": "Does extra payment go entirely toward principal?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Extra payments are applied directly to the outstanding principal balance, reducing the interest charged in all subsequent months and shortening the loan term."
          }
        },
        {
          "@type": "Question",
          "name": "Can I use this for mortgage, auto, and personal loans?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. The formula applies to any fixed-rate, fully amortizing installment loan including mortgages, auto loans, personal loans, and student loans."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between principal and interest?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Principal is the original amount borrowed. Interest is the cost of borrowing that money. Each monthly payment includes both a principal portion and an interest portion."
          }
        },
        {
          "@type": "Question",
          "name": "How accurate is this calculator?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The calculations match the standard amortization formula used by lenders. Actual payments may differ due to rounding conventions or fee structures. Always confirm final terms with your lender."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data private?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All calculations happen in your browser using JavaScript. No data is sent to any server, no information is stored, and no cookies are set."
          }
        }
      ]
    }
  ]
}
</script>
