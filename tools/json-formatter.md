---
layout: page
title: "JSON Formatter & Validator - Free Online Tool | Zovo"
description: "Free JSON formatter online -- beautify, minify, and validate JSON instantly. Syntax highlighting, error detection with line numbers, and one-click copy."
permalink: /tools/json-formatter/
keywords: "json formatter, json formatter online, json validator, json beautifier, json minify, format json, json pretty print"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [json formatter, json validator, json beautifier, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --jf-primary: #6C5CE7;
    --jf-primary-dark: #5A4BD1;
    --jf-primary-light: #A29BFE;
    --jf-bg: #F8F9FE;
    --jf-surface: #FFFFFF;
    --jf-text: #2D3436;
    --jf-text-muted: #636E72;
    --jf-border: #DFE6E9;
    --jf-success: #00B894;
    --jf-error: #D63031;
    --jf-warning: #FDCB6E;
    --jf-radius: 12px;
  }

  .jf-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--jf-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .jf-wrapper * {
    box-sizing: border-box;
  }

  .jf-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .jf-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--jf-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .jf-hero h1 span {
    color: var(--jf-primary);
  }

  .jf-intro {
    font-size: 1.05rem;
    color: var(--jf-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Toolbar */
  .jf-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .jf-btn {
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

  .jf-btn-primary {
    background: var(--jf-primary);
    color: #fff;
  }

  .jf-btn-primary:hover {
    background: var(--jf-primary-dark);
  }

  .jf-btn-secondary {
    background: var(--jf-bg);
    color: var(--jf-text);
    border: 1px solid var(--jf-border);
  }

  .jf-btn-secondary:hover {
    background: var(--jf-border);
  }

  .jf-btn-success {
    background: var(--jf-success);
    color: #fff;
  }

  .jf-btn-success:hover {
    background: #00A383;
  }

  .jf-btn.copied {
    background: var(--jf-success);
    color: #fff;
  }

  .jf-select {
    padding: 8px 12px;
    border: 1px solid var(--jf-border);
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    background: var(--jf-surface);
    color: var(--jf-text);
    cursor: pointer;
  }

  .jf-toolbar-spacer {
    flex: 1;
  }

  /* Editor Layout */
  .jf-editor {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .jf-panel {
    background: var(--jf-surface);
    border: 1px solid var(--jf-border);
    border-radius: var(--jf-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .jf-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--jf-bg);
    border-bottom: 1px solid var(--jf-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--jf-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .jf-panel-header span {
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .jf-input-area {
    width: 100%;
    min-height: 420px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    resize: vertical;
    color: var(--jf-text);
    background: var(--jf-surface);
    outline: none;
    tab-size: 2;
  }

  .jf-input-area::placeholder {
    color: #B2BEC3;
  }

  .jf-output-area {
    width: 100%;
    min-height: 420px;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    overflow: auto;
    white-space: pre;
    background: var(--jf-surface);
    color: var(--jf-text);
  }

  /* Syntax Highlighting */
  .jf-string { color: #00B894; }
  .jf-number { color: #6C5CE7; }
  .jf-boolean { color: #E17055; }
  .jf-null { color: #B2BEC3; font-style: italic; }
  .jf-key { color: #0984E3; }
  .jf-bracket { color: #636E72; }
  .jf-comma { color: #636E72; }

  /* Status Bar */
  .jf-status {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 24px;
  }

  .jf-status-msg {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.875rem;
    font-weight: 500;
    padding: 6px 14px;
    border-radius: 20px;
  }

  .jf-status-valid {
    background: rgba(0, 184, 148, 0.1);
    color: #00B894;
  }

  .jf-status-invalid {
    background: rgba(214, 48, 49, 0.1);
    color: #D63031;
  }

  .jf-status-empty {
    background: var(--jf-bg);
    color: var(--jf-text-muted);
  }

  .jf-stats {
    display: flex;
    gap: 16px;
    font-size: 0.825rem;
    color: var(--jf-text-muted);
  }

  .jf-stat {
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .jf-stat strong {
    color: var(--jf-text);
    font-weight: 600;
  }

  /* Error display */
  .jf-error-detail {
    font-size: 0.825rem;
    color: var(--jf-error);
    padding: 8px 16px;
    background: rgba(214, 48, 49, 0.05);
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    margin-bottom: 16px;
    display: none;
    word-break: break-word;
  }

  /* Meta footer */
  .jf-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--jf-text-muted);
    border-top: 1px solid var(--jf-border);
    margin-bottom: 40px;
  }

  /* FAQ Section */
  .jf-faq {
    max-width: 820px;
    margin: 0 auto 60px;
  }

  .jf-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--jf-text);
  }

  .jf-faq-item {
    border: 1px solid var(--jf-border);
    border-radius: var(--jf-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--jf-surface);
    box-shadow: 0 1px 4px rgba(108, 92, 231, 0.04);
  }

  .jf-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--jf-text);
  }

  .jf-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--jf-text-muted);
    line-height: 1.7;
  }

  /* Sample button */
  .jf-link-btn {
    background: none;
    border: none;
    color: var(--jf-primary);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .jf-link-btn:hover {
    color: var(--jf-primary-dark);
  }

  /* Mobile responsive */
  @media (max-width: 768px) {
    .jf-hero h1 {
      font-size: 1.6rem;
    }

    .jf-editor {
      grid-template-columns: 1fr;
    }

    .jf-input-area,
    .jf-output-area {
      min-height: 260px;
    }

    .jf-toolbar {
      gap: 6px;
    }

    .jf-btn {
      padding: 7px 12px;
      font-size: 0.8rem;
    }

    .jf-stats {
      gap: 10px;
      flex-wrap: wrap;
    }
  }
</style>

<div class="jf-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="JSON Formatter & Validator">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="jf-hero">
    <h1><span>JSON Formatter</span> & Validator</h1>
    <p class="jf-intro">Paste your JSON and instantly format, validate, or minify it -- right in your browser. This free JSON formatter online highlights syntax errors with line numbers, calculates structure stats, and lets you copy the result in one click. Nothing is sent to a server; all processing happens locally.</p>
  </div>

  <!-- Toolbar -->
  <div class="jf-toolbar">
    <button class="jf-btn jf-btn-primary" onclick="jfFormat()" title="Format & beautify JSON">&#9998; Format</button>
    <button class="jf-btn jf-btn-secondary" onclick="jfMinify()" title="Minify JSON">&#9660; Minify</button>
    <select id="jfIndent" class="jf-select" title="Indentation level">
      <option value="2">2 spaces</option>
      <option value="4">4 spaces</option>
    </select>
    <button class="jf-btn jf-btn-secondary" onclick="jfCopy()" id="jfCopyBtn" title="Copy output to clipboard">&#128203; <span id="jfCopyLabel">Copy</span></button>
    <div class="jf-toolbar-spacer"></div>
    <button class="jf-link-btn" onclick="jfLoadSample()" title="Load example JSON">Load sample</button>
    <button class="jf-btn jf-btn-secondary" onclick="jfClear()" title="Clear input and output">&#10005; Clear</button>
  </div>

  <!-- Error detail -->
  <div id="jfError" class="jf-error-detail"></div>

  <!-- Editor panels -->
  <div class="jf-editor">
    <div class="jf-panel">
      <div class="jf-panel-header">
        <span>&#9998; Input</span>
        <span id="jfInputSize">0 bytes</span>
      </div>
      <textarea id="jfInput" class="jf-input-area" placeholder='Paste your JSON here...&#10;&#10;Example:&#10;{&#10;  "name": "Zovo",&#10;  "version": 1&#10;}' spellcheck="false"></textarea>
    </div>
    <div class="jf-panel">
      <div class="jf-panel-header">
        <span>&#10004; Output</span>
        <span id="jfOutputSize">0 bytes</span>
      </div>
      <div id="jfOutput" class="jf-output-area"></div>
    </div>
  </div>

  <!-- Status & Stats -->
  <div class="jf-status">
    <div id="jfStatusMsg" class="jf-status-msg jf-status-empty">Paste JSON and click Format</div>
    <div class="jf-stats">
      <span class="jf-stat">Keys: <strong id="jfKeyCount">0</strong></span>
      <span class="jf-stat">Depth: <strong id="jfDepth">0</strong></span>
      <span class="jf-stat">Size: <strong id="jfByteSize">0 B</strong></span>
    </div>
  </div>

  <div class="jf-meta">
    <span>Processing happens entirely in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- FAQ with Schema.org markup -->
  <div class="jf-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="jf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What does a JSON formatter do?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A JSON formatter takes raw or compacted JSON data and restructures it with consistent indentation and line breaks so the content is easy to read. This tool parses your input, verifies the syntax is valid, and outputs the data with your choice of two-space or four-space indentation. Formatted JSON is far easier to scan when debugging API responses, editing configuration files, or reviewing data exports.</p>
      </div>
    </div>

    <div class="jf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does the JSON validator detect errors?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The validator runs your input through the browser's native JSON parser. When a syntax error exists -- such as a missing comma, unquoted key, or trailing comma -- the parser returns a description and the approximate character position. This tool converts that position into a line number and column so you can jump directly to the problem. Common mistakes it catches include single-quoted strings, missing closing brackets, and extra commas after the last element in an array or object.</p>
      </div>
    </div>

    <div class="jf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between JSON beautify and JSON minify?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">JSON beautify (also called pretty-print) adds indentation and newlines to make the structure human-readable. JSON minify does the opposite -- it strips all unnecessary whitespace to produce the smallest possible output. Beautified JSON is ideal during development and debugging. Minified JSON is used in production APIs and configuration payloads because it reduces bandwidth and file size, sometimes by 30-60 percent on deeply nested structures.</p>
      </div>
    </div>

    <div class="jf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my JSON data safe in this online formatter?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This JSON formatter runs entirely inside your browser using JavaScript. Your data never leaves your device -- there are no network requests, no server-side processing, and nothing is logged or stored. You can verify this by opening your browser's developer tools and watching the Network tab while you format JSON. This makes it safe for working with API keys, tokens, and other sensitive payloads that should not be shared with third-party services.</p>
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

  var SAMPLE = '{\n  "name": "Zovo Tools",\n  "version": 2,\n  "features": [\n    "JSON Formatter",\n    "JSON Validator",\n    "Minifier"\n  ],\n  "config": {\n    "theme": "dark",\n    "indentation": 2,\n    "autoValidate": true\n  },\n  "stats": {\n    "users": 14500,\n    "rating": 4.8,\n    "free": true\n  },\n  "tags": ["developer", "productivity", "web"],\n  "homepage": "https://zovo.one"\n}';

  var inputEl = document.getElementById("jfInput");
  var outputEl = document.getElementById("jfOutput");
  var statusEl = document.getElementById("jfStatusMsg");
  var errorEl = document.getElementById("jfError");

  // --- Helpers ---

  function byteSize(str) {
    return new Blob([str]).size;
  }

  function formatBytes(bytes) {
    if (bytes === 0) return "0 B";
    if (bytes < 1024) return bytes + " B";
    if (bytes < 1048576) return (bytes / 1024).toFixed(1) + " KB";
    return (bytes / 1048576).toFixed(2) + " MB";
  }

  function countKeys(obj) {
    var count = 0;
    if (obj !== null && typeof obj === "object") {
      if (Array.isArray(obj)) {
        for (var i = 0; i < obj.length; i++) {
          count += countKeys(obj[i]);
        }
      } else {
        var keys = Object.keys(obj);
        count += keys.length;
        for (var k = 0; k < keys.length; k++) {
          count += countKeys(obj[keys[k]]);
        }
      }
    }
    return count;
  }

  function measureDepth(obj) {
    if (obj === null || typeof obj !== "object") return 0;
    var max = 0;
    var values = Array.isArray(obj) ? obj : Object.keys(obj).map(function(k) { return obj[k]; });
    for (var i = 0; i < values.length; i++) {
      var d = measureDepth(values[i]);
      if (d > max) max = d;
    }
    return 1 + max;
  }

  function positionToLine(str, pos) {
    var line = 1;
    var col = 1;
    for (var i = 0; i < pos && i < str.length; i++) {
      if (str[i] === "\n") {
        line++;
        col = 1;
      } else {
        col++;
      }
    }
    return { line: line, col: col };
  }

  function parseErrorInfo(err, src) {
    var msg = err.message || "Unknown error";
    // Try to extract position from message (varies by browser)
    var posMatch = msg.match(/position\s+(\d+)/i) || msg.match(/column\s+(\d+)/i);
    var lineMatch = msg.match(/line\s+(\d+)/i);
    var result = { message: msg, line: null, col: null };

    if (posMatch) {
      var pos = parseInt(posMatch[1], 10);
      var loc = positionToLine(src, pos);
      result.line = loc.line;
      result.col = loc.col;
    } else if (lineMatch) {
      result.line = parseInt(lineMatch[1], 10);
    }
    return result;
  }

  // --- Syntax highlighting ---

  function escapeHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  function highlightJson(str) {
    // Tokenize and highlight
    return str.replace(
      /("(?:[^"\\]|\\.)*")\s*:/g,
      '<span class="jf-key">$1</span>:'
    ).replace(
      /:\s*("(?:[^"\\]|\\.)*")/g,
      ': <span class="jf-string">$1</span>'
    ).replace(
      /(?<=[\[,\n]\s*)("(?:[^"\\]|\\.)*")(?=\s*[,\]\n])/g,
      '<span class="jf-string">$1</span>'
    ).replace(
      /:\s*(-?\d+(?:\.\d+)?(?:[eE][+-]?\d+)?)/g,
      ': <span class="jf-number">$1</span>'
    ).replace(
      /(?<=[\[,\n]\s*)(-?\d+(?:\.\d+)?(?:[eE][+-]?\d+)?)(?=\s*[,\]\n])/g,
      '<span class="jf-number">$1</span>'
    ).replace(
      /:\s*(true|false)/g,
      ': <span class="jf-boolean">$1</span>'
    ).replace(
      /:\s*(null)/g,
      ': <span class="jf-null">$1</span>'
    );
  }

  function renderOutput(text) {
    var html = escapeHtml(text);
    html = highlightJson(html);
    outputEl.innerHTML = html;
  }

  // --- Stats update ---

  function updateStats(parsed, raw) {
    var keys = countKeys(parsed);
    var depth = measureDepth(parsed);
    var bytes = byteSize(raw);
    document.getElementById("jfKeyCount").textContent = keys;
    document.getElementById("jfDepth").textContent = depth;
    document.getElementById("jfByteSize").textContent = formatBytes(bytes);
  }

  function clearStats() {
    document.getElementById("jfKeyCount").textContent = "0";
    document.getElementById("jfDepth").textContent = "0";
    document.getElementById("jfByteSize").textContent = "0 B";
  }

  function updateInputSize() {
    var bytes = byteSize(inputEl.value);
    document.getElementById("jfInputSize").textContent = formatBytes(bytes);
  }

  function updateOutputSize(text) {
    var bytes = byteSize(text);
    document.getElementById("jfOutputSize").textContent = formatBytes(bytes);
  }

  function setStatus(type, msg) {
    statusEl.className = "jf-status-msg";
    if (type === "valid") {
      statusEl.classList.add("jf-status-valid");
      statusEl.innerHTML = "&#10004; " + msg;
    } else if (type === "invalid") {
      statusEl.classList.add("jf-status-invalid");
      statusEl.innerHTML = "&#10006; " + msg;
    } else {
      statusEl.classList.add("jf-status-empty");
      statusEl.textContent = msg;
    }
  }

  function showError(info) {
    var parts = [];
    if (info.line) parts.push("Line " + info.line);
    if (info.col) parts.push("Col " + info.col);
    var loc = parts.length ? parts.join(", ") + ": " : "";
    errorEl.textContent = loc + info.message;
    errorEl.style.display = "block";
  }

  function hideError() {
    errorEl.style.display = "none";
    errorEl.textContent = "";
  }

  // --- Core actions ---

  window.jfFormat = function() {
    var raw = inputEl.value.trim();
    hideError();
    if (!raw) {
      setStatus("empty", "Paste JSON and click Format");
      outputEl.textContent = "";
      clearStats();
      updateOutputSize("");
      return;
    }
    try {
      var indent = parseInt(document.getElementById("jfIndent").value, 10);
      var parsed = JSON.parse(raw);
      var formatted = JSON.stringify(parsed, null, indent);
      renderOutput(formatted);
      outputEl.setAttribute("data-text", formatted);
      setStatus("valid", "Valid JSON -- formatted");
      updateStats(parsed, formatted);
      updateOutputSize(formatted);
      resetCopyBtn();
    } catch (e) {
      var info = parseErrorInfo(e, raw);
      setStatus("invalid", "Invalid JSON");
      showError(info);
      outputEl.textContent = "";
      clearStats();
      updateOutputSize("");
    }
    updateInputSize();
  };

  window.jfMinify = function() {
    var raw = inputEl.value.trim();
    hideError();
    if (!raw) {
      setStatus("empty", "Paste JSON and click Minify");
      outputEl.textContent = "";
      clearStats();
      updateOutputSize("");
      return;
    }
    try {
      var parsed = JSON.parse(raw);
      var minified = JSON.stringify(parsed);
      renderOutput(minified);
      outputEl.setAttribute("data-text", minified);
      setStatus("valid", "Valid JSON -- minified");
      updateStats(parsed, minified);
      updateOutputSize(minified);
      resetCopyBtn();
    } catch (e) {
      var info = parseErrorInfo(e, raw);
      setStatus("invalid", "Invalid JSON");
      showError(info);
      outputEl.textContent = "";
      clearStats();
      updateOutputSize("");
    }
    updateInputSize();
  };

  window.jfCopy = function() {
    var text = outputEl.getAttribute("data-text");
    if (!text) return;
    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById("jfCopyBtn");
      var label = document.getElementById("jfCopyLabel");
      btn.classList.add("copied");
      label.textContent = "Copied!";
      setTimeout(function() {
        resetCopyBtn();
      }, 2000);
    });
  };

  function resetCopyBtn() {
    var btn = document.getElementById("jfCopyBtn");
    var label = document.getElementById("jfCopyLabel");
    btn.classList.remove("copied");
    label.textContent = "Copy";
  }

  window.jfClear = function() {
    inputEl.value = "";
    outputEl.innerHTML = "";
    outputEl.removeAttribute("data-text");
    hideError();
    setStatus("empty", "Paste JSON and click Format");
    clearStats();
    updateInputSize();
    updateOutputSize("");
    resetCopyBtn();
  };

  window.jfLoadSample = function() {
    inputEl.value = SAMPLE;
    updateInputSize();
    jfFormat();
  };

  // Auto-update input byte size on typing
  inputEl.addEventListener("input", function() {
    updateInputSize();
  });

  // Allow Tab key in textarea
  inputEl.addEventListener("keydown", function(e) {
    if (e.key === "Tab") {
      e.preventDefault();
      var start = this.selectionStart;
      var end = this.selectionEnd;
      this.value = this.value.substring(0, start) + "  " + this.value.substring(end);
      this.selectionStart = this.selectionEnd = start + 2;
    }
    // Ctrl/Cmd + Enter to format
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      jfFormat();
    }
  });

})();
</script>
