---
layout: page
title: "Color Picker from Image - Free Hex & RGB Tool | Zovo"
description: "Free color picker from image -- upload any photo and extract exact hex, RGB, and HSL codes instantly. Drag-and-drop, paste, and zoom magnifier included."
permalink: /tools/color-picker/
keywords: "color picker from image, hex color picker, image color code, pick color from photo, rgb color picker, color extractor, eyedropper tool online"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [color picker, hex color, rgb color, image color extractor, design tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>
  :root {
    --cp-primary: #6C5CE7;
    --cp-primary-dark: #5A4BD1;
    --cp-primary-light: #A29BFE;
    --cp-bg: #F8F9FE;
    --cp-surface: #FFFFFF;
    --cp-text: #2D3436;
    --cp-text-muted: #636E72;
    --cp-border: #DFE6E9;
    --cp-success: #00B894;
    --cp-radius: 12px;
  }

  .cp-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--cp-text);
    max-width: 960px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .cp-wrapper * {
    box-sizing: border-box;
  }

  .cp-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .cp-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--cp-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .cp-hero h1 span {
    color: var(--cp-primary);
  }

  .cp-intro {
    font-size: 1.05rem;
    color: var(--cp-text-muted);
    max-width: 700px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Upload Area */
  .cp-upload {
    background: var(--cp-bg);
    border: 2px dashed var(--cp-border);
    border-radius: var(--cp-radius);
    padding: 48px 24px;
    text-align: center;
    cursor: pointer;
    transition: border-color 0.2s, background 0.2s;
    margin-bottom: 20px;
    position: relative;
  }

  .cp-upload:hover,
  .cp-upload.dragover {
    border-color: var(--cp-primary);
    background: #F0EEFF;
  }

  .cp-upload-icon {
    display: block;
    margin: 0 auto 12px;
  }

  .cp-upload-title {
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--cp-text);
    margin: 0 0 6px;
  }

  .cp-upload-hint {
    font-size: 0.88rem;
    color: var(--cp-text-muted);
    margin: 0;
  }

  .cp-upload input[type="file"] {
    position: absolute;
    inset: 0;
    opacity: 0;
    cursor: pointer;
  }

  /* Canvas Area */
  .cp-canvas-wrap {
    display: none;
    background: var(--cp-surface);
    border: 1px solid var(--cp-border);
    border-radius: var(--cp-radius);
    overflow: hidden;
    margin-bottom: 20px;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .cp-canvas-toolbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    border-bottom: 1px solid var(--cp-border);
    background: var(--cp-bg);
    gap: 8px;
    flex-wrap: wrap;
  }

  .cp-canvas-filename {
    font-size: 0.85rem;
    color: var(--cp-text-muted);
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    max-width: 300px;
  }

  .cp-btn-new {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 6px 14px;
    font-size: 0.82rem;
    font-weight: 500;
    font-family: inherit;
    background: var(--cp-surface);
    color: var(--cp-text);
    border: 1px solid var(--cp-border);
    border-radius: 8px;
    cursor: pointer;
    transition: border-color 0.2s;
  }

  .cp-btn-new:hover {
    border-color: var(--cp-primary);
  }

  .cp-canvas-container {
    position: relative;
    overflow: auto;
    max-height: 520px;
    cursor: crosshair;
  }

  .cp-canvas-container canvas {
    display: block;
    max-width: 100%;
    height: auto;
  }

  /* Magnifier */
  .cp-magnifier {
    position: absolute;
    width: 120px;
    height: 120px;
    border: 3px solid var(--cp-primary);
    border-radius: 50%;
    pointer-events: none;
    display: none;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(0,0,0,0.25);
    z-index: 10;
  }

  .cp-magnifier canvas {
    display: block;
  }

  .cp-magnifier-crosshair {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 12px;
    height: 12px;
    margin: -6px 0 0 -6px;
    border: 1.5px solid rgba(255,255,255,0.9);
    border-radius: 50%;
    box-shadow: 0 0 0 1px rgba(0,0,0,0.3);
    pointer-events: none;
  }

  /* Color Result Panel */
  .cp-result {
    display: none;
    background: var(--cp-surface);
    border: 1px solid var(--cp-border);
    border-radius: var(--cp-radius);
    padding: 20px;
    margin-bottom: 20px;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .cp-result-row {
    display: flex;
    gap: 20px;
    align-items: flex-start;
    flex-wrap: wrap;
  }

  .cp-swatch-big {
    width: 80px;
    height: 80px;
    border-radius: 12px;
    border: 1px solid var(--cp-border);
    flex-shrink: 0;
    box-shadow: inset 0 0 0 1px rgba(0,0,0,0.05);
  }

  .cp-color-values {
    flex: 1;
    min-width: 200px;
  }

  .cp-color-field {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 8px;
  }

  .cp-color-label {
    font-size: 0.78rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: var(--cp-text-muted);
    width: 36px;
    flex-shrink: 0;
  }

  .cp-color-value {
    flex: 1;
    font-family: 'SF Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.92rem;
    color: var(--cp-text);
    background: var(--cp-bg);
    padding: 6px 10px;
    border-radius: 6px;
    border: 1px solid var(--cp-border);
    user-select: all;
  }

  .cp-copy-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 32px;
    height: 32px;
    background: var(--cp-surface);
    border: 1px solid var(--cp-border);
    border-radius: 6px;
    cursor: pointer;
    transition: border-color 0.2s, background 0.2s;
    flex-shrink: 0;
    padding: 0;
    font-family: inherit;
  }

  .cp-copy-btn:hover {
    border-color: var(--cp-primary);
    background: var(--cp-bg);
  }

  .cp-copy-btn.copied {
    border-color: var(--cp-success);
    background: #E8FFF7;
  }

  .cp-copy-btn svg {
    width: 15px;
    height: 15px;
    color: var(--cp-text-muted);
  }

  .cp-copy-btn.copied svg {
    color: var(--cp-success);
  }

  /* Color History */
  .cp-history {
    display: none;
    background: var(--cp-surface);
    border: 1px solid var(--cp-border);
    border-radius: var(--cp-radius);
    padding: 16px 20px;
    margin-bottom: 20px;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .cp-history-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
  }

  .cp-history-title {
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--cp-text);
  }

  .cp-history-clear {
    font-size: 0.78rem;
    color: var(--cp-text-muted);
    background: none;
    border: none;
    cursor: pointer;
    font-family: inherit;
    padding: 2px 6px;
    border-radius: 4px;
    transition: background 0.2s;
  }

  .cp-history-clear:hover {
    background: var(--cp-bg);
    color: var(--cp-text);
  }

  .cp-history-swatches {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .cp-history-swatch {
    width: 40px;
    height: 40px;
    border-radius: 8px;
    border: 2px solid var(--cp-border);
    cursor: pointer;
    transition: transform 0.15s, border-color 0.15s;
    position: relative;
    flex-shrink: 0;
  }

  .cp-history-swatch:hover {
    transform: scale(1.12);
    border-color: var(--cp-primary);
  }

  .cp-history-swatch-tip {
    display: none;
    position: absolute;
    bottom: calc(100% + 6px);
    left: 50%;
    transform: translateX(-50%);
    background: var(--cp-text);
    color: #fff;
    font-size: 0.72rem;
    font-family: 'SF Mono', 'Fira Code', 'Consolas', monospace;
    padding: 3px 7px;
    border-radius: 4px;
    white-space: nowrap;
    pointer-events: none;
    z-index: 20;
  }

  .cp-history-swatch:hover .cp-history-swatch-tip {
    display: block;
  }

  /* FAQ */
  .cp-faq {
    margin-top: 48px;
    padding-top: 32px;
    border-top: 1px solid var(--cp-border);
  }

  .cp-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    color: var(--cp-text);
  }

  .cp-faq-item {
    margin-bottom: 24px;
  }

  .cp-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--cp-text);
  }

  .cp-faq-item p {
    margin: 0;
    color: var(--cp-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  /* Responsive */
  @media (max-width: 640px) {
    .cp-hero h1 {
      font-size: 1.6rem;
    }

    .cp-upload {
      padding: 32px 16px;
    }

    .cp-result-row {
      flex-direction: column;
      align-items: stretch;
    }

    .cp-swatch-big {
      width: 100%;
      height: 48px;
    }

    .cp-canvas-container {
      max-height: 360px;
    }

    .cp-magnifier {
      width: 90px;
      height: 90px;
    }

    .cp-history-swatch {
      width: 34px;
      height: 34px;
    }
  }
</style>

<div class="cp-wrapper" id="cpApp">

  <div class="cp-hero">
    <h1><span>Color Picker</span> from Image</h1>
    <p class="cp-intro">Upload any image and click anywhere to extract the exact color. Get hex, RGB, and HSL color codes instantly -- perfect for designers, developers, and anyone who needs to pick a color from a photo. Drag and drop, paste from clipboard, or browse your files. The zoom magnifier helps you target the precise pixel every time.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <!-- Upload Area -->
  <div class="cp-upload" id="cpUpload">
    <svg class="cp-upload-icon" width="48" height="48" viewBox="0 0 48 48" fill="none"><rect x="6" y="10" width="36" height="28" rx="4" stroke="#6C5CE7" stroke-width="2.5" fill="none"/><circle cx="18" cy="22" r="4" stroke="#6C5CE7" stroke-width="2"/><path d="M6 34l10-10 8 8 6-6 12 12" stroke="#6C5CE7" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" fill="none"/><path d="M24 4v6M24 4l-3 3M24 4l3 3" stroke="#A29BFE" stroke-width="2" stroke-linecap="round"/></svg>
    <p class="cp-upload-title">Drop an image here, paste from clipboard, or click to browse</p>
    <p class="cp-upload-hint">Supports JPG, PNG, WebP, GIF, SVG &mdash; processed locally in your browser</p>
    <input type="file" id="cpFileInput" accept="image/*">
  </div>

  <!-- Canvas Area -->
  <div class="cp-canvas-wrap" id="cpCanvasWrap">
    <div class="cp-canvas-toolbar">
      <span class="cp-canvas-filename" id="cpFilename"></span>
      <button class="cp-btn-new" id="cpNewImage" onclick="cpLoadNew()">
        <svg width="14" height="14" viewBox="0 0 16 16" fill="none"><path d="M8 2v12M2 8h12" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
        New Image
      </button>
    </div>
    <div class="cp-canvas-container" id="cpCanvasContainer">
      <canvas id="cpCanvas"></canvas>
      <div class="cp-magnifier" id="cpMagnifier">
        <canvas id="cpMagCanvas" width="120" height="120"></canvas>
        <div class="cp-magnifier-crosshair"></div>
      </div>
    </div>
  </div>

  <!-- Color Result Panel -->
  <div class="cp-result" id="cpResult">
    <div class="cp-result-row">
      <div class="cp-swatch-big" id="cpSwatch"></div>
      <div class="cp-color-values">
        <div class="cp-color-field">
          <span class="cp-color-label">HEX</span>
          <span class="cp-color-value" id="cpHex">#6C5CE7</span>
          <button class="cp-copy-btn" onclick="cpCopyValue('cpHex', this)" title="Copy HEX">
            <svg viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
          </button>
        </div>
        <div class="cp-color-field">
          <span class="cp-color-label">RGB</span>
          <span class="cp-color-value" id="cpRgb">rgb(108, 92, 231)</span>
          <button class="cp-copy-btn" onclick="cpCopyValue('cpRgb', this)" title="Copy RGB">
            <svg viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
          </button>
        </div>
        <div class="cp-color-field">
          <span class="cp-color-label">HSL</span>
          <span class="cp-color-value" id="cpHsl">hsl(247, 75%, 63%)</span>
          <button class="cp-copy-btn" onclick="cpCopyValue('cpHsl', this)" title="Copy HSL">
            <svg viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
          </button>
        </div>
      </div>
    </div>
  </div>

  <!-- Color History -->
  <div class="cp-history" id="cpHistory">
    <div class="cp-history-header">
      <span class="cp-history-title">Recent Colors</span>
      <button class="cp-history-clear" onclick="cpClearHistory()">Clear</button>
    </div>
    <div class="cp-history-swatches" id="cpSwatches"></div>
  </div>

  <!-- FAQ Section with Schema.org -->
  <div class="cp-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="cp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I pick a color from an image online?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Upload any image to this free color picker tool by dragging and dropping it onto the page, pasting from your clipboard, or clicking to browse your files. Once the image loads, click or tap anywhere on it to instantly see the exact hex, RGB, and HSL color codes for that pixel. A zoom magnifier follows your cursor so you can target the precise spot you want. All processing happens locally in your browser -- nothing is uploaded to a server.</p>
      </div>
    </div>

    <div class="cp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between HEX, RGB, and HSL color codes?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">HEX codes represent colors with a six-character string like #6C5CE7 and are the most common format in CSS and web design. RGB describes colors by their red, green, and blue channel values from 0 to 255, which is useful for code and image editors. HSL stands for hue, saturation, and lightness -- it maps to how humans naturally think about color and makes it easy to create variations by adjusting one value. This tool shows all three formats so you can copy whichever your project needs.</p>
      </div>
    </div>

    <div class="cp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I pick colors from a screenshot or photo on my phone?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This color picker from image tool works on mobile devices. You can upload a screenshot or photo from your camera roll using the file browser, or paste an image you copied to your clipboard. The interface adapts to smaller screens and touch input so you can tap to select any pixel. It supports JPG, PNG, WebP, GIF, and SVG files of any size.</p>
      </div>
    </div>

    <div class="cp-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is the hex color code extracted from my image?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The color extraction is pixel-perfect. The tool reads the raw pixel data directly from the HTML canvas element, which means you get the exact color value of the pixel you clicked -- no approximation or sampling. The zoom magnifier helps you pick the right pixel in areas with fine detail or gradients. Keep in mind that JPEG compression can slightly alter colors from the original, so for absolute precision use PNG or WebP source images.</p>
      </div>
    </div>

  </div>

  <div style="margin: 2rem 0; padding: 1rem 1.25rem; background: #f3f0ff; border: 1px solid #6C5CE7; border-radius: 8px;">
<div style="font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.1em; color: #6C5CE7; margin-bottom: 0.5rem; font-weight: 600;">Related Guide</div>
<a href="/guides/chrome-dark-mode-complete-guide/" style="color: #1d1d1f; text-decoration: none; font-size: 0.95rem; font-weight: 500;">Chrome Dark Mode: Complete Guide &rarr;</a>
</div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/qr-code-generator/" style="color:#00ff88;text-decoration:none;">QR Code Generator</a> - Create custom QR codes with colors and logos</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/barcode-generator/" style="color:#00ff88;text-decoration:none;">Barcode Generator</a> - Create barcodes in multiple formats</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/ai-detector/" style="color:#00ff88;text-decoration:none;">AI Content Detector</a> - Analyze text for AI-generated patterns</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/password-generator/" style="color:#00ff88;text-decoration:none;">Password Generator</a> - Generate secure random passwords</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>


  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid #2a2a3a; margin-top: 3rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var canvas = document.getElementById("cpCanvas");
  var ctx = canvas.getContext("2d", { willReadFrequently: true });
  var magCanvas = document.getElementById("cpMagCanvas");
  var magCtx = magCanvas.getContext("2d");
  var container = document.getElementById("cpCanvasContainer");
  var magnifier = document.getElementById("cpMagnifier");
  var uploadEl = document.getElementById("cpUpload");
  var canvasWrap = document.getElementById("cpCanvasWrap");
  var resultEl = document.getElementById("cpResult");
  var historyEl = document.getElementById("cpHistory");
  var swatchesEl = document.getElementById("cpSwatches");
  var fileInput = document.getElementById("cpFileInput");

  var imgData = null; // ImageData for the full canvas
  var displayScale = 1; // ratio of displayed canvas size to actual canvas size
  var colorHistory = [];
  var MAX_HISTORY = 10;
  var MAG_ZOOM = 6;

  // --- Image Loading ---

  function loadImageFromFile(file) {
    if (!file || !file.type.match(/^image\//)) return;
    var reader = new FileReader();
    reader.onload = function(e) {
      loadImageFromSrc(e.target.result, file.name || "Image");
    };
    reader.readAsDataURL(file);
  }

  function loadImageFromSrc(src, name) {
    var img = new Image();
    img.onload = function() {
      // Limit canvas size for performance
      var maxW = 1600;
      var w = img.naturalWidth;
      var h = img.naturalHeight;
      if (w > maxW) {
        h = Math.round(h * (maxW / w));
        w = maxW;
      }
      canvas.width = w;
      canvas.height = h;
      ctx.drawImage(img, 0, 0, w, h);
      imgData = ctx.getImageData(0, 0, w, h);

      document.getElementById("cpFilename").textContent = name;
      uploadEl.style.display = "none";
      canvasWrap.style.display = "block";
      resultEl.style.display = "none";

      // Compute display scale
      requestAnimationFrame(function() {
        displayScale = canvas.width / canvas.offsetWidth;
      });
    };
    img.crossOrigin = "anonymous";
    img.src = src;
  }

  // File input change
  fileInput.addEventListener("change", function() {
    if (this.files && this.files[0]) {
      loadImageFromFile(this.files[0]);
    }
  });

  // Drag and drop
  uploadEl.addEventListener("dragover", function(e) {
    e.preventDefault();
    uploadEl.classList.add("dragover");
  });

  uploadEl.addEventListener("dragleave", function() {
    uploadEl.classList.remove("dragover");
  });

  uploadEl.addEventListener("drop", function(e) {
    e.preventDefault();
    uploadEl.classList.remove("dragover");
    var files = e.dataTransfer.files;
    if (files && files[0]) {
      loadImageFromFile(files[0]);
    }
  });

  // Clipboard paste
  document.addEventListener("paste", function(e) {
    var items = e.clipboardData && e.clipboardData.items;
    if (!items) return;
    for (var i = 0; i < items.length; i++) {
      if (items[i].type.match(/^image\//)) {
        e.preventDefault();
        loadImageFromFile(items[i].getAsFile());
        return;
      }
    }
  });

  // New image button
  window.cpLoadNew = function() {
    uploadEl.style.display = "";
    canvasWrap.style.display = "none";
    resultEl.style.display = "none";
    fileInput.value = "";
    imgData = null;
  };

  // --- Color Picking ---

  function getPixelColor(x, y) {
    if (!imgData) return null;
    // Map displayed coords to canvas coords
    var cx = Math.round(x * displayScale);
    var cy = Math.round(y * displayScale);
    if (cx < 0 || cy < 0 || cx >= imgData.width || cy >= imgData.height) return null;
    var idx = (cy * imgData.width + cx) * 4;
    return {
      r: imgData.data[idx],
      g: imgData.data[idx + 1],
      b: imgData.data[idx + 2]
    };
  }

  function rgbToHex(r, g, b) {
    return "#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1).toUpperCase();
  }

  function rgbToHsl(r, g, b) {
    r /= 255; g /= 255; b /= 255;
    var max = Math.max(r, g, b);
    var min = Math.min(r, g, b);
    var h, s, l = (max + min) / 2;

    if (max === min) {
      h = s = 0;
    } else {
      var d = max - min;
      s = l > 0.5 ? d / (2 - max - min) : d / (max + min);
      switch (max) {
        case r: h = ((g - b) / d + (g < b ? 6 : 0)) / 6; break;
        case g: h = ((b - r) / d + 2) / 6; break;
        case b: h = ((r - g) / d + 4) / 6; break;
      }
    }
    return {
      h: Math.round(h * 360),
      s: Math.round(s * 100),
      l: Math.round(l * 100)
    };
  }

  function displayColor(color) {
    var hex = rgbToHex(color.r, color.g, color.b);
    var hsl = rgbToHsl(color.r, color.g, color.b);

    document.getElementById("cpSwatch").style.background = hex;
    document.getElementById("cpHex").textContent = hex;
    document.getElementById("cpRgb").textContent = "rgb(" + color.r + ", " + color.g + ", " + color.b + ")";
    document.getElementById("cpHsl").textContent = "hsl(" + hsl.h + ", " + hsl.s + "%, " + hsl.l + "%)";
    resultEl.style.display = "block";

    // Reset copy button states
    var btns = resultEl.querySelectorAll(".cp-copy-btn");
    for (var i = 0; i < btns.length; i++) {
      btns[i].classList.remove("copied");
    }
  }

  function addToHistory(color) {
    var hex = rgbToHex(color.r, color.g, color.b);
    // Remove duplicates
    colorHistory = colorHistory.filter(function(c) { return c.hex !== hex; });
    colorHistory.unshift({ hex: hex, r: color.r, g: color.g, b: color.b });
    if (colorHistory.length > MAX_HISTORY) {
      colorHistory = colorHistory.slice(0, MAX_HISTORY);
    }
    renderHistory();
  }

  function renderHistory() {
    if (colorHistory.length === 0) {
      historyEl.style.display = "none";
      return;
    }
    historyEl.style.display = "block";
    var html = "";
    for (var i = 0; i < colorHistory.length; i++) {
      var c = colorHistory[i];
      html += '<div class="cp-history-swatch" style="background:' + c.hex + '" onclick="cpPickHistory(' + i + ')" title="' + c.hex + '">';
      html += '<span class="cp-history-swatch-tip">' + c.hex + '</span>';
      html += '</div>';
    }
    swatchesEl.innerHTML = html;
  }

  window.cpPickHistory = function(idx) {
    if (colorHistory[idx]) {
      displayColor(colorHistory[idx]);
    }
  };

  window.cpClearHistory = function() {
    colorHistory = [];
    renderHistory();
  };

  // Canvas click -- pick color
  container.addEventListener("click", function(e) {
    if (!imgData) return;
    var rect = canvas.getBoundingClientRect();
    var x = e.clientX - rect.left;
    var y = e.clientY - rect.top;
    var color = getPixelColor(x, y);
    if (color) {
      displayColor(color);
      addToHistory(color);
    }
  });

  // --- Magnifier ---

  function updateMagnifier(e) {
    if (!imgData) return;
    var rect = canvas.getBoundingClientRect();
    var x = e.clientX - rect.left;
    var y = e.clientY - rect.top;

    // Position magnifier
    var contRect = container.getBoundingClientRect();
    var mx = e.clientX - contRect.left;
    var my = e.clientY - contRect.top;

    // Offset magnifier so it doesn't overlap cursor
    var magSize = magnifier.offsetWidth;
    var offsetX = 20;
    var offsetY = -magSize - 10;

    // Keep magnifier within container
    var posX = mx + offsetX + container.scrollLeft;
    var posY = my + offsetY + container.scrollTop;

    if (posY < container.scrollTop) {
      posY = my + 20 + container.scrollTop;
    }
    if (posX + magSize > container.scrollWidth) {
      posX = mx - magSize - 10 + container.scrollLeft;
    }

    magnifier.style.left = posX + "px";
    magnifier.style.top = posY + "px";
    magnifier.style.display = "block";

    // Draw magnified view
    var srcX = Math.round(x * displayScale) - Math.floor(magCanvas.width / MAG_ZOOM / 2);
    var srcY = Math.round(y * displayScale) - Math.floor(magCanvas.height / MAG_ZOOM / 2);
    var srcW = Math.ceil(magCanvas.width / MAG_ZOOM);
    var srcH = Math.ceil(magCanvas.height / MAG_ZOOM);

    magCtx.imageSmoothingEnabled = false;
    magCtx.clearRect(0, 0, magCanvas.width, magCanvas.height);
    magCtx.drawImage(canvas, srcX, srcY, srcW, srcH, 0, 0, magCanvas.width, magCanvas.height);

    // Draw pixel grid at high zoom
    magCtx.strokeStyle = "rgba(255,255,255,0.15)";
    magCtx.lineWidth = 0.5;
    var step = MAG_ZOOM;
    for (var gx = 0; gx < magCanvas.width; gx += step) {
      magCtx.beginPath();
      magCtx.moveTo(gx, 0);
      magCtx.lineTo(gx, magCanvas.height);
      magCtx.stroke();
    }
    for (var gy = 0; gy < magCanvas.height; gy += step) {
      magCtx.beginPath();
      magCtx.moveTo(0, gy);
      magCtx.lineTo(magCanvas.width, gy);
      magCtx.stroke();
    }
  }

  container.addEventListener("mousemove", function(e) {
    updateMagnifier(e);
  });

  container.addEventListener("mouseleave", function() {
    magnifier.style.display = "none";
  });

  // Recalculate display scale on resize
  window.addEventListener("resize", function() {
    if (canvas.width && canvas.offsetWidth) {
      displayScale = canvas.width / canvas.offsetWidth;
    }
  });

  // --- Copy ---

  window.cpCopyValue = function(elId, btn) {
    var text = document.getElementById(elId).textContent;
    navigator.clipboard.writeText(text).then(function() {
      btn.classList.add("copied");
      setTimeout(function() {
        btn.classList.remove("copied");
      }, 1500);
    });
  };

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Color Picker",
      "url": "https://theluckystrike.github.io/tools/color-picker/",
      "applicationCategory": "DesignApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Color Picker", "item": "https://theluckystrike.github.io/tools/color-picker/" }
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
