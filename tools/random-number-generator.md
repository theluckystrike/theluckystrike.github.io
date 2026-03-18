---
layout: page
title: "Free Random Number Generator — Dice, Lists, Coins & Custom Ranges | Zovo"
description: "Generate random numbers, roll dice, flip coins, pick from lists, and create random sequences. Cryptographically secure random number generator with history and bulk generation."
permalink: /tools/random-number-generator/
keywords: "random number generator, rng, random number, dice roller, coin flip, random picker, number randomizer, random sequence generator"
date: 2026-03-19
categories: [tools]
tags: [random-number, rng, dice, coin-flip, generator, probability]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">

<style>
  :root {
    --rng-bg: #0a0a0f;
    --rng-surface: #12121a;
    --rng-surface-2: #1a1a28;
    --rng-border: #1e1e2e;
    --rng-border-light: #2a2a3e;
    --rng-primary: #6C5CE7;
    --rng-primary-dark: #5A4BD1;
    --rng-primary-glow: rgba(108, 92, 231, 0.3);
    --rng-secondary: #00ff88;
    --rng-secondary-dark: #00cc6a;
    --rng-text: #e0e0e0;
    --rng-text-muted: #8888aa;
    --rng-text-dim: #555577;
    --rng-error: #ff4466;
    --rng-radius: 12px;
    --rng-radius-sm: 8px;
  }

  .rng-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--rng-text);
    max-width: 960px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .rng-wrapper * {
    box-sizing: border-box;
  }

  .rng-wrapper input, .rng-wrapper select, .rng-wrapper textarea, .rng-wrapper button {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  }

  /* Hero */
  .rng-hero {
    text-align: center;
    padding: 36px 0 24px;
  }

  .rng-hero h1 {
    font-size: 2rem;
    font-weight: 700;
    color: var(--rng-text);
    margin: 0 0 14px;
    line-height: 1.2;
  }

  .rng-hero h1 span {
    color: var(--rng-primary);
  }

  .rng-intro {
    font-size: 1rem;
    color: var(--rng-text-muted);
    max-width: 680px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Tab bar */
  .rng-tabs {
    display: flex;
    gap: 4px;
    background: var(--rng-surface);
    border: 1px solid var(--rng-border);
    border-radius: var(--rng-radius);
    padding: 4px;
    margin-bottom: 20px;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
  }

  .rng-tab {
    flex: 1;
    min-width: 0;
    padding: 10px 12px;
    border: none;
    border-radius: var(--rng-radius-sm);
    background: transparent;
    color: var(--rng-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s ease;
    white-space: nowrap;
    text-align: center;
  }

  .rng-tab:hover {
    color: var(--rng-text);
    background: var(--rng-surface-2);
  }

  .rng-tab.active {
    background: var(--rng-primary);
    color: #fff;
    font-weight: 600;
  }

  .rng-tab-icon {
    display: block;
    font-size: 1.1rem;
    margin-bottom: 2px;
  }

  /* Panel container */
  .rng-panel {
    display: none;
    background: var(--rng-surface);
    border: 1px solid var(--rng-border);
    border-radius: var(--rng-radius);
    padding: 24px;
    margin-bottom: 20px;
  }

  .rng-panel.active {
    display: block;
  }

  /* Form controls */
  .rng-row {
    display: flex;
    gap: 12px;
    align-items: flex-end;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }

  .rng-field {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .rng-field label {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--rng-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .rng-input {
    padding: 9px 12px;
    border: 1px solid var(--rng-border-light);
    border-radius: var(--rng-radius-sm);
    background: var(--rng-bg);
    color: var(--rng-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.15s ease;
    width: 100%;
  }

  .rng-input:focus {
    border-color: var(--rng-primary);
    box-shadow: 0 0 0 3px var(--rng-primary-glow);
  }

  .rng-input-sm {
    width: 100px;
  }

  .rng-select {
    padding: 9px 12px;
    border: 1px solid var(--rng-border-light);
    border-radius: var(--rng-radius-sm);
    background: var(--rng-bg);
    color: var(--rng-text);
    font-size: 0.85rem;
    outline: none;
    cursor: pointer;
    transition: border-color 0.15s ease;
  }

  .rng-select:focus {
    border-color: var(--rng-primary);
  }

  .rng-textarea {
    width: 100%;
    min-height: 140px;
    padding: 12px;
    border: 1px solid var(--rng-border-light);
    border-radius: var(--rng-radius-sm);
    background: var(--rng-bg);
    color: var(--rng-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    line-height: 1.5;
    resize: vertical;
    outline: none;
    transition: border-color 0.15s ease;
  }

  .rng-textarea:focus {
    border-color: var(--rng-primary);
    box-shadow: 0 0 0 3px var(--rng-primary-glow);
  }

  .rng-checkbox-row {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 0;
  }

  .rng-checkbox-row input[type="checkbox"] {
    accent-color: var(--rng-primary);
    width: 16px;
    height: 16px;
    cursor: pointer;
  }

  .rng-checkbox-row label {
    font-size: 0.85rem;
    color: var(--rng-text-muted);
    cursor: pointer;
  }

  /* Buttons */
  .rng-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: var(--rng-radius-sm);
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
    white-space: nowrap;
  }

  .rng-btn-primary {
    background: var(--rng-primary);
    color: #fff;
  }

  .rng-btn-primary:hover {
    background: var(--rng-primary-dark);
    box-shadow: 0 4px 16px var(--rng-primary-glow);
  }

  .rng-btn-primary:active {
    transform: scale(0.97);
  }

  .rng-btn-secondary {
    background: var(--rng-surface-2);
    color: var(--rng-text);
    border: 1px solid var(--rng-border-light);
  }

  .rng-btn-secondary:hover {
    background: var(--rng-border);
    border-color: var(--rng-border-light);
  }

  .rng-btn-green {
    background: var(--rng-secondary);
    color: #0a0a0f;
    font-weight: 700;
  }

  .rng-btn-green:hover {
    background: var(--rng-secondary-dark);
    box-shadow: 0 4px 16px rgba(0, 255, 136, 0.2);
  }

  .rng-btn-green:active {
    transform: scale(0.97);
  }

  .rng-btn-sm {
    padding: 6px 12px;
    font-size: 0.8rem;
  }

  .rng-btn-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }

  /* Result area */
  .rng-result {
    background: var(--rng-bg);
    border: 1px solid var(--rng-border);
    border-radius: var(--rng-radius-sm);
    padding: 16px;
    min-height: 60px;
    margin-bottom: 12px;
    position: relative;
  }

  .rng-result-empty {
    color: var(--rng-text-dim);
    font-size: 0.85rem;
    text-align: center;
    padding: 20px 0;
  }

  .rng-chips {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .rng-chip {
    display: inline-flex;
    align-items: center;
    padding: 5px 12px;
    background: var(--rng-surface-2);
    border: 1px solid var(--rng-border-light);
    border-radius: 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--rng-secondary);
    font-weight: 500;
    animation: rngChipIn 0.3s ease;
  }

  @keyframes rngChipIn {
    from { opacity: 0; transform: scale(0.8); }
    to { opacity: 1; transform: scale(1); }
  }

  /* Big number display */
  .rng-big-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 3rem;
    font-weight: 700;
    color: var(--rng-secondary);
    text-align: center;
    padding: 16px 0;
    line-height: 1;
  }

  /* Dice visuals */
  .rng-dice-area {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    padding: 20px 0;
    min-height: 100px;
  }

  .rng-die {
    width: 64px;
    height: 64px;
    background: var(--rng-surface-2);
    border: 2px solid var(--rng-border-light);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--rng-secondary);
    position: relative;
    transition: all 0.3s ease;
  }

  .rng-die.rolling {
    animation: rngDieRoll 0.4s ease;
    border-color: var(--rng-primary);
    box-shadow: 0 0 16px var(--rng-primary-glow);
  }

  @keyframes rngDieRoll {
    0% { transform: rotateX(0deg) rotateZ(0deg); }
    25% { transform: rotateX(90deg) rotateZ(90deg); }
    50% { transform: rotateX(180deg) rotateZ(0deg); }
    75% { transform: rotateX(270deg) rotateZ(-90deg); }
    100% { transform: rotateX(360deg) rotateZ(0deg); }
  }

  .rng-die-label {
    position: absolute;
    bottom: -18px;
    font-size: 0.65rem;
    color: var(--rng-text-dim);
    font-weight: 500;
  }

  .rng-dice-total {
    text-align: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.1rem;
    color: var(--rng-text-muted);
    padding: 8px 0;
  }

  .rng-dice-total strong {
    color: var(--rng-secondary);
    font-size: 1.4rem;
  }

  /* Coin */
  .rng-coin-area {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 0;
  }

  .rng-coin {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 2.2rem;
    font-weight: 700;
    cursor: pointer;
    position: relative;
    transition: all 0.3s ease;
    border: 4px solid;
    perspective: 200px;
  }

  .rng-coin-heads {
    background: linear-gradient(135deg, #ffd700, #ffb300);
    color: #5a4000;
    border-color: #cc9900;
    box-shadow: 0 4px 20px rgba(255, 215, 0, 0.3), inset 0 2px 4px rgba(255, 255, 255, 0.3);
  }

  .rng-coin-tails {
    background: linear-gradient(135deg, #c0c0c0, #999999);
    color: #333;
    border-color: #888;
    box-shadow: 0 4px 20px rgba(192, 192, 192, 0.3), inset 0 2px 4px rgba(255, 255, 255, 0.3);
  }

  .rng-coin-idle {
    background: linear-gradient(135deg, var(--rng-surface-2), var(--rng-border));
    color: var(--rng-text-muted);
    border-color: var(--rng-border-light);
  }

  .rng-coin.flipping {
    animation: rngCoinFlip 0.6s ease;
  }

  @keyframes rngCoinFlip {
    0% { transform: rotateY(0deg) scale(1); }
    25% { transform: rotateY(450deg) scale(1.1); }
    50% { transform: rotateY(900deg) scale(1); }
    75% { transform: rotateY(1260deg) scale(1.05); }
    100% { transform: rotateY(1440deg) scale(1); }
  }

  .rng-coin-stats {
    display: flex;
    gap: 24px;
    margin-top: 16px;
    font-size: 0.9rem;
  }

  .rng-coin-stat {
    text-align: center;
  }

  .rng-coin-stat-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.4rem;
    font-weight: 700;
  }

  .rng-coin-stat-label {
    font-size: 0.75rem;
    color: var(--rng-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .rng-streak {
    margin-top: 10px;
    font-size: 0.82rem;
    color: var(--rng-text-muted);
  }

  .rng-streak strong {
    color: var(--rng-primary);
  }

  /* History */
  .rng-history-section {
    background: var(--rng-surface);
    border: 1px solid var(--rng-border);
    border-radius: var(--rng-radius);
    padding: 20px;
    margin-bottom: 20px;
  }

  .rng-history-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
  }

  .rng-history-title {
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--rng-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .rng-history-list {
    max-height: 200px;
    overflow-y: auto;
    scrollbar-width: thin;
    scrollbar-color: var(--rng-border-light) transparent;
  }

  .rng-history-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 8px 12px;
    border-radius: 6px;
    font-size: 0.82rem;
    transition: background 0.1s ease;
  }

  .rng-history-item:hover {
    background: var(--rng-surface-2);
  }

  .rng-history-item-type {
    color: var(--rng-primary);
    font-weight: 600;
    min-width: 80px;
  }

  .rng-history-item-value {
    font-family: 'JetBrains Mono', monospace;
    color: var(--rng-secondary);
    flex: 1;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-left: 12px;
  }

  .rng-history-item-time {
    color: var(--rng-text-dim);
    font-size: 0.75rem;
    margin-left: 12px;
    white-space: nowrap;
  }

  .rng-history-empty {
    color: var(--rng-text-dim);
    font-size: 0.82rem;
    text-align: center;
    padding: 12px 0;
  }

  /* Stats panel */
  .rng-stats-panel {
    background: var(--rng-surface);
    border: 1px solid var(--rng-border);
    border-radius: var(--rng-radius);
    padding: 20px;
    margin-bottom: 20px;
  }

  .rng-stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 16px;
    margin-bottom: 16px;
  }

  .rng-stat-card {
    text-align: center;
    padding: 12px;
    background: var(--rng-bg);
    border-radius: var(--rng-radius-sm);
    border: 1px solid var(--rng-border);
  }

  .rng-stat-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--rng-primary);
  }

  .rng-stat-label {
    font-size: 0.7rem;
    color: var(--rng-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-top: 4px;
  }

  /* Distribution chart */
  .rng-chart {
    height: 100px;
    display: flex;
    align-items: flex-end;
    gap: 2px;
    padding: 8px 0;
  }

  .rng-chart-bar {
    flex: 1;
    background: var(--rng-primary);
    border-radius: 3px 3px 0 0;
    min-height: 2px;
    transition: height 0.3s ease;
    position: relative;
  }

  .rng-chart-bar:hover {
    background: var(--rng-secondary);
  }

  .rng-chart-bar-label {
    position: absolute;
    bottom: -18px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 0.6rem;
    color: var(--rng-text-dim);
    white-space: nowrap;
  }

  /* Seed display */
  .rng-seed {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 12px;
    background: var(--rng-bg);
    border-radius: 6px;
    font-size: 0.75rem;
    color: var(--rng-text-dim);
    margin-top: 8px;
  }

  .rng-seed-badge {
    background: var(--rng-primary);
    color: #fff;
    font-size: 0.65rem;
    font-weight: 600;
    padding: 2px 6px;
    border-radius: 4px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .rng-seed-value {
    font-family: 'JetBrains Mono', monospace;
    color: var(--rng-text-muted);
    overflow: hidden;
    text-overflow: ellipsis;
  }

  /* Export */
  .rng-export-row {
    display: flex;
    gap: 8px;
    justify-content: flex-end;
    margin-top: 8px;
  }

  /* Content section */
  .rng-content {
    max-width: 780px;
    margin: 40px auto;
    line-height: 1.8;
    color: var(--rng-text-muted);
    font-size: 0.95rem;
  }

  .rng-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--rng-text);
    margin: 36px 0 14px;
    line-height: 1.3;
  }

  .rng-content h2:first-child {
    margin-top: 0;
  }

  .rng-content p {
    margin: 0 0 16px;
  }

  .rng-content ul, .rng-content ol {
    margin: 0 0 16px;
    padding-left: 24px;
  }

  .rng-content li {
    margin-bottom: 6px;
  }

  /* FAQ */
  .rng-faq {
    max-width: 780px;
    margin: 0 auto 60px;
  }

  .rng-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 20px;
    text-align: center;
    color: var(--rng-text);
  }

  .rng-faq-item {
    border: 1px solid var(--rng-border);
    border-radius: var(--rng-radius);
    padding: 18px 22px;
    margin-bottom: 10px;
    background: var(--rng-surface);
  }

  .rng-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--rng-text);
  }

  .rng-faq-item p {
    margin: 0;
    font-size: 0.9rem;
    color: var(--rng-text-muted);
    line-height: 1.7;
  }

  /* Footer */
  .rng-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--rng-text-dim);
    font-size: 0.85rem;
    border-top: 1px solid var(--rng-border);
    margin-top: 3rem;
  }

  .rng-footer a {
    color: var(--rng-primary);
    text-decoration: none;
  }

  /* Meta bar */
  .rng-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 0;
    font-size: 0.78rem;
    color: var(--rng-text-dim);
    border-top: 1px solid var(--rng-border);
    margin-bottom: 24px;
  }

  /* List result items */
  .rng-list-item {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 6px 0;
    border-bottom: 1px solid var(--rng-border);
    font-size: 0.9rem;
  }

  .rng-list-item:last-child {
    border-bottom: none;
  }

  .rng-list-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--rng-text-dim);
    min-width: 24px;
  }

  .rng-list-val {
    color: var(--rng-text);
  }

  /* PIN/Password display */
  .rng-pin-display {
    font-family: 'JetBrains Mono', monospace;
    font-size: 2rem;
    font-weight: 700;
    text-align: center;
    padding: 20px;
    color: var(--rng-secondary);
    letter-spacing: 0.15em;
    word-break: break-all;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .rng-hero h1 {
      font-size: 1.5rem;
    }

    .rng-tabs {
      gap: 2px;
      padding: 3px;
    }

    .rng-tab {
      padding: 8px 6px;
      font-size: 0.72rem;
    }

    .rng-tab-icon {
      font-size: 1rem;
    }

    .rng-panel {
      padding: 16px;
    }

    .rng-row {
      flex-direction: column;
      align-items: stretch;
    }

    .rng-input-sm {
      width: 100%;
    }

    .rng-die {
      width: 52px;
      height: 52px;
      font-size: 1.2rem;
    }

    .rng-coin {
      width: 100px;
      height: 100px;
      font-size: 1.8rem;
    }

    .rng-big-number {
      font-size: 2.2rem;
    }

    .rng-stats-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .rng-btn-row {
      flex-direction: column;
    }

    .rng-history-item {
      font-size: 0.75rem;
    }
  }

  @media (max-width: 480px) {
    .rng-tabs {
      flex-wrap: nowrap;
    }

    .rng-tab {
      padding: 7px 4px;
      font-size: 0.68rem;
    }

    .rng-coin-stats {
      gap: 16px;
    }
  }
</style>

<div class="rng-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Random Number Generator">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="rng-hero">
    <h1><span>Random Number</span> Generator</h1>
    <p class="rng-intro">Generate cryptographically secure random numbers, roll dice, flip coins, shuffle lists, and create PINs. Everything runs in your browser using <code style="background:var(--rng-surface-2);padding:2px 6px;border-radius:4px;font-size:0.85em;">crypto.getRandomValues()</code> for true randomness. Nothing is sent to a server.</p>
  </div>

  <!-- Tabs -->
  <div class="rng-tabs" role="tablist">
    <button class="rng-tab active" onclick="rngSwitchTab('numbers')" role="tab" aria-selected="true">
      <span class="rng-tab-icon">&#x1f522;</span>Numbers
    </button>
    <button class="rng-tab" onclick="rngSwitchTab('dice')" role="tab" aria-selected="false">
      <span class="rng-tab-icon">&#x1f3b2;</span>Dice
    </button>
    <button class="rng-tab" onclick="rngSwitchTab('coin')" role="tab" aria-selected="false">
      <span class="rng-tab-icon">&#x1fa99;</span>Coin
    </button>
    <button class="rng-tab" onclick="rngSwitchTab('list')" role="tab" aria-selected="false">
      <span class="rng-tab-icon">&#x1f500;</span>List
    </button>
    <button class="rng-tab" onclick="rngSwitchTab('pin')" role="tab" aria-selected="false">
      <span class="rng-tab-icon">&#x1f510;</span>PIN
    </button>
  </div>

  <!-- Panel 1: Number Generator -->
  <div id="rngPanelNumbers" class="rng-panel active">
    <div class="rng-row">
      <div class="rng-field">
        <label for="rngMin">Min</label>
        <input type="number" id="rngMin" class="rng-input rng-input-sm" value="1">
      </div>
      <div class="rng-field">
        <label for="rngMax">Max</label>
        <input type="number" id="rngMax" class="rng-input rng-input-sm" value="100">
      </div>
      <div class="rng-field">
        <label for="rngQty">Quantity</label>
        <input type="number" id="rngQty" class="rng-input rng-input-sm" value="1" min="1" max="1000">
      </div>
      <div class="rng-field" style="align-self:flex-end;">
        <button class="rng-btn rng-btn-green" onclick="rngGenerate()">Generate</button>
      </div>
    </div>
    <div class="rng-row" style="margin-bottom:8px;">
      <div class="rng-checkbox-row">
        <input type="checkbox" id="rngDupes" checked>
        <label for="rngDupes">Allow duplicates</label>
      </div>
      <div class="rng-checkbox-row" style="margin-left:16px;">
        <input type="checkbox" id="rngSort">
        <label for="rngSort">Sort results</label>
      </div>
    </div>
    <div id="rngNumberResult" class="rng-result">
      <div class="rng-result-empty">Results appear here after generating</div>
    </div>
    <div class="rng-export-row">
      <button class="rng-btn rng-btn-secondary rng-btn-sm" onclick="rngCopyNumbers()">Copy All</button>
      <button class="rng-btn rng-btn-secondary rng-btn-sm" onclick="rngExportCSV('numbers')">Export CSV</button>
    </div>
    <div id="rngNumberSeed" class="rng-seed" style="display:none;">
      <span class="rng-seed-badge">Crypto</span>
      <span class="rng-seed-value" id="rngNumberSeedVal"></span>
    </div>
  </div>

  <!-- Panel 2: Dice Roller -->
  <div id="rngPanelDice" class="rng-panel">
    <div class="rng-row">
      <div class="rng-field">
        <label for="rngDiceCount">Dice</label>
        <input type="number" id="rngDiceCount" class="rng-input rng-input-sm" value="2" min="1" max="10">
      </div>
      <div class="rng-field">
        <label for="rngDiceType">Type</label>
        <select id="rngDiceType" class="rng-select">
          <option value="4">d4</option>
          <option value="6" selected>d6</option>
          <option value="8">d8</option>
          <option value="10">d10</option>
          <option value="12">d12</option>
          <option value="20">d20</option>
          <option value="100">d100</option>
        </select>
      </div>
      <div class="rng-field">
        <label for="rngDiceMod">Modifier</label>
        <input type="number" id="rngDiceMod" class="rng-input rng-input-sm" value="0" placeholder="+/- N">
      </div>
      <div class="rng-field" style="align-self:flex-end;">
        <button class="rng-btn rng-btn-green" onclick="rngRollDice()">Roll</button>
      </div>
    </div>
    <div id="rngDiceArea" class="rng-dice-area">
      <div style="color:var(--rng-text-dim);font-size:0.85rem;">Click Roll to throw the dice</div>
    </div>
    <div id="rngDiceTotal" class="rng-dice-total" style="display:none;"></div>
    <div id="rngDiceSeed" class="rng-seed" style="display:none;">
      <span class="rng-seed-badge">Crypto</span>
      <span class="rng-seed-value" id="rngDiceSeedVal"></span>
    </div>
  </div>

  <!-- Panel 3: Coin Flipper -->
  <div id="rngPanelCoin" class="rng-panel">
    <div class="rng-coin-area">
      <div id="rngCoin" class="rng-coin rng-coin-idle" onclick="rngFlipCoin()" title="Click to flip">?</div>
      <div id="rngCoinStats" class="rng-coin-stats" style="display:none;">
        <div class="rng-coin-stat">
          <div class="rng-coin-stat-value" id="rngHeadsCount" style="color:#ffd700;">0</div>
          <div class="rng-coin-stat-label">Heads (<span id="rngHeadsPct">0</span>%)</div>
        </div>
        <div class="rng-coin-stat">
          <div class="rng-coin-stat-value" id="rngFlipTotal" style="color:var(--rng-primary);">0</div>
          <div class="rng-coin-stat-label">Total Flips</div>
        </div>
        <div class="rng-coin-stat">
          <div class="rng-coin-stat-value" id="rngTailsCount" style="color:#c0c0c0;">0</div>
          <div class="rng-coin-stat-label">Tails (<span id="rngTailsPct">0</span>%)</div>
        </div>
      </div>
      <div id="rngStreak" class="rng-streak" style="display:none;"></div>
    </div>
    <div class="rng-btn-row" style="justify-content:center;margin-top:12px;">
      <button class="rng-btn rng-btn-green" onclick="rngFlipCoin()">Flip Once</button>
      <button class="rng-btn rng-btn-secondary" onclick="rngBulkFlip(10)">Flip 10x</button>
      <button class="rng-btn rng-btn-secondary" onclick="rngBulkFlip(100)">Flip 100x</button>
      <button class="rng-btn rng-btn-secondary" onclick="rngBulkFlip(1000)">Flip 1000x</button>
      <button class="rng-btn rng-btn-secondary" onclick="rngResetCoin()">Reset</button>
    </div>
  </div>

  <!-- Panel 4: List Randomizer -->
  <div id="rngPanelList" class="rng-panel">
    <div class="rng-field" style="margin-bottom:12px;">
      <label for="rngListInput">Enter items (one per line)</label>
      <textarea id="rngListInput" class="rng-textarea" placeholder="Apple&#10;Banana&#10;Cherry&#10;Dragonfruit&#10;Elderberry" rows="6"></textarea>
    </div>
    <div class="rng-row">
      <div class="rng-field">
        <label for="rngPickCount">Pick N items</label>
        <input type="number" id="rngPickCount" class="rng-input rng-input-sm" value="0" min="0" placeholder="0 = all">
      </div>
      <div class="rng-field" style="align-self:flex-end;">
        <button class="rng-btn rng-btn-green" onclick="rngShuffleList()">Shuffle</button>
      </div>
      <div class="rng-field" style="align-self:flex-end;">
        <button class="rng-btn rng-btn-primary" onclick="rngPickFromList()">Pick Random</button>
      </div>
    </div>
    <div id="rngListResult" class="rng-result" style="margin-top:12px;">
      <div class="rng-result-empty">Shuffled or picked items appear here</div>
    </div>
    <div class="rng-export-row">
      <button class="rng-btn rng-btn-secondary rng-btn-sm" onclick="rngCopyList()">Copy Result</button>
    </div>
  </div>

  <!-- Panel 5: PIN/Password -->
  <div id="rngPanelPin" class="rng-panel">
    <div class="rng-row">
      <div class="rng-field">
        <label for="rngPinType">Type</label>
        <select id="rngPinType" class="rng-select" onchange="rngPinTypeChange()">
          <option value="pin">Numeric PIN</option>
          <option value="hex">Hex String</option>
          <option value="bytes">Random Bytes</option>
        </select>
      </div>
      <div class="rng-field">
        <label for="rngPinLength" id="rngPinLengthLabel">Length (digits)</label>
        <input type="number" id="rngPinLength" class="rng-input rng-input-sm" value="4" min="1" max="128">
      </div>
      <div class="rng-field" style="align-self:flex-end;">
        <button class="rng-btn rng-btn-green" onclick="rngGeneratePin()">Generate</button>
      </div>
    </div>
    <div id="rngPinResult" class="rng-result" style="margin-top:12px;">
      <div class="rng-result-empty">Generated value appears here</div>
    </div>
    <div class="rng-export-row">
      <button class="rng-btn rng-btn-secondary rng-btn-sm" onclick="rngCopyPin()">Copy</button>
    </div>
  </div>

  <!-- History -->
  <div class="rng-history-section">
    <div class="rng-history-header">
      <span class="rng-history-title">Generation History</span>
      <button class="rng-btn rng-btn-secondary rng-btn-sm" onclick="rngClearHistory()">Clear</button>
    </div>
    <div id="rngHistoryList" class="rng-history-list">
      <div class="rng-history-empty">No history yet. Generate something to get started.</div>
    </div>
  </div>

  <!-- Statistics -->
  <div id="rngStatsPanel" class="rng-stats-panel" style="display:none;">
    <div class="rng-history-header">
      <span class="rng-history-title">Statistics (Number Generator)</span>
      <button class="rng-btn rng-btn-secondary rng-btn-sm" onclick="rngClearStats()">Reset</button>
    </div>
    <div class="rng-stats-grid">
      <div class="rng-stat-card">
        <div class="rng-stat-value" id="rngStatCount">0</div>
        <div class="rng-stat-label">Generated</div>
      </div>
      <div class="rng-stat-card">
        <div class="rng-stat-value" id="rngStatMean">-</div>
        <div class="rng-stat-label">Mean</div>
      </div>
      <div class="rng-stat-card">
        <div class="rng-stat-value" id="rngStatMedian">-</div>
        <div class="rng-stat-label">Median</div>
      </div>
      <div class="rng-stat-card">
        <div class="rng-stat-value" id="rngStatMode">-</div>
        <div class="rng-stat-label">Mode</div>
      </div>
      <div class="rng-stat-card">
        <div class="rng-stat-value" id="rngStatMin">-</div>
        <div class="rng-stat-label">Min</div>
      </div>
      <div class="rng-stat-card">
        <div class="rng-stat-value" id="rngStatMax">-</div>
        <div class="rng-stat-label">Max</div>
      </div>
    </div>
    <div id="rngDistChart" class="rng-chart"></div>
  </div>

  <div class="rng-meta">
    <span>All randomness from crypto.getRandomValues() -- nothing leaves your browser</span>
    <span>Zovo Tools</span>
  </div>

</div>

<!-- Content Section -->
<div class="rng-wrapper">
  <div class="rng-content">

<h2>What Is a Random Number Generator</h2>

<p>A random number generator (RNG) is a tool that produces numbers with no predictable pattern. Each output is independent of the last. The generator on this page uses your browser's built-in cryptographic API, which draws entropy from your operating system's random source, such as hardware interrupts, mouse movements, and timing jitter. The result is a sequence of numbers that cannot be predicted or reproduced, even by someone who knows the algorithm.</p>

<p>RNGs fall into two categories: those that produce a single number within a range and those that produce sequences. This tool handles both. You can generate a single number between 1 and 100 or produce 1,000 unique numbers in any range you choose. The output format is flexible. Results can be copied as plain text or exported to CSV for use in spreadsheets, scripts, or data analysis workflows.</p>

<h2>How Random Numbers Are Generated</h2>

<p>This tool calls <code>crypto.getRandomValues()</code>, a Web Crypto API method available in all modern browsers. The function fills a typed array with cryptographically strong random bytes. To produce a number within a specific range, the tool converts these bytes into an integer and maps it to the requested interval using rejection sampling. Rejection sampling avoids the modulo bias that occurs when you simply take a random integer modulo N. That bias, while small for large ranges, becomes noticeable when the range does not evenly divide the byte space.</p>

<p>For the dice roller and coin flipper, the same underlying function is used. A d6 roll maps to the integers 1 through 6. A coin flip maps to 0 or 1. The list shuffler implements a Fisher-Yates shuffle, where each swap position is chosen using a cryptographically random index. Fisher-Yates produces a uniform distribution over all possible permutations when the random source is unbiased.</p>

<h2>True Random vs Pseudo-Random</h2>

<p>Pseudo-random number generators (PRNGs) like JavaScript's <code>Math.random()</code> use a deterministic algorithm seeded with an initial value. Given the same seed, they produce the same sequence every time. This is fine for games and visual effects but unsuitable for security, lotteries, or any application where predictability is a risk.</p>

<p>Cryptographic random number generators (CSPRNGs) like <code>crypto.getRandomValues()</code> draw from entropy collected by the operating system. On modern hardware, this entropy comes from sources such as CPU instruction timing, interrupt timing, and hardware random number generators built into the processor (Intel's RDRAND, for example). The output passes statistical randomness tests and is considered suitable for generating encryption keys, tokens, and other security-sensitive values.</p>

<p>True random in the physics sense requires measuring quantum events, such as radioactive decay or photon behavior. For practical purposes, a well-implemented CSPRNG is indistinguishable from true random and is what this tool provides.</p>

<h2>Common Uses for Random Number Generators</h2>

<p>Random numbers appear in nearly every field that involves uncertainty or fairness:</p>

<ul>
  <li>Selecting lottery or raffle winners from a participant list</li>
  <li>Assigning participants to control and treatment groups in clinical trials</li>
  <li>Generating test data for software quality assurance</li>
  <li>Choosing random samples from a population for surveys or audits</li>
  <li>Rolling dice in tabletop RPGs like Dungeons and Dragons</li>
  <li>Creating secure PINs, tokens, and session identifiers</li>
  <li>Shuffling playlists, quiz questions, or flashcards</li>
  <li>Monte Carlo simulations in finance, physics, and engineering</li>
  <li>Settling disputes or making decisions when no rational basis exists</li>
</ul>

<p>The coin flipper and list picker cover the simpler cases. The bulk number generator handles scenarios where you need hundreds or thousands of values at once, such as populating a test database or running a simulation.</p>

<h2>Understanding Dice Probability</h2>

<p>A fair die gives each face an equal probability. For a d6, each number from 1 to 6 has a 1/6 chance, roughly 16.67%. When you roll multiple dice and sum the results, the distribution shifts from uniform to roughly bell-shaped. Two d6 dice produce sums from 2 to 12, with 7 being the most likely outcome (6 out of 36 combinations, or 16.67%). The extremes of 2 and 12 each have only one combination (2.78%).</p>

<p>The modifier field adds or subtracts a fixed number from the total. Rolling 2d6+3 produces values from 5 to 15, shifting the entire distribution upward by 3 without changing its shape. This matches the standard notation used in tabletop RPGs.</p>

<p>For a d20, each value from 1 to 20 has a 5% chance. The distribution is perfectly flat. Rolling with advantage (roll two d20, take the higher) increases the average from 10.5 to about 13.8. This tool does not implement advantage/disadvantage directly, but you can roll two d20 and take the result you need.</p>

<h2>Frequently Asked Questions</h2>

  </div>

  <div class="rng-faq" itemscope itemtype="https://schema.org/FAQPage">

    <div class="rng-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is this random number generator truly random?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool uses the Web Crypto API's crypto.getRandomValues() function, which is a cryptographically secure pseudo-random number generator (CSPRNG). It draws entropy from your operating system's random source, including hardware events and timing data. The output is statistically indistinguishable from true randomness and is the same mechanism browsers use for generating encryption keys and secure tokens.</p>
      </div>
    </div>

    <div class="rng-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I generate random numbers without duplicates?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Uncheck the "Allow duplicates" option in the Number Generator tab. The tool will then produce a set of unique numbers within your specified range. Keep in mind that the quantity cannot exceed the size of the range when duplicates are disabled. For example, you cannot generate 50 unique numbers between 1 and 10.</p>
      </div>
    </div>

    <div class="rng-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does this tool send my data to a server?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All processing happens locally in your browser using JavaScript. No network requests are made when you generate numbers, roll dice, flip coins, or shuffle lists. You can verify this by opening your browser's developer tools and monitoring the Network tab. Your generated values and list contents stay on your device.</p>
      </div>
    </div>

    <div class="rng-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What dice types does the dice roller support?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The dice roller supports d4, d6, d8, d10, d12, d20, and d100. You can roll between 1 and 10 dice at once and apply a positive or negative modifier to the total. These cover the standard dice used in tabletop role-playing games, board games, and probability exercises.</p>
      </div>
    </div>

    <div class="rng-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How many random numbers can I generate at once?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The Number Generator tab supports generating up to 1,000 numbers in a single batch. You can set any integer range, including negative numbers. Results can be sorted, copied to clipboard, or exported as a CSV file. For repeated generation, the statistics panel tracks mean, median, mode, and distribution across all your generated values.</p>
      </div>
    </div>

    <div class="rng-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between a PIN and a hex string?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A PIN consists of only decimal digits (0-9), making it suitable for numeric keypads, phone unlock codes, and verification codes. A hex string uses characters 0-9 and a-f, giving 16 possible values per position instead of 10. Hex strings are commonly used for encryption keys, color codes, and memory addresses. The random bytes option produces raw byte values displayed in hexadecimal, useful for generating tokens and cryptographic material.</p>
      </div>
    </div>

  </div>

  <footer class="rng-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>
</div>

<script>
(function() {
  "use strict";

  // --- Crypto random helpers ---

  function cryptoRandInt(min, max) {
    // Inclusive of both min and max
    var range = max - min + 1;
    if (range <= 0) return min;
    if (range === 1) return min;
    // Find the number of bytes needed
    var bitsNeeded = Math.ceil(Math.log2(range));
    var bytesNeeded = Math.ceil(bitsNeeded / 8);
    var mask = Math.pow(2, bitsNeeded) - 1;
    var arr = new Uint8Array(bytesNeeded);
    while (true) {
      crypto.getRandomValues(arr);
      var val = 0;
      for (var i = 0; i < bytesNeeded; i++) {
        val = (val << 8) | arr[i];
      }
      val = val & mask;
      if (val < range) {
        return min + val;
      }
      // Rejection: try again to avoid modulo bias
    }
  }

  function cryptoRandBytes(n) {
    var arr = new Uint8Array(n);
    crypto.getRandomValues(arr);
    return arr;
  }

  function getSeedDisplay() {
    var bytes = cryptoRandBytes(8);
    var hex = "";
    for (var i = 0; i < bytes.length; i++) {
      hex += ("0" + bytes[i].toString(16)).slice(-2);
    }
    return hex;
  }

  // --- State ---

  var history = [];
  var allGeneratedNumbers = [];
  var coinState = { heads: 0, tails: 0, streak: 0, streakType: null, lastResults: [] };
  var lastNumberResults = [];
  var lastListResults = [];
  var lastPinResult = "";

  // --- Tab switching ---

  window.rngSwitchTab = function(tab) {
    var panels = ["numbers", "dice", "coin", "list", "pin"];
    var tabs = document.querySelectorAll(".rng-tab");
    panels.forEach(function(p, i) {
      var el = document.getElementById("rngPanel" + p.charAt(0).toUpperCase() + p.slice(1));
      if (el) {
        el.classList.toggle("active", p === tab);
      }
      if (tabs[i]) {
        tabs[i].classList.toggle("active", p === tab);
        tabs[i].setAttribute("aria-selected", p === tab ? "true" : "false");
      }
    });
  };

  // --- Number Generator ---

  window.rngGenerate = function() {
    var min = parseInt(document.getElementById("rngMin").value, 10);
    var max = parseInt(document.getElementById("rngMax").value, 10);
    var qty = parseInt(document.getElementById("rngQty").value, 10);
    var allowDupes = document.getElementById("rngDupes").checked;
    var sortResults = document.getElementById("rngSort").checked;

    if (isNaN(min) || isNaN(max) || isNaN(qty)) return;
    if (min > max) { var tmp = min; min = max; max = tmp; }
    if (qty < 1) qty = 1;
    if (qty > 1000) qty = 1000;

    var range = max - min + 1;
    if (!allowDupes && qty > range) {
      qty = range;
      document.getElementById("rngQty").value = qty;
    }

    var results = [];
    if (allowDupes) {
      for (var i = 0; i < qty; i++) {
        results.push(cryptoRandInt(min, max));
      }
    } else {
      var pool = {};
      while (results.length < qty) {
        var n = cryptoRandInt(min, max);
        if (!pool[n]) {
          pool[n] = true;
          results.push(n);
        }
      }
    }

    if (sortResults) {
      results.sort(function(a, b) { return a - b; });
    }

    lastNumberResults = results;
    allGeneratedNumbers = allGeneratedNumbers.concat(results);

    // Display chips
    var container = document.getElementById("rngNumberResult");
    var html = '<div class="rng-chips">';
    for (var j = 0; j < results.length; j++) {
      html += '<span class="rng-chip" style="animation-delay:' + (j * 0.02) + 's">' + results[j] + '</span>';
    }
    html += '</div>';
    container.innerHTML = html;

    // Seed
    var seedEl = document.getElementById("rngNumberSeed");
    seedEl.style.display = "flex";
    document.getElementById("rngNumberSeedVal").textContent = "entropy: " + getSeedDisplay();

    addHistory("Number", results.length === 1 ? results[0].toString() : results.slice(0, 5).join(", ") + (results.length > 5 ? " ... (" + results.length + " total)" : ""));
    updateStats();
  };

  window.rngCopyNumbers = function() {
    if (!lastNumberResults.length) return;
    navigator.clipboard.writeText(lastNumberResults.join(", "));
    flashBtn(event.target, "Copied");
  };

  // --- Dice Roller ---

  window.rngRollDice = function() {
    var count = parseInt(document.getElementById("rngDiceCount").value, 10);
    var sides = parseInt(document.getElementById("rngDiceType").value, 10);
    var mod = parseInt(document.getElementById("rngDiceMod").value, 10) || 0;

    if (isNaN(count) || count < 1) count = 1;
    if (count > 10) count = 10;

    var results = [];
    for (var i = 0; i < count; i++) {
      results.push(cryptoRandInt(1, sides));
    }

    var area = document.getElementById("rngDiceArea");
    area.innerHTML = "";

    results.forEach(function(val, idx) {
      var die = document.createElement("div");
      die.className = "rng-die rolling";
      die.textContent = val;

      var label = document.createElement("div");
      label.className = "rng-die-label";
      label.textContent = "d" + sides;
      die.appendChild(label);

      die.style.animationDelay = (idx * 0.08) + "s";
      area.appendChild(die);

      setTimeout(function() {
        die.classList.remove("rolling");
      }, 400 + idx * 80);
    });

    var sum = results.reduce(function(a, b) { return a + b; }, 0);
    var total = sum + mod;

    var totalEl = document.getElementById("rngDiceTotal");
    totalEl.style.display = "block";
    var modStr = mod > 0 ? " + " + mod : (mod < 0 ? " - " + Math.abs(mod) : "");
    totalEl.innerHTML = results.join(" + ") + modStr + " = <strong>" + total + "</strong>";

    // Seed
    var seedEl = document.getElementById("rngDiceSeed");
    seedEl.style.display = "flex";
    document.getElementById("rngDiceSeedVal").textContent = "entropy: " + getSeedDisplay();

    var notation = count + "d" + sides + (mod > 0 ? "+" + mod : (mod < 0 ? mod : ""));
    addHistory("Dice (" + notation + ")", total.toString());
  };

  // --- Coin Flipper ---

  window.rngFlipCoin = function() {
    var coinEl = document.getElementById("rngCoin");
    var result = cryptoRandInt(0, 1);
    var isHeads = result === 0;

    coinEl.className = "rng-coin flipping";

    setTimeout(function() {
      if (isHeads) {
        coinEl.className = "rng-coin rng-coin-heads";
        coinEl.textContent = "H";
        coinState.heads++;
      } else {
        coinEl.className = "rng-coin rng-coin-tails";
        coinEl.textContent = "T";
        coinState.tails++;
      }

      // Streak
      var type = isHeads ? "H" : "T";
      coinState.lastResults.push(type);
      if (type === coinState.streakType) {
        coinState.streak++;
      } else {
        coinState.streakType = type;
        coinState.streak = 1;
      }

      updateCoinDisplay();
    }, 600);

    addHistory("Coin", isHeads ? "Heads" : "Tails");
  };

  window.rngBulkFlip = function(count) {
    for (var i = 0; i < count; i++) {
      var result = cryptoRandInt(0, 1);
      var isHeads = result === 0;
      if (isHeads) {
        coinState.heads++;
      } else {
        coinState.tails++;
      }
      var type = isHeads ? "H" : "T";
      coinState.lastResults.push(type);
      if (type === coinState.streakType) {
        coinState.streak++;
      } else {
        coinState.streakType = type;
        coinState.streak = 1;
      }
    }

    // Show last result on coin
    var coinEl = document.getElementById("rngCoin");
    var lastType = coinState.lastResults[coinState.lastResults.length - 1];
    if (lastType === "H") {
      coinEl.className = "rng-coin rng-coin-heads";
      coinEl.textContent = "H";
    } else {
      coinEl.className = "rng-coin rng-coin-tails";
      coinEl.textContent = "T";
    }

    updateCoinDisplay();
    addHistory("Coin (x" + count + ")", coinState.heads + "H / " + coinState.tails + "T");
  };

  window.rngResetCoin = function() {
    coinState = { heads: 0, tails: 0, streak: 0, streakType: null, lastResults: [] };
    var coinEl = document.getElementById("rngCoin");
    coinEl.className = "rng-coin rng-coin-idle";
    coinEl.textContent = "?";
    document.getElementById("rngCoinStats").style.display = "none";
    document.getElementById("rngStreak").style.display = "none";
  };

  function updateCoinDisplay() {
    var total = coinState.heads + coinState.tails;
    document.getElementById("rngCoinStats").style.display = "flex";
    document.getElementById("rngHeadsCount").textContent = coinState.heads;
    document.getElementById("rngTailsCount").textContent = coinState.tails;
    document.getElementById("rngFlipTotal").textContent = total;
    document.getElementById("rngHeadsPct").textContent = total > 0 ? ((coinState.heads / total) * 100).toFixed(1) : "0";
    document.getElementById("rngTailsPct").textContent = total > 0 ? ((coinState.tails / total) * 100).toFixed(1) : "0";

    // Longest streak
    var longestStreak = 0;
    var longestType = "";
    var currentStreak = 0;
    var currentType = "";
    for (var i = 0; i < coinState.lastResults.length; i++) {
      if (coinState.lastResults[i] === currentType) {
        currentStreak++;
      } else {
        currentType = coinState.lastResults[i];
        currentStreak = 1;
      }
      if (currentStreak > longestStreak) {
        longestStreak = currentStreak;
        longestType = currentType;
      }
    }

    if (longestStreak > 1) {
      var streakEl = document.getElementById("rngStreak");
      streakEl.style.display = "block";
      streakEl.innerHTML = "Longest streak: <strong>" + longestStreak + " " + (longestType === "H" ? "Heads" : "Tails") + "</strong> in a row";
    }
  }

  // --- List Randomizer ---

  window.rngShuffleList = function() {
    var input = document.getElementById("rngListInput").value.trim();
    if (!input) return;
    var items = input.split("\n").filter(function(s) { return s.trim() !== ""; });
    if (items.length === 0) return;

    // Fisher-Yates shuffle with crypto random
    for (var i = items.length - 1; i > 0; i--) {
      var j = cryptoRandInt(0, i);
      var temp = items[i];
      items[i] = items[j];
      items[j] = temp;
    }

    lastListResults = items;
    displayListResult(items);
    addHistory("Shuffle", items.length + " items shuffled");
  };

  window.rngPickFromList = function() {
    var input = document.getElementById("rngListInput").value.trim();
    if (!input) return;
    var items = input.split("\n").filter(function(s) { return s.trim() !== ""; });
    if (items.length === 0) return;

    var count = parseInt(document.getElementById("rngPickCount").value, 10);
    if (isNaN(count) || count < 1) count = 1;
    if (count > items.length) count = items.length;

    // Pick N random unique items
    var pool = items.slice();
    var picked = [];
    for (var i = 0; i < count; i++) {
      var idx = cryptoRandInt(0, pool.length - 1);
      picked.push(pool[idx]);
      pool.splice(idx, 1);
    }

    lastListResults = picked;
    displayListResult(picked);
    addHistory("Pick " + count, picked.join(", ").substring(0, 60));
  };

  function displayListResult(items) {
    var container = document.getElementById("rngListResult");
    var html = "";
    for (var i = 0; i < items.length; i++) {
      html += '<div class="rng-list-item"><span class="rng-list-num">' + (i + 1) + '.</span><span class="rng-list-val">' + escapeHtml(items[i]) + '</span></div>';
    }
    container.innerHTML = html;
  }

  window.rngCopyList = function() {
    if (!lastListResults.length) return;
    navigator.clipboard.writeText(lastListResults.join("\n"));
    flashBtn(event.target, "Copied");
  };

  // --- PIN / Hex / Bytes ---

  window.rngPinTypeChange = function() {
    var type = document.getElementById("rngPinType").value;
    var label = document.getElementById("rngPinLengthLabel");
    var input = document.getElementById("rngPinLength");
    if (type === "pin") {
      label.textContent = "Length (digits)";
      input.value = "4";
      input.max = "8";
    } else if (type === "hex") {
      label.textContent = "Length (chars)";
      input.value = "16";
      input.max = "128";
    } else {
      label.textContent = "Length (bytes)";
      input.value = "16";
      input.max = "128";
    }
  };

  window.rngGeneratePin = function() {
    var type = document.getElementById("rngPinType").value;
    var len = parseInt(document.getElementById("rngPinLength").value, 10);

    if (isNaN(len) || len < 1) len = 1;

    var result = "";
    if (type === "pin") {
      if (len > 8) len = 8;
      for (var i = 0; i < len; i++) {
        result += cryptoRandInt(0, 9).toString();
      }
    } else if (type === "hex") {
      if (len > 128) len = 128;
      var hexBytes = cryptoRandBytes(Math.ceil(len / 2));
      var hexStr = "";
      for (var j = 0; j < hexBytes.length; j++) {
        hexStr += ("0" + hexBytes[j].toString(16)).slice(-2);
      }
      result = hexStr.substring(0, len);
    } else {
      // Random bytes displayed as hex pairs
      if (len > 128) len = 128;
      var bytes = cryptoRandBytes(len);
      var parts = [];
      for (var k = 0; k < bytes.length; k++) {
        parts.push(("0" + bytes[k].toString(16)).slice(-2));
      }
      result = parts.join(" ");
    }

    lastPinResult = result;
    var container = document.getElementById("rngPinResult");
    container.innerHTML = '<div class="rng-pin-display">' + escapeHtml(result) + '</div>';

    var typeLabel = type === "pin" ? "PIN" : (type === "hex" ? "Hex" : "Bytes");
    addHistory(typeLabel, result.substring(0, 40));
  };

  window.rngCopyPin = function() {
    if (!lastPinResult) return;
    navigator.clipboard.writeText(lastPinResult);
    flashBtn(event.target, "Copied");
  };

  // --- History ---

  function addHistory(type, value) {
    var now = new Date();
    var timeStr = now.toLocaleTimeString([], { hour: "2-digit", minute: "2-digit", second: "2-digit" });
    history.unshift({ type: type, value: value, time: timeStr });
    if (history.length > 20) history.pop();
    renderHistory();
  }

  function renderHistory() {
    var container = document.getElementById("rngHistoryList");
    if (history.length === 0) {
      container.innerHTML = '<div class="rng-history-empty">No history yet. Generate something to get started.</div>';
      return;
    }
    var html = "";
    for (var i = 0; i < history.length; i++) {
      var h = history[i];
      html += '<div class="rng-history-item">';
      html += '<span class="rng-history-item-type">' + escapeHtml(h.type) + '</span>';
      html += '<span class="rng-history-item-value">' + escapeHtml(h.value) + '</span>';
      html += '<span class="rng-history-item-time">' + h.time + '</span>';
      html += '</div>';
    }
    container.innerHTML = html;
  }

  window.rngClearHistory = function() {
    history = [];
    renderHistory();
  };

  // --- Statistics ---

  function updateStats() {
    if (allGeneratedNumbers.length === 0) {
      document.getElementById("rngStatsPanel").style.display = "none";
      return;
    }
    document.getElementById("rngStatsPanel").style.display = "block";

    var nums = allGeneratedNumbers;
    var count = nums.length;
    var sum = 0;
    for (var i = 0; i < count; i++) sum += nums[i];
    var mean = sum / count;

    // Median
    var sorted = nums.slice().sort(function(a, b) { return a - b; });
    var median;
    if (count % 2 === 0) {
      median = (sorted[count / 2 - 1] + sorted[count / 2]) / 2;
    } else {
      median = sorted[Math.floor(count / 2)];
    }

    // Mode
    var freq = {};
    var maxFreq = 0;
    var mode = nums[0];
    for (var j = 0; j < count; j++) {
      var n = nums[j];
      freq[n] = (freq[n] || 0) + 1;
      if (freq[n] > maxFreq) {
        maxFreq = freq[n];
        mode = n;
      }
    }

    document.getElementById("rngStatCount").textContent = count;
    document.getElementById("rngStatMean").textContent = mean.toFixed(2);
    document.getElementById("rngStatMedian").textContent = median % 1 === 0 ? median : median.toFixed(2);
    document.getElementById("rngStatMode").textContent = mode;
    document.getElementById("rngStatMin").textContent = sorted[0];
    document.getElementById("rngStatMax").textContent = sorted[count - 1];

    // Distribution chart
    renderDistChart(freq, sorted[0], sorted[count - 1]);
  }

  function renderDistChart(freq, minVal, maxVal) {
    var chart = document.getElementById("rngDistChart");
    var range = maxVal - minVal + 1;

    // If range is too wide, bucket into ~20 bins
    var buckets = [];
    var bucketLabels = [];
    var maxCount = 0;

    if (range <= 30) {
      for (var i = minVal; i <= maxVal; i++) {
        var c = freq[i] || 0;
        buckets.push(c);
        bucketLabels.push(i.toString());
        if (c > maxCount) maxCount = c;
      }
    } else {
      var numBins = 20;
      var binSize = range / numBins;
      for (var b = 0; b < numBins; b++) {
        var lo = Math.floor(minVal + b * binSize);
        var hi = Math.floor(minVal + (b + 1) * binSize) - 1;
        if (b === numBins - 1) hi = maxVal;
        var cnt = 0;
        for (var v = lo; v <= hi; v++) {
          cnt += (freq[v] || 0);
        }
        buckets.push(cnt);
        bucketLabels.push(lo + "-" + hi);
        if (cnt > maxCount) maxCount = cnt;
      }
    }

    if (maxCount === 0) {
      chart.innerHTML = "";
      return;
    }

    var html = "";
    for (var k = 0; k < buckets.length; k++) {
      var pct = (buckets[k] / maxCount) * 100;
      var showLabel = buckets.length <= 20;
      html += '<div class="rng-chart-bar" style="height:' + Math.max(pct, 2) + '%" title="' + bucketLabels[k] + ': ' + buckets[k] + '">';
      if (showLabel && buckets.length <= 15) {
        html += '<span class="rng-chart-bar-label">' + bucketLabels[k] + '</span>';
      }
      html += '</div>';
    }
    chart.innerHTML = html;
  }

  window.rngClearStats = function() {
    allGeneratedNumbers = [];
    document.getElementById("rngStatsPanel").style.display = "none";
  };

  // --- Export ---

  window.rngExportCSV = function(type) {
    var data = "";
    if (type === "numbers" && lastNumberResults.length) {
      data = "value\n" + lastNumberResults.join("\n");
    } else {
      return;
    }
    var blob = new Blob([data], { type: "text/csv" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "random-numbers.csv";
    a.click();
    URL.revokeObjectURL(url);
  };

  // --- Utility ---

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.appendChild(document.createTextNode(str));
    return div.innerHTML;
  }

  function flashBtn(el, msg) {
    var orig = el.textContent;
    el.textContent = msg;
    setTimeout(function() {
      el.textContent = orig;
    }, 1500);
  }

  // --- Keyboard shortcut: Enter to generate in focused panel ---
  document.addEventListener("keydown", function(e) {
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      var active = document.querySelector(".rng-panel.active");
      if (!active) return;
      var id = active.id;
      if (id === "rngPanelNumbers") rngGenerate();
      else if (id === "rngPanelDice") rngRollDice();
      else if (id === "rngPanelCoin") rngFlipCoin();
      else if (id === "rngPanelList") rngShuffleList();
      else if (id === "rngPanelPin") rngGeneratePin();
    }
  });

})();
</script>
