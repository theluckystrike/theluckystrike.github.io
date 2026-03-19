---
layout: page
title: "Free Percentage Calculator — Discount, Tip, Markup & Change | Zovo"
description: "Calculate percentages instantly with 10 modes: percentage of a number, percentage change, tip calculator, discount calculator, markup, margin, tax, fraction to percent, and more."
permalink: /tools/percentage-calculator/
keywords: "percentage calculator, percent calculator, percentage change calculator, tip calculator, discount calculator, markup calculator, margin calculator, fraction to percent"
date: 2026-03-19
categories: [tools]
tags: [percentage, calculator, math, tip, discount, markup, margin, finance]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --pc-primary: #6C5CE7;
    --pc-primary-dark: #5A4BD1;
    --pc-primary-light: #A29BFE;
    --pc-bg: #0a0a0f;
    --pc-surface: #12121a;
    --pc-surface-alt: #181824;
    --pc-border: #1e1e2e;
    --pc-text: #e0e0e0;
    --pc-text-muted: #8888aa;
    --pc-green: #00ff88;
    --pc-green-dark: #00cc6a;
    --pc-red: #ff4466;
    --pc-radius: 12px;
    --pc-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .pc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--pc-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .pc-wrapper * {
    box-sizing: border-box;
  }

  .pc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .pc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--pc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .pc-hero h1 span {
    color: var(--pc-primary);
  }

  .pc-intro {
    font-size: 1.05rem;
    color: var(--pc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .pc-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--pc-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--pc-border);
    border-radius: 20px;
  }

  /* Calculator Grid */
  .pc-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 32px;
  }

  .pc-card {
    background: var(--pc-surface);
    border: 1px solid var(--pc-border);
    border-radius: var(--pc-radius);
    padding: 20px;
    box-shadow: var(--pc-shadow);
  }

  .pc-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--pc-text-muted);
    margin: 0 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .pc-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--pc-primary);
    border-radius: 2px;
  }

  .pc-field {
    margin-bottom: 12px;
  }

  .pc-field:last-child {
    margin-bottom: 0;
  }

  .pc-label {
    display: block;
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--pc-text-muted);
    margin-bottom: 4px;
  }

  .pc-input-row {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .pc-input-wrap {
    position: relative;
    display: flex;
    align-items: center;
    flex: 1;
  }

  .pc-input-suffix {
    position: absolute;
    right: 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--pc-text-muted);
    pointer-events: none;
    z-index: 1;
  }

  .pc-input-prefix {
    position: absolute;
    left: 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--pc-text-muted);
    pointer-events: none;
    z-index: 1;
  }

  .pc-input {
    width: 100%;
    padding: 9px 12px;
    background: var(--pc-bg);
    border: 1px solid var(--pc-border);
    border-radius: 8px;
    color: var(--pc-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    -moz-appearance: textfield;
  }

  .pc-input::-webkit-outer-spin-button,
  .pc-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  .pc-input:focus {
    border-color: var(--pc-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .pc-input.has-suffix {
    padding-right: 32px;
  }

  .pc-input.has-prefix {
    padding-left: 28px;
  }

  .pc-eq {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1rem;
    color: var(--pc-text-muted);
    flex-shrink: 0;
  }

  .pc-result {
    margin-top: 12px;
    padding: 10px 14px;
    background: var(--pc-surface-alt);
    border-radius: 8px;
    border: 1px solid var(--pc-border);
    font-family: 'JetBrains Mono', monospace;
    font-size: 1rem;
    color: var(--pc-green);
    min-height: 40px;
    display: flex;
    align-items: center;
    transition: color 0.2s ease;
  }

  .pc-result.negative {
    color: var(--pc-red);
  }

  .pc-result-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }

  .pc-result-label {
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
    color: var(--pc-text-muted);
    font-weight: 500;
  }

  .pc-result-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
  }

  .pc-result-multi {
    margin-top: 12px;
    padding: 10px 14px;
    background: var(--pc-surface-alt);
    border-radius: 8px;
    border: 1px solid var(--pc-border);
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .pc-direction {
    display: inline-block;
    padding: 1px 6px;
    border-radius: 4px;
    font-size: 0.75rem;
    font-weight: 600;
    margin-left: 6px;
  }

  .pc-direction.up {
    background: rgba(0, 255, 136, 0.12);
    color: var(--pc-green);
  }

  .pc-direction.down {
    background: rgba(255, 68, 102, 0.12);
    color: var(--pc-red);
  }

  /* Cross Links */
  .pc-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .pc-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--pc-surface);
    border: 1px solid var(--pc-border);
    border-radius: 8px;
    color: var(--pc-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .pc-cross-link:hover {
    border-color: var(--pc-primary);
    color: var(--pc-text);
  }

  /* Content */
  .pc-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .pc-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 2.5rem 0 1rem;
    color: var(--pc-text);
  }

  .pc-content p {
    font-size: 0.95rem;
    color: var(--pc-text-muted);
    line-height: 1.8;
    margin: 0 0 1rem;
  }

  .pc-content ul, .pc-content ol {
    color: var(--pc-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 1.5rem;
    margin: 0 0 1rem;
  }

  .pc-content li {
    margin-bottom: 0.4rem;
  }

  .pc-formula-block {
    background: var(--pc-surface);
    border: 1px solid var(--pc-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin: 1rem 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--pc-primary-light);
    overflow-x: auto;
  }

  /* Author Box */
  .pc-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--pc-surface);
    border: 1px solid var(--pc-border);
    border-radius: var(--pc-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .pc-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--pc-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .pc-author-info {
    flex: 1;
  }

  .pc-author-name {
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--pc-text);
    margin: 0 0 4px;
  }

  .pc-author-bio {
    font-size: 0.82rem;
    color: var(--pc-text-muted);
    line-height: 1.6;
    margin: 0;
  }

  /* FAQ */
  .pc-faq {
    max-width: 780px;
    margin: 2.5rem auto 0;
  }

  .pc-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 1.2rem;
    color: var(--pc-text);
  }

  .pc-faq-item {
    padding: 16px 0;
    border-bottom: 1px solid var(--pc-border);
  }

  .pc-faq-item:last-child {
    border-bottom: none;
  }

  .pc-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--pc-text);
  }

  .pc-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--pc-text-muted);
    line-height: 1.7;
  }

  /* Footer */
  .pc-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--pc-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--pc-border);
    margin-top: 3rem;
  }

  .pc-footer a {
    color: var(--pc-primary);
    text-decoration: none;
  }

  .pc-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .pc-hero h1 {
      font-size: 1.6rem;
    }

    .pc-grid {
      grid-template-columns: 1fr;
    }

    .pc-input-row {
      flex-wrap: wrap;
    }

    .pc-author-box {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
  }
</style>

<div class="pc-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Percentage Calculator">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="pc-hero">
    <h1><span>Percentage</span> Calculator</h1>
    <p class="pc-intro">Ten percentage calculation modes covering everyday math, tipping, discounts, markup, margin, tax, and fraction conversions. Every calculation runs in your browser as you type. Nothing is sent to a server.</p>
    <div class="pc-updated">Last updated: March 19, 2026</div>
  </div>

  <!-- Calculator Grid -->
  <div class="pc-grid">

    <!-- 1. X% of Y -->
    <div class="pc-card">
      <div class="pc-card-title">Percentage of a Number</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">What is</span>
          <div class="pc-input-wrap" style="max-width:100px;">
            <input type="number" id="pcOfPct" class="pc-input has-suffix" value="15" step="any">
            <span class="pc-input-suffix">%</span>
          </div>
          <span class="pc-label">of</span>
          <div class="pc-input-wrap">
            <input type="number" id="pcOfNum" class="pc-input" value="200" step="any">
          </div>
        </div>
      </div>
      <div class="pc-result" id="pcOfResult">= 30</div>
    </div>

    <!-- 2. X is what % of Y -->
    <div class="pc-card">
      <div class="pc-card-title">What Percent of</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <div class="pc-input-wrap">
            <input type="number" id="pcWhatX" class="pc-input" value="30" step="any">
          </div>
          <span class="pc-label">is what % of</span>
          <div class="pc-input-wrap">
            <input type="number" id="pcWhatY" class="pc-input" value="200" step="any">
          </div>
        </div>
      </div>
      <div class="pc-result" id="pcWhatResult">= 15%</div>
    </div>

    <!-- 3. Percentage Change -->
    <div class="pc-card">
      <div class="pc-card-title">Percentage Change</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">From</span>
          <div class="pc-input-wrap">
            <input type="number" id="pcChgFrom" class="pc-input" value="80" step="any">
          </div>
          <span class="pc-label">to</span>
          <div class="pc-input-wrap">
            <input type="number" id="pcChgTo" class="pc-input" value="100" step="any">
          </div>
        </div>
      </div>
      <div class="pc-result" id="pcChgResult">= 25%<span class="pc-direction up">increase</span></div>
    </div>

    <!-- 4. Tip Calculator -->
    <div class="pc-card">
      <div class="pc-card-title">Tip Calculator</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">Bill</span>
          <div class="pc-input-wrap">
            <span class="pc-input-prefix">$</span>
            <input type="number" id="pcTipBill" class="pc-input has-prefix" value="85" step="any" min="0">
          </div>
          <span class="pc-label">Tip</span>
          <div class="pc-input-wrap" style="max-width:80px;">
            <input type="number" id="pcTipPct" class="pc-input has-suffix" value="18" step="any" min="0">
            <span class="pc-input-suffix">%</span>
          </div>
          <span class="pc-label">Split</span>
          <div class="pc-input-wrap" style="max-width:60px;">
            <input type="number" id="pcTipSplit" class="pc-input" value="2" step="1" min="1">
          </div>
        </div>
      </div>
      <div class="pc-result-multi" id="pcTipResult">
        <div class="pc-result-row"><span class="pc-result-label">Tip</span><span class="pc-result-value" style="color:var(--pc-green);">$15.30</span></div>
        <div class="pc-result-row"><span class="pc-result-label">Total</span><span class="pc-result-value" style="color:var(--pc-green);">$100.30</span></div>
        <div class="pc-result-row"><span class="pc-result-label">Per person</span><span class="pc-result-value" style="color:var(--pc-primary-light);">$50.15</span></div>
      </div>
    </div>

    <!-- 5. Discount Calculator -->
    <div class="pc-card">
      <div class="pc-card-title">Discount Calculator</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">Price</span>
          <div class="pc-input-wrap">
            <span class="pc-input-prefix">$</span>
            <input type="number" id="pcDiscPrice" class="pc-input has-prefix" value="120" step="any" min="0">
          </div>
          <span class="pc-label">Off</span>
          <div class="pc-input-wrap" style="max-width:90px;">
            <input type="number" id="pcDiscPct" class="pc-input has-suffix" value="25" step="any" min="0">
            <span class="pc-input-suffix">%</span>
          </div>
        </div>
      </div>
      <div class="pc-result-multi" id="pcDiscResult">
        <div class="pc-result-row"><span class="pc-result-label">You save</span><span class="pc-result-value" style="color:var(--pc-green);">$30.00</span></div>
        <div class="pc-result-row"><span class="pc-result-label">Final price</span><span class="pc-result-value" style="color:var(--pc-primary-light);">$90.00</span></div>
      </div>
    </div>

    <!-- 6. Markup Calculator -->
    <div class="pc-card">
      <div class="pc-card-title">Markup Calculator</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">Cost</span>
          <div class="pc-input-wrap">
            <span class="pc-input-prefix">$</span>
            <input type="number" id="pcMarkCost" class="pc-input has-prefix" value="50" step="any" min="0">
          </div>
          <span class="pc-label">Markup</span>
          <div class="pc-input-wrap" style="max-width:90px;">
            <input type="number" id="pcMarkPct" class="pc-input has-suffix" value="60" step="any" min="0">
            <span class="pc-input-suffix">%</span>
          </div>
        </div>
      </div>
      <div class="pc-result-multi" id="pcMarkResult">
        <div class="pc-result-row"><span class="pc-result-label">Selling price</span><span class="pc-result-value" style="color:var(--pc-green);">$80.00</span></div>
        <div class="pc-result-row"><span class="pc-result-label">Profit</span><span class="pc-result-value" style="color:var(--pc-primary-light);">$30.00</span></div>
      </div>
    </div>

    <!-- 7. Margin Calculator -->
    <div class="pc-card">
      <div class="pc-card-title">Margin Calculator</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">Revenue</span>
          <div class="pc-input-wrap">
            <span class="pc-input-prefix">$</span>
            <input type="number" id="pcMarginRev" class="pc-input has-prefix" value="100" step="any" min="0">
          </div>
          <span class="pc-label">Cost</span>
          <div class="pc-input-wrap">
            <span class="pc-input-prefix">$</span>
            <input type="number" id="pcMarginCost" class="pc-input has-prefix" value="60" step="any" min="0">
          </div>
        </div>
      </div>
      <div class="pc-result-multi" id="pcMarginResult">
        <div class="pc-result-row"><span class="pc-result-label">Margin</span><span class="pc-result-value" style="color:var(--pc-green);">40.00%</span></div>
        <div class="pc-result-row"><span class="pc-result-label">Profit</span><span class="pc-result-value" style="color:var(--pc-primary-light);">$40.00</span></div>
      </div>
    </div>

    <!-- 8. Tax Calculator -->
    <div class="pc-card">
      <div class="pc-card-title">Tax Calculator</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <span class="pc-label">Amount</span>
          <div class="pc-input-wrap">
            <span class="pc-input-prefix">$</span>
            <input type="number" id="pcTaxAmt" class="pc-input has-prefix" value="75" step="any" min="0">
          </div>
          <span class="pc-label">Tax</span>
          <div class="pc-input-wrap" style="max-width:90px;">
            <input type="number" id="pcTaxRate" class="pc-input has-suffix" value="8.5" step="any" min="0">
            <span class="pc-input-suffix">%</span>
          </div>
        </div>
      </div>
      <div class="pc-result-multi" id="pcTaxResult">
        <div class="pc-result-row"><span class="pc-result-label">Tax amount</span><span class="pc-result-value" style="color:var(--pc-green);">$6.38</span></div>
        <div class="pc-result-row"><span class="pc-result-label">Total</span><span class="pc-result-value" style="color:var(--pc-primary-light);">$81.38</span></div>
      </div>
    </div>

    <!-- 9. Fraction to Percent -->
    <div class="pc-card">
      <div class="pc-card-title">Fraction to Percent</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <div class="pc-input-wrap" style="max-width:100px;">
            <input type="number" id="pcFracNum" class="pc-input" value="3" step="any">
          </div>
          <span class="pc-eq">/</span>
          <div class="pc-input-wrap" style="max-width:100px;">
            <input type="number" id="pcFracDen" class="pc-input" value="8" step="any">
          </div>
        </div>
      </div>
      <div class="pc-result" id="pcFracResult">= 37.5%</div>
    </div>

    <!-- 10. Percent to Fraction -->
    <div class="pc-card">
      <div class="pc-card-title">Percent to Fraction</div>
      <div class="pc-field">
        <div class="pc-input-row">
          <div class="pc-input-wrap">
            <input type="number" id="pcPctToFrac" class="pc-input has-suffix" value="37.5" step="any">
            <span class="pc-input-suffix">%</span>
          </div>
        </div>
      </div>
      <div class="pc-result" id="pcPctFracResult">= 3/8</div>
    </div>

  </div>

  <!-- Cross Links -->
  <div class="pc-cross-links">
    <a href="/tools/compound-interest-calculator/" class="pc-cross-link">Compound Interest Calculator</a>
    <a href="/tools/gpa-calculator/" class="pc-cross-link">GPA Calculator</a>
    <a href="/tools/grade-calculator/" class="pc-cross-link">Grade Calculator</a>
  </div>

  <!-- SEO Content -->
  <div class="pc-content">

<h2>What Is a Percentage</h2>

<p>A percentage is a number expressed as a fraction of 100. The word itself comes from the Latin per centum, meaning "by the hundred." When you see 25%, it means 25 out of every 100, or equivalently 0.25 as a decimal, or 1/4 as a fraction. These three representations are interchangeable, and converting between them is one of the most common tasks in everyday math.</p>

<p>Percentages appear constantly in daily life: sales tax, restaurant tips, exam scores, investment returns, inflation rates, battery charge levels, probability forecasts, nutritional labels. The reason they are so widespread is that they normalize different quantities to a common scale. Comparing 18 out of 24 to 45 out of 60 takes mental effort. Comparing 75% to 75% does not.</p>

<p>This calculator covers ten distinct percentage operations. Rather than forcing you to rearrange formulas yourself, each mode accepts plain inputs and gives you the answer instantly. Every calculation happens in your browser using JavaScript. No data leaves your device.</p>

<h2>Common Percentage Formulas</h2>

<p>Three fundamental formulas cover most percentage problems:</p>

<div class="pc-formula-block">
Result = (Percentage / 100) x Number
</div>

<p>This handles the question "what is X% of Y?" and is the basis of the first calculator card above. If you need to find 15% of 200, you compute (15 / 100) x 200 = 30.</p>

<div class="pc-formula-block">
Percentage = (Part / Whole) x 100
</div>

<p>This answers "X is what percent of Y?" It is the inverse of the first formula. If 30 is the part and 200 is the whole, you get (30 / 200) x 100 = 15%.</p>

<div class="pc-formula-block">
Percentage Change = ((New - Old) / |Old|) x 100
</div>

<p>This measures how much a value has increased or decreased relative to its original size. A move from 80 to 100 is a 25% increase. A move from 100 to 80 is a 20% decrease. Note the asymmetry: the same absolute change (20) produces different percentages depending on the starting value. This is a common source of confusion and exactly why the percentage change calculator shows the direction alongside the number.</p>

<h2>How to Calculate Percentage Change</h2>

<p>Percentage change compares two values and expresses the difference as a proportion of the original. The formula divides the absolute difference by the original value, then multiplies by 100.</p>

<p>Suppose a stock price moved from $40 to $52. The change is $12. Dividing $12 by the original $40 gives 0.3. Multiplied by 100, that is a 30% increase. If the price later drops from $52 back to $40, the change is still $12, but now you divide by $52 (the new "old" value), giving 23.08%. The trip up was 30%, but the trip down was only 23.08%. This asymmetry trips people up regularly, and it is mathematically correct.</p>

<p>Percentage change is used extensively in finance (stock returns, revenue growth), economics (inflation, GDP growth), science (measurement changes), and everyday contexts like comparing prices or grades. The calculator above handles the direction for you, coloring increases green and decreases red so the result is immediately clear.</p>

<h2>Understanding Markup vs Margin</h2>

<p>Markup and margin both describe the relationship between cost and selling price, but they use different denominators. This distinction confuses even experienced businesspeople.</p>

<p>Markup is the percentage added to cost to get the selling price. If an item costs $50 and you apply a 60% markup, the selling price is $50 + ($50 x 0.60) = $80. The profit is $30. Markup is calculated relative to cost.</p>

<p>Margin is the percentage of revenue that is profit. Using the same numbers: revenue is $80, cost is $50, profit is $30. Margin = ($30 / $80) x 100 = 37.5%. Margin is calculated relative to revenue.</p>

<p>The same transaction produces a 60% markup but only a 37.5% margin. Markup is always higher than margin for the same sale because it uses the smaller number (cost) as the denominator. Converting between them requires care:</p>

<div class="pc-formula-block">
Margin = Markup / (1 + Markup)
Markup = Margin / (1 - Margin)
</div>

<p>A 50% markup equals a 33.3% margin. A 100% markup equals a 50% margin. A 50% margin requires a 100% markup. Retailers, wholesalers, and SaaS companies all need to keep these straight when pricing products. Use the markup and margin calculators above to convert between them without memorizing the formulas.</p>

<h2>Tips for Mental Math Percentages</h2>

<p>Calculating percentages in your head is faster than reaching for a calculator in most everyday situations. A few techniques make it simple.</p>

<p>To find 10% of any number, move the decimal point one place left. 10% of 85 is 8.5. 10% of 230 is 23. From there, you can derive other percentages by addition or halving. 5% is half of 10%. 20% is double 10%. 15% is 10% plus 5%. This covers most tipping scenarios.</p>

<p>For 1%, move the decimal two places left. 1% of 850 is 8.5. You can then multiply by whatever factor you need: 3% of 850 is 3 x 8.5 = 25.5.</p>

<p>The commutative property of percentages is useful: X% of Y equals Y% of X. So 8% of 50 is the same as 50% of 8, which is 4. Similarly, 4% of 75 equals 75% of 4, which is 3. Look for the easier direction and compute that one instead.</p>

<p>For discounts, subtract from 100% first. A 30% discount means you pay 70%. To find 70% of $120: 10% is $12, so 70% is $84. Or: 120 x 0.7 = 84. Either way, $84 is the final price. This avoids the extra step of calculating the discount amount and then subtracting.</p>

  </div>

  <!-- FAQ Section -->
  <div class="pc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="pc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I calculate a percentage of a number?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Divide the percentage by 100, then multiply by the number. For example, 15% of 200 is (15 / 100) x 200 = 30. The first calculator card on this page does this automatically as you type. Enter the percentage and the number, and the result appears instantly.</p>
      </div>
    </div>

    <div class="pc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between markup and margin?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Markup is calculated as a percentage of cost, while margin is calculated as a percentage of revenue (selling price). A product that costs $50 and sells for $80 has a 60% markup (profit / cost = 30/50) but only a 37.5% margin (profit / revenue = 30/80). Markup is always a higher number than margin for the same transaction.</p>
      </div>
    </div>

    <div class="pc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why is percentage change different going up vs going down?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Percentage change divides by the starting value, and the starting value is different depending on the direction. Going from 100 to 120 is a 20% increase (20/100). Going from 120 to 100 is only a 16.67% decrease (20/120). The same absolute difference of 20 produces different percentages because the base of the calculation changes.</p>
      </div>
    </div>

    <div class="pc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I convert a fraction to a percentage?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Divide the numerator by the denominator, then multiply by 100. For example, 3/8 = 0.375, and 0.375 x 100 = 37.5%. The fraction-to-percent card on this page handles this conversion automatically. Enter the numerator and denominator and the percentage appears.</p>
      </div>
    </div>

    <div class="pc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I calculate tip on a restaurant bill?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Multiply the bill amount by the tip percentage divided by 100. For an $85 bill with an 18% tip: 85 x 0.18 = $15.30. The total becomes $100.30. If splitting between two people, each pays $50.15. For mental math, find 10% ($8.50), then add about half of that for roughly 15%, or double 10% for 20%.</p>
      </div>
    </div>

    <div class="pc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe when using this calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All calculations run entirely in your web browser using JavaScript. No data is transmitted to any server, no information is stored, and no cookies are set. You can verify this by opening your browser's developer tools and monitoring the Network tab while using any of the ten calculators. Your inputs never leave your device.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="pc-author-box">
    <div class="pc-author-avatar">ML</div>
    <div class="pc-author-info">
      <p class="pc-author-name">Michael Lip</p>
      <p class="pc-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="pc-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Percentage Calculator",
      "description": "Calculate percentages instantly with 10 modes: percentage of a number, percentage change, tip calculator, discount calculator, markup, margin, tax, fraction to percent, and more.",
      "url": "https://theluckystrike.github.io/tools/percentage-calculator/",
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
        {"@type": "ListItem", "position": 3, "name": "Percentage Calculator", "item": "https://theluckystrike.github.io/tools/percentage-calculator/"}
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
          "name": "How do I calculate a percentage of a number?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Divide the percentage by 100, then multiply by the number. For example, 15% of 200 is (15 / 100) x 200 = 30. The first calculator card on this page does this automatically as you type."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between markup and margin?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Markup is calculated as a percentage of cost, while margin is calculated as a percentage of revenue (selling price). A product that costs $50 and sells for $80 has a 60% markup but only a 37.5% margin."
          }
        },
        {
          "@type": "Question",
          "name": "Why is percentage change different going up vs going down?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Percentage change divides by the starting value, and the starting value is different depending on the direction. Going from 100 to 120 is a 20% increase (20/100). Going from 120 to 100 is only a 16.67% decrease (20/120)."
          }
        },
        {
          "@type": "Question",
          "name": "How do I convert a fraction to a percentage?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Divide the numerator by the denominator, then multiply by 100. For example, 3/8 = 0.375, and 0.375 x 100 = 37.5%."
          }
        },
        {
          "@type": "Question",
          "name": "How do I calculate tip on a restaurant bill?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Multiply the bill amount by the tip percentage divided by 100. For an $85 bill with an 18% tip: 85 x 0.18 = $15.30. The total becomes $100.30."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data safe when using this calculator?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All calculations run entirely in your web browser using JavaScript. No data is transmitted to any server, no information is stored, and no cookies are set."
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

  // --- Helpers ---
  function fmt(n, decimals) {
    if (typeof decimals === "undefined") decimals = 2;
    if (isNaN(n) || !isFinite(n)) return "---";
    return Number(n).toLocaleString("en-US", { minimumFractionDigits: decimals, maximumFractionDigits: decimals });
  }

  function fmtMoney(n) {
    if (isNaN(n) || !isFinite(n)) return "$---";
    return "$" + Math.abs(n).toLocaleString("en-US", { minimumFractionDigits: 2, maximumFractionDigits: 2 });
  }

  function gcd(a, b) {
    a = Math.abs(Math.round(a));
    b = Math.abs(Math.round(b));
    if (b === 0) return a;
    return gcd(b, a % b);
  }

  // --- 1. X% of Y ---
  function calcOf() {
    var pct = parseFloat(document.getElementById("pcOfPct").value);
    var num = parseFloat(document.getElementById("pcOfNum").value);
    var el = document.getElementById("pcOfResult");
    if (isNaN(pct) || isNaN(num)) { el.textContent = "= ---"; return; }
    var result = (pct / 100) * num;
    el.textContent = "= " + fmt(result, 4).replace(/\.?0+$/, "");
  }

  // --- 2. X is what % of Y ---
  function calcWhat() {
    var x = parseFloat(document.getElementById("pcWhatX").value);
    var y = parseFloat(document.getElementById("pcWhatY").value);
    var el = document.getElementById("pcWhatResult");
    if (isNaN(x) || isNaN(y) || y === 0) { el.textContent = "= ---"; return; }
    var result = (x / y) * 100;
    el.textContent = "= " + fmt(result, 4).replace(/\.?0+$/, "") + "%";
  }

  // --- 3. Percentage Change ---
  function calcChange() {
    var from = parseFloat(document.getElementById("pcChgFrom").value);
    var to = parseFloat(document.getElementById("pcChgTo").value);
    var el = document.getElementById("pcChgResult");
    if (isNaN(from) || isNaN(to) || from === 0) { el.textContent = "= ---"; el.className = "pc-result"; return; }
    var change = ((to - from) / Math.abs(from)) * 100;
    var direction = change >= 0 ? "increase" : "decrease";
    var dirClass = change >= 0 ? "up" : "down";
    el.innerHTML = "= " + fmt(Math.abs(change), 2) + '%<span class="pc-direction ' + dirClass + '">' + direction + "</span>";
    el.className = change >= 0 ? "pc-result" : "pc-result negative";
  }

  // --- 4. Tip Calculator ---
  function calcTip() {
    var bill = parseFloat(document.getElementById("pcTipBill").value) || 0;
    var pct = parseFloat(document.getElementById("pcTipPct").value) || 0;
    var split = parseInt(document.getElementById("pcTipSplit").value) || 1;
    if (split < 1) split = 1;

    var tip = bill * (pct / 100);
    var total = bill + tip;
    var perPerson = total / split;

    document.getElementById("pcTipResult").innerHTML =
      '<div class="pc-result-row"><span class="pc-result-label">Tip</span><span class="pc-result-value" style="color:var(--pc-green);">' + fmtMoney(tip) + '</span></div>' +
      '<div class="pc-result-row"><span class="pc-result-label">Total</span><span class="pc-result-value" style="color:var(--pc-green);">' + fmtMoney(total) + '</span></div>' +
      '<div class="pc-result-row"><span class="pc-result-label">Per person</span><span class="pc-result-value" style="color:var(--pc-primary-light);">' + fmtMoney(perPerson) + '</span></div>';
  }

  // --- 5. Discount Calculator ---
  function calcDiscount() {
    var price = parseFloat(document.getElementById("pcDiscPrice").value) || 0;
    var pct = parseFloat(document.getElementById("pcDiscPct").value) || 0;

    var savings = price * (pct / 100);
    var finalPrice = price - savings;

    document.getElementById("pcDiscResult").innerHTML =
      '<div class="pc-result-row"><span class="pc-result-label">You save</span><span class="pc-result-value" style="color:var(--pc-green);">' + fmtMoney(savings) + '</span></div>' +
      '<div class="pc-result-row"><span class="pc-result-label">Final price</span><span class="pc-result-value" style="color:var(--pc-primary-light);">' + fmtMoney(finalPrice) + '</span></div>';
  }

  // --- 6. Markup Calculator ---
  function calcMarkup() {
    var cost = parseFloat(document.getElementById("pcMarkCost").value) || 0;
    var pct = parseFloat(document.getElementById("pcMarkPct").value) || 0;

    var profit = cost * (pct / 100);
    var selling = cost + profit;

    document.getElementById("pcMarkResult").innerHTML =
      '<div class="pc-result-row"><span class="pc-result-label">Selling price</span><span class="pc-result-value" style="color:var(--pc-green);">' + fmtMoney(selling) + '</span></div>' +
      '<div class="pc-result-row"><span class="pc-result-label">Profit</span><span class="pc-result-value" style="color:var(--pc-primary-light);">' + fmtMoney(profit) + '</span></div>';
  }

  // --- 7. Margin Calculator ---
  function calcMargin() {
    var rev = parseFloat(document.getElementById("pcMarginRev").value) || 0;
    var cost = parseFloat(document.getElementById("pcMarginCost").value) || 0;

    var profit = rev - cost;
    var margin = rev > 0 ? (profit / rev) * 100 : 0;

    document.getElementById("pcMarginResult").innerHTML =
      '<div class="pc-result-row"><span class="pc-result-label">Margin</span><span class="pc-result-value" style="color:' + (margin >= 0 ? 'var(--pc-green)' : 'var(--pc-red)') + ';">' + fmt(margin) + '%</span></div>' +
      '<div class="pc-result-row"><span class="pc-result-label">Profit</span><span class="pc-result-value" style="color:' + (profit >= 0 ? 'var(--pc-primary-light)' : 'var(--pc-red)') + ';">' + fmtMoney(profit) + '</span></div>';
  }

  // --- 8. Tax Calculator ---
  function calcTax() {
    var amt = parseFloat(document.getElementById("pcTaxAmt").value) || 0;
    var rate = parseFloat(document.getElementById("pcTaxRate").value) || 0;

    var tax = amt * (rate / 100);
    var total = amt + tax;

    document.getElementById("pcTaxResult").innerHTML =
      '<div class="pc-result-row"><span class="pc-result-label">Tax amount</span><span class="pc-result-value" style="color:var(--pc-green);">' + fmtMoney(tax) + '</span></div>' +
      '<div class="pc-result-row"><span class="pc-result-label">Total</span><span class="pc-result-value" style="color:var(--pc-primary-light);">' + fmtMoney(total) + '</span></div>';
  }

  // --- 9. Fraction to Percent ---
  function calcFracToPct() {
    var num = parseFloat(document.getElementById("pcFracNum").value);
    var den = parseFloat(document.getElementById("pcFracDen").value);
    var el = document.getElementById("pcFracResult");
    if (isNaN(num) || isNaN(den) || den === 0) { el.textContent = "= ---"; return; }
    var result = (num / den) * 100;
    el.textContent = "= " + fmt(result, 4).replace(/\.?0+$/, "") + "%";
  }

  // --- 10. Percent to Fraction ---
  function calcPctToFrac() {
    var pct = parseFloat(document.getElementById("pcPctToFrac").value);
    var el = document.getElementById("pcPctFracResult");
    if (isNaN(pct)) { el.textContent = "= ---"; return; }

    // Convert percentage to fraction and simplify
    // Handle decimals by scaling
    var numerator = pct;
    var denominator = 100;

    // Scale to remove decimal places
    var decStr = String(pct);
    var decIndex = decStr.indexOf(".");
    if (decIndex !== -1) {
      var decPlaces = decStr.length - decIndex - 1;
      var scale = Math.pow(10, decPlaces);
      numerator = Math.round(pct * scale);
      denominator = 100 * scale;
    }

    var g = gcd(Math.abs(numerator), Math.abs(denominator));
    if (g > 0) {
      numerator = numerator / g;
      denominator = denominator / g;
    }

    if (denominator === 1) {
      el.textContent = "= " + numerator;
    } else {
      el.textContent = "= " + numerator + "/" + denominator;
    }
  }

  // --- Wire up all inputs ---
  var bindings = [
    { ids: ["pcOfPct", "pcOfNum"], fn: calcOf },
    { ids: ["pcWhatX", "pcWhatY"], fn: calcWhat },
    { ids: ["pcChgFrom", "pcChgTo"], fn: calcChange },
    { ids: ["pcTipBill", "pcTipPct", "pcTipSplit"], fn: calcTip },
    { ids: ["pcDiscPrice", "pcDiscPct"], fn: calcDiscount },
    { ids: ["pcMarkCost", "pcMarkPct"], fn: calcMarkup },
    { ids: ["pcMarginRev", "pcMarginCost"], fn: calcMargin },
    { ids: ["pcTaxAmt", "pcTaxRate"], fn: calcTax },
    { ids: ["pcFracNum", "pcFracDen"], fn: calcFracToPct },
    { ids: ["pcPctToFrac"], fn: calcPctToFrac }
  ];

  bindings.forEach(function(b) {
    b.ids.forEach(function(id) {
      var el = document.getElementById(id);
      if (el) {
        el.addEventListener("input", b.fn);
        el.addEventListener("change", b.fn);
      }
    });
  });

  // --- Initial calculations ---
  calcOf();
  calcWhat();
  calcChange();
  calcTip();
  calcDiscount();
  calcMarkup();
  calcMargin();
  calcTax();
  calcFracToPct();
  calcPctToFrac();

})();
</script>
