---
layout: page
title: "Free Typing Speed Test — Check Your WPM & Accuracy | Zovo"
description: "Test your typing speed and accuracy with our free online typing test. Measure words per minute (WPM), accuracy percentage, and track your progress. Multiple difficulty levels and text samples."
permalink: /tools/typing-test/
keywords: "typing test, typing speed test, wpm test, typing speed, words per minute, typing practice, typing accuracy, keyboard test"
date: 2026-03-19
categories: [tools]
tags: [typing, speed-test, wpm, keyboard, accuracy, practice]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  body { margin: 0; padding: 0; background: #0a0a0f !important; }

  :root {
    --tt-primary: #6C5CE7;
    --tt-primary-dark: #5A4BD1;
    --tt-primary-light: #A29BFE;
    --tt-bg: #0a0a0f;
    --tt-surface: #12121a;
    --tt-surface-alt: #181824;
    --tt-border: #1e1e2e;
    --tt-border-light: #2a2a3e;
    --tt-text: #e0e0e0;
    --tt-text-muted: #8888aa;
    --tt-green: #00ff88;
    --tt-green-dark: #00cc6a;
    --tt-red: #ff4466;
    --tt-yellow: #ffaa00;
    --tt-cyan: #00d4ff;
    --tt-radius: 12px;
    --tt-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .tt-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--tt-text);
    max-width: 900px;
    margin: 0 auto;
    padding: 0 20px;
    line-height: 1.6;
  }

  .tt-wrapper * { box-sizing: border-box; }

  .tt-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .tt-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--tt-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .tt-hero h1 span { color: var(--tt-primary); }

  .tt-intro {
    font-size: 1.05rem;
    color: var(--tt-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .tt-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--tt-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--tt-border);
    border-radius: 20px;
  }

  /* Controls */
  .tt-controls {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .tt-control-group {
    display: flex;
    gap: 0;
    border: 1px solid var(--tt-border);
    border-radius: 8px;
    overflow: hidden;
  }

  .tt-ctrl-btn {
    padding: 8px 14px;
    background: var(--tt-bg);
    border: none;
    color: var(--tt-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
    white-space: nowrap;
  }

  .tt-ctrl-btn:not(:last-child) { border-right: 1px solid var(--tt-border); }

  .tt-ctrl-btn.active {
    background: var(--tt-primary);
    color: #fff;
  }

  .tt-ctrl-btn:hover:not(.active) { background: var(--tt-surface); }

  .tt-ctrl-label {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--tt-text-muted);
    margin-right: 6px;
    align-self: center;
  }

  .tt-custom-input {
    width: 60px;
    padding: 8px 10px;
    background: var(--tt-surface);
    border: 1px solid var(--tt-border);
    border-radius: 8px;
    color: var(--tt-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    text-align: center;
    outline: none;
    display: none;
  }

  .tt-custom-input:focus { border-color: var(--tt-primary); }
  .tt-custom-input.visible { display: block; }

  /* Live stats bar */
  .tt-stats-bar {
    display: flex;
    gap: 16px;
    justify-content: center;
    margin-bottom: 16px;
    flex-wrap: wrap;
  }

  .tt-stat {
    text-align: center;
    min-width: 80px;
    padding: 12px 16px;
    background: var(--tt-surface);
    border: 1px solid var(--tt-border);
    border-radius: 10px;
  }

  .tt-stat-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--tt-green);
    line-height: 1;
  }

  .tt-stat-value.warn { color: var(--tt-yellow); }
  .tt-stat-value.bad { color: var(--tt-red); }

  .tt-stat-label {
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--tt-text-muted);
    margin-top: 4px;
  }

  /* Timer */
  .tt-timer {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--tt-primary-light);
  }

  .tt-timer.running { color: var(--tt-yellow); }
  .tt-timer.danger { color: var(--tt-red); }

  /* Text display */
  .tt-text-container {
    background: var(--tt-surface);
    border: 1px solid var(--tt-border);
    border-radius: var(--tt-radius);
    padding: 24px;
    margin-bottom: 16px;
    min-height: 160px;
    cursor: text;
    position: relative;
    box-shadow: var(--tt-shadow);
    transition: border-color 0.15s;
  }

  .tt-text-container:focus-within,
  .tt-text-container.focused {
    border-color: var(--tt-primary);
  }

  .tt-text-display {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.15rem;
    line-height: 2;
    letter-spacing: 0.02em;
    word-break: break-word;
    user-select: none;
  }

  .tt-char { transition: color 0.05s; }
  .tt-char.correct { color: var(--tt-green); }
  .tt-char.incorrect { color: #fff; background: var(--tt-red); border-radius: 2px; }
  .tt-char.current { border-left: 2px solid var(--tt-yellow); animation: ttBlink 0.8s step-end infinite; }
  .tt-char.untyped { color: #444466; }

  @keyframes ttBlink {
    50% { border-left-color: transparent; }
  }

  .tt-hidden-input {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    cursor: text;
    font-size: 16px;
  }

  .tt-focus-hint {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: var(--tt-text-muted);
    font-size: 0.95rem;
    pointer-events: none;
    display: none;
  }

  .tt-focus-hint.visible { display: block; }

  /* Action buttons */
  .tt-actions {
    display: flex;
    gap: 8px;
    justify-content: center;
    margin-bottom: 24px;
  }

  .tt-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
    white-space: nowrap;
  }

  .tt-btn-primary {
    background: var(--tt-primary);
    color: #fff;
  }

  .tt-btn-primary:hover {
    background: var(--tt-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 16px rgba(108, 92, 231, 0.35);
  }

  .tt-btn-secondary {
    background: var(--tt-surface-alt);
    color: var(--tt-text);
    border: 1px solid var(--tt-border);
  }

  .tt-btn-secondary:hover {
    border-color: var(--tt-primary);
    background: rgba(108, 92, 231, 0.1);
  }

  /* Results overlay */
  .tt-results {
    display: none;
    background: var(--tt-surface);
    border: 1px solid var(--tt-border);
    border-radius: var(--tt-radius);
    padding: 32px;
    margin-bottom: 24px;
    text-align: center;
    box-shadow: var(--tt-shadow);
  }

  .tt-results.visible { display: block; }

  .tt-results h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    color: var(--tt-text);
  }

  .tt-result-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 12px;
    margin-bottom: 24px;
  }

  .tt-result-card {
    background: var(--tt-surface-alt);
    border: 1px solid var(--tt-border);
    border-radius: 10px;
    padding: 16px;
  }

  .tt-result-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--tt-green);
    line-height: 1;
  }

  .tt-result-label {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--tt-text-muted);
    margin-top: 6px;
  }

  .tt-result-value.primary { color: var(--tt-primary-light); }

  /* Chart */
  .tt-chart-container {
    background: var(--tt-surface-alt);
    border: 1px solid var(--tt-border);
    border-radius: 10px;
    padding: 16px;
    margin-bottom: 24px;
  }

  .tt-chart-title {
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--tt-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-bottom: 8px;
    text-align: left;
  }

  .tt-chart-canvas {
    width: 100%;
    height: 150px;
    display: block;
  }

  /* Personal best */
  .tt-pb {
    display: inline-block;
    padding: 6px 14px;
    background: rgba(108, 92, 231, 0.15);
    border: 1px solid rgba(108, 92, 231, 0.3);
    border-radius: 20px;
    font-size: 0.85rem;
    color: var(--tt-primary-light);
    margin-bottom: 16px;
  }

  .tt-pb-new {
    background: rgba(0, 255, 136, 0.15);
    border-color: rgba(0, 255, 136, 0.3);
    color: var(--tt-green);
  }

  /* History */
  .tt-history {
    background: var(--tt-surface);
    border: 1px solid var(--tt-border);
    border-radius: var(--tt-radius);
    padding: 24px;
    margin-bottom: 24px;
  }

  .tt-history h3 {
    font-size: 1rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--tt-text);
  }

  .tt-history-empty {
    color: var(--tt-text-muted);
    font-size: 0.9rem;
    text-align: center;
    padding: 20px;
  }

  .tt-history-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.82rem;
  }

  .tt-history-table th {
    text-align: left;
    padding: 8px 10px;
    font-weight: 600;
    color: var(--tt-text-muted);
    border-bottom: 1px solid var(--tt-border);
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  .tt-history-table td {
    padding: 8px 10px;
    color: var(--tt-text);
    border-bottom: 1px solid var(--tt-border);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
  }

  .tt-history-table tr:last-child td { border-bottom: none; }

  .tt-history-chart {
    margin-top: 16px;
  }

  /* Content section */
  .tt-content {
    margin-top: 48px;
    max-width: 800px;
  }

  .tt-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--tt-text);
  }

  .tt-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 10px;
    color: var(--tt-text);
  }

  .tt-content p {
    color: var(--tt-text-muted);
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .tt-content ul, .tt-content ol {
    color: var(--tt-text-muted);
    padding-left: 24px;
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .tt-content code {
    background: var(--tt-surface-alt);
    padding: 2px 6px;
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85em;
    color: var(--tt-primary-light);
  }

  /* FAQ */
  .tt-faq {
    max-width: 820px;
    margin: 48px auto 40px;
  }

  .tt-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--tt-text);
  }

  .tt-faq-item {
    border: 1px solid var(--tt-border);
    border-radius: var(--tt-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--tt-surface);
  }

  .tt-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--tt-text);
  }

  .tt-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--tt-text-muted);
    line-height: 1.7;
  }

  .tt-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--tt-text-muted);
    border-top: 1px solid var(--tt-border);
    margin-bottom: 40px;
  }

  @media (max-width: 768px) {
    .tt-hero h1 { font-size: 1.6rem; }
    .tt-controls { justify-content: center; }
    .tt-stats-bar { gap: 8px; }
    .tt-stat { min-width: 60px; padding: 8px 10px; }
    .tt-stat-value { font-size: 1.1rem; }
    .tt-text-display { font-size: 1rem; line-height: 1.8; }
    .tt-result-grid { grid-template-columns: repeat(2, 1fr); }
    .tt-result-value { font-size: 1.4rem; }
    .tt-history-table { font-size: 0.72rem; }
    .tt-history-table th, .tt-history-table td { padding: 6px 6px; }
  }
</style>

<div class="tt-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Typing Speed Test">
  <meta itemprop="applicationCategory" content="UtilitiesApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="tt-hero">
    <h1><span>Typing Speed</span> Test</h1>
    <p class="tt-intro">Measure your typing speed in words per minute (WPM) and accuracy with character-by-character feedback. Choose a duration and text type, then start typing. Your progress is tracked locally.</p>
    <span class="tt-updated">Last updated: March 2026 | Free to use, no signup required</span>
  </div>

  <!-- Controls -->
  <div class="tt-controls">
    <span class="tt-ctrl-label">Duration:</span>
    <div class="tt-control-group" id="ttDurationGroup">
      <button class="tt-ctrl-btn" data-dur="15" onclick="ttSetDuration(15, this)">15s</button>
      <button class="tt-ctrl-btn active" data-dur="30" onclick="ttSetDuration(30, this)">30s</button>
      <button class="tt-ctrl-btn" data-dur="60" onclick="ttSetDuration(60, this)">60s</button>
      <button class="tt-ctrl-btn" data-dur="120" onclick="ttSetDuration(120, this)">120s</button>
      <button class="tt-ctrl-btn" data-dur="custom" onclick="ttSetDuration('custom', this)">Custom</button>
    </div>
    <input type="number" class="tt-custom-input" id="ttCustomDur" placeholder="sec" min="5" max="300" value="45">
  </div>

  <div class="tt-controls">
    <span class="tt-ctrl-label">Text type:</span>
    <div class="tt-control-group" id="ttModeGroup">
      <button class="tt-ctrl-btn active" data-mode="words" onclick="ttSetMode('words', this)">Common Words</button>
      <button class="tt-ctrl-btn" data-mode="sentences" onclick="ttSetMode('sentences', this)">Sentences</button>
      <button class="tt-ctrl-btn" data-mode="code" onclick="ttSetMode('code', this)">Code</button>
      <button class="tt-ctrl-btn" data-mode="numbers" onclick="ttSetMode('numbers', this)">Numbers</button>
    </div>
  </div>

  <!-- Live stats -->
  <div class="tt-stats-bar">
    <div class="tt-stat">
      <div class="tt-stat-value tt-timer" id="ttTimer">30</div>
      <div class="tt-stat-label">Seconds</div>
    </div>
    <div class="tt-stat">
      <div class="tt-stat-value" id="ttLiveWpm">0</div>
      <div class="tt-stat-label">WPM</div>
    </div>
    <div class="tt-stat">
      <div class="tt-stat-value" id="ttLiveAcc">100</div>
      <div class="tt-stat-label">Accuracy %</div>
    </div>
    <div class="tt-stat">
      <div class="tt-stat-value" id="ttLiveChars" style="color:var(--tt-cyan);">0</div>
      <div class="tt-stat-label">Characters</div>
    </div>
    <div class="tt-stat">
      <div class="tt-stat-value bad" id="ttLiveErrors">0</div>
      <div class="tt-stat-label">Errors</div>
    </div>
  </div>

  <!-- Text display -->
  <div class="tt-text-container" id="ttTextContainer" onclick="document.getElementById('ttInput').focus();">
    <div class="tt-text-display" id="ttTextDisplay"></div>
    <textarea class="tt-hidden-input" id="ttInput" autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false"></textarea>
    <div class="tt-focus-hint visible" id="ttFocusHint">Click here or press any key to start typing</div>
  </div>

  <!-- Actions -->
  <div class="tt-actions">
    <button class="tt-btn tt-btn-primary" onclick="ttRestart()">Restart</button>
    <button class="tt-btn tt-btn-secondary" onclick="ttNewText()">New Text</button>
  </div>

  <!-- Results -->
  <div class="tt-results" id="ttResults">
    <h2>Test Complete</h2>
    <div id="ttPbBadge"></div>
    <div class="tt-result-grid">
      <div class="tt-result-card">
        <div class="tt-result-value" id="ttResWpm">0</div>
        <div class="tt-result-label">Net WPM</div>
      </div>
      <div class="tt-result-card">
        <div class="tt-result-value primary" id="ttResGrossWpm">0</div>
        <div class="tt-result-label">Gross WPM</div>
      </div>
      <div class="tt-result-card">
        <div class="tt-result-value" id="ttResAcc">0%</div>
        <div class="tt-result-label">Accuracy</div>
      </div>
      <div class="tt-result-card">
        <div class="tt-result-value primary" id="ttResChars">0</div>
        <div class="tt-result-label">Characters</div>
      </div>
      <div class="tt-result-card">
        <div class="tt-result-value primary" id="ttResCorrect">0</div>
        <div class="tt-result-label">Correct</div>
      </div>
      <div class="tt-result-card">
        <div class="tt-result-value bad" id="ttResErrors">0</div>
        <div class="tt-result-label">Errors</div>
      </div>
      <div class="tt-result-card">
        <div class="tt-result-value primary" id="ttResConsist">0%</div>
        <div class="tt-result-label">Consistency</div>
      </div>
    </div>

    <!-- Speed chart -->
    <div class="tt-chart-container">
      <div class="tt-chart-title">Speed Over Time (WPM per 5s interval)</div>
      <canvas class="tt-chart-canvas" id="ttChart"></canvas>
    </div>

    <div class="tt-actions">
      <button class="tt-btn tt-btn-primary" onclick="ttRestart()">Try Again</button>
      <button class="tt-btn tt-btn-secondary" onclick="ttNewText()">New Text</button>
    </div>
  </div>

  <!-- History -->
  <div class="tt-history" id="ttHistory">
    <h3>Recent Tests</h3>
    <div id="ttHistoryContent">
      <div class="tt-history-empty">No tests completed yet. Start typing to record your first result.</div>
    </div>
    <div class="tt-chart-container tt-history-chart" id="ttHistoryChartWrap" style="display:none;">
      <div class="tt-chart-title">WPM History (Last 10 Tests)</div>
      <canvas class="tt-chart-canvas" id="ttHistoryChart"></canvas>
    </div>
  </div>

  <div class="tt-meta">
    <span>All data stored locally in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO Content -->
  <div class="tt-content">
    <h2>What Is a Typing Speed Test</h2>
    <p>A typing speed test measures how quickly and accurately you can type text displayed on screen. The standard metric is Words Per Minute (WPM), where one "word" is defined as five characters including spaces. This standardization allows fair comparison regardless of the language or text complexity being typed. Most tests also track accuracy as the percentage of characters typed correctly out of all characters typed.</p>
    <p>Typing tests serve several purposes. Job applicants use them to demonstrate proficiency for data entry, transcription, and administrative roles. Students use them to benchmark their progress while learning touch typing. Programmers use them to measure general keyboard fluency, which translates directly to coding speed. And many people simply use them as a quick, competitive exercise to see how they stack up against averages.</p>

    <h3>How WPM Is Calculated</h3>
    <p>Gross WPM counts every character you type, divides by five (the standard word length), and divides by the elapsed time in minutes. For a 60-second test where you typed 300 characters, the gross WPM would be (300 / 5) / 1 = 60 WPM.</p>
    <p>Net WPM subtracts errors from the gross figure. The formula is: Net WPM = Gross WPM - (Uncorrected Errors / Time in Minutes). If you had 60 gross WPM and made 3 uncorrected errors in one minute, your net WPM would be 57. Some tests calculate net WPM differently by factoring accuracy as a percentage: Net WPM = Gross WPM * (Accuracy / 100).</p>
    <p>This tool reports both values so you can see the full picture. The primary figure shown is net WPM, since it reflects usable typing output.</p>

    <h3>Average Typing Speeds by Profession</h3>
    <ul>
      <li>General population (casual typists): 35-45 WPM</li>
      <li>Office workers and students: 40-60 WPM</li>
      <li>Professional typists and secretaries: 65-85 WPM</li>
      <li>Software developers: 50-80 WPM</li>
      <li>Data entry specialists: 75-100 WPM</li>
      <li>Court reporters (using stenotype): 200-300 WPM</li>
      <li>Competitive typists: 120-180 WPM</li>
    </ul>
    <p>These ranges represent sustained typing on unfamiliar text. When typing familiar content or short bursts, speeds can be considerably higher.</p>

    <h3>How to Improve Your Typing Speed</h3>
    <p>The most effective way to increase typing speed is to focus on accuracy first. Correcting mistakes takes more time than typing slowly but correctly. Once your accuracy consistently stays above 95%, speed improvements follow naturally with practice.</p>
    <p>Learn the home row position: place your left fingers on A, S, D, F and your right fingers on J, K, L, and the semicolon key. Your index fingers rest on F and J, which have tactile bumps on most keyboards. From this position, each finger is responsible for a specific set of keys. Practice reaching each key from the home row without looking at the keyboard.</p>
    <p>Practice daily in short sessions of 10-15 minutes rather than long marathon sessions. Consistency builds muscle memory faster than occasional long practices. Vary your text sources to avoid memorizing specific passages. Use tests with sentences and code snippets in addition to random words.</p>

    <h3>Touch Typing Basics</h3>
    <p>Touch typing means typing without looking at the keyboard. It relies on muscle memory so each finger automatically moves to the correct key. The learning curve takes roughly 2-4 weeks of daily practice to reach your previous "hunt and peck" speed, after which improvement accelerates.</p>
    <p>The home row (ASDF JKL;) is the anchor position. The top row (QWERTY) is reached by extending fingers upward. The bottom row (ZXCV) is reached by curling fingers downward. Each finger handles a vertical column of keys, with the index fingers covering two columns each (the home column plus the adjacent inner column). Thumbs handle the space bar.</p>
    <p>Common mistakes during the transition include reverting to old habits under pressure and tensing the hands. Keep your wrists floating slightly above the keyboard surface, not resting on the desk. Maintain a relaxed posture with shoulders down. If you notice tension building, pause and shake your hands out.</p>
  </div>

  <!-- FAQ -->
  <div class="tt-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="tt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is a good typing speed?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">For most purposes, 40 WPM is functional and 60 WPM is proficient. Professional roles that involve heavy typing typically require 65-80 WPM. Above 80 WPM is considered fast, and above 100 WPM is competitive. The important thing is that accuracy stays above 95%, since errors negate speed gains. Focus on accuracy first, and speed will increase with practice.</p>
      </div>
    </div>

    <div class="tt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How is WPM calculated in this test?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This test uses the standard definition where one word equals five characters (including spaces). Gross WPM is total characters typed divided by 5, divided by time in minutes. Net WPM subtracts errors: Net WPM = Gross WPM * (Accuracy / 100). Both values are shown in the results. The timer starts on your first keystroke and counts down from your selected duration.</p>
      </div>
    </div>

    <div class="tt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does the test work on mobile devices?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The test works on mobile but results will not be comparable to desktop typing. Mobile keyboards use autocorrect, predictive text, and swipe gestures that inflate WPM relative to physical keyboard typing. For an accurate measurement of your typing ability, use a physical keyboard. If you are testing thumb typing speed on a phone, the results are valid within that context but should not be compared to desktop benchmarks.</p>
      </div>
    </div>

    <div class="tt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why do my results vary between tests?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Variation of 5-15 WPM between tests is normal. Factors include text difficulty (common words are faster than sentences with punctuation), your current focus level, physical fatigue, and the specific word combinations in each sample. The consistency metric shown in results reflects this variation. A consistency above 80% indicates steady performance. Take multiple tests and look at your average rather than any single result.</p>
      </div>
    </div>

    <div class="tt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my test data stored anywhere?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">All test data, including your personal best and test history, is stored locally in your browser using localStorage. Nothing is sent to any server. If you clear your browser data or switch browsers, your history will be reset. There is no account system and no cloud sync. Your data stays on your device.</p>
      </div>
    </div>
  </div>

  <!-- Related Tools -->
  <div style="padding:1.5rem;background:var(--tt-surface);border:1px solid var(--tt-border);border-radius:12px;margin-bottom:20px;">
    <h2 style="color:var(--tt-primary);font-size:1.3rem;margin:0 0 1rem;">Related Tools</h2>
    <ul style="list-style:none;padding:0;margin:0;">
      <li style="margin-bottom:0.5rem;"><a href="/tools/word-counter/" style="color:var(--tt-green);text-decoration:none;">Word Counter</a> -- Count words, characters, and reading time</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/text-to-speech/" style="color:var(--tt-green);text-decoration:none;">Text to Speech</a> -- Convert text to audio in your browser</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/pomodoro-timer/" style="color:var(--tt-green);text-decoration:none;">Pomodoro Timer</a> -- Focus timer with break tracking</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/stopwatch/" style="color:var(--tt-green);text-decoration:none;">Stopwatch</a> -- Precise time tracking with lap support</li>
    </ul>
  </div>

  <!-- Author Box -->
  <div style="padding:1.5rem;background:var(--tt-surface);border:1px solid var(--tt-border);border-radius:12px;display:flex;gap:1rem;align-items:center;margin-bottom:20px;">
    <div style="width:48px;height:48px;border-radius:50%;background:var(--tt-primary);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;flex-shrink:0;">ML</div>
    <div>
      <div style="color:var(--tt-text);font-weight:600;">Michael Lip</div>
      <div style="color:var(--tt-text-muted);font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:var(--tt-primary);">Zovo</a>. Building free developer and productivity tools.</div>
    </div>
  </div>

  <footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid var(--tt-border);margin-top:1rem;">
    <p>Built by <a href="https://zovo.one" style="color:var(--tt-primary);text-decoration:none;">Michael Lip</a> at <a href="https://zovo.one" style="color:var(--tt-primary);text-decoration:none;">zovo.one</a></p>
  </footer>
</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Typing Speed Test",
      "url": "https://zovo.one/tools/typing-test/",
      "applicationCategory": "UtilitiesApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://zovo.one/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://zovo.one/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Typing Speed Test", "item": "https://zovo.one/tools/typing-test/" }
      ]
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What is a good typing speed?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For most purposes, 40 WPM is functional and 60 WPM is proficient. Professional roles that involve heavy typing typically require 65-80 WPM. Above 80 WPM is fast, above 100 is competitive."
          }
        },
        {
          "@type": "Question",
          "name": "How is WPM calculated in this test?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "One word equals five characters. Gross WPM = (total characters / 5) / time in minutes. Net WPM = Gross WPM * (accuracy / 100). Both are shown in results."
          }
        },
        {
          "@type": "Question",
          "name": "Does the test work on mobile devices?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It works but results are not comparable to desktop. Mobile autocorrect and swipe inflate WPM. Use a physical keyboard for accurate measurement."
          }
        },
        {
          "@type": "Question",
          "name": "Why do my results vary between tests?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Variation of 5-15 WPM is normal due to text difficulty, focus level, and fatigue. Take multiple tests and look at your average."
          }
        },
        {
          "@type": "Question",
          "name": "Is my test data stored anywhere?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "All data is stored locally in your browser via localStorage. Nothing is sent to any server. Clearing browser data resets your history."
          }
        }
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://zovo.one/favicon.ico"
    }
  ]
}
</script>

<script>
(function() {
  "use strict";

  // ============ TEXT SAMPLES ============

  var SAMPLES = {
    words: [
      "the be to of and a in that have i it for not on with he as you do at this but his by from they we say her she or an will my one all would there their what so up out if about who get which go me when make can like time no just him know take people into year your good some could them see other than then now look only come its over think also back after use two how our work first well way even new want because any these give day most us",
      "about after again air all along also an and another any are around as at away back be because been before began being between big both but by came can come could day did different do does down each end even every few find first for from get give go going good great had has have he help her here him his home house how i if in into is it its just know large last let life like line little long look made make man many may me more most much must my name never new next no not now number of off old on one only or other our out over own part people place point right said same say see she should show small so some something sound still such take tell than that the their them then there these they thing think this those thought three through time to together too two under up us use very want water was way we well were what when where which while who why will with word work world would write year you your",
      "ability about above accept according account across act action activity actually add address administration admit adult affect after again against age agency agent ago agree agreement ahead air all allow almost alone along already also always american among amount analysis and animal another answer any anyone anything appear apply approach area argue arm around arrive art article as ask assume at attack attention available avoid away back bad bag ball bank bar base be beat beautiful because become bed before begin behavior behind believe benefit best better between beyond big billion bit black blood blue board body bone book born both box boy break bring brother budget build building business but buy by call camera campaign can cancer candidate capital car card care career carry case catch cause cell center central century certain chair chairman challenge chance change character charge check child choice choose church citizen city civil claim class clear clearly close coach cold collection college color come commercial common community company compare computer concern condition conference congress consider consumer contain continue control cost could country couple course court cover create crime cultural culture cup current customer cut dark data daughter day dead deal death debate decade decide decision deep defense degree democrat democratic department depend describe design despite detail determine develop development die difference different difficult dinner direction director discover discussion disease do doctor dog door down draw dream drive drop drug during each east eat economic economy edge education effect effort eight either election else employee end energy enjoy enough enter entire environment especially establish even evening event ever every everybody everyone everything evidence exactly example executive exist expect experience expert explain eye face fact factor fail fall family far fast father fear federal feel few field fight figure fill final finally financial find finger firm first fish five floor fly focus follow food foot for force foreign forget form former forward four free friend from front full fund future game garden gas general generation get girl give glass go goal good government great green ground group grow growth guess gun guy hair half hand hang happen happy hard have he head health hear heart heat heavy help her here herself high him himself his hit hold home hope hot hotel hour house how however huge human hundred husband idea identify if image imagine impact important improve in include including increase indicate industry information inside instead institution interest interesting international interview into investment involve issue it item its itself job join just keep key kid kill kind kitchen know knowledge land language large last late later laugh law lawyer lay lead leader learn least leave left leg legal less let letter level lie life light like likely line list listen little live local long look lose loss lot love low machine magazine main maintain major majority manage management manager many market marriage material matter may maybe me mean measure media medical meeting member memory mention message method middle might military million mind minute miss mission model modern moment money month more morning most mother mouth move movement movie mr mrs much music must my myself name nation national natural nature near nearly necessary need network never new news newspaper next nice night no none nor north not note nothing now number occur of off offer office officer official often oh oil ok old on once one only onto open operation opportunity option or order organization other others our out outside over own owner page pain painting pair paper parent part particular particularly partner party pass past patient pattern pay peace people per perform performance perhaps period person personal phone physical pick picture piece place plan plant play player please point police policy political politics poor popular population position positive possible power practice prepare present president pressure pretty prevent price private probably problem process produce product production professional professor program project property protect prove provide public pull purpose push put quality question quickly quite race raise range rate rather reach read ready real reality realize really reason receive recent recently record red reduce reflect region relate relationship religious remain remember remove repeat report represent republican require research resource respond response rest result return reveal right rise risk road rock role room rule run safe same save say scene school science scientist score sea season seat second section security see seek seem sell send senior sense series serious serve service set seven several shake share she shoot short shot shoulder show side sign significant similar simple simply since sing sister sit site situation six size skill skin small smile so social society soldier some somebody someone something sometimes son song soon sort source south southern space speak special specific speech spend sport spring staff stage stand standard star start state statement station stay step still stock stop story strategy street strong structure student study stuff style subject success successful such suddenly suffer suggest summer support sure surface system table take talk task tax teach teacher team technology television tell ten tend term test than thank that the their them then there these they thing think third this those though thought thousand threat three through throughout throw thus time to today together tonight too top total tough toward town trade traditional training travel treat treatment tree trial trip trouble true truth try turn tv two type under understand unit until up upon us use usually value various very victim view violence visit voice vote wait walk wall want war watch water way we weapon wear week weight well west western what whatever when where whether which while white who whole whom whose why wide wife will win wind window wish with within without woman wonder word work worker world worry would write writer wrong yard yeah year yes yet you young your yourself youth",
      "paper river music dance heart stone cloud reach dream house light earth water space clear drive watch plant write close study learn point force small great sound table chair floor field track guide match shape build trade value basic model serve press cover break stand night bring carry found group start under place state power world light still order never other right story round again under every first think three small large other about which would their state could after first write think about these other which about heart dream space light cloud water earth paper music stone river dance table chair floor field sound",
      "begin world place point house stand start large small every under light sound earth water cloud paper stone music dance heart river dream clear still write space night order state think round again group found carry bring serve press cover trade value basic model build shape guide track field floor chair table three which about other first after would could state their these think other large small house great close drive watch force plant point learn study floor group still right night round place start found carry bring press cover shape guide under every power world light order sound clear write space earth water cloud paper music river stone heart dance dream again",
      "across against allow almost alone along already also always among amount another answer anyone anything appear apply around arrive article away back because become before began behind believe between beyond billion both break bring brother budget building business camera campaign candidate capital career catch cause center central century certain chairman challenge chance change character check choice choose church citizen civil claim class coach collection college color commercial common community company compare computer concern condition conference consider consumer contain continue control country couple create crime cultural current customer daughter debate decade decide decision defense degree democrat department depend describe design despite develop different difficult dinner direction director discover discussion disease doctor during eastern economic economy education effect effort election employee energy enjoy enough enter entire especially establish evening evidence exactly example executive expect experience explain factor federal figure finally financial foreign forget former forward future garden general generation government growth happen hundred husband identify imagine impact important improve include increase indicate industry information instead institution interest international interview investment involve itself knowledge language lawyer letter listen little magazine maintain majority management manager marriage material measure medical meeting mention message method middle military mission modern moment morning movement national natural necessary network newspaper nothing number officer official operation opportunity option organization outside painting particular partner patient pattern percent perform performance physical picture player please political politics popular population position positive possible practice prepare present president pressure private probably problem process produce product production professional professor project property protect provide quality quickly rather reality realize recently recognize record reduce reflect region relate relationship religious remember remove repeat represent republican require research resource respond restaurant reveal science scientist security senior serious several shoulder significant similar simply situation society soldier somebody someone something sometimes southern special specific statement station strategy structure student subject success suffer suggest support surface system teacher technology television thousand throughout together tonight toward traditional training treatment trouble understand usually various violence whatever western without worker yourself",
      "apple orange grape lemon mango peach plumb berry melon cherry walnut almond wheat barley sugar cream butter bread cheese pasta sauce olive basil thyme pepper garlic onion carrot celery lettuce turnip radish squash melon gourd beans lentil grain flour dough yeast toast roast grill steam saute braise poach blanch slice chop mince grate",
      "north south east west front back left right upper lower inner outer under above below near far close deep wide tall short thick thin light heavy full empty open shut start close begin final first second third fourth fifth sixth next prior early later soon never often always rarely maybe truly fully partly almost nearly quite rather",
      "happy angry calm quiet loud brave smart quick sharp clear fresh clean rough smooth plain fancy simple whole broken mixed fixed solid liquid frozen boiled fresh stale bitter sweet salty sour spicy bland mild rich poor young grand humble noble loyal proud fair just kind warm cool gentle fierce steady rapid slow steady swift",
      "running walking sitting standing jumping climbing falling rising floating sinking diving swimming flying gliding sailing rowing driving riding pulling pushing lifting carrying holding catching throwing dropping picking choosing making taking giving sharing keeping losing finding seeking knowing feeling seeing hearing tasting smelling touching moving staying waiting resting sleeping waking"
    ],
    sentences: [
      "The quick brown fox jumps over the lazy dog near the riverbank.",
      "A journey of a thousand miles begins with a single step forward.",
      "She picked up the heavy box and carried it across the narrow hallway.",
      "The old clock on the mantle had stopped working years ago.",
      "Rain pattered against the window as the storm gathered strength outside.",
      "He spent the entire afternoon organizing his collection of vintage records.",
      "The mountain trail was steep, but the view from the top made it worthwhile.",
      "Fresh bread from the bakery down the street always smells wonderful.",
      "They decided to take the longer route because the bridge was closed.",
      "A small bird landed on the fence and began to sing a familiar tune.",
      "The library was quiet except for the occasional sound of turning pages.",
      "She wrote the address on the envelope and sealed it with care.",
      "Winter mornings are best spent with a warm drink and a good book.",
      "The train arrived at the station three minutes ahead of schedule.",
      "He fixed the leaking pipe under the kitchen sink before dinner.",
      "Sunlight filtered through the curtains and fell across the wooden floor.",
      "The garden needed water, so she connected the hose and turned it on.",
      "They walked along the beach collecting shells and smooth stones.",
      "The meeting was scheduled for nine but started fifteen minutes late.",
      "She found the missing key under a pile of papers on her desk.",
      "The road curved sharply to the left before crossing the narrow bridge.",
      "He opened the window to let fresh air into the stuffy room.",
      "The children played in the yard while their parents watched from the porch.",
      "A thick fog settled over the valley and stayed until midday.",
      "She plugged in the laptop and waited for it to finish charging.",
      "The restaurant on the corner serves the best grilled fish in town.",
      "He checked his watch and realized he had less than ten minutes left.",
      "The package arrived earlier than expected and was left at the front door.",
      "Autumn leaves covered the pathway leading up to the old stone house.",
      "She measured the fabric twice before making the first cut.",
      "The engine started on the second try after sitting idle for weeks.",
      "He sorted the mail into three piles: bills, letters, and junk.",
      "The concert was sold out weeks before the band arrived in the city.",
      "She put the groceries away and started preparing dinner for the family.",
      "The ceiling fan hummed quietly as the room slowly cooled down.",
      "He tightened the bolts on the shelf to make sure it was secure.",
      "The sunset painted the sky in shades of orange and deep purple.",
      "She double-checked the calculations before submitting the final report.",
      "The neighbor's cat sat on the fence watching the birds in the tree.",
      "He packed a sandwich, an apple, and a bottle of water for the hike.",
      "The first chapter of the book introduces the main character and setting.",
      "She adjusted the mirror and checked her blind spot before merging.",
      "They set up the tent near the river where the ground was flat.",
      "The printer ran out of ink in the middle of a fifty-page document.",
      "He stacked the firewood neatly against the wall of the shed.",
      "The bus was running late because of construction on the main road.",
      "She watered the plants on the balcony every morning before work.",
      "The coffee had gone cold by the time she remembered to drink it.",
      "He replaced the batteries in the remote control and tried again.",
      "The airport was crowded with travelers heading home for the holidays."
    ],
    code: [
      "function add(a, b) { return a + b; }",
      "const items = data.filter(item => item.active === true);",
      "for (let i = 0; i < array.length; i++) { sum += array[i]; }",
      "if (user && user.isAdmin) { grantAccess(); } else { denyAccess(); }",
      "const result = await fetch('/api/users').then(r => r.json());",
      "document.getElementById('output').textContent = result.toString();",
      "const map = new Map(); map.set('key', 'value');",
      "try { JSON.parse(input); } catch (e) { console.error(e.message); }",
      "export default function App() { return <div>Hello</div>; }",
      "const [count, setCount] = useState(0);",
      "arr.reduce((acc, val) => acc + val, 0);",
      "Object.keys(obj).forEach(key => { console.log(key, obj[key]); });",
      "class Node { constructor(val) { this.val = val; this.next = null; } }",
      "const sorted = [...array].sort((a, b) => a - b);",
      "router.get('/users/:id', async (req, res) => { res.json(user); });",
      "const unique = [...new Set(array)];",
      "setTimeout(() => { callback(); }, 1000);",
      "const { name, age, email } = userData;",
      "while (queue.length > 0) { process(queue.shift()); }",
      "element.addEventListener('click', (e) => { e.preventDefault(); });",
      "const config = { port: 3000, host: 'localhost', debug: false };",
      "return str.split('').reverse().join('');",
      "const isValid = /^[a-zA-Z0-9]+$/.test(input);",
      "Promise.all([fetchA(), fetchB()]).then(([a, b]) => merge(a, b));",
      "switch (action.type) { case 'ADD': return [...state, action.payload]; }",
      "fs.readFileSync('config.json', 'utf8');",
      "console.log(`Total: ${items.length} items, ${total} bytes`);",
      "const debounce = (fn, ms) => { let t; return (...a) => { clearTimeout(t); t = setTimeout(() => fn(...a), ms); }; };",
      "app.use(express.json()); app.use(cors());",
      "db.collection('users').find({ age: { $gte: 18 } }).toArray();",
      "type User = { id: number; name: string; email: string; };",
      "interface Config { port: number; host: string; debug?: boolean; }",
      "enum Status { Active = 'active', Inactive = 'inactive' }",
      "SELECT name, email FROM users WHERE active = true ORDER BY name;",
      "CREATE TABLE posts (id SERIAL PRIMARY KEY, title TEXT NOT NULL);",
      "git commit -m 'fix: resolve null reference in auth module'",
      "docker run -d -p 8080:80 --name web nginx:latest",
      "npm install --save-dev typescript @types/node eslint prettier",
      "curl -X POST https://api.example.com/data -H 'Content-Type: application/json'",
      "ssh -i key.pem user@192.168.1.100"
    ],
    numbers: [
      "1234 5678 9012 3456 7890 1234 5678 9012",
      "42 17 93 65 28 74 51 86 39 10",
      "3.14159 2.71828 1.41421 1.61803 0.57721",
      "192.168.1.1 10.0.0.1 172.16.0.1 255.255.255.0",
      "2026-03-19 14:30:00 2025-12-31 23:59:59",
      "100 200 300 400 500 600 700 800 900 1000",
      "$19.99 $249.50 $1,299.00 $5.75 $89.99",
      "55 89 144 233 377 610 987 1597 2584 4181",
      "0xFF 0xA3 0x1B 0xC0 0x7F 0x00 0xDE 0xAD",
      "1001 0110 1010 0101 1100 0011 1111 0000",
      "+1 (555) 123-4567 +44 20 7946 0958",
      "98.6 100.4 37.0 38.5 36.8 39.2 37.5",
      "3 1 4 1 5 9 2 6 5 3 5 8 9 7 9 3 2 3 8 4",
      "50% 75% 33% 90% 12% 67% 88% 45% 21% 99%",
      "1024 2048 4096 8192 16384 32768 65536 131072"
    ]
  };

  // ============ STATE ============

  var duration = 30;
  var mode = "words";
  var currentText = "";
  var charIndex = 0;
  var errors = 0;
  var correctChars = 0;
  var totalTyped = 0;
  var testStarted = false;
  var testEnded = false;
  var timerInterval = null;
  var timeLeft = 30;
  var startTime = 0;
  var wpmSnapshots = [];
  var snapshotInterval = null;

  var inputEl = document.getElementById("ttInput");
  var displayEl = document.getElementById("ttTextDisplay");
  var timerEl = document.getElementById("ttTimer");
  var hintEl = document.getElementById("ttFocusHint");

  // ============ TEXT GENERATION ============

  function generateText() {
    var pool = SAMPLES[mode];
    if (mode === "words") {
      // Pick a random word list and shuffle words
      var wordList = pool[Math.floor(Math.random() * pool.length)];
      var words = wordList.split(/\s+/);
      shuffleArray(words);
      // Take enough words for the duration
      var count = Math.max(80, Math.ceil(duration * 2.5));
      var selected = [];
      while (selected.length < count) {
        for (var i = 0; i < words.length && selected.length < count; i++) {
          selected.push(words[i]);
        }
        shuffleArray(words);
      }
      return selected.join(" ");
    } else if (mode === "sentences") {
      var shuffled = pool.slice();
      shuffleArray(shuffled);
      var count2 = Math.max(6, Math.ceil(duration / 8));
      return shuffled.slice(0, Math.min(count2, shuffled.length)).join(" ");
    } else if (mode === "code") {
      var shuffled2 = pool.slice();
      shuffleArray(shuffled2);
      var count3 = Math.max(5, Math.ceil(duration / 6));
      return shuffled2.slice(0, Math.min(count3, shuffled2.length)).join("\n");
    } else if (mode === "numbers") {
      var shuffled3 = pool.slice();
      shuffleArray(shuffled3);
      var count4 = Math.max(4, Math.ceil(duration / 6));
      return shuffled3.slice(0, Math.min(count4, shuffled3.length)).join(" ");
    }
    return "";
  }

  function shuffleArray(arr) {
    for (var i = arr.length - 1; i > 0; i--) {
      var j = Math.floor(Math.random() * (i + 1));
      var t = arr[i]; arr[i] = arr[j]; arr[j] = t;
    }
  }

  // ============ RENDERING ============

  function renderText() {
    var html = "";
    for (var i = 0; i < currentText.length; i++) {
      var cls = "tt-char untyped";
      if (i === charIndex && !testEnded) {
        cls = "tt-char current";
      }
      var ch = currentText[i];
      if (ch === " ") ch = " ";
      else if (ch === "\n") ch = "\u21B5\n";
      else if (ch === "<") ch = "&lt;";
      else if (ch === ">") ch = "&gt;";
      else if (ch === "&") ch = "&amp;";
      html += '<span class="' + cls + '" data-idx="' + i + '">' + ch + '</span>';
    }
    displayEl.innerHTML = html;
  }

  function updateChar(idx, state) {
    var span = displayEl.querySelector('[data-idx="' + idx + '"]');
    if (span) {
      span.className = "tt-char " + state;
    }
  }

  // ============ TIMER ============

  function startTimer() {
    testStarted = true;
    startTime = Date.now();
    timeLeft = duration;
    timerEl.textContent = timeLeft;
    timerEl.classList.add("running");
    timerEl.classList.remove("danger");

    timerInterval = setInterval(function() {
      var elapsed = (Date.now() - startTime) / 1000;
      timeLeft = Math.max(0, Math.ceil(duration - elapsed));
      timerEl.textContent = timeLeft;

      if (timeLeft <= 5) {
        timerEl.classList.add("danger");
      }

      updateLiveStats();

      if (timeLeft <= 0) {
        endTest();
      }
    }, 100);

    // WPM snapshots every 5 seconds
    snapshotInterval = setInterval(function() {
      var elapsed = (Date.now() - startTime) / 1000 / 60;
      if (elapsed > 0) {
        var wpm = Math.round((correctChars / 5) / elapsed);
        wpmSnapshots.push(wpm);
      }
    }, 5000);
  }

  function updateLiveStats() {
    var elapsed = (Date.now() - startTime) / 1000 / 60;
    if (elapsed <= 0) return;

    var grossWpm = Math.round((totalTyped / 5) / elapsed);
    var acc = totalTyped > 0 ? Math.round((correctChars / totalTyped) * 100) : 100;
    var netWpm = Math.max(0, Math.round(grossWpm * (acc / 100)));

    document.getElementById("ttLiveWpm").textContent = netWpm;
    document.getElementById("ttLiveAcc").textContent = acc;
    document.getElementById("ttLiveChars").textContent = totalTyped;
    document.getElementById("ttLiveErrors").textContent = errors;

    // Color code accuracy
    var accEl = document.getElementById("ttLiveAcc");
    accEl.classList.remove("warn", "bad");
    if (acc < 90) accEl.classList.add("bad");
    else if (acc < 95) accEl.classList.add("warn");
  }

  // ============ INPUT HANDLING ============

  inputEl.addEventListener("input", function(e) {
    if (testEnded) return;

    if (!testStarted) {
      startTimer();
      hintEl.classList.remove("visible");
    }

    var val = inputEl.value;
    var len = val.length;

    // Handle backspace: user deleted characters
    if (len < charIndex) {
      // Move charIndex back
      for (var b = charIndex - 1; b >= len; b--) {
        updateChar(b, b === len ? "current" : "untyped");
      }
      charIndex = len;
      // Recalculate errors and correct for the visible range
      recalculate(val);
      return;
    }

    // Process new characters
    while (charIndex < len && charIndex < currentText.length) {
      var typed = val[charIndex];
      var expected = currentText[charIndex];
      totalTyped++;

      if (typed === expected) {
        correctChars++;
        updateChar(charIndex, "correct");
      } else {
        errors++;
        updateChar(charIndex, "incorrect");
      }

      charIndex++;
    }

    // Mark next char as current
    if (charIndex < currentText.length) {
      updateChar(charIndex, "current");
    }

    // If user typed all text, end early
    if (charIndex >= currentText.length) {
      endTest();
    }
  });

  function recalculate(val) {
    errors = 0;
    correctChars = 0;
    totalTyped = val.length;
    for (var i = 0; i < val.length && i < currentText.length; i++) {
      if (val[i] === currentText[i]) {
        correctChars++;
      } else {
        errors++;
      }
    }
  }

  inputEl.addEventListener("focus", function() {
    document.getElementById("ttTextContainer").classList.add("focused");
    if (!testStarted && !testEnded) {
      hintEl.classList.remove("visible");
    }
  });

  inputEl.addEventListener("blur", function() {
    document.getElementById("ttTextContainer").classList.remove("focused");
    if (!testStarted && !testEnded) {
      hintEl.classList.add("visible");
    }
  });

  // Prevent tab from leaving the input
  inputEl.addEventListener("keydown", function(e) {
    if (e.key === "Tab") {
      e.preventDefault();
    }
  });

  // ============ END TEST ============

  function endTest() {
    testEnded = true;
    clearInterval(timerInterval);
    clearInterval(snapshotInterval);
    timerEl.classList.remove("running", "danger");

    // Final snapshot
    var elapsed = (Date.now() - startTime) / 1000 / 60;
    if (elapsed > 0 && wpmSnapshots.length === 0) {
      wpmSnapshots.push(Math.round((correctChars / 5) / elapsed));
    }

    var grossWpm = elapsed > 0 ? Math.round((totalTyped / 5) / elapsed) : 0;
    var acc = totalTyped > 0 ? Math.round((correctChars / totalTyped) * 100) : 0;
    var netWpm = Math.max(0, Math.round(grossWpm * (acc / 100)));

    // Consistency: 100% - coefficient of variation of WPM snapshots
    var consistency = 100;
    if (wpmSnapshots.length >= 2) {
      var mean = wpmSnapshots.reduce(function(a, b) { return a + b; }, 0) / wpmSnapshots.length;
      var variance = wpmSnapshots.reduce(function(a, b) { return a + Math.pow(b - mean, 2); }, 0) / wpmSnapshots.length;
      var stdDev = Math.sqrt(variance);
      var cv = mean > 0 ? (stdDev / mean) * 100 : 0;
      consistency = Math.max(0, Math.round(100 - cv));
    }

    // Display results
    document.getElementById("ttResWpm").textContent = netWpm;
    document.getElementById("ttResGrossWpm").textContent = grossWpm;
    document.getElementById("ttResAcc").textContent = acc + "%";
    document.getElementById("ttResChars").textContent = totalTyped;
    document.getElementById("ttResCorrect").textContent = correctChars;
    document.getElementById("ttResErrors").textContent = errors;
    document.getElementById("ttResConsist").textContent = consistency + "%";

    // Color code net WPM
    var wpmEl = document.getElementById("ttResWpm");
    if (netWpm >= 80) wpmEl.style.color = "var(--tt-green)";
    else if (netWpm >= 50) wpmEl.style.color = "var(--tt-yellow)";
    else wpmEl.style.color = "var(--tt-red)";

    // Color code accuracy
    var accResEl = document.getElementById("ttResAcc");
    if (acc >= 95) accResEl.style.color = "var(--tt-green)";
    else if (acc >= 90) accResEl.style.color = "var(--tt-yellow)";
    else accResEl.style.color = "var(--tt-red)";

    // Personal best
    checkPersonalBest(netWpm);

    // Draw chart
    drawSpeedChart(wpmSnapshots);

    // Save to history
    saveHistory(netWpm, grossWpm, acc, consistency);

    // Show results
    document.getElementById("ttResults").classList.add("visible");
  }

  // ============ PERSONAL BEST ============

  function checkPersonalBest(wpm) {
    var key = "zovo_tt_pb_" + mode + "_" + duration;
    var pb = parseInt(localStorage.getItem(key) || "0", 10);
    var badge = document.getElementById("ttPbBadge");

    if (wpm > pb && wpm > 0) {
      localStorage.setItem(key, wpm.toString());
      badge.innerHTML = '<span class="tt-pb tt-pb-new">New Personal Best: ' + wpm + ' WPM</span>';
    } else if (pb > 0) {
      badge.innerHTML = '<span class="tt-pb">Personal Best: ' + pb + ' WPM</span>';
    } else {
      badge.innerHTML = '';
    }
  }

  // ============ SPEED CHART ============

  function drawSpeedChart(data) {
    var canvas = document.getElementById("ttChart");
    var ctx = canvas.getContext("2d");
    var dpr = window.devicePixelRatio || 1;
    var rect = canvas.getBoundingClientRect();
    canvas.width = rect.width * dpr;
    canvas.height = rect.height * dpr;
    ctx.scale(dpr, dpr);

    var w = rect.width;
    var h = rect.height;
    var pad = { top: 10, right: 10, bottom: 25, left: 40 };
    var chartW = w - pad.left - pad.right;
    var chartH = h - pad.top - pad.bottom;

    ctx.clearRect(0, 0, w, h);

    if (data.length < 2) {
      ctx.fillStyle = "#8888aa";
      ctx.font = "12px Inter, sans-serif";
      ctx.textAlign = "center";
      ctx.fillText("Need longer test for speed chart (at least 10 seconds)", w / 2, h / 2);
      return;
    }

    var maxWpm = Math.max.apply(null, data) * 1.15;
    if (maxWpm === 0) maxWpm = 10;

    // Grid lines
    ctx.strokeStyle = "#1e1e2e";
    ctx.lineWidth = 1;
    for (var g = 0; g <= 4; g++) {
      var gy = pad.top + chartH - (chartH * g / 4);
      ctx.beginPath();
      ctx.moveTo(pad.left, gy);
      ctx.lineTo(w - pad.right, gy);
      ctx.stroke();

      ctx.fillStyle = "#8888aa";
      ctx.font = "10px JetBrains Mono, monospace";
      ctx.textAlign = "right";
      ctx.fillText(Math.round(maxWpm * g / 4), pad.left - 5, gy + 3);
    }

    // X axis labels
    ctx.textAlign = "center";
    for (var xi = 0; xi < data.length; xi++) {
      var xx = pad.left + (chartW * xi / (data.length - 1));
      ctx.fillText((xi + 1) * 5 + "s", xx, h - 5);
    }

    // Line
    ctx.beginPath();
    ctx.strokeStyle = "#6C5CE7";
    ctx.lineWidth = 2;
    ctx.lineJoin = "round";
    for (var di = 0; di < data.length; di++) {
      var px = pad.left + (chartW * di / (data.length - 1));
      var py = pad.top + chartH - (chartH * data[di] / maxWpm);
      if (di === 0) ctx.moveTo(px, py);
      else ctx.lineTo(px, py);
    }
    ctx.stroke();

    // Fill
    ctx.lineTo(pad.left + chartW, pad.top + chartH);
    ctx.lineTo(pad.left, pad.top + chartH);
    ctx.closePath();
    ctx.fillStyle = "rgba(108, 92, 231, 0.12)";
    ctx.fill();

    // Dots
    for (var dd = 0; dd < data.length; dd++) {
      var dx = pad.left + (chartW * dd / (data.length - 1));
      var dy = pad.top + chartH - (chartH * data[dd] / maxWpm);
      ctx.beginPath();
      ctx.arc(dx, dy, 3, 0, Math.PI * 2);
      ctx.fillStyle = "#6C5CE7";
      ctx.fill();
    }
  }

  // ============ HISTORY ============

  function saveHistory(netWpm, grossWpm, acc, consistency) {
    var history = JSON.parse(localStorage.getItem("zovo_tt_history") || "[]");
    history.unshift({
      date: new Date().toISOString(),
      netWpm: netWpm,
      grossWpm: grossWpm,
      accuracy: acc,
      consistency: consistency,
      duration: duration,
      mode: mode
    });
    if (history.length > 10) history = history.slice(0, 10);
    localStorage.setItem("zovo_tt_history", JSON.stringify(history));
    renderHistory();
  }

  function renderHistory() {
    var history = JSON.parse(localStorage.getItem("zovo_tt_history") || "[]");
    var container = document.getElementById("ttHistoryContent");
    var chartWrap = document.getElementById("ttHistoryChartWrap");

    if (history.length === 0) {
      container.innerHTML = '<div class="tt-history-empty">No tests completed yet. Start typing to record your first result.</div>';
      chartWrap.style.display = "none";
      return;
    }

    var html = '<table class="tt-history-table">';
    html += '<tr><th>Date</th><th>Net WPM</th><th>Gross WPM</th><th>Accuracy</th><th>Duration</th><th>Mode</th></tr>';
    for (var i = 0; i < history.length; i++) {
      var h = history[i];
      var d = new Date(h.date);
      var dateStr = d.toLocaleDateString() + " " + d.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
      html += '<tr>';
      html += '<td style="font-family:Inter,sans-serif;color:var(--tt-text-muted);">' + dateStr + '</td>';
      html += '<td style="color:var(--tt-green);">' + h.netWpm + '</td>';
      html += '<td>' + h.grossWpm + '</td>';
      html += '<td>' + h.accuracy + '%</td>';
      html += '<td>' + h.duration + 's</td>';
      html += '<td style="font-family:Inter,sans-serif;text-transform:capitalize;">' + h.mode + '</td>';
      html += '</tr>';
    }
    html += '</table>';
    container.innerHTML = html;

    // History chart
    if (history.length >= 2) {
      chartWrap.style.display = "block";
      var wpms = history.slice().reverse().map(function(h) { return h.netWpm; });
      drawHistoryChart(wpms);
    } else {
      chartWrap.style.display = "none";
    }
  }

  function drawHistoryChart(data) {
    var canvas = document.getElementById("ttHistoryChart");
    var ctx = canvas.getContext("2d");
    var dpr = window.devicePixelRatio || 1;
    var rect = canvas.getBoundingClientRect();
    canvas.width = rect.width * dpr;
    canvas.height = rect.height * dpr;
    ctx.scale(dpr, dpr);

    var w = rect.width;
    var h = rect.height;
    var pad = { top: 10, right: 10, bottom: 25, left: 40 };
    var chartW = w - pad.left - pad.right;
    var chartH = h - pad.top - pad.bottom;

    ctx.clearRect(0, 0, w, h);

    var maxWpm = Math.max.apply(null, data) * 1.15;
    if (maxWpm === 0) maxWpm = 10;

    // Grid
    ctx.strokeStyle = "#1e1e2e";
    ctx.lineWidth = 1;
    for (var g = 0; g <= 4; g++) {
      var gy = pad.top + chartH - (chartH * g / 4);
      ctx.beginPath();
      ctx.moveTo(pad.left, gy);
      ctx.lineTo(w - pad.right, gy);
      ctx.stroke();

      ctx.fillStyle = "#8888aa";
      ctx.font = "10px JetBrains Mono, monospace";
      ctx.textAlign = "right";
      ctx.fillText(Math.round(maxWpm * g / 4), pad.left - 5, gy + 3);
    }

    // X labels
    ctx.textAlign = "center";
    for (var xi = 0; xi < data.length; xi++) {
      var xx = pad.left + (chartW * xi / Math.max(1, data.length - 1));
      ctx.fillText("#" + (xi + 1), xx, h - 5);
    }

    // Line
    ctx.beginPath();
    ctx.strokeStyle = "#00ff88";
    ctx.lineWidth = 2;
    ctx.lineJoin = "round";
    for (var di = 0; di < data.length; di++) {
      var px = pad.left + (chartW * di / Math.max(1, data.length - 1));
      var py = pad.top + chartH - (chartH * data[di] / maxWpm);
      if (di === 0) ctx.moveTo(px, py);
      else ctx.lineTo(px, py);
    }
    ctx.stroke();

    // Fill
    ctx.lineTo(pad.left + (chartW * (data.length - 1) / Math.max(1, data.length - 1)), pad.top + chartH);
    ctx.lineTo(pad.left, pad.top + chartH);
    ctx.closePath();
    ctx.fillStyle = "rgba(0, 255, 136, 0.08)";
    ctx.fill();

    // Dots
    for (var dd = 0; dd < data.length; dd++) {
      var dx = pad.left + (chartW * dd / Math.max(1, data.length - 1));
      var dy = pad.top + chartH - (chartH * data[dd] / maxWpm);
      ctx.beginPath();
      ctx.arc(dx, dy, 4, 0, Math.PI * 2);
      ctx.fillStyle = "#00ff88";
      ctx.fill();
    }
  }

  // ============ CONTROLS ============

  window.ttSetDuration = function(dur, btn) {
    if (testStarted && !testEnded) return;

    var btns = document.querySelectorAll("#ttDurationGroup .tt-ctrl-btn");
    for (var i = 0; i < btns.length; i++) btns[i].classList.remove("active");
    btn.classList.add("active");

    var customInput = document.getElementById("ttCustomDur");

    if (dur === "custom") {
      customInput.classList.add("visible");
      customInput.focus();
      duration = parseInt(customInput.value, 10) || 45;
    } else {
      customInput.classList.remove("visible");
      duration = dur;
    }
    timerEl.textContent = duration;
    timeLeft = duration;
    ttRestart();
  };

  document.getElementById("ttCustomDur").addEventListener("input", function() {
    var val = parseInt(this.value, 10);
    if (val >= 5 && val <= 300) {
      duration = val;
      timerEl.textContent = duration;
      timeLeft = duration;
      if (!testStarted) ttRestart();
    }
  });

  window.ttSetMode = function(m, btn) {
    if (testStarted && !testEnded) return;

    var btns = document.querySelectorAll("#ttModeGroup .tt-ctrl-btn");
    for (var i = 0; i < btns.length; i++) btns[i].classList.remove("active");
    btn.classList.add("active");

    mode = m;
    ttRestart();
  };

  window.ttRestart = function() {
    clearInterval(timerInterval);
    clearInterval(snapshotInterval);
    testStarted = false;
    testEnded = false;
    charIndex = 0;
    errors = 0;
    correctChars = 0;
    totalTyped = 0;
    timeLeft = duration;
    wpmSnapshots = [];

    timerEl.textContent = duration;
    timerEl.classList.remove("running", "danger");

    document.getElementById("ttLiveWpm").textContent = "0";
    document.getElementById("ttLiveAcc").textContent = "100";
    document.getElementById("ttLiveChars").textContent = "0";
    document.getElementById("ttLiveErrors").textContent = "0";
    document.getElementById("ttLiveAcc").classList.remove("warn", "bad");

    document.getElementById("ttResults").classList.remove("visible");

    inputEl.value = "";
    renderText();
    hintEl.classList.add("visible");
    inputEl.focus();
  };

  window.ttNewText = function() {
    currentText = generateText();
    ttRestart();
  };

  // ============ INIT ============

  currentText = generateText();
  renderText();
  renderHistory();

  // Focus input when clicking container or pressing any key
  document.addEventListener("keydown", function(e) {
    if (e.target === inputEl) return;
    if (e.key.length === 1 && !e.ctrlKey && !e.metaKey && !e.altKey) {
      inputEl.focus();
    }
  });
})();
</script>
