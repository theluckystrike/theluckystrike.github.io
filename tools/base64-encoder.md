---
layout: page
title: "Base64 Encoder Decoder - Free Online Tool | Zovo"
description: "Free base64 encoder decoder online. Encode text to base64, decode base64 to text, upload files to encode. Auto-detects base64 input. Runs in your browser."
permalink: /tools/base64-encoder/
keywords: "base64 encode decode, base64 encoder, base64 decoder, base64 online, encode base64, decode base64, base64 converter, base64 file encoder"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [base64 encoder, base64 decoder, base64 converter, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --b64-primary: #6C5CE7;
    --b64-primary-dark: #5A4BD1;
    --b64-primary-light: #A29BFE;
    --b64-bg: #F8F9FE;
    --b64-surface: #FFFFFF;
    --b64-text: #2D3436;
    --b64-text-muted: #636E72;
    --b64-border: #DFE6E9;
    --b64-success: #00B894;
    --b64-error: #D63031;
    --b64-warning: #FDCB6E;
    --b64-radius: 12px;
  }

  .b64-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--b64-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .b64-wrapper * {
    box-sizing: border-box;
  }

  .b64-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .b64-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--b64-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .b64-hero h1 span {
    color: var(--b64-primary);
  }

  .b64-intro {
    font-size: 1.05rem;
    color: var(--b64-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Mode Tabs */
  .b64-modes {
    display: flex;
    gap: 0;
    margin-bottom: 20px;
    border: 1px solid var(--b64-border);
    border-radius: 10px;
    overflow: hidden;
    max-width: 480px;
    margin-left: auto;
    margin-right: auto;
  }

  .b64-mode-btn {
    flex: 1;
    padding: 10px 20px;
    border: none;
    background: var(--b64-bg);
    color: var(--b64-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .b64-mode-btn:not(:last-child) {
    border-right: 1px solid var(--b64-border);
  }

  .b64-mode-btn.active {
    background: var(--b64-primary);
    color: #fff;
  }

  .b64-mode-btn:hover:not(.active) {
    background: #EEF0FB;
  }

  /* Toolbar */
  .b64-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .b64-btn {
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

  .b64-btn-primary {
    background: var(--b64-primary);
    color: #fff;
  }

  .b64-btn-primary:hover {
    background: var(--b64-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3);
  }

  .b64-btn-secondary {
    background: var(--b64-bg);
    color: var(--b64-text);
    border: 1px solid var(--b64-border);
  }

  .b64-btn-secondary:hover {
    background: #EEF0FB;
    border-color: var(--b64-primary-light);
  }

  .b64-btn.copied {
    background: var(--b64-success);
    color: #fff;
  }

  .b64-toolbar-spacer {
    flex: 1;
  }

  .b64-link-btn {
    background: none;
    border: none;
    color: var(--b64-primary);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .b64-link-btn:hover {
    color: var(--b64-primary-dark);
  }

  /* File upload zone */
  .b64-file-zone {
    border: 2px dashed var(--b64-border);
    border-radius: var(--b64-radius);
    padding: 24px;
    text-align: center;
    margin-bottom: 16px;
    cursor: pointer;
    transition: all 0.2s ease;
    display: none;
    background: var(--b64-bg);
  }

  .b64-file-zone.visible {
    display: block;
  }

  .b64-file-zone:hover,
  .b64-file-zone.dragover {
    border-color: var(--b64-primary);
    background: #F0EEFA;
  }

  .b64-file-zone-icon {
    font-size: 2rem;
    margin-bottom: 8px;
  }

  .b64-file-zone-text {
    font-size: 0.9rem;
    color: var(--b64-text-muted);
  }

  .b64-file-zone-text strong {
    color: var(--b64-primary);
  }

  .b64-file-info {
    display: none;
    align-items: center;
    gap: 12px;
    padding: 10px 16px;
    background: var(--b64-bg);
    border-radius: 8px;
    margin-bottom: 16px;
    font-size: 0.85rem;
    color: var(--b64-text-muted);
  }

  .b64-file-info.visible {
    display: flex;
  }

  .b64-file-info strong {
    color: var(--b64-text);
  }

  .b64-file-remove {
    margin-left: auto;
    background: none;
    border: none;
    color: var(--b64-error);
    cursor: pointer;
    font-size: 1rem;
    padding: 2px 6px;
  }

  /* Editor Layout */
  .b64-editor {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .b64-panel {
    background: var(--b64-surface);
    border: 1px solid var(--b64-border);
    border-radius: var(--b64-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .b64-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--b64-bg);
    border-bottom: 1px solid var(--b64-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--b64-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .b64-panel-header span {
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .b64-input-area {
    width: 100%;
    min-height: 340px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    resize: vertical;
    color: var(--b64-text);
    background: var(--b64-surface);
    outline: none;
    word-break: break-all;
  }

  .b64-input-area::placeholder {
    color: #B2BEC3;
    word-break: normal;
  }

  /* Auto-detect badge */
  .b64-detect-badge {
    display: none;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 0.82rem;
    font-weight: 500;
    margin-bottom: 16px;
  }

  .b64-detect-badge.visible {
    display: inline-flex;
  }

  .b64-detect-badge.is-base64 {
    background: rgba(108, 92, 231, 0.1);
    color: var(--b64-primary);
  }

  .b64-detect-badge.is-text {
    background: rgba(0, 184, 148, 0.1);
    color: var(--b64-success);
  }

  /* Status Bar */
  .b64-status {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 24px;
  }

  .b64-status-msg {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.875rem;
    font-weight: 500;
    padding: 6px 14px;
    border-radius: 20px;
  }

  .b64-status-success {
    background: rgba(0, 184, 148, 0.1);
    color: #00B894;
  }

  .b64-status-error {
    background: rgba(214, 48, 49, 0.1);
    color: #D63031;
  }

  .b64-status-empty {
    background: var(--b64-bg);
    color: var(--b64-text-muted);
  }

  .b64-stats {
    display: flex;
    gap: 16px;
    font-size: 0.825rem;
    color: var(--b64-text-muted);
  }

  .b64-stat {
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .b64-stat strong {
    color: var(--b64-text);
    font-weight: 600;
  }

  /* Meta footer */
  .b64-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--b64-text-muted);
    border-top: 1px solid var(--b64-border);
    margin-bottom: 40px;
  }

  /* Content section */
  .b64-content {
    margin-top: 48px;
    max-width: 800px;
  }

  .b64-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--b64-text);
  }

  .b64-content p {
    color: var(--b64-text-muted);
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .b64-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 10px;
    color: var(--b64-text);
  }

  .b64-content ul {
    color: var(--b64-text-muted);
    padding-left: 24px;
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .b64-content code {
    background: var(--b64-bg);
    padding: 2px 6px;
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85em;
    color: var(--b64-primary);
  }

  /* FAQ Section */
  .b64-faq {
    max-width: 820px;
    margin: 48px auto 60px;
  }

  .b64-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--b64-text);
  }

  .b64-faq-item {
    border: 1px solid var(--b64-border);
    border-radius: var(--b64-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--b64-surface);
    box-shadow: 0 1px 4px rgba(108, 92, 231, 0.04);
  }

  .b64-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--b64-text);
  }

  .b64-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--b64-text-muted);
    line-height: 1.7;
  }

  /* Mobile responsive */
  @media (max-width: 768px) {
    .b64-hero h1 {
      font-size: 1.6rem;
    }

    .b64-editor {
      grid-template-columns: 1fr;
    }

    .b64-input-area {
      min-height: 200px;
    }

    .b64-toolbar {
      gap: 6px;
    }

    .b64-btn {
      padding: 7px 12px;
      font-size: 0.8rem;
    }

    .b64-stats {
      gap: 10px;
      flex-wrap: wrap;
    }

    .b64-modes {
      max-width: 100%;
    }
  }
</style>

<div class="b64-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Base64 Encoder Decoder">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="b64-hero">
    <h1><span>Base64 Encoder</span> & Decoder</h1>
    <p class="b64-intro">Encode text to base64, decode base64 to text, or upload a file to get its base64 representation. This free base64 encoder decoder runs entirely in your browser with no server uploads. It auto-detects whether your input is base64 and offers one-click conversion.</p>
  </div>

  <!-- Mode Tabs -->
  <div class="b64-modes">
    <button class="b64-mode-btn active" id="b64ModeEncode" onclick="b64SetMode('encode')">Encode</button>
    <button class="b64-mode-btn" id="b64ModeDecode" onclick="b64SetMode('decode')">Decode</button>
    <button class="b64-mode-btn" id="b64ModeFile" onclick="b64SetMode('file')">File Upload</button>
  </div>

  <!-- Auto-detect badge -->
  <div id="b64DetectBadge" class="b64-detect-badge"></div>

  <!-- Toolbar -->
  <div class="b64-toolbar">
    <button class="b64-btn b64-btn-primary" onclick="b64Convert()" id="b64ConvertBtn">&#9654; Encode</button>
    <button class="b64-btn b64-btn-secondary" onclick="b64Copy()" id="b64CopyBtn">&#128203; <span id="b64CopyLabel">Copy</span></button>
    <div class="b64-toolbar-spacer"></div>
    <button class="b64-link-btn" onclick="b64LoadSample()" title="Load example data">Load sample</button>
    <button class="b64-btn b64-btn-secondary" onclick="b64Swap()" id="b64SwapBtn" title="Swap input and output">&#8644; Swap</button>
    <button class="b64-btn b64-btn-secondary" onclick="b64Clear()" title="Clear all">&#10005; Clear</button>
  </div>

  <!-- File upload zone -->
  <div class="b64-file-zone" id="b64FileZone">
    <div class="b64-file-zone-icon">&#128206;</div>
    <div class="b64-file-zone-text">Drop a file here or <strong>click to browse</strong></div>
    <input type="file" id="b64FileInput" style="display:none">
  </div>

  <!-- File info bar -->
  <div class="b64-file-info" id="b64FileInfo">
    &#128196; <strong id="b64FileName">file.txt</strong> <span id="b64FileSize">0 KB</span>
    <button class="b64-file-remove" onclick="b64RemoveFile()" title="Remove file">&#10005;</button>
  </div>

  <!-- Editor panels -->
  <div class="b64-editor">
    <div class="b64-panel">
      <div class="b64-panel-header">
        <span id="b64InputLabel">&#9998; Text Input</span>
        <span id="b64InputSize">0 bytes</span>
      </div>
      <textarea id="b64Input" class="b64-input-area" placeholder="Type or paste text to encode to base64..." spellcheck="false"></textarea>
    </div>
    <div class="b64-panel">
      <div class="b64-panel-header">
        <span id="b64OutputLabel">&#10004; Base64 Output</span>
        <span id="b64OutputSize">0 bytes</span>
      </div>
      <textarea id="b64Output" class="b64-input-area" readonly placeholder="Encoded result will appear here..." spellcheck="false" style="background:#FAFBFE;"></textarea>
    </div>
  </div>

  <!-- Status & Stats -->
  <div class="b64-status">
    <div id="b64StatusMsg" class="b64-status-msg b64-status-empty">Enter text and click Encode</div>
    <div class="b64-stats">
      <span class="b64-stat">Input: <strong id="b64StatInput">0 B</strong></span>
      <span class="b64-stat">Output: <strong id="b64StatOutput">0 B</strong></span>
      <span class="b64-stat">Ratio: <strong id="b64StatRatio">-</strong></span>
    </div>
  </div>

  <div class="b64-meta">
    <span>Processing happens entirely in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO content -->
  <div class="b64-content">
    <h2>How Base64 Encoding Works</h2>
    <p>Base64 encoding converts binary data into a text representation using 64 printable ASCII characters: <code>A-Z</code>, <code>a-z</code>, <code>0-9</code>, <code>+</code>, and <code>/</code>, with <code>=</code> used for padding. Every three bytes of input become four base64 characters, making the output roughly 33% larger than the original data.</p>

    <h3>Common Uses for Base64</h3>
    <ul>
      <li>Embedding images in HTML or CSS using data URIs</li>
      <li>Encoding binary attachments in email (MIME)</li>
      <li>Storing binary data in JSON or XML payloads</li>
      <li>Passing data through URL parameters or HTTP headers</li>
      <li>Encoding authentication credentials (HTTP Basic Auth)</li>
      <li>Encoding cryptographic keys and certificates (PEM format)</li>
    </ul>

    <h3>Why Use This Tool</h3>
    <p>Unlike many online base64 tools that upload your data to a server, this encoder and decoder runs entirely in your browser using the built-in <code>btoa()</code> and <code>atob()</code> functions combined with proper UTF-8 handling. Your data never leaves your device, making it safe for encoding API keys, tokens, passwords, and other sensitive content. The file upload feature reads files locally using the FileReader API and produces a base64 string you can copy directly into your code.</p>
  </div>

  <!-- FAQ with Schema.org markup -->
  <div class="b64-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="b64-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is base64 encoding used for?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Base64 encoding converts binary data into plain ASCII text so it can be safely transmitted through text-based systems. Common use cases include embedding images directly in HTML or CSS as data URIs, encoding email attachments in MIME format, passing binary data in JSON or XML payloads, and encoding credentials for HTTP Basic Authentication. Any time you need to represent binary data as a string that survives copy-paste, email transport, or URL parameters, base64 is the standard solution.</p>
      </div>
    </div>

    <div class="b64-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is base64 encoding the same as encryption?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. Base64 is an encoding scheme, not encryption. It transforms data into a different representation but does not protect it. Anyone with a base64 decoder can reverse the encoding and read the original content. If you need to protect sensitive data, use proper encryption algorithms like AES-256 or RSA before optionally base64-encoding the encrypted output for transport. Base64 is about format compatibility, not security.</p>
      </div>
    </div>

    <div class="b64-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why is my base64-encoded output larger than the input?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Base64 encoding increases data size by approximately 33%. This happens because every three bytes of input are represented as four base64 characters. Three bytes contain 24 bits, which are split into four groups of 6 bits, and each 6-bit group maps to one of 64 characters. If the input length is not a multiple of three, padding characters (=) are added. For a 1 MB file, the base64 output will be roughly 1.33 MB.</p>
      </div>
    </div>

    <div class="b64-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can this tool encode files to base64?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Click the File Upload tab and drag-and-drop a file or click to browse. The tool reads the file locally using the browser's FileReader API and converts it to a base64 string. This works with any file type, including images, PDFs, fonts, and binary executables. The entire process happens in your browser; no data is uploaded to any server. For images, you can use the output directly as a data URI in your HTML or CSS.</p>
      </div>
    </div>

    <div class="b64-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe using this online base64 encoder?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This base64 encoder and decoder runs entirely inside your browser using JavaScript. Your data never leaves your device. There are no network requests, no server-side processing, and nothing is logged or stored. You can verify this by opening your browser's developer tools and monitoring the Network tab while encoding or decoding data. This makes it safe for working with API keys, authentication tokens, and other sensitive content.</p>
      </div>
    </div>

  </div>

  <div style="margin: 2rem 0; padding: 1rem 1.25rem; background: #f3f0ff; border: 1px solid #6C5CE7; border-radius: 8px;">
<div style="font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.1em; color: #6C5CE7; margin-bottom: 0.5rem; font-weight: 600;">Related Guide</div>
<a href="/guides/creating-a-chrome-extension/" style="color: #1d1d1f; text-decoration: none; font-size: 0.95rem; font-weight: 500;">How to Create a Chrome Extension &rarr;</a>
</div>

  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid #2a2a3a; margin-top: 3rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var inputEl = document.getElementById("b64Input");
  var outputEl = document.getElementById("b64Output");
  var statusEl = document.getElementById("b64StatusMsg");
  var detectBadge = document.getElementById("b64DetectBadge");
  var fileZone = document.getElementById("b64FileZone");
  var fileInput = document.getElementById("b64FileInput");
  var fileInfo = document.getElementById("b64FileInfo");
  var convertBtn = document.getElementById("b64ConvertBtn");

  var currentMode = "encode";
  var currentFile = null;

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

  function isBase64(str) {
    if (!str || str.length < 4) return false;
    var trimmed = str.trim();
    // Must be reasonable length and match base64 pattern
    if (trimmed.length % 4 !== 0 && trimmed.indexOf("\n") === -1) {
      // Allow multi-line base64 (e.g., PEM format)
      var joined = trimmed.replace(/[\r\n\s]/g, "");
      if (joined.length % 4 !== 0) return false;
    }
    var clean = trimmed.replace(/[\r\n\s]/g, "");
    if (!/^[A-Za-z0-9+/]*={0,2}$/.test(clean)) return false;
    if (clean.length < 4) return false;
    // Try to actually decode it
    try {
      atob(clean);
      return true;
    } catch (e) {
      return false;
    }
  }

  // UTF-8 safe encode/decode using TextEncoder/TextDecoder
  function utf8ToBase64(str) {
    var bytes = new TextEncoder().encode(str);
    var binary = "";
    for (var i = 0; i < bytes.length; i++) {
      binary += String.fromCharCode(bytes[i]);
    }
    return btoa(binary);
  }

  function base64ToUtf8(b64) {
    var clean = b64.replace(/[\r\n\s]/g, "");
    var binary = atob(clean);
    var bytes = new Uint8Array(binary.length);
    for (var i = 0; i < binary.length; i++) {
      bytes[i] = binary.charCodeAt(i);
    }
    return new TextDecoder().decode(bytes);
  }

  function updateSizes() {
    document.getElementById("b64InputSize").textContent = formatBytes(byteSize(inputEl.value));
    document.getElementById("b64OutputSize").textContent = formatBytes(byteSize(outputEl.value));
  }

  function updateStats(inputBytes, outputBytes) {
    document.getElementById("b64StatInput").textContent = formatBytes(inputBytes);
    document.getElementById("b64StatOutput").textContent = formatBytes(outputBytes);
    if (inputBytes > 0 && outputBytes > 0) {
      var ratio = (outputBytes / inputBytes).toFixed(2);
      document.getElementById("b64StatRatio").textContent = ratio + "x";
    } else {
      document.getElementById("b64StatRatio").textContent = "-";
    }
  }

  function clearStats() {
    document.getElementById("b64StatInput").textContent = "0 B";
    document.getElementById("b64StatOutput").textContent = "0 B";
    document.getElementById("b64StatRatio").textContent = "-";
  }

  function setStatus(type, msg) {
    statusEl.className = "b64-status-msg";
    if (type === "success") {
      statusEl.classList.add("b64-status-success");
      statusEl.innerHTML = "&#10004; " + msg;
    } else if (type === "error") {
      statusEl.classList.add("b64-status-error");
      statusEl.innerHTML = "&#10006; " + msg;
    } else {
      statusEl.classList.add("b64-status-empty");
      statusEl.textContent = msg;
    }
  }

  function resetCopyBtn() {
    var btn = document.getElementById("b64CopyBtn");
    var label = document.getElementById("b64CopyLabel");
    btn.classList.remove("copied");
    label.textContent = "Copy";
  }

  // --- Auto-detect on input ---

  function checkAutoDetect() {
    var val = inputEl.value.trim();
    if (!val || currentMode === "file") {
      detectBadge.classList.remove("visible");
      return;
    }
    if (isBase64(val) && currentMode === "encode") {
      detectBadge.className = "b64-detect-badge visible is-base64";
      detectBadge.innerHTML = "&#128270; Input looks like base64 &#8212; <button class='b64-link-btn' onclick='b64SetMode(\"decode\")'>Switch to Decode?</button>";
    } else if (!isBase64(val) && currentMode === "decode") {
      detectBadge.className = "b64-detect-badge visible is-text";
      detectBadge.innerHTML = "&#128270; Input looks like plain text &#8212; <button class='b64-link-btn' onclick='b64SetMode(\"encode\")'>Switch to Encode?</button>";
    } else {
      detectBadge.classList.remove("visible");
    }
  }

  inputEl.addEventListener("input", function() {
    updateSizes();
    checkAutoDetect();
  });

  // --- Mode switching ---

  window.b64SetMode = function(mode) {
    currentMode = mode;
    document.getElementById("b64ModeEncode").classList.toggle("active", mode === "encode");
    document.getElementById("b64ModeDecode").classList.toggle("active", mode === "decode");
    document.getElementById("b64ModeFile").classList.toggle("active", mode === "file");

    if (mode === "encode") {
      convertBtn.innerHTML = "&#9654; Encode";
      document.getElementById("b64InputLabel").innerHTML = "&#9998; Text Input";
      document.getElementById("b64OutputLabel").innerHTML = "&#10004; Base64 Output";
      inputEl.placeholder = "Type or paste text to encode to base64...";
      outputEl.placeholder = "Encoded result will appear here...";
      fileZone.classList.remove("visible");
      document.getElementById("b64SwapBtn").style.display = "";
      inputEl.readOnly = false;
    } else if (mode === "decode") {
      convertBtn.innerHTML = "&#9654; Decode";
      document.getElementById("b64InputLabel").innerHTML = "&#9998; Base64 Input";
      document.getElementById("b64OutputLabel").innerHTML = "&#10004; Decoded Text";
      inputEl.placeholder = "Paste base64 string to decode...";
      outputEl.placeholder = "Decoded result will appear here...";
      fileZone.classList.remove("visible");
      document.getElementById("b64SwapBtn").style.display = "";
      inputEl.readOnly = false;
    } else if (mode === "file") {
      convertBtn.innerHTML = "&#9654; Encode File";
      document.getElementById("b64InputLabel").innerHTML = "&#9998; File Content (read-only)";
      document.getElementById("b64OutputLabel").innerHTML = "&#10004; Base64 Output";
      inputEl.placeholder = "File content will appear here after upload...";
      outputEl.placeholder = "Base64-encoded file will appear here...";
      fileZone.classList.add("visible");
      document.getElementById("b64SwapBtn").style.display = "none";
      inputEl.readOnly = true;
    }

    detectBadge.classList.remove("visible");
    setStatus("empty", mode === "decode" ? "Paste base64 and click Decode" : mode === "file" ? "Upload a file to encode" : "Enter text and click Encode");
  };

  // --- File handling ---

  fileZone.addEventListener("click", function() {
    fileInput.click();
  });

  fileZone.addEventListener("dragover", function(e) {
    e.preventDefault();
    fileZone.classList.add("dragover");
  });

  fileZone.addEventListener("dragleave", function() {
    fileZone.classList.remove("dragover");
  });

  fileZone.addEventListener("drop", function(e) {
    e.preventDefault();
    fileZone.classList.remove("dragover");
    if (e.dataTransfer.files.length > 0) {
      handleFile(e.dataTransfer.files[0]);
    }
  });

  fileInput.addEventListener("change", function() {
    if (fileInput.files.length > 0) {
      handleFile(fileInput.files[0]);
    }
  });

  function handleFile(file) {
    currentFile = file;
    document.getElementById("b64FileName").textContent = file.name;
    document.getElementById("b64FileSize").textContent = formatBytes(file.size);
    fileInfo.classList.add("visible");

    // Show preview in input panel
    if (file.type.startsWith("text/") || file.size < 50000) {
      var textReader = new FileReader();
      textReader.onload = function(e) {
        inputEl.value = e.target.result;
        updateSizes();
      };
      textReader.readAsText(file);
    } else {
      inputEl.value = "[Binary file: " + file.name + " (" + formatBytes(file.size) + ")]";
      updateSizes();
    }
  }

  window.b64RemoveFile = function() {
    currentFile = null;
    fileInfo.classList.remove("visible");
    fileInput.value = "";
    inputEl.value = "";
    outputEl.value = "";
    updateSizes();
    clearStats();
    setStatus("empty", "Upload a file to encode");
  };

  // --- Core actions ---

  window.b64Convert = function() {
    resetCopyBtn();

    if (currentMode === "file") {
      if (!currentFile) {
        setStatus("error", "No file selected");
        return;
      }
      var reader = new FileReader();
      reader.onload = function(e) {
        // result is a data URL like "data:type;base64,XXXX"
        var dataUrl = e.target.result;
        var base64 = dataUrl.split(",")[1] || "";
        outputEl.value = base64;
        updateSizes();
        var inBytes = currentFile.size;
        var outBytes = byteSize(base64);
        updateStats(inBytes, outBytes);
        setStatus("success", "File encoded (" + formatBytes(inBytes) + " &#8594; " + formatBytes(outBytes) + ")");
      };
      reader.onerror = function() {
        setStatus("error", "Failed to read file");
      };
      reader.readAsDataURL(currentFile);
      return;
    }

    var raw = inputEl.value;
    if (!raw) {
      setStatus("empty", currentMode === "decode" ? "Paste base64 and click Decode" : "Enter text and click Encode");
      outputEl.value = "";
      updateSizes();
      clearStats();
      return;
    }

    try {
      var result;
      var inBytes = byteSize(raw);

      if (currentMode === "encode") {
        result = utf8ToBase64(raw);
        outputEl.value = result;
        var outBytes = byteSize(result);
        updateStats(inBytes, outBytes);
        setStatus("success", "Encoded (" + formatBytes(inBytes) + " &#8594; " + formatBytes(outBytes) + ")");
      } else {
        result = base64ToUtf8(raw);
        outputEl.value = result;
        var outBytes = byteSize(result);
        updateStats(inBytes, outBytes);
        setStatus("success", "Decoded (" + formatBytes(inBytes) + " &#8594; " + formatBytes(outBytes) + ")");
      }

      updateSizes();
    } catch (e) {
      setStatus("error", currentMode === "decode" ? "Invalid base64 input" : "Encoding failed: " + e.message);
      outputEl.value = "";
      updateSizes();
      clearStats();
    }
  };

  window.b64Copy = function() {
    var text = outputEl.value;
    if (!text) return;
    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById("b64CopyBtn");
      var label = document.getElementById("b64CopyLabel");
      btn.classList.add("copied");
      label.textContent = "Copied!";
      setTimeout(function() {
        resetCopyBtn();
      }, 2000);
    });
  };

  window.b64Swap = function() {
    if (currentMode === "file") return;
    var tmp = inputEl.value;
    inputEl.value = outputEl.value;
    outputEl.value = tmp;
    updateSizes();
    // Also swap the mode
    if (currentMode === "encode") {
      b64SetMode("decode");
    } else {
      b64SetMode("encode");
    }
    checkAutoDetect();
  };

  window.b64Clear = function() {
    inputEl.value = "";
    outputEl.value = "";
    currentFile = null;
    fileInfo.classList.remove("visible");
    fileInput.value = "";
    detectBadge.classList.remove("visible");
    updateSizes();
    clearStats();
    resetCopyBtn();
    setStatus("empty", currentMode === "decode" ? "Paste base64 and click Decode" : currentMode === "file" ? "Upload a file to encode" : "Enter text and click Encode");
  };

  window.b64LoadSample = function() {
    if (currentMode === "encode" || currentMode === "file") {
      b64SetMode("encode");
      inputEl.value = '{"api_key": "sk-test-abc123", "endpoint": "https://api.zovo.one/v1/encode", "payload": {"name": "Base64 Demo", "features": ["encode", "decode", "file upload"], "rating": 4.9}}';
    } else {
      inputEl.value = "eyJhcGlfa2V5IjogInNrLXRlc3QtYWJjMTIzIiwgImVuZHBvaW50IjogImh0dHBzOi8vYXBpLnpvdm8ub25lL3YxL2VuY29kZSIsICJwYXlsb2FkIjogeyJuYW1lIjogIkJhc2U2NCBEZW1vIiwgImZlYXR1cmVzIjogWyJlbmNvZGUiLCAiZGVjb2RlIiwgImZpbGUgdXBsb2FkIl0sICJyYXRpbmciOiA0Ljl9fQ==";
    }
    updateSizes();
    b64Convert();
  };

  // Keyboard shortcut: Ctrl/Cmd + Enter to convert
  inputEl.addEventListener("keydown", function(e) {
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      b64Convert();
    }
  });

})();
</script>
