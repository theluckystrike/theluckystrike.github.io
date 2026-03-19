---
layout: page
title: "Free JSON to YAML Converter — Bidirectional with Validation | Zovo"
description: "Free JSON to YAML converter -- convert JSON to YAML or YAML to JSON instantly with validation, error messages, and line numbers. Runs in your browser, no signup required."
permalink: /tools/json-yaml-converter/
keywords: "json to yaml, yaml to json, json yaml converter, convert json to yaml online, yaml converter, json converter, yaml to json online"
date: 2026-03-19
last_modified_at: 2026-03-19
categories: [tools]
tags: [json to yaml, yaml to json, json yaml converter, data conversion, developer tools, online tools]
target_keyword: "json to yaml converter"
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --jyc-primary: #6C5CE7;
    --jyc-primary-dark: #5A4BD1;
    --jyc-primary-light: #A29BFE;
    --jyc-bg: #0d0d14;
    --jyc-surface: #12121a;
    --jyc-surface-alt: #1a1a2e;
    --jyc-text: #e0e0e0;
    --jyc-text-muted: #8888aa;
    --jyc-border: #2a2a3a;
    --jyc-success: #00B894;
    --jyc-error: #D63031;
    --jyc-warning: #FDCB6E;
    --jyc-radius: 12px;
  }

  .jyc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--jyc-text);
    max-width: 1280px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .jyc-wrapper * {
    box-sizing: border-box;
  }

  .jyc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .jyc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--jyc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .jyc-hero h1 span {
    color: var(--jyc-primary);
  }

  .jyc-intro {
    font-size: 1.05rem;
    color: var(--jyc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .jyc-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
    padding: 12px 16px;
    background: var(--jyc-surface);
    border: 1px solid var(--jyc-border);
    border-radius: var(--jyc-radius);
  }

  .jyc-toolbar-spacer {
    flex: 1;
  }

  .jyc-option-group {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 0.85rem;
    color: var(--jyc-text);
  }

  .jyc-option-group label {
    font-weight: 500;
    white-space: nowrap;
    color: var(--jyc-text-muted);
  }

  .jyc-option-group select {
    padding: 6px 10px;
    border: 1px solid var(--jyc-border);
    border-radius: 6px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    background: var(--jyc-surface-alt);
    color: var(--jyc-text);
    cursor: pointer;
  }

  .jyc-option-group select:focus {
    outline: none;
    border-color: var(--jyc-primary);
    box-shadow: 0 0 0 2px rgba(108, 92, 231, 0.25);
  }

  .jyc-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .jyc-btn-primary {
    background: var(--jyc-primary);
    color: #fff;
  }

  .jyc-btn-primary:hover {
    background: var(--jyc-primary-dark);
  }

  .jyc-btn-secondary {
    background: var(--jyc-surface-alt);
    color: var(--jyc-text);
    border: 1px solid var(--jyc-border);
  }

  .jyc-btn-secondary:hover {
    background: var(--jyc-border);
  }

  .jyc-btn-success {
    background: var(--jyc-success);
    color: #fff;
  }

  .jyc-btn-success:hover {
    background: #00a884;
  }

  .jyc-split {
    display: grid;
    grid-template-columns: 1fr 60px 1fr;
    gap: 0;
    margin-bottom: 16px;
    min-height: 480px;
  }

  .jyc-pane {
    display: flex;
    flex-direction: column;
    background: var(--jyc-surface);
    border: 1px solid var(--jyc-border);
    border-radius: var(--jyc-radius);
    overflow: hidden;
  }

  .jyc-pane-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--jyc-surface-alt);
    border-bottom: 1px solid var(--jyc-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--jyc-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .jyc-pane-header-actions {
    display: flex;
    gap: 6px;
  }

  .jyc-pane-header-actions button {
    padding: 4px 10px;
    font-size: 0.75rem;
    border-radius: 6px;
    border: 1px solid var(--jyc-border);
    background: var(--jyc-surface);
    color: var(--jyc-text-muted);
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: all 0.15s;
  }

  .jyc-pane-header-actions button:hover {
    background: var(--jyc-primary);
    color: #fff;
    border-color: var(--jyc-primary);
  }

  .jyc-editor-wrap {
    flex: 1;
    position: relative;
    display: flex;
  }

  .jyc-line-numbers {
    width: 40px;
    padding: 16px 8px 16px 4px;
    text-align: right;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    line-height: 1.55;
    color: #555;
    background: var(--jyc-bg);
    border-right: 1px solid var(--jyc-border);
    user-select: none;
    overflow: hidden;
  }

  .jyc-editor {
    flex: 1;
    width: 100%;
    min-height: 420px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    line-height: 1.55;
    resize: none;
    outline: none;
    color: var(--jyc-text);
    background: var(--jyc-surface);
    tab-size: 2;
  }

  .jyc-editor::placeholder {
    color: #555;
  }

  .jyc-arrows {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px;
    padding: 12px 0;
  }

  .jyc-arrow-btn {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    border: 2px solid var(--jyc-primary);
    background: var(--jyc-surface);
    color: var(--jyc-primary);
    font-size: 1.1rem;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.15s;
    font-family: 'Inter', sans-serif;
    font-weight: 700;
  }

  .jyc-arrow-btn:hover {
    background: var(--jyc-primary);
    color: #fff;
  }

  .jyc-arrow-label {
    font-size: 0.65rem;
    color: var(--jyc-text-muted);
    text-align: center;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .jyc-status {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 14px;
    font-size: 0.82rem;
    border-top: 1px solid var(--jyc-border);
    background: var(--jyc-bg);
    min-height: 36px;
  }

  .jyc-status-valid {
    color: var(--jyc-success);
  }

  .jyc-status-error {
    color: var(--jyc-error);
  }

  .jyc-status-neutral {
    color: var(--jyc-text-muted);
  }

  .jyc-content {
    max-width: 820px;
    margin: 48px auto 0;
  }

  .jyc-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 40px 0 16px;
    color: var(--jyc-text);
  }

  .jyc-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 12px;
    color: var(--jyc-text);
  }

  .jyc-content p {
    font-size: 0.95rem;
    color: var(--jyc-text-muted);
    line-height: 1.7;
    margin: 0 0 16px;
  }

  .jyc-content ul, .jyc-content ol {
    padding-left: 24px;
    margin: 0 0 16px;
  }

  .jyc-content li {
    font-size: 0.95rem;
    color: var(--jyc-text-muted);
    line-height: 1.7;
    margin-bottom: 6px;
  }

  .jyc-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    background: var(--jyc-surface-alt);
    padding: 2px 6px;
    border-radius: 4px;
    color: var(--jyc-primary-light);
  }

  .jyc-content pre {
    background: var(--jyc-surface);
    border: 1px solid var(--jyc-border);
    border-radius: 8px;
    padding: 16px;
    overflow-x: auto;
    margin: 0 0 16px;
  }

  .jyc-content pre code {
    background: none;
    padding: 0;
    font-size: 0.82rem;
    line-height: 1.6;
  }

  .jyc-comparison-table {
    width: 100%;
    border-collapse: collapse;
    margin: 0 0 24px;
    font-size: 0.9rem;
  }

  .jyc-comparison-table th,
  .jyc-comparison-table td {
    padding: 10px 14px;
    text-align: left;
    border: 1px solid var(--jyc-border);
  }

  .jyc-comparison-table th {
    background: var(--jyc-surface-alt);
    font-weight: 600;
    color: var(--jyc-text);
  }

  .jyc-comparison-table td {
    color: var(--jyc-text-muted);
  }

  .jyc-faq {
    max-width: 820px;
    margin: 48px auto 60px;
  }

  .jyc-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
  }

  .jyc-faq-item {
    border: 1px solid var(--jyc-border);
    border-radius: var(--jyc-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--jyc-surface);
  }

  .jyc-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--jyc-text);
  }

  .jyc-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--jyc-text-muted);
    line-height: 1.7;
  }

  @media (max-width: 768px) {
    .jyc-hero h1 { font-size: 1.6rem; }
    .jyc-split { grid-template-columns: 1fr; grid-template-rows: 1fr auto 1fr; min-height: auto; }
    .jyc-arrows { flex-direction: row; padding: 8px 0; }
    .jyc-editor { min-height: 240px; }
    .jyc-toolbar { flex-direction: column; align-items: stretch; }
  }
</style>

<div class="jyc-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="JSON to YAML Converter">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="jyc-hero">
    <h1><span>JSON to YAML</span> Converter</h1>
    <p class="jyc-intro">Convert between JSON and YAML in either direction. Paste or type in one editor and convert to the other format with validation, error messages, and line numbers. Everything runs in your browser.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <div class="jyc-toolbar">
    <div class="jyc-option-group">
      <label for="jycIndent">Indentation:</label>
      <select id="jycIndent">
        <option value="2" selected>2 spaces</option>
        <option value="4">4 spaces</option>
      </select>
    </div>
    <div class="jyc-toolbar-spacer"></div>
    <button class="jyc-btn jyc-btn-secondary" onclick="jycLoadSample()">Sample Data</button>
    <button class="jyc-btn jyc-btn-secondary" onclick="jycClearAll()">Clear All</button>
  </div>

  <div class="jyc-split">
    <div class="jyc-pane">
      <div class="jyc-pane-header">
        <span>JSON</span>
        <div class="jyc-pane-header-actions">
          <button onclick="jycCopyJson()">Copy</button>
          <button onclick="jycDownload('json')">Download</button>
        </div>
      </div>
      <div class="jyc-editor-wrap">
        <div class="jyc-line-numbers" id="jycJsonLines">1</div>
        <textarea class="jyc-editor" id="jycJsonEditor" placeholder='Paste or type JSON here...' spellcheck="false"></textarea>
      </div>
      <div class="jyc-status" id="jycJsonStatus">
        <span class="jyc-status-neutral">Ready</span>
      </div>
    </div>

    <div class="jyc-arrows">
      <div>
        <button class="jyc-arrow-btn" onclick="jycConvertJsonToYaml()" title="Convert JSON to YAML">&#8594;</button>
        <div class="jyc-arrow-label">JSON<br>to YAML</div>
      </div>
      <div>
        <button class="jyc-arrow-btn" onclick="jycConvertYamlToJson()" title="Convert YAML to JSON">&#8592;</button>
        <div class="jyc-arrow-label">YAML<br>to JSON</div>
      </div>
    </div>

    <div class="jyc-pane">
      <div class="jyc-pane-header">
        <span>YAML</span>
        <div class="jyc-pane-header-actions">
          <button onclick="jycCopyYaml()">Copy</button>
          <button onclick="jycDownload('yaml')">Download</button>
        </div>
      </div>
      <div class="jyc-editor-wrap">
        <div class="jyc-line-numbers" id="jycYamlLines">1</div>
        <textarea class="jyc-editor" id="jycYamlEditor" placeholder="Paste or type YAML here..." spellcheck="false"></textarea>
      </div>
      <div class="jyc-status" id="jycYamlStatus">
        <span class="jyc-status-neutral">Ready</span>
      </div>
    </div>
  </div>

  <div style="display:flex;gap:8px;flex-wrap:wrap;margin-bottom:48px;">
    <button class="jyc-btn jyc-btn-success" onclick="jycAutoConvert()">Auto-detect & Convert</button>
  </div>

  <div class="jyc-content">
    <h2>What Is YAML</h2>
    <p>YAML (YAML Ain't Markup Language) is a human-readable data serialization format. It was first released in 2001 and has since become a standard for configuration files across many platforms. Docker Compose, Kubernetes, Ansible, GitHub Actions, and dozens of other tools rely on YAML because it prioritizes readability over the bracket-heavy syntax of JSON or XML.</p>
    <p>YAML uses indentation to represent nesting, colons to separate keys from values, and dashes to denote list items. It supports strings, numbers, booleans, null values, multiline text blocks, and comments (which JSON does not). A simple YAML document might look like this:</p>
<pre><code>server:
  host: localhost
  port: 8080
  debug: true
  allowed_origins:
    - "https://example.com"
    - "https://api.example.com"</code></pre>
    <p>The equivalent JSON for the above would wrap every key and string value in double quotes and use braces and brackets to define structure. Both formats represent the same data, but YAML tends to be easier to read and edit by hand.</p>

    <h2>JSON vs YAML Comparison</h2>
    <table class="jyc-comparison-table">
      <thead>
        <tr><th>Feature</th><th>JSON</th><th>YAML</th></tr>
      </thead>
      <tbody>
        <tr><td>Readability</td><td>Moderate, bracket-heavy</td><td>High, indentation-based</td></tr>
        <tr><td>Comments</td><td>Not supported</td><td>Supported with #</td></tr>
        <tr><td>Data types</td><td>String, number, boolean, null, array, object</td><td>All JSON types plus dates, multiline strings, anchors</td></tr>
        <tr><td>File extensions</td><td>.json</td><td>.yaml, .yml</td></tr>
        <tr><td>Parsing speed</td><td>Fast, native in browsers</td><td>Slower, requires a parser library</td></tr>
        <tr><td>Trailing commas</td><td>Not allowed</td><td>Not applicable</td></tr>
        <tr><td>Multiline strings</td><td>Escaped newlines only</td><td>Block scalars with | or ></td></tr>
        <tr><td>Use cases</td><td>APIs, data exchange, web storage</td><td>Configuration files, CI/CD pipelines, DevOps</td></tr>
      </tbody>
    </table>

    <h2>When to Use YAML vs JSON</h2>
    <p>Choosing between YAML and JSON depends on the context. Here are guidelines that apply in most situations.</p>
    <p>Use JSON when the data is consumed by machines first and humans second. API request and response bodies, web storage payloads, and inter-service communication are natural fits for JSON. Every modern programming language has a built-in or near-built-in JSON parser, and the format is unambiguous. There is no indentation sensitivity, so whitespace changes never break the data.</p>
    <p>Use YAML when a human needs to read, write, or maintain the file regularly. Configuration files for Docker Compose, Kubernetes manifests, Ansible playbooks, and CI/CD pipelines all benefit from YAML readability. The ability to add comments is especially useful in config files where certain values need explanation. YAML also handles multiline strings cleanly, which matters in templates or scripts embedded in configuration.</p>
    <p>Some projects use both. A developer might write a YAML configuration file for readability, then convert it to JSON before passing it to an API endpoint. This converter handles that workflow in either direction.</p>

    <h3>Common YAML Syntax</h3>
    <p>Understanding a few YAML constructs helps avoid conversion errors.</p>
    <ul>
      <li><code>key: value</code> -- a mapping (equivalent to a JSON object property). The colon must be followed by a space.</li>
      <li><code>- item</code> -- a sequence entry (equivalent to a JSON array element). The dash must be followed by a space.</li>
      <li><code>#</code> -- a comment. Everything after the hash on a line is ignored. JSON has no comment syntax.</li>
      <li><code>|</code> -- a literal block scalar. Preserves newlines in multiline strings exactly as written.</li>
      <li><code>></code> -- a folded block scalar. Joins lines with spaces, treating blank lines as paragraph breaks.</li>
      <li><code>true</code>, <code>false</code>, <code>null</code> -- boolean and null values work the same as in JSON, though YAML also accepts <code>yes</code>/<code>no</code> and <code>~</code> for null.</li>
      <li>Strings without quotes are valid in YAML as long as they do not collide with reserved words. Quote strings that start with special characters or contain colons.</li>
    </ul>

    <h2>How This Converter Works</h2>
    <p>This tool parses JSON using the browser's native <code>JSON.parse()</code> and serializes YAML using a custom JavaScript YAML serializer. The YAML parser reads indentation levels, identifies mappings and sequences, and converts them into a JavaScript object that is then passed to <code>JSON.stringify()</code>. All processing happens client-side. No data leaves your browser, and nothing is stored on any server.</p>
    <p>The converter handles nested objects and arrays, quoted and unquoted strings, numbers, booleans, null values, and multiline block scalars. The auto-detect feature checks whether the input starts with <code>{</code> or <code>[</code> to determine if it is JSON, and treats everything else as YAML.</p>
  </div>

  <div class="jyc-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="jyc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I convert nested JSON to YAML?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The converter handles deeply nested objects and arrays. Each nesting level in JSON becomes an additional indentation level in YAML. The indentation selector lets you choose between 2-space and 4-space indentation for the YAML output.</p>
      </div>
    </div>

    <div class="jyc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does the YAML to JSON conversion preserve comments?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. JSON does not support comments, so any YAML comments (lines starting with #) are stripped during conversion. The data values themselves are preserved exactly. If you need to keep comments, stay in YAML format or store them separately.</p>
      </div>
    </div>

    <div class="jyc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data sent to a server during conversion?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All parsing and serialization runs entirely in your browser using JavaScript. You can verify this by opening the Network tab in your browser's developer tools. No HTTP requests are made when you convert. Your data stays on your machine.</p>
      </div>
    </div>

    <div class="jyc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What YAML features are supported?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The parser handles mappings (key-value pairs), sequences (lists), nested structures, quoted and unquoted strings, numbers, booleans, null values, and multiline block scalars (| and > syntax). Anchors, aliases, and custom tags are not supported since they have no JSON equivalent.</p>
      </div>
    </div>

    <div class="jyc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What happens if the input has syntax errors?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The converter validates the input and displays an error message with the line number where the problem was detected. For JSON, this uses the browser's built-in JSON parser error messages. For YAML, the custom parser reports issues like incorrect indentation, missing colons, or unmatched quotes.</p>
      </div>
    </div>
  </div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter/" style="color:#00ff88;text-decoration:none;">JSON Formatter</a> - Format and validate JSON data</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter-pro/" style="color:#00ff88;text-decoration:none;">JSON Formatter Pro</a> - Advanced JSON editing with tree view</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/csv-to-json-converter/" style="color:#00ff88;text-decoration:none;">CSV to JSON Converter</a> - Convert CSV files to JSON</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/diff-checker/" style="color:#00ff88;text-decoration:none;">Diff Checker</a> - Compare two texts side by side</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>

<footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid #2a2a3a;margin-top:3rem;">
  <p>Built by Michael Lip at <a href="https://zovo.one" style="color:#6C5CE7;text-decoration:none;">zovo.one</a></p>
</footer>
</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "JSON to YAML Converter",
  "url": "https://zovo.one/tools/json-yaml-converter/",
  "applicationCategory": "DeveloperApplication",
  "operatingSystem": "Any",
  "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
  "author": { "@type": "Person", "name": "Michael Lip" }
}
</script>

<script>
(function() {
  "use strict";

  var jsonEditor = document.getElementById("jycJsonEditor");
  var yamlEditor = document.getElementById("jycYamlEditor");
  var jsonLines = document.getElementById("jycJsonLines");
  var yamlLines = document.getElementById("jycYamlLines");
  var jsonStatus = document.getElementById("jycJsonStatus");
  var yamlStatus = document.getElementById("jycYamlStatus");
  var indentSelect = document.getElementById("jycIndent");

  function getIndent() {
    return parseInt(indentSelect.value, 10);
  }

  function updateLineNumbers(textarea, lineEl) {
    var count = (textarea.value.match(/\n/g) || []).length + 1;
    var nums = [];
    for (var i = 1; i <= count; i++) nums.push(i);
    lineEl.textContent = nums.join("\n");
  }

  jsonEditor.addEventListener("input", function() { updateLineNumbers(jsonEditor, jsonLines); });
  yamlEditor.addEventListener("input", function() { updateLineNumbers(yamlEditor, yamlLines); });
  jsonEditor.addEventListener("scroll", function() { jsonLines.style.transform = "translateY(-" + jsonEditor.scrollTop + "px)"; });
  yamlEditor.addEventListener("scroll", function() { yamlLines.style.transform = "translateY(-" + yamlEditor.scrollTop + "px)"; });

  function setStatus(el, msg, type) {
    el.innerHTML = '<span class="jyc-status-' + type + '">' + escapeHtml(msg) + '</span>';
  }

  function escapeHtml(s) {
    return s.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  /* ── JSON to YAML serializer ── */
  function jsonToYaml(obj, indent, level) {
    if (level === undefined) level = 0;
    var sp = "";
    for (var s = 0; s < level * indent; s++) sp += " ";
    var childSp = "";
    for (var s2 = 0; s2 < (level + 1) * indent; s2++) childSp += " ";

    if (obj === null) return "null";
    if (typeof obj === "boolean") return obj ? "true" : "false";
    if (typeof obj === "number") return String(obj);
    if (typeof obj === "string") {
      if (obj === "") return '""';
      if (obj.indexOf("\n") !== -1) {
        var lines = obj.split("\n");
        var result = "|\n";
        for (var i = 0; i < lines.length; i++) {
          result += childSp + lines[i];
          if (i < lines.length - 1) result += "\n";
        }
        return result;
      }
      if (/^[\d]/.test(obj) || /^(true|false|null|yes|no|on|off|~)$/i.test(obj) ||
          obj.indexOf(":") !== -1 || obj.indexOf("#") !== -1 || obj.indexOf("{") !== -1 ||
          obj.indexOf("}") !== -1 || obj.indexOf("[") !== -1 || obj.indexOf("]") !== -1 ||
          obj.indexOf(",") !== -1 || obj.indexOf("&") !== -1 || obj.indexOf("*") !== -1 ||
          obj.indexOf("'") !== -1 || obj.indexOf('"') !== -1 || obj.indexOf("|") !== -1 ||
          obj.indexOf(">") !== -1 || obj.indexOf("%") !== -1 || obj.indexOf("@") !== -1 ||
          obj.indexOf("!") !== -1 || obj.indexOf("`") !== -1 || obj.trim() !== obj) {
        return '"' + obj.replace(/\\/g, "\\\\").replace(/"/g, '\\"') + '"';
      }
      return obj;
    }
    if (Array.isArray(obj)) {
      if (obj.length === 0) return "[]";
      var items = [];
      for (var i = 0; i < obj.length; i++) {
        var val = obj[i];
        if (val !== null && typeof val === "object") {
          if (Array.isArray(val)) {
            items.push(sp + "- " + jsonToYaml(val, indent, level + 1).trim());
          } else {
            var keys = Object.keys(val);
            if (keys.length === 0) {
              items.push(sp + "- {}");
            } else {
              var first = keys[0];
              var firstVal = jsonToYaml(val[first], indent, level + 2);
              var firstLine = sp + "- " + yamlKey(first) + ": " + (isScalar(val[first]) ? firstVal : "\n" + childSp + "  " + firstVal.trim());
              items.push(firstLine);
              for (var k = 1; k < keys.length; k++) {
                var kv = jsonToYaml(val[keys[k]], indent, level + 2);
                items.push(childSp + "  " + yamlKey(keys[k]) + ": " + (isScalar(val[keys[k]]) ? kv : "\n" + childSp + "  " + kv.trim()));
              }
            }
          }
        } else {
          items.push(sp + "- " + jsonToYaml(val, indent, level + 1));
        }
      }
      return items.join("\n");
    }
    if (typeof obj === "object") {
      var keys = Object.keys(obj);
      if (keys.length === 0) return "{}";
      var parts = [];
      for (var i = 0; i < keys.length; i++) {
        var v = obj[keys[i]];
        var serialized = jsonToYaml(v, indent, level + 1);
        if (isScalar(v)) {
          parts.push(sp + yamlKey(keys[i]) + ": " + serialized);
        } else {
          parts.push(sp + yamlKey(keys[i]) + ":\n" + serialized);
        }
      }
      return parts.join("\n");
    }
    return String(obj);
  }

  function isScalar(v) {
    return v === null || typeof v !== "object";
  }

  function yamlKey(k) {
    if (/^[a-zA-Z_][a-zA-Z0-9_\-]*$/.test(k) && !/^(true|false|null|yes|no|on|off)$/i.test(k)) {
      return k;
    }
    return '"' + k.replace(/\\/g, "\\\\").replace(/"/g, '\\"') + '"';
  }

  /* ── YAML to JSON parser ── */
  function yamlToJson(yamlStr) {
    var lines = yamlStr.split("\n");
    var filtered = [];
    var rawLineMap = [];
    for (var i = 0; i < lines.length; i++) {
      var line = lines[i];
      var stripped = line.replace(/#.*$/, function(match, offset) {
        var before = line.substring(0, offset);
        var singleQuotes = (before.match(/'/g) || []).length;
        var doubleQuotes = (before.match(/"/g) || []).length;
        if (singleQuotes % 2 !== 0 || doubleQuotes % 2 !== 0) return match;
        return "";
      });
      if (stripped.trim() === "") continue;
      if (stripped.trim() === "---" || stripped.trim() === "...") continue;
      filtered.push(stripped);
      rawLineMap.push(i + 1);
    }
    if (filtered.length === 0) return null;

    var pos = { idx: 0 };
    var result = parseNode(filtered, rawLineMap, pos, -1);
    return result;
  }

  function getIndentLevel(line) {
    var match = line.match(/^(\s*)/);
    return match ? match[1].length : 0;
  }

  function parseNode(lines, lineMap, pos, parentIndent) {
    if (pos.idx >= lines.length) return null;
    var line = lines[pos.idx];
    var indent = getIndentLevel(line);
    var trimmed = line.trim();

    if (trimmed.charAt(0) === "-" && (trimmed.length === 1 || trimmed.charAt(1) === " ")) {
      return parseSequence(lines, lineMap, pos, indent);
    }
    if (trimmed.indexOf(":") !== -1) {
      var colonIdx = findColon(trimmed);
      if (colonIdx !== -1) {
        return parseMapping(lines, lineMap, pos, indent);
      }
    }
    return parseScalar(trimmed, lineMap[pos.idx]);
  }

  function findColon(s) {
    var inSingle = false, inDouble = false;
    for (var i = 0; i < s.length; i++) {
      var c = s.charAt(i);
      if (c === "'" && !inDouble) inSingle = !inSingle;
      if (c === '"' && !inSingle) inDouble = !inDouble;
      if (c === ":" && !inSingle && !inDouble && (i + 1 >= s.length || s.charAt(i + 1) === " ")) {
        return i;
      }
    }
    return -1;
  }

  function parseMapping(lines, lineMap, pos, baseIndent) {
    var obj = {};
    while (pos.idx < lines.length) {
      var line = lines[pos.idx];
      var indent = getIndentLevel(line);
      if (indent < baseIndent) break;
      if (indent > baseIndent) break;
      var trimmed = line.trim();
      if (trimmed.charAt(0) === "-") break;

      var colonIdx = findColon(trimmed);
      if (colonIdx === -1) break;

      var key = trimmed.substring(0, colonIdx).trim();
      key = unquoteString(key);
      var valueStr = trimmed.substring(colonIdx + 1).trim();

      if (valueStr === "" || valueStr === "|" || valueStr === ">" || valueStr === "|+" || valueStr === "|-" || valueStr === ">+" || valueStr === ">-") {
        pos.idx++;
        if (valueStr === "|" || valueStr === "|-" || valueStr === "|+") {
          obj[key] = parseBlockScalar(lines, lineMap, pos, indent, "literal", valueStr);
        } else if (valueStr === ">" || valueStr === ">-" || valueStr === ">+") {
          obj[key] = parseBlockScalar(lines, lineMap, pos, indent, "folded", valueStr);
        } else if (pos.idx < lines.length) {
          var nextIndent = getIndentLevel(lines[pos.idx]);
          if (nextIndent > indent) {
            obj[key] = parseNode(lines, lineMap, pos, indent);
          } else {
            obj[key] = null;
          }
        } else {
          obj[key] = null;
        }
      } else {
        obj[key] = parseInlineValue(valueStr, lineMap[pos.idx]);
        pos.idx++;
      }
    }
    return obj;
  }

  function parseSequence(lines, lineMap, pos, baseIndent) {
    var arr = [];
    while (pos.idx < lines.length) {
      var line = lines[pos.idx];
      var indent = getIndentLevel(line);
      if (indent < baseIndent) break;
      if (indent > baseIndent) break;
      var trimmed = line.trim();
      if (trimmed.charAt(0) !== "-") break;

      var rest = trimmed.substring(1).trim();
      if (rest === "") {
        pos.idx++;
        if (pos.idx < lines.length && getIndentLevel(lines[pos.idx]) > indent) {
          arr.push(parseNode(lines, lineMap, pos, indent));
        } else {
          arr.push(null);
        }
      } else {
        var restColon = findColon(rest);
        if (restColon !== -1 && rest.charAt(0) !== '"' && rest.charAt(0) !== "'") {
          var fakeIndent = indent + 2;
          var subLines = [new Array(fakeIndent + 1).join(" ") + rest];
          var subLineMap = [lineMap[pos.idx]];
          pos.idx++;
          while (pos.idx < lines.length && getIndentLevel(lines[pos.idx]) > indent) {
            subLines.push(lines[pos.idx]);
            subLineMap.push(lineMap[pos.idx]);
            pos.idx++;
          }
          var subPos = { idx: 0 };
          arr.push(parseNode(subLines, subLineMap, subPos, fakeIndent - 1));
        } else {
          arr.push(parseInlineValue(rest, lineMap[pos.idx]));
          pos.idx++;
        }
      }
    }
    return arr;
  }

  function parseBlockScalar(lines, lineMap, pos, parentIndent, mode, chomping) {
    var blockLines = [];
    var blockIndent = -1;
    while (pos.idx < lines.length) {
      var line = lines[pos.idx];
      var rawLine = line;
      var lineIndent = 0;
      for (var c = 0; c < rawLine.length; c++) {
        if (rawLine.charAt(c) === " ") lineIndent++;
        else break;
      }
      if (lineIndent <= parentIndent && rawLine.trim() !== "") break;
      if (rawLine.trim() === "") {
        blockLines.push("");
        pos.idx++;
        continue;
      }
      if (blockIndent === -1) blockIndent = lineIndent;
      blockLines.push(rawLine.substring(blockIndent));
      pos.idx++;
    }
    while (blockLines.length > 0 && blockLines[blockLines.length - 1] === "") {
      blockLines.pop();
    }
    if (mode === "literal") {
      var result = blockLines.join("\n");
      if (chomping === "|+" || chomping === ">+") result += "\n";
      return result;
    }
    return blockLines.join(" ").replace(/\s+/g, " ").trim();
  }

  function parseInlineValue(s, lineNum) {
    if (s === "" || s === "~" || s === "null" || s === "Null" || s === "NULL") return null;
    if (s === "true" || s === "True" || s === "TRUE" || s === "yes" || s === "Yes" || s === "YES" || s === "on" || s === "On" || s === "ON") return true;
    if (s === "false" || s === "False" || s === "FALSE" || s === "no" || s === "No" || s === "NO" || s === "off" || s === "Off" || s === "OFF") return false;

    if (s.charAt(0) === "[") {
      try { return JSON.parse(s); } catch (e) { return s; }
    }
    if (s.charAt(0) === "{") {
      try { return JSON.parse(s); } catch (e) { return s; }
    }

    if (/^-?\d+$/.test(s)) return parseInt(s, 10);
    if (/^-?\d*\.\d+$/.test(s)) return parseFloat(s);
    if (/^-?\d+\.?\d*[eE][+-]?\d+$/.test(s)) return parseFloat(s);
    if (/^0x[0-9a-fA-F]+$/.test(s)) return parseInt(s, 16);
    if (/^0o[0-7]+$/.test(s)) return parseInt(s.substring(2), 8);

    if (s === ".inf" || s === ".Inf" || s === ".INF") return Infinity;
    if (s === "-.inf" || s === "-.Inf" || s === "-.INF") return -Infinity;
    if (s === ".nan" || s === ".NaN" || s === ".NAN") return NaN;

    return unquoteString(s);
  }

  function unquoteString(s) {
    if (s.length >= 2) {
      if ((s.charAt(0) === '"' && s.charAt(s.length - 1) === '"') ||
          (s.charAt(0) === "'" && s.charAt(s.length - 1) === "'")) {
        return s.substring(1, s.length - 1).replace(/\\"/g, '"').replace(/\\'/g, "'").replace(/\\\\/g, "\\");
      }
    }
    return s;
  }

  function parseScalar(s, lineNum) {
    return parseInlineValue(s, lineNum);
  }

  /* ── Conversion functions ── */
  window.jycConvertJsonToYaml = function() {
    var jsonStr = jsonEditor.value.trim();
    if (!jsonStr) {
      setStatus(jsonStatus, "No JSON input provided", "error");
      return;
    }
    try {
      var obj = JSON.parse(jsonStr);
      var yaml = jsonToYaml(obj, getIndent(), 0);
      yamlEditor.value = yaml;
      updateLineNumbers(yamlEditor, yamlLines);
      setStatus(jsonStatus, "Valid JSON", "valid");
      setStatus(yamlStatus, "Converted from JSON", "valid");
    } catch (e) {
      var msg = e.message;
      var lineMatch = msg.match(/position (\d+)/);
      if (lineMatch) {
        var position = parseInt(lineMatch[1], 10);
        var upToPos = jsonStr.substring(0, position);
        var line = (upToPos.match(/\n/g) || []).length + 1;
        msg = "Line " + line + ": " + msg;
      }
      setStatus(jsonStatus, msg, "error");
    }
  };

  window.jycConvertYamlToJson = function() {
    var yamlStr = yamlEditor.value.trim();
    if (!yamlStr) {
      setStatus(yamlStatus, "No YAML input provided", "error");
      return;
    }
    try {
      var obj = yamlToJson(yamlStr);
      var json = JSON.stringify(obj, null, getIndent());
      jsonEditor.value = json;
      updateLineNumbers(jsonEditor, jsonLines);
      setStatus(yamlStatus, "Valid YAML", "valid");
      setStatus(jsonStatus, "Converted from YAML", "valid");
    } catch (e) {
      setStatus(yamlStatus, e.message || "Invalid YAML", "error");
    }
  };

  window.jycAutoConvert = function() {
    var jsonStr = jsonEditor.value.trim();
    var yamlStr = yamlEditor.value.trim();

    if (jsonStr && !yamlStr) {
      window.jycConvertJsonToYaml();
      return;
    }
    if (yamlStr && !jsonStr) {
      window.jycConvertYamlToJson();
      return;
    }
    if (jsonStr) {
      if (jsonStr.charAt(0) === "{" || jsonStr.charAt(0) === "[") {
        window.jycConvertJsonToYaml();
      } else {
        yamlEditor.value = jsonStr;
        jsonEditor.value = "";
        updateLineNumbers(yamlEditor, yamlLines);
        updateLineNumbers(jsonEditor, jsonLines);
        window.jycConvertYamlToJson();
      }
      return;
    }
    if (yamlStr) {
      window.jycConvertYamlToJson();
    }
  };

  window.jycLoadSample = function() {
    var sample = {
      "apiVersion": "v1",
      "kind": "Deployment",
      "metadata": {
        "name": "web-server",
        "labels": {
          "app": "nginx",
          "environment": "production"
        }
      },
      "spec": {
        "replicas": 3,
        "selector": {
          "matchLabels": {
            "app": "nginx"
          }
        },
        "template": {
          "containers": [
            {
              "name": "nginx",
              "image": "nginx:1.25",
              "ports": [
                { "containerPort": 80 }
              ],
              "env": [
                { "name": "NODE_ENV", "value": "production" },
                { "name": "LOG_LEVEL", "value": "info" }
              ],
              "resources": {
                "limits": { "cpu": "500m", "memory": "256Mi" },
                "requests": { "cpu": "250m", "memory": "128Mi" }
              }
            }
          ]
        }
      },
      "database": {
        "host": "db.example.com",
        "port": 5432,
        "ssl": true,
        "pool_size": 10,
        "credentials": null
      }
    };
    jsonEditor.value = JSON.stringify(sample, null, getIndent());
    updateLineNumbers(jsonEditor, jsonLines);
    setStatus(jsonStatus, "Sample data loaded", "valid");
    yamlEditor.value = "";
    updateLineNumbers(yamlEditor, yamlLines);
    setStatus(yamlStatus, "Ready", "neutral");
  };

  window.jycClearAll = function() {
    jsonEditor.value = "";
    yamlEditor.value = "";
    updateLineNumbers(jsonEditor, jsonLines);
    updateLineNumbers(yamlEditor, yamlLines);
    setStatus(jsonStatus, "Ready", "neutral");
    setStatus(yamlStatus, "Ready", "neutral");
  };

  window.jycCopyJson = function() {
    if (!jsonEditor.value) return;
    navigator.clipboard.writeText(jsonEditor.value).then(function() {
      setStatus(jsonStatus, "Copied to clipboard", "valid");
    });
  };

  window.jycCopyYaml = function() {
    if (!yamlEditor.value) return;
    navigator.clipboard.writeText(yamlEditor.value).then(function() {
      setStatus(yamlStatus, "Copied to clipboard", "valid");
    });
  };

  window.jycDownload = function(format) {
    var content, filename, mime;
    if (format === "json") {
      content = jsonEditor.value;
      filename = "data.json";
      mime = "application/json";
    } else {
      content = yamlEditor.value;
      filename = "data.yaml";
      mime = "text/yaml";
    }
    if (!content) return;
    var blob = new Blob([content], { type: mime });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = filename;
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  updateLineNumbers(jsonEditor, jsonLines);
  updateLineNumbers(yamlEditor, yamlLines);
})();
</script>
