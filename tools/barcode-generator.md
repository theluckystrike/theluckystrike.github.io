---
layout: page
title: "Barcode Generator - Free Online Barcode Maker | Zovo"
description: "Free barcode generator -- create Code 128, Code 39, EAN-13, UPC-A, and QR codes instantly. Download as PNG or copy to clipboard with one click."
permalink: /tools/barcode-generator/
keywords: "barcode generator, free barcode maker, qr code generator, code 128 barcode, ean-13 barcode, upc-a barcode"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [barcode generator, qr code, code 128, ean-13, upc-a, code 39, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/jsbarcode@3.11.6/dist/JsBarcode.all.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.3/build/qrcode.min.js"></script>

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
    --zovo-error: #E17055;
    --zovo-radius: 12px;
  }

  .bcg-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--zovo-text);
    max-width: 820px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .bcg-wrapper * {
    box-sizing: border-box;
  }

  .bcg-hero {
    text-align: center;
    padding: 40px 0 32px;
  }

  .bcg-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--zovo-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .bcg-hero h1 span {
    color: var(--zovo-primary);
  }

  .bcg-intro {
    font-size: 1.05rem;
    color: var(--zovo-text-muted);
    max-width: 640px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Tool Card */
  .bcg-tool {
    background: var(--zovo-surface);
    border: 1px solid var(--zovo-border);
    border-radius: var(--zovo-radius);
    padding: 28px;
    margin-bottom: 32px;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  /* Controls */
  .bcg-controls {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    align-items: end;
    margin-bottom: 20px;
  }

  .bcg-field {
    display: flex;
    flex-direction: column;
    gap: 6px;
    flex: 1;
    min-width: 140px;
  }

  .bcg-field-wide {
    flex: 2;
    min-width: 240px;
  }

  .bcg-field label {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--zovo-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .bcg-field select,
  .bcg-field input[type="text"] {
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    padding: 10px 14px;
    border: 1.5px solid var(--zovo-border);
    border-radius: 8px;
    background: var(--zovo-bg);
    color: var(--zovo-text);
    transition: border-color 0.2s;
    appearance: auto;
  }

  .bcg-field select:focus,
  .bcg-field input[type="text"]:focus {
    outline: none;
    border-color: var(--zovo-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.12);
  }

  .bcg-hint {
    font-size: 0.78rem;
    color: var(--zovo-text-muted);
    margin-top: 2px;
  }

  .bcg-btn-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .bcg-btn {
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

  .bcg-btn-generate {
    background: var(--zovo-primary);
    color: #fff;
  }

  .bcg-btn-generate:hover {
    background: var(--zovo-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3);
  }

  .bcg-btn-download {
    background: var(--zovo-bg);
    color: var(--zovo-primary);
    border: 1.5px solid var(--zovo-primary-light);
  }

  .bcg-btn-download:hover {
    background: rgba(108, 92, 231, 0.08);
  }

  .bcg-btn-copy {
    background: var(--zovo-bg);
    color: var(--zovo-primary);
    border: 1.5px solid var(--zovo-primary-light);
  }

  .bcg-btn-copy:hover {
    background: rgba(108, 92, 231, 0.08);
  }

  .bcg-btn-copy.copied {
    background: var(--zovo-success);
    color: #fff;
    border-color: var(--zovo-success);
  }

  /* Output */
  .bcg-output-wrap {
    position: relative;
    margin-top: 20px;
  }

  .bcg-output {
    background: var(--zovo-bg);
    border: 1.5px solid var(--zovo-border);
    border-radius: 8px;
    padding: 24px;
    min-height: 180px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 12px;
  }

  .bcg-output canvas {
    max-width: 100%;
    height: auto;
  }

  .bcg-output svg {
    max-width: 100%;
    height: auto;
  }

  .bcg-placeholder {
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    text-align: center;
    padding: 40px 0;
  }

  .bcg-error {
    color: var(--zovo-error);
    font-size: 0.9rem;
    font-weight: 500;
    text-align: center;
    padding: 8px 16px;
    background: rgba(225, 112, 85, 0.08);
    border-radius: 8px;
  }

  .bcg-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 12px;
    font-size: 0.82rem;
    color: var(--zovo-text-muted);
  }

  /* CTA */
  .bcg-cta {
    background: linear-gradient(135deg, #6C5CE7 0%, #A29BFE 100%);
    border-radius: var(--zovo-radius);
    padding: 32px;
    text-align: center;
    margin: 40px 0;
  }

  .bcg-cta h3 {
    color: #fff;
    font-size: 1.3rem;
    font-weight: 700;
    margin: 0 0 10px;
  }

  .bcg-cta p {
    color: rgba(255,255,255,0.88);
    font-size: 0.95rem;
    margin: 0 0 20px;
    line-height: 1.6;
  }

  .bcg-cta a {
    display: inline-block;
    background: #fff;
    color: var(--zovo-primary);
    font-weight: 600;
    font-size: 0.95rem;
    padding: 10px 28px;
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.2s;
  }

  .bcg-cta a:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 16px rgba(0,0,0,0.15);
  }

  /* FAQ */
  .bcg-faq {
    margin-top: 48px;
    padding-top: 32px;
    border-top: 1px solid var(--zovo-border);
  }

  .bcg-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    color: var(--zovo-text);
  }

  .bcg-faq-item {
    margin-bottom: 24px;
  }

  .bcg-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--zovo-text);
  }

  .bcg-faq-item p {
    margin: 0;
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  /* SEO Content */
  .bcg-seo {
    margin-top: 48px;
    padding-top: 32px;
    border-top: 1px solid var(--zovo-border);
  }

  .bcg-seo h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--zovo-text);
  }

  .bcg-seo h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin: 24px 0 8px;
    color: var(--zovo-text);
  }

  .bcg-seo p {
    margin: 0 0 14px;
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .bcg-seo ul {
    margin: 0 0 14px;
    padding-left: 20px;
    color: var(--zovo-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .bcg-seo ul li {
    margin-bottom: 6px;
  }

  /* Responsive */
  @media (max-width: 600px) {
    .bcg-hero h1 {
      font-size: 1.6rem;
    }

    .bcg-tool {
      padding: 18px;
    }

    .bcg-controls {
      flex-direction: column;
    }

    .bcg-field {
      min-width: 100%;
    }

    .bcg-field-wide {
      min-width: 100%;
    }

    .bcg-btn-row {
      width: 100%;
    }

    .bcg-btn {
      flex: 1;
      justify-content: center;
    }

    .bcg-output {
      padding: 16px;
    }

    .bcg-cta {
      padding: 24px 18px;
    }
  }
</style>

<div class="bcg-wrapper" id="bcgApp">

  <div class="bcg-hero">
    <h1><span>Barcode</span> Generator</h1>
    <p class="bcg-intro">Generate barcodes for free. Create Code 128, Code 39, EAN-13, UPC-A, and QR codes in seconds. Enter your data, pick a format, and download the barcode as a PNG image or copy it straight to your clipboard.</p>
  </div>

  <div class="bcg-tool">
    <div class="bcg-controls">
      <div class="bcg-field bcg-field-wide">
        <label for="bcgInput">Data / Text</label>
        <input type="text" id="bcgInput" placeholder="Enter text or numbers..." value="ZOVO-2026">
      </div>
      <div class="bcg-field">
        <label for="bcgType">Barcode Type</label>
        <select id="bcgType" onchange="bcgUpdateHint()">
          <option value="CODE128">Code 128</option>
          <option value="CODE39">Code 39</option>
          <option value="EAN13">EAN-13</option>
          <option value="UPC">UPC-A</option>
          <option value="QR">QR Code</option>
        </select>
      </div>
    </div>
    <div id="bcgHint" class="bcg-hint">Code 128: Supports all 128 ASCII characters. Ideal for shipping labels, packaging, and inventory.</div>
    <div class="bcg-btn-row" style="margin-top: 16px;">
      <button class="bcg-btn bcg-btn-generate" onclick="bcgGenerate()">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" style="flex-shrink:0"><rect x="1" y="2" width="2" height="12" rx="0.5" fill="currentColor"/><rect x="4.5" y="2" width="1.5" height="12" rx="0.3" fill="currentColor"/><rect x="7" y="2" width="3" height="12" rx="0.5" fill="currentColor"/><rect x="11.5" y="2" width="1" height="12" rx="0.3" fill="currentColor"/><rect x="13.5" y="2" width="1.5" height="12" rx="0.3" fill="currentColor"/></svg>
        Generate
      </button>
      <button class="bcg-btn bcg-btn-download" id="bcgDownload" onclick="bcgDownloadPng()">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" style="flex-shrink:0"><path d="M8 2v8m0 0l-3-3m3 3l3-3M3 13h10" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
        Download PNG
      </button>
      <button class="bcg-btn bcg-btn-copy" id="bcgCopy" onclick="bcgCopyToClipboard()">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" style="flex-shrink:0"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
        <span id="bcgCopyText">Copy to Clipboard</span>
      </button>
    </div>
    <div class="bcg-output-wrap">
      <div class="bcg-output" id="bcgOutput">
        <div class="bcg-placeholder" id="bcgPlaceholder">Your barcode will appear here. Click Generate to start.</div>
        <canvas id="bcgCanvas" style="display:none;"></canvas>
        <svg id="bcgSvg" style="display:none;"></svg>
      </div>
    </div>
    <div class="bcg-meta">
      <span id="bcgStats"></span>
      <span>Zovo Tools</span>
    </div>
  </div>

  <div class="bcg-cta">
    <h3>Zovo -- Tools That Just Work</h3>
    <p>Free, fast, and built for real workflows. Explore more developer and design tools at Zovo.</p>
    <a href="https://zovo.one/tools">Browse All Tools</a>
  </div>

  <div class="bcg-seo">
    <h2>What Is a Barcode Generator?</h2>
    <p>A barcode generator converts text, numbers, or URLs into a scannable barcode image. Barcodes are used across retail, logistics, healthcare, and manufacturing to track products, manage inventory, and speed up point-of-sale transactions. Instead of buying desktop software or signing up for a subscription, you can use this free online barcode generator to create barcodes right in your browser.</p>

    <h3>Supported Barcode Types</h3>
    <p>This tool supports five of the most widely used barcode formats:</p>
    <ul>
      <li><strong>Code 128</strong> -- A high-density linear barcode that encodes all 128 ASCII characters. Commonly used for shipping labels, packaging, and inventory management systems. It is the most versatile 1D barcode format available.</li>
      <li><strong>Code 39</strong> -- An older alphanumeric barcode format that supports uppercase letters, digits, and a handful of special characters. Still widely used in automotive, defense, and government applications.</li>
      <li><strong>EAN-13</strong> -- The 13-digit European Article Number standard used on consumer products worldwide. If you sell goods in retail stores outside North America, you will likely need EAN-13 barcodes.</li>
      <li><strong>UPC-A</strong> -- The 12-digit Universal Product Code found on nearly every product sold in the United States and Canada. Retailers require UPC-A barcodes for point-of-sale scanning.</li>
      <li><strong>QR Code</strong> -- A two-dimensional matrix barcode that can store URLs, contact information, plain text, and more. QR codes are popular for marketing materials, event tickets, restaurant menus, and mobile payments.</li>
    </ul>

    <h3>Common Use Cases</h3>
    <p>Small businesses use barcode generators to print product labels, asset tags, and warehouse bin identifiers. Event organizers create QR codes for ticket validation. Developers generate test barcodes while building scanning features into mobile apps. Marketers embed QR codes on flyers, business cards, and product packaging to link customers directly to landing pages or special offers.</p>

    <h3>How to Use This Tool</h3>
    <p>Type or paste your data into the input field, select a barcode type from the dropdown, and click Generate. The barcode renders instantly in your browser with no server round-trip. Download the result as a high-resolution PNG file, or copy it to your clipboard for pasting into design tools like Figma, Canva, or Google Docs. All processing happens locally, so your data never leaves your device.</p>

    <p>Need more tools? <a href="https://zovo.one/tools" style="color: var(--zovo-primary); text-decoration: none; font-weight: 500;">Explore the full Zovo toolkit</a> for JSON formatting, color picking, diff checking, and more.</p>
  </div>

  <div class="bcg-faq">
    <h2>Frequently Asked Questions</h2>

    <div class="bcg-faq-item" itemscope itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is this barcode generator really free?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes, completely free with no sign-up, no watermark, and no usage limits. The barcode is generated entirely in your browser using open-source libraries, so there is no server involved and no data leaves your machine.</p>
      </div>
    </div>

    <div class="bcg-faq-item" itemscope itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between a 1D barcode and a QR code?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">One-dimensional (1D) barcodes like Code 128, Code 39, EAN-13, and UPC-A encode data in a series of parallel lines with varying widths. They store small amounts of data, typically numbers or short text. QR codes are two-dimensional and store data in a grid of black and white squares, allowing them to hold much more information, including full URLs, contact cards, and paragraphs of text.</p>
      </div>
    </div>

    <div class="bcg-faq-item" itemscope itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I use the barcodes for commercial products?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The barcode images you generate here are yours to use however you like, including on commercial products. However, if you need official UPC or EAN codes for retail distribution, you must first purchase a GS1 company prefix from GS1 (gs1.org) to get unique product numbers. This tool encodes whatever numbers you provide but does not assign or register barcode numbers.</p>
      </div>
    </div>

    <div class="bcg-faq-item" itemscope itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why does my EAN-13 or UPC-A barcode fail to generate?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">EAN-13 requires exactly 12 or 13 digits (the 13th is a check digit that the tool can calculate automatically). UPC-A requires exactly 11 or 12 digits. If you enter letters or the wrong number of digits, the generator will show an error message explaining what is expected. Double-check your input and try again.</p>
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

  var HINTS = {
    CODE128: "Code 128: Supports all 128 ASCII characters. Ideal for shipping labels, packaging, and inventory.",
    CODE39: "Code 39: Uppercase letters, digits, and symbols (-.$/+% space). Used in automotive and government.",
    EAN13: "EAN-13: Enter 12 or 13 digits. The check digit is calculated automatically if you provide 12.",
    UPC: "UPC-A: Enter 11 or 12 digits. The check digit is calculated automatically if you provide 11.",
    QR: "QR Code: Supports any text, URL, or data up to ~4,296 characters."
  };

  window.bcgUpdateHint = function() {
    var type = document.getElementById("bcgType").value;
    document.getElementById("bcgHint").textContent = HINTS[type] || "";
  };

  function showError(msg) {
    var output = document.getElementById("bcgOutput");
    var canvas = document.getElementById("bcgCanvas");
    var svg = document.getElementById("bcgSvg");
    var placeholder = document.getElementById("bcgPlaceholder");

    canvas.style.display = "none";
    svg.style.display = "none";
    placeholder.style.display = "none";

    var existing = output.querySelector(".bcg-error");
    if (existing) existing.remove();

    var errDiv = document.createElement("div");
    errDiv.className = "bcg-error";
    errDiv.textContent = msg;
    output.appendChild(errDiv);

    document.getElementById("bcgStats").textContent = "";
  }

  function clearError() {
    var output = document.getElementById("bcgOutput");
    var existing = output.querySelector(".bcg-error");
    if (existing) existing.remove();
  }

  function renderToExportCanvas(callback) {
    var type = document.getElementById("bcgType").value;
    var canvas = document.getElementById("bcgCanvas");

    if (type === "QR") {
      callback(canvas);
    } else {
      var svg = document.getElementById("bcgSvg");
      var svgData = new XMLSerializer().serializeToString(svg);
      var svgBlob = new Blob([svgData], { type: "image/svg+xml;charset=utf-8" });
      var url = URL.createObjectURL(svgBlob);

      var img = new Image();
      img.onload = function() {
        var scale = 2;
        var exportCanvas = document.createElement("canvas");
        exportCanvas.width = img.naturalWidth * scale;
        exportCanvas.height = img.naturalHeight * scale;

        var ctx = exportCanvas.getContext("2d");
        ctx.fillStyle = "#FFFFFF";
        ctx.fillRect(0, 0, exportCanvas.width, exportCanvas.height);
        ctx.drawImage(img, 0, 0, exportCanvas.width, exportCanvas.height);
        URL.revokeObjectURL(url);
        callback(exportCanvas);
      };
      img.onerror = function() {
        URL.revokeObjectURL(url);
        showError("Failed to render barcode for export.");
      };
      img.src = url;
    }
  }

  window.bcgGenerate = function() {
    var input = document.getElementById("bcgInput").value.trim();
    var type = document.getElementById("bcgType").value;
    var canvas = document.getElementById("bcgCanvas");
    var svg = document.getElementById("bcgSvg");
    var placeholder = document.getElementById("bcgPlaceholder");

    clearError();

    if (!input) {
      showError("Please enter some text or data to encode.");
      return;
    }

    placeholder.style.display = "none";

    if (type === "QR") {
      svg.style.display = "none";
      canvas.style.display = "block";

      QRCode.toCanvas(canvas, input, {
        width: 280,
        margin: 2,
        color: {
          dark: "#2D3436",
          light: "#FFFFFF"
        },
        errorCorrectionLevel: "M"
      }, function(error) {
        if (error) {
          showError("QR Code error: " + error.message);
          canvas.style.display = "none";
          return;
        }
        document.getElementById("bcgStats").textContent = "QR Code \u00B7 " + input.length + " characters";
      });

    } else {
      canvas.style.display = "none";
      svg.style.display = "block";

      try {
        var valid = true;
        JsBarcode(svg, input, {
          format: type,
          lineColor: "#2D3436",
          background: "#FFFFFF",
          width: 2,
          height: 80,
          displayValue: true,
          font: "Inter, sans-serif",
          fontSize: 14,
          fontOptions: "500",
          textMargin: 6,
          margin: 10,
          valid: function(isValid) {
            if (!isValid) {
              valid = false;
              svg.style.display = "none";
              var typeLabel = type === "CODE128" ? "Code 128" : type === "CODE39" ? "Code 39" : type === "EAN13" ? "EAN-13" : "UPC-A";
              if (type === "EAN13") {
                showError("Invalid input for " + typeLabel + ". Enter exactly 12 or 13 digits.");
              } else if (type === "UPC") {
                showError("Invalid input for " + typeLabel + ". Enter exactly 11 or 12 digits.");
              } else if (type === "CODE39") {
                showError("Invalid input for " + typeLabel + ". Use uppercase letters, digits, and - . $ / + % space only.");
              } else {
                showError("Invalid input for " + typeLabel + ". Check your data and try again.");
              }
            }
          }
        });

        if (valid) {
          var typeLabel = type === "CODE128" ? "Code 128" : type === "CODE39" ? "Code 39" : type === "EAN13" ? "EAN-13" : "UPC-A";
          document.getElementById("bcgStats").textContent = typeLabel + " \u00B7 " + input.length + " characters";
        }
      } catch (e) {
        showError("Generation failed: " + e.message);
        svg.style.display = "none";
      }
    }

    // Reset copy button state
    var copyBtn = document.getElementById("bcgCopy");
    copyBtn.classList.remove("copied");
    document.getElementById("bcgCopyText").textContent = "Copy to Clipboard";
  };

  window.bcgDownloadPng = function() {
    var canvas = document.getElementById("bcgCanvas");
    var svg = document.getElementById("bcgSvg");
    var type = document.getElementById("bcgType").value;

    if (type === "QR" && canvas.style.display === "none") {
      showError("Generate a barcode first, then download.");
      return;
    }
    if (type !== "QR" && svg.style.display === "none") {
      showError("Generate a barcode first, then download.");
      return;
    }

    renderToExportCanvas(function(exportCanvas) {
      exportCanvas.toBlob(function(blob) {
        if (!blob) return;
        var url = URL.createObjectURL(blob);
        var a = document.createElement("a");
        var input = document.getElementById("bcgInput").value.trim();
        var safeName = input.replace(/[^a-zA-Z0-9\-_]/g, "_").substring(0, 30) || "barcode";
        a.href = url;
        a.download = safeName + "-barcode.png";
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        URL.revokeObjectURL(url);
      }, "image/png");
    });
  };

  window.bcgCopyToClipboard = function() {
    var canvas = document.getElementById("bcgCanvas");
    var svg = document.getElementById("bcgSvg");
    var type = document.getElementById("bcgType").value;

    if (type === "QR" && canvas.style.display === "none") {
      showError("Generate a barcode first, then copy.");
      return;
    }
    if (type !== "QR" && svg.style.display === "none") {
      showError("Generate a barcode first, then copy.");
      return;
    }

    renderToExportCanvas(function(exportCanvas) {
      exportCanvas.toBlob(function(blob) {
        if (!blob) return;
        try {
          var item = new ClipboardItem({ "image/png": blob });
          navigator.clipboard.write([item]).then(function() {
            var btn = document.getElementById("bcgCopy");
            var label = document.getElementById("bcgCopyText");
            btn.classList.add("copied");
            label.textContent = "Copied!";
            setTimeout(function() {
              btn.classList.remove("copied");
              label.textContent = "Copy to Clipboard";
            }, 2000);
          }).catch(function() {
            showError("Clipboard access denied. Try downloading the image instead.");
          });
        } catch (e) {
          showError("Your browser does not support copying images to the clipboard. Try downloading instead.");
        }
      }, "image/png");
    });
  };

  document.getElementById("bcgInput").addEventListener("keydown", function(e) {
    if (e.key === "Enter") {
      e.preventDefault();
      bcgGenerate();
    }
  });

  // Generate initial barcode on load
  window.bcgGenerate();
})();
</script>
