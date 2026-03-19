---
layout: page
title: "Free GPA Calculator — Semester, Cumulative & Weighted | Zovo"
description: "Calculate your GPA with our free online tool. Supports semester GPA, cumulative GPA, weighted GPA, and target GPA calculation. Add unlimited courses with letter grades or percentages."
permalink: /tools/gpa-calculator/
keywords: "gpa calculator, college gpa calculator, cumulative gpa calculator, semester gpa calculator, weighted gpa calculator, grade point average calculator, gpa calc"
date: 2026-03-19
categories: [tools]
tags: [gpa, calculator, education, grades, college, university]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --gpa-primary: #6C5CE7;
    --gpa-primary-dark: #5A4BD1;
    --gpa-primary-light: #A29BFE;
    --gpa-bg: #0a0a0f;
    --gpa-surface: #12121a;
    --gpa-surface-alt: #181824;
    --gpa-border: #1e1e2e;
    --gpa-text: #e0e0e0;
    --gpa-text-muted: #8888aa;
    --gpa-green: #00ff88;
    --gpa-green-dark: #00cc6a;
    --gpa-red: #ff4466;
    --gpa-radius: 12px;
    --gpa-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .gpa-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--gpa-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .gpa-wrapper * {
    box-sizing: border-box;
  }

  .gpa-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .gpa-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--gpa-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .gpa-hero h1 span {
    color: var(--gpa-primary);
  }

  .gpa-intro {
    font-size: 1.05rem;
    color: var(--gpa-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Tabs */
  .gpa-tabs {
    display: flex;
    gap: 0;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid var(--gpa-border);
    margin-bottom: 24px;
  }

  .gpa-tab {
    flex: 1;
    padding: 12px 16px;
    background: var(--gpa-bg);
    border: none;
    color: var(--gpa-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    text-align: center;
    border-right: 1px solid var(--gpa-border);
  }

  .gpa-tab:last-child {
    border-right: none;
  }

  .gpa-tab.active {
    background: var(--gpa-primary);
    color: #fff;
  }

  .gpa-tab:not(.active):hover {
    background: var(--gpa-surface-alt);
    color: var(--gpa-text);
  }

  .gpa-tab-panel {
    display: none;
  }

  .gpa-tab-panel.active {
    display: block;
  }

  /* Card */
  .gpa-card {
    background: var(--gpa-surface);
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    padding: 24px;
    box-shadow: var(--gpa-shadow);
    margin-bottom: 24px;
  }

  .gpa-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--gpa-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .gpa-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--gpa-primary);
    border-radius: 2px;
  }

  /* Fields */
  .gpa-field {
    margin-bottom: 16px;
  }

  .gpa-field:last-child {
    margin-bottom: 0;
  }

  .gpa-label {
    display: block;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--gpa-text-muted);
    margin-bottom: 6px;
  }

  .gpa-input-wrap {
    position: relative;
    display: flex;
    align-items: center;
  }

  .gpa-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--gpa-bg);
    border: 1px solid var(--gpa-border);
    border-radius: 8px;
    color: var(--gpa-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    -moz-appearance: textfield;
  }

  .gpa-input::-webkit-outer-spin-button,
  .gpa-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  .gpa-input:focus {
    border-color: var(--gpa-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .gpa-select {
    width: 100%;
    padding: 10px 14px;
    background: var(--gpa-bg);
    border: 1px solid var(--gpa-border);
    border-radius: 8px;
    color: var(--gpa-text);
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

  .gpa-select:focus {
    border-color: var(--gpa-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .gpa-select option {
    background: var(--gpa-surface);
    color: var(--gpa-text);
  }

  /* Course Row */
  .gpa-course-row {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 40px;
    gap: 10px;
    align-items: end;
    margin-bottom: 10px;
  }

  .gpa-course-row-label {
    font-size: 0.75rem;
    color: var(--gpa-text-muted);
    margin-bottom: 4px;
  }

  .gpa-remove-btn {
    width: 36px;
    height: 38px;
    background: transparent;
    border: 1px solid var(--gpa-border);
    border-radius: 8px;
    color: var(--gpa-text-muted);
    font-size: 1.1rem;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.15s ease;
  }

  .gpa-remove-btn:hover {
    background: rgba(255, 68, 102, 0.15);
    border-color: var(--gpa-red);
    color: var(--gpa-red);
  }

  /* Buttons */
  .gpa-actions {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 24px;
  }

  .gpa-btn {
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

  .gpa-btn-primary {
    background: var(--gpa-primary);
    color: #fff;
  }

  .gpa-btn-primary:hover {
    background: var(--gpa-primary-dark);
  }

  .gpa-btn-secondary {
    background: var(--gpa-surface);
    color: var(--gpa-text);
    border: 1px solid var(--gpa-border);
  }

  .gpa-btn-secondary:hover {
    background: var(--gpa-surface-alt);
    border-color: var(--gpa-primary);
  }

  .gpa-btn-sm {
    padding: 7px 14px;
    font-size: 0.8rem;
  }

  .gpa-actions-spacer {
    flex: 1;
  }

  /* Results */
  .gpa-results {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-bottom: 24px;
  }

  .gpa-result-card {
    background: var(--gpa-surface);
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    padding: 20px;
    text-align: center;
    box-shadow: var(--gpa-shadow);
    transition: border-color 0.2s ease;
  }

  .gpa-result-card.highlight {
    border-color: var(--gpa-primary);
    background: linear-gradient(135deg, rgba(108, 92, 231, 0.08), var(--gpa-surface));
  }

  .gpa-result-label {
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--gpa-text-muted);
    margin-bottom: 8px;
  }

  .gpa-result-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--gpa-text);
    line-height: 1.2;
  }

  .gpa-result-card.highlight .gpa-result-value {
    color: var(--gpa-primary-light);
    font-size: 1.7rem;
  }

  .gpa-result-sub {
    font-size: 0.75rem;
    color: var(--gpa-text-muted);
    margin-top: 4px;
    font-family: 'JetBrains Mono', monospace;
  }

  /* Target result */
  .gpa-target-result {
    background: var(--gpa-surface);
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    padding: 28px;
    text-align: center;
    margin-bottom: 24px;
    box-shadow: var(--gpa-shadow);
  }

  .gpa-target-result .gpa-target-label {
    font-size: 0.85rem;
    color: var(--gpa-text-muted);
    margin-bottom: 12px;
  }

  .gpa-target-result .gpa-target-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 2.4rem;
    font-weight: 700;
    color: var(--gpa-primary-light);
    line-height: 1.2;
  }

  .gpa-target-result .gpa-target-note {
    font-size: 0.85rem;
    color: var(--gpa-text-muted);
    margin-top: 10px;
    line-height: 1.6;
  }

  .gpa-target-possible {
    color: var(--gpa-green);
  }

  .gpa-target-impossible {
    color: var(--gpa-red);
  }

  /* Inline fields */
  .gpa-inline-fields {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 20px;
  }

  /* Grade Scale Table */
  .gpa-scale-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.875rem;
  }

  .gpa-scale-table th {
    padding: 10px 16px;
    text-align: center;
    font-weight: 600;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--gpa-text-muted);
    background: var(--gpa-surface-alt);
    border-bottom: 1px solid var(--gpa-border);
  }

  .gpa-scale-table td {
    padding: 9px 16px;
    text-align: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--gpa-text);
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
  }

  .gpa-scale-table tbody tr:nth-child(even) {
    background: rgba(18, 18, 26, 0.5);
  }

  .gpa-scale-table tbody tr:nth-child(odd) {
    background: var(--gpa-surface);
  }

  .gpa-scale-table tbody tr:hover {
    background: rgba(108, 92, 231, 0.06);
  }

  .gpa-scale-table .gpa-grade-col {
    color: var(--gpa-primary-light);
    font-weight: 600;
  }

  /* Print */
  @media print {
    .gpa-wrapper {
      color: #222;
    }

    .gpa-actions, .gpa-hero, .gpa-tabs {
      display: none;
    }

    .gpa-card, .gpa-result-card, .gpa-target-result {
      background: #fff;
      border-color: #ddd;
      box-shadow: none;
      break-inside: avoid;
    }

    .gpa-result-value, .gpa-scale-table td, .gpa-scale-table th {
      color: #222;
    }

    .gpa-result-card.highlight .gpa-result-value {
      color: var(--gpa-primary);
    }
  }

  /* Content section */
  .gpa-content {
    max-width: 820px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--gpa-border);
  }

  .gpa-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--gpa-text);
    margin: 36px 0 16px;
    line-height: 1.3;
  }

  .gpa-content h2:first-child {
    margin-top: 0;
  }

  .gpa-content p {
    font-size: 0.95rem;
    color: var(--gpa-text-muted);
    line-height: 1.8;
    margin: 0 0 16px;
  }

  .gpa-content ul, .gpa-content ol {
    padding-left: 24px;
    margin: 0 0 16px;
  }

  .gpa-content li {
    font-size: 0.95rem;
    color: var(--gpa-text-muted);
    line-height: 1.8;
    margin-bottom: 6px;
  }

  .gpa-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.88rem;
    background: var(--gpa-surface);
    padding: 2px 7px;
    border-radius: 4px;
    color: var(--gpa-primary-light);
    border: 1px solid var(--gpa-border);
  }

  .gpa-formula-block {
    background: var(--gpa-surface);
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    padding: 20px 24px;
    margin: 16px 0 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    color: var(--gpa-primary-light);
    text-align: center;
    line-height: 1.8;
    overflow-x: auto;
  }

  /* FAQ */
  .gpa-faq {
    max-width: 820px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--gpa-border);
  }

  .gpa-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--gpa-text);
  }

  .gpa-faq-item {
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--gpa-surface);
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.15);
  }

  .gpa-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--gpa-text);
  }

  .gpa-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--gpa-text-muted);
    line-height: 1.7;
  }

  /* Author box */
  .gpa-author {
    max-width: 820px;
    margin: 32px auto 0;
    padding: 24px;
    background: var(--gpa-surface);
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    display: flex;
    gap: 20px;
    align-items: center;
  }

  .gpa-author-avatar {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    background: var(--gpa-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    flex-shrink: 0;
  }

  .gpa-author-info h4 {
    margin: 0 0 4px;
    font-size: 1rem;
    font-weight: 600;
    color: var(--gpa-text);
  }

  .gpa-author-info p {
    margin: 0;
    font-size: 0.85rem;
    color: var(--gpa-text-muted);
    line-height: 1.6;
  }

  .gpa-updated {
    text-align: center;
    font-size: 0.8rem;
    color: var(--gpa-text-muted);
    margin-top: 16px;
  }

  /* Cross-links */
  .gpa-related {
    max-width: 820px;
    margin: 32px auto 0;
  }

  .gpa-related h3 {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--gpa-text-muted);
    margin: 0 0 12px;
  }

  .gpa-related-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }

  .gpa-related-link {
    display: block;
    padding: 16px;
    background: var(--gpa-surface);
    border: 1px solid var(--gpa-border);
    border-radius: var(--gpa-radius);
    text-decoration: none;
    color: var(--gpa-text);
    font-size: 0.9rem;
    font-weight: 500;
    transition: all 0.2s ease;
  }

  .gpa-related-link:hover {
    border-color: var(--gpa-primary);
    background: var(--gpa-surface-alt);
  }

  .gpa-related-link span {
    display: block;
    font-size: 0.75rem;
    color: var(--gpa-text-muted);
    margin-top: 4px;
    font-weight: 400;
  }

  /* Footer */
  .gpa-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--gpa-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--gpa-border);
    margin-top: 3rem;
  }

  .gpa-footer a {
    color: var(--gpa-primary);
    text-decoration: none;
  }

  .gpa-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .gpa-hero h1 {
      font-size: 1.6rem;
    }

    .gpa-tabs {
      flex-wrap: wrap;
    }

    .gpa-tab {
      flex: 1 1 45%;
      font-size: 0.78rem;
      padding: 10px 8px;
    }

    .gpa-course-row {
      grid-template-columns: 1fr 1fr 1fr 36px;
    }

    .gpa-results {
      grid-template-columns: 1fr;
    }

    .gpa-result-card.highlight .gpa-result-value {
      font-size: 1.3rem;
    }

    .gpa-result-value {
      font-size: 1.2rem;
    }

    .gpa-inline-fields {
      grid-template-columns: 1fr;
    }

    .gpa-btn {
      padding: 8px 14px;
      font-size: 0.8rem;
    }

    .gpa-related-grid {
      grid-template-columns: 1fr;
    }

    .gpa-author {
      flex-direction: column;
      text-align: center;
    }
  }

  @media (max-width: 480px) {
    .gpa-course-row {
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }

    .gpa-course-row .gpa-course-name-col {
      grid-column: 1 / -1;
    }
  }
</style>

<div class="gpa-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="GPA Calculator">
  <meta itemprop="applicationCategory" content="EducationalApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="gpa-hero">
    <h1><span>GPA</span> Calculator</h1>
    <p class="gpa-intro">Calculate your semester GPA, cumulative GPA, or figure out what you need to hit your target. Add courses, pick grades, and see results instantly. Everything runs in your browser -- nothing is stored or sent anywhere.</p>
  </div>

  <!-- Tabs -->
  <div class="gpa-tabs">
    <button type="button" class="gpa-tab active" onclick="gpaSetTab('semester')">Semester GPA</button>
    <button type="button" class="gpa-tab" onclick="gpaSetTab('cumulative')">Cumulative GPA</button>
    <button type="button" class="gpa-tab" onclick="gpaSetTab('target')">Target GPA</button>
    <button type="button" class="gpa-tab" onclick="gpaSetTab('whatif')">What-If Mode</button>
  </div>

  <!-- SEMESTER GPA TAB -->
  <div class="gpa-tab-panel active" id="gpaTabSemester">
    <div class="gpa-card">
      <div class="gpa-card-title">Semester Courses</div>
      <div class="gpa-course-row" style="margin-bottom: 6px;">
        <div class="gpa-course-row-label">Course Name</div>
        <div class="gpa-course-row-label">Credits</div>
        <div class="gpa-course-row-label">Grade</div>
        <div></div>
      </div>
      <div id="gpaSemesterCourses"></div>
      <div style="margin-top: 12px;">
        <button type="button" class="gpa-btn gpa-btn-primary gpa-btn-sm" onclick="gpaAddCourse('semester')">+ Add Course</button>
      </div>
    </div>

    <div class="gpa-results" id="gpaSemesterResults">
      <div class="gpa-result-card highlight">
        <div class="gpa-result-label">Semester GPA</div>
        <div class="gpa-result-value" id="gpaSemGpa">0.00</div>
      </div>
      <div class="gpa-result-card">
        <div class="gpa-result-label">Total Credits</div>
        <div class="gpa-result-value" id="gpaSemCredits">0</div>
      </div>
      <div class="gpa-result-card">
        <div class="gpa-result-label">Quality Points</div>
        <div class="gpa-result-value" id="gpaSemPoints">0.00</div>
      </div>
    </div>

    <div class="gpa-actions">
      <button type="button" class="gpa-btn gpa-btn-secondary" onclick="gpaExport('semester')" id="gpaSemExportBtn">Export as Text</button>
      <button type="button" class="gpa-btn gpa-btn-secondary" onclick="window.print()">Print</button>
      <div class="gpa-actions-spacer"></div>
      <button type="button" class="gpa-btn gpa-btn-secondary" onclick="gpaClearAll('semester')">Clear All</button>
    </div>
  </div>

  <!-- CUMULATIVE GPA TAB -->
  <div class="gpa-tab-panel" id="gpaTabCumulative">
    <div class="gpa-card">
      <div class="gpa-card-title">Current Academic Record</div>
      <div class="gpa-inline-fields">
        <div class="gpa-field">
          <label class="gpa-label" for="gpaCumCurrentGpa">Current Cumulative GPA</label>
          <input type="number" id="gpaCumCurrentGpa" class="gpa-input" value="3.0" min="0" max="4" step="0.01">
        </div>
        <div class="gpa-field">
          <label class="gpa-label" for="gpaCumCurrentCredits">Total Credits Completed</label>
          <input type="number" id="gpaCumCurrentCredits" class="gpa-input" value="60" min="0" step="1">
        </div>
      </div>
    </div>

    <div class="gpa-card">
      <div class="gpa-card-title">New Semester Courses</div>
      <div class="gpa-course-row" style="margin-bottom: 6px;">
        <div class="gpa-course-row-label">Course Name</div>
        <div class="gpa-course-row-label">Credits</div>
        <div class="gpa-course-row-label">Grade</div>
        <div></div>
      </div>
      <div id="gpaCumCourses"></div>
      <div style="margin-top: 12px;">
        <button type="button" class="gpa-btn gpa-btn-primary gpa-btn-sm" onclick="gpaAddCourse('cumulative')">+ Add Course</button>
      </div>
    </div>

    <div class="gpa-results">
      <div class="gpa-result-card highlight">
        <div class="gpa-result-label">New Cumulative GPA</div>
        <div class="gpa-result-value" id="gpaCumNewGpa">0.00</div>
      </div>
      <div class="gpa-result-card">
        <div class="gpa-result-label">Semester GPA</div>
        <div class="gpa-result-value" id="gpaCumSemGpa">0.00</div>
      </div>
      <div class="gpa-result-card">
        <div class="gpa-result-label">Total Credits</div>
        <div class="gpa-result-value" id="gpaCumTotalCredits">0</div>
      </div>
    </div>

    <div class="gpa-actions">
      <button type="button" class="gpa-btn gpa-btn-secondary" onclick="gpaExport('cumulative')" id="gpaCumExportBtn">Export as Text</button>
      <button type="button" class="gpa-btn gpa-btn-secondary" onclick="window.print()">Print</button>
      <div class="gpa-actions-spacer"></div>
      <button type="button" class="gpa-btn gpa-btn-secondary" onclick="gpaClearAll('cumulative')">Clear All</button>
    </div>
  </div>

  <!-- TARGET GPA TAB -->
  <div class="gpa-tab-panel" id="gpaTabTarget">
    <div class="gpa-card">
      <div class="gpa-card-title">Target GPA Settings</div>
      <div class="gpa-inline-fields">
        <div class="gpa-field">
          <label class="gpa-label" for="gpaTargetGoal">Target GPA</label>
          <input type="number" id="gpaTargetGoal" class="gpa-input" value="3.5" min="0" max="4" step="0.01">
        </div>
        <div class="gpa-field">
          <label class="gpa-label" for="gpaTargetCurrentGpa">Current GPA</label>
          <input type="number" id="gpaTargetCurrentGpa" class="gpa-input" value="3.0" min="0" max="4" step="0.01">
        </div>
      </div>
      <div class="gpa-inline-fields">
        <div class="gpa-field">
          <label class="gpa-label" for="gpaTargetCurrentCredits">Credits Completed</label>
          <input type="number" id="gpaTargetCurrentCredits" class="gpa-input" value="60" min="0" step="1">
        </div>
        <div class="gpa-field">
          <label class="gpa-label" for="gpaTargetRemaining">Remaining Credits</label>
          <input type="number" id="gpaTargetRemaining" class="gpa-input" value="30" min="1" step="1">
        </div>
      </div>
    </div>

    <div class="gpa-target-result" id="gpaTargetResult">
      <div class="gpa-target-label">GPA needed in remaining courses</div>
      <div class="gpa-target-value" id="gpaTargetNeeded">0.00</div>
      <div class="gpa-target-note" id="gpaTargetNote"></div>
    </div>
  </div>

  <!-- WHAT-IF TAB -->
  <div class="gpa-tab-panel" id="gpaTabWhatif">
    <div class="gpa-card">
      <div class="gpa-card-title">What-If Scenario</div>
      <p style="font-size: 0.88rem; color: var(--gpa-text-muted); margin: 0 0 16px; line-height: 1.6;">Copies your current semester courses below. Change grades to see how different outcomes would affect your GPA.</p>
      <div style="margin-bottom: 16px;">
        <button type="button" class="gpa-btn gpa-btn-primary gpa-btn-sm" onclick="gpaCloneToWhatIf()">Clone Semester Courses</button>
      </div>
      <div class="gpa-course-row" style="margin-bottom: 6px;">
        <div class="gpa-course-row-label">Course Name</div>
        <div class="gpa-course-row-label">Credits</div>
        <div class="gpa-course-row-label">Grade</div>
        <div></div>
      </div>
      <div id="gpaWhatifCourses"></div>
      <div style="margin-top: 12px;">
        <button type="button" class="gpa-btn gpa-btn-primary gpa-btn-sm" onclick="gpaAddCourse('whatif')">+ Add Course</button>
      </div>
    </div>

    <div class="gpa-results">
      <div class="gpa-result-card highlight">
        <div class="gpa-result-label">What-If GPA</div>
        <div class="gpa-result-value" id="gpaWhatifGpa">0.00</div>
      </div>
      <div class="gpa-result-card">
        <div class="gpa-result-label">Original GPA</div>
        <div class="gpa-result-value" id="gpaWhatifOriginal">0.00</div>
      </div>
      <div class="gpa-result-card">
        <div class="gpa-result-label">Difference</div>
        <div class="gpa-result-value" id="gpaWhatifDiff">0.00</div>
      </div>
    </div>
  </div>

  <!-- Grade Scale Reference -->
  <div class="gpa-card" style="margin-top: 8px;">
    <div class="gpa-card-title">Grade Scale Reference (4.0 Scale)</div>
    <table class="gpa-scale-table">
      <thead>
        <tr>
          <th>Grade</th><th>Points</th><th>Grade</th><th>Points</th><th>Grade</th><th>Points</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="gpa-grade-col">A+</td><td>4.0</td>
          <td class="gpa-grade-col">B+</td><td>3.3</td>
          <td class="gpa-grade-col">C+</td><td>2.3</td>
        </tr>
        <tr>
          <td class="gpa-grade-col">A</td><td>4.0</td>
          <td class="gpa-grade-col">B</td><td>3.0</td>
          <td class="gpa-grade-col">C</td><td>2.0</td>
        </tr>
        <tr>
          <td class="gpa-grade-col">A-</td><td>3.7</td>
          <td class="gpa-grade-col">B-</td><td>2.7</td>
          <td class="gpa-grade-col">C-</td><td>1.7</td>
        </tr>
        <tr>
          <td class="gpa-grade-col">D+</td><td>1.3</td>
          <td class="gpa-grade-col">D</td><td>1.0</td>
          <td class="gpa-grade-col">D-</td><td>0.7</td>
        </tr>
        <tr>
          <td class="gpa-grade-col">F</td><td>0.0</td>
          <td colspan="4" style="color: var(--gpa-text-muted); font-family: Inter, sans-serif; font-size: 0.8rem;">Standard US 4.0 scale</td>
        </tr>
      </tbody>
    </table>
  </div>

  <!-- SEO Content -->
  <div class="gpa-content">

<h2>What Is GPA</h2>

<p>GPA stands for Grade Point Average. It is a standardized numerical representation of your academic performance, calculated by assigning point values to letter grades and weighting them by the number of credit hours each course carries. Most colleges and universities in the United States use a 4.0 scale, where an A equals 4.0 and an F equals 0.0.</p>

<p>Your GPA serves as a snapshot of your overall academic standing. Graduate programs, employers, scholarships, and honor societies all use it as a benchmark. A single number can never capture the full picture of what you learned, but it remains the standard metric that institutions rely on for admissions and hiring decisions.</p>

<p>There are several types of GPA you might encounter. Your semester GPA reflects performance in a single term. Your cumulative GPA represents all coursework across your entire college career. A major GPA only includes courses within your declared major. Some institutions also calculate a weighted GPA that accounts for course difficulty, though this is more common at the high school level.</p>

<h2>How GPA Is Calculated</h2>

<p>The GPA formula is straightforward. For each course, multiply the grade points earned by the number of credit hours. Add up all of those products to get your total quality points. Then divide by the total number of credit hours attempted.</p>

<div class="gpa-formula-block">
GPA = Sum(Grade Points x Credit Hours) / Sum(Credit Hours)
</div>

<p>Suppose you take four courses this semester:</p>

<ul>
  <li>English (3 credits) -- A (4.0): quality points = 12.0</li>
  <li>Biology (4 credits) -- B+ (3.3): quality points = 13.2</li>
  <li>History (3 credits) -- A- (3.7): quality points = 11.1</li>
  <li>Math (3 credits) -- B (3.0): quality points = 9.0</li>
</ul>

<p>Total quality points: 45.3. Total credits: 13. Semester GPA: 45.3 / 13 = 3.48.</p>

<p>Cumulative GPA works the same way but includes every semester. If you had 60 prior credits at a 3.0 GPA (180 quality points), adding this semester gives you 225.3 quality points across 73 credits, for a new cumulative GPA of 3.09.</p>

<h2>Understanding the 4.0 Scale</h2>

<p>The 4.0 scale is the most widely used grading scale in American higher education. Each letter grade maps to a specific point value. An A and A+ both equal 4.0 points. Each step down subtracts either 0.3 or 0.4 points. A B+ is 3.3, a B is 3.0, a B- is 2.7, and the pattern continues down to F at 0.0.</p>

<p>Some institutions use slight variations. A handful of schools award 4.3 for an A+. Others do not use plus/minus grading at all, so there are only five grades: A (4.0), B (3.0), C (2.0), D (1.0), F (0.0). Always check your school's specific grading policy. The calculator above uses the standard 4.0 scale with plus/minus distinctions.</p>

<p>Pass/fail and withdrawal grades generally do not factor into GPA calculations. A "P" earns the credits but carries no quality points, so it does not raise or lower your average. A "W" (withdrawal) also carries no GPA impact at most schools, though too many withdrawals can raise flags on your transcript.</p>

<h2>Semester vs Cumulative GPA</h2>

<p>Your semester GPA resets every term. It only reflects courses taken during that specific semester. If you have a rough fall semester, a strong spring semester will produce a higher spring GPA. However, both feed into your cumulative GPA.</p>

<p>Cumulative GPA is the running average across all terms. It moves more slowly than semester GPA, especially as you accumulate more credits. If you have 90 credits of coursework, a single 15-credit semester cannot shift your cumulative GPA by much in either direction. This is why early semesters matter so much -- they form the foundation that later semesters build on.</p>

<p>Some students focus exclusively on cumulative GPA, but semester GPA matters too. Applications sometimes ask for both. A steady or upward trend in semester GPA shows improvement over time, which can offset a lower cumulative number. Admissions committees pay attention to trajectories, not just static numbers.</p>

<h2>How to Raise Your GPA</h2>

<p>The math is simple but the execution takes discipline. Every grade above your current GPA pulls the average up, and every grade below pulls it down. The fewer credits you have completed, the more impact each new course has.</p>

<p>Start by calculating what is realistic. Use the Target GPA tab above to find out exactly what GPA you need in your remaining courses. Sometimes the target is achievable; other times the math makes it impossible without retaking courses.</p>

<p>Retaking courses is one option many schools allow. If your school uses grade replacement (where only the newer grade counts in GPA calculations), retaking a D or F can provide a meaningful boost. Check your school's policy, because some institutions average both attempts rather than replacing the old grade.</p>

<p>Taking courses you know you can excel in helps too. This does not mean seeking out easy classes, but rather playing to your strengths. A student who is strong in writing might pick up an additional humanities elective rather than an extra STEM course outside their major requirements.</p>

<p>Credit load also matters. If you are struggling, reducing your course load lets you invest more time per class. Four courses at a 3.8 GPA does more for your average than five courses at a 3.0.</p>

<h2>GPA Requirements by Program</h2>

<p>Different programs and opportunities set different GPA thresholds. Here are common benchmarks across US higher education:</p>

<ul>
  <li>Dean's List: typically 3.5 or higher for a given semester</li>
  <li>Cum Laude: usually 3.5 to 3.69 cumulative at graduation</li>
  <li>Magna Cum Laude: usually 3.7 to 3.89</li>
  <li>Summa Cum Laude: usually 3.9 to 4.0</li>
  <li>Medical school admissions: average accepted GPA is around 3.7</li>
  <li>Law school (top 14): average accepted GPA is around 3.8</li>
  <li>MBA programs (top 20): average accepted GPA is around 3.5</li>
  <li>Graduate school (general): minimum 3.0 is a common cutoff</li>
  <li>Academic probation: typically below 2.0</li>
</ul>

<p>These are averages and minimums, not guarantees. A 3.7 GPA does not automatically get you into medical school, and a 2.9 does not automatically disqualify you from graduate programs. Other factors like test scores, research experience, personal statements, and letters of recommendation all play a role. But GPA is often the first filter, so falling below a program's threshold can mean your application never gets a full review.</p>

  </div>

  <!-- FAQ Section -->
  <div class="gpa-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="gpa-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I calculate my cumulative GPA?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Multiply each course's grade points by its credit hours to get quality points. Sum all quality points across every semester, then divide by the total credit hours attempted. For example, if you have 180 quality points across 60 credit hours, your cumulative GPA is 180 / 60 = 3.0. The Cumulative GPA tab in this calculator handles this automatically when you enter your current GPA, credits completed, and new semester courses.</p>
      </div>
    </div>

    <div class="gpa-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does an A+ give more than 4.0 points?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">On the standard 4.0 scale used by most US institutions, an A+ equals 4.0 -- the same as an A. Some schools do award 4.3 for an A+, but this is uncommon. Check your specific institution's grading policy to confirm. This calculator uses the standard scale where both A+ and A equal 4.0 points.</p>
      </div>
    </div>

    <div class="gpa-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Do pass/fail courses affect my GPA?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">At most institutions, a passing grade (P) in a pass/fail course earns you the credit hours but does not count toward your GPA. A failing grade (F) in a pass/fail course usually does impact your GPA. Policies vary by school, so check with your registrar. When using this calculator, simply omit pass/fail courses from your entries since they carry no grade points.</p>
      </div>
    </div>

    <div class="gpa-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I raise my GPA from a 2.5 to a 3.5?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">It depends on how many credits you have completed and how many remain. Use the Target GPA tab to find out exactly what you need. If you have 30 credits at a 2.5 and 90 credits remaining, you would need a 3.83 GPA in those remaining courses. If you have 90 credits at a 2.5 and only 30 remaining, you would need a 6.5 GPA in those courses -- which is mathematically impossible on a 4.0 scale. The earlier you start improving, the more achievable the target becomes.</p>
      </div>
    </div>

    <div class="gpa-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between weighted and unweighted GPA?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">An unweighted GPA treats all courses equally on a 4.0 scale. A weighted GPA adds extra points for advanced courses (AP, IB, or honors), often using a 5.0 scale where an A in an AP class counts as 5.0 instead of 4.0. Weighted GPA is primarily a high school concept. Most colleges and universities use unweighted GPA. This calculator uses the standard unweighted 4.0 scale, which is what college registrars report on official transcripts.</p>
      </div>
    </div>

    <div class="gpa-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data stored when I use this calculator?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. This calculator runs entirely in your web browser using JavaScript. Nothing is sent to a server, no data is stored in cookies or databases, and no personal information is collected. All calculations happen locally on your device. You can verify this by checking the Network tab in your browser's developer tools while using the tool.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="gpa-author" itemscope itemtype="https://schema.org/Person">
    <div class="gpa-author-avatar">ML</div>
    <div class="gpa-author-info">
      <h4 itemprop="name">Michael Lip</h4>
      <p itemprop="description">Developer and founder of <a href="https://zovo.one" style="color: var(--gpa-primary); text-decoration: none;">zovo.one</a>. Building free, privacy-focused tools for students, developers, and professionals.</p>
    </div>
  </div>

  <div class="gpa-updated">Last updated: March 2026</div>

  <!-- Cross-links -->
  <div class="gpa-related">
    <h3>Related Tools</h3>
    <div class="gpa-related-grid">
      <a href="/tools/grade-calculator/" class="gpa-related-link">Grade Calculator <span>Final exam grade, weighted averages</span></a>
      <a href="/tools/citation-generator/" class="gpa-related-link">Citation Generator <span>APA, MLA, Chicago citations</span></a>
      <a href="/tools/compound-interest-calculator/" class="gpa-related-link">Compound Interest Calculator <span>Savings and investment growth</span></a>
    </div>
  </div>

  <footer class="gpa-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "GPA Calculator",
      "url": "https://theluckystrike.github.io/tools/gpa-calculator/",
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
      "description": "Calculate your GPA with our free online tool. Supports semester GPA, cumulative GPA, weighted GPA, and target GPA calculation."
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
          "name": "GPA Calculator",
          "item": "https://theluckystrike.github.io/tools/gpa-calculator/"
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
          "name": "How do I calculate my cumulative GPA?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Multiply each course's grade points by its credit hours to get quality points. Sum all quality points across every semester, then divide by the total credit hours attempted. For example, if you have 180 quality points across 60 credit hours, your cumulative GPA is 180 / 60 = 3.0."
          }
        },
        {
          "@type": "Question",
          "name": "Does an A+ give more than 4.0 points?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "On the standard 4.0 scale used by most US institutions, an A+ equals 4.0 -- the same as an A. Some schools do award 4.3 for an A+, but this is uncommon."
          }
        },
        {
          "@type": "Question",
          "name": "Do pass/fail courses affect my GPA?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "At most institutions, a passing grade (P) in a pass/fail course earns you the credit hours but does not count toward your GPA. A failing grade (F) in a pass/fail course usually does impact your GPA."
          }
        },
        {
          "@type": "Question",
          "name": "Can I raise my GPA from a 2.5 to a 3.5?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It depends on how many credits you have completed and how many remain. The earlier you start improving, the more achievable the target becomes. Use the Target GPA tab to find out exactly what you need."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between weighted and unweighted GPA?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "An unweighted GPA treats all courses equally on a 4.0 scale. A weighted GPA adds extra points for advanced courses (AP, IB, or honors), often using a 5.0 scale. Weighted GPA is primarily a high school concept. Most colleges use unweighted GPA."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data stored when I use this calculator?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. This calculator runs entirely in your web browser using JavaScript. Nothing is sent to a server, no data is stored in cookies or databases, and no personal information is collected."
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

  // --- Grade scale ---
  var GRADES = {
    "A+": 4.0, "A": 4.0, "A-": 3.7,
    "B+": 3.3, "B": 3.0, "B-": 2.7,
    "C+": 2.3, "C": 2.0, "C-": 1.7,
    "D+": 1.3, "D": 1.0, "D-": 0.7,
    "F": 0.0
  };

  var GRADE_OPTIONS = ["A+","A","A-","B+","B","B-","C+","C","C-","D+","D","D-","F"];

  var courseCounters = { semester: 0, cumulative: 0, whatif: 0 };
  var debounceTimer = null;

  // --- Build grade select HTML ---
  function gradeSelectHtml(id, selected) {
    var html = '<select class="gpa-select" id="' + id + '" onchange="gpaUpdate()">';
    for (var i = 0; i < GRADE_OPTIONS.length; i++) {
      var g = GRADE_OPTIONS[i];
      var sel = (g === selected) ? ' selected' : '';
      html += '<option value="' + g + '"' + sel + '>' + g + ' (' + GRADES[g].toFixed(1) + ')</option>';
    }
    html += '</select>';
    return html;
  }

  // --- Add course row ---
  window.gpaAddCourse = function(tab, name, credits, grade) {
    var container;
    if (tab === "semester") container = document.getElementById("gpaSemesterCourses");
    else if (tab === "cumulative") container = document.getElementById("gpaCumCourses");
    else container = document.getElementById("gpaWhatifCourses");

    courseCounters[tab]++;
    var idx = courseCounters[tab];
    var prefix = tab.substring(0, 3);

    var row = document.createElement("div");
    row.className = "gpa-course-row";
    row.id = prefix + "Row" + idx;

    var nameVal = name || "Course " + idx;
    var credVal = credits || 3;
    var gradeVal = grade || "A";

    row.innerHTML =
      '<div class="gpa-course-name-col"><input type="text" class="gpa-input" id="' + prefix + 'Name' + idx + '" value="' + nameVal + '" placeholder="Course name"></div>' +
      '<div><select class="gpa-select" id="' + prefix + 'Cred' + idx + '" onchange="gpaUpdate()">' +
        '<option value="1"' + (credVal==1?' selected':'') + '>1</option>' +
        '<option value="2"' + (credVal==2?' selected':'') + '>2</option>' +
        '<option value="3"' + (credVal==3?' selected':'') + '>3</option>' +
        '<option value="4"' + (credVal==4?' selected':'') + '>4</option>' +
        '<option value="5"' + (credVal==5?' selected':'') + '>5</option>' +
        '<option value="6"' + (credVal==6?' selected':'') + '>6</option>' +
      '</select></div>' +
      '<div>' + gradeSelectHtml(prefix + 'Grade' + idx, gradeVal) + '</div>' +
      '<button type="button" class="gpa-remove-btn" onclick="gpaRemoveCourse(\'' + tab + '\',' + idx + ')">x</button>';

    container.appendChild(row);
    gpaUpdate();
  };

  // --- Remove course ---
  window.gpaRemoveCourse = function(tab, idx) {
    var prefix = tab.substring(0, 3);
    var row = document.getElementById(prefix + "Row" + idx);
    if (row) row.remove();
    gpaUpdate();
  };

  // --- Get courses from a tab ---
  function getCourses(tab) {
    var container;
    if (tab === "semester") container = document.getElementById("gpaSemesterCourses");
    else if (tab === "cumulative") container = document.getElementById("gpaCumCourses");
    else container = document.getElementById("gpaWhatifCourses");

    var rows = container.querySelectorAll(".gpa-course-row");
    var courses = [];
    for (var i = 0; i < rows.length; i++) {
      var inputs = rows[i].querySelectorAll("input, select");
      if (inputs.length >= 3) {
        var nameInput = inputs[0];
        var credSelect = inputs[1];
        var gradeSelect = inputs[2];
        courses.push({
          name: nameInput.value || "Course",
          credits: parseInt(credSelect.value) || 3,
          grade: gradeSelect.value || "A",
          points: GRADES[gradeSelect.value] || 0
        });
      }
    }
    return courses;
  }

  // --- Calculate GPA from courses ---
  function calcGpa(courses) {
    var totalPoints = 0;
    var totalCredits = 0;
    for (var i = 0; i < courses.length; i++) {
      totalPoints += courses[i].points * courses[i].credits;
      totalCredits += courses[i].credits;
    }
    return {
      gpa: totalCredits > 0 ? totalPoints / totalCredits : 0,
      totalCredits: totalCredits,
      qualityPoints: totalPoints
    };
  }

  // --- Update all results ---
  window.gpaUpdate = function() {
    // Semester GPA
    var semCourses = getCourses("semester");
    var semResult = calcGpa(semCourses);
    document.getElementById("gpaSemGpa").textContent = semResult.gpa.toFixed(2);
    document.getElementById("gpaSemCredits").textContent = semResult.totalCredits;
    document.getElementById("gpaSemPoints").textContent = semResult.qualityPoints.toFixed(2);

    // Cumulative GPA
    var cumCurrentGpa = parseFloat(document.getElementById("gpaCumCurrentGpa").value) || 0;
    var cumCurrentCredits = parseInt(document.getElementById("gpaCumCurrentCredits").value) || 0;
    var cumCourses = getCourses("cumulative");
    var cumNewResult = calcGpa(cumCourses);

    var existingPoints = cumCurrentGpa * cumCurrentCredits;
    var totalPoints = existingPoints + cumNewResult.qualityPoints;
    var totalCredits = cumCurrentCredits + cumNewResult.totalCredits;
    var newCumGpa = totalCredits > 0 ? totalPoints / totalCredits : 0;

    document.getElementById("gpaCumNewGpa").textContent = newCumGpa.toFixed(2);
    document.getElementById("gpaCumSemGpa").textContent = cumNewResult.gpa.toFixed(2);
    document.getElementById("gpaCumTotalCredits").textContent = totalCredits;

    // Target GPA
    var targetGoal = parseFloat(document.getElementById("gpaTargetGoal").value) || 0;
    var targetCurrentGpa = parseFloat(document.getElementById("gpaTargetCurrentGpa").value) || 0;
    var targetCurrentCredits = parseInt(document.getElementById("gpaTargetCurrentCredits").value) || 0;
    var targetRemaining = parseInt(document.getElementById("gpaTargetRemaining").value) || 0;

    var currentPoints = targetCurrentGpa * targetCurrentCredits;
    var totalNeeded = targetGoal * (targetCurrentCredits + targetRemaining);
    var pointsNeeded = totalNeeded - currentPoints;
    var neededGpa = targetRemaining > 0 ? pointsNeeded / targetRemaining : 0;

    var targetValueEl = document.getElementById("gpaTargetNeeded");
    var targetNoteEl = document.getElementById("gpaTargetNote");

    targetValueEl.textContent = neededGpa.toFixed(2);

    if (targetRemaining <= 0) {
      targetNoteEl.textContent = "Enter remaining credits to calculate.";
      targetNoteEl.className = "gpa-target-note";
    } else if (neededGpa > 4.0) {
      targetValueEl.textContent = neededGpa.toFixed(2);
      targetNoteEl.innerHTML = '<span class="gpa-target-impossible">This target is not achievable on a 4.0 scale with ' + targetRemaining + ' remaining credits.</span> You would need to add more credits or adjust your target.';
    } else if (neededGpa < 0) {
      targetValueEl.textContent = "0.00";
      targetNoteEl.innerHTML = '<span class="gpa-target-possible">You have already surpassed your target GPA.</span> Any passing grades will keep you above your goal.';
    } else {
      targetNoteEl.innerHTML = '<span class="gpa-target-possible">Achievable.</span> Maintain a ' + neededGpa.toFixed(2) + ' GPA across your remaining ' + targetRemaining + ' credits to reach your ' + targetGoal.toFixed(2) + ' target.';
    }

    // What-If
    var whatifCourses = getCourses("whatif");
    var whatifResult = calcGpa(whatifCourses);
    document.getElementById("gpaWhatifGpa").textContent = whatifResult.gpa.toFixed(2);
    document.getElementById("gpaWhatifOriginal").textContent = semResult.gpa.toFixed(2);

    var diff = whatifResult.gpa - semResult.gpa;
    var diffEl = document.getElementById("gpaWhatifDiff");
    if (whatifCourses.length === 0 || semCourses.length === 0) {
      diffEl.textContent = "--";
      diffEl.style.color = "var(--gpa-text)";
    } else {
      diffEl.textContent = (diff >= 0 ? "+" : "") + diff.toFixed(2);
      diffEl.style.color = diff >= 0 ? "var(--gpa-green)" : "var(--gpa-red)";
    }
  };

  // --- Tab switching ---
  window.gpaSetTab = function(tabName) {
    var tabs = document.querySelectorAll(".gpa-tab");
    var panels = document.querySelectorAll(".gpa-tab-panel");

    for (var i = 0; i < tabs.length; i++) {
      tabs[i].classList.remove("active");
    }
    for (var i = 0; i < panels.length; i++) {
      panels[i].classList.remove("active");
    }

    var map = { semester: 0, cumulative: 1, target: 2, whatif: 3 };
    var panelMap = {
      semester: "gpaTabSemester",
      cumulative: "gpaTabCumulative",
      target: "gpaTabTarget",
      whatif: "gpaTabWhatif"
    };

    tabs[map[tabName]].classList.add("active");
    document.getElementById(panelMap[tabName]).classList.add("active");
  };

  // --- Clone to What-If ---
  window.gpaCloneToWhatIf = function() {
    var container = document.getElementById("gpaWhatifCourses");
    container.innerHTML = "";
    courseCounters.whatif = 0;

    var semCourses = getCourses("semester");
    for (var i = 0; i < semCourses.length; i++) {
      gpaAddCourse("whatif", semCourses[i].name, semCourses[i].credits, semCourses[i].grade);
    }
    gpaUpdate();
  };

  // --- Clear all ---
  window.gpaClearAll = function(tab) {
    var container;
    if (tab === "semester") container = document.getElementById("gpaSemesterCourses");
    else if (tab === "cumulative") container = document.getElementById("gpaCumCourses");
    else container = document.getElementById("gpaWhatifCourses");

    container.innerHTML = "";
    courseCounters[tab] = 0;

    // Re-add default courses
    gpaAddCourse(tab);
    gpaAddCourse(tab);
    gpaAddCourse(tab);
    gpaUpdate();
  };

  // --- Export ---
  window.gpaExport = function(tab) {
    var courses = getCourses(tab);
    var result = calcGpa(courses);

    var text = "GPA Calculation Results\n";
    text += "=======================\n\n";

    if (tab === "cumulative") {
      var cumGpa = parseFloat(document.getElementById("gpaCumCurrentGpa").value) || 0;
      var cumCred = parseInt(document.getElementById("gpaCumCurrentCredits").value) || 0;
      text += "Previous GPA: " + cumGpa.toFixed(2) + " (" + cumCred + " credits)\n\n";
    }

    text += "Courses:\n";
    for (var i = 0; i < courses.length; i++) {
      var c = courses[i];
      text += "  " + c.name + " | " + c.credits + " credits | " + c.grade + " (" + c.points.toFixed(1) + ")\n";
    }

    text += "\n";

    if (tab === "semester") {
      text += "Semester GPA: " + result.gpa.toFixed(2) + "\n";
      text += "Total Credits: " + result.totalCredits + "\n";
      text += "Quality Points: " + result.qualityPoints.toFixed(2) + "\n";
    } else if (tab === "cumulative") {
      var newCum = document.getElementById("gpaCumNewGpa").textContent;
      text += "New Cumulative GPA: " + newCum + "\n";
      text += "Semester GPA: " + result.gpa.toFixed(2) + "\n";
      text += "Total Credits: " + document.getElementById("gpaCumTotalCredits").textContent + "\n";
    }

    var btnId = tab === "semester" ? "gpaSemExportBtn" : "gpaCumExportBtn";

    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById(btnId);
      var orig = btn.textContent;
      btn.textContent = "Copied";
      btn.style.borderColor = "var(--gpa-green)";
      btn.style.color = "var(--gpa-green)";
      setTimeout(function() {
        btn.textContent = orig;
        btn.style.borderColor = "";
        btn.style.color = "";
      }, 2000);
    });
  };

  // --- Debounced input listeners for cumulative and target fields ---
  function attachListeners() {
    var fields = ["gpaCumCurrentGpa", "gpaCumCurrentCredits", "gpaTargetGoal", "gpaTargetCurrentGpa", "gpaTargetCurrentCredits", "gpaTargetRemaining"];
    for (var i = 0; i < fields.length; i++) {
      var el = document.getElementById(fields[i]);
      if (el) {
        el.addEventListener("input", function() {
          clearTimeout(debounceTimer);
          debounceTimer = setTimeout(gpaUpdate, 150);
        });
        el.addEventListener("change", function() {
          clearTimeout(debounceTimer);
          debounceTimer = setTimeout(gpaUpdate, 150);
        });
      }
    }
  }

  // --- Initialize ---
  function init() {
    // Add default semester courses
    gpaAddCourse("semester", "Course 1", 3, "A");
    gpaAddCourse("semester", "Course 2", 4, "B+");
    gpaAddCourse("semester", "Course 3", 3, "A-");
    gpaAddCourse("semester", "Course 4", 3, "B");

    // Add default cumulative courses
    gpaAddCourse("cumulative", "Course 1", 3, "A");
    gpaAddCourse("cumulative", "Course 2", 3, "B+");
    gpaAddCourse("cumulative", "Course 3", 3, "A-");

    attachListeners();
    gpaUpdate();
  }

  init();
})();
</script>
