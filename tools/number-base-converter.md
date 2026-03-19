---
layout: page
title: "Free Number Base Converter — Binary, Hex, Octal & Decimal | Zovo"
description: "Convert between binary, hexadecimal, octal, and decimal number systems. Visualize bits, view IEEE 754 floating point, convert ASCII/Unicode codes, and batch convert numbers. Free online base converter."
permalink: /tools/number-base-converter/
keywords: "binary to decimal, hex to decimal, octal converter, number base converter, binary converter, hexadecimal converter, base converter, decimal to binary"
date: 2026-03-19
categories: [tools]
tags: [number-base-converter, binary, hexadecimal, octal, decimal, bit-visualization, ieee754, ascii, unicode]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --nb-primary: #6C5CE7;
    --nb-primary-dark: #5A4BD1;
    --nb-primary-light: #A29BFE;
    --nb-bg: #0a0a0f;
    --nb-surface: #12121a;
    --nb-surface-alt: #181825;
    --nb-border: #1e1e2e;
    --nb-text: #e0e0e0;
    --nb-text-muted: #8888aa;
    --nb-green: #00ff88;
    --nb-green-dark: #00cc6a;
    --nb-red: #ff4466;
    --nb-yellow: #FDCB6E;
    --nb-radius: 12px;
    --nb-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .nb-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--nb-text);
    max-width: 960px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .nb-wrapper * { box-sizing: border-box; }

  .nb-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .nb-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    margin: 0 0 16px;
    line-height: 1.2;
    color: #fff;
  }

  .nb-hero h1 span { color: var(--nb-primary); }

  .nb-hero p {
    color: var(--nb-text-muted);
    font-size: 1.05rem;
    max-width: 640px;
    margin: 0 auto;
  }

  .nb-section {
    background: var(--nb-surface);
    border: 1px solid var(--nb-border);
    border-radius: var(--nb-radius);
    padding: 24px;
    margin-bottom: 20px;
  }

  .nb-section-title {
    font-size: 1rem;
    font-weight: 600;
    color: var(--nb-primary-light);
    margin: 0 0 16px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    font-size: 0.82rem;
  }

  /* Base Converter Grid */
  .nb-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .nb-field {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .nb-field label {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--nb-text-muted);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nb-field label .nb-base-tag {
    font-size: 0.72rem;
    background: var(--nb-surface-alt);
    border: 1px solid var(--nb-border);
    padding: 2px 8px;
    border-radius: 4px;
    color: var(--nb-primary-light);
    font-family: 'JetBrains Mono', monospace;
  }

  .nb-input-row {
    display: flex;
    gap: 6px;
  }

  .nb-field input[type="text"] {
    flex: 1;
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text);
    padding: 10px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s;
  }

  .nb-field input[type="text"]:focus {
    border-color: var(--nb-primary);
  }

  .nb-copy-btn {
    background: var(--nb-surface-alt);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text-muted);
    padding: 0 12px;
    cursor: pointer;
    font-size: 0.78rem;
    font-family: 'Inter', sans-serif;
    transition: border-color 0.2s, color 0.2s;
    white-space: nowrap;
  }

  .nb-copy-btn:hover {
    border-color: var(--nb-primary);
    color: var(--nb-text);
  }

  /* Custom Base */
  .nb-custom-row {
    display: flex;
    gap: 12px;
    align-items: flex-end;
    flex-wrap: wrap;
  }

  .nb-custom-row .nb-field { flex: 1; min-width: 120px; }

  .nb-custom-row input[type="number"] {
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text);
    padding: 10px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    width: 100%;
    transition: border-color 0.2s;
  }

  .nb-custom-row input[type="number"]:focus {
    border-color: var(--nb-primary);
  }

  .nb-swap-btn {
    background: var(--nb-primary);
    color: white;
    border: none;
    border-radius: 8px;
    padding: 10px 18px;
    cursor: pointer;
    font-weight: 600;
    font-size: 0.85rem;
    font-family: 'Inter', sans-serif;
    margin-bottom: 0;
    transition: background 0.2s;
  }

  .nb-swap-btn:hover { background: var(--nb-primary-dark); }

  /* Bit Visualization */
  .nb-bit-controls {
    display: flex;
    gap: 8px;
    margin-bottom: 16px;
    flex-wrap: wrap;
  }

  .nb-bit-mode {
    background: var(--nb-surface-alt);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text-muted);
    padding: 6px 14px;
    cursor: pointer;
    font-size: 0.8rem;
    font-family: 'Inter', sans-serif;
    font-weight: 500;
    transition: border-color 0.2s, color 0.2s, background 0.2s;
  }

  .nb-bit-mode.active {
    background: var(--nb-primary);
    border-color: var(--nb-primary);
    color: white;
  }

  .nb-bits-container {
    display: flex;
    flex-wrap: wrap;
    gap: 2px;
    justify-content: center;
    margin-bottom: 12px;
  }

  .nb-bit-group {
    display: flex;
    gap: 2px;
    margin: 0 4px;
  }

  .nb-bit-btn {
    width: 32px;
    height: 36px;
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 4px;
    color: var(--nb-text-muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    cursor: pointer;
    transition: background 0.15s, color 0.15s, border-color 0.15s;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
  }

  .nb-bit-btn.active {
    background: var(--nb-primary);
    border-color: var(--nb-primary);
    color: white;
  }

  .nb-bit-btn:hover {
    border-color: var(--nb-primary-light);
  }

  .nb-bit-labels {
    display: flex;
    flex-wrap: wrap;
    gap: 2px;
    justify-content: center;
    margin-bottom: 8px;
  }

  .nb-bit-label-group {
    display: flex;
    gap: 2px;
    margin: 0 4px;
  }

  .nb-bit-label {
    width: 32px;
    text-align: center;
    font-size: 0.6rem;
    color: var(--nb-text-muted);
    font-family: 'JetBrains Mono', monospace;
  }

  .nb-twos-complement {
    background: var(--nb-surface-alt);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    padding: 12px 16px;
    font-size: 0.85rem;
    color: var(--nb-text-muted);
    margin-top: 12px;
    font-family: 'JetBrains Mono', monospace;
  }

  .nb-twos-complement span { color: var(--nb-green); }

  /* IEEE 754 */
  .nb-ieee-input {
    display: flex;
    gap: 8px;
    margin-bottom: 16px;
  }

  .nb-ieee-input input {
    flex: 1;
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text);
    padding: 10px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s;
  }

  .nb-ieee-input input:focus { border-color: var(--nb-primary); }

  .nb-ieee-result {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 8px 16px;
    font-size: 0.85rem;
  }

  .nb-ieee-label {
    color: var(--nb-text-muted);
    font-weight: 500;
  }

  .nb-ieee-value {
    font-family: 'JetBrains Mono', monospace;
    color: var(--nb-text);
    word-break: break-all;
  }

  .nb-ieee-bits {
    display: flex;
    flex-wrap: wrap;
    gap: 2px;
    margin-top: 12px;
  }

  .nb-ieee-bit {
    width: 22px;
    height: 28px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    border-radius: 3px;
    border: 1px solid transparent;
  }

  .nb-ieee-bit.sign { background: #ff446622; color: var(--nb-red); border-color: #ff446644; }
  .nb-ieee-bit.exponent { background: #6C5CE722; color: var(--nb-primary-light); border-color: #6C5CE744; }
  .nb-ieee-bit.mantissa { background: #00ff8822; color: var(--nb-green); border-color: #00ff8844; }

  .nb-ieee-legend {
    display: flex;
    gap: 16px;
    margin-top: 10px;
    font-size: 0.75rem;
  }

  .nb-ieee-legend-item {
    display: flex;
    align-items: center;
    gap: 6px;
    color: var(--nb-text-muted);
  }

  .nb-ieee-legend-dot {
    width: 10px;
    height: 10px;
    border-radius: 3px;
  }

  .nb-ieee-legend-dot.sign { background: var(--nb-red); }
  .nb-ieee-legend-dot.exponent { background: var(--nb-primary); }
  .nb-ieee-legend-dot.mantissa { background: var(--nb-green); }

  /* ASCII/Unicode */
  .nb-ascii-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .nb-ascii-result {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 6px 16px;
    font-size: 0.85rem;
    margin-top: 12px;
  }

  .nb-ascii-label {
    color: var(--nb-text-muted);
    font-weight: 500;
  }

  .nb-ascii-value {
    font-family: 'JetBrains Mono', monospace;
    color: var(--nb-green);
  }

  /* Batch Converter */
  .nb-batch-row {
    display: flex;
    gap: 12px;
    align-items: flex-end;
    margin-bottom: 12px;
    flex-wrap: wrap;
  }

  .nb-batch-row select {
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text);
    padding: 10px 14px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    outline: none;
  }

  .nb-batch-row select:focus { border-color: var(--nb-primary); }

  .nb-batch-textarea {
    width: 100%;
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text);
    padding: 12px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    resize: vertical;
    min-height: 100px;
    outline: none;
    transition: border-color 0.2s;
  }

  .nb-batch-textarea:focus { border-color: var(--nb-primary); }

  .nb-batch-output {
    background: var(--nb-bg);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    padding: 12px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--nb-green);
    min-height: 100px;
    margin-top: 12px;
    white-space: pre-wrap;
    word-break: break-all;
  }

  /* Cross Links */
  .nb-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .nb-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--nb-surface);
    border: 1px solid var(--nb-border);
    border-radius: 8px;
    color: var(--nb-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .nb-cross-link:hover {
    border-color: var(--nb-primary);
    color: var(--nb-text);
  }

  /* Content */
  .nb-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .nb-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    margin: 2.5rem 0 1rem;
  }

  .nb-content p {
    color: var(--nb-text-muted);
    margin: 0 0 1rem;
    line-height: 1.7;
    font-size: 0.95rem;
  }

  .nb-content table {
    width: 100%;
    border-collapse: collapse;
    margin: 1.5rem 0;
    font-size: 0.88rem;
  }

  .nb-content th, .nb-content td {
    padding: 10px 14px;
    text-align: left;
    border-bottom: 1px solid var(--nb-border);
  }

  .nb-content th {
    background: var(--nb-surface);
    color: var(--nb-text);
    font-weight: 600;
  }

  .nb-content td {
    color: var(--nb-text-muted);
  }

  /* FAQ */
  .nb-faq {
    max-width: 780px;
    margin: 2rem auto 0;
  }

  .nb-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    margin: 0 0 1.2rem;
  }

  .nb-faq-item {
    border-bottom: 1px solid var(--nb-border);
    padding: 1rem 0;
  }

  .nb-faq-item:last-child { border-bottom: none; }

  .nb-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--nb-text);
    margin: 0 0 8px;
  }

  .nb-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--nb-text-muted);
    line-height: 1.7;
  }

  /* Author Box */
  .nb-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--nb-surface);
    border: 1px solid var(--nb-border);
    border-radius: var(--nb-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .nb-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--nb-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .nb-author-info { flex: 1; }

  .nb-author-name {
    font-weight: 600;
    color: var(--nb-text);
    margin: 0 0 4px;
    font-size: 0.95rem;
  }

  .nb-author-bio {
    color: var(--nb-text-muted);
    font-size: 0.85rem;
    margin: 0;
    line-height: 1.5;
  }

  .nb-author-bio a {
    color: var(--nb-primary);
    text-decoration: none;
  }

  /* Footer */
  .nb-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--nb-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--nb-border);
    margin-top: 3rem;
  }

  .nb-footer a {
    color: var(--nb-primary);
    text-decoration: none;
  }

  .nb-footer a:hover { text-decoration: underline; }

  .nb-last-updated {
    text-align: center;
    color: var(--nb-text-muted);
    font-size: 0.78rem;
    margin-top: 8px;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .nb-hero h1 { font-size: 1.6rem; }
    .nb-grid { grid-template-columns: 1fr; }
    .nb-ascii-grid { grid-template-columns: 1fr; }
    .nb-custom-row { flex-direction: column; }
    .nb-author-box {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
    .nb-bit-btn { width: 26px; height: 30px; font-size: 0.75rem; }
    .nb-bit-label { width: 26px; font-size: 0.5rem; }
    .nb-ieee-bit { width: 18px; height: 24px; font-size: 0.65rem; }
  }

  @media (max-width: 480px) {
    .nb-section { padding: 16px; }
    .nb-bit-btn { width: 22px; height: 26px; font-size: 0.7rem; }
    .nb-bit-label { width: 22px; }
  }
</style>

<div class="nb-wrapper">

  <div class="nb-hero">
    <h1>Number <span>Base Converter</span></h1>
    <p>Convert between binary, octal, decimal, and hexadecimal. Visualize bits, explore IEEE 754 floats, and decode ASCII/Unicode characters.</p>
  </div>

  <!-- Main Converter -->
  <div class="nb-section">
    <div class="nb-section-title">Base Converter</div>
    <div class="nb-grid">
      <div class="nb-field">
        <label>Binary <span class="nb-base-tag">Base 2</span></label>
        <div class="nb-input-row">
          <input type="text" id="nbBin" placeholder="e.g. 11010110" oninput="nbConvert('bin')">
          <button class="nb-copy-btn" onclick="nbCopy('nbBin')">Copy</button>
        </div>
      </div>
      <div class="nb-field">
        <label>Octal <span class="nb-base-tag">Base 8</span></label>
        <div class="nb-input-row">
          <input type="text" id="nbOct" placeholder="e.g. 326" oninput="nbConvert('oct')">
          <button class="nb-copy-btn" onclick="nbCopy('nbOct')">Copy</button>
        </div>
      </div>
      <div class="nb-field">
        <label>Decimal <span class="nb-base-tag">Base 10</span></label>
        <div class="nb-input-row">
          <input type="text" id="nbDec" placeholder="e.g. 214" oninput="nbConvert('dec')">
          <button class="nb-copy-btn" onclick="nbCopy('nbDec')">Copy</button>
        </div>
      </div>
      <div class="nb-field">
        <label>Hexadecimal <span class="nb-base-tag">Base 16</span></label>
        <div class="nb-input-row">
          <input type="text" id="nbHex" placeholder="e.g. D6" oninput="nbConvert('hex')">
          <button class="nb-copy-btn" onclick="nbCopy('nbHex')">Copy</button>
        </div>
      </div>
    </div>
  </div>

  <!-- Custom Base Converter -->
  <div class="nb-section">
    <div class="nb-section-title">Custom Base Converter</div>
    <div class="nb-custom-row">
      <div class="nb-field">
        <label>Value</label>
        <input type="text" id="nbCustomVal" placeholder="Enter number" oninput="nbCustomConvert()">
      </div>
      <div class="nb-field">
        <label>From Base (2-36)</label>
        <input type="number" id="nbCustomFrom" min="2" max="36" value="10" oninput="nbCustomConvert()">
      </div>
      <div class="nb-field">
        <label>To Base (2-36)</label>
        <input type="number" id="nbCustomTo" min="2" max="36" value="16" oninput="nbCustomConvert()">
      </div>
      <button class="nb-swap-btn" onclick="nbSwapCustom()">Swap</button>
    </div>
    <div style="margin-top:12px;">
      <div class="nb-field">
        <label>Result <span id="nbCustomResultLabel" class="nb-base-tag">Base 16</span></label>
        <div class="nb-input-row">
          <input type="text" id="nbCustomResult" readonly style="color:var(--nb-green);">
          <button class="nb-copy-btn" onclick="nbCopy('nbCustomResult')">Copy</button>
        </div>
      </div>
    </div>
  </div>

  <!-- Bit Visualization -->
  <div class="nb-section">
    <div class="nb-section-title">Bit Visualization</div>
    <div class="nb-bit-controls">
      <button class="nb-bit-mode active" onclick="nbSetBitWidth(8, this)">8-bit</button>
      <button class="nb-bit-mode" onclick="nbSetBitWidth(16, this)">16-bit</button>
      <button class="nb-bit-mode" onclick="nbSetBitWidth(32, this)">32-bit</button>
    </div>
    <div id="nbBitLabels" class="nb-bit-labels"></div>
    <div id="nbBitContainer" class="nb-bits-container"></div>
    <div id="nbTwosComplement" class="nb-twos-complement" style="display:none;"></div>
  </div>

  <!-- IEEE 754 Viewer -->
  <div class="nb-section">
    <div class="nb-section-title">IEEE 754 Floating Point (32-bit)</div>
    <div class="nb-ieee-input">
      <input type="text" id="nbIeeeInput" placeholder="Enter a decimal number, e.g. -3.14" oninput="nbIeeeConvert()">
    </div>
    <div id="nbIeeeBits" class="nb-ieee-bits"></div>
    <div class="nb-ieee-legend" id="nbIeeeLegend" style="display:none;">
      <div class="nb-ieee-legend-item"><div class="nb-ieee-legend-dot sign"></div> Sign (1 bit)</div>
      <div class="nb-ieee-legend-item"><div class="nb-ieee-legend-dot exponent"></div> Exponent (8 bits)</div>
      <div class="nb-ieee-legend-item"><div class="nb-ieee-legend-dot mantissa"></div> Mantissa (23 bits)</div>
    </div>
    <div id="nbIeeeResult" class="nb-ieee-result" style="margin-top:16px;"></div>
  </div>

  <!-- ASCII/Unicode Converter -->
  <div class="nb-section">
    <div class="nb-section-title">ASCII / Unicode Converter</div>
    <div class="nb-ascii-grid">
      <div>
        <div class="nb-field">
          <label>Character</label>
          <input type="text" id="nbAsciiChar" placeholder="Type a character" maxlength="2" oninput="nbCharToCode()">
        </div>
        <div id="nbCharResult" class="nb-ascii-result"></div>
      </div>
      <div>
        <div class="nb-field">
          <label>Code Point (decimal)</label>
          <div class="nb-input-row">
            <input type="text" id="nbAsciiCode" placeholder="e.g. 65" oninput="nbCodeToChar()">
          </div>
        </div>
        <div id="nbCodeResult" class="nb-ascii-result"></div>
      </div>
    </div>
  </div>

  <!-- Batch Converter -->
  <div class="nb-section">
    <div class="nb-section-title">Batch Converter</div>
    <div class="nb-batch-row">
      <div class="nb-field">
        <label>From</label>
        <select id="nbBatchFrom">
          <option value="2">Binary (2)</option>
          <option value="8">Octal (8)</option>
          <option value="10" selected>Decimal (10)</option>
          <option value="16">Hexadecimal (16)</option>
        </select>
      </div>
      <div class="nb-field">
        <label>To</label>
        <select id="nbBatchTo">
          <option value="2">Binary (2)</option>
          <option value="8">Octal (8)</option>
          <option value="10">Decimal (10)</option>
          <option value="16" selected>Hexadecimal (16)</option>
        </select>
      </div>
      <button class="nb-swap-btn" onclick="nbBatchConvert()">Convert</button>
      <button class="nb-copy-btn" onclick="nbCopy('nbBatchOutput')" style="padding:10px 18px;">Copy Result</button>
    </div>
    <textarea class="nb-batch-textarea" id="nbBatchInput" placeholder="Enter numbers, one per line"></textarea>
    <div class="nb-batch-output" id="nbBatchOutput">Results will appear here</div>
  </div>

  <!-- Cross Links -->
  <div class="nb-cross-links">
    <a href="/tools/hash-generator/" class="nb-cross-link">Hash Generator</a>
    <a href="/tools/unit-converter/" class="nb-cross-link">Unit Converter</a>
    <a href="/tools/base64/" class="nb-cross-link">Base64 Encoder/Decoder</a>
  </div>

  <!-- SEO Content -->
  <div class="nb-content">

<h2>What Are Number Bases</h2>

<p>A number base (or radix) is the total count of unique digits a numbering system uses to represent values. The decimal system has ten digits (0 through 9), so its base is 10. Binary uses two digits (0 and 1), octal uses eight (0 through 7), and hexadecimal uses sixteen (0 through 9 plus A through F). Each position in a number represents a power of the base, starting from the rightmost position at power zero and increasing leftward.</p>

<p>Humans settled on base 10 likely because we have ten fingers. Computers settled on base 2 because transistors operate in two states: on and off, 1 and 0. Every piece of data a computer processes, from text to video to encrypted network packets, reduces to a sequence of binary digits at the hardware level.</p>

<p>Other bases exist for practical reasons. Base 8 (octal) and base 16 (hexadecimal) are compact representations of binary. Each octal digit maps to exactly three binary digits, and each hex digit maps to exactly four. This makes them convenient shorthands for programmers who need to inspect or specify binary values without writing out long strings of ones and zeros.</p>

<h2>Binary Number System</h2>

<p>Binary is the foundation of all digital computing. A single binary digit is called a bit. Eight bits form a byte, which can represent 256 distinct values (0 to 255 unsigned, or -128 to 127 signed). Groups of bytes represent larger data structures: a 32-bit integer stores values up to roughly 4.3 billion, and a 64-bit integer covers a range large enough for most practical counting purposes.</p>

<p>Reading binary by hand follows a consistent pattern. Each position doubles in value from right to left: 1, 2, 4, 8, 16, 32, 64, 128. To convert binary 11010110 to decimal, you add the position values where a 1 appears: 128 + 64 + 16 + 4 + 2 = 214. The tool above does this automatically for any input.</p>

<p>Binary arithmetic follows the same rules as decimal arithmetic, but carries happen more often. 1 + 1 = 10 in binary (that is, 0 carry 1), the same way 5 + 5 = 10 in decimal. Understanding these mechanics helps when debugging low-level code, working with bitwise operations, or analyzing network protocol headers.</p>

<h2>Hexadecimal in Computing</h2>

<p>Hexadecimal (hex) is the preferred human-readable format for binary data in computing. Memory addresses, color codes, MAC addresses, cryptographic hashes, and error codes are all conventionally written in hex. A CSS color like #6C5CE7 encodes three bytes: 6C for red (108 decimal), 5C for green (92 decimal), and E7 for blue (231 decimal).</p>

<p>One hex digit represents exactly four bits (a nibble). Two hex digits represent one byte. This direct mapping means you can mentally convert between hex and binary without calculation: hex D is binary 1101, hex 6 is binary 0110, so D6 is 11010110. The bit visualization section above shows this relationship interactively.</p>

<p>Hex digits use letters A through F for values 10 through 15. Both uppercase and lowercase are valid; the convention varies by context. C and C++ use the 0x prefix to denote hex literals (0xFF), Python uses the same convention, and HTML/CSS use the # prefix. This tool accepts hex input with or without any prefix.</p>

<h2>How Base Conversion Works</h2>

<p>Converting from any base to decimal uses the positional value method. Each digit is multiplied by the base raised to the power of its position (counting from zero on the right), and the products are summed. For hex 1A3: (1 x 16^2) + (10 x 16^1) + (3 x 16^0) = 256 + 160 + 3 = 419 in decimal.</p>

<p>Converting from decimal to another base uses repeated division. Divide the decimal number by the target base, record the remainder, and repeat with the quotient until it reaches zero. The remainders, read bottom to top, form the result. For 214 to binary: 214/2 = 107 r0, 107/2 = 53 r1, 53/2 = 26 r1, 26/2 = 13 r0, 13/2 = 6 r1, 6/2 = 3 r0, 3/2 = 1 r1, 1/2 = 0 r1. Reading remainders upward gives 11010110.</p>

<p>The custom base section of this tool lets you convert between any pair of bases from 2 to 36. Base 36 uses all ten digits plus all 26 letters of the English alphabet. While bases beyond 16 are uncommon, they appear in certain URL shorteners, hash functions, and data encoding schemes.</p>

<p>Negative numbers in binary use a representation called two's complement. The leftmost bit indicates the sign (0 for positive, 1 for negative). To find the two's complement of a number, invert all bits and add 1. The bit visualization section shows the two's complement interpretation when the high bit is set.</p>

<h2>IEEE 754 Floating Point</h2>

<p>Computers represent fractional numbers using the IEEE 754 standard. A 32-bit float divides its bits into three fields: one sign bit, eight exponent bits, and twenty-three mantissa (significand) bits. The sign bit determines positive (0) or negative (1). The exponent uses a biased representation where the stored value minus 127 gives the actual exponent. The mantissa represents the fractional part with an implied leading 1.</p>

<p>This encoding has practical consequences. Not all decimal fractions have exact binary representations. The number 0.1, for example, becomes a repeating binary fraction, similar to how 1/3 becomes 0.333... in decimal. This is why floating-point arithmetic sometimes produces results like 0.1 + 0.2 = 0.30000000000000004. The IEEE 754 viewer above lets you enter any decimal and inspect exactly how the computer stores it.</p>

  </div>

  <!-- FAQ -->
  <div class="nb-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="nb-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I convert binary to decimal manually?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Write out the binary number and assign powers of 2 to each position from right to left, starting at 2^0. Multiply each bit by its positional value and add the results. For example, binary 1011 = (1 x 8) + (0 x 4) + (1 x 2) + (1 x 1) = 11 in decimal.</p>
      </div>
    </div>

    <div class="nb-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between signed and unsigned binary?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Unsigned binary treats all bits as magnitude, giving a range of 0 to 2^n - 1 for n bits. Signed binary (using two's complement) reserves the leftmost bit as a sign indicator, giving a range of -2^(n-1) to 2^(n-1) - 1. An 8-bit unsigned byte holds 0 to 255, while a signed byte holds -128 to 127.</p>
      </div>
    </div>

    <div class="nb-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why do programmers use hexadecimal instead of binary?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Hex is more compact. A single byte requires 8 binary digits but only 2 hex digits. Since each hex digit maps to exactly 4 bits, conversion between hex and binary is straightforward. Hex is therefore the standard for displaying memory addresses, color codes, and raw data dumps.</p>
      </div>
    </div>

    <div class="nb-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is IEEE 754 and why does 0.1 + 0.2 not equal 0.3?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">IEEE 754 is the standard for representing floating-point numbers in binary. Some decimal fractions, like 0.1, cannot be represented exactly in binary (similar to how 1/3 cannot be written exactly in decimal). The small rounding errors accumulate, which is why 0.1 + 0.2 produces 0.30000000000000004 in most programming languages.</p>
      </div>
    </div>

    <div class="nb-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data sent to a server when I use this tool?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All conversions happen entirely in your browser using JavaScript. No data is transmitted, stored, or logged. You can verify this by monitoring the Network tab in your browser's developer tools while using the tool.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="nb-author-box">
    <div class="nb-author-avatar">ML</div>
    <div class="nb-author-info">
      <p class="nb-author-name">Michael Lip</p>
      <p class="nb-author-bio">Michael builds free tools and writes guides at <a href="https://zovo.one">zovo.one</a>. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <p class="nb-last-updated">Last updated: March 19, 2026</p>

  <footer class="nb-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Number Base Converter",
      "description": "Convert between binary, hexadecimal, octal, and decimal number systems. Visualize bits, view IEEE 754 floating point, and convert ASCII/Unicode codes.",
      "url": "https://theluckystrike.github.io/tools/number-base-converter/",
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
        {"@type": "ListItem", "position": 3, "name": "Number Base Converter", "item": "https://theluckystrike.github.io/tools/number-base-converter/"}
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
          "name": "How do I convert binary to decimal manually?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Write out the binary number and assign powers of 2 to each position from right to left, starting at 2^0. Multiply each bit by its positional value and add the results."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between signed and unsigned binary?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Unsigned binary treats all bits as magnitude (0 to 2^n - 1). Signed binary uses two's complement, reserving the leftmost bit as a sign indicator (-2^(n-1) to 2^(n-1) - 1)."
          }
        },
        {
          "@type": "Question",
          "name": "Why do programmers use hexadecimal instead of binary?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Hex is more compact. A byte requires 8 binary digits but only 2 hex digits, and each hex digit maps to exactly 4 bits, making conversion straightforward."
          }
        },
        {
          "@type": "Question",
          "name": "What is IEEE 754 and why does 0.1 + 0.2 not equal 0.3?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "IEEE 754 is the standard for binary floating-point. Some decimal fractions like 0.1 cannot be represented exactly in binary, causing small rounding errors that accumulate."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data sent to a server when I use this tool?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All conversions happen entirely in your browser using JavaScript. No data is transmitted, stored, or logged."
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

  var currentBitWidth = 8;
  var currentDecValue = 0;

  // =============================================
  // Main Base Converter (synchronized fields)
  // =============================================
  window.nbConvert = function(source) {
    var val;
    var dec;

    if (source === "bin") {
      val = document.getElementById("nbBin").value.replace(/\s/g, "");
      if (!val) { clearFields("bin"); return; }
      if (!/^[01]+$/.test(val)) return;
      dec = parseInt(val, 2);
    } else if (source === "oct") {
      val = document.getElementById("nbOct").value.replace(/\s/g, "");
      if (!val) { clearFields("oct"); return; }
      if (!/^[0-7]+$/.test(val)) return;
      dec = parseInt(val, 8);
    } else if (source === "dec") {
      val = document.getElementById("nbDec").value.replace(/\s/g, "");
      if (!val) { clearFields("dec"); return; }
      if (!/^-?\d+$/.test(val)) return;
      dec = parseInt(val, 10);
    } else if (source === "hex") {
      val = document.getElementById("nbHex").value.replace(/\s/g, "").replace(/^0x/i, "");
      if (!val) { clearFields("hex"); return; }
      if (!/^[0-9a-fA-F]+$/.test(val)) return;
      dec = parseInt(val, 16);
    }

    if (isNaN(dec)) return;

    currentDecValue = dec;

    if (source !== "bin") document.getElementById("nbBin").value = (dec >>> 0).toString(2);
    if (source !== "oct") document.getElementById("nbOct").value = (dec >>> 0).toString(8);
    if (source !== "dec") document.getElementById("nbDec").value = dec.toString(10);
    if (source !== "hex") document.getElementById("nbHex").value = (dec >>> 0).toString(16).toUpperCase();

    // Handle negative for binary display
    if (dec < 0) {
      var unsigned = dec >>> 0;
      if (source !== "bin") document.getElementById("nbBin").value = unsigned.toString(2);
      if (source !== "oct") document.getElementById("nbOct").value = unsigned.toString(8);
      if (source !== "hex") document.getElementById("nbHex").value = unsigned.toString(16).toUpperCase();
    }

    updateBitVisualization(dec);
  };

  function clearFields(except) {
    if (except !== "bin") document.getElementById("nbBin").value = "";
    if (except !== "oct") document.getElementById("nbOct").value = "";
    if (except !== "dec") document.getElementById("nbDec").value = "";
    if (except !== "hex") document.getElementById("nbHex").value = "";
    currentDecValue = 0;
    updateBitVisualization(0);
  }

  // =============================================
  // Custom Base Converter
  // =============================================
  window.nbCustomConvert = function() {
    var val = document.getElementById("nbCustomVal").value.trim();
    var fromBase = parseInt(document.getElementById("nbCustomFrom").value);
    var toBase = parseInt(document.getElementById("nbCustomTo").value);
    var resultEl = document.getElementById("nbCustomResult");
    var labelEl = document.getElementById("nbCustomResultLabel");

    labelEl.textContent = "Base " + (toBase || "?");

    if (!val || isNaN(fromBase) || isNaN(toBase) || fromBase < 2 || fromBase > 36 || toBase < 2 || toBase > 36) {
      resultEl.value = "";
      return;
    }

    try {
      var dec = parseInt(val, fromBase);
      if (isNaN(dec)) { resultEl.value = "Invalid"; return; }
      resultEl.value = dec.toString(toBase).toUpperCase();
    } catch (e) {
      resultEl.value = "Error";
    }
  };

  window.nbSwapCustom = function() {
    var fromEl = document.getElementById("nbCustomFrom");
    var toEl = document.getElementById("nbCustomTo");
    var tmp = fromEl.value;
    fromEl.value = toEl.value;
    toEl.value = tmp;
    nbCustomConvert();
  };

  // =============================================
  // Bit Visualization
  // =============================================
  window.nbSetBitWidth = function(width, btn) {
    currentBitWidth = width;
    var buttons = document.querySelectorAll(".nb-bit-mode");
    for (var i = 0; i < buttons.length; i++) buttons[i].classList.remove("active");
    btn.classList.add("active");
    updateBitVisualization(currentDecValue);
  };

  function updateBitVisualization(dec) {
    var container = document.getElementById("nbBitContainer");
    var labelsContainer = document.getElementById("nbBitLabels");
    var tcEl = document.getElementById("nbTwosComplement");
    var width = currentBitWidth;

    // Clamp to bit width using unsigned representation
    var mask;
    if (width === 32) {
      mask = 0xFFFFFFFF;
    } else {
      mask = (1 << width) - 1;
    }
    var unsigned = dec & mask;
    if (width === 32) unsigned = dec >>> 0;

    var bits = [];
    for (var i = width - 1; i >= 0; i--) {
      bits.push((unsigned >>> i) & 1);
    }

    // Build bit buttons
    var html = "";
    var labelHtml = "";
    for (var i = 0; i < bits.length; i++) {
      if (i > 0 && i % 4 === 0) {
        html += '</div><div class="nb-bit-group">';
        labelHtml += '</div><div class="nb-bit-label-group">';
      }
      if (i === 0) {
        html += '<div class="nb-bit-group">';
        labelHtml += '<div class="nb-bit-label-group">';
      }
      html += '<button class="nb-bit-btn' + (bits[i] ? ' active' : '') + '" data-pos="' + (width - 1 - i) + '" onclick="nbToggleBit(' + (width - 1 - i) + ')">' + bits[i] + '</button>';
      labelHtml += '<div class="nb-bit-label">' + (width - 1 - i) + '</div>';
    }
    html += '</div>';
    labelHtml += '</div>';

    labelsContainer.innerHTML = labelHtml;
    container.innerHTML = html;

    // Two's complement display
    var signBit = bits[0];
    if (signBit === 1) {
      var signedVal;
      if (width === 8) signedVal = unsigned > 127 ? unsigned - 256 : unsigned;
      else if (width === 16) signedVal = unsigned > 32767 ? unsigned - 65536 : unsigned;
      else signedVal = dec | 0;

      tcEl.style.display = "block";
      tcEl.innerHTML = "Two's complement (signed): <span>" + signedVal + "</span> | Unsigned: <span>" + unsigned + "</span>";
    } else {
      if (unsigned !== 0) {
        tcEl.style.display = "block";
        tcEl.innerHTML = "Unsigned: <span>" + unsigned + "</span> | Signed: <span>" + unsigned + "</span> (positive)";
      } else {
        tcEl.style.display = "none";
      }
    }
  }

  window.nbToggleBit = function(pos) {
    var mask;
    if (currentBitWidth === 32) {
      mask = 0xFFFFFFFF;
    } else {
      mask = (1 << currentBitWidth) - 1;
    }
    var unsigned = currentDecValue & mask;
    if (currentBitWidth === 32) unsigned = currentDecValue >>> 0;

    // Toggle the bit
    unsigned ^= (1 << pos);
    if (currentBitWidth === 32) unsigned = unsigned >>> 0;

    currentDecValue = unsigned;

    document.getElementById("nbBin").value = unsigned.toString(2);
    document.getElementById("nbOct").value = unsigned.toString(8);
    document.getElementById("nbDec").value = unsigned.toString(10);
    document.getElementById("nbHex").value = unsigned.toString(16).toUpperCase();

    updateBitVisualization(unsigned);
  };

  // =============================================
  // IEEE 754 Viewer
  // =============================================
  window.nbIeeeConvert = function() {
    var input = document.getElementById("nbIeeeInput").value.trim();
    var bitsEl = document.getElementById("nbIeeeBits");
    var resultEl = document.getElementById("nbIeeeResult");
    var legendEl = document.getElementById("nbIeeeLegend");

    if (!input) {
      bitsEl.innerHTML = "";
      resultEl.innerHTML = "";
      legendEl.style.display = "none";
      return;
    }

    var num = parseFloat(input);
    if (isNaN(num)) {
      resultEl.innerHTML = '<span class="nb-ieee-label">Error</span><span class="nb-ieee-value">Invalid number</span>';
      bitsEl.innerHTML = "";
      legendEl.style.display = "none";
      return;
    }

    // Use Float32Array to get IEEE 754 bits
    var f32 = new Float32Array(1);
    f32[0] = num;
    var u32 = new Uint32Array(f32.buffer);
    var raw = u32[0];

    var sign = (raw >>> 31) & 1;
    var exponent = (raw >>> 23) & 0xFF;
    var mantissa = raw & 0x7FFFFF;

    // Build bit visualization
    var bitStr = "";
    for (var i = 31; i >= 0; i--) {
      bitStr += ((raw >>> i) & 1).toString();
    }

    var html = "";
    for (var i = 0; i < 32; i++) {
      var cls = "nb-ieee-bit ";
      if (i === 0) cls += "sign";
      else if (i <= 8) cls += "exponent";
      else cls += "mantissa";
      html += '<div class="' + cls + '">' + bitStr[i] + '</div>';
    }
    bitsEl.innerHTML = html;
    legendEl.style.display = "flex";

    // Build result grid
    var biasedExp = exponent - 127;
    var mantissaBin = mantissa.toString(2);
    while (mantissaBin.length < 23) mantissaBin = "0" + mantissaBin;

    var hexStr = raw.toString(16).toUpperCase();
    while (hexStr.length < 8) hexStr = "0" + hexStr;

    resultEl.innerHTML =
      '<span class="nb-ieee-label">Sign</span><span class="nb-ieee-value">' + sign + ' (' + (sign ? 'negative' : 'positive') + ')</span>' +
      '<span class="nb-ieee-label">Exponent</span><span class="nb-ieee-value">' + exponent + ' (biased) = ' + biasedExp + ' (actual)</span>' +
      '<span class="nb-ieee-label">Mantissa</span><span class="nb-ieee-value">1.' + mantissaBin + '</span>' +
      '<span class="nb-ieee-label">Hex</span><span class="nb-ieee-value">0x' + hexStr + '</span>' +
      '<span class="nb-ieee-label">Stored value</span><span class="nb-ieee-value">' + f32[0] + '</span>';
  };

  // =============================================
  // ASCII / Unicode Converter
  // =============================================
  window.nbCharToCode = function() {
    var ch = document.getElementById("nbAsciiChar").value;
    var resultEl = document.getElementById("nbCharResult");

    if (!ch) { resultEl.innerHTML = ""; return; }

    var code = ch.codePointAt(0);
    var decVal = code;
    var hexVal = code.toString(16).toUpperCase();
    var octVal = code.toString(8);
    var binVal = code.toString(2);

    resultEl.innerHTML =
      '<span class="nb-ascii-label">Decimal</span><span class="nb-ascii-value">' + decVal + '</span>' +
      '<span class="nb-ascii-label">Hex</span><span class="nb-ascii-value">0x' + hexVal + '</span>' +
      '<span class="nb-ascii-label">Octal</span><span class="nb-ascii-value">' + octVal + '</span>' +
      '<span class="nb-ascii-label">Binary</span><span class="nb-ascii-value">' + binVal + '</span>' +
      '<span class="nb-ascii-label">Unicode</span><span class="nb-ascii-value">U+' + hexVal.padStart(4, '0') + '</span>';
  };

  window.nbCodeToChar = function() {
    var input = document.getElementById("nbAsciiCode").value.trim();
    var resultEl = document.getElementById("nbCodeResult");

    if (!input) { resultEl.innerHTML = ""; return; }

    var code = parseInt(input, 10);
    if (isNaN(code) || code < 0 || code > 0x10FFFF) {
      resultEl.innerHTML = '<span class="nb-ascii-label">Error</span><span class="nb-ascii-value">Invalid code point</span>';
      return;
    }

    var ch;
    try {
      ch = String.fromCodePoint(code);
    } catch (e) {
      resultEl.innerHTML = '<span class="nb-ascii-label">Error</span><span class="nb-ascii-value">Invalid code point</span>';
      return;
    }

    var hexVal = code.toString(16).toUpperCase();

    resultEl.innerHTML =
      '<span class="nb-ascii-label">Character</span><span class="nb-ascii-value" style="font-size:1.5rem;">' + escapeHtml(ch) + '</span>' +
      '<span class="nb-ascii-label">Hex</span><span class="nb-ascii-value">0x' + hexVal + '</span>' +
      '<span class="nb-ascii-label">Binary</span><span class="nb-ascii-value">' + code.toString(2) + '</span>' +
      '<span class="nb-ascii-label">Octal</span><span class="nb-ascii-value">' + code.toString(8) + '</span>' +
      '<span class="nb-ascii-label">Unicode</span><span class="nb-ascii-value">U+' + hexVal.padStart(4, '0') + '</span>';
  };

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.textContent = str;
    return div.innerHTML;
  }

  // =============================================
  // Batch Converter
  // =============================================
  window.nbBatchConvert = function() {
    var input = document.getElementById("nbBatchInput").value.trim();
    var fromBase = parseInt(document.getElementById("nbBatchFrom").value);
    var toBase = parseInt(document.getElementById("nbBatchTo").value);
    var outputEl = document.getElementById("nbBatchOutput");

    if (!input) { outputEl.textContent = "Enter numbers above, one per line"; return; }

    var lines = input.split(/\n/);
    var results = [];

    for (var i = 0; i < lines.length; i++) {
      var line = lines[i].trim();
      if (!line) { results.push(""); continue; }

      // Strip common prefixes
      var clean = line.replace(/^0x/i, "").replace(/^0b/i, "").replace(/^0o/i, "");

      try {
        var dec = parseInt(clean, fromBase);
        if (isNaN(dec)) {
          results.push(line + " -> [invalid]");
        } else {
          results.push(line + " -> " + dec.toString(toBase).toUpperCase());
        }
      } catch (e) {
        results.push(line + " -> [error]");
      }
    }

    outputEl.textContent = results.join("\n");
  };

  // =============================================
  // Copy helper
  // =============================================
  window.nbCopy = function(id) {
    var el = document.getElementById(id);
    var text = el.value !== undefined ? el.value : el.textContent;
    if (!text) return;

    navigator.clipboard.writeText(text).then(function() {
      var btn = el.closest ? el.closest(".nb-input-row") : el.parentElement;
      if (btn) {
        var copyBtn = btn.querySelector(".nb-copy-btn");
        if (!copyBtn) {
          // For batch output, find the copy button nearby
          copyBtn = document.querySelector('[onclick="nbCopy(\'' + id + '\')"]');
        }
        if (copyBtn) {
          var orig = copyBtn.textContent;
          copyBtn.textContent = "Copied";
          copyBtn.style.borderColor = "var(--nb-green)";
          copyBtn.style.color = "var(--nb-green)";
          setTimeout(function() {
            copyBtn.textContent = orig;
            copyBtn.style.borderColor = "";
            copyBtn.style.color = "";
          }, 1500);
        }
      }
    });
  };

  // =============================================
  // Initialize
  // =============================================
  updateBitVisualization(0);

})();
</script>
