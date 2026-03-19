---
layout: page
title: "Free Online Stopwatch & Countdown Timer — Lap Times & Alarms | Zovo"
description: "Precise online stopwatch with lap times, split tracking, and countdown timer with alarm. Millisecond accuracy, fullscreen mode, and exportable results. Free, no installation needed."
permalink: /tools/stopwatch/
keywords: "online stopwatch, stopwatch, countdown timer, timer online, lap timer, split timer, free stopwatch, online timer"
date: 2026-03-19
categories: [tools]
tags: [stopwatch, timer, countdown, lap-timer, time, productivity]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --sw-primary: #6C5CE7;
    --sw-primary-dark: #5A4BD1;
    --sw-primary-light: #A29BFE;
    --sw-bg: #0a0a0f;
    --sw-surface: #12121a;
    --sw-surface-alt: #181824;
    --sw-border: #1e1e2e;
    --sw-text: #e0e0e0;
    --sw-text-muted: #8888aa;
    --sw-green: #00ff88;
    --sw-green-dark: #00cc6a;
    --sw-red: #ff4466;
    --sw-yellow: #ffaa00;
    --sw-radius: 12px;
    --sw-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .sw-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--sw-text);
    max-width: 900px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .sw-wrapper * {
    box-sizing: border-box;
  }

  .sw-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .sw-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--sw-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .sw-hero h1 span {
    color: var(--sw-primary);
  }

  .sw-intro {
    font-size: 1.05rem;
    color: var(--sw-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .sw-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--sw-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--sw-border);
    border-radius: 20px;
  }

  /* Tabs */
  .sw-tabs {
    display: flex;
    gap: 0;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid var(--sw-border);
    margin-bottom: 24px;
  }

  .sw-tab {
    flex: 1;
    padding: 12px 16px;
    background: var(--sw-bg);
    border: none;
    color: var(--sw-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    text-align: center;
    border-right: 1px solid var(--sw-border);
  }

  .sw-tab:last-child {
    border-right: none;
  }

  .sw-tab.active {
    background: var(--sw-primary);
    color: #fff;
  }

  .sw-tab:not(.active):hover {
    background: var(--sw-surface-alt);
    color: var(--sw-text);
  }

  .sw-tab-panel {
    display: none;
  }

  .sw-tab-panel.active {
    display: block;
  }

  /* Display */
  .sw-display-area {
    text-align: center;
    padding: 40px 0 24px;
  }

  .sw-time-display {
    font-family: 'JetBrains Mono', monospace;
    font-size: 4.2rem;
    font-weight: 600;
    color: var(--sw-text);
    letter-spacing: 0.02em;
    line-height: 1;
    margin-bottom: 8px;
    user-select: none;
  }

  .sw-time-ms {
    font-size: 2.4rem;
    color: var(--sw-text-muted);
  }

  .sw-sub-label {
    font-size: 0.78rem;
    color: var(--sw-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-weight: 500;
  }

  /* Controls */
  .sw-controls {
    display: flex;
    gap: 12px;
    justify-content: center;
    margin-bottom: 24px;
  }

  .sw-btn {
    padding: 10px 24px;
    border: 1px solid var(--sw-border);
    border-radius: 8px;
    background: var(--sw-surface);
    color: var(--sw-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .sw-btn:hover {
    background: var(--sw-surface-alt);
    border-color: var(--sw-primary-light);
  }

  .sw-btn-primary {
    background: var(--sw-primary);
    border-color: var(--sw-primary);
    color: #fff;
  }

  .sw-btn-primary:hover {
    background: var(--sw-primary-dark);
    border-color: var(--sw-primary-dark);
  }

  .sw-btn-green {
    background: var(--sw-green-dark);
    border-color: var(--sw-green-dark);
    color: #fff;
  }

  .sw-btn-green:hover {
    background: #00b35c;
    border-color: #00b35c;
  }

  .sw-btn-red {
    background: var(--sw-red);
    border-color: var(--sw-red);
    color: #fff;
  }

  .sw-btn-red:hover {
    background: #e0334d;
    border-color: #e0334d;
  }

  .sw-btn-sm {
    padding: 6px 14px;
    font-size: 0.8rem;
  }

  /* Shortcuts */
  .sw-shortcuts {
    display: flex;
    gap: 16px;
    justify-content: center;
    margin-bottom: 24px;
    flex-wrap: wrap;
  }

  .sw-shortcut {
    font-size: 0.75rem;
    color: var(--sw-text-muted);
  }

  .sw-key {
    display: inline-block;
    padding: 2px 8px;
    background: var(--sw-surface);
    border: 1px solid var(--sw-border);
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--sw-text);
    margin-right: 4px;
  }

  /* Lap Table */
  .sw-card {
    background: var(--sw-surface);
    border: 1px solid var(--sw-border);
    border-radius: var(--sw-radius);
    padding: 24px;
    box-shadow: var(--sw-shadow);
    margin-bottom: 24px;
  }

  .sw-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--sw-text-muted);
    margin: 0 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .sw-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--sw-primary);
    border-radius: 2px;
  }

  .sw-lap-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.85rem;
  }

  .sw-lap-table th {
    text-align: left;
    padding: 8px 12px;
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--sw-text-muted);
    border-bottom: 1px solid var(--sw-border);
  }

  .sw-lap-table td {
    padding: 8px 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--sw-text);
    border-bottom: 1px solid rgba(30, 30, 46, 0.5);
  }

  .sw-lap-table tr.fastest td {
    color: var(--sw-green);
  }

  .sw-lap-table tr.slowest td {
    color: var(--sw-red);
  }

  .sw-lap-table .sw-lap-badge {
    font-family: 'Inter', sans-serif;
    font-size: 0.65rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    padding: 2px 6px;
    border-radius: 4px;
    margin-left: 8px;
  }

  .sw-lap-badge-fast {
    background: rgba(0, 255, 136, 0.15);
    color: var(--sw-green);
  }

  .sw-lap-badge-slow {
    background: rgba(255, 68, 102, 0.15);
    color: var(--sw-red);
  }

  .sw-lap-empty {
    text-align: center;
    padding: 20px;
    color: var(--sw-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
  }

  .sw-lap-actions {
    display: flex;
    gap: 8px;
    margin-top: 12px;
  }

  /* Countdown Input */
  .sw-cd-input-area {
    display: flex;
    gap: 8px;
    justify-content: center;
    align-items: center;
    margin-bottom: 20px;
  }

  .sw-cd-input-group {
    text-align: center;
  }

  .sw-cd-input-group label {
    display: block;
    font-size: 0.7rem;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--sw-text-muted);
    margin-bottom: 4px;
  }

  .sw-cd-input {
    width: 72px;
    padding: 10px 8px;
    background: var(--sw-bg);
    border: 1px solid var(--sw-border);
    border-radius: 8px;
    color: var(--sw-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.3rem;
    font-weight: 600;
    text-align: center;
    outline: none;
    transition: border-color 0.2s;
  }

  .sw-cd-input:focus {
    border-color: var(--sw-primary);
  }

  .sw-cd-sep {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.6rem;
    color: var(--sw-text-muted);
    padding-top: 18px;
  }

  /* Quick Presets */
  .sw-presets {
    display: flex;
    gap: 8px;
    justify-content: center;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .sw-preset-btn {
    padding: 6px 14px;
    background: var(--sw-bg);
    border: 1px solid var(--sw-border);
    border-radius: 6px;
    color: var(--sw-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
  }

  .sw-preset-btn:hover {
    border-color: var(--sw-primary);
    color: var(--sw-text);
  }

  .sw-preset-btn.active {
    background: var(--sw-primary);
    border-color: var(--sw-primary);
    color: #fff;
  }

  /* Progress Bar */
  .sw-progress-bar {
    width: 100%;
    height: 6px;
    background: var(--sw-border);
    border-radius: 3px;
    margin-bottom: 20px;
    overflow: hidden;
  }

  .sw-progress-fill {
    height: 100%;
    background: var(--sw-primary);
    border-radius: 3px;
    transition: width 0.3s linear;
    width: 100%;
  }

  /* Repeat Toggle */
  .sw-toggle-row {
    display: flex;
    align-items: center;
    gap: 10px;
    justify-content: center;
    margin-bottom: 16px;
  }

  .sw-toggle-label {
    font-size: 0.82rem;
    color: var(--sw-text-muted);
    font-weight: 500;
  }

  .sw-toggle {
    position: relative;
    width: 40px;
    height: 22px;
    cursor: pointer;
  }

  .sw-toggle input {
    opacity: 0;
    width: 0;
    height: 0;
    position: absolute;
  }

  .sw-toggle-track {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: var(--sw-border);
    border-radius: 11px;
    transition: background 0.2s;
  }

  .sw-toggle input:checked + .sw-toggle-track {
    background: var(--sw-primary);
  }

  .sw-toggle-thumb {
    position: absolute;
    top: 2px;
    left: 2px;
    width: 18px;
    height: 18px;
    background: var(--sw-text);
    border-radius: 50%;
    transition: transform 0.2s;
    pointer-events: none;
  }

  .sw-toggle input:checked ~ .sw-toggle-thumb {
    transform: translateX(18px);
  }

  /* Fullscreen */
  .sw-fullscreen-btn {
    position: fixed;
    top: 16px;
    right: 16px;
    z-index: 1000;
    padding: 8px 12px;
    background: var(--sw-surface);
    border: 1px solid var(--sw-border);
    border-radius: 8px;
    color: var(--sw-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
    cursor: pointer;
    transition: all 0.2s;
    display: none;
  }

  .sw-fullscreen-btn:hover {
    border-color: var(--sw-primary);
    color: var(--sw-text);
  }

  .sw-wrapper.fullscreen {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    max-width: 100%;
    background: var(--sw-bg);
    z-index: 999;
    overflow-y: auto;
    padding: 24px;
  }

  .sw-wrapper.fullscreen .sw-fullscreen-btn {
    display: block;
  }

  .sw-wrapper.fullscreen .sw-hero,
  .sw-wrapper.fullscreen .sw-content,
  .sw-wrapper.fullscreen .sw-faq,
  .sw-wrapper.fullscreen .sw-author-box,
  .sw-wrapper.fullscreen .sw-footer,
  .sw-wrapper.fullscreen .sw-related,
  .sw-wrapper.fullscreen .sw-updated-signal {
    display: none;
  }

  .sw-wrapper.fullscreen .sw-time-display {
    font-size: 6rem;
  }

  .sw-wrapper.fullscreen .sw-time-ms {
    font-size: 3.2rem;
  }

  /* SEO Content */
  .sw-content {
    margin-top: 16px;
    margin-bottom: 24px;
  }

  .sw-content h2 {
    font-size: 1.35rem;
    font-weight: 700;
    color: var(--sw-text);
    margin: 32px 0 12px;
    line-height: 1.3;
  }

  .sw-content p {
    font-size: 0.95rem;
    color: var(--sw-text-muted);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .sw-content ul, .sw-content ol {
    margin: 0 0 14px;
    padding-left: 24px;
  }

  .sw-content li {
    font-size: 0.95rem;
    color: var(--sw-text-muted);
    line-height: 1.75;
    margin-bottom: 4px;
  }

  /* FAQ */
  .sw-faq {
    margin-bottom: 24px;
  }

  .sw-faq h2 {
    font-size: 1.35rem;
    font-weight: 700;
    color: var(--sw-text);
    margin: 0 0 20px;
  }

  .sw-faq-item {
    background: var(--sw-surface);
    border: 1px solid var(--sw-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin-bottom: 8px;
  }

  .sw-faq-item h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--sw-text);
    margin: 0 0 8px;
  }

  .sw-faq-item p {
    font-size: 0.88rem;
    color: var(--sw-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Author Box */
  .sw-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px;
    background: var(--sw-surface);
    border: 1px solid var(--sw-border);
    border-radius: var(--sw-radius);
    margin-bottom: 16px;
  }

  .sw-author-avatar {
    width: 52px;
    height: 52px;
    border-radius: 50%;
    background: var(--sw-primary);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    flex-shrink: 0;
  }

  .sw-author-info p {
    margin: 0;
  }

  .sw-author-name {
    font-weight: 600;
    font-size: 0.95rem;
    color: var(--sw-text);
  }

  .sw-author-bio {
    font-size: 0.82rem;
    color: var(--sw-text-muted);
    line-height: 1.6;
    margin-top: 4px;
  }

  /* Related */
  .sw-related {
    margin-bottom: 16px;
  }

  .sw-related h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--sw-text);
    margin: 0 0 12px;
  }

  .sw-related-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
  }

  .sw-related-link {
    display: block;
    padding: 12px 16px;
    background: var(--sw-surface);
    border: 1px solid var(--sw-border);
    border-radius: 8px;
    color: var(--sw-text);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 500;
    transition: border-color 0.2s;
  }

  .sw-related-link:hover {
    border-color: var(--sw-primary);
  }

  .sw-related-link span {
    display: block;
    font-size: 0.75rem;
    color: var(--sw-text-muted);
    font-weight: 400;
    margin-top: 4px;
  }

  .sw-footer {
    text-align: center;
    padding: 24px 0;
    font-size: 0.78rem;
    color: var(--sw-text-muted);
  }

  .sw-footer a {
    color: var(--sw-primary);
    text-decoration: none;
  }

  .sw-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .sw-hero h1 {
      font-size: 1.6rem;
    }

    .sw-time-display {
      font-size: 2.8rem;
    }

    .sw-time-ms {
      font-size: 1.6rem;
    }

    .sw-controls {
      flex-wrap: wrap;
    }

    .sw-cd-input {
      width: 60px;
      font-size: 1.1rem;
      padding: 8px 6px;
    }

    .sw-presets {
      gap: 6px;
    }

    .sw-preset-btn {
      padding: 5px 10px;
      font-size: 0.72rem;
    }

    .sw-lap-table {
      font-size: 0.78rem;
    }

    .sw-lap-table th,
    .sw-lap-table td {
      padding: 6px 8px;
    }

    .sw-related-grid {
      grid-template-columns: 1fr;
    }

    .sw-author-box {
      flex-direction: column;
      text-align: center;
    }

    .sw-wrapper.fullscreen .sw-time-display {
      font-size: 3.6rem;
    }

    .sw-wrapper.fullscreen .sw-time-ms {
      font-size: 2rem;
    }
  }
</style>

<div class="sw-wrapper" id="swWrapper">
  <button type="button" class="sw-fullscreen-btn" id="swExitFs" onclick="swToggleFullscreen()">Exit Fullscreen</button>

  <div class="sw-hero">
    <h1><span>Stopwatch</span> and Timer</h1>
    <p class="sw-intro">A precise online stopwatch with lap tracking and a countdown timer with alarm. Millisecond accuracy, keyboard controls, CSV export, and fullscreen mode. Runs entirely in your browser with no installation.</p>
    <span class="sw-updated">Last updated: March 2026</span>
  </div>

  <!-- Tabs -->
  <div class="sw-tabs">
    <button type="button" class="sw-tab active" id="swTabBtnStopwatch" onclick="swSetTab('stopwatch')">Stopwatch</button>
    <button type="button" class="sw-tab" id="swTabBtnCountdown" onclick="swSetTab('countdown')">Countdown Timer</button>
  </div>

  <!-- ==================== STOPWATCH TAB ==================== -->
  <div class="sw-tab-panel active" id="swTabStopwatch">

    <div class="sw-display-area">
      <div class="sw-time-display" id="swStopwatchDisplay">00:00:00<span class="sw-time-ms">.000</span></div>
      <div class="sw-sub-label">Stopwatch</div>
    </div>

    <div class="sw-controls">
      <button type="button" class="sw-btn sw-btn-primary" id="swStartBtn" onclick="swToggleStopwatch()">Start</button>
      <button type="button" class="sw-btn sw-btn-green" onclick="swLap()">Lap</button>
      <button type="button" class="sw-btn" onclick="swResetStopwatch()">Reset</button>
      <button type="button" class="sw-btn" onclick="swToggleFullscreen()">Fullscreen</button>
    </div>

    <div class="sw-shortcuts">
      <span class="sw-shortcut"><span class="sw-key">Space</span> Start / Stop</span>
      <span class="sw-shortcut"><span class="sw-key">L</span> Lap</span>
      <span class="sw-shortcut"><span class="sw-key">R</span> Reset</span>
    </div>

    <!-- Lap Table -->
    <div class="sw-card" id="swLapCard">
      <div class="sw-card-title">Lap Times</div>
      <table class="sw-lap-table">
        <thead>
          <tr>
            <th>Lap</th>
            <th>Lap Time</th>
            <th>Split Time</th>
            <th></th>
          </tr>
        </thead>
        <tbody id="swLapBody">
          <tr><td colspan="4" class="sw-lap-empty">Press Lap to record split times</td></tr>
        </tbody>
      </table>
      <div class="sw-lap-actions" id="swLapActions" style="display:none;">
        <button type="button" class="sw-btn sw-btn-sm" onclick="swExportCSV()">Export CSV</button>
        <button type="button" class="sw-btn sw-btn-sm" onclick="swClearLaps()">Clear Laps</button>
      </div>
    </div>

  </div>

  <!-- ==================== COUNTDOWN TAB ==================== -->
  <div class="sw-tab-panel" id="swTabCountdown">

    <div class="sw-display-area">
      <div class="sw-time-display" id="swCountdownDisplay">00:00:00</div>
      <div class="sw-sub-label" id="swCdLabel">Countdown Timer</div>
    </div>

    <div class="sw-progress-bar" id="swCdProgressBar">
      <div class="sw-progress-fill" id="swCdProgressFill"></div>
    </div>

    <div class="sw-cd-input-area" id="swCdInputArea">
      <div class="sw-cd-input-group">
        <label for="swCdHours">Hours</label>
        <input type="number" class="sw-cd-input" id="swCdHours" value="0" min="0" max="99">
      </div>
      <span class="sw-cd-sep">:</span>
      <div class="sw-cd-input-group">
        <label for="swCdMinutes">Min</label>
        <input type="number" class="sw-cd-input" id="swCdMinutes" value="5" min="0" max="59">
      </div>
      <span class="sw-cd-sep">:</span>
      <div class="sw-cd-input-group">
        <label for="swCdSeconds">Sec</label>
        <input type="number" class="sw-cd-input" id="swCdSeconds" value="0" min="0" max="59">
      </div>
    </div>

    <div class="sw-presets" id="swPresets">
      <button type="button" class="sw-preset-btn" onclick="swSetPreset(0,1,0)">1 min</button>
      <button type="button" class="sw-preset-btn" onclick="swSetPreset(0,5,0)">5 min</button>
      <button type="button" class="sw-preset-btn" onclick="swSetPreset(0,10,0)">10 min</button>
      <button type="button" class="sw-preset-btn" onclick="swSetPreset(0,15,0)">15 min</button>
      <button type="button" class="sw-preset-btn" onclick="swSetPreset(0,30,0)">30 min</button>
      <button type="button" class="sw-preset-btn" onclick="swSetPreset(1,0,0)">1 hr</button>
    </div>

    <div class="sw-toggle-row">
      <span class="sw-toggle-label">Repeat</span>
      <label class="sw-toggle">
        <input type="checkbox" id="swCdRepeat">
        <span class="sw-toggle-track"></span>
        <span class="sw-toggle-thumb"></span>
      </label>
    </div>

    <div class="sw-controls">
      <button type="button" class="sw-btn sw-btn-primary" id="swCdStartBtn" onclick="swToggleCountdown()">Start</button>
      <button type="button" class="sw-btn" onclick="swResetCountdown()">Reset</button>
      <button type="button" class="sw-btn" onclick="swToggleFullscreen()">Fullscreen</button>
    </div>

    <div class="sw-shortcuts">
      <span class="sw-shortcut"><span class="sw-key">Space</span> Start / Pause</span>
      <span class="sw-shortcut"><span class="sw-key">R</span> Reset</span>
    </div>

  </div>

  <!-- SEO Content -->
  <div class="sw-content">

<h2>What Is an Online Stopwatch</h2>

<p>An online stopwatch is a browser-based timing tool that measures elapsed time from the moment you press start until you press stop. Unlike a physical stopwatch, it requires no hardware and works on any device with a web browser: phones, tablets, laptops, and desktops. The tool above measures time with millisecond precision using JavaScript's Date.now() function, which returns timestamps from the system clock.</p>

<p>The key advantage of a software stopwatch over a hardware one is the data it can record. Each lap is stored in a table with both lap time (the duration of that specific lap) and split time (total elapsed time from the start). You can see at a glance which lap was fastest and which was slowest. The data can be exported as a CSV file for analysis in a spreadsheet.</p>

<p>This stopwatch continues running accurately even if you switch to another browser tab. Many web timers lose accuracy in background tabs because browsers throttle JavaScript intervals. This tool sidesteps that problem by calculating elapsed time from timestamps rather than counting interval ticks. When you return to the tab, the display shows the correct time.</p>

<h2>Stopwatch vs Timer</h2>

<p>A stopwatch counts up from zero. You start it and let it run until you decide to stop. It answers the question: how long did that take? A timer (or countdown timer) counts down from a set duration to zero. You specify the target time in advance and the timer tells you when that duration has passed. It answers the question: has enough time passed yet?</p>

<p>Both tools measure time, but they serve different purposes. Stopwatches are used for measuring events whose duration is unknown in advance: running a race, timing a presentation, tracking how long a task takes. Timers are used when you know how long something should last: cooking for 10 minutes, taking a 5-minute break, timing an exam period.</p>

<p>This tool includes both. The Stopwatch tab gives you a count-up timer with lap recording. The Countdown Timer tab gives you a configurable countdown with an alarm that sounds when it reaches zero. Both share the same keyboard shortcuts and fullscreen mode.</p>

<h2>How Lap Timing Works</h2>

<p>When you press the Lap button, the stopwatch records two values. The split time is the total elapsed time from when you first pressed Start. The lap time is the time elapsed since the previous lap (or since the start if this is the first lap). The difference matters for analysis.</p>

<p>Consider a runner doing 400-meter laps on a track. After four laps, the split times might be 1:12, 2:28, 3:50, 5:15. The corresponding lap times would be 1:12, 1:16, 1:22, 1:25. The split times show overall progress, while the lap times reveal pacing -- this runner slowed down with each successive lap.</p>

<p>The table highlights the fastest lap in green and the slowest lap in red (when there are at least 3 laps). These visual indicators make it easy to spot your best and worst segments without doing mental arithmetic. For athletic training, knowing your fastest and slowest intervals helps you calibrate your pacing strategy.</p>

<p>The export function generates a CSV file with columns for lap number, lap time, and split time. You can open this file in any spreadsheet application (Excel, Google Sheets, LibreOffice Calc) for further analysis, charting, or record-keeping.</p>

<h2>Using Timers for Productivity</h2>

<p>Countdown timers have direct applications for productivity beyond the Pomodoro Technique. Timeboxing is a project management method where you allocate a fixed amount of time to a task and stop when the timer expires, regardless of whether the task is finished. This prevents scope creep and forces prioritization.</p>

<p>Meeting timers keep discussions on track. Setting a 15-minute countdown for a standup meeting or a 5-minute countdown for each agenda item creates a shared sense of urgency that reduces tangents. The visual progress bar provides a non-verbal cue that time is running out.</p>

<p>Study sessions benefit from timed intervals. The spacing effect in memory research shows that distributing study across multiple shorter sessions produces better retention than one long session. A countdown timer helps enforce those boundaries. Set it for your planned study duration, work until it rings, take a break, and repeat.</p>

<p>The repeat toggle on the countdown timer is useful for interval training, both physical and mental. Set a duration, enable repeat, and the timer automatically restarts when it hits zero. This is practical for HIIT workouts, timed drills, or any situation where you need recurring intervals of the same length.</p>

<h2>Accuracy and Browser Behavior</h2>

<p>JavaScript timing in browsers is subject to certain constraints. The system clock provides millisecond-resolution timestamps, but the actual precision depends on the browser and operating system. Most modern browsers deliver timing accuracy within 1-2 milliseconds, which is sufficient for nearly all practical use cases.</p>

<p>When a tab is in the background, browsers may reduce the frequency of timer callbacks (setInterval, setTimeout, requestAnimationFrame) to save battery and CPU. This tool compensates by storing the start timestamp and calculating elapsed time on each frame. The displayed time is always derived from the difference between the current timestamp and the start timestamp, so it remains accurate regardless of callback frequency.</p>

<p>For applications requiring sub-millisecond precision (scientific instruments, high-frequency trading), a browser-based timer is not the appropriate tool. For athletics, cooking, studying, and general productivity, the accuracy provided here is more than adequate.</p>

  </div>

  <!-- FAQ Section -->
  <div class="sw-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="sw-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is this stopwatch?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The stopwatch uses Date.now() for timing, which provides millisecond-resolution timestamps from your system clock. In practice, accuracy is within 1-2 milliseconds on modern browsers and operating systems. This is sufficient for athletics, cooking, presentations, and general productivity. It is not suitable for scientific measurements requiring sub-millisecond precision.</p>
      </div>
    </div>

    <div class="sw-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does the timer keep running if I switch tabs or lock my phone?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes, the timer continues tracking time accurately when the tab is in the background. It calculates elapsed time from timestamps rather than relying on interval callbacks, so throttling by the browser does not affect accuracy. When you return to the tab, the correct time is displayed. However, if the browser fully suspends the page (some mobile browsers do this aggressively), the timer may need a moment to update when you return.</p>
      </div>
    </div>

    <div class="sw-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I export my lap times?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">After recording laps, click the "Export CSV" button below the lap table. This downloads a CSV file containing columns for lap number, lap time, and split time. You can open this file in Excel, Google Sheets, LibreOffice Calc, or any other spreadsheet application for further analysis or record-keeping.</p>
      </div>
    </div>

    <div class="sw-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What sound does the countdown alarm make?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The alarm is generated using the Web Audio API directly in your browser. It plays a series of ascending tones that are distinct enough to be heard but not jarring. No external audio files are downloaded. The alarm requires that you have interacted with the page at least once (clicked a button) before it can play, due to browser autoplay policies.</p>
      </div>
    </div>

    <div class="sw-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use this for interval training?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. On the Countdown Timer tab, set your desired interval duration and enable the Repeat toggle. The timer will automatically restart each time it reaches zero, playing the alarm at each cycle. This works for HIIT workouts, timed drills, cooking intervals, or any activity that requires repeating timed segments.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="sw-author-box">
    <div class="sw-author-avatar">ML</div>
    <div class="sw-author-info">
      <p class="sw-author-name">Michael Lip</p>
      <p class="sw-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <div class="sw-updated-signal" style="text-align:center;margin-bottom:16px;font-size:0.75rem;color:var(--sw-text-muted);">Last updated: March 2026</div>

  <!-- Cross-links -->
  <div class="sw-related">
    <h3>Related Tools</h3>
    <div class="sw-related-grid">
      <a href="/tools/pomodoro-timer/" class="sw-related-link">Pomodoro Timer <span>Focus intervals with break tracking</span></a>
      <a href="/tools/unix-timestamp-converter/" class="sw-related-link">Unix Timestamp Converter <span>Convert timestamps and dates</span></a>
      <a href="/tools/word-counter/" class="sw-related-link">Word Counter <span>Words, characters, readability</span></a>
    </div>
  </div>

  <footer class="sw-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Online Stopwatch & Countdown Timer",
      "description": "Precise online stopwatch with lap times, split tracking, and countdown timer with alarm. Millisecond accuracy, fullscreen mode, and exportable results.",
      "url": "https://theluckystrike.github.io/tools/stopwatch/",
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
      }
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/"},
        {"@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/"},
        {"@type": "ListItem", "position": 3, "name": "Stopwatch & Timer", "item": "https://theluckystrike.github.io/tools/stopwatch/"}
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
          "name": "How accurate is this stopwatch?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The stopwatch uses Date.now() for millisecond-resolution timestamps. Accuracy is within 1-2 milliseconds on modern browsers, sufficient for athletics and general productivity."
          }
        },
        {
          "@type": "Question",
          "name": "Does the timer keep running if I switch tabs or lock my phone?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. It calculates elapsed time from timestamps rather than interval callbacks, so browser throttling does not affect accuracy."
          }
        },
        {
          "@type": "Question",
          "name": "How do I export my lap times?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Click Export CSV below the lap table. This downloads a CSV file with lap number, lap time, and split time columns."
          }
        },
        {
          "@type": "Question",
          "name": "What sound does the countdown alarm make?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The alarm is generated using the Web Audio API in your browser. It plays a series of ascending tones. No external audio files are needed."
          }
        },
        {
          "@type": "Question",
          "name": "Can I use this for interval training?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Set your interval duration on the Countdown Timer tab and enable the Repeat toggle. The timer auto-restarts at zero with an alarm each cycle."
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

  // --- Audio (Web Audio API) ---
  var audioCtx = null;

  function playAlarm() {
    try {
      if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      if (audioCtx.state === "suspended") audioCtx.resume();
      var now = audioCtx.currentTime;
      var freqs = [523, 659, 784, 1047, 784, 1047];
      for (var i = 0; i < freqs.length; i++) {
        var osc = audioCtx.createOscillator();
        var gain = audioCtx.createGain();
        osc.connect(gain);
        gain.connect(audioCtx.destination);
        osc.type = "sine";
        osc.frequency.value = freqs[i];
        gain.gain.setValueAtTime(0.25, now + i * 0.18);
        gain.gain.exponentialRampToValueAtTime(0.001, now + i * 0.18 + 0.3);
        osc.start(now + i * 0.18);
        osc.stop(now + i * 0.18 + 0.3);
      }
    } catch(e) {}
  }

  // --- Tab switching ---
  var currentTab = "stopwatch";

  window.swSetTab = function(tab) {
    currentTab = tab;
    var btnSW = document.getElementById("swTabBtnStopwatch");
    var btnCD = document.getElementById("swTabBtnCountdown");
    var panelSW = document.getElementById("swTabStopwatch");
    var panelCD = document.getElementById("swTabCountdown");

    btnSW.className = "sw-tab" + (tab === "stopwatch" ? " active" : "");
    btnCD.className = "sw-tab" + (tab === "countdown" ? " active" : "");
    panelSW.className = "sw-tab-panel" + (tab === "stopwatch" ? " active" : "");
    panelCD.className = "sw-tab-panel" + (tab === "countdown" ? " active" : "");
  };

  // ==================== STOPWATCH ====================
  var sw = {
    running: false,
    startTimestamp: null,
    accumulated: 0, // ms accumulated before current run
    animFrame: null,
    laps: [],       // [{lapMs, splitMs}]
    lastLapSplit: 0 // ms at last lap
  };

  var elSwDisplay = document.getElementById("swStopwatchDisplay");
  var elSwStartBtn = document.getElementById("swStartBtn");
  var elSwLapBody = document.getElementById("swLapBody");
  var elSwLapActions = document.getElementById("swLapActions");

  function formatStopwatch(ms) {
    var totalSec = Math.floor(ms / 1000);
    var hours = Math.floor(totalSec / 3600);
    var mins = Math.floor((totalSec % 3600) / 60);
    var secs = totalSec % 60;
    var millis = ms % 1000;

    var hh = (hours < 10 ? "0" : "") + hours;
    var mm = (mins < 10 ? "0" : "") + mins;
    var ss = (secs < 10 ? "0" : "") + secs;
    var mss = (millis < 100 ? "0" : "") + (millis < 10 ? "0" : "") + millis;

    return hh + ":" + mm + ":" + ss + '<span class="sw-time-ms">.' + mss + '</span>';
  }

  function formatTime(ms) {
    var totalSec = Math.floor(ms / 1000);
    var hours = Math.floor(totalSec / 3600);
    var mins = Math.floor((totalSec % 3600) / 60);
    var secs = totalSec % 60;
    var millis = ms % 1000;

    var hh = (hours < 10 ? "0" : "") + hours;
    var mm = (mins < 10 ? "0" : "") + mins;
    var ss = (secs < 10 ? "0" : "") + secs;
    var mss = (millis < 100 ? "0" : "") + (millis < 10 ? "0" : "") + millis;

    return hh + ":" + mm + ":" + ss + "." + mss;
  }

  function getElapsedMs() {
    if (!sw.running) return sw.accumulated;
    return sw.accumulated + (Date.now() - sw.startTimestamp);
  }

  function swTick() {
    if (!sw.running) return;
    var elapsed = getElapsedMs();
    elSwDisplay.innerHTML = formatStopwatch(elapsed);
    sw.animFrame = requestAnimationFrame(swTick);
  }

  window.swToggleStopwatch = function() {
    if (sw.running) {
      // Pause
      sw.accumulated += (Date.now() - sw.startTimestamp);
      sw.running = false;
      sw.startTimestamp = null;
      if (sw.animFrame) cancelAnimationFrame(sw.animFrame);
      elSwStartBtn.textContent = "Start";
      elSwStartBtn.className = "sw-btn sw-btn-primary";
      elSwDisplay.innerHTML = formatStopwatch(sw.accumulated);
    } else {
      // Start / Resume
      sw.running = true;
      sw.startTimestamp = Date.now();
      elSwStartBtn.textContent = "Stop";
      elSwStartBtn.className = "sw-btn sw-btn-red";
      swTick();
    }
  };

  window.swLap = function() {
    if (!sw.running && sw.accumulated === 0) return;
    var splitMs = getElapsedMs();
    var lapMs = splitMs - sw.lastLapSplit;
    sw.lastLapSplit = splitMs;
    sw.laps.push({ lapMs: lapMs, splitMs: splitMs });
    renderLaps();
  };

  window.swResetStopwatch = function() {
    sw.running = false;
    sw.accumulated = 0;
    sw.startTimestamp = null;
    sw.lastLapSplit = 0;
    sw.laps = [];
    if (sw.animFrame) cancelAnimationFrame(sw.animFrame);
    elSwStartBtn.textContent = "Start";
    elSwStartBtn.className = "sw-btn sw-btn-primary";
    elSwDisplay.innerHTML = formatStopwatch(0);
    renderLaps();
  };

  function renderLaps() {
    if (sw.laps.length === 0) {
      elSwLapBody.innerHTML = '<tr><td colspan="4" class="sw-lap-empty">Press Lap to record split times</td></tr>';
      elSwLapActions.style.display = "none";
      return;
    }

    // Find fastest and slowest (only if 3+ laps)
    var fastIdx = -1, slowIdx = -1;
    if (sw.laps.length >= 3) {
      var minMs = Infinity, maxMs = -1;
      for (var i = 0; i < sw.laps.length; i++) {
        if (sw.laps[i].lapMs < minMs) { minMs = sw.laps[i].lapMs; fastIdx = i; }
        if (sw.laps[i].lapMs > maxMs) { maxMs = sw.laps[i].lapMs; slowIdx = i; }
      }
    }

    var html = "";
    // Render in reverse (newest first)
    for (var j = sw.laps.length - 1; j >= 0; j--) {
      var lap = sw.laps[j];
      var cls = "";
      var badge = "";
      if (j === fastIdx) {
        cls = ' class="fastest"';
        badge = '<span class="sw-lap-badge sw-lap-badge-fast">Fastest</span>';
      } else if (j === slowIdx) {
        cls = ' class="slowest"';
        badge = '<span class="sw-lap-badge sw-lap-badge-slow">Slowest</span>';
      }
      html += '<tr' + cls + '>';
      html += '<td>' + (j + 1) + badge + '</td>';
      html += '<td>' + formatTime(lap.lapMs) + '</td>';
      html += '<td>' + formatTime(lap.splitMs) + '</td>';
      html += '<td></td>';
      html += '</tr>';
    }
    elSwLapBody.innerHTML = html;
    elSwLapActions.style.display = "flex";
  }

  window.swExportCSV = function() {
    if (sw.laps.length === 0) return;
    var csv = "Lap,Lap Time,Split Time\n";
    for (var i = 0; i < sw.laps.length; i++) {
      csv += (i + 1) + "," + formatTime(sw.laps[i].lapMs) + "," + formatTime(sw.laps[i].splitMs) + "\n";
    }
    var blob = new Blob([csv], { type: "text/csv" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "stopwatch-laps-" + Date.now() + ".csv";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  window.swClearLaps = function() {
    sw.laps = [];
    sw.lastLapSplit = getElapsedMs();
    renderLaps();
  };

  // ==================== COUNTDOWN TIMER ====================
  var cd = {
    running: false,
    totalMs: 0,
    timeLeftMs: 0,
    startTimestamp: null,
    pausedTimeLeft: 0,
    animFrame: null
  };

  var elCdDisplay = document.getElementById("swCountdownDisplay");
  var elCdStartBtn = document.getElementById("swCdStartBtn");
  var elCdProgressFill = document.getElementById("swCdProgressFill");
  var elCdHours = document.getElementById("swCdHours");
  var elCdMinutes = document.getElementById("swCdMinutes");
  var elCdSeconds = document.getElementById("swCdSeconds");
  var elCdRepeat = document.getElementById("swCdRepeat");
  var elCdLabel = document.getElementById("swCdLabel");
  var elCdInputArea = document.getElementById("swCdInputArea");
  var elPresets = document.getElementById("swPresets");

  function getCdTotalMs() {
    var h = parseInt(elCdHours.value) || 0;
    var m = parseInt(elCdMinutes.value) || 0;
    var s = parseInt(elCdSeconds.value) || 0;
    return (h * 3600 + m * 60 + s) * 1000;
  }

  function formatCountdown(ms) {
    if (ms <= 0) return "00:00:00";
    var totalSec = Math.ceil(ms / 1000);
    var hours = Math.floor(totalSec / 3600);
    var mins = Math.floor((totalSec % 3600) / 60);
    var secs = totalSec % 60;

    var hh = (hours < 10 ? "0" : "") + hours;
    var mm = (mins < 10 ? "0" : "") + mins;
    var ss = (secs < 10 ? "0" : "") + secs;

    return hh + ":" + mm + ":" + ss;
  }

  function updateCdDisplay() {
    elCdDisplay.textContent = formatCountdown(cd.timeLeftMs);
    var pct = cd.totalMs > 0 ? (cd.timeLeftMs / cd.totalMs) * 100 : 0;
    elCdProgressFill.style.width = Math.max(0, pct) + "%";

    if (cd.timeLeftMs <= 0 && cd.totalMs > 0) {
      elCdProgressFill.style.background = "var(--sw-red)";
    } else {
      elCdProgressFill.style.background = "var(--sw-primary)";
    }
  }

  function cdTick() {
    if (!cd.running) return;
    var elapsed = Date.now() - cd.startTimestamp;
    cd.timeLeftMs = Math.max(0, cd.pausedTimeLeft - elapsed);

    updateCdDisplay();

    if (cd.timeLeftMs <= 0) {
      cd.running = false;
      playAlarm();
      elCdLabel.textContent = "Time is up";
      elCdStartBtn.textContent = "Start";
      elCdStartBtn.className = "sw-btn sw-btn-primary";

      // Repeat check
      if (elCdRepeat.checked && cd.totalMs > 0) {
        setTimeout(function() {
          cd.timeLeftMs = cd.totalMs;
          cd.pausedTimeLeft = cd.totalMs;
          cd.startTimestamp = Date.now();
          cd.running = true;
          elCdLabel.textContent = "Countdown Timer";
          elCdStartBtn.textContent = "Pause";
          elCdStartBtn.className = "sw-btn sw-btn-red";
          cdTick();
        }, 1000);
      }
      return;
    }

    cd.animFrame = requestAnimationFrame(cdTick);
  }

  window.swToggleCountdown = function() {
    if (cd.running) {
      // Pause
      cd.running = false;
      var elapsed = Date.now() - cd.startTimestamp;
      cd.timeLeftMs = Math.max(0, cd.pausedTimeLeft - elapsed);
      cd.pausedTimeLeft = cd.timeLeftMs;
      cd.startTimestamp = null;
      if (cd.animFrame) cancelAnimationFrame(cd.animFrame);
      elCdStartBtn.textContent = "Start";
      elCdStartBtn.className = "sw-btn sw-btn-primary";
      updateCdDisplay();
    } else {
      // Start
      if (cd.timeLeftMs <= 0 || cd.totalMs === 0) {
        cd.totalMs = getCdTotalMs();
        cd.timeLeftMs = cd.totalMs;
        cd.pausedTimeLeft = cd.totalMs;
      }
      if (cd.totalMs <= 0) return;
      cd.running = true;
      cd.startTimestamp = Date.now();
      cd.pausedTimeLeft = cd.timeLeftMs;
      elCdStartBtn.textContent = "Pause";
      elCdStartBtn.className = "sw-btn sw-btn-red";
      elCdLabel.textContent = "Countdown Timer";
      cdTick();
    }
  };

  window.swResetCountdown = function() {
    cd.running = false;
    if (cd.animFrame) cancelAnimationFrame(cd.animFrame);
    cd.totalMs = getCdTotalMs();
    cd.timeLeftMs = cd.totalMs;
    cd.pausedTimeLeft = cd.totalMs;
    cd.startTimestamp = null;
    elCdStartBtn.textContent = "Start";
    elCdStartBtn.className = "sw-btn sw-btn-primary";
    elCdLabel.textContent = "Countdown Timer";
    updateCdDisplay();
  };

  window.swSetPreset = function(h, m, s) {
    elCdHours.value = h;
    elCdMinutes.value = m;
    elCdSeconds.value = s;

    // Highlight active preset
    var btns = elPresets.querySelectorAll(".sw-preset-btn");
    var target = h * 3600 + m * 60 + s;
    for (var i = 0; i < btns.length; i++) {
      btns[i].classList.remove("active");
    }
    // Find matching button
    var presetVals = [[0,1,0],[0,5,0],[0,10,0],[0,15,0],[0,30,0],[1,0,0]];
    for (var j = 0; j < presetVals.length; j++) {
      var pv = presetVals[j];
      if (pv[0] === h && pv[1] === m && pv[2] === s) {
        btns[j].classList.add("active");
      }
    }

    if (!cd.running) {
      cd.totalMs = target * 1000;
      cd.timeLeftMs = cd.totalMs;
      cd.pausedTimeLeft = cd.totalMs;
      updateCdDisplay();
    }
  };

  // Update display when inputs change
  function onCdInputChange() {
    if (!cd.running) {
      cd.totalMs = getCdTotalMs();
      cd.timeLeftMs = cd.totalMs;
      cd.pausedTimeLeft = cd.totalMs;
      updateCdDisplay();
    }
  }

  elCdHours.addEventListener("change", onCdInputChange);
  elCdMinutes.addEventListener("change", onCdInputChange);
  elCdSeconds.addEventListener("change", onCdInputChange);
  elCdHours.addEventListener("input", onCdInputChange);
  elCdMinutes.addEventListener("input", onCdInputChange);
  elCdSeconds.addEventListener("input", onCdInputChange);

  // ==================== FULLSCREEN ====================
  window.swToggleFullscreen = function() {
    var wrapper = document.getElementById("swWrapper");
    wrapper.classList.toggle("fullscreen");
    var exitBtn = document.getElementById("swExitFs");
    exitBtn.style.display = wrapper.classList.contains("fullscreen") ? "block" : "none";
  };

  // ==================== KEYBOARD SHORTCUTS ====================
  document.addEventListener("keydown", function(e) {
    var tag = e.target.tagName.toLowerCase();
    if (tag === "input" || tag === "textarea" || tag === "select") return;

    if (e.code === "Space" || e.key === " ") {
      e.preventDefault();
      if (currentTab === "stopwatch") {
        swToggleStopwatch();
      } else {
        swToggleCountdown();
      }
    } else if (e.key === "l" || e.key === "L") {
      if (currentTab === "stopwatch") {
        e.preventDefault();
        swLap();
      }
    } else if (e.key === "r" || e.key === "R") {
      e.preventDefault();
      if (currentTab === "stopwatch") {
        swResetStopwatch();
      } else {
        swResetCountdown();
      }
    }
  });

  // ==================== INIT ====================
  updateCdDisplay();

})();
</script>
