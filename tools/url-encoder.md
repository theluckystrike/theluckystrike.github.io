---
layout: page
title: "URL Encoder Decoder - Free Online Tool | Zovo"
description: "Free URL encoder decoder online. Encode special characters for URLs, decode percent-encoded strings. Handles UTF-8, query params, and full URLs. Browser-only."
permalink: /tools/url-encoder/
keywords: "url encoder, url decoder, url encode online, url decode online, percent encoding, urlencode, urldecode, encode url characters"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [url encoder, url decoder, percent encoding, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --ue-primary: #6C5CE7;
    --ue-primary-dark: #5A4BD1;
    --ue-primary-light: #A29BFE;
    --ue-bg: #F8F9FE;
    --ue-surface: #FFFFFF;
    --ue-text: #2D3436;
    --ue-text-muted: #636E72;
    --ue-border: #DFE6E9;
    --ue-success: #00B894;
    --ue-error: #D63031;
    --ue-radius: 12px;
  }

  .ue-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ue-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .ue-wrapper * {
    box-sizing: border-box;
  }

  .ue-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .ue-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ue-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .ue-hero h1 span {
    color: var(--ue-primary);
  }

  .ue-intro {
    font-size: 1.05rem;
    color: var(--ue-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Mode Tabs */
  .ue-modes {
    display: flex;
    gap: 0;
    margin-bottom: 20px;
    border: 1px solid var(--ue-border);
    border-radius: 10px;
    overflow: hidden;
    max-width: 540px;
    margin-left: auto;
    margin-right: auto;
  }

  .ue-mode-btn {
    flex: 1;
    padding: 10px 20px;
    border: none;
    background: var(--ue-bg);
    color: var(--ue-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .ue-mode-btn:not(:last-child) {
    border-right: 1px solid var(--ue-border);
  }

  .ue-mode-btn.active {
    background: var(--ue-primary);
    color: #fff;
  }

  .ue-mode-btn:hover:not(.active) {
    background: #EEF0FB;
  }

  /* Toolbar */
  .ue-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .ue-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .ue-btn-primary {
    background: var(--ue-primary);
    color: #fff;
  }

  .ue-btn-primary:hover {
    background: var(--ue-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3);
  }

  .ue-btn-secondary {
    background: var(--ue-bg);
    color: var(--ue-text);
    border: 1px solid var(--ue-border);
  }

  .ue-btn-secondary:hover {
    background: #EEF0FB;
    border-color: var(--ue-primary-light);
  }

  .ue-btn.copied {
    background: var(--ue-success);
    color: #fff;
  }

  .ue-toolbar-spacer {
    flex: 1;
  }

  .ue-link-btn {
    background: none;
    border: none;
    color: var(--ue-primary);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .ue-link-btn:hover {
    color: var(--ue-primary-dark);
  }

  /* Editor Layout */
  .ue-editor {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .ue-panel {
    background: var(--ue-surface);
    border: 1px solid var(--ue-border);
    border-radius: var(--ue-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .ue-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--ue-bg);
    border-bottom: 1px solid var(--ue-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--ue-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .ue-panel-header span {
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .ue-input-area {
    width: 100%;
    min-height: 300px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    resize: vertical;
    color: var(--ue-text);
    background: var(--ue-surface);
    outline: none;
    word-break: break-all;
  }

  .ue-input-area::placeholder {
    color: #B2BEC3;
    word-break: normal;
  }

  /* URL breakdown panel */
  .ue-breakdown {
    display: none;
    background: var(--ue-surface);
    border: 1px solid var(--ue-border);
    border-radius: var(--ue-radius);
    padding: 16px 20px;
    margin-bottom: 16px;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .ue-breakdown.visible {
    display: block;
  }

  .ue-breakdown h3 {
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--ue-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin: 0 0 12px;
  }

  .ue-breakdown-row {
    display: flex;
    align-items: baseline;
    gap: 12px;
    padding: 6px 0;
    font-size: 0.85rem;
    border-bottom: 1px solid #F0F0F5;
  }

  .ue-breakdown-row:last-child {
    border-bottom: none;
  }

  .ue-breakdown-label {
    min-width: 90px;
    font-weight: 600;
    color: var(--ue-text);
  }

  .ue-breakdown-value {
    color: var(--ue-text-muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    word-break: break-all;
  }

  .ue-breakdown-value.ue-highlight {
    color: var(--ue-primary);
  }

  /* Status Bar */
  .ue-status {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 24px;
  }

  .ue-status-msg {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.875rem;
    font-weight: 500;
    padding: 6px 14px;
    border-radius: 20px;
  }

  .ue-status-success {
    background: rgba(0, 184, 148, 0.1);
    color: #00B894;
  }

  .ue-status-error {
    background: rgba(214, 48, 49, 0.1);
    color: #D63031;
  }

  .ue-status-empty {
    background: var(--ue-bg);
    color: var(--ue-text-muted);
  }

  .ue-stats {
    display: flex;
    gap: 16px;
    font-size: 0.825rem;
    color: var(--ue-text-muted);
  }

  .ue-stat {
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .ue-stat strong {
    color: var(--ue-text);
    font-weight: 600;
  }

  /* Meta footer */
  .ue-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--ue-text-muted);
    border-top: 1px solid var(--ue-border);
    margin-bottom: 40px;
  }

  /* Content section */
  .ue-content {
    margin-top: 48px;
    max-width: 800px;
  }

  .ue-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--ue-text);
  }

  .ue-content p {
    color: var(--ue-text-muted);
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .ue-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 10px;
    color: var(--ue-text);
  }

  .ue-content ul {
    color: var(--ue-text-muted);
    padding-left: 24px;
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .ue-content code {
    background: var(--ue-bg);
    padding: 2px 6px;
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85em;
    color: var(--ue-primary);
  }

  /* Char reference table */
  .ue-ref-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.85rem;
    margin: 16px 0;
  }

  .ue-ref-table th {
    text-align: left;
    padding: 8px 12px;
    background: var(--ue-bg);
    font-weight: 600;
    color: var(--ue-text);
    border-bottom: 1px solid var(--ue-border);
  }

  .ue-ref-table td {
    padding: 8px 12px;
    border-bottom: 1px solid #F0F0F5;
    color: var(--ue-text-muted);
  }

  .ue-ref-table td:first-child {
    font-family: 'JetBrains Mono', monospace;
    color: var(--ue-primary);
  }

  .ue-ref-table td:nth-child(2) {
    font-family: 'JetBrains Mono', monospace;
  }

  /* FAQ Section */
  .ue-faq {
    max-width: 820px;
    margin: 48px auto 60px;
  }

  .ue-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--ue-text);
  }

  .ue-faq-item {
    border: 1px solid var(--ue-border);
    border-radius: var(--ue-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--ue-surface);
    box-shadow: 0 1px 4px rgba(108, 92, 231, 0.04);
  }

  .ue-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--ue-text);
  }

  .ue-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--ue-text-muted);
    line-height: 1.7;
  }

  /* Mobile responsive */
  @media (max-width: 768px) {
    .ue-hero h1 {
      font-size: 1.6rem;
    }

    .ue-editor {
      grid-template-columns: 1fr;
    }

    .ue-input-area {
      min-height: 200px;
    }

    .ue-toolbar {
      gap: 6px;
    }

    .ue-btn {
      padding: 7px 12px;
      font-size: 0.8rem;
    }

    .ue-stats {
      gap: 10px;
      flex-wrap: wrap;
    }

    .ue-modes {
      max-width: 100%;
    }

    .ue-breakdown-row {
      flex-direction: column;
      gap: 2px;
    }
  }
</style>

<div class="ue-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="URL Encoder Decoder">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="ue-hero">
    <h1><span>URL Encoder</span> & Decoder</h1>
    <p class="ue-intro">Encode special characters for safe use in URLs or decode percent-encoded strings back to readable text. Handles UTF-8 characters, query parameters, and full URLs. All processing happens in your browser.</p>
  </div>

  <!-- Mode Tabs -->
  <div class="ue-modes">
    <button class="ue-mode-btn active" id="ueModeEncode" onclick="ueSetMode('encode')">Encode</button>
    <button class="ue-mode-btn" id="ueModeDecode" onclick="ueSetMode('decode')">Decode</button>
    <button class="ue-mode-btn" id="ueModeComponent" onclick="ueSetMode('component')">Component</button>
    <button class="ue-mode-btn" id="ueModeParse" onclick="ueSetMode('parse')">Parse URL</button>
  </div>

  <!-- Toolbar -->
  <div class="ue-toolbar">
    <button class="ue-btn ue-btn-primary" onclick="ueConvert()" id="ueConvertBtn">&#9654; Encode</button>
    <button class="ue-btn ue-btn-secondary" onclick="ueCopy()" id="ueCopyBtn">&#128203; <span id="ueCopyLabel">Copy</span></button>
    <div class="ue-toolbar-spacer"></div>
    <button class="ue-link-btn" onclick="ueLoadSample()" title="Load example URL">Load sample</button>
    <button class="ue-btn ue-btn-secondary" onclick="ueSwap()" id="ueSwapBtn" title="Swap input and output">&#8644; Swap</button>
    <button class="ue-btn ue-btn-secondary" onclick="ueClear()" title="Clear all">&#10005; Clear</button>
  </div>

  <!-- Editor panels -->
  <div class="ue-editor">
    <div class="ue-panel">
      <div class="ue-panel-header">
        <span id="ueInputLabel">&#9998; Text Input</span>
        <span id="ueInputSize">0 bytes</span>
      </div>
      <textarea id="ueInput" class="ue-input-area" placeholder="Type or paste text to URL-encode..." spellcheck="false"></textarea>
    </div>
    <div class="ue-panel">
      <div class="ue-panel-header">
        <span id="ueOutputLabel">&#10004; Encoded Output</span>
        <span id="ueOutputSize">0 bytes</span>
      </div>
      <textarea id="ueOutput" class="ue-input-area" readonly placeholder="Encoded result will appear here..." spellcheck="false" style="background:#FAFBFE;"></textarea>
    </div>
  </div>

  <!-- URL breakdown panel (for Parse URL mode) -->
  <div class="ue-breakdown" id="ueBreakdown">
    <h3>URL Components</h3>
    <div id="ueBreakdownContent"></div>
  </div>

  <!-- Status & Stats -->
  <div class="ue-status">
    <div id="ueStatusMsg" class="ue-status-msg ue-status-empty">Enter text and click Encode</div>
    <div class="ue-stats">
      <span class="ue-stat">Input: <strong id="ueStatInput">0 chars</strong></span>
      <span class="ue-stat">Output: <strong id="ueStatOutput">0 chars</strong></span>
      <span class="ue-stat">Encoded: <strong id="ueStatEncoded">0 chars</strong></span>
    </div>
  </div>

  <div class="ue-meta">
    <span>Processing happens entirely in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO content -->
  <div class="ue-content">
    <h2>How URL Encoding Works</h2>
    <p>URL encoding (percent encoding) replaces unsafe characters in a URL with a percent sign followed by their hexadecimal byte values. For example, a space becomes <code>%20</code>, an ampersand becomes <code>%26</code>, and a forward slash becomes <code>%2F</code>. This ensures that special characters do not break the URL structure or get misinterpreted by web servers and browsers.</p>

    <h3>Encode vs. encodeURIComponent</h3>
    <p>JavaScript provides two functions for URL encoding. <code>encodeURI()</code> encodes a full URL but preserves characters that are valid in URLs, such as <code>:</code>, <code>/</code>, <code>?</code>, <code>#</code>, and <code>&</code>. <code>encodeURIComponent()</code> encodes everything except letters, digits, and <code>- _ . ~</code>, making it the right choice for encoding individual query parameter values. This tool provides both options.</p>

    <h3>Common Characters That Need Encoding</h3>
    <table class="ue-ref-table">
      <tr><th>Character</th><th>Encoded</th><th>Description</th></tr>
      <tr><td>(space)</td><td>%20</td><td>Space character</td></tr>
      <tr><td>&</td><td>%26</td><td>Query parameter separator</td></tr>
      <tr><td>=</td><td>%3D</td><td>Key-value delimiter</td></tr>
      <tr><td>?</td><td>%3F</td><td>Query string start</td></tr>
      <tr><td>#</td><td>%23</td><td>Fragment identifier</td></tr>
      <tr><td>/</td><td>%2F</td><td>Path separator</td></tr>
      <tr><td>@</td><td>%40</td><td>User info delimiter</td></tr>
      <tr><td>+</td><td>%2B</td><td>Plus sign</td></tr>
    </table>
  </div>

  <!-- FAQ with Schema.org markup -->
  <div class="ue-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="ue-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is URL encoding and when do I need it?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">URL encoding (also called percent encoding) converts characters that are not allowed in URLs into a format that can be transmitted safely. You need it whenever you pass user input, special characters, or non-ASCII text in a URL. Common scenarios include building API query strings, encoding form data, passing file names with spaces in URLs, and working with internationalized domain names or paths containing characters like accents or emoji.</p>
      </div>
    </div>

    <div class="ue-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between encodeURI and encodeURIComponent?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">encodeURI encodes a complete URL while preserving characters that have special meaning in URLs, such as colons, slashes, question marks, and hash symbols. encodeURIComponent encodes a single URL component (like a query parameter value) and encodes all special characters including those preserved by encodeURI. Use encodeURI when you have a full URL that just needs non-ASCII characters encoded. Use encodeURIComponent when encoding a value that will be inserted into a query parameter, path segment, or fragment.</p>
      </div>
    </div>

    <div class="ue-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Should I use %20 or + for spaces in URLs?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Both are valid in different contexts. %20 is the standard percent encoding for spaces defined in RFC 3986 and works everywhere in a URL including paths, query strings, and fragments. The plus sign (+) for spaces is specific to the application/x-www-form-urlencoded format used in HTML form submissions and some query strings. When building API requests or encoding path segments, use %20. When encoding HTML form data, either works, but %20 is the safer universal choice.</p>
      </div>
    </div>

    <div class="ue-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can this tool handle UTF-8 and international characters?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This URL encoder fully supports UTF-8 encoding. International characters such as accented letters, Chinese, Japanese, Korean, Arabic, emoji, and other Unicode characters are converted to their UTF-8 byte sequences and then percent-encoded. For example, the character "cafe" with an accented e becomes "caf%C3%A9". This is the correct behavior specified by RFC 3986 and matches how modern browsers handle international URLs.</p>
      </div>
    </div>

    <div class="ue-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe using this online URL encoder?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This URL encoder and decoder runs entirely inside your browser using JavaScript. Your data never leaves your device. There are no server requests, no logging, and no data storage. You can verify this by monitoring the Network tab in your browser's developer tools. This makes it safe for encoding URLs containing API keys, tokens, passwords, and other sensitive parameters.</p>
      </div>
    </div>

  </div>

  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid #2a2a3a; margin-top: 3rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var inputEl = document.getElementById("ueInput");
  var outputEl = document.getElementById("ueOutput");
  var statusEl = document.getElementById("ueStatusMsg");
  var convertBtn = document.getElementById("ueConvertBtn");
  var breakdownEl = document.getElementById("ueBreakdown");
  var breakdownContent = document.getElementById("ueBreakdownContent");

  var currentMode = "encode";

  // --- Helpers ---

  function byteSize(str) {
    return new Blob([str]).size;
  }

  function formatBytes(bytes) {
    if (bytes === 0) return "0 bytes";
    if (bytes < 1024) return bytes + " bytes";
    return (bytes / 1024).toFixed(1) + " KB";
  }

  function escapeHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  function updateSizes() {
    document.getElementById("ueInputSize").textContent = formatBytes(byteSize(inputEl.value));
    document.getElementById("ueOutputSize").textContent = formatBytes(byteSize(outputEl.value));
  }

  function setStatus(type, msg) {
    statusEl.className = "ue-status-msg";
    if (type === "success") {
      statusEl.classList.add("ue-status-success");
      statusEl.innerHTML = "&#10004; " + msg;
    } else if (type === "error") {
      statusEl.classList.add("ue-status-error");
      statusEl.innerHTML = "&#10006; " + msg;
    } else {
      statusEl.classList.add("ue-status-empty");
      statusEl.textContent = msg;
    }
  }

  function updateStats(input, output) {
    document.getElementById("ueStatInput").textContent = input.length + " chars";
    document.getElementById("ueStatOutput").textContent = output.length + " chars";
    // Count percent-encoded chars
    var encoded = (output.match(/%[0-9A-Fa-f]{2}/g) || []).length;
    document.getElementById("ueStatEncoded").textContent = encoded + " chars";
  }

  function clearStats() {
    document.getElementById("ueStatInput").textContent = "0 chars";
    document.getElementById("ueStatOutput").textContent = "0 chars";
    document.getElementById("ueStatEncoded").textContent = "0 chars";
  }

  function resetCopyBtn() {
    var btn = document.getElementById("ueCopyBtn");
    var label = document.getElementById("ueCopyLabel");
    btn.classList.remove("copied");
    label.textContent = "Copy";
  }

  inputEl.addEventListener("input", function() {
    updateSizes();
  });

  // --- Mode switching ---

  window.ueSetMode = function(mode) {
    currentMode = mode;
    document.getElementById("ueModeEncode").classList.toggle("active", mode === "encode");
    document.getElementById("ueModeDecode").classList.toggle("active", mode === "decode");
    document.getElementById("ueModeComponent").classList.toggle("active", mode === "component");
    document.getElementById("ueModeParse").classList.toggle("active", mode === "parse");
    breakdownEl.classList.remove("visible");

    var swapBtn = document.getElementById("ueSwapBtn");

    if (mode === "encode") {
      convertBtn.innerHTML = "&#9654; Encode";
      document.getElementById("ueInputLabel").innerHTML = "&#9998; Text Input";
      document.getElementById("ueOutputLabel").innerHTML = "&#10004; Encoded Output";
      inputEl.placeholder = "Type or paste text to URL-encode...";
      outputEl.placeholder = "Encoded result will appear here...";
      swapBtn.style.display = "";
      setStatus("empty", "Enter text and click Encode");
    } else if (mode === "decode") {
      convertBtn.innerHTML = "&#9654; Decode";
      document.getElementById("ueInputLabel").innerHTML = "&#9998; Encoded Input";
      document.getElementById("ueOutputLabel").innerHTML = "&#10004; Decoded Output";
      inputEl.placeholder = "Paste URL-encoded string to decode...";
      outputEl.placeholder = "Decoded result will appear here...";
      swapBtn.style.display = "";
      setStatus("empty", "Paste encoded text and click Decode");
    } else if (mode === "component") {
      convertBtn.innerHTML = "&#9654; Encode Component";
      document.getElementById("ueInputLabel").innerHTML = "&#9998; Component Value";
      document.getElementById("ueOutputLabel").innerHTML = "&#10004; Encoded Component";
      inputEl.placeholder = "Paste a query parameter value to encode...\n\nThis encodes ALL special characters (including : / ? # & =)\nUse this for individual parameter values, not full URLs.";
      outputEl.placeholder = "Encoded component will appear here...";
      swapBtn.style.display = "";
      setStatus("empty", "Enter component value and click Encode");
    } else if (mode === "parse") {
      convertBtn.innerHTML = "&#9654; Parse URL";
      document.getElementById("ueInputLabel").innerHTML = "&#9998; Full URL";
      document.getElementById("ueOutputLabel").innerHTML = "&#10004; Decoded URL";
      inputEl.placeholder = "Paste a full URL to parse its components...\n\nhttps://example.com/path?key=value&q=hello%20world#section";
      outputEl.placeholder = "Decoded URL will appear here...";
      swapBtn.style.display = "none";
      setStatus("empty", "Paste a URL and click Parse");
    }
  };

  // --- URL parsing ---

  function parseUrl(url) {
    try {
      var parsed = new URL(url);
      var rows = [];
      rows.push({ label: "Protocol", value: parsed.protocol });
      if (parsed.username) rows.push({ label: "Username", value: parsed.username });
      if (parsed.password) rows.push({ label: "Password", value: parsed.password });
      rows.push({ label: "Host", value: parsed.host });
      rows.push({ label: "Hostname", value: parsed.hostname });
      if (parsed.port) rows.push({ label: "Port", value: parsed.port });
      rows.push({ label: "Path", value: parsed.pathname });
      if (parsed.search) {
        rows.push({ label: "Query", value: parsed.search, highlight: true });
        // Parse individual parameters
        parsed.searchParams.forEach(function(val, key) {
          rows.push({ label: "  " + key, value: val, highlight: true });
        });
      }
      if (parsed.hash) rows.push({ label: "Fragment", value: parsed.hash });
      rows.push({ label: "Origin", value: parsed.origin });
      return rows;
    } catch (e) {
      return null;
    }
  }

  function renderBreakdown(rows) {
    var html = "";
    for (var i = 0; i < rows.length; i++) {
      var cls = rows[i].highlight ? " ue-highlight" : "";
      html += '<div class="ue-breakdown-row">';
      html += '<span class="ue-breakdown-label">' + escapeHtml(rows[i].label) + '</span>';
      html += '<span class="ue-breakdown-value' + cls + '">' + escapeHtml(rows[i].value) + '</span>';
      html += '</div>';
    }
    breakdownContent.innerHTML = html;
    breakdownEl.classList.add("visible");
  }

  // --- Core actions ---

  window.ueConvert = function() {
    resetCopyBtn();
    var raw = inputEl.value;

    if (!raw) {
      var emptyMsg = {
        encode: "Enter text and click Encode",
        decode: "Paste encoded text and click Decode",
        component: "Enter component value and click Encode",
        parse: "Paste a URL and click Parse"
      };
      setStatus("empty", emptyMsg[currentMode] || "Enter text");
      outputEl.value = "";
      updateSizes();
      clearStats();
      breakdownEl.classList.remove("visible");
      return;
    }

    try {
      var result;

      if (currentMode === "encode") {
        result = encodeURI(raw);
        outputEl.value = result;
        updateStats(raw, result);
        setStatus("success", "URL encoded (" + raw.length + " &#8594; " + result.length + " chars)");
        breakdownEl.classList.remove("visible");

      } else if (currentMode === "decode") {
        result = decodeURI(raw);
        // Also try decodeURIComponent for more aggressive decoding
        try { result = decodeURIComponent(raw); } catch (e) { /* keep decodeURI result */ }
        outputEl.value = result;
        updateStats(raw, result);
        setStatus("success", "URL decoded (" + raw.length + " &#8594; " + result.length + " chars)");
        breakdownEl.classList.remove("visible");

      } else if (currentMode === "component") {
        result = encodeURIComponent(raw);
        outputEl.value = result;
        updateStats(raw, result);
        setStatus("success", "Component encoded (" + raw.length + " &#8594; " + result.length + " chars)");
        breakdownEl.classList.remove("visible");

      } else if (currentMode === "parse") {
        // Decode the URL for display
        try {
          result = decodeURI(raw);
        } catch (e) {
          result = raw;
        }
        outputEl.value = result;
        updateStats(raw, result);

        var parsed = parseUrl(raw);
        if (parsed) {
          renderBreakdown(parsed);
          setStatus("success", "URL parsed successfully");
        } else {
          breakdownEl.classList.remove("visible");
          setStatus("error", "Invalid URL — must include protocol (e.g., https://)");
        }
      }

      updateSizes();
    } catch (e) {
      setStatus("error", "Error: " + e.message);
      outputEl.value = "";
      updateSizes();
      clearStats();
    }
  };

  window.ueCopy = function() {
    var text = outputEl.value;
    if (!text) return;
    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById("ueCopyBtn");
      var label = document.getElementById("ueCopyLabel");
      btn.classList.add("copied");
      label.textContent = "Copied!";
      setTimeout(function() {
        resetCopyBtn();
      }, 2000);
    });
  };

  window.ueSwap = function() {
    if (currentMode === "parse") return;
    var tmp = inputEl.value;
    inputEl.value = outputEl.value;
    outputEl.value = tmp;
    updateSizes();
    if (currentMode === "encode") {
      ueSetMode("decode");
    } else if (currentMode === "decode") {
      ueSetMode("encode");
    }
  };

  window.ueClear = function() {
    inputEl.value = "";
    outputEl.value = "";
    updateSizes();
    clearStats();
    resetCopyBtn();
    breakdownEl.classList.remove("visible");
    var emptyMsg = {
      encode: "Enter text and click Encode",
      decode: "Paste encoded text and click Decode",
      component: "Enter component value and click Encode",
      parse: "Paste a URL and click Parse"
    };
    setStatus("empty", emptyMsg[currentMode] || "Enter text");
  };

  window.ueLoadSample = function() {
    if (currentMode === "decode") {
      inputEl.value = "https%3A%2F%2Fzovo.one%2Ftools%2Furl-encoder%3Fq%3Dhello%20world%26lang%3Den%26special%3Dcaf%C3%A9%20%26%20cr%C3%A8me%23section-1";
    } else if (currentMode === "component") {
      inputEl.value = "search query with spaces & special chars: café, naïve, résumé (2026)";
    } else if (currentMode === "parse") {
      inputEl.value = "https://api.zovo.one/v1/search?q=chrome%20extensions&category=productivity&sort=rating&limit=25&lang=en#results";
    } else {
      inputEl.value = "https://zovo.one/tools/url-encoder?q=hello world&lang=en&special=café & crème#section-1";
    }
    updateSizes();
    ueConvert();
  };

  // Keyboard shortcut: Ctrl/Cmd + Enter to convert
  inputEl.addEventListener("keydown", function(e) {
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      ueConvert();
    }
  });

})();
</script>
