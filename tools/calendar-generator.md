---
layout: page
title: "Free Calendar Generator — Printable Monthly & Yearly Calendars | Zovo"
description: "Generate printable monthly and yearly calendars with events, color-coded categories, US holidays, and PNG export. Customize week start, add notes, and print clean calendars. Free, no signup."
permalink: /tools/calendar-generator/
keywords: "calendar generator, printable calendar, monthly calendar, yearly calendar, calendar maker, custom calendar, blank calendar, calendar template"
date: 2026-03-19
last_modified_at: 2026-03-19
categories: [tools]
tags: [calendar, printable calendar, calendar generator, yearly calendar, monthly calendar, planner]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --cg-primary: #6C5CE7;
    --cg-primary-dark: #5A4BD1;
    --cg-primary-light: #A29BFE;
    --cg-bg: #0a0a0f;
    --cg-surface: #12121a;
    --cg-surface-alt: #181824;
    --cg-border: #1e1e2e;
    --cg-text: #e0e0e0;
    --cg-text-muted: #8888aa;
    --cg-green: #00ff88;
    --cg-green-dark: #00cc6a;
    --cg-red: #ff4466;
    --cg-yellow: #ffaa00;
    --cg-blue: #4dabf7;
    --cg-orange: #ff8c42;
    --cg-pink: #f06595;
    --cg-radius: 12px;
    --cg-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
    --cg-mono: 'JetBrains Mono', 'SF Mono', 'Consolas', monospace;
  }

  .cg-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--cg-text);
    max-width: 960px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .cg-wrapper * {
    box-sizing: border-box;
  }

  .cg-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .cg-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--cg-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .cg-hero h1 span {
    color: var(--cg-primary);
  }

  .cg-intro {
    font-size: 1.05rem;
    color: var(--cg-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .cg-updated {
    display: inline-block;
    margin-top: 12px;
    font-size: 0.78rem;
    color: var(--cg-text-muted);
    opacity: 0.7;
  }

  /* Cards */
  .cg-card {
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    padding: 24px;
    margin-bottom: 20px;
  }

  .cg-card-title {
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--cg-text);
    margin: 0 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .cg-card-title .cg-icon {
    font-size: 1.2rem;
  }

  /* Controls bar */
  .cg-controls {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }

  .cg-nav {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .cg-nav-btn {
    background: var(--cg-surface-alt);
    border: 1.5px solid var(--cg-border);
    color: var(--cg-text);
    width: 36px;
    height: 36px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    font-size: 1rem;
    transition: all 0.15s;
  }

  .cg-nav-btn:hover {
    border-color: var(--cg-primary);
    color: var(--cg-primary);
  }

  .cg-month-label {
    font-family: var(--cg-mono);
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--cg-text);
    min-width: 180px;
    text-align: center;
  }

  .cg-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 8px 16px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .cg-btn-primary {
    background: var(--cg-primary);
    color: #fff;
  }

  .cg-btn-primary:hover {
    background: var(--cg-primary-dark);
  }

  .cg-btn-sm {
    padding: 6px 12px;
    font-size: 0.8rem;
    border-radius: 6px;
  }

  .cg-btn-outline {
    background: transparent;
    color: var(--cg-text);
    border: 1.5px solid var(--cg-border);
  }

  .cg-btn-outline:hover {
    border-color: var(--cg-primary);
    color: var(--cg-primary-light);
  }

  .cg-btn-outline.active {
    background: var(--cg-primary);
    color: #fff;
    border-color: var(--cg-primary);
  }

  .cg-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
  }

  /* Calendar grid */
  .cg-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 1px;
    background: var(--cg-border);
    border: 1px solid var(--cg-border);
    border-radius: 8px;
    overflow: hidden;
  }

  .cg-day-header {
    background: var(--cg-surface-alt);
    padding: 10px 4px;
    text-align: center;
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--cg-text-muted);
  }

  .cg-day {
    background: var(--cg-surface);
    min-height: 80px;
    padding: 6px 8px;
    cursor: pointer;
    transition: background 0.1s;
    position: relative;
  }

  .cg-day:hover {
    background: var(--cg-surface-alt);
  }

  .cg-day-num {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--cg-text);
    margin-bottom: 4px;
  }

  .cg-day.cg-other-month .cg-day-num {
    color: var(--cg-text-muted);
    opacity: 0.4;
  }

  .cg-day.cg-today .cg-day-num {
    background: var(--cg-primary);
    color: #fff;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.75rem;
  }

  .cg-day-events {
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .cg-event-dot {
    font-size: 0.65rem;
    padding: 1px 4px;
    border-radius: 3px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    max-width: 100%;
    line-height: 1.3;
  }

  .cg-holiday-tag {
    font-size: 0.6rem;
    color: var(--cg-red);
    font-weight: 500;
    margin-top: 2px;
  }

  /* Year view */
  .cg-year-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 16px;
  }

  .cg-year-month {
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: 8px;
    padding: 12px;
  }

  .cg-year-month-title {
    font-size: 0.85rem;
    font-weight: 700;
    color: var(--cg-primary-light);
    margin-bottom: 8px;
    text-align: center;
  }

  .cg-mini-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 1px;
    text-align: center;
  }

  .cg-mini-header {
    font-size: 0.6rem;
    color: var(--cg-text-muted);
    padding: 2px 0;
    font-weight: 600;
  }

  .cg-mini-day {
    font-size: 0.7rem;
    padding: 3px 0;
    color: var(--cg-text);
    cursor: pointer;
    border-radius: 3px;
    transition: background 0.1s;
  }

  .cg-mini-day:hover {
    background: var(--cg-surface-alt);
  }

  .cg-mini-day.cg-mini-today {
    background: var(--cg-primary);
    color: #fff;
    font-weight: 700;
  }

  .cg-mini-day.cg-mini-empty {
    color: transparent;
    cursor: default;
  }

  .cg-mini-day.cg-mini-holiday {
    color: var(--cg-red);
    font-weight: 600;
  }

  .cg-mini-day.cg-mini-has-event {
    position: relative;
  }

  .cg-mini-day.cg-mini-has-event::after {
    content: '';
    display: block;
    width: 3px;
    height: 3px;
    border-radius: 50%;
    background: var(--cg-green);
    margin: 0 auto;
  }

  /* Event modal */
  .cg-modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.6);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 9999;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.2s;
  }

  .cg-modal-overlay.cg-show {
    opacity: 1;
    pointer-events: auto;
  }

  .cg-modal {
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    padding: 24px;
    width: 90%;
    max-width: 420px;
    max-height: 80vh;
    overflow-y: auto;
  }

  .cg-modal-title {
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--cg-text);
    margin: 0 0 16px;
  }

  .cg-modal-field {
    margin-bottom: 12px;
  }

  .cg-modal-field label {
    display: block;
    font-size: 0.75rem;
    font-weight: 500;
    color: var(--cg-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 4px;
  }

  .cg-modal-field input,
  .cg-modal-field select,
  .cg-modal-field textarea {
    width: 100%;
    padding: 9px 12px;
    border: 1.5px solid var(--cg-border);
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    color: var(--cg-text);
    background: var(--cg-surface-alt);
    outline: none;
    transition: border-color 0.15s;
  }

  .cg-modal-field input:focus,
  .cg-modal-field select:focus,
  .cg-modal-field textarea:focus {
    border-color: var(--cg-primary);
  }

  .cg-modal-field textarea {
    resize: vertical;
    min-height: 60px;
    font-size: 0.82rem;
  }

  .cg-modal-actions {
    display: flex;
    gap: 8px;
    justify-content: flex-end;
    margin-top: 16px;
  }

  .cg-event-list {
    margin-top: 12px;
  }

  .cg-event-item {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 10px;
    background: var(--cg-surface-alt);
    border: 1px solid var(--cg-border);
    border-radius: 6px;
    margin-bottom: 6px;
    font-size: 0.82rem;
  }

  .cg-event-color-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .cg-event-item-text {
    flex: 1;
    color: var(--cg-text);
  }

  .cg-event-item-note {
    font-size: 0.72rem;
    color: var(--cg-text-muted);
    margin-top: 2px;
  }

  .cg-event-remove {
    background: none;
    border: none;
    color: var(--cg-text-muted);
    cursor: pointer;
    font-size: 1rem;
    padding: 0;
    line-height: 1;
  }

  .cg-event-remove:hover {
    color: var(--cg-red);
  }

  /* Color categories */
  .cg-color-options {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .cg-color-opt {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    border: 2px solid transparent;
    cursor: pointer;
    transition: border-color 0.15s, transform 0.1s;
  }

  .cg-color-opt:hover {
    transform: scale(1.15);
  }

  .cg-color-opt.selected {
    border-color: #fff;
  }

  /* Toast */
  .cg-toast {
    position: fixed;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%) translateY(80px);
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    color: var(--cg-text);
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 0.85rem;
    font-weight: 500;
    z-index: 9999;
    opacity: 0;
    transition: all 0.3s ease;
    pointer-events: none;
  }

  .cg-toast.cg-show {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }

  /* Content section */
  .cg-content {
    margin-top: 40px;
    padding-top: 32px;
    border-top: 1px solid var(--cg-border);
  }

  .cg-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--cg-text);
    margin: 0 0 16px;
  }

  .cg-content h3 {
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--cg-text);
    margin: 28px 0 10px;
  }

  .cg-content p {
    color: var(--cg-text-muted);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .cg-content ul {
    color: var(--cg-text-muted);
    line-height: 1.75;
    padding-left: 20px;
    margin: 0 0 14px;
  }

  /* FAQ */
  .cg-faq {
    margin-top: 40px;
    padding-top: 32px;
    border-top: 1px solid var(--cg-border);
  }

  .cg-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 24px;
    text-align: center;
    color: var(--cg-text);
  }

  .cg-faq-item {
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    margin-bottom: 12px;
    overflow: hidden;
  }

  .cg-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0;
    padding: 16px 20px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--cg-surface);
    color: var(--cg-text);
    transition: background 0.15s;
  }

  .cg-faq-item h3:hover {
    background: var(--cg-surface-alt);
  }

  .cg-faq-item h3::after {
    content: '+';
    font-size: 1.3rem;
    font-weight: 400;
    color: var(--cg-text-muted);
  }

  .cg-faq-item.cg-open h3::after {
    content: '\2212';
  }

  .cg-faq-item p {
    margin: 0;
    padding: 0 20px 16px;
    color: var(--cg-text-muted);
    line-height: 1.7;
    display: none;
  }

  .cg-faq-item.cg-open p {
    display: block;
  }

  /* Author box */
  .cg-author-box {
    display: flex;
    gap: 16px;
    align-items: center;
    padding: 20px;
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    margin-top: 32px;
  }

  .cg-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--cg-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: 700;
    font-size: 1.2rem;
    flex-shrink: 0;
  }

  .cg-author-info {
    flex: 1;
  }

  .cg-author-name {
    font-weight: 600;
    color: var(--cg-text);
    margin: 0;
    font-size: 0.95rem;
  }

  .cg-author-bio {
    color: var(--cg-text-muted);
    font-size: 0.82rem;
    margin: 4px 0 0;
    line-height: 1.5;
  }

  /* Related tools */
  .cg-related {
    margin-top: 24px;
    margin-bottom: 16px;
  }

  .cg-related h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--cg-text);
    margin: 0 0 12px;
  }

  .cg-related-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
  }

  .cg-related-link {
    display: block;
    padding: 12px 16px;
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: 8px;
    color: var(--cg-text);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 500;
    transition: border-color 0.2s;
  }

  .cg-related-link:hover {
    border-color: var(--cg-primary);
  }

  .cg-related-link span {
    display: block;
    font-size: 0.75rem;
    color: var(--cg-text-muted);
    font-weight: 400;
    margin-top: 4px;
  }

  .cg-footer {
    text-align: center;
    padding: 24px 0;
    font-size: 0.78rem;
    color: var(--cg-text-muted);
  }

  .cg-footer a {
    color: var(--cg-primary);
    text-decoration: none;
  }

  .cg-footer a:hover {
    text-decoration: underline;
  }

  /* Print styles */
  @media print {
    body {
      background: #fff;
      color: #000;
    }

    .cg-wrapper {
      max-width: 100%;
      padding: 0;
      color: #000;
    }

    .cg-hero, .cg-controls .cg-toolbar, .cg-card-title, .cg-content,
    .cg-faq, .cg-author-box, .cg-related, .cg-footer, .cg-updated,
    .cg-modal-overlay, .cg-toast {
      display: none;
    }

    .cg-card {
      background: #fff;
      border: 1px solid #ccc;
      break-inside: avoid;
    }

    .cg-grid {
      background: #ccc;
      border-color: #ccc;
    }

    .cg-day-header {
      background: #f5f5f5;
      color: #333;
    }

    .cg-day {
      background: #fff;
      min-height: 60px;
    }

    .cg-day-num {
      color: #000;
    }

    .cg-day.cg-today .cg-day-num {
      background: #6C5CE7;
      color: #fff;
    }

    .cg-day.cg-other-month .cg-day-num {
      color: #bbb;
    }

    .cg-month-label {
      color: #000;
    }

    .cg-nav-btn {
      display: none;
    }

    .cg-holiday-tag {
      color: #cc0000;
    }

    .cg-year-month {
      background: #fff;
      border-color: #ccc;
    }

    .cg-year-month-title {
      color: #6C5CE7;
    }

    .cg-mini-day {
      color: #000;
    }

    .cg-mini-day.cg-mini-today {
      background: #6C5CE7;
      color: #fff;
    }

    .cg-mini-header {
      color: #666;
    }
  }

  /* Responsive */
  @media (max-width: 768px) {
    .cg-hero h1 {
      font-size: 1.6rem;
    }

    .cg-controls {
      flex-direction: column;
      align-items: stretch;
    }

    .cg-nav {
      justify-content: center;
    }

    .cg-toolbar {
      justify-content: center;
    }

    .cg-day {
      min-height: 50px;
      padding: 4px 3px;
    }

    .cg-day-num {
      font-size: 0.72rem;
    }

    .cg-event-dot {
      font-size: 0.55rem;
    }

    .cg-year-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .cg-author-box {
      flex-direction: column;
      text-align: center;
    }

    .cg-related-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 480px) {
    .cg-day-header {
      font-size: 0.6rem;
      padding: 6px 2px;
    }

    .cg-year-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="cg-wrapper">

  <div class="cg-hero">
    <h1><span>Calendar</span> Generator</h1>
    <p class="cg-intro">Generate printable monthly and yearly calendars with events, color-coded categories, and US federal holidays. Add notes, download as PNG, or print directly. Everything runs in your browser with events stored locally.</p>
    <span class="cg-updated">Last updated: March 2026</span>
  </div>

  <!-- Monthly Calendar -->
  <div class="cg-card" id="cgMonthCard">
    <div class="cg-controls">
      <div class="cg-nav">
        <button type="button" class="cg-nav-btn" onclick="cgPrev()" title="Previous month">&#9664;</button>
        <span class="cg-month-label" id="cgMonthLabel"></span>
        <button type="button" class="cg-nav-btn" onclick="cgNext()" title="Next month">&#9654;</button>
        <button type="button" class="cg-btn cg-btn-sm cg-btn-outline" onclick="cgToday()">Today</button>
      </div>
      <div class="cg-toolbar">
        <button type="button" class="cg-btn cg-btn-sm cg-btn-outline active" id="cgViewMonth" onclick="cgSetView('month')">Month</button>
        <button type="button" class="cg-btn cg-btn-sm cg-btn-outline" id="cgViewYear" onclick="cgSetView('year')">Year</button>
        <span style="color:var(--cg-text-muted);font-size:0.78rem;">Start:</span>
        <button type="button" class="cg-btn cg-btn-sm cg-btn-outline active" id="cgStartSun" onclick="cgSetWeekStart(0)">Sun</button>
        <button type="button" class="cg-btn cg-btn-sm cg-btn-outline" id="cgStartMon" onclick="cgSetWeekStart(1)">Mon</button>
        <button type="button" class="cg-btn cg-btn-sm cg-btn-primary" onclick="cgPrint()">Print</button>
        <button type="button" class="cg-btn cg-btn-sm cg-btn-outline" onclick="cgDownloadPNG()">PNG</button>
      </div>
    </div>
    <div id="cgCalendarArea"></div>
  </div>

  <!-- Event Modal -->
  <div class="cg-modal-overlay" id="cgModal">
    <div class="cg-modal">
      <div class="cg-modal-title" id="cgModalTitle">Add Event</div>
      <div class="cg-modal-field">
        <label for="cgEventTitle">Event title</label>
        <input type="text" id="cgEventTitle" placeholder="Meeting, Birthday, etc.">
      </div>
      <div class="cg-modal-field">
        <label for="cgEventNote">Notes (optional)</label>
        <textarea id="cgEventNote" placeholder="Additional details..."></textarea>
      </div>
      <div class="cg-modal-field">
        <label>Category color</label>
        <div class="cg-color-options" id="cgColorOptions"></div>
      </div>
      <div class="cg-event-list" id="cgEventList"></div>
      <div class="cg-modal-actions">
        <button type="button" class="cg-btn cg-btn-outline" onclick="cgCloseModal()">Close</button>
        <button type="button" class="cg-btn cg-btn-primary" onclick="cgSaveEvent()">Add Event</button>
      </div>
    </div>
  </div>

  <!-- SEO Content -->
  <div class="cg-content">

<h2>What Is a Calendar Generator</h2>

<p>A calendar generator is a tool that creates structured, printable calendar views for any month or year you select. Unlike pre-made calendar PDFs downloaded from the web, a generator lets you customize the output: choose the month and year, set whether weeks start on Sunday or Monday, add your own events and notes, and color-code entries by category. The result is a calendar tailored to your specific needs rather than a generic template.</p>

<p>This generator runs entirely in your browser. It uses JavaScript's Date object to compute the day-of-week for the first of each month, the number of days in each month (accounting for leap years), and where to place each date in a 7-column grid. No server is involved in generating the calendar, and no data leaves your device.</p>

<p>The tool also includes US federal holidays. These are computed algorithmically rather than stored in a static list, which means they are accurate for any year you select. Holidays like Thanksgiving (fourth Thursday of November) and Martin Luther King Jr. Day (third Monday of January) depend on the day-of-week and are calculated at render time.</p>

<h3>Monthly vs Yearly View</h3>

<p>The monthly view shows a single month at full size with room for events, notes, and holiday indicators on each date cell. This is the view most useful for day-to-day planning, as it gives you enough space to see what is scheduled on each date at a glance. You can click on any date to add or manage events.</p>

<p>The yearly view displays all 12 months in a compact grid on a single page. It is useful for long-range planning: identifying when holidays fall, counting weeks between dates, or getting an overview of the entire year. Each mini-month in the year view shows today highlighted and marks dates that have events with a small dot. Clicking on a month title switches to the full monthly view for that month.</p>

<h3>Adding Events to Your Calendar</h3>

<p>Click on any date in the monthly view to open the event editor. Enter a title, optional notes, and select a category color. The tool provides six color options: purple (default), green, red, blue, orange, and pink. Using different colors for different types of events (work, personal, deadlines, birthdays) makes it easy to scan the calendar and understand the composition of your schedule at a glance.</p>

<p>Events are stored in your browser's localStorage. They persist across page reloads, browser restarts, and system reboots. They remain on your device and are never transmitted to a server. If you clear your browser data, the events will be removed. For important data, consider exporting a screenshot or PNG before clearing storage.</p>

<h3>Printing Custom Calendars</h3>

<p>The print button triggers the browser's native print dialog with styles optimized for paper output. The dark theme is automatically converted to a white background with black text for readability on paper. Navigation buttons, toolbars, and the content section below the calendar are hidden in the print output, leaving only the clean calendar grid with events and holidays visible.</p>

<p>For best results when printing, select "A4" or "Letter" as the paper size and set margins to "Minimum" or "None." The monthly view prints well on a single page in landscape orientation. The yearly view fits on one page in portrait orientation with smaller fonts.</p>

<p>The PNG download option renders the calendar to an HTML5 Canvas element and saves the result as an image file. This is useful for sharing the calendar digitally, embedding it in a presentation, or posting it in a team chat without requiring the recipients to visit the tool.</p>

<h3>Week Start Preference</h3>

<p>The toggle between Sunday and Monday as the first day of the week reflects a genuine regional difference. In the United States, Canada, and Japan, calendars traditionally start on Sunday. In most of Europe, Russia, Australia, and much of Asia, Monday is the standard first day. The ISO 8601 standard defines Monday as the first day of the week. The toggle lets you match the convention you are accustomed to, and the setting persists between visits via localStorage.</p>

  </div>

  <!-- FAQ -->
  <div class="cg-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="cgToggleFaq(this)">Are my events saved between visits?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All events are stored in your browser's localStorage. They persist across page reloads and browser restarts. No data is sent to any server. If you clear your browser storage or use a different browser, the events will not be available. For permanent records, use the print or PNG download option to save a copy.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="cgToggleFaq(this)">Which holidays are included?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The calendar includes US federal holidays: New Year's Day, Martin Luther King Jr. Day, Presidents' Day, Memorial Day, Juneteenth, Independence Day, Labor Day, Columbus Day, Veterans Day, Thanksgiving, and Christmas Day. Holidays that fall on a fixed date are marked directly. Holidays defined by a day-of-week rule (e.g., third Monday of January) are calculated algorithmically and are accurate for any year.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="cgToggleFaq(this)">How do I print the calendar without the website header and footer?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Click the Print button. The tool uses a dedicated print stylesheet that hides the site navigation, toolbar buttons, content sections, and footer. Only the calendar grid with events and holidays is included in the printed output. In your browser's print dialog, you may also want to disable "Headers and footers" to remove the URL and page title from the printed page.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="cgToggleFaq(this)">Can I download the calendar as an image?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Click the PNG button in the toolbar. The tool renders the calendar to an HTML5 Canvas element and initiates a download of the resulting image file. The image uses a white background with clean formatting suitable for sharing, embedding in documents, or printing externally.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="cgToggleFaq(this)">Does this calendar handle leap years correctly?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The generator uses JavaScript's native Date object, which correctly handles leap years according to the Gregorian calendar rules: a year is a leap year if it is divisible by 4, except for years divisible by 100, unless also divisible by 400. February will show 29 days in leap years and 28 days otherwise.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="cg-author-box">
    <div class="cg-author-avatar">ML</div>
    <div class="cg-author-info">
      <p class="cg-author-name">Michael Lip</p>
      <p class="cg-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <div style="text-align:center;margin:16px 0;font-size:0.75rem;color:var(--cg-text-muted);">Last updated: March 2026</div>

  <!-- Cross-links -->
  <div class="cg-related">
    <h3>Related Tools</h3>
    <div class="cg-related-grid">
      <a href="/tools/pomodoro-timer/" class="cg-related-link">Pomodoro Timer <span>Focus intervals with break tracking</span></a>
      <a href="/tools/stopwatch/" class="cg-related-link">Stopwatch and Timer <span>Lap times, countdown, alarms</span></a>
      <a href="/tools/timezone-converter/" class="cg-related-link">Timezone Converter <span>World clock and meeting planner</span></a>
    </div>
  </div>

  <footer class="cg-footer">
    <p>Built by Michael Lip at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<!-- Toast -->
<div class="cg-toast" id="cgToast"></div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Calendar Generator",
      "description": "Generate printable monthly and yearly calendars with events, color-coded categories, US holidays, and PNG export.",
      "url": "https://theluckystrike.github.io/tools/calendar-generator/",
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
        {"@type": "ListItem", "position": 3, "name": "Calendar Generator", "item": "https://theluckystrike.github.io/tools/calendar-generator/"}
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
          "name": "Are my events saved between visits?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Events are stored in localStorage. They persist across page reloads and browser restarts. No data is sent to any server."
          }
        },
        {
          "@type": "Question",
          "name": "Which holidays are included?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "US federal holidays: New Year's Day, MLK Day, Presidents' Day, Memorial Day, Juneteenth, Independence Day, Labor Day, Columbus Day, Veterans Day, Thanksgiving, and Christmas Day."
          }
        },
        {
          "@type": "Question",
          "name": "How do I print the calendar without the website header and footer?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Click the Print button. The tool uses a print stylesheet that hides navigation, toolbars, and content sections, leaving only the calendar grid."
          }
        },
        {
          "@type": "Question",
          "name": "Can I download the calendar as an image?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Click the PNG button. The tool renders the calendar to an HTML5 Canvas and initiates a download of the resulting image file."
          }
        },
        {
          "@type": "Question",
          "name": "Does this calendar handle leap years correctly?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. It uses JavaScript's Date object which correctly handles leap year rules. February shows 29 days in leap years and 28 otherwise."
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

  // --- State ---
  var currentYear, currentMonth;
  var weekStart = 0; // 0 = Sunday, 1 = Monday
  var viewMode = "month"; // "month" or "year"
  var modalDate = null;
  var selectedColor = "#6C5CE7";

  var COLORS = [
    { hex: "#6C5CE7", name: "Purple" },
    { hex: "#00cc6a", name: "Green" },
    { hex: "#ff4466", name: "Red" },
    { hex: "#4dabf7", name: "Blue" },
    { hex: "#ff8c42", name: "Orange" },
    { hex: "#f06595", name: "Pink" }
  ];

  var MONTHS = ["January","February","March","April","May","June","July","August","September","October","November","December"];
  var DAYS_SUN = ["Sun","Mon","Tue","Wed","Thu","Fri","Sat"];
  var DAYS_MON = ["Mon","Tue","Wed","Thu","Fri","Sat","Sun"];

  // --- Init date ---
  var now = new Date();
  currentYear = now.getFullYear();
  currentMonth = now.getMonth();

  // --- DOM ---
  var elCalArea = document.getElementById("cgCalendarArea");
  var elMonthLabel = document.getElementById("cgMonthLabel");
  var elModal = document.getElementById("cgModal");
  var elModalTitle = document.getElementById("cgModalTitle");
  var elEventTitle = document.getElementById("cgEventTitle");
  var elEventNote = document.getElementById("cgEventNote");
  var elColorOpts = document.getElementById("cgColorOptions");
  var elEventList = document.getElementById("cgEventList");

  // --- localStorage events ---
  function getEventsKey(y, m, d) {
    return "cg_events_" + y + "-" + (m + 1) + "-" + d;
  }

  function getEvents(y, m, d) {
    try {
      var data = JSON.parse(localStorage.getItem(getEventsKey(y, m, d)));
      if (Array.isArray(data)) return data;
    } catch(e) {}
    return [];
  }

  function saveEvents(y, m, d, events) {
    try {
      if (events.length === 0) {
        localStorage.removeItem(getEventsKey(y, m, d));
      } else {
        localStorage.setItem(getEventsKey(y, m, d), JSON.stringify(events));
      }
    } catch(e) {}
  }

  // Load weekStart preference
  try {
    var savedStart = localStorage.getItem("cg_weekStart");
    if (savedStart !== null) {
      weekStart = parseInt(savedStart, 10);
    }
  } catch(e) {}

  // --- US Federal Holidays ---
  function getHolidays(year) {
    var holidays = {};

    function addH(m, d, name) {
      var key = m + "-" + d;
      holidays[key] = name;
    }

    // Fixed-date holidays
    addH(1, 1, "New Year's Day");
    addH(6, 19, "Juneteenth");
    addH(7, 4, "Independence Day");
    addH(11, 11, "Veterans Day");
    addH(12, 25, "Christmas Day");

    // Nth weekday holidays
    function nthWeekday(year, month, weekday, n) {
      var d = new Date(year, month - 1, 1);
      var count = 0;
      while (count < n) {
        if (d.getDay() === weekday) count++;
        if (count < n) d.setDate(d.getDate() + 1);
      }
      return d.getDate();
    }

    function lastWeekday(year, month, weekday) {
      var d = new Date(year, month, 0); // last day of month
      while (d.getDay() !== weekday) {
        d.setDate(d.getDate() - 1);
      }
      return d.getDate();
    }

    // MLK Day: 3rd Monday of January
    addH(1, nthWeekday(year, 1, 1, 3), "MLK Jr. Day");
    // Presidents' Day: 3rd Monday of February
    addH(2, nthWeekday(year, 2, 1, 3), "Presidents' Day");
    // Memorial Day: last Monday of May
    addH(5, lastWeekday(year, 5, 1), "Memorial Day");
    // Labor Day: 1st Monday of September
    addH(9, nthWeekday(year, 9, 1, 1), "Labor Day");
    // Columbus Day: 2nd Monday of October
    addH(10, nthWeekday(year, 10, 1, 2), "Columbus Day");
    // Thanksgiving: 4th Thursday of November
    addH(11, nthWeekday(year, 11, 4, 4), "Thanksgiving");

    return holidays;
  }

  // --- Calendar math ---
  function daysInMonth(y, m) {
    return new Date(y, m + 1, 0).getDate();
  }

  function firstDayOfMonth(y, m) {
    return new Date(y, m, 1).getDay();
  }

  function isToday(y, m, d) {
    var t = new Date();
    return t.getFullYear() === y && t.getMonth() === m && t.getDate() === d;
  }

  // --- Render month view ---
  function renderMonth() {
    var days = weekStart === 0 ? DAYS_SUN : DAYS_MON;
    var totalDays = daysInMonth(currentYear, currentMonth);
    var startDay = firstDayOfMonth(currentYear, currentMonth);
    var startOffset = (startDay - weekStart + 7) % 7;
    var holidays = getHolidays(currentYear);

    var html = '<div class="cg-grid">';

    // Headers
    for (var h = 0; h < 7; h++) {
      html += '<div class="cg-day-header">' + days[h] + '</div>';
    }

    // Previous month padding
    var prevMonth = currentMonth === 0 ? 11 : currentMonth - 1;
    var prevYear = currentMonth === 0 ? currentYear - 1 : currentYear;
    var prevDays = daysInMonth(prevYear, prevMonth);
    for (var p = startOffset - 1; p >= 0; p--) {
      var pd = prevDays - p;
      html += '<div class="cg-day cg-other-month"><div class="cg-day-num">' + pd + '</div></div>';
    }

    // Current month days
    for (var d = 1; d <= totalDays; d++) {
      var todayCls = isToday(currentYear, currentMonth, d) ? " cg-today" : "";
      var holidayKey = (currentMonth + 1) + "-" + d;
      var holiday = holidays[holidayKey] || null;
      var events = getEvents(currentYear, currentMonth, d);

      html += '<div class="cg-day' + todayCls + '" onclick="cgOpenModal(' + currentYear + ',' + currentMonth + ',' + d + ')">';
      html += '<div class="cg-day-num">' + d + '</div>';

      if (holiday) {
        html += '<div class="cg-holiday-tag">' + holiday + '</div>';
      }

      if (events.length > 0) {
        html += '<div class="cg-day-events">';
        for (var e = 0; e < Math.min(events.length, 3); e++) {
          html += '<div class="cg-event-dot" style="background:' + events[e].color + '22;color:' + events[e].color + ';">' + escapeHtml(events[e].title) + '</div>';
        }
        if (events.length > 3) {
          html += '<div class="cg-event-dot" style="color:var(--cg-text-muted);">+' + (events.length - 3) + ' more</div>';
        }
        html += '</div>';
      }

      html += '</div>';
    }

    // Next month padding
    var totalCells = startOffset + totalDays;
    var remaining = (7 - (totalCells % 7)) % 7;
    for (var n = 1; n <= remaining; n++) {
      html += '<div class="cg-day cg-other-month"><div class="cg-day-num">' + n + '</div></div>';
    }

    html += '</div>';
    elCalArea.innerHTML = html;
    elMonthLabel.textContent = MONTHS[currentMonth] + " " + currentYear;
  }

  // --- Render year view ---
  function renderYear() {
    var holidays = getHolidays(currentYear);
    var today = new Date();
    var html = '<div class="cg-year-grid">';
    var days = weekStart === 0 ? DAYS_SUN : DAYS_MON;

    for (var m = 0; m < 12; m++) {
      html += '<div class="cg-year-month">';
      html += '<div class="cg-year-month-title" style="cursor:pointer;" onclick="cgGoToMonth(' + m + ')">' + MONTHS[m] + '</div>';
      html += '<div class="cg-mini-grid">';

      for (var h = 0; h < 7; h++) {
        html += '<div class="cg-mini-header">' + days[h].charAt(0) + '</div>';
      }

      var totalDays = daysInMonth(currentYear, m);
      var startDay = firstDayOfMonth(currentYear, m);
      var startOffset = (startDay - weekStart + 7) % 7;

      for (var p = 0; p < startOffset; p++) {
        html += '<div class="cg-mini-day cg-mini-empty"></div>';
      }

      for (var d = 1; d <= totalDays; d++) {
        var isTodayDay = today.getFullYear() === currentYear && today.getMonth() === m && today.getDate() === d;
        var holidayKey = (m + 1) + "-" + d;
        var isHoliday = !!holidays[holidayKey];
        var hasEvent = getEvents(currentYear, m, d).length > 0;
        var cls = "cg-mini-day";
        if (isTodayDay) cls += " cg-mini-today";
        if (isHoliday) cls += " cg-mini-holiday";
        if (hasEvent) cls += " cg-mini-has-event";
        html += '<div class="' + cls + '">' + d + '</div>';
      }

      html += '</div></div>';
    }

    html += '</div>';
    elCalArea.innerHTML = html;
    elMonthLabel.textContent = String(currentYear);
  }

  // --- Render ---
  function render() {
    if (viewMode === "month") {
      renderMonth();
    } else {
      renderYear();
    }
  }

  // --- Navigation ---
  window.cgPrev = function() {
    if (viewMode === "month") {
      currentMonth--;
      if (currentMonth < 0) {
        currentMonth = 11;
        currentYear--;
      }
    } else {
      currentYear--;
    }
    render();
  };

  window.cgNext = function() {
    if (viewMode === "month") {
      currentMonth++;
      if (currentMonth > 11) {
        currentMonth = 0;
        currentYear++;
      }
    } else {
      currentYear++;
    }
    render();
  };

  window.cgToday = function() {
    var t = new Date();
    currentYear = t.getFullYear();
    currentMonth = t.getMonth();
    render();
  };

  window.cgSetView = function(mode) {
    viewMode = mode;
    document.getElementById("cgViewMonth").className = "cg-btn cg-btn-sm cg-btn-outline" + (mode === "month" ? " active" : "");
    document.getElementById("cgViewYear").className = "cg-btn cg-btn-sm cg-btn-outline" + (mode === "year" ? " active" : "");
    render();
  };

  window.cgSetWeekStart = function(start) {
    weekStart = start;
    document.getElementById("cgStartSun").className = "cg-btn cg-btn-sm cg-btn-outline" + (start === 0 ? " active" : "");
    document.getElementById("cgStartMon").className = "cg-btn cg-btn-sm cg-btn-outline" + (start === 1 ? " active" : "");
    try { localStorage.setItem("cg_weekStart", String(start)); } catch(e) {}
    render();
  };

  window.cgGoToMonth = function(m) {
    currentMonth = m;
    viewMode = "month";
    document.getElementById("cgViewMonth").className = "cg-btn cg-btn-sm cg-btn-outline active";
    document.getElementById("cgViewYear").className = "cg-btn cg-btn-sm cg-btn-outline";
    render();
  };

  // --- Modal ---
  function renderColorOptions() {
    var html = "";
    for (var i = 0; i < COLORS.length; i++) {
      var c = COLORS[i];
      var sel = c.hex === selectedColor ? " selected" : "";
      html += '<div class="cg-color-opt' + sel + '" style="background:' + c.hex + ';" onclick="cgSelectColor(\'' + c.hex + '\')" title="' + c.name + '"></div>';
    }
    elColorOpts.innerHTML = html;
  }

  function renderModalEvents() {
    if (!modalDate) return;
    var events = getEvents(modalDate.y, modalDate.m, modalDate.d);
    if (events.length === 0) {
      elEventList.innerHTML = "";
      return;
    }
    var html = '<div style="font-size:0.78rem;font-weight:600;color:var(--cg-text);margin-bottom:8px;">Events on this date</div>';
    for (var i = 0; i < events.length; i++) {
      var ev = events[i];
      html += '<div class="cg-event-item">';
      html += '<div class="cg-event-color-dot" style="background:' + ev.color + ';"></div>';
      html += '<div class="cg-event-item-text">' + escapeHtml(ev.title);
      if (ev.note) {
        html += '<div class="cg-event-item-note">' + escapeHtml(ev.note) + '</div>';
      }
      html += '</div>';
      html += '<button type="button" class="cg-event-remove" onclick="cgRemoveEvent(' + i + ')">&times;</button>';
      html += '</div>';
    }
    elEventList.innerHTML = html;
  }

  window.cgOpenModal = function(y, m, d) {
    modalDate = { y: y, m: m, d: d };
    elModalTitle.textContent = MONTHS[m] + " " + d + ", " + y;
    elEventTitle.value = "";
    elEventNote.value = "";
    selectedColor = COLORS[0].hex;
    renderColorOptions();
    renderModalEvents();
    elModal.classList.add("cg-show");
    setTimeout(function() { elEventTitle.focus(); }, 100);
  };

  window.cgCloseModal = function() {
    elModal.classList.remove("cg-show");
    modalDate = null;
    render();
  };

  window.cgSelectColor = function(hex) {
    selectedColor = hex;
    renderColorOptions();
  };

  window.cgSaveEvent = function() {
    if (!modalDate) return;
    var title = elEventTitle.value.trim();
    if (!title) return;
    var note = elEventNote.value.trim();
    var events = getEvents(modalDate.y, modalDate.m, modalDate.d);
    events.push({ title: title, note: note, color: selectedColor });
    saveEvents(modalDate.y, modalDate.m, modalDate.d, events);
    elEventTitle.value = "";
    elEventNote.value = "";
    renderModalEvents();
    showToast("Event added");
  };

  window.cgRemoveEvent = function(idx) {
    if (!modalDate) return;
    var events = getEvents(modalDate.y, modalDate.m, modalDate.d);
    events.splice(idx, 1);
    saveEvents(modalDate.y, modalDate.m, modalDate.d, events);
    renderModalEvents();
    showToast("Event removed");
  };

  // Close modal on overlay click
  elModal.addEventListener("click", function(e) {
    if (e.target === elModal) {
      cgCloseModal();
    }
  });

  // Close modal on Escape
  document.addEventListener("keydown", function(e) {
    if (e.key === "Escape" && elModal.classList.contains("cg-show")) {
      cgCloseModal();
    }
  });

  // Enter key to add event
  elEventTitle.addEventListener("keydown", function(e) {
    if (e.key === "Enter") {
      e.preventDefault();
      cgSaveEvent();
    }
  });

  // --- Print ---
  window.cgPrint = function() {
    window.print();
  };

  // --- PNG Download ---
  window.cgDownloadPNG = function() {
    var calArea = document.getElementById("cgCalendarArea");
    var label = elMonthLabel.textContent;

    // Create a canvas
    var canvas = document.createElement("canvas");
    var ctx = canvas.getContext("2d");
    var w = 1200;
    var lineH = 18;

    if (viewMode === "month") {
      // Compute grid dimensions
      var totalDays = daysInMonth(currentYear, currentMonth);
      var startDay = firstDayOfMonth(currentYear, currentMonth);
      var startOffset = (startDay - weekStart + 7) % 7;
      var totalCells = startOffset + totalDays;
      var rows = Math.ceil(totalCells / 7);
      var cellW = Math.floor(w / 7);
      var cellH = 80;
      var headerH = 60;
      var dayHeaderH = 30;
      var h = headerH + dayHeaderH + rows * cellH + 20;

      canvas.width = w;
      canvas.height = h;

      // Background
      ctx.fillStyle = "#ffffff";
      ctx.fillRect(0, 0, w, h);

      // Title
      ctx.fillStyle = "#333333";
      ctx.font = "bold 28px Inter, sans-serif";
      ctx.textAlign = "center";
      ctx.fillText(label, w / 2, 40);

      // Day headers
      var days = weekStart === 0 ? DAYS_SUN : DAYS_MON;
      ctx.font = "600 12px Inter, sans-serif";
      ctx.fillStyle = "#888888";
      ctx.textAlign = "center";
      for (var dh = 0; dh < 7; dh++) {
        ctx.fillText(days[dh], dh * cellW + cellW / 2, headerH + 18);
      }

      // Grid lines and days
      var holidays = getHolidays(currentYear);
      var today = new Date();
      var yTop = headerH + dayHeaderH;

      ctx.strokeStyle = "#dddddd";
      ctx.lineWidth = 1;

      var cellIdx = 0;
      for (var r = 0; r < rows; r++) {
        for (var c = 0; c < 7; c++) {
          var x = c * cellW;
          var y = yTop + r * cellH;

          ctx.strokeRect(x, y, cellW, cellH);

          var dayNum = cellIdx - startOffset + 1;
          if (dayNum >= 1 && dayNum <= totalDays) {
            // Today highlight
            if (today.getFullYear() === currentYear && today.getMonth() === currentMonth && today.getDate() === dayNum) {
              ctx.fillStyle = "#6C5CE7";
              ctx.beginPath();
              ctx.arc(x + 16, y + 16, 12, 0, Math.PI * 2);
              ctx.fill();
              ctx.fillStyle = "#ffffff";
              ctx.font = "bold 12px Inter, sans-serif";
              ctx.textAlign = "center";
              ctx.fillText(String(dayNum), x + 16, y + 20);
            } else {
              ctx.fillStyle = "#333333";
              ctx.font = "600 12px Inter, sans-serif";
              ctx.textAlign = "left";
              ctx.fillText(String(dayNum), x + 8, y + 18);
            }

            // Holiday
            var hKey = (currentMonth + 1) + "-" + dayNum;
            if (holidays[hKey]) {
              ctx.fillStyle = "#cc0000";
              ctx.font = "500 9px Inter, sans-serif";
              ctx.textAlign = "left";
              ctx.fillText(holidays[hKey], x + 8, y + 34);
            }

            // Events
            var evts = getEvents(currentYear, currentMonth, dayNum);
            for (var ei = 0; ei < Math.min(evts.length, 2); ei++) {
              ctx.fillStyle = evts[ei].color;
              ctx.font = "500 9px Inter, sans-serif";
              ctx.textAlign = "left";
              var evY = y + (holidays[hKey] ? 46 : 34) + ei * 14;
              ctx.fillText(evts[ei].title.substring(0, 18), x + 8, evY);
            }
          } else {
            // Other month
            var otherDay;
            if (dayNum < 1) {
              var prevM = currentMonth === 0 ? 11 : currentMonth - 1;
              var prevY = currentMonth === 0 ? currentYear - 1 : currentYear;
              otherDay = daysInMonth(prevY, prevM) + dayNum;
            } else {
              otherDay = dayNum - totalDays;
            }
            ctx.fillStyle = "#cccccc";
            ctx.font = "600 12px Inter, sans-serif";
            ctx.textAlign = "left";
            ctx.fillText(String(otherDay), x + 8, y + 18);
          }

          cellIdx++;
        }
      }

    } else {
      // Year view - simplified
      var monthW = 280;
      var cols = 4;
      var monthH = 180;
      var titleH = 50;
      var yearH = titleH + Math.ceil(12 / cols) * (monthH + 10) + 20;
      canvas.width = cols * (monthW + 10) + 10;
      canvas.height = yearH;

      ctx.fillStyle = "#ffffff";
      ctx.fillRect(0, 0, canvas.width, yearH);

      ctx.fillStyle = "#333333";
      ctx.font = "bold 28px Inter, sans-serif";
      ctx.textAlign = "center";
      ctx.fillText(String(currentYear), canvas.width / 2, 35);

      var miniDays = weekStart === 0 ? DAYS_SUN : DAYS_MON;
      var holidays = getHolidays(currentYear);
      var today = new Date();

      for (var mi = 0; mi < 12; mi++) {
        var col = mi % cols;
        var row = Math.floor(mi / cols);
        var mx = col * (monthW + 10) + 10;
        var my = titleH + row * (monthH + 10);

        ctx.fillStyle = "#6C5CE7";
        ctx.font = "bold 14px Inter, sans-serif";
        ctx.textAlign = "center";
        ctx.fillText(MONTHS[mi], mx + monthW / 2, my + 18);

        // Mini headers
        var miniCellW = monthW / 7;
        ctx.fillStyle = "#888888";
        ctx.font = "600 9px Inter, sans-serif";
        for (var mh = 0; mh < 7; mh++) {
          ctx.fillText(miniDays[mh].charAt(0), mx + mh * miniCellW + miniCellW / 2, my + 34);
        }

        var mTotalDays = daysInMonth(currentYear, mi);
        var mStartDay = firstDayOfMonth(currentYear, mi);
        var mOffset = (mStartDay - weekStart + 7) % 7;

        for (var md = 1; md <= mTotalDays; md++) {
          var idx = mOffset + md - 1;
          var mc = idx % 7;
          var mr = Math.floor(idx / 7);
          var dx = mx + mc * miniCellW + miniCellW / 2;
          var dy = my + 48 + mr * 18;

          var mIsToday = today.getFullYear() === currentYear && today.getMonth() === mi && today.getDate() === md;
          if (mIsToday) {
            ctx.fillStyle = "#6C5CE7";
            ctx.beginPath();
            ctx.arc(dx, dy - 4, 9, 0, Math.PI * 2);
            ctx.fill();
            ctx.fillStyle = "#ffffff";
          } else {
            var hk = (mi + 1) + "-" + md;
            ctx.fillStyle = holidays[hk] ? "#cc0000" : "#333333";
          }
          ctx.font = "500 10px Inter, sans-serif";
          ctx.fillText(String(md), dx, dy);
        }
      }
    }

    // Download
    var link = document.createElement("a");
    link.download = "calendar-" + label.replace(/\s+/g, "-").toLowerCase() + ".png";
    link.href = canvas.toDataURL("image/png");
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
    showToast("PNG downloaded");
  };

  // --- Toast ---
  var toastTimer;
  function showToast(msg) {
    var t = document.getElementById("cgToast");
    t.textContent = msg;
    t.classList.add("cg-show");
    clearTimeout(toastTimer);
    toastTimer = setTimeout(function() { t.classList.remove("cg-show"); }, 2000);
  }

  // --- Escape HTML ---
  function escapeHtml(str) {
    var div = document.createElement("div");
    div.textContent = str;
    return div.innerHTML;
  }

  // --- FAQ toggle ---
  window.cgToggleFaq = function(el) {
    var item = el.parentElement;
    item.classList.toggle("cg-open");
  };

  // --- Update weekStart buttons on init ---
  if (weekStart === 1) {
    document.getElementById("cgStartSun").className = "cg-btn cg-btn-sm cg-btn-outline";
    document.getElementById("cgStartMon").className = "cg-btn cg-btn-sm cg-btn-outline active";
  }

  // --- Initial render ---
  render();

})();
</script>
