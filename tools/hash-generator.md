---
layout: page
title: "Free Hash Generator — MD5, SHA-1, SHA-256, SHA-512 & HMAC | Zovo"
description: "Generate MD5, SHA-1, SHA-256, SHA-384, SHA-512, and HMAC hashes from text or files. Compare hashes, verify file integrity, and learn about cryptographic hash functions."
permalink: /tools/hash-generator/
keywords: "hash generator, md5 hash, sha256 hash, sha1 generator, hash calculator, file hash checker, hmac generator, checksum calculator"
date: 2026-03-19
categories: [tools]
tags: [hash, md5, sha256, sha1, sha512, hmac, checksum, security]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --hg-primary: #6C5CE7;
    --hg-primary-dark: #5A4BD1;
    --hg-primary-light: #A29BFE;
    --hg-bg: #0a0a0f;
    --hg-surface: #12121a;
    --hg-surface-alt: #181825;
    --hg-text: #e0e0e0;
    --hg-text-muted: #8888aa;
    --hg-border: #1e1e2e;
    --hg-success: #00ff88;
    --hg-error: #ff4466;
    --hg-warning: #FDCB6E;
    --hg-radius: 12px;
    --hg-secondary: #00ff88;
  }
  .hg-wrapper { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--hg-text); max-width: 900px; margin: 0 auto; padding: 0 16px; line-height: 1.6; }
  .hg-wrapper * { box-sizing: border-box; }
  .hg-hero { text-align: center; padding: 40px 0 28px; }
  .hg-hero h1 { font-size: 2.2rem; font-weight: 700; margin: 0 0 16px; line-height: 1.2; color: #fff; }
  .hg-hero h1 span { color: var(--hg-primary); }
  .hg-intro { font-size: 1.05rem; color: var(--hg-text-muted); max-width: 720px; margin: 0 auto; line-height: 1.7; }
  .hg-panel { background: var(--hg-surface); border: 1px solid var(--hg-border); border-radius: var(--hg-radius); padding: 24px; margin-bottom: 20px; }
  .hg-panel-header { font-size: 0.8rem; font-weight: 600; color: var(--hg-text-muted); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 16px; }
  .hg-tabs { display: flex; gap: 0; margin-bottom: 20px; border-radius: 8px; overflow: hidden; border: 1px solid var(--hg-border); }
  .hg-tab { flex: 1; padding: 10px 16px; text-align: center; font-size: 0.875rem; font-weight: 600; cursor: pointer; background: var(--hg-surface-alt); color: var(--hg-text-muted); border: none; transition: all 0.15s; font-family: 'Inter', sans-serif; }
  .hg-tab.active { background: var(--hg-primary); color: #fff; }
  .hg-tab:hover:not(.active) { background: var(--hg-border); color: var(--hg-text); }
  .hg-textarea { width: 100%; min-height: 120px; padding: 14px 16px; border: 1px solid var(--hg-border); border-radius: 8px; background: var(--hg-bg); color: var(--hg-text); font-family: 'JetBrains Mono', monospace; font-size: 0.9rem; line-height: 1.6; resize: vertical; outline: none; transition: border-color 0.2s; }
  .hg-textarea:focus { border-color: var(--hg-primary); }
  .hg-textarea::placeholder { color: #555566; }
  .hg-input { width: 100%; padding: 10px 14px; border: 1px solid var(--hg-border); border-radius: 8px; background: var(--hg-bg); color: var(--hg-text); font-family: 'JetBrains Mono', monospace; font-size: 0.9rem; outline: none; transition: border-color 0.2s; }
  .hg-input:focus { border-color: var(--hg-primary); }
  .hg-input::placeholder { color: #555566; }
  .hg-dropzone { border: 2px dashed var(--hg-border); border-radius: 8px; padding: 32px 20px; text-align: center; cursor: pointer; transition: all 0.2s; background: var(--hg-bg); }
  .hg-dropzone:hover, .hg-dropzone.dragover { border-color: var(--hg-primary); background: rgba(108,92,231,0.06); }
  .hg-dropzone-icon { font-size: 2rem; margin-bottom: 8px; color: var(--hg-primary-light); }
  .hg-dropzone-text { font-size: 0.9rem; color: var(--hg-text-muted); }
  .hg-dropzone-text strong { color: var(--hg-primary); cursor: pointer; }
  .hg-dropzone-hint { font-size: 0.78rem; color: #555566; margin-top: 4px; }
  .hg-file-info { display: none; background: rgba(108,92,231,0.08); border: 1px solid var(--hg-border); border-radius: 8px; padding: 10px 16px; margin-bottom: 16px; font-size: 0.85rem; color: var(--hg-text-muted); align-items: center; gap: 8px; }
  .hg-file-info.visible { display: flex; }
  .hg-file-info-name { font-weight: 600; color: var(--hg-text); }
  .hg-file-dismiss { margin-left: auto; background: none; border: none; color: var(--hg-text-muted); cursor: pointer; font-size: 1.1rem; padding: 0 4px; }
  .hg-algos { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 20px; }
  .hg-algo-check { display: flex; align-items: center; gap: 8px; padding: 8px 14px; border: 1px solid var(--hg-border); border-radius: 8px; cursor: pointer; transition: all 0.15s; font-size: 0.875rem; font-weight: 500; user-select: none; color: var(--hg-text-muted); background: var(--hg-surface-alt); }
  .hg-algo-check.active { border-color: var(--hg-primary); background: rgba(108,92,231,0.12); color: var(--hg-primary-light); }
  .hg-algo-check input { display: none; }
  .hg-option-row { display: flex; gap: 12px; align-items: center; margin-bottom: 16px; flex-wrap: wrap; }
  .hg-option-label { font-size: 0.85rem; font-weight: 600; color: var(--hg-text-muted); min-width: 100px; }
  .hg-select { padding: 8px 12px; border: 1px solid var(--hg-border); border-radius: 8px; background: var(--hg-bg); color: var(--hg-text); font-family: 'Inter', sans-serif; font-size: 0.85rem; outline: none; cursor: pointer; }
  .hg-select:focus { border-color: var(--hg-primary); }
  .hg-toggle-row { display: flex; align-items: center; gap: 10px; margin-bottom: 16px; }
  .hg-toggle { position: relative; width: 44px; height: 24px; cursor: pointer; }
  .hg-toggle input { display: none; }
  .hg-toggle-track { position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: var(--hg-border); border-radius: 12px; transition: background 0.2s; }
  .hg-toggle input:checked + .hg-toggle-track { background: var(--hg-primary); }
  .hg-toggle-knob { position: absolute; top: 2px; left: 2px; width: 20px; height: 20px; background: #fff; border-radius: 50%; transition: transform 0.2s; pointer-events: none; }
  .hg-toggle input:checked ~ .hg-toggle-knob { transform: translateX(20px); }
  .hg-toggle-label { font-size: 0.875rem; font-weight: 600; color: var(--hg-text-muted); }
  .hg-hmac-key { display: none; margin-bottom: 16px; }
  .hg-hmac-key.visible { display: block; }
  .hg-results { margin-top: 16px; }
  .hg-result-item { background: var(--hg-bg); border: 1px solid var(--hg-border); border-radius: 8px; padding: 12px 16px; margin-bottom: 10px; }
  .hg-result-label { font-size: 0.75rem; font-weight: 600; color: var(--hg-primary-light); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 6px; }
  .hg-result-row { display: flex; gap: 8px; align-items: center; }
  .hg-result-hash { flex: 1; font-family: 'JetBrains Mono', monospace; font-size: 0.82rem; word-break: break-all; color: var(--hg-text); line-height: 1.5; padding: 4px 0; }
  .hg-btn { display: inline-flex; align-items: center; justify-content: center; gap: 6px; padding: 8px 14px; border: none; border-radius: 8px; font-family: 'Inter', sans-serif; font-size: 0.8rem; font-weight: 600; cursor: pointer; transition: all 0.15s; white-space: nowrap; }
  .hg-btn-copy { background: var(--hg-surface-alt); color: var(--hg-text-muted); border: 1px solid var(--hg-border); }
  .hg-btn-copy:hover { background: var(--hg-border); color: var(--hg-text); }
  .hg-btn-copy.copied { background: var(--hg-success); color: #000; border-color: var(--hg-success); }
  .hg-btn-primary { background: var(--hg-primary); color: #fff; padding: 10px 20px; font-size: 0.875rem; }
  .hg-btn-primary:hover { background: var(--hg-primary-dark); }
  .hg-compare-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 16px; }
  .hg-compare-result { padding: 12px 16px; border-radius: 8px; font-size: 0.9rem; font-weight: 600; text-align: center; display: none; }
  .hg-compare-result.visible { display: block; }
  .hg-compare-match { background: rgba(0,255,136,0.1); border: 1px solid rgba(0,255,136,0.3); color: var(--hg-success); }
  .hg-compare-mismatch { background: rgba(255,68,102,0.1); border: 1px solid rgba(255,68,102,0.3); color: var(--hg-error); }
  .hg-diff-display { font-family: 'JetBrains Mono', monospace; font-size: 0.82rem; word-break: break-all; line-height: 1.8; padding: 12px; background: var(--hg-bg); border: 1px solid var(--hg-border); border-radius: 8px; display: none; margin-bottom: 16px; }
  .hg-diff-display.visible { display: block; }
  .hg-diff-match { color: var(--hg-success); }
  .hg-diff-differ { color: var(--hg-error); background: rgba(255,68,102,0.15); border-radius: 2px; padding: 0 1px; }
  .hg-verify-result { display: none; align-items: center; gap: 8px; padding: 12px 16px; border-radius: 8px; font-size: 0.9rem; font-weight: 600; margin-top: 12px; }
  .hg-verify-result.visible { display: flex; }
  .hg-verify-pass { background: rgba(0,255,136,0.1); border: 1px solid rgba(0,255,136,0.3); color: var(--hg-success); }
  .hg-verify-fail { background: rgba(255,68,102,0.1); border: 1px solid rgba(255,68,102,0.3); color: var(--hg-error); }
  .hg-verify-icon { font-size: 1.2rem; }
  .hg-progress { display: none; margin-top: 12px; }
  .hg-progress.visible { display: block; }
  .hg-progress-bar { height: 4px; background: var(--hg-border); border-radius: 2px; overflow: hidden; }
  .hg-progress-fill { height: 100%; background: var(--hg-primary); border-radius: 2px; transition: width 0.2s; width: 0%; }
  .hg-progress-text { font-size: 0.78rem; color: var(--hg-text-muted); margin-top: 4px; }
  .hg-meta { display: flex; justify-content: space-between; align-items: center; padding-top: 12px; font-size: 0.8rem; color: var(--hg-text-muted); border-top: 1px solid var(--hg-border); margin-bottom: 40px; }
  .hg-content { margin-top: 48px; padding-top: 32px; border-top: 1px solid var(--hg-border); }
  .hg-content h2 { font-size: 1.4rem; font-weight: 700; margin: 32px 0 12px; color: #fff; }
  .hg-content h2:first-child { margin-top: 0; }
  .hg-content h3 { font-size: 1.1rem; font-weight: 600; margin: 24px 0 8px; color: var(--hg-text); }
  .hg-content p { margin: 0 0 14px; color: var(--hg-text-muted); font-size: 0.95rem; line-height: 1.7; }
  .hg-content ul, .hg-content ol { margin: 0 0 14px; padding-left: 20px; color: var(--hg-text-muted); font-size: 0.95rem; line-height: 1.8; }
  .hg-content a { color: var(--hg-primary); text-decoration: none; }
  .hg-content a:hover { text-decoration: underline; }
  .hg-content code { font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; background: var(--hg-surface-alt); padding: 2px 6px; border-radius: 4px; color: var(--hg-primary-light); }
  .hg-algo-table { width: 100%; border-collapse: collapse; margin: 16px 0 20px; font-size: 0.88rem; }
  .hg-algo-table th { text-align: left; padding: 10px 12px; background: var(--hg-surface-alt); color: var(--hg-primary-light); font-weight: 600; border: 1px solid var(--hg-border); }
  .hg-algo-table td { padding: 10px 12px; border: 1px solid var(--hg-border); color: var(--hg-text-muted); }
  .hg-faq { margin-top: 40px; }
  .hg-faq h2 { text-align: center; }
  .hg-faq-item { border: 1px solid var(--hg-border); border-radius: var(--hg-radius); padding: 20px 24px; margin-bottom: 12px; background: var(--hg-surface); }
  .hg-faq-item h3 { font-size: 1.05rem; font-weight: 600; margin: 0 0 10px; color: var(--hg-text); }
  .hg-faq-item p { margin: 0; font-size: 0.95rem; color: var(--hg-text-muted); line-height: 1.7; }
  @media (max-width: 768px) {
    .hg-hero h1 { font-size: 1.6rem; }
    .hg-algos { gap: 8px; }
    .hg-algo-check { padding: 6px 10px; font-size: 0.8rem; }
    .hg-compare-grid { grid-template-columns: 1fr; }
    .hg-result-row { flex-direction: column; align-items: flex-start; }
    .hg-option-row { flex-direction: column; align-items: flex-start; gap: 6px; }
    .hg-tabs { flex-direction: column; }
  }
</style>

<div class="hg-wrapper">

  <div class="hg-hero">
    <h1><span>Hash Generator</span> Online</h1>
    <p class="hg-intro">Generate MD5, SHA-1, SHA-256, SHA-384, SHA-512, and HMAC hashes from text or files. Compare hashes, verify file integrity, and copy results. Everything runs locally in your browser.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <!-- Input Mode Tabs -->
  <div class="hg-panel">
    <div class="hg-tabs">
      <button class="hg-tab active" id="hgTabText" onclick="hgSwitchTab('text')">Text Input</button>
      <button class="hg-tab" id="hgTabFile" onclick="hgSwitchTab('file')">File Input</button>
    </div>

    <!-- Text Input -->
    <div id="hgTextPane">
      <textarea class="hg-textarea" id="hgTextInput" placeholder="Type or paste text here to generate hashes..." spellcheck="false"></textarea>
    </div>

    <!-- File Input -->
    <div id="hgFilePane" style="display:none;">
      <div class="hg-dropzone" id="hgDropzone">
        <div class="hg-dropzone-icon">
          <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="#A29BFE" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="17 8 12 3 7 8"/><line x1="12" y1="3" x2="12" y2="15"/></svg>
        </div>
        <div class="hg-dropzone-text">Drag and drop a file here, or <strong id="hgBrowseBtn">browse</strong></div>
        <div class="hg-dropzone-hint">The file will be read locally and hashed in your browser</div>
        <input type="file" id="hgFileInput" style="display:none;">
      </div>
      <div class="hg-file-info" id="hgFileInfo">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
        <span>File: <span class="hg-file-info-name" id="hgFileName"></span> (<span id="hgFileSize"></span>)</span>
        <button class="hg-file-dismiss" id="hgFileDismiss">&times;</button>
      </div>
      <div class="hg-progress" id="hgProgress">
        <div class="hg-progress-bar"><div class="hg-progress-fill" id="hgProgressFill"></div></div>
        <div class="hg-progress-text" id="hgProgressText">Processing...</div>
      </div>
    </div>

    <!-- Algorithm Checkboxes -->
    <div style="margin-top:16px;">
      <div class="hg-panel-header">Algorithms</div>
      <div class="hg-algos" id="hgAlgos">
        <label class="hg-algo-check" data-algo="MD5"><input type="checkbox"> MD5</label>
        <label class="hg-algo-check active" data-algo="SHA-1"><input type="checkbox" checked> SHA-1</label>
        <label class="hg-algo-check active" data-algo="SHA-256"><input type="checkbox" checked> SHA-256</label>
        <label class="hg-algo-check" data-algo="SHA-384"><input type="checkbox"> SHA-384</label>
        <label class="hg-algo-check" data-algo="SHA-512"><input type="checkbox"> SHA-512</label>
      </div>
    </div>

    <!-- Output Format -->
    <div class="hg-option-row">
      <span class="hg-option-label">Output Format</span>
      <select class="hg-select" id="hgFormat" onchange="hgReformat()">
        <option value="hex-lower">Hex (lowercase)</option>
        <option value="hex-upper">Hex (UPPERCASE)</option>
        <option value="base64">Base64</option>
      </select>
    </div>

    <!-- HMAC Toggle -->
    <div class="hg-toggle-row">
      <label class="hg-toggle">
        <input type="checkbox" id="hgHmacToggle" onchange="hgToggleHmac()">
        <div class="hg-toggle-track"></div>
        <div class="hg-toggle-knob"></div>
      </label>
      <span class="hg-toggle-label">HMAC Mode</span>
    </div>

    <div class="hg-hmac-key" id="hgHmacKeyWrap">
      <input class="hg-input" type="text" id="hgHmacKey" placeholder="Enter HMAC secret key...">
    </div>

    <!-- Hash Results -->
    <div class="hg-results" id="hgResults"></div>
  </div>

  <!-- Hash Comparison -->
  <div class="hg-panel">
    <div class="hg-panel-header">Hash Comparison</div>
    <div class="hg-compare-grid">
      <div>
        <label style="font-size:0.8rem;color:var(--hg-text-muted);display:block;margin-bottom:4px;">Hash A</label>
        <input class="hg-input" type="text" id="hgCompareA" placeholder="Paste first hash..." oninput="hgCompare()">
      </div>
      <div>
        <label style="font-size:0.8rem;color:var(--hg-text-muted);display:block;margin-bottom:4px;">Hash B</label>
        <input class="hg-input" type="text" id="hgCompareB" placeholder="Paste second hash..." oninput="hgCompare()">
      </div>
    </div>
    <div class="hg-compare-result" id="hgCompareResult"></div>
    <div class="hg-diff-display" id="hgDiffDisplay"></div>
  </div>

  <!-- File Integrity Checker -->
  <div class="hg-panel">
    <div class="hg-panel-header">File Integrity Checker</div>
    <div style="margin-bottom:12px;">
      <label style="font-size:0.8rem;color:var(--hg-text-muted);display:block;margin-bottom:4px;">Expected Hash</label>
      <input class="hg-input" type="text" id="hgExpectedHash" placeholder="Paste the expected hash value...">
    </div>
    <div class="hg-option-row">
      <span class="hg-option-label">Algorithm</span>
      <select class="hg-select" id="hgVerifyAlgo">
        <option value="MD5">MD5</option>
        <option value="SHA-1">SHA-1</option>
        <option value="SHA-256" selected>SHA-256</option>
        <option value="SHA-384">SHA-384</option>
        <option value="SHA-512">SHA-512</option>
      </select>
    </div>
    <div>
      <input type="file" id="hgVerifyFileInput" style="display:none;">
      <button class="hg-btn hg-btn-primary" onclick="document.getElementById('hgVerifyFileInput').click()">Choose File to Verify</button>
      <span id="hgVerifyFileName" style="margin-left:10px;font-size:0.85rem;color:var(--hg-text-muted);"></span>
    </div>
    <div class="hg-progress" id="hgVerifyProgress">
      <div class="hg-progress-bar"><div class="hg-progress-fill" id="hgVerifyProgressFill"></div></div>
      <div class="hg-progress-text" id="hgVerifyProgressText">Hashing file...</div>
    </div>
    <div class="hg-verify-result" id="hgVerifyResult">
      <span class="hg-verify-icon" id="hgVerifyIcon"></span>
      <span id="hgVerifyText"></span>
    </div>
  </div>

  <div class="hg-meta">
    <span>All hashing happens in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO Content -->
  <div class="hg-content">
    <h2>What Is a Hash Function</h2>

    <p>A hash function takes an input of any size and produces a fixed-length output, called a digest. The same input always produces the same output, but even a single-bit change in the input produces a completely different digest. This property is called the avalanche effect. Good hash functions are one-way: given a digest, it is computationally infeasible to reconstruct the original input. These properties make hash functions useful for password storage, data integrity verification, digital signatures, and many other security applications.</p>

    <p>Hash functions are deterministic. If you hash the string "hello" with SHA-256 today, you get the same 64-character hex string you would get next year on a different computer. This consistency is what allows systems to compare hashes instead of comparing raw data, which is the foundation of file integrity checking and password verification.</p>

    <h2>Common Hash Algorithms Compared</h2>

    <table class="hg-algo-table">
      <thead>
        <tr><th>Algorithm</th><th>Digest Size</th><th>Speed</th><th>Security Status</th></tr>
      </thead>
      <tbody>
        <tr><td>MD5</td><td>128 bits (32 hex chars)</td><td>Very fast</td><td>Broken for collision resistance. Not suitable for security purposes. Still used for checksums and non-security fingerprinting.</td></tr>
        <tr><td>SHA-1</td><td>160 bits (40 hex chars)</td><td>Fast</td><td>Collision attacks demonstrated (SHAttered, 2017). Deprecated by NIST. Avoid for new systems.</td></tr>
        <tr><td>SHA-256</td><td>256 bits (64 hex chars)</td><td>Moderate</td><td>Part of the SHA-2 family. Widely used and considered secure. Used in Bitcoin, TLS certificates, and code signing.</td></tr>
        <tr><td>SHA-384</td><td>384 bits (96 hex chars)</td><td>Moderate</td><td>Truncated variant of SHA-512. Higher security margin than SHA-256. Used in government and financial systems.</td></tr>
        <tr><td>SHA-512</td><td>512 bits (128 hex chars)</td><td>Moderate</td><td>Largest SHA-2 variant. Can be faster than SHA-256 on 64-bit processors due to native 64-bit arithmetic.</td></tr>
      </tbody>
    </table>

    <p>For most use cases today, SHA-256 is the default recommendation. It provides a strong security margin, wide ecosystem support, and reasonable performance. MD5 and SHA-1 should only be used for backward compatibility or non-security purposes like deduplication and cache keys.</p>

    <h2>How SHA-256 Works</h2>

    <p>SHA-256 processes input in 512-bit (64-byte) blocks. The algorithm begins by padding the message: a single 1 bit is appended, followed by enough 0 bits to make the total length 448 mod 512, and then a 64-bit representation of the original message length. This guarantees the padded message is an exact multiple of 512 bits.</p>

    <p>Eight 32-bit working variables are initialized to specific fractional parts of the square roots of the first eight prime numbers. For each 512-bit block, the algorithm expands the 16 input words into 64 words using bitwise rotations and shifts, then runs 64 rounds of compression. Each round combines the working variables with a round constant (derived from the cube roots of the first 64 primes) and a message schedule word through a mix of addition modulo 2^32, bitwise AND, XOR, and right-rotation operations.</p>

    <p>After processing all blocks, the eight working variables are concatenated to produce the final 256-bit (32-byte) digest. The constants derived from prime numbers ensure there is no hidden structure or backdoor in the algorithm. This design, created by the NSA and published by NIST in 2001, has withstood over two decades of public cryptanalysis without any practical attack.</p>

    <h2>HMAC Authentication Explained</h2>

    <p>HMAC (Hash-based Message Authentication Code) combines a cryptographic hash function with a secret key to produce an authentication tag. Unlike a plain hash, an HMAC proves both integrity and authenticity: only someone who knows the secret key can generate or verify the tag. The construction is defined in RFC 2104 as <code>HMAC(K, m) = H((K' XOR opad) || H((K' XOR ipad) || m))</code>, where K' is the key padded to the block size, ipad is the byte 0x36 repeated, and opad is the byte 0x5c repeated.</p>

    <p>HMAC is used extensively in API authentication (webhook signatures from Stripe, GitHub, and Slack all use HMAC-SHA256), JWT token signing (the HS256 algorithm), and secure cookie verification. The double-hashing construction protects against length-extension attacks that would be possible with a naive "hash the key concatenated with the message" approach. When you use the HMAC mode in this tool, the Web Crypto API handles the key derivation and double-hashing internally.</p>

    <h2>Verifying File Integrity with Hashes</h2>

    <p>Software distributors publish hash values alongside their downloads so that users can verify they received an unmodified copy. The process is straightforward: download the file, compute its hash using the same algorithm the publisher specifies, and compare the two values character by character. If they match, the file has not been altered in transit or tampered with on a mirror. If even one character differs, the file should be discarded.</p>

    <p>This tool provides two ways to verify file integrity. The main hash generator computes all selected algorithm digests from any uploaded file. The dedicated File Integrity Checker panel lets you paste an expected hash, select the algorithm, and upload the file. The tool computes the hash and displays a clear pass or fail indicator. This is particularly useful when downloading ISO images, firmware updates, or security-sensitive packages where a supply-chain compromise could have serious consequences.</p>

    <p>For developers, hash-based integrity verification also underpins package managers (npm, pip, cargo all verify package hashes), Subresource Integrity (SRI) in browsers, and content-addressable storage systems like Git, which uses SHA-1 internally to identify every object in a repository.</p>

    <p>Related tools: <a href="/tools/password-generator/">Password Generator</a>, <a href="/tools/base64-encoder-decoder/">Base64 Encoder/Decoder</a>, <a href="/tools/uuid-generator/">UUID Generator</a>, <a href="/tools/jwt-decoder/">JWT Decoder</a>.</p>

    <!-- FAQ -->
    <div class="hg-faq" itemscope itemtype="https://schema.org/FAQPage">
      <h2>Frequently Asked Questions</h2>

      <div class="hg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
        <h3 itemprop="name">Is this hash generator safe to use with sensitive data?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">Yes. All hashing happens entirely in your browser using the Web Crypto API (for SHA algorithms) and a pure JavaScript implementation (for MD5). No data is transmitted to any server, stored, or logged. You can verify this by opening your browser's developer tools and monitoring the Network tab, or by disconnecting from the internet before using the tool. Your text and files never leave your machine.</p>
        </div>
      </div>

      <div class="hg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
        <h3 itemprop="name">What is the difference between MD5 and SHA-256?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">MD5 produces a 128-bit (32-character hex) digest and is very fast, but it is cryptographically broken. Researchers have demonstrated practical collision attacks where two different inputs produce the same MD5 hash. SHA-256 produces a 256-bit (64-character hex) digest and has no known practical attacks after over 20 years of scrutiny. For any security-related purpose (password hashing, digital signatures, integrity verification), SHA-256 or stronger should be used. MD5 remains acceptable for non-security uses like cache keys and deduplication.</p>
        </div>
      </div>

      <div class="hg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
        <h3 itemprop="name">Can I reverse a hash to get the original text?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">No. Cryptographic hash functions are designed to be one-way. Given a hash digest, there is no mathematical method to reconstruct the original input. For short inputs like common passwords, attackers use precomputed lookup tables (rainbow tables) or brute-force guessing, but this is not "reversing" the hash. It is guessing inputs until one matches. For sufficiently long and random inputs, this approach is computationally infeasible. This is why salted hashing (adding random data to each input before hashing) is standard practice for password storage.</p>
        </div>
      </div>

      <div class="hg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
        <h3 itemprop="name">What is HMAC and when should I use it?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">HMAC (Hash-based Message Authentication Code) combines a hash function with a secret key to produce an authentication tag. A plain hash verifies integrity (the data has not been altered), while an HMAC verifies both integrity and authenticity (the data was created by someone who knows the secret key). Use HMAC when you need to verify that a message came from a trusted source, such as validating webhook signatures, signing API requests, or creating session tokens. Common HMAC algorithms include HMAC-SHA256 and HMAC-SHA512.</p>
        </div>
      </div>

      <div class="hg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
        <h3 itemprop="name">How do I verify a file download using a hash?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">First, note the expected hash value published by the software distributor (usually on their download page or in a checksums file). Then use the File Integrity Checker panel in this tool: paste the expected hash, select the matching algorithm (typically SHA-256), and upload the downloaded file. The tool computes the file's hash in your browser and compares it character by character against the expected value. A green checkmark means the file is intact. A red indicator means the file differs from what the publisher intended, and you should re-download it from the official source.</p>
        </div>
      </div>

      <div class="hg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
        <h3 itemprop="name">Why do different hash algorithms produce different length outputs?</h3>
        <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
          <p itemprop="text">Each hash algorithm is designed to produce a specific fixed-length digest regardless of input size. MD5 outputs 128 bits (32 hex characters), SHA-1 outputs 160 bits (40 hex characters), SHA-256 outputs 256 bits (64 hex characters), SHA-384 outputs 384 bits (96 hex characters), and SHA-512 outputs 512 bits (128 hex characters). Longer digests provide a larger output space, which means a lower probability of collisions (two different inputs producing the same hash). The tradeoff is that longer hashes require more storage space and slightly more computation, though the difference is negligible for most applications.</p>
        </div>
      </div>
    </div>
  </div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/password-generator/" style="color:#00ff88;text-decoration:none;">Password Generator</a> - Generate secure random passwords</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/base64-encoder-decoder/" style="color:#00ff88;text-decoration:none;">Base64 Encoder/Decoder</a> - Encode and decode Base64 strings</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/uuid-generator/" style="color:#00ff88;text-decoration:none;">UUID Generator</a> - Generate random UUID v4 values</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/jwt-decoder/" style="color:#00ff88;text-decoration:none;">JWT Decoder</a> - Decode and inspect JSON Web Tokens</li>
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
[
  {
    "@context": "https://schema.org",
    "@type": "WebApplication",
    "name": "Hash Generator Online",
    "description": "Generate MD5, SHA-1, SHA-256, SHA-384, SHA-512, and HMAC hashes from text or files.",
    "url": "https://zovo.one/tools/hash-generator/",
    "applicationCategory": "DeveloperApplication",
    "operatingSystem": "Any",
    "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
    "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" }
  },
  {
    "@context": "https://schema.org",
    "@type": "BreadcrumbList",
    "itemListElement": [
      { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://zovo.one" },
      { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://zovo.one/tools/" },
      { "@type": "ListItem", "position": 3, "name": "Hash Generator", "item": "https://zovo.one/tools/hash-generator/" }
    ]
  },
  {
    "@context": "https://schema.org",
    "@type": "Organization",
    "name": "Zovo",
    "url": "https://zovo.one",
    "logo": "https://zovo.one/assets/logo.png",
    "sameAs": []
  },
  {
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [
      {
        "@type": "Question",
        "name": "Is this hash generator safe to use with sensitive data?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Yes. All hashing happens entirely in your browser using the Web Crypto API (for SHA algorithms) and a pure JavaScript implementation (for MD5). No data is transmitted to any server, stored, or logged. You can verify this by monitoring the Network tab in your browser's developer tools."
        }
      },
      {
        "@type": "Question",
        "name": "What is the difference between MD5 and SHA-256?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "MD5 produces a 128-bit digest and is cryptographically broken. SHA-256 produces a 256-bit digest and has no known practical attacks. For security purposes, SHA-256 or stronger should be used. MD5 is acceptable for non-security uses like cache keys."
        }
      },
      {
        "@type": "Question",
        "name": "Can I reverse a hash to get the original text?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "No. Cryptographic hash functions are one-way. There is no mathematical method to reconstruct the original input from a digest. Attackers use precomputed tables or brute force for short inputs, but this is guessing, not reversing."
        }
      },
      {
        "@type": "Question",
        "name": "What is HMAC and when should I use it?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "HMAC combines a hash function with a secret key. A plain hash verifies integrity, while HMAC verifies both integrity and authenticity. Use HMAC for webhook signatures, API request signing, and session tokens."
        }
      },
      {
        "@type": "Question",
        "name": "How do I verify a file download using a hash?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Paste the expected hash from the publisher into the File Integrity Checker, select the algorithm, and upload your file. The tool computes the hash locally and compares it. A green checkmark means the file matches."
        }
      },
      {
        "@type": "Question",
        "name": "Why do different hash algorithms produce different length outputs?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Each algorithm is designed for a specific fixed output size. MD5 outputs 128 bits (32 hex chars), SHA-1 outputs 160 bits (40 hex chars), SHA-256 outputs 256 bits (64 hex chars), SHA-384 outputs 384 bits (96 hex chars), and SHA-512 outputs 512 bits (128 hex chars). Longer digests provide lower collision probability."
        }
      }
    ]
  }
]
</script>

<script>
(function() {
  "use strict";

  // ===== MD5 Implementation (RFC 1321) =====
  function md5(input) {
    // input: Uint8Array, returns hex string
    var S = [
      7,12,17,22, 7,12,17,22, 7,12,17,22, 7,12,17,22,
      5, 9,14,20, 5, 9,14,20, 5, 9,14,20, 5, 9,14,20,
      4,11,16,23, 4,11,16,23, 4,11,16,23, 4,11,16,23,
      6,10,15,21, 6,10,15,21, 6,10,15,21, 6,10,15,21
    ];
    var K = [
      0xd76aa478,0xe8c7b756,0x242070db,0xc1bdceee,0xf57c0faf,0x4787c62a,0xa8304613,0xfd469501,
      0x698098d8,0x8b44f7af,0xffff5bb1,0x895cd7be,0x6b901122,0xfd987193,0xa679438e,0x49b40821,
      0xf61e2562,0xc040b340,0x265e5a51,0xe9b6c7aa,0xd62f105d,0x02441453,0xd8a1e681,0xe7d3fbc8,
      0x21e1cde6,0xc33707d6,0xf4d50d87,0x455a14ed,0xa9e3e905,0xfcefa3f8,0x676f02d9,0x8d2a4c8a,
      0xfffa3942,0x8771f681,0x6d9d6122,0xfde5380c,0xa4beea44,0x4bdecfa9,0xf6bb4b60,0xbebfbc70,
      0x289b7ec6,0xeaa127fa,0xd4ef3085,0x04881d05,0xd9d4d039,0xe6db99e5,0x1fa27cf8,0xc4ac5665,
      0xf4292244,0x432aff97,0xab9423a7,0xfc93a039,0x655b59c3,0x8f0ccc92,0xffeff47d,0x85845dd1,
      0x6fa87e4f,0xfe2ce6e0,0xa3014314,0x4e0811a1,0xf7537e82,0xbd3af235,0x2ad7d2bb,0xeb86d391
    ];

    function leftRotate(x, c) {
      return ((x << c) | (x >>> (32 - c))) >>> 0;
    }

    // Pre-processing: padding
    var msgLen = input.length;
    var bitLen = msgLen * 8;
    // append 1 bit + zeros until length = 448 mod 512 (56 mod 64 bytes)
    var padLen = ((56 - (msgLen + 1) % 64) + 64) % 64;
    var padded = new Uint8Array(msgLen + 1 + padLen + 8);
    padded.set(input);
    padded[msgLen] = 0x80;
    // append original length in bits as 64-bit little-endian
    padded[padded.length - 8] = bitLen & 0xff;
    padded[padded.length - 7] = (bitLen >>> 8) & 0xff;
    padded[padded.length - 6] = (bitLen >>> 16) & 0xff;
    padded[padded.length - 5] = (bitLen >>> 24) & 0xff;
    // for messages > 2^32 bits (very large files), upper 32 bits
    var bitLenHi = Math.floor(bitLen / 0x100000000);
    padded[padded.length - 4] = bitLenHi & 0xff;
    padded[padded.length - 3] = (bitLenHi >>> 8) & 0xff;
    padded[padded.length - 2] = (bitLenHi >>> 16) & 0xff;
    padded[padded.length - 1] = (bitLenHi >>> 24) & 0xff;

    // Initialize hash values
    var a0 = 0x67452301 >>> 0;
    var b0 = 0xefcdab89 >>> 0;
    var c0 = 0x98badcfe >>> 0;
    var d0 = 0x10325476 >>> 0;

    // Process each 64-byte block
    var view = new DataView(padded.buffer);
    for (var offset = 0; offset < padded.length; offset += 64) {
      var M = new Uint32Array(16);
      for (var j = 0; j < 16; j++) {
        M[j] = view.getUint32(offset + j * 4, true); // little-endian
      }

      var A = a0, B = b0, C = c0, D = d0;

      for (var i = 0; i < 64; i++) {
        var F, g;
        if (i < 16) {
          F = ((B & C) | ((~B >>> 0) & D)) >>> 0;
          g = i;
        } else if (i < 32) {
          F = ((D & B) | ((~D >>> 0) & C)) >>> 0;
          g = (5 * i + 1) % 16;
        } else if (i < 48) {
          F = (B ^ C ^ D) >>> 0;
          g = (3 * i + 5) % 16;
        } else {
          F = (C ^ (B | (~D >>> 0))) >>> 0;
          g = (7 * i) % 16;
        }

        F = (F + A + K[i] + M[g]) >>> 0;
        A = D;
        D = C;
        C = B;
        B = (B + leftRotate(F, S[i])) >>> 0;
      }

      a0 = (a0 + A) >>> 0;
      b0 = (b0 + B) >>> 0;
      c0 = (c0 + C) >>> 0;
      d0 = (d0 + D) >>> 0;
    }

    // Output as little-endian hex
    function toLEHex(val) {
      return (
        ((val & 0xff).toString(16).padStart(2, "0")) +
        (((val >>> 8) & 0xff).toString(16).padStart(2, "0")) +
        (((val >>> 16) & 0xff).toString(16).padStart(2, "0")) +
        (((val >>> 24) & 0xff).toString(16).padStart(2, "0"))
      );
    }

    return toLEHex(a0) + toLEHex(b0) + toLEHex(c0) + toLEHex(d0);
  }

  // ===== HMAC-MD5 Implementation =====
  function hmacMd5(keyBytes, msgBytes) {
    var blockSize = 64;
    var k = keyBytes;
    if (k.length > blockSize) {
      // hash the key
      var hexHash = md5(k);
      k = hexToBytes(hexHash);
    }
    if (k.length < blockSize) {
      var padded = new Uint8Array(blockSize);
      padded.set(k);
      k = padded;
    }
    var ipad = new Uint8Array(blockSize);
    var opad = new Uint8Array(blockSize);
    for (var i = 0; i < blockSize; i++) {
      ipad[i] = k[i] ^ 0x36;
      opad[i] = k[i] ^ 0x5c;
    }
    // inner hash
    var inner = new Uint8Array(blockSize + msgBytes.length);
    inner.set(ipad);
    inner.set(msgBytes, blockSize);
    var innerHash = md5(inner);
    var innerHashBytes = hexToBytes(innerHash);
    // outer hash
    var outer = new Uint8Array(blockSize + innerHashBytes.length);
    outer.set(opad);
    outer.set(innerHashBytes, blockSize);
    return md5(outer);
  }

  function hexToBytes(hex) {
    var bytes = new Uint8Array(hex.length / 2);
    for (var i = 0; i < bytes.length; i++) {
      bytes[i] = parseInt(hex.substr(i * 2, 2), 16);
    }
    return bytes;
  }

  // ===== Utilities =====
  function arrayBufferToHex(buffer) {
    var bytes = new Uint8Array(buffer);
    var hex = "";
    for (var i = 0; i < bytes.length; i++) {
      hex += bytes[i].toString(16).padStart(2, "0");
    }
    return hex;
  }

  function arrayBufferToBase64(buffer) {
    var bytes = new Uint8Array(buffer);
    var binary = "";
    for (var i = 0; i < bytes.length; i++) {
      binary += String.fromCharCode(bytes[i]);
    }
    return btoa(binary);
  }

  function hexToBase64(hex) {
    var bytes = hexToBytes(hex);
    return arrayBufferToBase64(bytes.buffer);
  }

  function formatHash(hexLower, fmt) {
    if (fmt === "hex-upper") return hexLower.toUpperCase();
    if (fmt === "base64") return hexToBase64(hexLower);
    return hexLower;
  }

  function formatBytes(bytes) {
    if (bytes === 0) return "0 bytes";
    if (bytes < 1024) return bytes + " bytes";
    if (bytes < 1048576) return (bytes / 1024).toFixed(1) + " KB";
    return (bytes / 1048576).toFixed(2) + " MB";
  }

  // ===== State =====
  var currentMode = "text";
  var currentFileBuffer = null;
  var lastHashes = {}; // algo -> hex lowercase

  // ===== Tab Switching =====
  window.hgSwitchTab = function(mode) {
    currentMode = mode;
    document.getElementById("hgTabText").className = "hg-tab" + (mode === "text" ? " active" : "");
    document.getElementById("hgTabFile").className = "hg-tab" + (mode === "file" ? " active" : "");
    document.getElementById("hgTextPane").style.display = mode === "text" ? "block" : "none";
    document.getElementById("hgFilePane").style.display = mode === "file" ? "block" : "none";
    if (mode === "text") {
      hgHashText();
    }
  };

  // ===== Algorithm Checkboxes =====
  var algoChecks = document.querySelectorAll(".hg-algo-check");
  algoChecks.forEach(function(label) {
    label.addEventListener("click", function() {
      var cb = this.querySelector("input");
      cb.checked = !cb.checked;
      this.classList.toggle("active", cb.checked);
      if (currentMode === "text") hgHashText();
      else if (currentFileBuffer) hgHashFile(currentFileBuffer);
    });
  });

  function getSelectedAlgos() {
    var algos = [];
    algoChecks.forEach(function(label) {
      if (label.querySelector("input").checked) {
        algos.push(label.getAttribute("data-algo"));
      }
    });
    return algos;
  }

  // ===== HMAC Toggle =====
  window.hgToggleHmac = function() {
    var on = document.getElementById("hgHmacToggle").checked;
    document.getElementById("hgHmacKeyWrap").className = "hg-hmac-key" + (on ? " visible" : "");
    if (currentMode === "text") hgHashText();
    else if (currentFileBuffer) hgHashFile(currentFileBuffer);
  };

  document.getElementById("hgHmacKey").addEventListener("input", function() {
    if (currentMode === "text") hgHashText();
    else if (currentFileBuffer) hgHashFile(currentFileBuffer);
  });

  // ===== Text Hashing (real-time) =====
  var textInput = document.getElementById("hgTextInput");
  var hashTimer = null;

  textInput.addEventListener("input", function() {
    clearTimeout(hashTimer);
    hashTimer = setTimeout(hgHashText, 80);
  });

  function hgHashText() {
    var text = textInput.value;
    var algos = getSelectedAlgos();
    if (algos.length === 0 || text.length === 0) {
      document.getElementById("hgResults").innerHTML = "";
      lastHashes = {};
      return;
    }
    var encoder = new TextEncoder();
    var data = encoder.encode(text);
    var hmacMode = document.getElementById("hgHmacToggle").checked;
    var hmacKey = document.getElementById("hgHmacKey").value;

    var promises = algos.map(function(algo) {
      if (algo === "MD5") {
        if (hmacMode && hmacKey) {
          var keyBytes = new TextEncoder().encode(hmacKey);
          return Promise.resolve({ algo: algo, hex: hmacMd5(keyBytes, data) });
        }
        return Promise.resolve({ algo: algo, hex: md5(data) });
      }
      if (hmacMode && hmacKey) {
        return crypto.subtle.importKey(
          "raw",
          new TextEncoder().encode(hmacKey),
          { name: "HMAC", hash: algo },
          false,
          ["sign"]
        ).then(function(key) {
          return crypto.subtle.sign("HMAC", key, data);
        }).then(function(sig) {
          return { algo: algo, hex: arrayBufferToHex(sig) };
        });
      }
      return crypto.subtle.digest(algo, data).then(function(buf) {
        return { algo: algo, hex: arrayBufferToHex(buf) };
      });
    });

    Promise.all(promises).then(function(results) {
      lastHashes = {};
      results.forEach(function(r) { lastHashes[r.algo] = r.hex; });
      renderResults(results);
    });
  }

  // ===== File Hashing =====
  function hgHashFile(buffer) {
    var algos = getSelectedAlgos();
    if (algos.length === 0) {
      document.getElementById("hgResults").innerHTML = "";
      lastHashes = {};
      return;
    }
    var data = new Uint8Array(buffer);
    var hmacMode = document.getElementById("hgHmacToggle").checked;
    var hmacKey = document.getElementById("hgHmacKey").value;

    document.getElementById("hgProgress").classList.add("visible");
    document.getElementById("hgProgressFill").style.width = "30%";
    document.getElementById("hgProgressText").textContent = "Hashing file...";

    var promises = algos.map(function(algo) {
      if (algo === "MD5") {
        if (hmacMode && hmacKey) {
          var keyBytes = new TextEncoder().encode(hmacKey);
          return Promise.resolve({ algo: algo, hex: hmacMd5(keyBytes, data) });
        }
        return Promise.resolve({ algo: algo, hex: md5(data) });
      }
      if (hmacMode && hmacKey) {
        return crypto.subtle.importKey(
          "raw",
          new TextEncoder().encode(hmacKey),
          { name: "HMAC", hash: algo },
          false,
          ["sign"]
        ).then(function(key) {
          return crypto.subtle.sign("HMAC", key, data);
        }).then(function(sig) {
          return { algo: algo, hex: arrayBufferToHex(sig) };
        });
      }
      return crypto.subtle.digest(algo, buffer).then(function(buf) {
        return { algo: algo, hex: arrayBufferToHex(buf) };
      });
    });

    Promise.all(promises).then(function(results) {
      lastHashes = {};
      results.forEach(function(r) { lastHashes[r.algo] = r.hex; });
      renderResults(results);
      document.getElementById("hgProgressFill").style.width = "100%";
      document.getElementById("hgProgressText").textContent = "Done";
      setTimeout(function() {
        document.getElementById("hgProgress").classList.remove("visible");
      }, 1000);
    });
  }

  // ===== Render Results =====
  function renderResults(results) {
    var fmt = document.getElementById("hgFormat").value;
    var html = "";
    results.forEach(function(r, idx) {
      var display = formatHash(r.hex, fmt);
      var algoLabel = r.algo;
      if (document.getElementById("hgHmacToggle").checked && document.getElementById("hgHmacKey").value) {
        algoLabel = "HMAC-" + r.algo;
      }
      html += '<div class="hg-result-item">';
      html += '<div class="hg-result-label">' + algoLabel + '</div>';
      html += '<div class="hg-result-row">';
      html += '<div class="hg-result-hash" id="hgHash' + idx + '">' + display + '</div>';
      html += '<button class="hg-btn hg-btn-copy" onclick="hgCopyHash(' + idx + ', this)">Copy</button>';
      html += '</div></div>';
    });
    document.getElementById("hgResults").innerHTML = html;
  }

  // ===== Reformat on format change =====
  window.hgReformat = function() {
    if (Object.keys(lastHashes).length === 0) return;
    var fmt = document.getElementById("hgFormat").value;
    var algos = getSelectedAlgos();
    var results = algos.filter(function(a) { return lastHashes[a]; }).map(function(a) {
      return { algo: a, hex: lastHashes[a] };
    });
    renderResults(results);
  };

  // ===== Copy Hash =====
  window.hgCopyHash = function(idx, btn) {
    var el = document.getElementById("hgHash" + idx);
    if (!el) return;
    navigator.clipboard.writeText(el.textContent).then(function() {
      btn.classList.add("copied");
      btn.textContent = "Copied";
      setTimeout(function() {
        btn.classList.remove("copied");
        btn.textContent = "Copy";
      }, 2000);
    });
  };

  // ===== File Input Handling =====
  var dropzone = document.getElementById("hgDropzone");
  var fileInput = document.getElementById("hgFileInput");

  document.getElementById("hgBrowseBtn").addEventListener("click", function(e) {
    e.stopPropagation();
    fileInput.click();
  });

  dropzone.addEventListener("click", function() { fileInput.click(); });

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
    if (e.dataTransfer.files.length > 0) handleFile(e.dataTransfer.files[0]);
  });

  fileInput.addEventListener("change", function() {
    if (fileInput.files.length > 0) handleFile(fileInput.files[0]);
  });

  function handleFile(file) {
    document.getElementById("hgFileName").textContent = file.name;
    document.getElementById("hgFileSize").textContent = formatBytes(file.size);
    document.getElementById("hgFileInfo").classList.add("visible");

    var reader = new FileReader();
    reader.onload = function(e) {
      currentFileBuffer = e.target.result;
      hgHashFile(currentFileBuffer);
    };
    reader.readAsArrayBuffer(file);
  }

  document.getElementById("hgFileDismiss").addEventListener("click", function() {
    document.getElementById("hgFileInfo").classList.remove("visible");
    currentFileBuffer = null;
    fileInput.value = "";
    document.getElementById("hgResults").innerHTML = "";
    lastHashes = {};
  });

  // ===== Hash Comparison =====
  window.hgCompare = function() {
    var a = document.getElementById("hgCompareA").value.trim().toLowerCase();
    var b = document.getElementById("hgCompareB").value.trim().toLowerCase();
    var resultEl = document.getElementById("hgCompareResult");
    var diffEl = document.getElementById("hgDiffDisplay");

    if (!a || !b) {
      resultEl.className = "hg-compare-result";
      diffEl.className = "hg-diff-display";
      return;
    }

    if (a === b) {
      resultEl.className = "hg-compare-result visible hg-compare-match";
      resultEl.innerHTML = "&#10003; Hashes match";
      diffEl.className = "hg-diff-display";
    } else {
      resultEl.className = "hg-compare-result visible hg-compare-mismatch";
      resultEl.innerHTML = "&#10007; Hashes do not match";

      // Character-by-character diff
      var maxLen = Math.max(a.length, b.length);
      var diffHtml = "<div style='margin-bottom:8px;color:var(--hg-text-muted);font-size:0.78rem;'>Character-by-character comparison:</div>";
      diffHtml += "<div>A: ";
      for (var i = 0; i < maxLen; i++) {
        var ca = a[i] || " ";
        var cb = b[i] || " ";
        if (ca === cb) {
          diffHtml += '<span class="hg-diff-match">' + ca + '</span>';
        } else {
          diffHtml += '<span class="hg-diff-differ">' + ca + '</span>';
        }
      }
      diffHtml += "</div><div>B: ";
      for (var i = 0; i < maxLen; i++) {
        var ca = a[i] || " ";
        var cb = b[i] || " ";
        if (ca === cb) {
          diffHtml += '<span class="hg-diff-match">' + cb + '</span>';
        } else {
          diffHtml += '<span class="hg-diff-differ">' + cb + '</span>';
        }
      }
      diffHtml += "</div>";
      diffEl.innerHTML = diffHtml;
      diffEl.className = "hg-diff-display visible";
    }
  };

  // ===== File Integrity Checker =====
  var verifyFileInput = document.getElementById("hgVerifyFileInput");

  verifyFileInput.addEventListener("change", function() {
    if (verifyFileInput.files.length === 0) return;
    var file = verifyFileInput.files[0];
    var expectedHash = document.getElementById("hgExpectedHash").value.trim().toLowerCase();
    var algo = document.getElementById("hgVerifyAlgo").value;

    document.getElementById("hgVerifyFileName").textContent = file.name + " (" + formatBytes(file.size) + ")";

    if (!expectedHash) {
      showVerifyResult(false, "Please enter an expected hash value first.");
      verifyFileInput.value = "";
      return;
    }

    document.getElementById("hgVerifyProgress").classList.add("visible");
    document.getElementById("hgVerifyProgressFill").style.width = "40%";
    document.getElementById("hgVerifyProgressText").textContent = "Hashing file with " + algo + "...";

    var reader = new FileReader();
    reader.onload = function(e) {
      var buffer = e.target.result;
      var data = new Uint8Array(buffer);

      var hashPromise;
      if (algo === "MD5") {
        hashPromise = Promise.resolve(md5(data));
      } else {
        hashPromise = crypto.subtle.digest(algo, buffer).then(function(buf) {
          return arrayBufferToHex(buf);
        });
      }

      hashPromise.then(function(computedHex) {
        document.getElementById("hgVerifyProgressFill").style.width = "100%";
        document.getElementById("hgVerifyProgressText").textContent = "Done";

        // Normalize expected hash: remove spaces, convert to lower for hex comparison
        var normalExpected = expectedHash.replace(/\s+/g, "").toLowerCase();
        // If expected looks like base64, try converting computed to base64 for comparison
        var match = (normalExpected === computedHex);
        if (!match) {
          // try base64 comparison
          var computedB64 = hexToBase64(computedHex);
          match = (normalExpected === computedB64.toLowerCase()) || (expectedHash.trim() === computedB64);
        }
        if (!match) {
          // try uppercase
          match = (normalExpected === computedHex.toUpperCase().toLowerCase());
        }

        if (match) {
          showVerifyResult(true, "File integrity verified. The computed " + algo + " hash matches the expected value.");
        } else {
          showVerifyResult(false, "Mismatch. Computed " + algo + ": " + computedHex);
        }

        setTimeout(function() {
          document.getElementById("hgVerifyProgress").classList.remove("visible");
        }, 800);
      });
    };
    reader.readAsArrayBuffer(file);
  });

  function showVerifyResult(pass, msg) {
    var el = document.getElementById("hgVerifyResult");
    var icon = document.getElementById("hgVerifyIcon");
    var text = document.getElementById("hgVerifyText");
    el.className = "hg-verify-result visible " + (pass ? "hg-verify-pass" : "hg-verify-fail");
    icon.innerHTML = pass ? "&#10003;" : "&#10007;";
    text.textContent = msg;
  }

})();
</script>
