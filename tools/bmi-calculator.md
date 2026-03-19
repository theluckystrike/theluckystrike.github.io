---
layout: page
title: "Free BMI Calculator — Body Mass Index with Health Ranges | Zovo"
description: "Calculate your Body Mass Index instantly with metric or imperial units. See your BMI category, healthy weight range, visual gauge, and BMI chart. Free online BMI calculator."
permalink: /tools/bmi-calculator/
keywords: "bmi calculator, body mass index, bmi chart, healthy weight, bmi checker, weight calculator, bmi formula"
date: 2026-03-19
categories: [tools]
tags: [bmi, calculator, health, weight, body-mass-index, fitness]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --bmi-primary: #6C5CE7;
    --bmi-primary-dark: #5A4BD1;
    --bmi-primary-light: #A29BFE;
    --bmi-bg: #0a0a0f;
    --bmi-surface: #12121a;
    --bmi-surface-alt: #181824;
    --bmi-border: #1e1e2e;
    --bmi-text: #e0e0e0;
    --bmi-text-muted: #8888aa;
    --bmi-green: #00ff88;
    --bmi-green-dark: #00cc6a;
    --bmi-red: #ff4466;
    --bmi-orange: #ffaa33;
    --bmi-blue: #33aaff;
    --bmi-radius: 12px;
    --bmi-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .bmi-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--bmi-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .bmi-wrapper * {
    box-sizing: border-box;
  }

  .bmi-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .bmi-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--bmi-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .bmi-hero h1 span {
    color: var(--bmi-primary);
  }

  .bmi-intro {
    font-size: 1.05rem;
    color: var(--bmi-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .bmi-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--bmi-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--bmi-border);
    border-radius: 20px;
  }

  /* Card */
  .bmi-card {
    background: var(--bmi-surface);
    border: 1px solid var(--bmi-border);
    border-radius: var(--bmi-radius);
    padding: 24px;
    box-shadow: var(--bmi-shadow);
    margin-bottom: 20px;
  }

  .bmi-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--bmi-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .bmi-card-title svg {
    width: 16px;
    height: 16px;
    opacity: 0.6;
  }

  /* Layout */
  .bmi-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-bottom: 24px;
  }

  /* Unit Toggle */
  .bmi-unit-toggle {
    display: flex;
    background: var(--bmi-surface-alt);
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 20px;
    border: 1px solid var(--bmi-border);
  }

  .bmi-unit-btn {
    flex: 1;
    padding: 10px 16px;
    border: none;
    background: transparent;
    color: var(--bmi-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
  }

  .bmi-unit-btn.active {
    background: var(--bmi-primary);
    color: #fff;
  }

  .bmi-unit-btn:hover:not(.active) {
    color: var(--bmi-text);
    background: rgba(108, 92, 231, 0.1);
  }

  /* Form */
  .bmi-field {
    margin-bottom: 16px;
  }

  .bmi-label {
    display: block;
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--bmi-text-muted);
    margin-bottom: 6px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .bmi-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--bmi-surface-alt);
    border: 1px solid var(--bmi-border);
    border-radius: 8px;
    color: var(--bmi-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 1rem;
    transition: border-color 0.2s;
  }

  .bmi-input:focus {
    outline: none;
    border-color: var(--bmi-primary);
  }

  .bmi-select {
    width: 100%;
    padding: 10px 14px;
    background: var(--bmi-surface-alt);
    border: 1px solid var(--bmi-border);
    border-radius: 8px;
    color: var(--bmi-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    cursor: pointer;
    appearance: none;
    -webkit-appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' fill='%238888aa' viewBox='0 0 16 16'%3E%3Cpath d='M8 11L3 6h10l-5 5z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
  }

  .bmi-select:focus {
    outline: none;
    border-color: var(--bmi-primary);
  }

  .bmi-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .bmi-height-imperial {
    display: none;
  }

  .bmi-height-metric {
    display: block;
  }

  /* Results */
  .bmi-result-big {
    text-align: center;
    padding: 24px 0 8px;
  }

  .bmi-result-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 4rem;
    font-weight: 700;
    color: var(--bmi-green);
    line-height: 1;
    margin-bottom: 8px;
  }

  .bmi-result-category {
    font-size: 1.1rem;
    font-weight: 600;
    padding: 6px 16px;
    border-radius: 20px;
    display: inline-block;
    margin-bottom: 16px;
  }

  .bmi-cat-underweight { background: rgba(51, 170, 255, 0.15); color: var(--bmi-blue); }
  .bmi-cat-normal { background: rgba(0, 255, 136, 0.15); color: var(--bmi-green); }
  .bmi-cat-overweight { background: rgba(255, 170, 51, 0.15); color: var(--bmi-orange); }
  .bmi-cat-obese { background: rgba(255, 68, 102, 0.15); color: var(--bmi-red); }

  .bmi-healthy-range {
    font-size: 0.9rem;
    color: var(--bmi-text-muted);
    margin-top: 8px;
  }

  .bmi-healthy-range span {
    color: var(--bmi-green);
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
  }

  /* Gauge */
  .bmi-gauge-wrap {
    padding: 20px 0 12px;
  }

  .bmi-gauge-bar {
    position: relative;
    height: 24px;
    border-radius: 12px;
    overflow: visible;
    display: flex;
    margin-bottom: 8px;
  }

  .bmi-gauge-zone {
    height: 100%;
    position: relative;
  }

  .bmi-gauge-zone:first-child {
    border-radius: 12px 0 0 12px;
  }

  .bmi-gauge-zone:last-child {
    border-radius: 0 12px 12px 0;
  }

  .bmi-gauge-zone-under { background: var(--bmi-blue); width: 18.5%; opacity: 0.5; }
  .bmi-gauge-zone-normal { background: var(--bmi-green); width: 24.9%; opacity: 0.5; }
  .bmi-gauge-zone-over { background: var(--bmi-orange); width: 19.1%; opacity: 0.5; }
  .bmi-gauge-zone-obese { background: var(--bmi-red); width: 37.5%; opacity: 0.5; }

  .bmi-gauge-marker {
    position: absolute;
    top: -6px;
    width: 4px;
    height: 36px;
    background: #fff;
    border-radius: 2px;
    transform: translateX(-50%);
    transition: left 0.4s ease;
    box-shadow: 0 0 8px rgba(255,255,255,0.4);
    z-index: 2;
  }

  .bmi-gauge-labels {
    display: flex;
    justify-content: space-between;
    font-size: 0.7rem;
    color: var(--bmi-text-muted);
    padding: 0 2px;
  }

  .bmi-gauge-labels span {
    text-align: center;
  }

  /* Info Grid */
  .bmi-info-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    margin-top: 16px;
  }

  .bmi-info-item {
    background: var(--bmi-surface-alt);
    border-radius: 8px;
    padding: 10px 14px;
  }

  .bmi-info-label {
    font-size: 0.7rem;
    color: var(--bmi-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .bmi-info-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--bmi-text);
    margin-top: 2px;
  }

  /* BMI Table */
  .bmi-table-wrap {
    overflow-x: auto;
    margin-bottom: 24px;
  }

  .bmi-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.85rem;
  }

  .bmi-table th {
    background: var(--bmi-surface-alt);
    color: var(--bmi-text-muted);
    font-weight: 600;
    text-transform: uppercase;
    font-size: 0.7rem;
    letter-spacing: 0.05em;
    padding: 10px 14px;
    text-align: left;
    border-bottom: 1px solid var(--bmi-border);
  }

  .bmi-table td {
    padding: 10px 14px;
    border-bottom: 1px solid var(--bmi-border);
    color: var(--bmi-text);
  }

  .bmi-table tr:last-child td {
    border-bottom: none;
  }

  .bmi-table .bmi-dot {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    margin-right: 8px;
    vertical-align: middle;
  }

  /* Content */
  .bmi-content {
    background: var(--bmi-surface);
    border: 1px solid var(--bmi-border);
    border-radius: var(--bmi-radius);
    padding: 32px;
    margin-bottom: 24px;
  }

  .bmi-content h2 {
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--bmi-text);
    margin: 32px 0 12px;
    line-height: 1.3;
  }

  .bmi-content h2:first-child {
    margin-top: 0;
  }

  .bmi-content p {
    color: var(--bmi-text-muted);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .bmi-formula-block {
    background: var(--bmi-surface-alt);
    border: 1px solid var(--bmi-border);
    border-left: 3px solid var(--bmi-primary);
    border-radius: 6px;
    padding: 14px 18px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--bmi-green);
    margin: 16px 0;
    overflow-x: auto;
    white-space: pre-line;
  }

  /* FAQ */
  .bmi-faq {
    background: var(--bmi-surface);
    border: 1px solid var(--bmi-border);
    border-radius: var(--bmi-radius);
    padding: 32px;
    margin-bottom: 24px;
  }

  .bmi-faq h2 {
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--bmi-text);
    margin: 0 0 20px;
  }

  .bmi-faq-item {
    border-bottom: 1px solid var(--bmi-border);
    padding: 16px 0;
  }

  .bmi-faq-item:last-child {
    border-bottom: none;
    padding-bottom: 0;
  }

  .bmi-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--bmi-text);
    margin: 0 0 8px;
  }

  .bmi-faq-item p {
    font-size: 0.9rem;
    color: var(--bmi-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Cross Links */
  .bmi-cross-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 24px;
  }

  .bmi-cross-link {
    background: var(--bmi-surface);
    border: 1px solid var(--bmi-border);
    border-radius: 8px;
    padding: 10px 18px;
    color: var(--bmi-primary-light);
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    transition: all 0.2s;
  }

  .bmi-cross-link:hover {
    border-color: var(--bmi-primary);
    background: rgba(108, 92, 231, 0.08);
    color: var(--bmi-primary-light);
  }

  /* Author Box */
  .bmi-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    background: var(--bmi-surface);
    border: 1px solid var(--bmi-border);
    border-radius: var(--bmi-radius);
    padding: 20px 24px;
    margin-bottom: 24px;
  }

  .bmi-author-avatar {
    width: 48px;
    height: 48px;
    background: var(--bmi-primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1rem;
    color: #fff;
    flex-shrink: 0;
  }

  .bmi-author-info {
    flex: 1;
  }

  .bmi-author-name {
    font-weight: 600;
    font-size: 0.95rem;
    color: var(--bmi-text);
    margin: 0 0 4px;
  }

  .bmi-author-bio {
    font-size: 0.8rem;
    color: var(--bmi-text-muted);
    margin: 0;
    line-height: 1.5;
  }

  /* Footer */
  .bmi-footer {
    text-align: center;
    padding: 20px 0 40px;
    font-size: 0.8rem;
    color: var(--bmi-text-muted);
  }

  .bmi-footer a {
    color: var(--bmi-primary-light);
    text-decoration: none;
  }

  .bmi-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .bmi-hero h1 {
      font-size: 1.6rem;
    }

    .bmi-layout {
      grid-template-columns: 1fr;
    }

    .bmi-row {
      grid-template-columns: 1fr 1fr;
    }

    .bmi-info-grid {
      grid-template-columns: 1fr 1fr;
    }

    .bmi-result-number {
      font-size: 3rem;
    }
  }

  @media (max-width: 480px) {
    .bmi-info-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="bmi-wrapper">

  <div class="bmi-hero">
    <h1><span>BMI</span> Calculator</h1>
    <p class="bmi-intro">Enter your weight and height to calculate your Body Mass Index. Switch between metric and imperial units, see where you fall on the BMI scale, and find the healthy weight range for your height.</p>
    <span class="bmi-updated">Updated March 2026</span>
  </div>

  <div class="bmi-layout">

    <!-- Input Panel -->
    <div class="bmi-card">
      <div class="bmi-card-title">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2a5 5 0 1 0 0 10 5 5 0 0 0 0-10zM2 21a10 10 0 0 1 20 0"/></svg>
        Your Measurements
      </div>

      <!-- Unit Toggle -->
      <div class="bmi-unit-toggle">
        <button type="button" class="bmi-unit-btn active" id="bmiMetricBtn" onclick="bmiSetUnit('metric')">Metric (kg / cm)</button>
        <button type="button" class="bmi-unit-btn" id="bmiImperialBtn" onclick="bmiSetUnit('imperial')">Imperial (lbs / ft+in)</button>
      </div>

      <!-- Weight -->
      <div class="bmi-field">
        <label class="bmi-label" id="bmiWeightLabel" for="bmiWeight">Weight (kg)</label>
        <input type="number" class="bmi-input" id="bmiWeight" value="70" min="1" max="500" step="0.1">
      </div>

      <!-- Height Metric -->
      <div class="bmi-field bmi-height-metric" id="bmiHeightMetricWrap">
        <label class="bmi-label" for="bmiHeightCm">Height (cm)</label>
        <input type="number" class="bmi-input" id="bmiHeightCm" value="175" min="50" max="300" step="0.1">
      </div>

      <!-- Height Imperial -->
      <div class="bmi-field bmi-height-imperial" id="bmiHeightImperialWrap">
        <label class="bmi-label">Height</label>
        <div class="bmi-row">
          <div>
            <input type="number" class="bmi-input" id="bmiHeightFt" value="5" min="1" max="8" step="1" placeholder="ft">
            <span style="font-size:0.75rem;color:var(--bmi-text-muted);margin-top:2px;display:block;">feet</span>
          </div>
          <div>
            <input type="number" class="bmi-input" id="bmiHeightIn" value="9" min="0" max="11" step="1" placeholder="in">
            <span style="font-size:0.75rem;color:var(--bmi-text-muted);margin-top:2px;display:block;">inches</span>
          </div>
        </div>
      </div>

      <!-- Age & Gender -->
      <div class="bmi-row">
        <div class="bmi-field">
          <label class="bmi-label" for="bmiAge">Age</label>
          <input type="number" class="bmi-input" id="bmiAge" value="30" min="2" max="120" step="1">
        </div>
        <div class="bmi-field">
          <label class="bmi-label" for="bmiGender">Gender</label>
          <select class="bmi-select" id="bmiGender">
            <option value="male">Male</option>
            <option value="female">Female</option>
            <option value="other">Other</option>
          </select>
        </div>
      </div>
    </div>

    <!-- Results Panel -->
    <div class="bmi-card">
      <div class="bmi-card-title">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>
        Your Results
      </div>

      <div class="bmi-result-big">
        <div class="bmi-result-number" id="bmiResultNum">22.9</div>
        <div class="bmi-result-category bmi-cat-normal" id="bmiResultCat">Normal weight</div>
      </div>

      <!-- Gauge -->
      <div class="bmi-gauge-wrap">
        <div class="bmi-gauge-bar" id="bmiGauge">
          <div class="bmi-gauge-zone bmi-gauge-zone-under"></div>
          <div class="bmi-gauge-zone bmi-gauge-zone-normal"></div>
          <div class="bmi-gauge-zone bmi-gauge-zone-over"></div>
          <div class="bmi-gauge-zone bmi-gauge-zone-obese"></div>
          <div class="bmi-gauge-marker" id="bmiGaugeMarker" style="left:30%;"></div>
        </div>
        <div class="bmi-gauge-labels">
          <span>Underweight<br>&lt;18.5</span>
          <span>Normal<br>18.5-24.9</span>
          <span>Overweight<br>25-29.9</span>
          <span>Obese<br>30+</span>
        </div>
      </div>

      <div class="bmi-healthy-range" id="bmiHealthyRange">
        Healthy weight for your height: <span id="bmiHealthyMin">56.7</span> - <span id="bmiHealthyMax">76.2</span> <span id="bmiHealthyUnit">kg</span>
      </div>

      <div class="bmi-info-grid">
        <div class="bmi-info-item">
          <div class="bmi-info-label">BMI Prime</div>
          <div class="bmi-info-value" id="bmiPrime">0.92</div>
        </div>
        <div class="bmi-info-item">
          <div class="bmi-info-label">Ponderal Index</div>
          <div class="bmi-info-value" id="bmiPonderal">12.7</div>
        </div>
        <div class="bmi-info-item">
          <div class="bmi-info-label">Weight to Lose/Gain</div>
          <div class="bmi-info-value" id="bmiWeightDiff">--</div>
        </div>
        <div class="bmi-info-item">
          <div class="bmi-info-label">Age Context</div>
          <div class="bmi-info-value" id="bmiAgeContext">Adult</div>
        </div>
      </div>
    </div>

  </div>

  <!-- BMI Chart Table -->
  <div class="bmi-card">
    <div class="bmi-card-title">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 3v18"/></svg>
      BMI Reference Chart
    </div>
    <div class="bmi-table-wrap">
      <table class="bmi-table">
        <thead>
          <tr>
            <th>Category</th>
            <th>BMI Range</th>
            <th>Risk Level</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-blue);"></span>Severe Thinness</td>
            <td>&lt; 16.0</td>
            <td>High</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-blue);opacity:0.7;"></span>Moderate Thinness</td>
            <td>16.0 - 16.9</td>
            <td>Moderate</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-blue);opacity:0.5;"></span>Mild Thinness</td>
            <td>17.0 - 18.4</td>
            <td>Low</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-green);"></span>Normal</td>
            <td>18.5 - 24.9</td>
            <td>Low</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-orange);"></span>Overweight</td>
            <td>25.0 - 29.9</td>
            <td>Moderate</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-red);opacity:0.6;"></span>Obese Class I</td>
            <td>30.0 - 34.9</td>
            <td>High</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-red);opacity:0.8;"></span>Obese Class II</td>
            <td>35.0 - 39.9</td>
            <td>Very High</td>
          </tr>
          <tr>
            <td><span class="bmi-dot" style="background:var(--bmi-red);"></span>Obese Class III</td>
            <td>&ge; 40.0</td>
            <td>Extremely High</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Cross Links -->
  <div class="bmi-cross-links">
    <a href="/tools/percentage-calculator/" class="bmi-cross-link">Percentage Calculator</a>
    <a href="/tools/unit-converter/" class="bmi-cross-link">Unit Converter</a>
    <a href="/tools/age-calculator/" class="bmi-cross-link">Age Calculator</a>
  </div>

  <!-- SEO Content -->
  <div class="bmi-content">

<h2>What Is BMI</h2>

<p>Body Mass Index is a numerical value derived from a person's weight and height. Adolphe Quetelet, a Belgian mathematician, developed it in the 1830s as a way to quantify human body size for population-level studies. The measure was never designed as a diagnostic tool for individual health, but it became widely adopted because it requires only two inputs that are easy to collect: weight and height.</p>

<p>BMI provides a rough estimate of body fat for most people. A higher BMI generally correlates with higher body fat percentage, though the relationship is not perfect. Two people with the same BMI can have very different body compositions depending on their muscle mass, bone density, and fat distribution. A 190 cm athlete weighing 100 kg and a sedentary person of the same dimensions will both register a BMI of 27.7, despite having fundamentally different health profiles.</p>

<p>Despite its limitations, BMI remains the most commonly used screening tool in clinical settings, public health research, and insurance underwriting. It works well as a starting point for conversations about weight and health, provided it is combined with other measurements and clinical judgment.</p>

<h2>How BMI Is Calculated</h2>

<p>The BMI formula divides weight in kilograms by the square of height in meters:</p>

<div class="bmi-formula-block">BMI = weight (kg) / height (m)^2</div>

<p>For someone who weighs 70 kg and stands 1.75 m tall, the calculation is 70 / (1.75 x 1.75) = 70 / 3.0625 = 22.86. This result places them in the normal weight category.</p>

<p>When using imperial units (pounds and inches), the formula includes a conversion factor:</p>

<div class="bmi-formula-block">BMI = (weight in lbs x 703) / (height in inches)^2</div>

<p>A person weighing 154 lbs at 69 inches tall: (154 x 703) / (69 x 69) = 108,262 / 4,761 = 22.74. Both formulas produce the same result because they are algebraically equivalent after unit conversion.</p>

<p>The calculator above handles the conversion automatically. Enter your values in whichever unit system you prefer, and the BMI will appear in real time. The BMI Prime value shown in the results panel is your BMI divided by 25 (the upper bound of normal). A BMI Prime below 1.0 means you are within the normal range.</p>

<h2>BMI Categories Explained</h2>

<p>The World Health Organization defines four primary BMI categories for adults aged 20 and older. Underweight is a BMI below 18.5. Normal weight spans 18.5 to 24.9. Overweight covers 25.0 to 29.9. Obese is any BMI at or above 30.0, which further subdivides into Class I (30.0-34.9), Class II (35.0-39.9), and Class III (40.0 and above).</p>

<p>These thresholds are based on statistical associations between BMI and health outcomes across large populations. The risk of type 2 diabetes, cardiovascular disease, and certain cancers tends to increase as BMI rises above 25. Below 18.5, risks associated with nutrient deficiency, immune suppression, and bone loss increase. The "normal" range of 18.5 to 24.9 is the zone where population-level health risks are statistically lowest.</p>

<p>For children and adolescents under 20, BMI is interpreted differently. Pediatric BMI uses percentile charts that account for age and sex because body fat changes naturally as young people grow. A child at the 85th percentile for their age and sex is considered overweight; at the 95th percentile, obese. This calculator notes when the entered age is below 20 and reminds users that pediatric interpretation requires percentile-based charts rather than the fixed adult cutoffs.</p>

<h2>Limitations of BMI</h2>

<p>BMI does not distinguish between fat mass and lean mass. A muscular person can register as overweight or obese despite having low body fat. This is common among athletes, weightlifters, and people who do manual labor. Conversely, someone with a normal BMI may carry excess visceral fat around their organs, a pattern sometimes called "normal weight obesity" or "skinny fat." Waist circumference, waist-to-hip ratio, and body fat percentage tests (DEXA scans, bioelectrical impedance) provide more granular information about body composition.</p>

<p>Age affects the relationship between BMI and body fat. Older adults tend to have more body fat and less muscle than younger adults at the same BMI. Sex matters too: women generally carry more body fat than men at any given BMI. Ethnicity introduces further variation. Research shows that some Asian populations develop health risks at lower BMI values than European populations, which has led some countries to adopt lower cutoff points.</p>

<p>BMI also ignores fat distribution. Abdominal fat (visceral fat) is more metabolically active and more strongly associated with disease risk than subcutaneous fat stored in the hips and thighs. Two people with identical BMI values but different fat distribution patterns face different health risks. This is why many clinicians measure waist circumference alongside BMI and consider them together when assessing risk.</p>

<p>None of these limitations make BMI useless. They make it incomplete. BMI is best understood as one data point among several, not as a standalone verdict on health.</p>

  </div>

  <!-- FAQ Section -->
  <div class="bmi-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="bmi-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is a healthy BMI range?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The World Health Organization defines a healthy BMI as 18.5 to 24.9 for adults aged 20 and older. Within this range, population-level risks for type 2 diabetes, heart disease, and other conditions are statistically lowest. Individual health depends on many factors beyond BMI, including body composition, fitness level, and family history.</p>
      </div>
    </div>

    <div class="bmi-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is BMI for muscular people?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">BMI tends to overestimate body fat in people with high muscle mass. A muscular person may register as overweight or obese by BMI standards while actually having a low body fat percentage. Athletes, bodybuilders, and manual laborers often fall into this category. For these individuals, body fat percentage measurements or waist circumference provide more meaningful assessments.</p>
      </div>
    </div>

    <div class="bmi-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does BMI differ for men and women?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The BMI formula and category cutoffs are the same for both sexes. However, women typically carry a higher percentage of body fat than men at the same BMI. A man and a woman with a BMI of 24 may have different body fat percentages. Some researchers have proposed sex-specific cutoffs, but the WHO categories remain universal for now.</p>
      </div>
    </div>

    <div class="bmi-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use BMI for children?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">BMI for children and teens (ages 2 to 19) is calculated the same way but interpreted using age-and-sex-specific percentile charts from the CDC. A BMI at the 85th percentile is considered overweight; the 95th percentile is considered obese. Fixed adult cutoffs do not apply to growing children because their body composition changes with age.</p>
      </div>
    </div>

    <div class="bmi-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data stored when I use this calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All calculations run entirely in your browser using JavaScript. Your weight, height, age, and gender inputs are never sent to any server. No cookies are set, no data is stored, and no analytics track your inputs. You can verify this by inspecting the Network tab in your browser's developer tools while using the calculator.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="bmi-author-box">
    <div class="bmi-author-avatar">ML</div>
    <div class="bmi-author-info">
      <p class="bmi-author-name">Michael Lip</p>
      <p class="bmi-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="bmi-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "BMI Calculator",
      "description": "Calculate your Body Mass Index instantly with metric or imperial units. See your BMI category, healthy weight range, visual gauge, and BMI chart.",
      "url": "https://theluckystrike.github.io/tools/bmi-calculator/",
      "applicationCategory": "HealthApplication",
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
        {"@type": "ListItem", "position": 3, "name": "BMI Calculator", "item": "https://theluckystrike.github.io/tools/bmi-calculator/"}
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
          "name": "What is a healthy BMI range?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The World Health Organization defines a healthy BMI as 18.5 to 24.9 for adults aged 20 and older. Within this range, population-level risks for type 2 diabetes, heart disease, and other conditions are statistically lowest."
          }
        },
        {
          "@type": "Question",
          "name": "How accurate is BMI for muscular people?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "BMI tends to overestimate body fat in people with high muscle mass. A muscular person may register as overweight or obese by BMI standards while actually having a low body fat percentage. Body fat percentage measurements or waist circumference provide more meaningful assessments for these individuals."
          }
        },
        {
          "@type": "Question",
          "name": "Does BMI differ for men and women?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The BMI formula and category cutoffs are the same for both sexes. However, women typically carry a higher percentage of body fat than men at the same BMI."
          }
        },
        {
          "@type": "Question",
          "name": "Can I use BMI for children?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "BMI for children and teens (ages 2 to 19) is calculated the same way but interpreted using age-and-sex-specific percentile charts. A BMI at the 85th percentile is considered overweight; the 95th percentile is considered obese."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data stored when I use this calculator?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All calculations run entirely in your browser using JavaScript. Your weight, height, age, and gender inputs are never sent to any server. No cookies are set and no data is stored."
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

  var unit = "metric"; // "metric" or "imperial"

  var elWeight = document.getElementById("bmiWeight");
  var elWeightLabel = document.getElementById("bmiWeightLabel");
  var elHeightCm = document.getElementById("bmiHeightCm");
  var elHeightFt = document.getElementById("bmiHeightFt");
  var elHeightIn = document.getElementById("bmiHeightIn");
  var elAge = document.getElementById("bmiAge");
  var elGender = document.getElementById("bmiGender");
  var elMetricWrap = document.getElementById("bmiHeightMetricWrap");
  var elImperialWrap = document.getElementById("bmiHeightImperialWrap");
  var elResultNum = document.getElementById("bmiResultNum");
  var elResultCat = document.getElementById("bmiResultCat");
  var elGaugeMarker = document.getElementById("bmiGaugeMarker");
  var elHealthyMin = document.getElementById("bmiHealthyMin");
  var elHealthyMax = document.getElementById("bmiHealthyMax");
  var elHealthyUnit = document.getElementById("bmiHealthyUnit");
  var elPrime = document.getElementById("bmiPrime");
  var elPonderal = document.getElementById("bmiPonderal");
  var elWeightDiff = document.getElementById("bmiWeightDiff");
  var elAgeContext = document.getElementById("bmiAgeContext");

  var debounceTimer = null;

  // --- Set Unit ---
  window.bmiSetUnit = function(u) {
    unit = u;
    var metricBtn = document.getElementById("bmiMetricBtn");
    var imperialBtn = document.getElementById("bmiImperialBtn");

    if (u === "metric") {
      metricBtn.classList.add("active");
      imperialBtn.classList.remove("active");
      elMetricWrap.style.display = "block";
      elImperialWrap.style.display = "none";
      elWeightLabel.textContent = "Weight (kg)";

      // Convert current imperial values to metric
      var lbs = parseFloat(elWeight.value) || 0;
      var ft = parseInt(elHeightFt.value) || 0;
      var inches = parseInt(elHeightIn.value) || 0;
      if (lbs > 0 && lbs < 100) {
        // Already metric-ish, don't convert
      } else if (lbs > 100) {
        elWeight.value = (lbs / 2.20462).toFixed(1);
      }
      var totalIn = ft * 12 + inches;
      if (totalIn > 0) {
        elHeightCm.value = (totalIn * 2.54).toFixed(1);
      }
    } else {
      imperialBtn.classList.add("active");
      metricBtn.classList.remove("active");
      elMetricWrap.style.display = "none";
      elImperialWrap.style.display = "block";
      elWeightLabel.textContent = "Weight (lbs)";

      // Convert current metric values to imperial
      var kg = parseFloat(elWeight.value) || 0;
      if (kg > 0 && kg < 200) {
        elWeight.value = (kg * 2.20462).toFixed(1);
      }
      var cm = parseFloat(elHeightCm.value) || 0;
      if (cm > 0) {
        var totalInches = cm / 2.54;
        elHeightFt.value = Math.floor(totalInches / 12);
        elHeightIn.value = Math.round(totalInches % 12);
      }
    }
    calculate();
  };

  // --- Get weight in kg ---
  function getWeightKg() {
    var w = parseFloat(elWeight.value) || 0;
    if (unit === "imperial") {
      return w / 2.20462;
    }
    return w;
  }

  // --- Get height in meters ---
  function getHeightM() {
    if (unit === "metric") {
      var cm = parseFloat(elHeightCm.value) || 0;
      return cm / 100;
    } else {
      var ft = parseInt(elHeightFt.value) || 0;
      var inches = parseInt(elHeightIn.value) || 0;
      var totalInches = ft * 12 + inches;
      return totalInches * 0.0254;
    }
  }

  // --- Calculate BMI ---
  function calculate() {
    var weightKg = getWeightKg();
    var heightM = getHeightM();
    var age = parseInt(elAge.value) || 30;

    if (weightKg <= 0 || heightM <= 0) {
      elResultNum.textContent = "--";
      elResultCat.textContent = "Enter values";
      elResultCat.className = "bmi-result-category";
      return;
    }

    var bmi = weightKg / (heightM * heightM);
    elResultNum.textContent = bmi.toFixed(1);

    // Category
    var catText, catClass;
    if (bmi < 18.5) {
      catText = "Underweight";
      catClass = "bmi-cat-underweight";
    } else if (bmi < 25) {
      catText = "Normal weight";
      catClass = "bmi-cat-normal";
    } else if (bmi < 30) {
      catText = "Overweight";
      catClass = "bmi-cat-overweight";
    } else {
      catText = "Obese";
      catClass = "bmi-cat-obese";
    }
    elResultCat.textContent = catText;
    elResultCat.className = "bmi-result-category " + catClass;

    // Gauge marker position
    // Map BMI 10-50 to 0-100%
    var pct = ((bmi - 10) / 40) * 100;
    pct = Math.max(0, Math.min(100, pct));
    elGaugeMarker.style.left = pct + "%";

    // Healthy weight range
    var minW = 18.5 * heightM * heightM;
    var maxW = 24.9 * heightM * heightM;
    if (unit === "imperial") {
      elHealthyMin.textContent = (minW * 2.20462).toFixed(1);
      elHealthyMax.textContent = (maxW * 2.20462).toFixed(1);
      elHealthyUnit.textContent = "lbs";
    } else {
      elHealthyMin.textContent = minW.toFixed(1);
      elHealthyMax.textContent = maxW.toFixed(1);
      elHealthyUnit.textContent = "kg";
    }

    // BMI Prime
    var prime = bmi / 25;
    elPrime.textContent = prime.toFixed(2);

    // Ponderal Index
    var pi = weightKg / (heightM * heightM * heightM);
    elPonderal.textContent = pi.toFixed(1);

    // Weight to lose/gain
    if (bmi >= 18.5 && bmi <= 24.9) {
      elWeightDiff.textContent = "In range";
      elWeightDiff.style.color = "var(--bmi-green)";
    } else if (bmi < 18.5) {
      var toGain = minW - weightKg;
      if (unit === "imperial") toGain = toGain * 2.20462;
      var unitLabel = unit === "imperial" ? "lbs" : "kg";
      elWeightDiff.textContent = "+" + toGain.toFixed(1) + " " + unitLabel;
      elWeightDiff.style.color = "var(--bmi-blue)";
    } else {
      var toLose = weightKg - maxW;
      if (unit === "imperial") toLose = toLose * 2.20462;
      var unitLabel2 = unit === "imperial" ? "lbs" : "kg";
      elWeightDiff.textContent = "-" + toLose.toFixed(1) + " " + unitLabel2;
      elWeightDiff.style.color = "var(--bmi-orange)";
    }

    // Age context
    if (age < 2) {
      elAgeContext.textContent = "Too young for BMI";
    } else if (age < 20) {
      elAgeContext.textContent = "Use pediatric percentile charts";
      elAgeContext.style.color = "var(--bmi-orange)";
    } else if (age < 65) {
      elAgeContext.textContent = "Adult (standard ranges)";
      elAgeContext.style.color = "var(--bmi-text)";
    } else {
      elAgeContext.textContent = "Senior (slightly higher BMI may be normal)";
      elAgeContext.style.color = "var(--bmi-text-muted)";
    }
  }

  // --- Wire inputs ---
  var allInputs = [elWeight, elHeightCm, elHeightFt, elHeightIn, elAge, elGender];
  for (var i = 0; i < allInputs.length; i++) {
    allInputs[i].addEventListener("input", function() {
      clearTimeout(debounceTimer);
      debounceTimer = setTimeout(calculate, 80);
    });
    allInputs[i].addEventListener("change", function() {
      clearTimeout(debounceTimer);
      debounceTimer = setTimeout(calculate, 80);
    });
  }

  // --- Initial ---
  calculate();

})();
</script>
