---
layout: page
title: "Free Color Palette Generator — Create, Extract & Export Palettes | Zovo"
description: "Generate beautiful color palettes with complementary, analogous, triadic, and split-complementary schemes. Extract palettes from images, export as CSS, SCSS, Tailwind, or JSON."
permalink: /tools/color-palette-generator/
keywords: "color palette generator, color scheme generator, color palette from image, css color palette, tailwind colors, complementary colors, color harmony, palette maker"
date: 2026-03-19
categories: [tools]
tags: [color, palette, design, css, tailwind, generator, harmony]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root {
  --cpg-bg: #0a0a0f;
  --cpg-surface: #12121a;
  --cpg-surface2: #1a1a28;
  --cpg-border: #1e1e2e;
  --cpg-border-hover: #2e2e44;
  --cpg-primary: #6C5CE7;
  --cpg-primary-dark: #5A4BD1;
  --cpg-primary-light: #8B7CF7;
  --cpg-secondary: #00ff88;
  --cpg-secondary-dark: #00cc6e;
  --cpg-text: #e0e0e0;
  --cpg-text-muted: #8888aa;
  --cpg-text-dim: #555570;
  --cpg-error: #ff4757;
  --cpg-success: #00ff88;
  --cpg-warning: #ffa502;
  --cpg-radius: 10px;
  --cpg-radius-sm: 6px;
  --cpg-font: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --cpg-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
}

.cpg-wrap {
  font-family: var(--cpg-font);
  color: var(--cpg-text);
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 16px;
  line-height: 1.6;
}
.cpg-wrap * { box-sizing: border-box; }
.cpg-wrap a { color: var(--cpg-primary-light); text-decoration: none; }
.cpg-wrap a:hover { color: var(--cpg-primary); }

/* Hero */
.cpg-hero { text-align: center; padding: 40px 0 28px; }
.cpg-hero h1 { font-size: 2.1rem; font-weight: 700; color: var(--cpg-text); margin: 0 0 16px; line-height: 1.25; }
.cpg-hero h1 span { color: var(--cpg-primary); }
.cpg-intro { font-size: 1.02rem; color: var(--cpg-text-muted); max-width: 720px; margin: 0 auto; line-height: 1.7; }

/* Panel */
.cpg-panel {
  background: var(--cpg-surface);
  border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius);
  padding: 24px;
  margin-bottom: 20px;
}

/* Buttons */
.cpg-btn {
  display: inline-flex; align-items: center; justify-content: center; gap: 6px;
  padding: 9px 16px; border: none; border-radius: var(--cpg-radius-sm);
  font-family: var(--cpg-font); font-size: 0.85rem; font-weight: 600;
  cursor: pointer; transition: all 0.15s; white-space: nowrap;
}
.cpg-btn-primary { background: var(--cpg-primary); color: #fff; }
.cpg-btn-primary:hover { background: var(--cpg-primary-dark); }
.cpg-btn-secondary { background: var(--cpg-surface2); color: var(--cpg-text); border: 1px solid var(--cpg-border); }
.cpg-btn-secondary:hover { border-color: var(--cpg-border-hover); background: var(--cpg-border); }
.cpg-btn-sm { padding: 5px 10px; font-size: 0.78rem; }

/* Color Input Row */
.cpg-input-row {
  display: flex; gap: 12px; align-items: center; flex-wrap: wrap; margin-bottom: 20px;
}
.cpg-hex-input {
  font-family: var(--cpg-mono); font-size: 1rem; padding: 10px 14px;
  background: var(--cpg-bg); border: 1px solid var(--cpg-border); border-radius: var(--cpg-radius-sm);
  color: var(--cpg-text); width: 140px; outline: none;
}
.cpg-hex-input:focus { border-color: var(--cpg-primary); }
.cpg-native-picker {
  width: 48px; height: 44px; border: 2px solid var(--cpg-border); border-radius: var(--cpg-radius-sm);
  background: none; cursor: pointer; padding: 2px;
}
.cpg-native-picker::-webkit-color-swatch-wrapper { padding: 0; }
.cpg-native-picker::-webkit-color-swatch { border: none; border-radius: 4px; }

/* HSL Wheel Canvas */
.cpg-wheel-wrap {
  position: relative; width: 240px; height: 240px; margin: 0 auto 20px; cursor: crosshair;
}
.cpg-wheel-wrap canvas { border-radius: 50%; }
.cpg-wheel-marker {
  position: absolute; width: 16px; height: 16px; border: 2px solid #fff;
  border-radius: 50%; box-shadow: 0 0 4px rgba(0,0,0,0.5); pointer-events: none;
  transform: translate(-50%, -50%); z-index: 2;
}

/* Harmony Tabs */
.cpg-tabs {
  display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 20px;
}
.cpg-tab {
  padding: 7px 14px; font-size: 0.8rem; font-weight: 600; font-family: var(--cpg-font);
  background: var(--cpg-surface2); color: var(--cpg-text-muted); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius-sm); cursor: pointer; transition: all 0.15s;
}
.cpg-tab:hover { border-color: var(--cpg-border-hover); color: var(--cpg-text); }
.cpg-tab.active { background: var(--cpg-primary); color: #fff; border-color: var(--cpg-primary); }

/* Global Sliders */
.cpg-slider-row {
  display: flex; gap: 16px; align-items: center; margin-bottom: 16px; flex-wrap: wrap;
}
.cpg-slider-group { flex: 1; min-width: 200px; }
.cpg-slider-label {
  font-size: 0.78rem; font-weight: 600; color: var(--cpg-text-muted);
  text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 6px;
  display: flex; justify-content: space-between;
}
.cpg-slider {
  width: 100%; height: 6px; border-radius: 3px; -webkit-appearance: none;
  appearance: none; background: var(--cpg-border); outline: none; cursor: pointer;
}
.cpg-slider::-webkit-slider-thumb {
  -webkit-appearance: none; width: 18px; height: 18px; border-radius: 50%;
  background: var(--cpg-primary); cursor: pointer; border: 2px solid var(--cpg-surface);
  box-shadow: 0 2px 6px rgba(0,0,0,0.3);
}
.cpg-slider::-moz-range-thumb {
  width: 18px; height: 18px; border-radius: 50%; background: var(--cpg-primary);
  cursor: pointer; border: 2px solid var(--cpg-surface);
}

/* Palette Display */
.cpg-palette {
  display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 20px;
}
.cpg-swatch {
  flex: 1; min-width: 100px; background: var(--cpg-surface2); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius); overflow: hidden; transition: transform 0.15s;
  position: relative;
}
.cpg-swatch:hover { transform: translateY(-2px); }
.cpg-swatch-color {
  height: 100px; cursor: pointer; position: relative; transition: background 0.2s;
}
.cpg-swatch-lock {
  position: absolute; top: 6px; right: 6px; width: 28px; height: 28px;
  background: rgba(0,0,0,0.45); border: none; border-radius: 50%; cursor: pointer;
  display: flex; align-items: center; justify-content: center; color: #fff;
  font-size: 0.75rem; transition: background 0.15s; z-index: 2;
}
.cpg-swatch-lock:hover { background: rgba(0,0,0,0.7); }
.cpg-swatch-lock.locked { background: var(--cpg-primary); }
.cpg-swatch-info {
  padding: 10px; font-family: var(--cpg-mono); font-size: 0.75rem;
  color: var(--cpg-text-muted); line-height: 1.6;
}
.cpg-swatch-info .cpg-hex-val {
  color: var(--cpg-text); font-weight: 500; font-size: 0.82rem; cursor: pointer;
}
.cpg-swatch-info .cpg-hex-val:hover { color: var(--cpg-secondary); }
.cpg-copied-toast {
  position: absolute; top: 50%; left: 50%; transform: translate(-50%,-50%);
  background: var(--cpg-primary); color: #fff; padding: 4px 12px; border-radius: 4px;
  font-size: 0.75rem; font-family: var(--cpg-font); font-weight: 600;
  pointer-events: none; opacity: 0; transition: opacity 0.2s;
}
.cpg-copied-toast.show { opacity: 1; }

/* Action Bar */
.cpg-actions {
  display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px;
}

/* Image Upload */
.cpg-upload {
  border: 2px dashed var(--cpg-border); border-radius: var(--cpg-radius);
  padding: 36px 20px; text-align: center; cursor: pointer;
  transition: border-color 0.2s; margin-bottom: 20px; position: relative;
}
.cpg-upload:hover { border-color: var(--cpg-primary); }
.cpg-upload-text { color: var(--cpg-text-muted); font-size: 0.9rem; }
.cpg-upload input[type="file"] {
  position: absolute; inset: 0; opacity: 0; cursor: pointer;
}
.cpg-img-preview {
  display: none; margin-bottom: 16px; border-radius: var(--cpg-radius);
  overflow: hidden; border: 1px solid var(--cpg-border);
}
.cpg-img-preview canvas { display: block; max-width: 100%; height: auto; }
.cpg-img-palette { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 16px; }
.cpg-img-swatch {
  width: 60px; height: 60px; border-radius: var(--cpg-radius-sm);
  border: 2px solid var(--cpg-border); cursor: pointer; transition: transform 0.15s;
  position: relative;
}
.cpg-img-swatch:hover { transform: scale(1.08); border-color: var(--cpg-primary); }

/* Export Modal */
.cpg-export-overlay {
  display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.7);
  z-index: 1000; align-items: center; justify-content: center;
}
.cpg-export-overlay.show { display: flex; }
.cpg-export-modal {
  background: var(--cpg-surface); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius); padding: 28px; width: 90%; max-width: 600px;
  max-height: 80vh; overflow-y: auto;
}
.cpg-export-modal h3 {
  font-size: 1.1rem; font-weight: 700; margin: 0 0 16px; color: var(--cpg-text);
}
.cpg-export-tabs {
  display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 16px;
}
.cpg-export-tab {
  padding: 6px 12px; font-size: 0.78rem; font-weight: 600; font-family: var(--cpg-font);
  background: var(--cpg-surface2); color: var(--cpg-text-muted); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius-sm); cursor: pointer; transition: all 0.15s;
}
.cpg-export-tab.active { background: var(--cpg-primary); color: #fff; border-color: var(--cpg-primary); }
.cpg-export-code {
  font-family: var(--cpg-mono); font-size: 0.82rem; background: var(--cpg-bg);
  border: 1px solid var(--cpg-border); border-radius: var(--cpg-radius-sm);
  padding: 16px; color: var(--cpg-text); white-space: pre-wrap; word-break: break-all;
  max-height: 300px; overflow-y: auto; line-height: 1.7; margin-bottom: 12px;
}
.cpg-export-close {
  position: absolute; top: 12px; right: 12px;
}

/* Accessibility Panel */
.cpg-a11y {
  background: var(--cpg-surface); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius); padding: 20px; margin-bottom: 20px;
}
.cpg-a11y h3 {
  font-size: 0.95rem; font-weight: 700; margin: 0 0 14px; color: var(--cpg-text);
}
.cpg-a11y-grid {
  display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 10px;
}
.cpg-a11y-pair {
  background: var(--cpg-surface2); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius-sm); padding: 10px 12px; font-size: 0.78rem;
}
.cpg-a11y-colors {
  display: flex; gap: 6px; align-items: center; margin-bottom: 6px;
}
.cpg-a11y-dot {
  width: 18px; height: 18px; border-radius: 50%; border: 1px solid var(--cpg-border);
  flex-shrink: 0;
}
.cpg-a11y-ratio { font-family: var(--cpg-mono); font-weight: 600; color: var(--cpg-text); }
.cpg-a11y-badges { display: flex; gap: 4px; margin-top: 4px; }
.cpg-badge {
  font-size: 0.68rem; font-weight: 700; padding: 2px 6px; border-radius: 3px;
  font-family: var(--cpg-font);
}
.cpg-badge-pass { background: rgba(0,255,136,0.15); color: var(--cpg-success); }
.cpg-badge-fail { background: rgba(255,71,87,0.12); color: var(--cpg-error); }

/* History */
.cpg-history {
  background: var(--cpg-surface); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius); padding: 16px 20px; margin-bottom: 20px;
}
.cpg-history-header {
  display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px;
}
.cpg-history-title { font-size: 0.88rem; font-weight: 600; color: var(--cpg-text); }
.cpg-history-list { display: flex; flex-direction: column; gap: 8px; }
.cpg-history-item {
  display: flex; gap: 6px; align-items: center; padding: 8px 12px;
  background: var(--cpg-surface2); border: 1px solid var(--cpg-border);
  border-radius: var(--cpg-radius-sm); cursor: pointer; transition: border-color 0.15s;
}
.cpg-history-item:hover { border-color: var(--cpg-primary); }
.cpg-history-dot {
  width: 22px; height: 22px; border-radius: 4px; flex-shrink: 0;
  border: 1px solid var(--cpg-border);
}
.cpg-history-label {
  font-family: var(--cpg-mono); font-size: 0.75rem; color: var(--cpg-text-muted);
  overflow: hidden; text-overflow: ellipsis; white-space: nowrap;
}

/* Content Sections */
.cpg-content { margin-top: 48px; }
.cpg-content h2 {
  font-size: 1.4rem; font-weight: 700; color: var(--cpg-text); margin: 40px 0 16px;
  padding-top: 20px; border-top: 1px solid var(--cpg-border);
}
.cpg-content h2:first-child { border-top: none; padding-top: 0; margin-top: 0; }
.cpg-content p {
  color: var(--cpg-text-muted); font-size: 0.95rem; line-height: 1.75; margin: 0 0 16px;
}
.cpg-content ul {
  color: var(--cpg-text-muted); font-size: 0.95rem; line-height: 1.75;
  padding-left: 20px; margin: 0 0 16px;
}
.cpg-content li { margin-bottom: 6px; }

/* FAQ */
.cpg-faq { margin-top: 48px; }
.cpg-faq h2 { font-size: 1.4rem; font-weight: 700; margin: 0 0 24px; color: var(--cpg-text); }
.cpg-faq-item {
  border: 1px solid var(--cpg-border); border-radius: var(--cpg-radius);
  padding: 18px 22px; margin-bottom: 12px; background: var(--cpg-surface);
}
.cpg-faq-item h3 { font-size: 1rem; font-weight: 600; margin: 0 0 10px; color: var(--cpg-text); }
.cpg-faq-item p { margin: 0; font-size: 0.93rem; color: var(--cpg-text-muted); line-height: 1.7; }

/* Responsive */
@media (max-width: 768px) {
  .cpg-hero h1 { font-size: 1.5rem; }
  .cpg-palette { flex-direction: column; }
  .cpg-swatch { min-width: 0; }
  .cpg-swatch-color { height: 70px; }
  .cpg-wheel-wrap { width: 200px; height: 200px; }
  .cpg-a11y-grid { grid-template-columns: 1fr; }
  .cpg-slider-row { flex-direction: column; }
}
@media (max-width: 480px) {
  .cpg-tabs { gap: 4px; }
  .cpg-tab { padding: 5px 10px; font-size: 0.72rem; }
  .cpg-actions { flex-direction: column; }
}
</style>

<div class="cpg-wrap" id="cpgApp">

  <div class="cpg-hero">
    <h1><span>Color Palette</span> Generator</h1>
    <p class="cpg-intro">Pick a base color, select a harmony mode, and generate a complete palette. Extract colors from images, check accessibility contrast ratios, and export to CSS, SCSS, Tailwind, or JSON. Everything runs locally in your browser.</p>
  </div>

  <p style="color:var(--cpg-text-dim);font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <!-- Base Color Input -->
  <div class="cpg-panel">
    <div class="cpg-input-row">
      <input type="color" class="cpg-native-picker" id="cpgPicker" value="#6C5CE7">
      <input type="text" class="cpg-hex-input" id="cpgHexInput" value="#6C5CE7" maxlength="7" spellcheck="false">
      <button class="cpg-btn cpg-btn-primary" onclick="CPG.randomBase()">Random</button>
    </div>

    <!-- HSL Wheel -->
    <div class="cpg-wheel-wrap" id="cpgWheelWrap">
      <canvas id="cpgWheel" width="240" height="240"></canvas>
      <div class="cpg-wheel-marker" id="cpgWheelMarker"></div>
    </div>

    <!-- Harmony Mode Tabs -->
    <div class="cpg-tabs" id="cpgTabs">
      <button class="cpg-tab active" data-mode="complementary">Complementary</button>
      <button class="cpg-tab" data-mode="analogous">Analogous</button>
      <button class="cpg-tab" data-mode="triadic">Triadic</button>
      <button class="cpg-tab" data-mode="split">Split-Comp</button>
      <button class="cpg-tab" data-mode="tetradic">Tetradic</button>
      <button class="cpg-tab" data-mode="monochromatic">Monochromatic</button>
    </div>

    <!-- Global Saturation / Lightness -->
    <div class="cpg-slider-row">
      <div class="cpg-slider-group">
        <div class="cpg-slider-label"><span>Saturation</span><span id="cpgSatVal">0</span></div>
        <input type="range" class="cpg-slider" id="cpgSatSlider" min="-50" max="50" value="0">
      </div>
      <div class="cpg-slider-group">
        <div class="cpg-slider-label"><span>Lightness</span><span id="cpgLitVal">0</span></div>
        <input type="range" class="cpg-slider" id="cpgLitSlider" min="-50" max="50" value="0">
      </div>
    </div>
  </div>

  <!-- Palette Display -->
  <div class="cpg-palette" id="cpgPalette"></div>

  <!-- Actions -->
  <div class="cpg-actions">
    <button class="cpg-btn cpg-btn-primary" onclick="CPG.generate()">Regenerate</button>
    <button class="cpg-btn cpg-btn-secondary" onclick="CPG.randomBase()">Random Palette</button>
    <button class="cpg-btn cpg-btn-secondary" onclick="CPG.showExport()">Export</button>
  </div>

  <!-- Accessibility Checker -->
  <div class="cpg-a11y" id="cpgA11y">
    <h3>Contrast Checker (WCAG)</h3>
    <div class="cpg-a11y-grid" id="cpgA11yGrid"></div>
  </div>

  <!-- Image Extraction Section -->
  <div class="cpg-panel">
    <h3 style="font-size:1rem;font-weight:700;margin:0 0 14px;color:var(--cpg-text);">Extract Palette from Image</h3>
    <div class="cpg-upload" id="cpgUpload">
      <p class="cpg-upload-text">Drop an image here or click to browse (JPG, PNG, WebP)</p>
      <input type="file" id="cpgFileInput" accept="image/*">
    </div>
    <div class="cpg-img-preview" id="cpgImgPreview">
      <canvas id="cpgImgCanvas"></canvas>
    </div>
    <div class="cpg-img-palette" id="cpgImgPalette"></div>
  </div>

  <!-- Palette History -->
  <div class="cpg-history" id="cpgHistory" style="display:none;">
    <div class="cpg-history-header">
      <span class="cpg-history-title">Palette History</span>
      <button class="cpg-btn cpg-btn-sm cpg-btn-secondary" onclick="CPG.clearHistory()">Clear</button>
    </div>
    <div class="cpg-history-list" id="cpgHistoryList"></div>
  </div>

  <!-- Export Modal -->
  <div class="cpg-export-overlay" id="cpgExportOverlay" onclick="CPG.closeExport(event)">
    <div class="cpg-export-modal" onclick="event.stopPropagation()">
      <h3>Export Palette</h3>
      <div class="cpg-export-tabs" id="cpgExportTabs">
        <button class="cpg-export-tab active" data-fmt="css">CSS</button>
        <button class="cpg-export-tab" data-fmt="scss">SCSS</button>
        <button class="cpg-export-tab" data-fmt="tailwind">Tailwind</button>
        <button class="cpg-export-tab" data-fmt="json">JSON</button>
        <button class="cpg-export-tab" data-fmt="text">Plain Text</button>
      </div>
      <div class="cpg-export-code" id="cpgExportCode"></div>
      <button class="cpg-btn cpg-btn-primary" onclick="CPG.copyExport()">Copy to Clipboard</button>
    </div>
  </div>

  <!-- Content Sections -->
  <div class="cpg-content">

    <h2>What Is a Color Palette</h2>
    <p>A color palette is a defined set of colors used together across a design system, website, or application. Rather than selecting colors ad hoc, designers and developers establish a palette upfront to ensure visual consistency. A typical web palette includes a primary color, one or two accent colors, a range of neutrals, and semantic colors for states like success, warning, and error.</p>
    <p>The relationship between the colors in a palette matters more than any single color on its own. Colors that share a logical connection through hue, saturation, or lightness tend to look cohesive when placed side by side. This is where color harmony theory comes in. A palette built on harmonic relationships feels intentional, while a random assortment of colors often looks disjointed regardless of how attractive each color is individually.</p>
    <p>Digital palettes are typically expressed as hex codes, RGB values, or HSL values. Each format serves a different purpose. Hex is the standard in CSS. RGB maps to how screens physically render color. HSL describes color in terms humans can reason about: hue is the color wheel position, saturation is the intensity, and lightness is how bright or dark the color appears.</p>

    <h2>Understanding Color Harmony</h2>
    <p>Color harmony refers to combinations of colors that are visually balanced according to their positions on the color wheel. The six harmony modes in this tool each produce a different character.</p>
    <ul>
      <li>Complementary pairs sit opposite each other on the wheel (like blue and orange). They create strong contrast and draw attention, making them useful for call-to-action elements against a background.</li>
      <li>Analogous colors are neighbors on the wheel (like blue, blue-green, and green). They produce smooth, low-contrast palettes that feel calm and unified.</li>
      <li>Triadic schemes use three colors spaced 120 degrees apart. They offer variety while maintaining balance, and work well when you need a palette with more range than complementary but more structure than random selection.</li>
      <li>Split-complementary takes a base color and pairs it with the two colors adjacent to its complement. This softens the contrast of a pure complementary scheme while keeping visual tension.</li>
      <li>Tetradic (double-complementary) uses four colors in two complementary pairs. It gives the widest range but requires careful handling of saturation and lightness to avoid visual chaos.</li>
      <li>Monochromatic schemes use a single hue with variations in saturation and lightness. They are the safest choice when you need a palette that cannot clash.</li>
    </ul>

    <h2>How to Choose Colors for Web Design</h2>
    <p>Start with a single brand color or a color that reflects the tone of the project. A SaaS product might anchor on a professional blue. A food brand might start with a warm red or orange. Use that base color to generate a harmonic palette, then adjust saturation and lightness to create hierarchy. Primary actions get the most saturated color. Secondary elements use muted or lighter variants. Backgrounds and surfaces use near-neutral tones.</p>
    <p>A practical web palette needs more than just the accent colors. Plan for at least four layers: background, surface (cards and panels), text, and interactive elements. Each layer should have enough contrast against its neighbors to remain readable. This tool's built-in contrast checker helps verify those relationships against WCAG standards before you commit to a palette.</p>
    <p>Test your palette at scale before finalizing. A color that looks good in a small swatch can overwhelm a full-page layout. Apply the palette to actual UI components, including buttons, form fields, navigation, and data tables, to see how it holds up in context.</p>

    <h2>Accessibility and Color Contrast</h2>
    <p>The Web Content Accessibility Guidelines (WCAG) define minimum contrast ratios between text and background colors. Normal text requires a ratio of at least 4.5:1 for AA compliance and 7:1 for AAA. Large text (18px bold or 24px regular) needs 3:1 for AA and 4.5:1 for AAA. These thresholds exist because low-contrast text is difficult or impossible to read for people with low vision or color vision deficiencies.</p>
    <p>Contrast ratio is calculated using the relative luminance of two colors. The formula compares the lighter and darker values on a scale from 0 (black) to 1 (white). The contrast checker in this tool runs that calculation for every pair of colors in your palette and displays the ratio alongside AA and AAA pass/fail indicators. This lets you identify problem pairs before writing any code.</p>
    <p>Beyond contrast, consider how your palette performs under color blindness simulations. About 8% of men and 0.5% of women have some form of color vision deficiency. Avoid relying on color alone to convey meaning. Pair color indicators with icons, labels, or patterns so that information remains accessible regardless of how a user perceives hue.</p>

    <h2>Exporting Palettes for Development</h2>
    <p>Once you have a palette you are satisfied with, the next step is translating it into code. This tool supports five export formats. CSS custom properties (also known as CSS variables) work in any modern stylesheet. SCSS variables are useful if your build pipeline uses Sass. Tailwind config output gives you a ready-to-paste colors object for your tailwind.config.js file. JSON is a portable format for design tokens that can feed into tools like Style Dictionary or Figma plugins. Plain text is a simple list of hex codes for quick reference.</p>
    <p>Name your colors semantically rather than by their literal hue. A variable called --color-primary is more maintainable than --purple-600 because it decouples the intent from the specific value. If the brand color changes from purple to blue next quarter, you only need to update the value, not every reference. This tool generates names like color-1 through color-5, which you can rename to match your project's naming conventions after export.</p>
  </div>

  <!-- FAQ -->
  <div class="cpg-faq">
    <h2>Frequently Asked Questions</h2>

    <div class="cpg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How many colors should a web design palette have?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Most web design systems use between 5 and 8 core colors. This typically breaks down into 1-2 brand/accent colors, 2-3 neutral shades for backgrounds and text, and 2-3 semantic colors for success, warning, and error states. Each core color usually has a range of lighter and darker variants (sometimes called a color scale), which can bring the total number of individual values to 30 or more in a mature design system. The palette generated by this tool gives you the core harmonic colors, which you can then extend into full scales as needed.</p>
      </div>
    </div>

    <div class="cpg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between complementary and split-complementary color schemes?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A complementary scheme uses two colors that sit directly opposite each other on the color wheel, creating maximum contrast. A split-complementary scheme starts with one base color but instead of using its direct opposite, it uses the two colors adjacent to the opposite. This reduces the visual tension while still providing clear contrast. Split-complementary palettes are often easier to work with in practice because the softer contrast is more forgiving across different UI elements.</p>
      </div>
    </div>

    <div class="cpg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I extract a color palette from a photograph?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Upload any image using the extraction section below the palette generator. The tool samples pixels across the image and clusters them to identify the 5 most dominant colors. This is useful for deriving a palette from photography, artwork, or any visual reference. The extracted colors can then be used as starting points for further refinement with the harmony modes and saturation/lightness sliders.</p>
      </div>
    </div>

    <div class="cpg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What WCAG contrast ratio do I need for accessible text?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">WCAG 2.1 Level AA requires a contrast ratio of at least 4.5:1 for normal-sized text and 3:1 for large text (18px bold or 24px regular). Level AAA, which is a stricter standard, requires 7:1 for normal text and 4.5:1 for large text. The contrast checker in this tool calculates the ratio for every color pair in your palette and shows whether each pair passes AA and AAA thresholds. Most projects aim for at least AA compliance.</p>
      </div>
    </div>

    <div class="cpg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I use the exported Tailwind config?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The Tailwind export generates a JavaScript object that fits inside the colors key of your tailwind.config.js file. Copy the output, open your config, and paste it into theme.extend.colors (to add alongside defaults) or theme.colors (to replace defaults). After saving, you can use the new colors as utility classes like bg-palette-1, text-palette-2, and border-palette-3. Run your build process to regenerate the CSS with the new values.</p>
      </div>
    </div>

    <div class="cpg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my uploaded image sent to a server?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All image processing happens locally in your browser using the HTML Canvas API. The image is drawn onto a canvas element, and pixel data is read directly from that canvas using JavaScript. Nothing is uploaded, transmitted, or stored on any server. The same applies to the palette generation, export, and history features. Everything runs client-side and your data stays on your device.</p>
      </div>
    </div>
  </div>

  <!-- Cross-link to color picker -->
  <div style="margin:2rem 0;padding:1rem 1.25rem;background:var(--cpg-surface);border:1px solid var(--cpg-primary);border-radius:8px;">
    <div style="font-size:0.75rem;text-transform:uppercase;letter-spacing:0.1em;color:var(--cpg-primary);margin-bottom:0.5rem;font-weight:600;">Related Tool</div>
    <a href="/tools/color-picker/" style="color:var(--cpg-text);text-decoration:none;font-size:0.95rem;font-weight:500;">Color Picker from Image -- extract exact hex, RGB, and HSL codes from any photo &rarr;</a>
  </div>

  <!-- Related Tools -->
  <div style="margin-top:2rem;padding:1.5rem;background:var(--cpg-surface);border:1px solid var(--cpg-border);border-radius:12px;">
    <h2 style="color:var(--cpg-primary);font-size:1.3rem;margin:0 0 1rem;">Related Tools</h2>
    <ul style="list-style:none;padding:0;margin:0;">
      <li style="margin-bottom:0.5rem;"><a href="/tools/color-picker/" style="color:var(--cpg-secondary);text-decoration:none;">Color Picker from Image</a> - Extract exact colors from any photo</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/css-gradient-generator/" style="color:var(--cpg-secondary);text-decoration:none;">CSS Gradient Generator</a> - Create linear and radial CSS gradients</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/meta-tag-generator/" style="color:var(--cpg-secondary);text-decoration:none;">Meta Tag Generator</a> - Generate SEO meta tags for your site</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter-pro/" style="color:var(--cpg-secondary);text-decoration:none;">JSON Formatter Pro</a> - Validate, compare, and transform JSON</li>
    </ul>
  </div>

  <!-- Author Box (E-E-A-T) -->
  <div style="margin-top:2rem;padding:1.5rem;background:var(--cpg-surface);border:1px solid var(--cpg-border);border-radius:12px;display:flex;gap:1rem;align-items:center;">
    <div style="width:48px;height:48px;border-radius:50%;background:var(--cpg-primary);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;flex-shrink:0;">ML</div>
    <div>
      <div style="color:var(--cpg-text);font-weight:600;">Michael Lip</div>
      <div style="color:var(--cpg-text-muted);font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:var(--cpg-primary);">Zovo</a>. Building free developer and productivity tools.</div>
    </div>
  </div>

  <footer style="text-align:center;padding:2rem 0;color:var(--cpg-text-dim);font-size:0.85rem;border-top:1px solid var(--cpg-border);margin-top:3rem;">
    <p>Built by <a href="https://zovo.one" style="color:var(--cpg-primary);text-decoration:none;">Michael Lip</a> at <a href="https://zovo.one" style="color:var(--cpg-primary);text-decoration:none;">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var state = {
    baseHSL: [247, 75, 63],
    mode: "complementary",
    palette: [],
    locked: [],
    satAdj: 0,
    litAdj: 0,
    history: [],
    exportFmt: "css",
    MAX_HISTORY: 10
  };

  // --- Color Utilities ---

  function hslToRgb(h, s, l) {
    h = ((h % 360) + 360) % 360;
    s = Math.max(0, Math.min(100, s)) / 100;
    l = Math.max(0, Math.min(100, l)) / 100;
    var c = (1 - Math.abs(2 * l - 1)) * s;
    var x = c * (1 - Math.abs((h / 60) % 2 - 1));
    var m = l - c / 2;
    var r, g, b;
    if (h < 60) { r = c; g = x; b = 0; }
    else if (h < 120) { r = x; g = c; b = 0; }
    else if (h < 180) { r = 0; g = c; b = x; }
    else if (h < 240) { r = 0; g = x; b = c; }
    else if (h < 300) { r = x; g = 0; b = c; }
    else { r = c; g = 0; b = x; }
    return [Math.round((r + m) * 255), Math.round((g + m) * 255), Math.round((b + m) * 255)];
  }

  function rgbToHsl(r, g, b) {
    r /= 255; g /= 255; b /= 255;
    var max = Math.max(r, g, b), min = Math.min(r, g, b);
    var h, s, l = (max + min) / 2;
    if (max === min) { h = 0; s = 0; }
    else {
      var d = max - min;
      s = l > 0.5 ? d / (2 - max - min) : d / (max + min);
      switch (max) {
        case r: h = ((g - b) / d + (g < b ? 6 : 0)) / 6; break;
        case g: h = ((b - r) / d + 2) / 6; break;
        case b: h = ((r - g) / d + 4) / 6; break;
      }
    }
    return [Math.round(h * 360), Math.round(s * 100), Math.round(l * 100)];
  }

  function rgbToHex(r, g, b) {
    return "#" + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1).toUpperCase();
  }

  function hexToRgb(hex) {
    hex = hex.replace(/^#/, "");
    if (hex.length === 3) hex = hex[0]+hex[0]+hex[1]+hex[1]+hex[2]+hex[2];
    var n = parseInt(hex, 16);
    return [(n >> 16) & 255, (n >> 8) & 255, n & 255];
  }

  function clamp(v, lo, hi) { return Math.max(lo, Math.min(hi, v)); }

  // Relative luminance per WCAG
  function luminance(r, g, b) {
    var a = [r, g, b].map(function(v) {
      v /= 255;
      return v <= 0.03928 ? v / 12.92 : Math.pow((v + 0.055) / 1.055, 2.4);
    });
    return 0.2126 * a[0] + 0.7152 * a[1] + 0.0722 * a[2];
  }

  function contrastRatio(rgb1, rgb2) {
    var l1 = luminance(rgb1[0], rgb1[1], rgb1[2]);
    var l2 = luminance(rgb2[0], rgb2[1], rgb2[2]);
    var lighter = Math.max(l1, l2);
    var darker = Math.min(l1, l2);
    return (lighter + 0.05) / (darker + 0.05);
  }

  // --- HSL Wheel ---

  var wheelCanvas = document.getElementById("cpgWheel");
  var wheelCtx = wheelCanvas.getContext("2d");
  var wheelMarker = document.getElementById("cpgWheelMarker");
  var wheelWrap = document.getElementById("cpgWheelWrap");
  var wheelSize = 240;
  var wheelCenter = wheelSize / 2;
  var wheelRadius = wheelSize / 2 - 4;

  function drawWheel() {
    var imgData = wheelCtx.createImageData(wheelSize, wheelSize);
    for (var y = 0; y < wheelSize; y++) {
      for (var x = 0; x < wheelSize; x++) {
        var dx = x - wheelCenter;
        var dy = y - wheelCenter;
        var dist = Math.sqrt(dx * dx + dy * dy);
        var idx = (y * wheelSize + x) * 4;
        if (dist <= wheelRadius) {
          var angle = (Math.atan2(dy, dx) * 180 / Math.PI + 360) % 360;
          var sat = (dist / wheelRadius) * 100;
          var rgb = hslToRgb(angle, sat, state.baseHSL[2]);
          imgData.data[idx] = rgb[0];
          imgData.data[idx + 1] = rgb[1];
          imgData.data[idx + 2] = rgb[2];
          imgData.data[idx + 3] = 255;
        } else {
          imgData.data[idx + 3] = 0;
        }
      }
    }
    wheelCtx.putImageData(imgData, 0, 0);
  }

  function updateWheelMarker() {
    var h = state.baseHSL[0];
    var s = state.baseHSL[1];
    var angle = h * Math.PI / 180;
    var dist = (s / 100) * wheelRadius;
    var x = wheelCenter + dist * Math.cos(angle);
    var y = wheelCenter + dist * Math.sin(angle);
    wheelMarker.style.left = x + "px";
    wheelMarker.style.top = y + "px";
    var rgb = hslToRgb(h, s, state.baseHSL[2]);
    wheelMarker.style.background = rgbToHex(rgb[0], rgb[1], rgb[2]);
  }

  function wheelPick(e) {
    var rect = wheelCanvas.getBoundingClientRect();
    var x = e.clientX - rect.left;
    var y = e.clientY - rect.top;
    var scaleX = wheelSize / rect.width;
    var scaleY = wheelSize / rect.height;
    var cx = x * scaleX;
    var cy = y * scaleY;
    var dx = cx - wheelCenter;
    var dy = cy - wheelCenter;
    var dist = Math.sqrt(dx * dx + dy * dy);
    if (dist > wheelRadius) return;
    var angle = (Math.atan2(dy, dx) * 180 / Math.PI + 360) % 360;
    var sat = Math.round((dist / wheelRadius) * 100);
    state.baseHSL[0] = Math.round(angle);
    state.baseHSL[1] = sat;
    syncFromHSL();
  }

  var wheelDragging = false;
  wheelCanvas.addEventListener("mousedown", function(e) { wheelDragging = true; wheelPick(e); });
  document.addEventListener("mousemove", function(e) { if (wheelDragging) wheelPick(e); });
  document.addEventListener("mouseup", function() { wheelDragging = false; });
  wheelCanvas.addEventListener("touchstart", function(e) { e.preventDefault(); wheelDragging = true; wheelPick(e.touches[0]); }, {passive: false});
  document.addEventListener("touchmove", function(e) { if (wheelDragging) wheelPick(e.touches[0]); });
  document.addEventListener("touchend", function() { wheelDragging = false; });

  // --- Sync Functions ---

  function syncFromHSL() {
    var rgb = hslToRgb(state.baseHSL[0], state.baseHSL[1], state.baseHSL[2]);
    var hex = rgbToHex(rgb[0], rgb[1], rgb[2]);
    document.getElementById("cpgHexInput").value = hex;
    document.getElementById("cpgPicker").value = hex;
    updateWheelMarker();
    generate();
  }

  function syncFromHex(hex) {
    var rgb = hexToRgb(hex);
    state.baseHSL = rgbToHsl(rgb[0], rgb[1], rgb[2]);
    document.getElementById("cpgPicker").value = hex.toUpperCase();
    drawWheel();
    updateWheelMarker();
    generate();
  }

  // --- Input Handlers ---

  document.getElementById("cpgHexInput").addEventListener("input", function() {
    var v = this.value.trim();
    if (/^#[0-9a-fA-F]{6}$/.test(v)) syncFromHex(v);
  });

  document.getElementById("cpgPicker").addEventListener("input", function() {
    document.getElementById("cpgHexInput").value = this.value.toUpperCase();
    syncFromHex(this.value);
  });

  // Tabs
  var tabs = document.querySelectorAll("#cpgTabs .cpg-tab");
  tabs.forEach(function(tab) {
    tab.addEventListener("click", function() {
      tabs.forEach(function(t) { t.classList.remove("active"); });
      tab.classList.add("active");
      state.mode = tab.getAttribute("data-mode");
      generate();
    });
  });

  // Sliders
  document.getElementById("cpgSatSlider").addEventListener("input", function() {
    state.satAdj = parseInt(this.value);
    document.getElementById("cpgSatVal").textContent = (state.satAdj > 0 ? "+" : "") + state.satAdj;
    generate();
  });
  document.getElementById("cpgLitSlider").addEventListener("input", function() {
    state.litAdj = parseInt(this.value);
    document.getElementById("cpgLitVal").textContent = (state.litAdj > 0 ? "+" : "") + state.litAdj;
    generate();
  });

  // --- Harmony Generation ---

  function harmonyAngles(mode) {
    switch (mode) {
      case "complementary": return [0, 180];
      case "analogous": return [0, -30, 30, -60, 60];
      case "triadic": return [0, 120, 240];
      case "split": return [0, 150, 210];
      case "tetradic": return [0, 90, 180, 270];
      case "monochromatic": return [0, 0, 0, 0, 0];
      default: return [0, 180];
    }
  }

  function generate() {
    var h = state.baseHSL[0];
    var s = state.baseHSL[1];
    var l = state.baseHSL[2];
    var angles = harmonyAngles(state.mode);
    var newPalette = [];

    for (var i = 0; i < angles.length; i++) {
      if (state.locked[i] && state.palette[i]) {
        newPalette.push(state.palette[i]);
        continue;
      }
      var nh = (h + angles[i] + 360) % 360;
      var ns = clamp(s + state.satAdj, 0, 100);
      var nl = l;

      if (state.mode === "monochromatic") {
        var offsets = [0, -20, -10, 10, 20];
        nl = clamp(l + offsets[i] + state.litAdj, 5, 95);
        ns = clamp(s + (i % 2 === 0 ? 0 : -15) + state.satAdj, 0, 100);
      } else {
        nl = clamp(l + state.litAdj, 5, 95);
      }

      // Add extra shades to reach 5+ colors for modes with fewer base angles
      var rgb = hslToRgb(nh, ns, nl);
      newPalette.push({
        h: nh, s: ns, l: nl,
        rgb: rgb,
        hex: rgbToHex(rgb[0], rgb[1], rgb[2])
      });
    }

    // Pad to at least 5 colors by adding lightness variants
    while (newPalette.length < 5) {
      var base = newPalette[newPalette.length - 1];
      var padL = clamp(base.l + (newPalette.length % 2 === 0 ? 15 : -15), 10, 90);
      var padS = clamp(base.s - 10, 0, 100);
      var padRgb = hslToRgb(base.h, padS, padL);
      newPalette.push({
        h: base.h, s: padS, l: padL,
        rgb: padRgb,
        hex: rgbToHex(padRgb[0], padRgb[1], padRgb[2])
      });
    }

    state.palette = newPalette;
    // Ensure locked array matches palette length
    while (state.locked.length < state.palette.length) state.locked.push(false);

    renderPalette();
    renderA11y();
    saveToHistory();
  }

  // --- Render Palette ---

  function renderPalette() {
    var container = document.getElementById("cpgPalette");
    var html = "";
    for (var i = 0; i < state.palette.length; i++) {
      var c = state.palette[i];
      var lockClass = state.locked[i] ? " locked" : "";
      var lockIcon = state.locked[i] ? "&#128274;" : "&#128275;";
      html += '<div class="cpg-swatch">';
      html += '<div class="cpg-swatch-color" style="background:' + c.hex + '" onclick="CPG.copyColor(' + i + ', this)">';
      html += '<button class="cpg-swatch-lock' + lockClass + '" onclick="event.stopPropagation();CPG.toggleLock(' + i + ')" title="' + (state.locked[i] ? "Unlock" : "Lock") + '">' + lockIcon + '</button>';
      html += '<span class="cpg-copied-toast" id="cpgToast' + i + '">Copied</span>';
      html += '</div>';
      html += '<div class="cpg-swatch-info">';
      html += '<div class="cpg-hex-val" onclick="CPG.copyHex(\'' + c.hex + '\')">' + c.hex + '</div>';
      html += '<div>rgb(' + c.rgb[0] + ', ' + c.rgb[1] + ', ' + c.rgb[2] + ')</div>';
      html += '<div>hsl(' + c.h + ', ' + c.s + '%, ' + c.l + '%)</div>';
      html += '</div></div>';
    }
    container.innerHTML = html;
  }

  // --- Accessibility ---

  function renderA11y() {
    var grid = document.getElementById("cpgA11yGrid");
    var html = "";
    var p = state.palette;
    for (var i = 0; i < p.length; i++) {
      for (var j = i + 1; j < p.length; j++) {
        var ratio = contrastRatio(p[i].rgb, p[j].rgb);
        var ratioStr = ratio.toFixed(2);
        var aa = ratio >= 4.5;
        var aaa = ratio >= 7;
        var aaLarge = ratio >= 3;
        html += '<div class="cpg-a11y-pair">';
        html += '<div class="cpg-a11y-colors">';
        html += '<span class="cpg-a11y-dot" style="background:' + p[i].hex + '"></span>';
        html += '<span style="color:var(--cpg-text-dim);font-size:0.7rem;">vs</span>';
        html += '<span class="cpg-a11y-dot" style="background:' + p[j].hex + '"></span>';
        html += '<span class="cpg-a11y-ratio">' + ratioStr + ':1</span>';
        html += '</div>';
        html += '<div class="cpg-a11y-badges">';
        html += '<span class="cpg-badge ' + (aa ? 'cpg-badge-pass' : 'cpg-badge-fail') + '">AA ' + (aa ? 'Pass' : 'Fail') + '</span>';
        html += '<span class="cpg-badge ' + (aaa ? 'cpg-badge-pass' : 'cpg-badge-fail') + '">AAA ' + (aaa ? 'Pass' : 'Fail') + '</span>';
        html += '<span class="cpg-badge ' + (aaLarge ? 'cpg-badge-pass' : 'cpg-badge-fail') + '">AA-Lg ' + (aaLarge ? 'Pass' : 'Fail') + '</span>';
        html += '</div></div>';
      }
    }
    grid.innerHTML = html;
  }

  // --- History (localStorage) ---

  function loadHistory() {
    try {
      var raw = localStorage.getItem("cpg_history");
      if (raw) state.history = JSON.parse(raw);
    } catch(e) {}
    renderHistory();
  }

  function saveToHistory() {
    var entry = state.palette.map(function(c) { return c.hex; });
    // Avoid duplicate of last entry
    if (state.history.length > 0 && JSON.stringify(state.history[0]) === JSON.stringify(entry)) return;
    state.history.unshift(entry);
    if (state.history.length > state.MAX_HISTORY) state.history = state.history.slice(0, state.MAX_HISTORY);
    try { localStorage.setItem("cpg_history", JSON.stringify(state.history)); } catch(e) {}
    renderHistory();
  }

  function renderHistory() {
    var el = document.getElementById("cpgHistory");
    var list = document.getElementById("cpgHistoryList");
    if (state.history.length === 0) { el.style.display = "none"; return; }
    el.style.display = "block";
    var html = "";
    for (var i = 0; i < state.history.length; i++) {
      var colors = state.history[i];
      html += '<div class="cpg-history-item" onclick="CPG.loadHistory(' + i + ')">';
      for (var j = 0; j < colors.length; j++) {
        html += '<span class="cpg-history-dot" style="background:' + colors[j] + '"></span>';
      }
      html += '<span class="cpg-history-label">' + colors.join(", ") + '</span>';
      html += '</div>';
    }
    list.innerHTML = html;
  }

  // --- Image Palette Extraction ---

  var imgCanvas = document.getElementById("cpgImgCanvas");
  var imgCtx = imgCanvas.getContext("2d", { willReadFrequently: true });

  document.getElementById("cpgFileInput").addEventListener("change", function() {
    if (this.files && this.files[0]) loadImage(this.files[0]);
  });

  var uploadEl = document.getElementById("cpgUpload");
  uploadEl.addEventListener("dragover", function(e) { e.preventDefault(); });
  uploadEl.addEventListener("drop", function(e) {
    e.preventDefault();
    if (e.dataTransfer.files && e.dataTransfer.files[0]) loadImage(e.dataTransfer.files[0]);
  });

  function loadImage(file) {
    if (!file.type.match(/^image\//)) return;
    var reader = new FileReader();
    reader.onload = function(e) {
      var img = new Image();
      img.onload = function() {
        var maxW = 400;
        var w = img.naturalWidth, h = img.naturalHeight;
        if (w > maxW) { h = Math.round(h * (maxW / w)); w = maxW; }
        imgCanvas.width = w;
        imgCanvas.height = h;
        imgCtx.drawImage(img, 0, 0, w, h);
        document.getElementById("cpgImgPreview").style.display = "block";
        extractImagePalette(w, h);
      };
      img.src = e.target.result;
    };
    reader.readAsDataURL(file);
  }

  function extractImagePalette(w, h) {
    var data = imgCtx.getImageData(0, 0, w, h).data;
    var samples = [];
    var step = Math.max(1, Math.floor((w * h) / 2000));
    for (var i = 0; i < data.length; i += step * 4) {
      samples.push([data[i], data[i+1], data[i+2]]);
    }
    // Simple k-means clustering for 5 colors
    var k = 5;
    var centroids = [];
    for (var c = 0; c < k; c++) {
      centroids.push(samples[Math.floor(Math.random() * samples.length)].slice());
    }
    for (var iter = 0; iter < 10; iter++) {
      var clusters = [];
      for (var ci = 0; ci < k; ci++) clusters.push([]);
      for (var si = 0; si < samples.length; si++) {
        var minD = Infinity, best = 0;
        for (var ci2 = 0; ci2 < k; ci2++) {
          var dr = samples[si][0] - centroids[ci2][0];
          var dg = samples[si][1] - centroids[ci2][1];
          var db = samples[si][2] - centroids[ci2][2];
          var d = dr*dr + dg*dg + db*db;
          if (d < minD) { minD = d; best = ci2; }
        }
        clusters[best].push(samples[si]);
      }
      for (var ci3 = 0; ci3 < k; ci3++) {
        if (clusters[ci3].length === 0) continue;
        var sr = 0, sg = 0, sb = 0;
        for (var p = 0; p < clusters[ci3].length; p++) {
          sr += clusters[ci3][p][0]; sg += clusters[ci3][p][1]; sb += clusters[ci3][p][2];
        }
        centroids[ci3] = [
          Math.round(sr / clusters[ci3].length),
          Math.round(sg / clusters[ci3].length),
          Math.round(sb / clusters[ci3].length)
        ];
      }
    }
    // Sort by luminance
    centroids.sort(function(a, b) { return luminance(b[0], b[1], b[2]) - luminance(a[0], a[1], a[2]); });
    var palEl = document.getElementById("cpgImgPalette");
    var html = "";
    for (var ci4 = 0; ci4 < centroids.length; ci4++) {
      var hex = rgbToHex(centroids[ci4][0], centroids[ci4][1], centroids[ci4][2]);
      html += '<div class="cpg-img-swatch" style="background:' + hex + '" onclick="CPG.useImgColor(\'' + hex + '\')" title="' + hex + '"></div>';
    }
    palEl.innerHTML = html;
  }

  // --- Export ---

  function getExportCode(fmt) {
    var colors = state.palette;
    var lines = [];
    switch (fmt) {
      case "css":
        lines.push(":root {");
        for (var i = 0; i < colors.length; i++) {
          lines.push("  --color-" + (i + 1) + ": " + colors[i].hex + ";");
        }
        lines.push("}");
        break;
      case "scss":
        for (var i2 = 0; i2 < colors.length; i2++) {
          lines.push("$color-" + (i2 + 1) + ": " + colors[i2].hex + ";");
        }
        break;
      case "tailwind":
        lines.push("// tailwind.config.js");
        lines.push("module.exports = {");
        lines.push("  theme: {");
        lines.push("    extend: {");
        lines.push("      colors: {");
        for (var i3 = 0; i3 < colors.length; i3++) {
          var comma = i3 < colors.length - 1 ? "," : "";
          lines.push("        'palette-" + (i3 + 1) + "': '" + colors[i3].hex + "'" + comma);
        }
        lines.push("      }");
        lines.push("    }");
        lines.push("  }");
        lines.push("}");
        break;
      case "json":
        var obj = {};
        for (var i4 = 0; i4 < colors.length; i4++) {
          obj["color-" + (i4 + 1)] = {
            hex: colors[i4].hex,
            rgb: "rgb(" + colors[i4].rgb[0] + ", " + colors[i4].rgb[1] + ", " + colors[i4].rgb[2] + ")",
            hsl: "hsl(" + colors[i4].h + ", " + colors[i4].s + "%, " + colors[i4].l + "%)"
          };
        }
        lines.push(JSON.stringify(obj, null, 2));
        break;
      case "text":
        for (var i5 = 0; i5 < colors.length; i5++) {
          lines.push(colors[i5].hex);
        }
        break;
    }
    return lines.join("\n");
  }

  // --- Public API ---

  window.CPG = {
    generate: function() { generate(); },

    randomBase: function() {
      state.baseHSL = [Math.floor(Math.random() * 360), 50 + Math.floor(Math.random() * 40), 40 + Math.floor(Math.random() * 30)];
      state.locked = [];
      drawWheel();
      syncFromHSL();
    },

    toggleLock: function(idx) {
      state.locked[idx] = !state.locked[idx];
      renderPalette();
    },

    copyColor: function(idx, el) {
      var hex = state.palette[idx].hex;
      navigator.clipboard.writeText(hex).then(function() {
        var toast = document.getElementById("cpgToast" + idx);
        if (toast) { toast.classList.add("show"); setTimeout(function() { toast.classList.remove("show"); }, 1200); }
      });
    },

    copyHex: function(hex) {
      navigator.clipboard.writeText(hex);
    },

    showExport: function() {
      state.exportFmt = "css";
      document.getElementById("cpgExportCode").textContent = getExportCode("css");
      var etabs = document.querySelectorAll("#cpgExportTabs .cpg-export-tab");
      etabs.forEach(function(t) { t.classList.remove("active"); });
      etabs[0].classList.add("active");
      document.getElementById("cpgExportOverlay").classList.add("show");
    },

    closeExport: function(e) {
      if (e.target === document.getElementById("cpgExportOverlay")) {
        document.getElementById("cpgExportOverlay").classList.remove("show");
      }
    },

    copyExport: function() {
      var code = document.getElementById("cpgExportCode").textContent;
      navigator.clipboard.writeText(code);
    },

    loadHistory: function(idx) {
      if (!state.history[idx]) return;
      var colors = state.history[idx];
      state.palette = [];
      state.locked = [];
      for (var i = 0; i < colors.length; i++) {
        var rgb = hexToRgb(colors[i]);
        var hsl = rgbToHsl(rgb[0], rgb[1], rgb[2]);
        state.palette.push({ h: hsl[0], s: hsl[1], l: hsl[2], rgb: rgb, hex: colors[i] });
        state.locked.push(false);
      }
      // Update base from first color
      state.baseHSL = [state.palette[0].h, state.palette[0].s, state.palette[0].l];
      document.getElementById("cpgHexInput").value = state.palette[0].hex;
      document.getElementById("cpgPicker").value = state.palette[0].hex;
      drawWheel();
      updateWheelMarker();
      renderPalette();
      renderA11y();
    },

    clearHistory: function() {
      state.history = [];
      try { localStorage.removeItem("cpg_history"); } catch(e) {}
      renderHistory();
    },

    useImgColor: function(hex) {
      document.getElementById("cpgHexInput").value = hex;
      syncFromHex(hex);
    }
  };

  // Export tab clicks
  var exportTabs = document.querySelectorAll("#cpgExportTabs .cpg-export-tab");
  exportTabs.forEach(function(tab) {
    tab.addEventListener("click", function() {
      exportTabs.forEach(function(t) { t.classList.remove("active"); });
      tab.classList.add("active");
      state.exportFmt = tab.getAttribute("data-fmt");
      document.getElementById("cpgExportCode").textContent = getExportCode(state.exportFmt);
    });
  });

  // --- Init ---
  drawWheel();
  updateWheelMarker();
  loadHistory();
  generate();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Color Palette Generator",
      "url": "https://theluckystrike.github.io/tools/color-palette-generator/",
      "applicationCategory": "DesignApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "description": "Generate color palettes with complementary, analogous, triadic, and split-complementary harmony modes. Extract palettes from images and export as CSS, SCSS, Tailwind, or JSON.",
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Color Palette Generator", "item": "https://theluckystrike.github.io/tools/color-palette-generator/" }
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://zovo.one/favicon.ico"
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How many colors should a web design palette have?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most web design systems use between 5 and 8 core colors. This typically breaks down into 1-2 brand/accent colors, 2-3 neutral shades for backgrounds and text, and 2-3 semantic colors for success, warning, and error states. Each core color usually has a range of lighter and darker variants, which can bring the total number of individual values to 30 or more in a mature design system."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between complementary and split-complementary color schemes?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A complementary scheme uses two colors that sit directly opposite each other on the color wheel, creating maximum contrast. A split-complementary scheme starts with one base color but instead of using its direct opposite, it uses the two colors adjacent to the opposite. This reduces the visual tension while still providing clear contrast."
          }
        },
        {
          "@type": "Question",
          "name": "Can I extract a color palette from a photograph?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Upload any image using the extraction section below the palette generator. The tool samples pixels across the image and clusters them to identify the 5 most dominant colors. The extracted colors can then be used as starting points for further refinement with the harmony modes."
          }
        },
        {
          "@type": "Question",
          "name": "What WCAG contrast ratio do I need for accessible text?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "WCAG 2.1 Level AA requires a contrast ratio of at least 4.5:1 for normal-sized text and 3:1 for large text. Level AAA requires 7:1 for normal text and 4.5:1 for large text."
          }
        },
        {
          "@type": "Question",
          "name": "How do I use the exported Tailwind config?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Tailwind export generates a JavaScript object that fits inside the colors key of your tailwind.config.js file. Copy the output, open your config, and paste it into theme.extend.colors to add alongside defaults, or theme.colors to replace defaults."
          }
        },
        {
          "@type": "Question",
          "name": "Is my uploaded image sent to a server?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All image processing happens locally in your browser using the HTML Canvas API. Nothing is uploaded, transmitted, or stored on any server. The same applies to the palette generation, export, and history features."
          }
        }
      ]
    }
  ]
}
</script>
