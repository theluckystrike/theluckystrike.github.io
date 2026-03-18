---
layout: page
title: "CSV to JSON Converter - Convert CSV Files to JSON Online | Zovo"
description: "Free CSV to JSON converter -- paste or upload CSV/TSV data and get clean JSON instantly. Supports quoted fields, custom delimiters, array-of-objects or array-of-arrays output. No signup, runs in your browser."
permalink: /tools/csv-to-json-converter/
keywords: "csv to json converter, csv to json, convert csv to json, csv to json online, csv file to json, tsv to json, csv converter"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [csv to json, json converter, data conversion, csv parser, tsv converter, online tools]
target_keyword: "csv to json converter"
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --ctj-primary: #6C5CE7;
    --ctj-primary-dark: #5A4BD1;
    --ctj-primary-light: #A29BFE;
    --ctj-bg: #F8F9FE;
    --ctj-surface: #FFFFFF;
    --ctj-text: #2D3436;
    --ctj-text-muted: #636E72;
    --ctj-border: #DFE6E9;
    --ctj-success: #00B894;
    --ctj-error: #D63031;
    --ctj-radius: 12px;
  }

  .ctj-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ctj-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .ctj-wrapper * {
    box-sizing: border-box;
  }

  .ctj-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .ctj-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ctj-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .ctj-hero h1 span {
    color: var(--ctj-primary);
  }

  .ctj-intro {
    font-size: 1.05rem;
    color: var(--ctj-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Upload zone */
  .ctj-upload-zone {
    border: 2px dashed var(--ctj-border);
    border-radius: var(--ctj-radius);
    padding: 24px;
    text-align: center;
    margin-bottom: 16px;
    cursor: pointer;
    transition: all 0.2s ease;
    background: var(--ctj-bg);
  }

  .ctj-upload-zone:hover,
  .ctj-upload-zone.dragover {
    border-color: var(--ctj-primary);
    background: rgba(108, 92, 231, 0.04);
  }

  .ctj-upload-zone p {
    margin: 0;
    font-size: 0.9rem;
    color: var(--ctj-text-muted);
  }

  .ctj-upload-icon {
    font-size: 1.6rem;
    margin-bottom: 6px;
    display: block;
  }

  .ctj-upload-link {
    color: var(--ctj-primary);
    font-weight: 500;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .ctj-file-input {
    display: none;
  }

  /* Options bar */
  .ctj-options {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    align-items: center;
    padding: 14px 20px;
    margin-bottom: 16px;
    background: var(--ctj-surface);
    border: 1px solid var(--ctj-border);
    border-radius: var(--ctj-radius);
    box-shadow: 0 1px 6px rgba(108, 92, 231, 0.04);
  }

  .ctj-option-group {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 0.85rem;
    color: var(--ctj-text);
  }

  .ctj-option-group label {
    font-weight: 500;
    white-space: nowrap;
    cursor: pointer;
    user-select: none;
  }

  .ctj-option-group select {
    padding: 6px 10px;
    border: 1px solid var(--ctj-border);
    border-radius: 6px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    background: var(--ctj-bg);
    color: var(--ctj-text);
    cursor: pointer;
  }

  .ctj-option-group select:focus {
    outline: none;
    border-color: var(--ctj-primary);
    box-shadow: 0 0 0 2px rgba(108, 92, 231, 0.12);
  }

  .ctj-checkbox {
    width: 16px;
    height: 16px;
    accent-color: var(--ctj-primary);
    cursor: pointer;
  }

  .ctj-options-divider {
    width: 1px;
    height: 24px;
    background: var(--ctj-border);
  }

  /* Toolbar */
  .ctj-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .ctj-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 9px 18px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .ctj-btn-primary {
    background: var(--ctj-primary);
    color: #fff;
  }

  .ctj-btn-primary:hover {
    background: var(--ctj-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3);
  }

  .ctj-btn-secondary {
    background: var(--ctj-bg);
    color: var(--ctj-text);
    border: 1px solid var(--ctj-border);
  }

  .ctj-btn-secondary:hover {
    background: var(--ctj-border);
  }

  .ctj-btn-success {
    background: var(--ctj-success);
    color: #fff;
  }

  .ctj-btn-success:hover {
    background: #00A383;
  }

  .ctj-btn.copied {
    background: var(--ctj-success);
    color: #fff;
    border-color: var(--ctj-success);
  }

  .ctj-toolbar-spacer {
    flex: 1;
  }

  .ctj-link-btn {
    background: none;
    border: none;
    color: var(--ctj-primary);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .ctj-link-btn:hover {
    color: var(--ctj-primary-dark);
  }

  .ctj-delimiter-badge {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-size: 0.8rem;
    font-weight: 500;
    padding: 4px 10px;
    border-radius: 12px;
    background: rgba(108, 92, 231, 0.1);
    color: var(--ctj-primary);
  }

  /* Error display */
  .ctj-error-detail {
    font-size: 0.825rem;
    color: var(--ctj-error);
    padding: 10px 16px;
    background: rgba(214, 48, 49, 0.05);
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    margin-bottom: 16px;
    display: none;
    word-break: break-word;
  }

  /* Editor Layout */
  .ctj-editor {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .ctj-panel {
    background: var(--ctj-surface);
    border: 1px solid var(--ctj-border);
    border-radius: var(--ctj-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .ctj-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--ctj-bg);
    border-bottom: 1px solid var(--ctj-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--ctj-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .ctj-panel-header span {
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .ctj-input-area {
    width: 100%;
    min-height: 360px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    resize: vertical;
    color: var(--ctj-text);
    background: var(--ctj-surface);
    outline: none;
    tab-size: 2;
  }

  .ctj-input-area::placeholder {
    color: #B2BEC3;
  }

  .ctj-output-area {
    width: 100%;
    min-height: 360px;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    overflow: auto;
    white-space: pre;
    background: var(--ctj-surface);
    color: var(--ctj-text);
  }

  /* Syntax Highlighting */
  .ctj-string { color: #00B894; }
  .ctj-number { color: #6C5CE7; }
  .ctj-boolean { color: #E17055; }
  .ctj-null { color: #B2BEC3; font-style: italic; }
  .ctj-key { color: #0984E3; }

  /* Status Bar */
  .ctj-status {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 24px;
  }

  .ctj-status-msg {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.875rem;
    font-weight: 500;
    padding: 6px 14px;
    border-radius: 20px;
  }

  .ctj-status-valid {
    background: rgba(0, 184, 148, 0.1);
    color: #00B894;
  }

  .ctj-status-invalid {
    background: rgba(214, 48, 49, 0.1);
    color: #D63031;
  }

  .ctj-status-empty {
    background: var(--ctj-bg);
    color: var(--ctj-text-muted);
  }

  .ctj-stats {
    display: flex;
    gap: 16px;
    font-size: 0.825rem;
    color: var(--ctj-text-muted);
  }

  .ctj-stat {
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .ctj-stat strong {
    color: var(--ctj-text);
    font-weight: 600;
  }

  /* Meta footer */
  .ctj-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--ctj-text-muted);
    border-top: 1px solid var(--ctj-border);
    margin-bottom: 40px;
  }

  /* SEO Content */
  .ctj-content {
    max-width: 820px;
    margin: 0 auto 48px;
  }

  .ctj-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--ctj-text);
  }

  .ctj-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 10px;
    color: var(--ctj-text);
  }

  .ctj-content p {
    font-size: 0.95rem;
    color: var(--ctj-text-muted);
    line-height: 1.75;
    margin: 0 0 16px;
  }

  .ctj-content ul {
    padding-left: 20px;
    margin: 0 0 16px;
  }

  .ctj-content li {
    font-size: 0.95rem;
    color: var(--ctj-text-muted);
    line-height: 1.75;
    margin-bottom: 6px;
  }

  .ctj-content a {
    color: var(--ctj-primary);
    text-decoration: none;
  }

  .ctj-content a:hover {
    text-decoration: underline;
  }

  /* FAQ */
  .ctj-faq {
    max-width: 820px;
    margin: 0 auto 60px;
  }

  .ctj-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--ctj-text);
  }

  .ctj-faq-item {
    border: 1px solid var(--ctj-border);
    border-radius: var(--ctj-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--ctj-surface);
    box-shadow: 0 1px 4px rgba(108, 92, 231, 0.04);
  }

  .ctj-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--ctj-text);
  }

  .ctj-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--ctj-text-muted);
    line-height: 1.7;
  }

  /* CTA */
  .ctj-cta {
    text-align: center;
    padding: 40px 24px;
    background: var(--ctj-bg);
    border-radius: var(--ctj-radius);
    margin: 0 auto 48px;
    max-width: 820px;
    border: 1px solid var(--ctj-border);
  }

  .ctj-cta h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 12px;
    color: var(--ctj-text);
  }

  .ctj-cta p {
    font-size: 0.95rem;
    color: var(--ctj-text-muted);
    margin: 0 0 20px;
    line-height: 1.7;
  }

  .ctj-cta-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 28px;
    background: var(--ctj-primary);
    color: #fff;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
  }

  .ctj-cta-btn:hover {
    background: var(--ctj-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 16px rgba(108, 92, 231, 0.3);
  }

  /* Responsive */
  @media (max-width: 768px) {
    .ctj-hero h1 {
      font-size: 1.6rem;
    }

    .ctj-editor {
      grid-template-columns: 1fr;
    }

    .ctj-input-area,
    .ctj-output-area {
      min-height: 220px;
    }

    .ctj-options {
      gap: 10px;
      padding: 12px 14px;
    }

    .ctj-options-divider {
      display: none;
    }

    .ctj-toolbar {
      gap: 6px;
    }

    .ctj-btn {
      padding: 7px 12px;
      font-size: 0.8rem;
    }

    .ctj-stats {
      gap: 10px;
      flex-wrap: wrap;
    }
  }
</style>

<div class="ctj-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="CSV to JSON Converter">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="ctj-hero">
    <h1><span>CSV to JSON</span> Converter</h1>
    <p class="ctj-intro">Paste CSV or TSV data, or drag and drop a file, and convert it to clean JSON instantly. Choose between array-of-objects and array-of-arrays output, toggle pretty-print or minified formatting, and download or copy the result. Everything runs locally in your browser.</p>
  </div>

  <!-- Upload zone -->
  <div class="ctj-upload-zone" id="ctjDropZone" onclick="document.getElementById('ctjFileInput').click()">
    <span class="ctj-upload-icon">&#128196;</span>
    <p>Drag &amp; drop a .csv or .tsv file here, or <span class="ctj-upload-link">browse to upload</span></p>
    <p style="font-size: 0.8rem; color: #B2BEC3; margin-top: 4px;">Supports .csv, .tsv, and .txt files up to 50 MB</p>
  </div>
  <input type="file" id="ctjFileInput" class="ctj-file-input" accept=".csv,.tsv,.txt">

  <!-- Options -->
  <div class="ctj-options">
    <div class="ctj-option-group">
      <label for="ctjDelimiter">Delimiter:</label>
      <select id="ctjDelimiter">
        <option value="auto">Auto-detect</option>
        <option value=",">Comma (,)</option>
        <option value="&#9;">Tab (TSV)</option>
        <option value=";">Semicolon (;)</option>
        <option value="|">Pipe (|)</option>
      </select>
    </div>

    <div class="ctj-options-divider"></div>

    <div class="ctj-option-group">
      <input type="checkbox" id="ctjHeaders" class="ctj-checkbox" checked>
      <label for="ctjHeaders">First row as headers</label>
    </div>

    <div class="ctj-options-divider"></div>

    <div class="ctj-option-group">
      <label for="ctjOutputFormat">Output:</label>
      <select id="ctjOutputFormat">
        <option value="objects">Array of objects</option>
        <option value="arrays">Array of arrays</option>
      </select>
    </div>

    <div class="ctj-options-divider"></div>

    <div class="ctj-option-group">
      <label for="ctjIndent">Format:</label>
      <select id="ctjIndent">
        <option value="2">Pretty (2 spaces)</option>
        <option value="4">Pretty (4 spaces)</option>
        <option value="tab">Pretty (tabs)</option>
        <option value="0">Minified</option>
      </select>
    </div>
  </div>

  <!-- Toolbar -->
  <div class="ctj-toolbar">
    <button class="ctj-btn ctj-btn-primary" onclick="ctjConvert()" title="Convert CSV to JSON">&#9654; Convert</button>
    <button class="ctj-btn ctj-btn-secondary" onclick="ctjCopy()" id="ctjCopyBtn" title="Copy JSON to clipboard">&#128203; <span id="ctjCopyLabel">Copy to Clipboard</span></button>
    <button class="ctj-btn ctj-btn-success" onclick="ctjDownload()" title="Download JSON file">&#11015; Download JSON</button>
    <div class="ctj-toolbar-spacer"></div>
    <span id="ctjDelimiterBadge" class="ctj-delimiter-badge" style="display:none;"></span>
    <button class="ctj-link-btn" onclick="ctjLoadSample()" title="Load example CSV">Load sample</button>
    <button class="ctj-btn ctj-btn-secondary" onclick="ctjClear()" title="Clear everything">&#10005; Clear</button>
  </div>

  <!-- Error -->
  <div id="ctjError" class="ctj-error-detail"></div>

  <!-- Editor panels -->
  <div class="ctj-editor">
    <div class="ctj-panel">
      <div class="ctj-panel-header">
        <span>&#9998; CSV Input</span>
        <span id="ctjInputSize">0 bytes</span>
      </div>
      <textarea id="ctjInput" class="ctj-input-area" placeholder='Paste your CSV or TSV data here...&#10;&#10;Example:&#10;name,email,role&#10;Alice,alice@example.com,admin&#10;Bob,bob@example.com,editor' spellcheck="false"></textarea>
    </div>
    <div class="ctj-panel">
      <div class="ctj-panel-header">
        <span>&#10004; JSON Output</span>
        <span id="ctjOutputSize">0 bytes</span>
      </div>
      <div id="ctjOutput" class="ctj-output-area"></div>
    </div>
  </div>

  <!-- Status & Stats -->
  <div class="ctj-status">
    <div id="ctjStatusMsg" class="ctj-status-msg ctj-status-empty">Paste CSV and click Convert</div>
    <div class="ctj-stats">
      <span class="ctj-stat">Rows: <strong id="ctjRowCount">0</strong></span>
      <span class="ctj-stat">Columns: <strong id="ctjColCount">0</strong></span>
      <span class="ctj-stat">Size: <strong id="ctjByteSize">0 B</strong></span>
    </div>
  </div>

  <div class="ctj-meta">
    <span>All processing happens in your browser. Nothing is sent to a server.</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO Content -->
  <div class="ctj-content">
    <h2>How to Convert CSV to JSON</h2>

    <p>CSV (Comma-Separated Values) and JSON (JavaScript Object Notation) are two of the most common data formats used in software development, data analysis, and system integrations. CSV files are simple, tabular, and widely supported by spreadsheet applications like Excel and Google Sheets. JSON, on the other hand, is the standard data format for web APIs, configuration files, and modern databases like MongoDB and Firebase.</p>

    <p>Converting CSV to JSON is a frequent task when migrating data between systems, preparing API payloads, or loading tabular data into a JavaScript application. This converter handles the process in your browser with zero dependencies and zero server calls.</p>

    <h3>When to Use CSV to JSON Conversion</h3>
    <ul>
      <li><strong>API development:</strong> Convert spreadsheet exports into JSON payloads for testing REST endpoints or seeding a database.</li>
      <li><strong>Front-end prototyping:</strong> Turn a quick CSV file into a JSON array you can drop directly into your JavaScript code.</li>
      <li><strong>Data pipeline prep:</strong> Reformat CSV exports from analytics tools or CRMs before feeding them into a JSON-based processing pipeline.</li>
      <li><strong>Configuration files:</strong> Translate a tabular settings sheet into structured JSON for application config.</li>
      <li><strong>Database imports:</strong> Prepare bulk-insert documents for NoSQL databases that accept JSON input.</li>
    </ul>

    <h3>Formatting Tips</h3>
    <p>For the cleanest conversion, make sure your CSV follows these guidelines:</p>
    <ul>
      <li>Use a consistent delimiter throughout the file. Mixing commas and tabs will cause parsing errors.</li>
      <li>Wrap fields that contain the delimiter character, newlines, or double quotes in double quotes. For example: <code>"San Francisco, CA"</code>.</li>
      <li>Escape literal double quotes inside a quoted field by doubling them: <code>"She said ""hello"""</code> becomes <code>She said "hello"</code> in the output.</li>
      <li>Keep header names short and descriptive. They become your JSON keys, so names like <code>first_name</code> or <code>orderTotal</code> work better than <code>Column A</code>.</li>
      <li>Remove trailing blank rows before converting. Empty rows produce empty objects that clutter your output.</li>
    </ul>

    <h3>Array of Objects vs. Array of Arrays</h3>
    <p>This converter supports two output shapes. "Array of objects" maps each row to a JSON object with named keys from the header row. This is the most common format for API payloads and database documents. "Array of arrays" outputs each row as a plain array of values with no keys, which is useful for lightweight data transport, charting libraries, or when column order matters more than column names. Choose the format that fits your downstream system.</p>

    <p>For more developer tools, visit <a href="https://zovo.one/tools">zovo.one/tools</a>.</p>
  </div>

  <!-- FAQ -->
  <div class="ctj-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="ctj-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does this CSV to JSON converter handle quoted fields with commas?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The parser follows RFC 4180 rules. Any field wrapped in double quotes is treated as a single value, even if it contains commas, tabs, or newline characters. A literal double quote inside a quoted field is represented by two double quotes in a row. For example, the CSV value "Hello, ""world""" converts to the JSON string "Hello, \"world\"".</p>
      </div>
    </div>

    <div class="ctj-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I convert TSV (tab-separated) files to JSON?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The auto-detect feature analyzes the first few lines of your data and identifies whether it uses commas, tabs, semicolons, or pipes as the delimiter. Tab-separated files are detected automatically. You can also manually select "Tab (TSV)" from the delimiter dropdown if the auto-detection picks the wrong separator.</p>
      </div>
    </div>

    <div class="ctj-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between array of objects and array of arrays?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Array of objects uses the first row as keys and maps each subsequent row into a JSON object like {"name":"Alice","email":"alice@example.com"}. Array of arrays outputs each row as a plain list of values like ["Alice","alice@example.com"]. Objects are better for APIs and databases. Arrays are smaller in size and useful for charting libraries or when you only care about column position.</p>
      </div>
    </div>

    <div class="ctj-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe when I use this converter?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This tool runs entirely inside your browser using client-side JavaScript. Your CSV data never leaves your device. No network requests are made, nothing is uploaded to a server, and no data is logged or stored. You can verify this by opening your browser's developer tools and checking the Network tab during conversion.</p>
      </div>
    </div>

    <div class="ctj-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does the converter auto-detect data types like numbers and booleans?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. When outputting as array of objects, the converter checks each value and stores it as a JSON number if it looks numeric, as a boolean for "true" and "false" strings, and as null for "null" strings. Everything else is stored as a string. This means a CSV value of 42 becomes the JSON number 42, not the string "42". Array-of-arrays mode keeps all values as strings.</p>
      </div>
    </div>
  </div>

  <!-- CTA -->
  <div class="ctj-cta">
    <h2>More Free Developer Tools</h2>
    <p>JSON formatters, diff checkers, color pickers, and more. All free, all running in your browser.</p>
    <a href="https://zovo.one/tools" class="ctj-cta-btn">Browse All Tools</a>
  </div>

  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid #2a2a3a; margin-top: 3rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var SAMPLE_CSV = 'name,email,role,department,salary\nAlice Johnson,alice@example.com,admin,Engineering,95000\nBob Smith,bob@example.com,editor,Marketing,72000\n"Carol White",carol@example.com,viewer,Design,68000\n"Dave ""The Dev"" Brown",dave@example.com,admin,Engineering,105000\n"Eve Davis",eve@example.com,editor,"Sales, Support",74000';

  var inputEl = document.getElementById("ctjInput");
  var outputEl = document.getElementById("ctjOutput");
  var statusEl = document.getElementById("ctjStatusMsg");
  var errorEl = document.getElementById("ctjError");
  var dropZone = document.getElementById("ctjDropZone");
  var fileInput = document.getElementById("ctjFileInput");
  var delimBadge = document.getElementById("ctjDelimiterBadge");

  var lastJson = "";

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

  // --- Delimiter Detection ---

  function detectDelimiter(text) {
    var lines = text.split("\n").slice(0, 10);
    var delimiters = [",", "\t", ";", "|"];
    var scores = {};

    for (var d = 0; d < delimiters.length; d++) {
      var delim = delimiters[d];
      var counts = [];
      for (var i = 0; i < lines.length; i++) {
        if (lines[i].trim().length === 0) continue;
        var count = 0;
        var inQuotes = false;
        for (var c = 0; c < lines[i].length; c++) {
          if (lines[i][c] === '"') inQuotes = !inQuotes;
          if (!inQuotes && lines[i][c] === delim) count++;
        }
        counts.push(count);
      }
      if (counts.length === 0) { scores[delim] = 0; continue; }
      var allSame = counts.every(function(v) { return v === counts[0]; });
      scores[delim] = allSame && counts[0] > 0 ? counts[0] * counts.length : 0;
    }

    var best = ",";
    var bestScore = 0;
    for (var key in scores) {
      if (scores[key] > bestScore) {
        bestScore = scores[key];
        best = key;
      }
    }
    return best;
  }

  function delimiterName(d) {
    if (d === ",") return "Comma";
    if (d === "\t") return "Tab (TSV)";
    if (d === ";") return "Semicolon";
    if (d === "|") return "Pipe";
    return d;
  }

  // --- CSV Parser (RFC 4180 compliant) ---

  function parseCSV(text, delimiter) {
    var rows = [];
    var row = [];
    var field = "";
    var inQuotes = false;
    var i = 0;
    var len = text.length;

    while (i < len) {
      var ch = text[i];

      if (inQuotes) {
        if (ch === '"') {
          if (i + 1 < len && text[i + 1] === '"') {
            // Escaped double quote
            field += '"';
            i += 2;
          } else {
            // End of quoted field
            inQuotes = false;
            i++;
          }
        } else {
          field += ch;
          i++;
        }
      } else {
        if (ch === '"') {
          inQuotes = true;
          i++;
        } else if (ch === delimiter) {
          row.push(field);
          field = "";
          i++;
        } else if (ch === "\r") {
          if (i + 1 < len && text[i + 1] === "\n") i++;
          row.push(field);
          field = "";
          rows.push(row);
          row = [];
          i++;
        } else if (ch === "\n") {
          row.push(field);
          field = "";
          rows.push(row);
          row = [];
          i++;
        } else {
          field += ch;
          i++;
        }
      }
    }

    // Push last field and row
    if (field.length > 0 || row.length > 0) {
      row.push(field);
      rows.push(row);
    }

    // Remove trailing empty row
    if (rows.length > 0) {
      var lastRow = rows[rows.length - 1];
      if (lastRow.length === 1 && lastRow[0].trim() === "") {
        rows.pop();
      }
    }

    return rows;
  }

  // --- Conversion to JSON ---

  function csvToJsonObjects(rows, useHeaders) {
    if (useHeaders) {
      if (rows.length < 2) return [];
      var headers = rows[0].map(function(h) { return h.trim(); });
      var result = [];
      for (var i = 1; i < rows.length; i++) {
        var obj = {};
        for (var j = 0; j < headers.length; j++) {
          var val = j < rows[i].length ? rows[i][j].trim() : "";
          obj[headers[j]] = autoType(val);
        }
        result.push(obj);
      }
      return result;
    } else {
      // No headers: generate col_0, col_1, etc.
      if (rows.length < 1) return [];
      var maxCols = 0;
      for (var m = 0; m < rows.length; m++) {
        if (rows[m].length > maxCols) maxCols = rows[m].length;
      }
      var genHeaders = [];
      for (var g = 0; g < maxCols; g++) {
        genHeaders.push("col_" + g);
      }
      var res = [];
      for (var r = 0; r < rows.length; r++) {
        var o = {};
        for (var c = 0; c < genHeaders.length; c++) {
          var v = c < rows[r].length ? rows[r][c].trim() : "";
          o[genHeaders[c]] = autoType(v);
        }
        res.push(o);
      }
      return res;
    }
  }

  function csvToJsonArrays(rows, useHeaders) {
    var startIdx = useHeaders ? 1 : 0;
    var result = [];
    for (var i = startIdx; i < rows.length; i++) {
      var arr = [];
      for (var j = 0; j < rows[i].length; j++) {
        arr.push(rows[i][j].trim());
      }
      result.push(arr);
    }
    return result;
  }

  function autoType(val) {
    if (val === "") return val;
    if (val === "true") return true;
    if (val === "false") return false;
    if (val === "null") return null;
    if (val !== "" && !isNaN(val) && val.trim() !== "") {
      return Number(val);
    }
    return val;
  }

  // --- Syntax Highlighting ---

  function highlightJson(json) {
    var str = json
      .replace(/&/g, "&amp;")
      .replace(/</g, "&lt;")
      .replace(/>/g, "&gt;");

    return str.replace(
      /("(\\u[a-fA-F0-9]{4}|\\[^u]|[^\\"])*"(\s*:)?|\b(true|false|null)\b|-?\d+(?:\.\d*)?(?:[eE][+\-]?\d+)?)/g,
      function(match) {
        var cls = "ctj-number";
        if (/^"/.test(match)) {
          if (/:$/.test(match)) {
            cls = "ctj-key";
          } else {
            cls = "ctj-string";
          }
        } else if (/true|false/.test(match)) {
          cls = "ctj-boolean";
        } else if (/null/.test(match)) {
          cls = "ctj-null";
        }
        return '<span class="' + cls + '">' + match + '</span>';
      }
    );
  }

  // --- Update input size ---

  function updateInputSize() {
    var size = byteSize(inputEl.value);
    document.getElementById("ctjInputSize").textContent = formatBytes(size);
  }

  inputEl.addEventListener("input", updateInputSize);

  // --- Get indent setting ---

  function getIndent() {
    var val = document.getElementById("ctjIndent").value;
    if (val === "0") return undefined;
    if (val === "tab") return "\t";
    return parseInt(val, 10);
  }

  // --- Main Convert ---

  window.ctjConvert = function() {
    var raw = inputEl.value.trim();
    errorEl.style.display = "none";

    if (!raw) {
      statusEl.className = "ctj-status-msg ctj-status-empty";
      statusEl.innerHTML = "Paste CSV and click Convert";
      outputEl.textContent = "";
      delimBadge.style.display = "none";
      document.getElementById("ctjRowCount").textContent = "0";
      document.getElementById("ctjColCount").textContent = "0";
      document.getElementById("ctjByteSize").textContent = "0 B";
      document.getElementById("ctjOutputSize").textContent = "0 bytes";
      lastJson = "";
      return;
    }

    // Determine delimiter
    var delimSelect = document.getElementById("ctjDelimiter").value;
    var delimiter;
    if (delimSelect === "auto") {
      delimiter = detectDelimiter(raw);
    } else {
      delimiter = delimSelect;
    }

    delimBadge.textContent = "Detected: " + delimiterName(delimiter);
    delimBadge.style.display = "inline-flex";

    // Parse
    var rows;
    try {
      rows = parseCSV(raw, delimiter);
    } catch (e) {
      errorEl.textContent = "Parse error: " + e.message;
      errorEl.style.display = "block";
      statusEl.className = "ctj-status-msg ctj-status-invalid";
      statusEl.innerHTML = "&#10008; Parse error";
      return;
    }

    var useHeaders = document.getElementById("ctjHeaders").checked;
    var outputFormat = document.getElementById("ctjOutputFormat").value;

    // Validate minimum rows
    var minRows = useHeaders ? 2 : 1;
    if (rows.length < minRows) {
      var msg = useHeaders
        ? "CSV must have at least a header row and one data row when 'First row as headers' is on."
        : "CSV must have at least one data row.";
      errorEl.textContent = msg;
      errorEl.style.display = "block";
      statusEl.className = "ctj-status-msg ctj-status-invalid";
      statusEl.innerHTML = "&#10008; Not enough rows";
      return;
    }

    // Convert
    var jsonData;
    if (outputFormat === "objects") {
      jsonData = csvToJsonObjects(rows, useHeaders);
    } else {
      jsonData = csvToJsonArrays(rows, useHeaders);
    }

    var indent = getIndent();
    var jsonStr = JSON.stringify(jsonData, null, indent);
    lastJson = jsonStr;

    // Output with highlighting
    if (indent === undefined) {
      // Minified: no highlighting, just escaped text
      outputEl.textContent = jsonStr;
    } else {
      outputEl.innerHTML = highlightJson(jsonStr);
    }

    // Stats
    var dataRows = useHeaders ? rows.length - 1 : rows.length;
    var cols = rows.length > 0 ? rows[0].length : 0;
    document.getElementById("ctjRowCount").textContent = dataRows;
    document.getElementById("ctjColCount").textContent = cols;
    var outSize = byteSize(jsonStr);
    document.getElementById("ctjByteSize").textContent = formatBytes(outSize);
    document.getElementById("ctjOutputSize").textContent = formatBytes(outSize);

    // Status
    statusEl.className = "ctj-status-msg ctj-status-valid";
    statusEl.innerHTML = "&#10004; Converted " + dataRows + " rows, " + cols + " columns";
  };

  // --- Copy ---

  window.ctjCopy = function() {
    if (!lastJson) return;
    var copyBtn = document.getElementById("ctjCopyBtn");
    var copyLabel = document.getElementById("ctjCopyLabel");

    navigator.clipboard.writeText(lastJson).then(function() {
      copyBtn.classList.add("copied");
      copyLabel.textContent = "Copied!";
      setTimeout(function() {
        copyBtn.classList.remove("copied");
        copyLabel.textContent = "Copy to Clipboard";
      }, 2000);
    });
  };

  // --- Download ---

  window.ctjDownload = function() {
    if (!lastJson) return;
    var blob = new Blob([lastJson], { type: "application/json" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "data.json";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  // --- Load Sample ---

  window.ctjLoadSample = function() {
    inputEl.value = SAMPLE_CSV;
    updateInputSize();
    ctjConvert();
  };

  // --- Clear ---

  window.ctjClear = function() {
    inputEl.value = "";
    outputEl.textContent = "";
    errorEl.style.display = "none";
    delimBadge.style.display = "none";
    statusEl.className = "ctj-status-msg ctj-status-empty";
    statusEl.innerHTML = "Paste CSV and click Convert";
    document.getElementById("ctjInputSize").textContent = "0 bytes";
    document.getElementById("ctjOutputSize").textContent = "0 bytes";
    document.getElementById("ctjRowCount").textContent = "0";
    document.getElementById("ctjColCount").textContent = "0";
    document.getElementById("ctjByteSize").textContent = "0 B";
    lastJson = "";
  };

  // --- File Upload ---

  fileInput.addEventListener("change", function(e) {
    var file = e.target.files[0];
    if (!file) return;
    var reader = new FileReader();
    reader.onload = function(ev) {
      inputEl.value = ev.target.result;
      updateInputSize();
      ctjConvert();
    };
    reader.readAsText(file);
    fileInput.value = "";
  });

  // --- Drag & Drop ---

  dropZone.addEventListener("dragover", function(e) {
    e.preventDefault();
    dropZone.classList.add("dragover");
  });

  dropZone.addEventListener("dragleave", function() {
    dropZone.classList.remove("dragover");
  });

  dropZone.addEventListener("drop", function(e) {
    e.preventDefault();
    dropZone.classList.remove("dragover");
    var file = e.dataTransfer.files[0];
    if (!file) return;
    var reader = new FileReader();
    reader.onload = function(ev) {
      inputEl.value = ev.target.result;
      updateInputSize();
      ctjConvert();
    };
    reader.readAsText(file);
  });

  // --- Auto-convert on option change ---

  document.getElementById("ctjHeaders").addEventListener("change", function() {
    if (inputEl.value.trim()) ctjConvert();
  });

  document.getElementById("ctjOutputFormat").addEventListener("change", function() {
    if (inputEl.value.trim()) ctjConvert();
  });

  document.getElementById("ctjIndent").addEventListener("change", function() {
    if (inputEl.value.trim()) ctjConvert();
  });

  document.getElementById("ctjDelimiter").addEventListener("change", function() {
    if (inputEl.value.trim()) ctjConvert();
  });

})();
</script>
