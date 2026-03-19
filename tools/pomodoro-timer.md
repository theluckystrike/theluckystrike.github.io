---
layout: page
title: "Free Pomodoro Timer — Focus Timer with Break Tracking | Zovo"
description: "Stay focused with the Pomodoro technique. Customizable work and break intervals, session tracking, notification sounds, and productivity stats. Free online Pomodoro timer."
permalink: /tools/pomodoro-timer/
keywords: "pomodoro timer, pomodoro technique, focus timer, study timer, productivity timer, work timer, 25 minute timer, pomodoro clock"
date: 2026-03-19
categories: [tools]
tags: [pomodoro, timer, productivity, focus, study, time-management]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --pm-primary: #6C5CE7;
    --pm-primary-dark: #5A4BD1;
    --pm-primary-light: #A29BFE;
    --pm-bg: #0a0a0f;
    --pm-surface: #12121a;
    --pm-surface-alt: #181824;
    --pm-border: #1e1e2e;
    --pm-text: #e0e0e0;
    --pm-text-muted: #8888aa;
    --pm-green: #00ff88;
    --pm-green-dark: #00cc6a;
    --pm-red: #ff4466;
    --pm-yellow: #ffaa00;
    --pm-radius: 12px;
    --pm-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
    --pm-focus: #6C5CE7;
    --pm-break: #00ff88;
  }

  .pm-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--pm-text);
    max-width: 900px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .pm-wrapper * {
    box-sizing: border-box;
  }

  .pm-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .pm-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--pm-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .pm-hero h1 span {
    color: var(--pm-primary);
  }

  .pm-intro {
    font-size: 1.05rem;
    color: var(--pm-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .pm-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--pm-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--pm-border);
    border-radius: 20px;
  }

  /* Mode Tabs */
  .pm-modes {
    display: flex;
    gap: 0;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid var(--pm-border);
    margin-bottom: 24px;
  }

  .pm-mode-btn {
    flex: 1;
    padding: 12px 16px;
    background: var(--pm-bg);
    border: none;
    color: var(--pm-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    text-align: center;
    border-right: 1px solid var(--pm-border);
  }

  .pm-mode-btn:last-child {
    border-right: none;
  }

  .pm-mode-btn.active-focus {
    background: var(--pm-focus);
    color: #fff;
  }

  .pm-mode-btn.active-break {
    background: var(--pm-green-dark);
    color: #fff;
  }

  .pm-mode-btn:not(.active-focus):not(.active-break):hover {
    background: var(--pm-surface-alt);
    color: var(--pm-text);
  }

  /* Timer Area */
  .pm-timer-area {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 24px;
  }

  .pm-timer-svg {
    position: relative;
    width: 320px;
    height: 320px;
  }

  .pm-timer-svg svg {
    width: 100%;
    height: 100%;
    transform: rotate(-90deg);
  }

  .pm-ring-bg {
    fill: none;
    stroke: var(--pm-border);
    stroke-width: 8;
  }

  .pm-ring-progress {
    fill: none;
    stroke: var(--pm-focus);
    stroke-width: 8;
    stroke-linecap: round;
    transition: stroke-dashoffset 0.5s linear, stroke 0.3s ease;
  }

  .pm-timer-display {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
  }

  .pm-time {
    font-family: 'JetBrains Mono', monospace;
    font-size: 3.6rem;
    font-weight: 600;
    color: var(--pm-text);
    letter-spacing: 0.02em;
    line-height: 1;
  }

  .pm-mode-label {
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--pm-text-muted);
    margin-top: 8px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  .pm-session-dots {
    display: flex;
    gap: 8px;
    margin-top: 16px;
    justify-content: center;
  }

  .pm-dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--pm-border);
    transition: background 0.3s ease;
  }

  .pm-dot.completed {
    background: var(--pm-focus);
  }

  .pm-dot.current {
    background: var(--pm-focus);
    box-shadow: 0 0 8px rgba(108, 92, 231, 0.5);
  }

  .pm-session-label {
    font-size: 0.78rem;
    color: var(--pm-text-muted);
    margin-top: 8px;
    font-weight: 500;
  }

  /* Controls */
  .pm-controls {
    display: flex;
    gap: 12px;
    justify-content: center;
    margin-bottom: 24px;
  }

  .pm-btn {
    padding: 10px 24px;
    border: 1px solid var(--pm-border);
    border-radius: 8px;
    background: var(--pm-surface);
    color: var(--pm-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .pm-btn:hover {
    background: var(--pm-surface-alt);
    border-color: var(--pm-primary-light);
  }

  .pm-btn-primary {
    background: var(--pm-primary);
    border-color: var(--pm-primary);
    color: #fff;
  }

  .pm-btn-primary:hover {
    background: var(--pm-primary-dark);
    border-color: var(--pm-primary-dark);
  }

  .pm-btn-sm {
    padding: 6px 14px;
    font-size: 0.8rem;
  }

  /* Settings */
  .pm-card {
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: var(--pm-radius);
    padding: 24px;
    box-shadow: var(--pm-shadow);
    margin-bottom: 24px;
  }

  .pm-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--pm-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .pm-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--pm-primary);
    border-radius: 2px;
  }

  .pm-settings-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  .pm-field label {
    display: block;
    font-size: 0.78rem;
    font-weight: 500;
    color: var(--pm-text-muted);
    margin-bottom: 6px;
  }

  .pm-input {
    width: 100%;
    padding: 8px 12px;
    background: var(--pm-bg);
    border: 1px solid var(--pm-border);
    border-radius: 6px;
    color: var(--pm-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    outline: none;
    text-align: center;
    transition: border-color 0.2s;
  }

  .pm-input:focus {
    border-color: var(--pm-primary);
  }

  /* Stats Bar */
  .pm-stats-bar {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
    margin-bottom: 24px;
  }

  .pm-stat {
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: 8px;
    padding: 10px 12px;
    text-align: center;
  }

  .pm-stat-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.3rem;
    font-weight: 600;
    color: var(--pm-green);
    display: block;
  }

  .pm-stat-label {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--pm-text-muted);
    margin-top: 2px;
    display: block;
  }

  /* Task List */
  .pm-task-input-row {
    display: flex;
    gap: 8px;
    margin-bottom: 12px;
  }

  .pm-task-input {
    flex: 1;
    padding: 8px 12px;
    background: var(--pm-bg);
    border: 1px solid var(--pm-border);
    border-radius: 6px;
    color: var(--pm-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    outline: none;
    transition: border-color 0.2s;
  }

  .pm-task-input:focus {
    border-color: var(--pm-primary);
  }

  .pm-task-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .pm-task-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 12px;
    border: 1px solid var(--pm-border);
    border-radius: 8px;
    margin-bottom: 6px;
    background: var(--pm-bg);
    transition: background 0.2s;
  }

  .pm-task-item.active-task {
    border-color: var(--pm-primary);
    background: rgba(108, 92, 231, 0.08);
  }

  .pm-task-item.done {
    opacity: 0.5;
  }

  .pm-task-item.done .pm-task-name {
    text-decoration: line-through;
  }

  .pm-task-check {
    width: 18px;
    height: 18px;
    border: 2px solid var(--pm-border);
    border-radius: 4px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    transition: all 0.2s;
    background: transparent;
    padding: 0;
  }

  .pm-task-check:hover {
    border-color: var(--pm-primary);
  }

  .pm-task-check.checked {
    background: var(--pm-green);
    border-color: var(--pm-green);
  }

  .pm-task-check.checked::after {
    content: '\2713';
    color: #0a0a0f;
    font-size: 12px;
    font-weight: 700;
  }

  .pm-task-name {
    flex: 1;
    font-size: 0.88rem;
    color: var(--pm-text);
  }

  .pm-task-pomos {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--pm-text-muted);
    white-space: nowrap;
  }

  .pm-task-select {
    padding: 4px 8px;
    font-size: 0.72rem;
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: 4px;
    color: var(--pm-text-muted);
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: all 0.2s;
  }

  .pm-task-select:hover {
    border-color: var(--pm-primary);
    color: var(--pm-text);
  }

  .pm-task-select.selected {
    background: var(--pm-primary);
    border-color: var(--pm-primary);
    color: #fff;
  }

  .pm-task-remove {
    background: none;
    border: none;
    color: var(--pm-text-muted);
    cursor: pointer;
    font-size: 1rem;
    padding: 0 4px;
    line-height: 1;
    transition: color 0.2s;
  }

  .pm-task-remove:hover {
    color: var(--pm-red);
  }

  /* Shortcuts */
  .pm-shortcuts {
    display: flex;
    gap: 16px;
    justify-content: center;
    margin-bottom: 24px;
    flex-wrap: wrap;
  }

  .pm-shortcut {
    font-size: 0.75rem;
    color: var(--pm-text-muted);
  }

  .pm-key {
    display: inline-block;
    padding: 2px 8px;
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--pm-text);
    margin-right: 4px;
  }

  /* Fullscreen */
  .pm-fullscreen-btn {
    position: fixed;
    top: 16px;
    right: 16px;
    z-index: 1000;
    padding: 8px 12px;
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: 8px;
    color: var(--pm-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.78rem;
    cursor: pointer;
    transition: all 0.2s;
    display: none;
  }

  .pm-fullscreen-btn:hover {
    border-color: var(--pm-primary);
    color: var(--pm-text);
  }

  .pm-wrapper.fullscreen {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    max-width: 100%;
    background: var(--pm-bg);
    z-index: 999;
    overflow-y: auto;
    padding: 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .pm-wrapper.fullscreen .pm-fullscreen-btn {
    display: block;
  }

  .pm-wrapper.fullscreen .pm-hero,
  .pm-wrapper.fullscreen .pm-settings-card,
  .pm-wrapper.fullscreen .pm-tasks-card,
  .pm-wrapper.fullscreen .pm-content,
  .pm-wrapper.fullscreen .pm-faq,
  .pm-wrapper.fullscreen .pm-author-box,
  .pm-wrapper.fullscreen .pm-footer,
  .pm-wrapper.fullscreen .pm-related,
  .pm-wrapper.fullscreen .pm-updated-signal {
    display: none;
  }

  .pm-wrapper.fullscreen .pm-timer-svg {
    width: 400px;
    height: 400px;
  }

  .pm-wrapper.fullscreen .pm-time {
    font-size: 5rem;
  }

  /* SEO Content */
  .pm-content {
    margin-top: 16px;
    margin-bottom: 24px;
  }

  .pm-content h2 {
    font-size: 1.35rem;
    font-weight: 700;
    color: var(--pm-text);
    margin: 32px 0 12px;
    line-height: 1.3;
  }

  .pm-content p {
    font-size: 0.95rem;
    color: var(--pm-text-muted);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .pm-content ul, .pm-content ol {
    margin: 0 0 14px;
    padding-left: 24px;
  }

  .pm-content li {
    font-size: 0.95rem;
    color: var(--pm-text-muted);
    line-height: 1.75;
    margin-bottom: 4px;
  }

  /* FAQ */
  .pm-faq {
    margin-bottom: 24px;
  }

  .pm-faq h2 {
    font-size: 1.35rem;
    font-weight: 700;
    color: var(--pm-text);
    margin: 0 0 20px;
  }

  .pm-faq-item {
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin-bottom: 8px;
  }

  .pm-faq-item h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--pm-text);
    margin: 0 0 8px;
  }

  .pm-faq-item p {
    font-size: 0.88rem;
    color: var(--pm-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Author Box */
  .pm-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px;
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: var(--pm-radius);
    margin-bottom: 16px;
  }

  .pm-author-avatar {
    width: 52px;
    height: 52px;
    border-radius: 50%;
    background: var(--pm-primary);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    flex-shrink: 0;
  }

  .pm-author-info p {
    margin: 0;
  }

  .pm-author-name {
    font-weight: 600;
    font-size: 0.95rem;
    color: var(--pm-text);
  }

  .pm-author-bio {
    font-size: 0.82rem;
    color: var(--pm-text-muted);
    line-height: 1.6;
    margin-top: 4px;
  }

  /* Related */
  .pm-related {
    margin-bottom: 16px;
  }

  .pm-related h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--pm-text);
    margin: 0 0 12px;
  }

  .pm-related-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
  }

  .pm-related-link {
    display: block;
    padding: 12px 16px;
    background: var(--pm-surface);
    border: 1px solid var(--pm-border);
    border-radius: 8px;
    color: var(--pm-text);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 500;
    transition: border-color 0.2s;
  }

  .pm-related-link:hover {
    border-color: var(--pm-primary);
  }

  .pm-related-link span {
    display: block;
    font-size: 0.75rem;
    color: var(--pm-text-muted);
    font-weight: 400;
    margin-top: 4px;
  }

  .pm-footer {
    text-align: center;
    padding: 24px 0;
    font-size: 0.78rem;
    color: var(--pm-text-muted);
  }

  .pm-footer a {
    color: var(--pm-primary);
    text-decoration: none;
  }

  .pm-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .pm-hero h1 {
      font-size: 1.6rem;
    }

    .pm-timer-svg {
      width: 260px;
      height: 260px;
    }

    .pm-time {
      font-size: 2.8rem;
    }

    .pm-settings-grid {
      grid-template-columns: 1fr;
    }

    .pm-stats-bar {
      grid-template-columns: 1fr;
    }

    .pm-modes {
      flex-wrap: wrap;
    }

    .pm-mode-btn {
      flex: 1 1 30%;
      font-size: 0.78rem;
      padding: 10px 8px;
    }

    .pm-controls {
      flex-wrap: wrap;
    }

    .pm-related-grid {
      grid-template-columns: 1fr;
    }

    .pm-author-box {
      flex-direction: column;
      text-align: center;
    }

    .pm-wrapper.fullscreen .pm-timer-svg {
      width: 280px;
      height: 280px;
    }

    .pm-wrapper.fullscreen .pm-time {
      font-size: 3.2rem;
    }
  }
</style>

<div class="pm-wrapper" id="pmWrapper">
  <button type="button" class="pm-fullscreen-btn" id="pmExitFs" onclick="pmToggleFullscreen()">Exit Fullscreen</button>

  <div class="pm-hero">
    <h1><span>Pomodoro</span> Timer</h1>
    <p class="pm-intro">Work in focused intervals with built-in breaks. Customize your durations, track sessions, and associate tasks with each pomodoro. Everything runs in your browser and your stats persist between visits.</p>
    <span class="pm-updated">Last updated: March 2026</span>
  </div>

  <!-- Mode Selector -->
  <div class="pm-modes">
    <button type="button" class="pm-mode-btn active-focus" id="pmModeWork" onclick="pmSetMode('work')">Focus</button>
    <button type="button" class="pm-mode-btn" id="pmModeShort" onclick="pmSetMode('short')">Short Break</button>
    <button type="button" class="pm-mode-btn" id="pmModeLong" onclick="pmSetMode('long')">Long Break</button>
  </div>

  <!-- Timer -->
  <div class="pm-timer-area">
    <div class="pm-timer-svg">
      <svg viewBox="0 0 320 320">
        <circle class="pm-ring-bg" cx="160" cy="160" r="140"></circle>
        <circle class="pm-ring-progress" id="pmRing" cx="160" cy="160" r="140" stroke-dasharray="879.65" stroke-dashoffset="0"></circle>
      </svg>
      <div class="pm-timer-display">
        <div class="pm-time" id="pmTime">25:00</div>
        <div class="pm-mode-label" id="pmModeLabel">Focus</div>
      </div>
    </div>

    <div class="pm-session-dots" id="pmDots">
      <div class="pm-dot current" id="pmDot1"></div>
      <div class="pm-dot" id="pmDot2"></div>
      <div class="pm-dot" id="pmDot3"></div>
      <div class="pm-dot" id="pmDot4"></div>
    </div>
    <div class="pm-session-label" id="pmSessionLabel">Session 1 of 4</div>
  </div>

  <!-- Controls -->
  <div class="pm-controls">
    <button type="button" class="pm-btn pm-btn-primary" id="pmStartBtn" onclick="pmToggle()">Start</button>
    <button type="button" class="pm-btn" onclick="pmReset()">Reset</button>
    <button type="button" class="pm-btn" onclick="pmSkip()">Skip</button>
    <button type="button" class="pm-btn" onclick="pmToggleFullscreen()">Fullscreen</button>
  </div>

  <!-- Keyboard Shortcuts -->
  <div class="pm-shortcuts">
    <span class="pm-shortcut"><span class="pm-key">Space</span> Start / Pause</span>
    <span class="pm-shortcut"><span class="pm-key">R</span> Reset</span>
    <span class="pm-shortcut"><span class="pm-key">S</span> Skip</span>
  </div>

  <!-- Daily Stats -->
  <div class="pm-stats-bar">
    <div class="pm-stat">
      <span class="pm-stat-value" id="pmTotalFocus">0m</span>
      <span class="pm-stat-label">Focus Time</span>
    </div>
    <div class="pm-stat">
      <span class="pm-stat-value" id="pmTotalSessions">0</span>
      <span class="pm-stat-label">Sessions</span>
    </div>
    <div class="pm-stat">
      <span class="pm-stat-value" id="pmTotalBreaks">0</span>
      <span class="pm-stat-label">Breaks</span>
    </div>
  </div>

  <!-- Settings -->
  <div class="pm-card pm-settings-card">
    <div class="pm-card-title">Timer Settings</div>
    <div class="pm-settings-grid">
      <div class="pm-field">
        <label for="pmFocusDur">Focus (minutes)</label>
        <input type="number" class="pm-input" id="pmFocusDur" value="25" min="1" max="120">
      </div>
      <div class="pm-field">
        <label for="pmShortDur">Short Break (minutes)</label>
        <input type="number" class="pm-input" id="pmShortDur" value="5" min="1" max="60">
      </div>
      <div class="pm-field">
        <label for="pmLongDur">Long Break (minutes)</label>
        <input type="number" class="pm-input" id="pmLongDur" value="15" min="1" max="60">
      </div>
    </div>
  </div>

  <!-- Task List -->
  <div class="pm-card pm-tasks-card">
    <div class="pm-card-title">Task List</div>
    <div class="pm-task-input-row">
      <input type="text" class="pm-task-input" id="pmTaskInput" placeholder="Add a task..." onkeydown="if(event.key==='Enter')pmAddTask()">
      <button type="button" class="pm-btn pm-btn-primary pm-btn-sm" onclick="pmAddTask()">Add</button>
    </div>
    <ul class="pm-task-list" id="pmTaskList"></ul>
  </div>

  <!-- SEO Content -->
  <div class="pm-content">

<h2>What Is the Pomodoro Technique</h2>

<p>The Pomodoro Technique is a time management method developed by Francesco Cirillo in the late 1980s. The name comes from the tomato-shaped kitchen timer Cirillo used as a university student. The core idea is simple: break work into intervals, traditionally 25 minutes long, separated by short breaks. Each interval is called a pomodoro.</p>

<p>The standard cycle works as follows. You work for 25 minutes with full focus on a single task. When the timer rings, you take a 5-minute short break. After completing four pomodoros, you take a longer break of 15 to 30 minutes. Then the cycle repeats. The rhythm of focused work followed by deliberate rest is what makes the technique effective.</p>

<p>The method addresses two problems that most people face when trying to be productive. First, it combats procrastination by reducing the perceived size of a task. Committing to 25 minutes feels manageable even when the overall project feels overwhelming. Second, it prevents burnout by enforcing regular breaks. Working without breaks leads to diminishing returns -- your concentration degrades over time, and the quality of your output drops even if you do not notice it happening.</p>

<h2>How to Use This Timer</h2>

<p>Set your preferred durations for focus, short break, and long break in the settings panel. The defaults are 25/5/15, which is the classic Pomodoro configuration. If you are new to the technique, start with those values and adjust later based on how your sessions feel.</p>

<p>Add your tasks to the task list before you begin. Select a task to associate it with the current pomodoro. As you complete focus sessions, the pomodoro count next to each task updates so you can see how much time you have invested in each item. Mark tasks as done by clicking the checkbox.</p>

<p>Press Start or hit the spacebar to begin the timer. The circular progress ring fills as time passes. When the interval ends, a notification sound plays and the timer automatically advances to the next phase in the cycle: Focus, Short Break, Focus, Short Break, Focus, Short Break, Focus, Long Break. You can also manually switch modes or skip ahead at any time.</p>

<p>Your daily statistics -- total focus time, sessions completed, and breaks taken -- persist in your browser's localStorage. They reset at midnight each day. No data leaves your device.</p>

<h2>Benefits of Timed Work Sessions</h2>

<p>Research on focused work intervals supports several advantages. A 2017 study published in the journal Cognition found that brief diversions from a task can dramatically improve focus during longer periods of sustained attention. The Pomodoro Technique structures those diversions deliberately rather than leaving them to chance.</p>

<p>Timeboxing also reduces the scope of decisions. Instead of asking "how long should I work on this," you decide before the timer starts and the question is settled. Decision fatigue is a real phenomenon. Eliminating unnecessary choices preserves cognitive energy for the actual work.</p>

<p>The session counter provides a concrete measure of effort. Tracking how many pomodoros a project requires gives you better estimates for future planning. Over weeks of use, patterns emerge: you learn that writing a report takes about 6 pomodoros, or that debugging a feature averages 3. This kind of calibration is difficult to develop without a consistent unit of measurement.</p>

<p>Breaks serve a neurological purpose. The default mode network in your brain activates during rest periods and plays a role in consolidating information and making creative connections. Working through a problem without interruption can lead to tunnel vision. Stepping away, even for five minutes, allows your brain to process the material from a different angle.</p>

<h2>Customizing Your Pomodoro Intervals</h2>

<p>The 25-minute default is a starting point, not a rule. Some people find that 25 minutes is too short for deep technical work like programming or writing. If you consistently feel like you are just hitting your stride when the timer goes off, try 45 or 50-minute focus intervals with 10-minute breaks.</p>

<p>Others find 25 minutes too long when the work requires high cognitive load. Studying dense material like organic chemistry or learning a new language can be mentally taxing. Shorter 15 or 20-minute intervals with more frequent breaks may work better for those situations.</p>

<p>The long break after four sessions matters more than most people realize. Skipping it leads to accumulated fatigue that compounds throughout the day. If you complete 8 pomodoros without a proper long break, your afternoon sessions will be measurably less productive than your morning ones. Protect the long break.</p>

<p>Experiment with ratios. Some practitioners use a 52/17 pattern (52 minutes of work, 17 minutes of break), which a 2014 productivity study by DeskTime found correlated with high output among their user base. Others prefer 90-minute blocks aligned with the body's ultradian rhythm cycle. The timer above supports any duration you want to test.</p>

<ul>
  <li>Classic: 25 min focus / 5 min short / 15 min long</li>
  <li>Extended: 50 min focus / 10 min short / 30 min long</li>
  <li>Short burst: 15 min focus / 3 min short / 10 min long</li>
  <li>DeskTime: 52 min focus / 17 min short / 30 min long</li>
</ul>

  </div>

  <!-- FAQ Section -->
  <div class="pm-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="pm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why 25 minutes specifically?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Francesco Cirillo settled on 25 minutes through experimentation during his university studies. He found it long enough to make meaningful progress on a task but short enough to maintain consistent focus. Research on sustained attention generally supports intervals in the 20-to-50-minute range, though individual variation is significant. The timer above lets you set any duration that works for you.</p>
      </div>
    </div>

    <div class="pm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What should I do during breaks?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Step away from your screen. Stand up, stretch, get water, look out a window, or take a short walk. Avoid checking email, social media, or starting another cognitively demanding activity. The purpose of the break is to let your brain rest and reset. If you spend your break consuming more information, you undermine the recovery that makes the next focus session effective.</p>
      </div>
    </div>

    <div class="pm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does the timer keep running if I switch tabs?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The timer uses Date.now() timestamps to calculate elapsed time rather than relying on setInterval accuracy. This means the timer stays accurate even if the browser throttles JavaScript in background tabs. When you return to the tab, the display will show the correct remaining time.</p>
      </div>
    </div>

    <div class="pm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Are my stats saved between sessions?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Daily statistics (total focus time, completed sessions, and breaks taken) are stored in your browser's localStorage. They persist across page reloads and browser restarts. The stats reset automatically at the start of each new calendar day. No data is sent to any server. Clearing your browser data will remove the stored stats.</p>
      </div>
    </div>

    <div class="pm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use the Pomodoro Technique for studying?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The technique works well for studying. The spaced intervals align with research on effective learning: concentrated study followed by rest allows for memory consolidation. Many students use shorter intervals (15-20 minutes) for memorization tasks and longer intervals (30-45 minutes) for reading or problem sets. The task list lets you plan which subjects to cover in each session.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="pm-author-box">
    <div class="pm-author-avatar">ML</div>
    <div class="pm-author-info">
      <p class="pm-author-name">Michael Lip</p>
      <p class="pm-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <div class="pm-updated-signal" style="text-align:center;margin-bottom:16px;font-size:0.75rem;color:var(--pm-text-muted);">Last updated: March 2026</div>

  <!-- Cross-links -->
  <div class="pm-related">
    <h3>Related Tools</h3>
    <div class="pm-related-grid">
      <a href="/tools/stopwatch/" class="pm-related-link">Stopwatch and Timer <span>Lap times, countdown, alarms</span></a>
      <a href="/tools/word-counter/" class="pm-related-link">Word Counter <span>Words, characters, readability</span></a>
      <a href="/tools/gpa-calculator/" class="pm-related-link">GPA Calculator <span>Semester, cumulative, target</span></a>
    </div>
  </div>

  <footer class="pm-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Pomodoro Timer",
      "description": "Stay focused with the Pomodoro technique. Customizable work and break intervals, session tracking, notification sounds, and productivity stats.",
      "url": "https://theluckystrike.github.io/tools/pomodoro-timer/",
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
        {"@type": "ListItem", "position": 3, "name": "Pomodoro Timer", "item": "https://theluckystrike.github.io/tools/pomodoro-timer/"}
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
          "name": "Why 25 minutes specifically?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Francesco Cirillo settled on 25 minutes through experimentation. Research on sustained attention supports intervals in the 20-to-50-minute range. The timer lets you set any duration."
          }
        },
        {
          "@type": "Question",
          "name": "What should I do during breaks?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Step away from your screen. Stand up, stretch, get water, or take a short walk. Avoid checking email or social media. The break is meant to let your brain rest and reset."
          }
        },
        {
          "@type": "Question",
          "name": "Does the timer keep running if I switch tabs?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. The timer uses Date.now() timestamps to calculate elapsed time, so it stays accurate even if the browser throttles background tabs."
          }
        },
        {
          "@type": "Question",
          "name": "Are my stats saved between sessions?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Daily statistics are stored in localStorage. They persist across page reloads and reset at the start of each new calendar day. No data is sent to any server."
          }
        },
        {
          "@type": "Question",
          "name": "Can I use the Pomodoro Technique for studying?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The technique works well for studying. Spaced intervals align with research on effective learning. Many students use shorter intervals for memorization and longer ones for reading."
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

  // --- Config ---
  var CIRCUMFERENCE = 2 * Math.PI * 140; // ~879.65

  // --- State ---
  var state = {
    mode: "work",        // "work", "short", "long"
    running: false,
    timeLeft: 25 * 60,   // seconds
    totalTime: 25 * 60,
    session: 1,          // 1-4
    cycleStep: 0,        // 0-7: work,short,work,short,work,short,work,long
    startTimestamp: null,
    pausedTimeLeft: null,
    animFrame: null
  };

  // Cycle: work, short, work, short, work, short, work, long
  var CYCLE = ["work","short","work","short","work","short","work","long"];

  // --- DOM ---
  var elTime = document.getElementById("pmTime");
  var elRing = document.getElementById("pmRing");
  var elModeLabel = document.getElementById("pmModeLabel");
  var elStartBtn = document.getElementById("pmStartBtn");
  var elSessionLabel = document.getElementById("pmSessionLabel");
  var elTotalFocus = document.getElementById("pmTotalFocus");
  var elTotalSessions = document.getElementById("pmTotalSessions");
  var elTotalBreaks = document.getElementById("pmTotalBreaks");
  var elFocusDur = document.getElementById("pmFocusDur");
  var elShortDur = document.getElementById("pmShortDur");
  var elLongDur = document.getElementById("pmLongDur");
  var elTaskInput = document.getElementById("pmTaskInput");
  var elTaskList = document.getElementById("pmTaskList");
  var elWrapper = document.getElementById("pmWrapper");

  // --- Audio (Web Audio API) ---
  var audioCtx = null;

  function playNotification() {
    try {
      if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      // Play a pleasant two-tone chime
      var now = audioCtx.currentTime;
      for (var i = 0; i < 3; i++) {
        var osc = audioCtx.createOscillator();
        var gain = audioCtx.createGain();
        osc.connect(gain);
        gain.connect(audioCtx.destination);
        osc.type = "sine";
        osc.frequency.value = i === 1 ? 880 : 660;
        gain.gain.setValueAtTime(0.3, now + i * 0.25);
        gain.gain.exponentialRampToValueAtTime(0.001, now + i * 0.25 + 0.4);
        osc.start(now + i * 0.25);
        osc.stop(now + i * 0.25 + 0.4);
      }
    } catch(e) {}
  }

  // --- Duration helpers ---
  function getDuration(mode) {
    if (mode === "work") return (parseInt(elFocusDur.value) || 25) * 60;
    if (mode === "short") return (parseInt(elShortDur.value) || 5) * 60;
    return (parseInt(elLongDur.value) || 15) * 60;
  }

  function getModeLabel(mode) {
    if (mode === "work") return "Focus";
    if (mode === "short") return "Short Break";
    return "Long Break";
  }

  function getSessionFromCycleStep(step) {
    // Steps 0,2,4,6 are work sessions 1,2,3,4
    var workSteps = [0, 2, 4, 6];
    var idx = workSteps.indexOf(step);
    return idx >= 0 ? idx + 1 : state.session;
  }

  // --- Display ---
  function formatTime(secs) {
    var m = Math.floor(secs / 60);
    var s = secs % 60;
    return (m < 10 ? "0" : "") + m + ":" + (s < 10 ? "0" : "") + s;
  }

  function updateDisplay() {
    elTime.textContent = formatTime(Math.max(0, Math.ceil(state.timeLeft)));

    // Progress ring
    var fraction = state.totalTime > 0 ? state.timeLeft / state.totalTime : 1;
    var offset = CIRCUMFERENCE * fraction;
    elRing.style.strokeDashoffset = CIRCUMFERENCE - offset;

    // Ring color
    var isBreak = state.mode === "short" || state.mode === "long";
    elRing.style.stroke = isBreak ? "var(--pm-break)" : "var(--pm-focus)";

    // Mode label
    elModeLabel.textContent = getModeLabel(state.mode);

    // Session dots
    for (var i = 1; i <= 4; i++) {
      var dot = document.getElementById("pmDot" + i);
      dot.className = "pm-dot";
      if (i < state.session) dot.classList.add("completed");
      if (i === state.session && state.mode === "work") dot.classList.add("current");
      if (i <= state.session && state.mode !== "work" && i < state.session) dot.classList.add("completed");
    }

    elSessionLabel.textContent = "Session " + state.session + " of 4";

    // Start button text
    elStartBtn.textContent = state.running ? "Pause" : "Start";

    // Mode tabs
    var modeWork = document.getElementById("pmModeWork");
    var modeShort = document.getElementById("pmModeShort");
    var modeLong = document.getElementById("pmModeLong");
    modeWork.className = "pm-mode-btn" + (state.mode === "work" ? " active-focus" : "");
    modeShort.className = "pm-mode-btn" + (state.mode === "short" ? " active-break" : "");
    modeLong.className = "pm-mode-btn" + (state.mode === "long" ? " active-break" : "");

    // Page title
    document.title = formatTime(Math.max(0, Math.ceil(state.timeLeft))) + " - " + getModeLabel(state.mode) + " | Pomodoro Timer";
  }

  // --- localStorage stats ---
  function getTodayKey() {
    var d = new Date();
    return "pm_stats_" + d.getFullYear() + "-" + (d.getMonth()+1) + "-" + d.getDate();
  }

  function getStats() {
    try {
      var data = JSON.parse(localStorage.getItem(getTodayKey()));
      if (data) return data;
    } catch(e) {}
    return { focusSeconds: 0, sessions: 0, breaks: 0 };
  }

  function saveStats(stats) {
    try {
      localStorage.setItem(getTodayKey(), JSON.stringify(stats));
    } catch(e) {}
  }

  function updateStatsDisplay() {
    var stats = getStats();
    var mins = Math.floor(stats.focusSeconds / 60);
    if (mins >= 60) {
      var h = Math.floor(mins / 60);
      var m = mins % 60;
      elTotalFocus.textContent = h + "h " + m + "m";
    } else {
      elTotalFocus.textContent = mins + "m";
    }
    elTotalSessions.textContent = stats.sessions;
    elTotalBreaks.textContent = stats.breaks;
  }

  function addFocusTime(seconds) {
    var stats = getStats();
    stats.focusSeconds += seconds;
    saveStats(stats);
    updateStatsDisplay();
  }

  function addSession() {
    var stats = getStats();
    stats.sessions++;
    saveStats(stats);
    updateStatsDisplay();
  }

  function addBreak() {
    var stats = getStats();
    stats.breaks++;
    saveStats(stats);
    updateStatsDisplay();
  }

  // --- Task List ---
  var tasks = [];
  var activeTaskId = null;
  var taskIdCounter = 0;

  function renderTasks() {
    var html = "";
    for (var i = 0; i < tasks.length; i++) {
      var t = tasks[i];
      var isActive = t.id === activeTaskId;
      var isDone = t.done;
      html += '<li class="pm-task-item' + (isActive ? ' active-task' : '') + (isDone ? ' done' : '') + '">';
      html += '<button type="button" class="pm-task-check' + (isDone ? ' checked' : '') + '" onclick="pmToggleTask(' + t.id + ')"></button>';
      html += '<span class="pm-task-name">' + escapeHtml(t.name) + '</span>';
      html += '<span class="pm-task-pomos">' + t.pomos + ' pomo' + (t.pomos !== 1 ? 's' : '') + '</span>';
      if (!isDone) {
        html += '<button type="button" class="pm-task-select' + (isActive ? ' selected' : '') + '" onclick="pmSelectTask(' + t.id + ')">' + (isActive ? 'Active' : 'Select') + '</button>';
      }
      html += '<button type="button" class="pm-task-remove" onclick="pmRemoveTask(' + t.id + ')">&times;</button>';
      html += '</li>';
    }
    elTaskList.innerHTML = html;
  }

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.textContent = str;
    return div.innerHTML;
  }

  window.pmAddTask = function() {
    var name = elTaskInput.value.trim();
    if (!name) return;
    taskIdCounter++;
    tasks.push({ id: taskIdCounter, name: name, pomos: 0, done: false });
    elTaskInput.value = "";
    renderTasks();
  };

  window.pmToggleTask = function(id) {
    for (var i = 0; i < tasks.length; i++) {
      if (tasks[i].id === id) {
        tasks[i].done = !tasks[i].done;
        if (tasks[i].done && activeTaskId === id) activeTaskId = null;
        break;
      }
    }
    renderTasks();
  };

  window.pmSelectTask = function(id) {
    activeTaskId = (activeTaskId === id) ? null : id;
    renderTasks();
  };

  window.pmRemoveTask = function(id) {
    tasks = tasks.filter(function(t) { return t.id !== id; });
    if (activeTaskId === id) activeTaskId = null;
    renderTasks();
  };

  function addPomoToActiveTask() {
    if (activeTaskId === null) return;
    for (var i = 0; i < tasks.length; i++) {
      if (tasks[i].id === activeTaskId) {
        tasks[i].pomos++;
        break;
      }
    }
    renderTasks();
  }

  // --- Timer logic ---
  function tick() {
    if (!state.running) return;

    var now = Date.now();
    var elapsed = (now - state.startTimestamp) / 1000;
    state.timeLeft = state.pausedTimeLeft - elapsed;

    if (state.timeLeft <= 0) {
      state.timeLeft = 0;
      updateDisplay();
      onTimerComplete();
      return;
    }

    updateDisplay();
    state.animFrame = requestAnimationFrame(tick);
  }

  function onTimerComplete() {
    state.running = false;
    playNotification();

    var completedMode = CYCLE[state.cycleStep];

    if (completedMode === "work") {
      var dur = getDuration("work");
      addFocusTime(dur);
      addSession();
      addPomoToActiveTask();
    } else {
      addBreak();
    }

    // Advance cycle
    state.cycleStep = (state.cycleStep + 1) % 8;
    var nextMode = CYCLE[state.cycleStep];
    state.mode = nextMode;
    state.session = getSessionFromCycleStep(state.cycleStep);
    state.totalTime = getDuration(nextMode);
    state.timeLeft = state.totalTime;
    state.pausedTimeLeft = state.totalTime;
    state.startTimestamp = null;

    updateDisplay();

    // Auto-start after a brief pause
    setTimeout(function() {
      pmStart();
    }, 1500);
  }

  function pmStart() {
    if (state.running) return;
    // Resume audio context if suspended
    if (audioCtx && audioCtx.state === "suspended") {
      audioCtx.resume();
    }
    state.running = true;
    state.pausedTimeLeft = state.timeLeft;
    state.startTimestamp = Date.now();
    elStartBtn.textContent = "Pause";
    tick();
  }

  function pmPause() {
    if (!state.running) return;
    state.running = false;
    if (state.animFrame) cancelAnimationFrame(state.animFrame);
    var now = Date.now();
    var elapsed = (now - state.startTimestamp) / 1000;
    state.timeLeft = Math.max(0, state.pausedTimeLeft - elapsed);
    state.pausedTimeLeft = state.timeLeft;
    state.startTimestamp = null;
    elStartBtn.textContent = "Start";
    updateDisplay();
  }

  window.pmToggle = function() {
    if (state.running) {
      pmPause();
    } else {
      pmStart();
    }
  };

  window.pmReset = function() {
    pmPause();
    state.timeLeft = getDuration(state.mode);
    state.totalTime = getDuration(state.mode);
    state.pausedTimeLeft = state.timeLeft;
    updateDisplay();
  };

  window.pmSkip = function() {
    pmPause();

    var skippedMode = CYCLE[state.cycleStep];

    // If skipping a work session, add partial focus time
    if (skippedMode === "work") {
      var dur = getDuration("work");
      var elapsed = dur - state.timeLeft;
      if (elapsed > 0) addFocusTime(Math.round(elapsed));
    }

    state.cycleStep = (state.cycleStep + 1) % 8;
    var nextMode = CYCLE[state.cycleStep];
    state.mode = nextMode;
    state.session = getSessionFromCycleStep(state.cycleStep);
    state.totalTime = getDuration(nextMode);
    state.timeLeft = state.totalTime;
    state.pausedTimeLeft = state.timeLeft;
    updateDisplay();
  };

  window.pmSetMode = function(mode) {
    pmPause();
    state.mode = mode;
    state.totalTime = getDuration(mode);
    state.timeLeft = state.totalTime;
    state.pausedTimeLeft = state.timeLeft;

    // Sync cycle step
    if (mode === "work") {
      // Find current work step
      var workSteps = [0, 2, 4, 6];
      state.cycleStep = workSteps[state.session - 1] || 0;
    } else if (mode === "short") {
      var shortSteps = [1, 3, 5];
      state.cycleStep = shortSteps[Math.min(state.session - 1, 2)] || 1;
    } else {
      state.cycleStep = 7;
    }
    updateDisplay();
  };

  // --- Fullscreen ---
  window.pmToggleFullscreen = function() {
    elWrapper.classList.toggle("fullscreen");
    var exitBtn = document.getElementById("pmExitFs");
    exitBtn.style.display = elWrapper.classList.contains("fullscreen") ? "block" : "none";
  };

  // --- Settings change ---
  function onSettingsChange() {
    if (!state.running) {
      state.totalTime = getDuration(state.mode);
      state.timeLeft = state.totalTime;
      state.pausedTimeLeft = state.timeLeft;
      updateDisplay();
    }
  }

  elFocusDur.addEventListener("change", onSettingsChange);
  elShortDur.addEventListener("change", onSettingsChange);
  elLongDur.addEventListener("change", onSettingsChange);

  // --- Keyboard shortcuts ---
  document.addEventListener("keydown", function(e) {
    // Do not trigger if user is typing in an input
    var tag = e.target.tagName.toLowerCase();
    if (tag === "input" || tag === "textarea" || tag === "select") return;

    if (e.code === "Space" || e.key === " ") {
      e.preventDefault();
      pmToggle();
    } else if (e.key === "r" || e.key === "R") {
      e.preventDefault();
      pmReset();
    } else if (e.key === "s" || e.key === "S") {
      e.preventDefault();
      pmSkip();
    }
  });

  // --- Init ---
  updateDisplay();
  updateStatsDisplay();

})();
</script>
