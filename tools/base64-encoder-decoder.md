---
layout: page
title: "Base64 Encode & Decode - Free Online Base64 Tool | Zovo"
description: "Free base64 encoder and decoder -- convert text or files to and from base64 instantly. Supports UTF-8, file uploads, drag-and-drop, and one-click copy."
permalink: /tools/base64/
keywords: "base64 decode, base64 encode, base64 encoder decoder, base64 converter, base64 to text, text to base64"
target_keyword: "base64 decode"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [base64, encoder, decoder, converter, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>
  :root {
    --zovo-primary: #6C5CE7;
    --zovo-primary-dark: #5A4BD1;
    --zovo-primary-light: #A29BFE;
    --zovo-bg: #F8F9FE;
    --zovo-surface: #FFFFFF;
    --zovo-text: #2D3436;
    --zovo-text-muted: #636E72;
    --zovo-border: #DFE6E9;
    --zovo-success: #00B894;
    --zovo-error: #D63031;
    --zovo-radius: 12px;
  }

  .b64-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--zovo-text);
    max-width: 960px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .b64-wrapper * {
    box-sizing: border-box;
  }

  .b64-hero {
    text-align: center;
    padding: 40px 0 32px;
  }

  .b64-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--zovo-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .b64-hero h1 span {
    color: var(--zovo-primary);
  }

  .b64-intro {
    font-size: 1.05rem;
    color: var(--zovo-text-muted);
    max-width: 680px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Tool Card */
  .b64-tool {
    background: var(--zovo-surface);
    border: 1px solid var(--zovo-border);
    border-radius: var(--zovo-radius);
    padding: 28px;
    margin-bottom: 32px;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  /* Button Row */
  .b64-btn-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 20px;
  }

  .b64-btn {
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    padding: 10px 24px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    white-space: nowrap;
  }

  .b64-btn-encode {
    background: var(--zovo-primary);
    color: #fff;
  }

  .b64-btn-encode:hover {
    background: var(--zovo-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3);
  }

  .b64-btn-decode {
    background: var(--zovo-bg);
    color: var(--zovo-primary);
    border: 1.5px solid var(--zovo-primary);
  }

  .b64-btn-decode:hover {
    background: rgba(108, 92, 231, 0.08);
    transform: translateY(-1px);
  }

  .b64-btn-copy {
    background: var(--zovo-bg);
    color: var(--zovo-primary);
    border: 1.5px solid var(--zovo-primary-light);
    margin-left: auto;
  }

  .b64-btn-copy:hover {
    background: rgba(108, 92, 231, 0.08);
  }

  .b64-btn-copy.copied {
    background: var(--zovo-success);
    color: #fff;
    border-color: var(--zovo-success);
  }

  .b64-btn-clear {
    background: var(--zovo-bg);
    color: var(--zovo-text-muted);
    border: 1.5px solid var(--zovo-border);
  }

  .b64-btn-clear:hover {
    background: #EEE;
  }

  /* Panels */
  .b64-panels {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }

  .b64-panel {
    display: flex;
    flex-direction: column;
  }

  .b64-panel-label {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--zovo-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .b64-panel-stats {
    font-weight: 400;
    font-size: 0.78rem;
    text-transform: none;
    letter-spacing: 0;
  }

  .b64-textarea {
    font-family: 'SF Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.9rem;
    padding: 16px;
    border: 1.5px solid var(--zovo-border);
    border-radius: 8px;
    background: var(--zovo-bg);
    color: var(--zovo-text);
    resize: vertical;
    min-height: 240px;
    line-height: 1.6;
    transition: border-color 0.2s;
    width: 100%;
    word-break: break-all;
  }

  .b64-textarea:focus {
    outline: none;
    border-color: var(--zovo-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.12);
  }

  .b64-textarea::placeholder {
    color: #B2BEC3;
  }

  /* Drop Zone */
  .b64-dropzone {
    border: 2px dashed var(--zovo-border);
    border-radius: 8px;
    padding: 20px;
    text-align: center;
    margin-bottom: 20px;
    cursor: pointer;
    transition: all 0.2s;
    background: var(--zovo-bg);
  }

  .b64-dropzone:hover,
  .b64-dropzone.dragover {
    border-color: var(--zovo-primary);
    background: rgba(108, 92, 231, 0.04);
  }

  .b64-dropzone-icon {
    font-size: 1.6rem;
    margin-bottom: 6px;
    color: var(--zovo-primary-light);
  }

  .b64-dropzone-text {
    font-size: 0.9rem;
    color: var(--zovo-text-muted);
  }

  .b64-dropzone-text strong {
    color: var(--zovo-primary);
    cursor: pointer;
  }

  .b64-dropzone-hint {
    font-size: 0.78rem;
    color: #B2BEC3;
    margin-top: 4px;
  }

  /* Suggestion Banner */
  .b64-suggestion {
    display: none;
    background: rgba(108, 92, 231, 0.08);
    border: 1px solid var(--zovo-primary-light);
    border-radius: 8px;
    padding: 10px 16px;
    margin-bottom: 16px;
    font-size: 0.88rem;
    color: var(--zovo-primary-dark);
    align-items: center;
    gap: 8px;
  }

  .b64-suggestion.visible {
    display: flex;
  }

  .b64-suggestion-btn {
    font-family: 'Inter', sans-serif;
    font-size: 0.82rem;
    font-weight: 600;
    padding: 4px 12px;
    border: none;
    border-radius: 6px;
    background: var(--zovo-primary);
    color: #fff;
    cursor: pointer;
    margin-left: auto;
    white-space: nowrap;
  }

  .b64-suggestion-btn:hover {
    background: var(--zovo-primary-dark);
  }

  /* Error */
  .b64-error {
    display: none;
    background: rgba(214, 48, 49, 0.08);
    border: 1px solid rgba(214, 48, 49, 0.3);
    border-radius: 8px;
    padding: 10px 16px;
    margin-bottom: 16px;
    font-size: 0.88rem;
    color: var(--zovo-error);
  }

  .b64-error.visible {
    display: block;
  }

  /* File Info */
  .b64-file-info {
    display: none;
    background: rgba(108, 92, 231, 0.06);
    border-radius: 8px;
    padding: 10px 16px;
    margin-bottom: 16px;
    font-size: 0.85rem;
    color: var(--zovo-text-muted);
    align-items: center;
    gap: 8px;
  }

  .b64-file-info.visible {
    display: flex;
  }

  .b64-file-info-name {
    font-weight: 600;
    color: var(--zovo-text);
  }

  .b64-file-info-dismiss {
    margin-left: auto;
    background: none;
    border: none;
    color: var(--zovo-text-muted);
    cursor: pointer;
    font-size: 1.1rem;
    padding: 0 4px;
    line-height: 1;
  }

  /* Meta */
  .b64-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 12px;
    font-size: 0.82rem;
    color: var(--zovo-text-muted);
  }

  /* FAQ / SEO Content */
  .b64-content {
    margin-top: 48px;
    padding-top: 32px;
    border-top: 1px solid var(--zovo-border);
  }

  .b64-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--zovo-text);
  }

  .b64-content h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin: 28px 0 8px;
    color: var(--zovo-text);
  }

  .b64-content p {
    margin: 0 0 14px;
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .b64-content ul {
    margin: 0 0 14px;
    padding-left: 20px;
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
  }

  .b64-content a {
    color: var(--zovo-primary);
    text-decoration: none;
  }

  .b64-content a:hover {
    text-decoration: underline;
  }

  /* CTA */
  .b64-cta {
    background: linear-gradient(135deg, var(--zovo-primary), var(--zovo-primary-dark));
    border-radius: var(--zovo-radius);
    padding: 32px;
    text-align: center;
    margin-top: 40px;
  }

  .b64-cta h3 {
    color: #fff;
    font-size: 1.3rem;
    font-weight: 700;
    margin: 0 0 8px;
  }

  .b64-cta p {
    color: rgba(255, 255, 255, 0.85);
    font-size: 0.95rem;
    margin: 0 0 20px;
  }

  .b64-cta a {
    display: inline-block;
    background: #fff;
    color: var(--zovo-primary);
    font-weight: 600;
    padding: 10px 28px;
    border-radius: 8px;
    text-decoration: none;
    font-size: 0.95rem;
    transition: transform 0.2s, box-shadow 0.2s;
  }

  .b64-cta a:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
  }

  /* FAQ */
  .b64-faq {
    margin-top: 40px;
  }

  .b64-faq-item {
    margin-bottom: 24px;
  }

  .b64-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--zovo-text);
  }

  .b64-faq-item p {
    margin: 0;
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  /* Responsive */
  @media (max-width: 700px) {
    .b64-hero h1 {
      font-size: 1.6rem;
    }

    .b64-tool {
      padding: 18px;
    }

    .b64-panels {
      grid-template-columns: 1fr;
    }

    .b64-btn-row {
      flex-direction: column;
    }

    .b64-btn {
      justify-content: center;
    }

    .b64-btn-copy {
      margin-left: 0;
    }

    .b64-textarea {
      min-height: 180px;
    }
  }
</style>

<div class="b64-wrapper" id="b64App">

  <div class="b64-hero">
    <h1><span>Base64</span> Encode & Decode</h1>
    <p class="b64-intro">Encode text or files to base64, or decode base64 strings back to readable text. Fast, private, and runs entirely in your browser. Nothing is sent to a server.</p>
  </div>

  <div class="b64-tool">

    <!-- Drop Zone -->
    <div class="b64-dropzone" id="b64Dropzone">
      <div class="b64-dropzone-icon">
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="#A29BFE" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="17 8 12 3 7 8"/><line x1="12" y1="3" x2="12" y2="15"/></svg>
      </div>
      <div class="b64-dropzone-text">Drag and drop a file here, or <strong id="b64BrowseBtn">browse</strong></div>
      <div class="b64-dropzone-hint">The file will be read locally and encoded to base64</div>
      <input type="file" id="b64FileInput" style="display:none;">
    </div>

    <!-- File Info -->
    <div class="b64-file-info" id="b64FileInfo">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
      <span>File: <span class="b64-file-info-name" id="b64FileName"></span> (<span id="b64FileSize"></span>)</span>
      <button class="b64-file-info-dismiss" id="b64FileDismiss" title="Remove file">&times;</button>
    </div>

    <!-- Suggestion Banner -->
    <div class="b64-suggestion" id="b64Suggestion">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="16" x2="12" y2="12"/><line x1="12" y1="8" x2="12.01" y2="8"/></svg>
      <span>This looks like base64-encoded text.</span>
      <button class="b64-suggestion-btn" onclick="b64Decode()">Decode it</button>
    </div>

    <!-- Error -->
    <div class="b64-error" id="b64Error"></div>

    <!-- Action Buttons -->
    <div class="b64-btn-row">
      <button class="b64-btn b64-btn-encode" onclick="b64Encode()">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
        Encode
      </button>
      <button class="b64-btn b64-btn-decode" onclick="b64Decode()">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="8 6 2 12 8 18"/><polyline points="16 18 22 12 16 6"/></svg>
        Decode
      </button>
      <button class="b64-btn b64-btn-clear" onclick="b64Clear()">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
        Clear
      </button>
      <button class="b64-btn b64-btn-copy" id="b64CopyBtn" onclick="b64Copy()">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" style="flex-shrink:0"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
        <span id="b64CopyText">Copy Output</span>
      </button>
    </div>

    <!-- Two-Panel Layout -->
    <div class="b64-panels">
      <div class="b64-panel">
        <div class="b64-panel-label">
          <span>Input</span>
          <span class="b64-panel-stats" id="b64InputStats">0 chars / 0 bytes</span>
        </div>
        <textarea class="b64-textarea" id="b64Input" placeholder="Type or paste text here, or drop a file above..." spellcheck="false"></textarea>
      </div>
      <div class="b64-panel">
        <div class="b64-panel-label">
          <span>Output</span>
          <span class="b64-panel-stats" id="b64OutputStats">0 chars / 0 bytes</span>
        </div>
        <textarea class="b64-textarea" id="b64Output" placeholder="Encoded or decoded result will appear here..." spellcheck="false" readonly></textarea>
      </div>
    </div>

    <div class="b64-meta">
      <span id="b64Status"></span>
      <span>Zovo Tools</span>
    </div>
  </div>

  <!-- SEO Content -->
  <div class="b64-content">
    <h2>What Is Base64 Encoding?</h2>

    <p>Base64 is a binary-to-text encoding scheme that converts binary data into a string of ASCII characters. It works by taking groups of three bytes (24 bits) and splitting them into four 6-bit values, each mapped to a character from a 64-character alphabet: A-Z, a-z, 0-9, plus sign (+), and forward slash (/). Padding with <code>=</code> signs fills out the final group if the input length is not divisible by three.</p>

    <p>The name "base64" comes directly from that 64-character alphabet. The encoding increases data size by roughly 33%, since every three bytes of input produce four bytes of output. That trade-off is worth it when you need to safely transmit binary data through systems that only handle text.</p>

    <h3>Common Use Cases</h3>

    <ul>
      <li><strong>Data URIs:</strong> Embedding images, fonts, or small files directly into HTML or CSS without a separate HTTP request. A base64-encoded PNG in an <code>&lt;img&gt;</code> tag's <code>src</code> attribute loads inline without hitting the server again.</li>
      <li><strong>Email attachments (MIME):</strong> Email protocols like SMTP were originally designed for plain ASCII text. Base64 encoding allows binary attachments (PDFs, images, zip files) to travel safely through email systems that would otherwise corrupt raw binary data.</li>
      <li><strong>API authentication tokens:</strong> HTTP Basic Auth concatenates a username and password with a colon and then base64-encodes the result. JWT tokens also use base64url encoding for their header and payload segments.</li>
      <li><strong>Storing binary in JSON or XML:</strong> Neither format natively supports binary data. Base64 lets you embed file contents, cryptographic keys, or certificates as plain text strings inside structured data formats.</li>
      <li><strong>URL-safe data transfer:</strong> A variant called base64url replaces <code>+</code> and <code>/</code> with <code>-</code> and <code>_</code> so the encoded string can be used in URLs and filenames without escaping.</li>
    </ul>

    <h3>Encoding vs. Encryption</h3>

    <p>Base64 is not encryption. It provides no security whatsoever. Anyone can decode a base64 string instantly, as this tool demonstrates. Its purpose is safe transport and compatibility, not confidentiality. If you need to protect sensitive data, use proper encryption (AES, RSA) and treat base64 as a formatting step that happens before or after encryption.</p>

    <h3>UTF-8 and Base64</h3>

    <p>JavaScript's built-in <code>btoa()</code> function only handles Latin-1 characters. This tool uses <code>TextEncoder</code> and <code>TextDecoder</code> to properly handle full UTF-8 text, including emoji, CJK characters, and other multi-byte sequences. That means you can safely encode and decode text in any language.</p>

    <p>For more developer tools, visit <a href="https://zovo.one/tools">zovo.one/tools</a>.</p>

    <!-- CTA -->
    <div class="b64-cta">
      <h3>More Free Developer Tools</h3>
      <p>JSON formatter, diff checker, color picker, and more. All free, all private, all in your browser.</p>
      <a href="https://zovo.one/tools">Explore Zovo Tools</a>
    </div>

    <!-- FAQ -->
    <div class="b64-faq">
      <h2>Frequently Asked Questions</h2>

      <div class="b64-faq-item" itemscope itemtype="https://schema.org/Question">
        <h3 itemprop="name">How do I decode a base64 string?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">Paste the base64-encoded string into the Input panel and click the Decode button. The decoded plain text will appear in the Output panel. This tool auto-detects base64 input and will suggest decoding when it recognizes the pattern.</p>
        </div>
      </div>

      <div class="b64-faq-item" itemscope itemtype="https://schema.org/Question">
        <h3 itemprop="name">Can I encode files to base64?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">Yes. Drag and drop any file onto the upload area, or click "browse" to select a file. The tool reads the file locally in your browser, encodes its contents to base64, and places the result in the Input field. No data is uploaded to any server.</p>
        </div>
      </div>

      <div class="b64-faq-item" itemscope itemtype="https://schema.org/Question">
        <h3 itemprop="name">Does base64 encoding work with non-English characters?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">This tool fully supports UTF-8 encoding. It uses the TextEncoder and TextDecoder APIs to properly handle multi-byte characters, including accented letters, CJK characters, emoji, and any other Unicode text. Standard JavaScript btoa/atob functions only handle Latin-1 characters, but this tool works around that limitation.</p>
        </div>
      </div>

      <div class="b64-faq-item" itemscope itemtype="https://schema.org/Question">
        <h3 itemprop="name">Is my data safe when using this tool?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">All encoding and decoding happens entirely in your browser using JavaScript. Nothing is transmitted to a server, stored, or logged. You can verify this by disconnecting from the internet and using the tool offline. Your data never leaves your machine.</p>
        </div>
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

  // ---- UTF-8 safe base64 encode/decode ----

  function utf8ToBase64(str) {
    var encoder = new TextEncoder();
    var bytes = encoder.encode(str);
    var binary = "";
    for (var i = 0; i < bytes.length; i++) {
      binary += String.fromCharCode(bytes[i]);
    }
    return btoa(binary);
  }

  function base64ToUtf8(b64) {
    var binary = atob(b64);
    var bytes = new Uint8Array(binary.length);
    for (var i = 0; i < binary.length; i++) {
      bytes[i] = binary.charCodeAt(i);
    }
    var decoder = new TextDecoder("utf-8", { fatal: true });
    return decoder.decode(bytes);
  }

  // ---- Helpers ----

  function byteSize(str) {
    return new TextEncoder().encode(str).length;
  }

  function formatBytes(bytes) {
    if (bytes === 0) return "0 bytes";
    if (bytes === 1) return "1 byte";
    if (bytes < 1024) return bytes + " bytes";
    if (bytes < 1048576) return (bytes / 1024).toFixed(1) + " KB";
    return (bytes / 1048576).toFixed(2) + " MB";
  }

  function updateStats(textareaId, statsId) {
    var el = document.getElementById(textareaId);
    var statsEl = document.getElementById(statsId);
    var val = el.value || "";
    var chars = val.length;
    var bytes = byteSize(val);
    statsEl.textContent = chars.toLocaleString() + " chars / " + formatBytes(bytes);
  }

  function looksLikeBase64(str) {
    if (!str || str.length < 4) return false;
    var trimmed = str.trim();
    // Must be reasonable length, only base64 chars, and properly padded
    if (trimmed.length < 4) return false;
    var re = /^[A-Za-z0-9+/\r\n]+=*\s*$/;
    if (!re.test(trimmed)) return false;
    // Check if length is valid (multiple of 4 after removing whitespace)
    var clean = trimmed.replace(/\s/g, "");
    if (clean.length % 4 !== 0) return false;
    // Avoid false positives on short plain words
    if (clean.length < 8) return false;
    return true;
  }

  function showError(msg) {
    var el = document.getElementById("b64Error");
    el.textContent = msg;
    el.classList.add("visible");
  }

  function hideError() {
    document.getElementById("b64Error").classList.remove("visible");
  }

  function showSuggestion() {
    document.getElementById("b64Suggestion").classList.add("visible");
  }

  function hideSuggestion() {
    document.getElementById("b64Suggestion").classList.remove("visible");
  }

  // ---- Core Operations ----

  window.b64Encode = function() {
    hideError();
    hideSuggestion();
    var input = document.getElementById("b64Input").value;
    if (!input) {
      showError("Nothing to encode. Type or paste some text into the Input field.");
      return;
    }
    try {
      var result = utf8ToBase64(input);
      document.getElementById("b64Output").value = result;
      document.getElementById("b64Status").textContent = "Encoded " + formatBytes(byteSize(input)) + " to " + formatBytes(byteSize(result));
      updateStats("b64Output", "b64OutputStats");
    } catch (e) {
      showError("Encoding failed: " + e.message);
    }
  };

  window.b64Decode = function() {
    hideError();
    hideSuggestion();
    var input = document.getElementById("b64Input").value.trim();
    if (!input) {
      showError("Nothing to decode. Paste a base64 string into the Input field.");
      return;
    }
    try {
      var result = base64ToUtf8(input);
      document.getElementById("b64Output").value = result;
      document.getElementById("b64Status").textContent = "Decoded " + formatBytes(byteSize(input)) + " to " + formatBytes(byteSize(result));
      updateStats("b64Output", "b64OutputStats");
    } catch (e) {
      showError("Decoding failed. The input does not appear to be valid base64.");
    }
  };

  window.b64Copy = function() {
    var output = document.getElementById("b64Output").value;
    if (!output) return;
    navigator.clipboard.writeText(output).then(function() {
      var btn = document.getElementById("b64CopyBtn");
      var label = document.getElementById("b64CopyText");
      btn.classList.add("copied");
      label.textContent = "Copied!";
      setTimeout(function() {
        btn.classList.remove("copied");
        label.textContent = "Copy Output";
      }, 2000);
    });
  };

  window.b64Clear = function() {
    hideError();
    hideSuggestion();
    document.getElementById("b64Input").value = "";
    document.getElementById("b64Output").value = "";
    document.getElementById("b64Status").textContent = "";
    updateStats("b64Input", "b64InputStats");
    updateStats("b64Output", "b64OutputStats");
    // Clear file info
    document.getElementById("b64FileInfo").classList.remove("visible");
  };

  // ---- Auto-detect base64 on input ----

  var inputEl = document.getElementById("b64Input");
  var detectTimer = null;

  inputEl.addEventListener("input", function() {
    updateStats("b64Input", "b64InputStats");
    hideError();

    clearTimeout(detectTimer);
    detectTimer = setTimeout(function() {
      var val = inputEl.value.trim();
      if (looksLikeBase64(val)) {
        showSuggestion();
      } else {
        hideSuggestion();
      }
    }, 400);
  });

  // ---- File Drag & Drop + Browse ----

  var dropzone = document.getElementById("b64Dropzone");
  var fileInput = document.getElementById("b64FileInput");

  document.getElementById("b64BrowseBtn").addEventListener("click", function(e) {
    e.stopPropagation();
    fileInput.click();
  });

  dropzone.addEventListener("click", function() {
    fileInput.click();
  });

  dropzone.addEventListener("dragover", function(e) {
    e.preventDefault();
    e.stopPropagation();
    dropzone.classList.add("dragover");
  });

  dropzone.addEventListener("dragleave", function(e) {
    e.preventDefault();
    e.stopPropagation();
    dropzone.classList.remove("dragover");
  });

  dropzone.addEventListener("drop", function(e) {
    e.preventDefault();
    e.stopPropagation();
    dropzone.classList.remove("dragover");
    var files = e.dataTransfer.files;
    if (files.length > 0) {
      handleFile(files[0]);
    }
  });

  fileInput.addEventListener("change", function() {
    if (fileInput.files.length > 0) {
      handleFile(fileInput.files[0]);
    }
  });

  function handleFile(file) {
    hideError();
    hideSuggestion();

    // Show file info
    document.getElementById("b64FileName").textContent = file.name;
    document.getElementById("b64FileSize").textContent = formatBytes(file.size);
    document.getElementById("b64FileInfo").classList.add("visible");

    var reader = new FileReader();
    reader.onload = function(e) {
      // e.target.result is a data URL like "data:mime;base64,XXXXX"
      var dataUrl = e.target.result;
      var base64Part = dataUrl.split(",")[1] || "";
      document.getElementById("b64Input").value = base64Part;
      updateStats("b64Input", "b64InputStats");

      // Auto-populate output with the encoded result
      document.getElementById("b64Output").value = base64Part;
      updateStats("b64Output", "b64OutputStats");
      document.getElementById("b64Status").textContent = "File encoded: " + file.name + " (" + formatBytes(file.size) + ")";
    };
    reader.onerror = function() {
      showError("Failed to read the file. Please try again.");
    };
    reader.readAsDataURL(file);
  }

  // Dismiss file info
  document.getElementById("b64FileDismiss").addEventListener("click", function() {
    document.getElementById("b64FileInfo").classList.remove("visible");
    fileInput.value = "";
  });

  // ---- Initialize stats ----
  updateStats("b64Input", "b64InputStats");
  updateStats("b64Output", "b64OutputStats");

})();
</script>
