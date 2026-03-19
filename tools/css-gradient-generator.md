---
layout: page
title: "Free CSS Gradient Generator — Linear, Radial & Conic Gradients | Zovo"
description: "Create beautiful CSS gradients with a visual editor. Generate linear, radial, and conic gradients with multiple color stops, angle control, and live preview. Copy CSS code instantly."
permalink: /tools/css-gradient-generator/
keywords: "css gradient generator, gradient maker, linear gradient, radial gradient, conic gradient, css gradient, gradient css code, color gradient tool"
date: 2026-03-19
categories: [tools]
tags: [css, gradient, generator, design, color, web-development, linear, radial]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root {
  --cg-bg: #0a0a0f;
  --cg-surface: #12121a;
  --cg-surface2: #1a1a28;
  --cg-border: #1e1e2e;
  --cg-border-hover: #2e2e44;
  --cg-primary: #6C5CE7;
  --cg-primary-dark: #5A4BD1;
  --cg-primary-light: #8B7CF7;
  --cg-secondary: #00ff88;
  --cg-text: #e0e0e0;
  --cg-text-muted: #8888aa;
  --cg-text-dim: #555570;
  --cg-radius: 10px;
  --cg-radius-sm: 6px;
  --cg-font: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --cg-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
}

.cg-wrap {
  font-family: var(--cg-font);
  color: var(--cg-text);
  max-width: 960px;
  margin: 0 auto;
  padding: 0 16px;
  line-height: 1.6;
}

.cg-wrap * { box-sizing: border-box; }

.cg-hero { text-align: center; padding: 40px 0 24px; }

.cg-hero h1 {
  font-size: 2.2rem;
  font-weight: 700;
  color: var(--cg-text);
  margin: 0 0 14px;
  line-height: 1.2;
}

.cg-hero h1 span { color: var(--cg-primary); }

.cg-intro {
  font-size: 1.02rem;
  color: var(--cg-text-muted);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.7;
}

.cg-updated {
  display: inline-block;
  font-size: 0.75rem;
  color: var(--cg-text-muted);
  margin-top: 12px;
  padding: 4px 12px;
  border: 1px solid var(--cg-border);
  border-radius: 20px;
}

/* Toast */
.cg-toast {
  position: fixed;
  bottom: 24px;
  left: 50%;
  transform: translateX(-50%) translateY(80px);
  background: var(--cg-primary);
  color: #fff;
  padding: 10px 24px;
  border-radius: 8px;
  font-size: 0.9rem;
  font-weight: 500;
  z-index: 9999;
  opacity: 0;
  transition: transform 0.3s ease, opacity 0.3s ease;
  pointer-events: none;
}

.cg-toast.show {
  transform: translateX(-50%) translateY(0);
  opacity: 1;
}

/* Type selector row */
.cg-type-row {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
  flex-wrap: wrap;
  align-items: center;
}

.cg-type-btn {
  padding: 8px 18px;
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: 8px;
  color: var(--cg-text-muted);
  font-family: var(--cg-font);
  font-size: 0.88rem;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.15s, color 0.15s, border-color 0.15s;
}

.cg-type-btn:hover { border-color: var(--cg-primary); color: var(--cg-text); }

.cg-type-btn.active {
  background: var(--cg-primary);
  border-color: var(--cg-primary);
  color: #fff;
}

.cg-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 8px 16px;
  background: var(--cg-primary);
  color: #fff;
  border: none;
  border-radius: 8px;
  font-family: var(--cg-font);
  font-size: 0.88rem;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.2s;
  white-space: nowrap;
}

.cg-btn:hover { background: var(--cg-primary-dark); }

.cg-btn-outline {
  background: transparent;
  border: 1px solid var(--cg-border);
  color: var(--cg-text);
}

.cg-btn-outline:hover {
  background: var(--cg-surface);
  border-color: var(--cg-primary);
}

.cg-btn-sm { padding: 6px 12px; font-size: 0.82rem; }

.cg-spacer { flex: 1; }

/* Preview */
.cg-preview {
  width: 100%;
  height: 320px;
  border-radius: var(--cg-radius);
  border: 1px solid var(--cg-border);
  margin-bottom: 16px;
  transition: background 0.15s;
}

/* Controls panel */
.cg-controls {
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: var(--cg-radius);
  padding: 20px;
  margin-bottom: 16px;
}

.cg-control-row {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 14px;
  flex-wrap: wrap;
}

.cg-control-row:last-child { margin-bottom: 0; }

.cg-label {
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--cg-text-muted);
  min-width: 80px;
}

.cg-slider {
  -webkit-appearance: none;
  appearance: none;
  flex: 1;
  min-width: 120px;
  height: 6px;
  background: var(--cg-border);
  border-radius: 3px;
  outline: none;
}

.cg-slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 18px;
  height: 18px;
  background: var(--cg-primary);
  border-radius: 50%;
  cursor: pointer;
  border: 2px solid #fff;
}

.cg-slider::-moz-range-thumb {
  width: 18px;
  height: 18px;
  background: var(--cg-primary);
  border-radius: 50%;
  cursor: pointer;
  border: 2px solid #fff;
}

.cg-val {
  font-family: var(--cg-mono);
  font-size: 0.85rem;
  color: var(--cg-secondary);
  min-width: 50px;
  text-align: right;
}

.cg-select {
  padding: 6px 10px;
  background: var(--cg-bg);
  border: 1px solid var(--cg-border);
  border-radius: var(--cg-radius-sm);
  color: var(--cg-text);
  font-family: var(--cg-font);
  font-size: 0.85rem;
  outline: none;
  cursor: pointer;
}

.cg-select:focus { border-color: var(--cg-primary); }

/* Color stop bar */
.cg-stops-section { margin-bottom: 14px; }

.cg-stops-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 10px;
}

.cg-stops-title {
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--cg-text-muted);
}

.cg-stop-bar-wrap {
  position: relative;
  height: 32px;
  border-radius: 6px;
  margin-bottom: 12px;
  cursor: pointer;
  border: 1px solid var(--cg-border);
}

.cg-stop-bar {
  width: 100%;
  height: 100%;
  border-radius: 5px;
}

.cg-stop-handle {
  position: absolute;
  top: -4px;
  width: 16px;
  height: 40px;
  border-radius: 4px;
  border: 2px solid #fff;
  cursor: grab;
  transform: translateX(-8px);
  box-shadow: 0 2px 6px rgba(0,0,0,0.4);
  transition: box-shadow 0.15s;
}

.cg-stop-handle:hover { box-shadow: 0 2px 10px rgba(108,92,231,0.6); }

.cg-stop-handle.active {
  border-color: var(--cg-primary);
  box-shadow: 0 0 0 3px rgba(108,92,231,0.3);
}

.cg-stop-handle.dragging { cursor: grabbing; }

/* Stop editor row */
.cg-stop-editor {
  display: flex;
  gap: 10px;
  align-items: center;
  flex-wrap: wrap;
  padding: 10px 12px;
  background: var(--cg-bg);
  border: 1px solid var(--cg-border);
  border-radius: var(--cg-radius-sm);
  margin-bottom: 10px;
}

.cg-stop-color-input {
  width: 36px;
  height: 36px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  padding: 0;
  background: transparent;
}

.cg-stop-color-input::-webkit-color-swatch-wrapper { padding: 0; }
.cg-stop-color-input::-webkit-color-swatch { border: 1px solid var(--cg-border); border-radius: 6px; }
.cg-stop-color-input::-moz-color-swatch { border: 1px solid var(--cg-border); border-radius: 6px; }

.cg-stop-pos {
  width: 60px;
  padding: 6px 8px;
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: var(--cg-radius-sm);
  color: var(--cg-text);
  font-family: var(--cg-mono);
  font-size: 0.82rem;
  text-align: center;
  outline: none;
}

.cg-stop-pos:focus { border-color: var(--cg-primary); }

.cg-stop-delete {
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: transparent;
  border: 1px solid var(--cg-border);
  border-radius: 4px;
  cursor: pointer;
  color: var(--cg-text-dim);
  padding: 0;
  transition: color 0.15s, border-color 0.15s;
}

.cg-stop-delete:hover { color: #ff4466; border-color: #ff4466; }

/* Toggle */
.cg-toggle-row {
  display: flex;
  align-items: center;
  gap: 10px;
}

.cg-toggle {
  position: relative;
  width: 40px;
  height: 22px;
  background: var(--cg-border);
  border-radius: 11px;
  cursor: pointer;
  transition: background 0.2s;
  border: none;
  padding: 0;
}

.cg-toggle.on { background: var(--cg-primary); }

.cg-toggle::after {
  content: "";
  position: absolute;
  top: 2px;
  left: 2px;
  width: 18px;
  height: 18px;
  background: #fff;
  border-radius: 50%;
  transition: transform 0.2s;
}

.cg-toggle.on::after { transform: translateX(18px); }

.cg-toggle-label {
  font-size: 0.85rem;
  color: var(--cg-text-muted);
}

/* Code output */
.cg-code-section {
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: var(--cg-radius);
  margin-bottom: 16px;
  overflow: hidden;
}

.cg-code-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 16px;
  border-bottom: 1px solid var(--cg-border);
  background: var(--cg-surface2);
}

.cg-code-title {
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--cg-text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.cg-code-block {
  padding: 16px;
  font-family: var(--cg-mono);
  font-size: 0.85rem;
  line-height: 1.7;
  color: var(--cg-text);
  overflow-x: auto;
  white-space: pre-wrap;
  word-break: break-all;
}

.cg-code-block .hl-prop { color: #7ec8e3; }
.cg-code-block .hl-val { color: var(--cg-secondary); }
.cg-code-block .hl-punc { color: var(--cg-text-dim); }
.cg-code-block .hl-comment { color: var(--cg-text-dim); font-style: italic; }

/* Presets */
.cg-presets {
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: var(--cg-radius);
  padding: 16px;
  margin-bottom: 16px;
}

.cg-presets-title {
  font-size: 0.82rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--cg-text-muted);
  margin-bottom: 12px;
}

.cg-presets-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
  gap: 8px;
}

.cg-preset {
  height: 56px;
  border-radius: 8px;
  border: 2px solid transparent;
  cursor: pointer;
  transition: border-color 0.15s, transform 0.15s;
}

.cg-preset:hover {
  border-color: var(--cg-primary);
  transform: scale(1.05);
}

/* Content */
.cg-content {
  margin-top: 48px;
  padding-top: 32px;
  border-top: 1px solid var(--cg-border);
}

.cg-content h2 {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--cg-text);
  margin: 32px 0 12px;
}

.cg-content h2:first-child { margin-top: 0; }

.cg-content p {
  color: var(--cg-text-muted);
  font-size: 0.95rem;
  line-height: 1.75;
  margin: 0 0 14px;
}

.cg-content ul {
  color: var(--cg-text-muted);
  font-size: 0.95rem;
  line-height: 1.75;
  padding-left: 20px;
  margin: 0 0 14px;
}

.cg-content code {
  font-family: var(--cg-mono);
  font-size: 0.88em;
  background: var(--cg-surface2);
  padding: 2px 6px;
  border-radius: 4px;
  color: var(--cg-secondary);
}

/* FAQ */
.cg-faq { margin-top: 32px; }

.cg-faq h2 {
  font-size: 1.4rem;
  font-weight: 700;
  margin: 0 0 20px;
  color: var(--cg-text);
}

.cg-faq-item { margin-bottom: 20px; }

.cg-faq-item h3 {
  font-size: 1rem;
  font-weight: 600;
  margin: 0 0 6px;
  color: var(--cg-text);
}

.cg-faq-item p {
  margin: 0;
  color: var(--cg-text-muted);
  font-size: 0.93rem;
  line-height: 1.7;
}

/* Related + Author + Footer */
.cg-related {
  margin-top: 2rem;
  padding: 1.5rem;
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: 12px;
}

.cg-related h2 {
  color: var(--cg-primary);
  font-size: 1.2rem;
  margin: 0 0 1rem;
}

.cg-related ul { list-style: none; padding: 0; margin: 0; }
.cg-related li { margin-bottom: 0.5rem; }
.cg-related a { color: var(--cg-secondary); text-decoration: none; }
.cg-related a:hover { text-decoration: underline; }

.cg-author {
  margin-top: 2rem;
  padding: 1.5rem;
  background: var(--cg-surface);
  border: 1px solid var(--cg-border);
  border-radius: 12px;
  display: flex;
  gap: 1rem;
  align-items: center;
}

.cg-author-avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: var(--cg-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: 700;
  font-size: 1.2rem;
  flex-shrink: 0;
}

.cg-author-name { color: var(--cg-text); font-weight: 600; }
.cg-author-bio { color: var(--cg-text-muted); font-size: 0.85rem; }
.cg-author a { color: var(--cg-primary); text-decoration: none; }

.cg-footer {
  text-align: center;
  padding: 2rem 0;
  color: var(--cg-text-dim);
  font-size: 0.85rem;
  border-top: 1px solid var(--cg-border);
  margin-top: 3rem;
}

.cg-footer a { color: var(--cg-primary); text-decoration: none; }

@media (max-width: 640px) {
  .cg-hero h1 { font-size: 1.6rem; }
  .cg-preview { height: 200px; }
  .cg-controls { padding: 14px; }
  .cg-control-row { gap: 8px; }
  .cg-label { min-width: 60px; font-size: 0.75rem; }
  .cg-presets-grid { grid-template-columns: repeat(auto-fill, minmax(60px, 1fr)); }
  .cg-preset { height: 44px; }
}
</style>

<div class="cg-wrap" id="cgApp">

<div class="cg-hero">
  <h1><span>CSS Gradient</span> Generator</h1>
  <p class="cg-intro">Create linear, radial, and conic CSS gradients with a visual editor. Adjust colors, positions, and angles in real time, then copy the generated CSS. Choose from presets or build from scratch. No signup needed, everything runs in your browser.</p>
  <span class="cg-updated">Last updated: March 2026</span>
</div>

<!-- Gradient Type + Actions -->
<div class="cg-type-row">
  <button class="cg-type-btn active" data-type="linear" onclick="cgSetType('linear',this)">Linear</button>
  <button class="cg-type-btn" data-type="radial" onclick="cgSetType('radial',this)">Radial</button>
  <button class="cg-type-btn" data-type="conic" onclick="cgSetType('conic',this)">Conic</button>
  <span class="cg-spacer"></span>
  <button class="cg-btn cg-btn-outline cg-btn-sm" onclick="cgRandomGradient()">Random</button>
</div>

<!-- Live Preview -->
<div class="cg-preview" id="cgPreview"></div>

<!-- Controls -->
<div class="cg-controls" id="cgControls">

  <!-- Linear controls -->
  <div id="cgLinearCtrl">
    <div class="cg-control-row">
      <span class="cg-label">Angle</span>
      <input type="range" class="cg-slider" id="cgAngle" min="0" max="360" value="90" oninput="cgUpdate()">
      <span class="cg-val" id="cgAngleVal">90deg</span>
    </div>
  </div>

  <!-- Radial controls -->
  <div id="cgRadialCtrl" style="display:none;">
    <div class="cg-control-row">
      <span class="cg-label">Shape</span>
      <select class="cg-select" id="cgRadialShape" onchange="cgUpdate()">
        <option value="circle">Circle</option>
        <option value="ellipse" selected>Ellipse</option>
      </select>
    </div>
    <div class="cg-control-row">
      <span class="cg-label">Position</span>
      <select class="cg-select" id="cgRadialPos" onchange="cgUpdate()">
        <option value="center" selected>Center</option>
        <option value="top">Top</option>
        <option value="bottom">Bottom</option>
        <option value="left">Left</option>
        <option value="right">Right</option>
        <option value="top left">Top Left</option>
        <option value="top right">Top Right</option>
        <option value="bottom left">Bottom Left</option>
        <option value="bottom right">Bottom Right</option>
      </select>
    </div>
  </div>

  <!-- Conic controls -->
  <div id="cgConicCtrl" style="display:none;">
    <div class="cg-control-row">
      <span class="cg-label">Start Angle</span>
      <input type="range" class="cg-slider" id="cgConicAngle" min="0" max="360" value="0" oninput="cgUpdate()">
      <span class="cg-val" id="cgConicAngleVal">0deg</span>
    </div>
    <div class="cg-control-row">
      <span class="cg-label">Position</span>
      <select class="cg-select" id="cgConicPos" onchange="cgUpdate()">
        <option value="center" selected>Center</option>
        <option value="top">Top</option>
        <option value="bottom">Bottom</option>
        <option value="left">Left</option>
        <option value="right">Right</option>
        <option value="top left">Top Left</option>
        <option value="top right">Top Right</option>
        <option value="bottom left">Bottom Left</option>
        <option value="bottom right">Bottom Right</option>
      </select>
    </div>
  </div>

  <!-- Color stops -->
  <div class="cg-stops-section">
    <div class="cg-stops-header">
      <span class="cg-stops-title">Color Stops</span>
      <button class="cg-btn cg-btn-sm cg-btn-outline" onclick="cgAddStop()">Add Stop</button>
    </div>
    <div class="cg-stop-bar-wrap" id="cgStopBar" onclick="cgBarClick(event)">
      <div class="cg-stop-bar" id="cgStopBarBg"></div>
    </div>
    <div id="cgStopEditors"></div>
  </div>

  <!-- Options -->
  <div class="cg-control-row">
    <div class="cg-toggle-row">
      <button class="cg-toggle" id="cgVendorToggle" onclick="cgToggleVendor(this)"></button>
      <span class="cg-toggle-label">Vendor prefixes (-webkit-)</span>
    </div>
    <div class="cg-toggle-row" style="margin-left:20px;">
      <button class="cg-toggle" id="cgRepeatToggle" onclick="cgToggleRepeat(this)"></button>
      <span class="cg-toggle-label">Repeating gradient</span>
    </div>
  </div>
</div>

<!-- CSS Output -->
<div class="cg-code-section">
  <div class="cg-code-header">
    <span class="cg-code-title">Generated CSS</span>
    <button class="cg-btn cg-btn-sm" onclick="cgCopyCSS()">Copy CSS</button>
  </div>
  <div class="cg-code-block" id="cgCodeBlock"></div>
</div>

<!-- Presets -->
<div class="cg-presets">
  <div class="cg-presets-title">Gradient Presets</div>
  <div class="cg-presets-grid" id="cgPresetsGrid"></div>
</div>

<div id="cgToast" class="cg-toast"></div>

<!-- Content -->
<div class="cg-content">

<h2>What Are CSS Gradients</h2>
<p>CSS gradients are image values generated by the browser that create smooth transitions between two or more colors. They are defined using CSS functions like <code>linear-gradient()</code>, <code>radial-gradient()</code>, and <code>conic-gradient()</code>, and can be applied to any property that accepts an image, including <code>background-image</code>, <code>border-image</code>, and <code>list-style-image</code>. Unlike raster images, gradients scale perfectly at any resolution and add zero HTTP requests to your page load, making them a lightweight and performant alternative to image backgrounds.</p>
<p>Gradients are constructed from color stops, which specify a color and optionally a position along the gradient line. The browser interpolates smoothly between adjacent color stops to produce the transition effect. You can have as few as two stops or as many as your design requires. When no position is given, the browser distributes stops evenly across the available space.</p>

<h2>Linear Gradients Explained</h2>
<p>The <code>linear-gradient()</code> function creates a color transition along a straight line. The direction of that line is controlled by an angle value (such as <code>90deg</code> for left-to-right or <code>180deg</code> for top-to-bottom) or by a keyword pair like <code>to bottom right</code>. The angle is measured clockwise from the top of the element, so <code>0deg</code> points upward, <code>90deg</code> points right, <code>180deg</code> points down, and <code>270deg</code> points left.</p>
<p>Color stops in a linear gradient are placed along the gradient line. Each stop can include an optional percentage or length value that pins it to a specific position. For example, <code>linear-gradient(90deg, #6C5CE7 0%, #00ff88 50%, #ff6b6b 100%)</code> creates a three-color transition from purple through green to red, with the green appearing at the midpoint. You can create hard color boundaries instead of smooth transitions by placing two stops at the same position, which is useful for striped patterns.</p>
<p>The <code>repeating-linear-gradient()</code> variant tiles the gradient pattern within the element. This is especially useful for creating diagonal stripes, progress bar effects, and textile-like patterns. The pattern repeats from the last color stop position, so controlling the stop positions directly determines the size of each repeating tile.</p>

<h2>Radial and Conic Gradients</h2>
<p>Radial gradients emanate from a central point outward in a circular or elliptical shape. The <code>radial-gradient()</code> function accepts a shape keyword (<code>circle</code> or <code>ellipse</code>) and a position that determines the center of the gradient. The default shape is an ellipse that conforms to the element's aspect ratio, and the default position is the center of the element. Sizing keywords like <code>closest-side</code>, <code>farthest-corner</code>, and <code>closest-corner</code> control how far the gradient extends.</p>
<p>Conic gradients, introduced with <code>conic-gradient()</code>, rotate color transitions around a center point rather than radiating outward. This produces pie-chart-like segments and color wheels. The <code>from</code> keyword sets the starting angle, and the <code>at</code> keyword sets the center position. Conic gradients are particularly effective for creating progress indicators, color wheels, and decorative radial patterns. Combined with <code>border-radius: 50%</code>, a conic gradient can produce a smooth color wheel with a single line of CSS.</p>

<h2>Using Gradients in Web Design</h2>
<p>Gradients serve several practical roles in web design beyond decoration. They create depth and visual hierarchy when used as section backgrounds, pulling the user's attention toward content. Subtle gradients on cards and buttons convey dimensionality without the weight of drop shadows. Dark-to-transparent gradients layered over hero images improve text readability without fully obscuring the background photo.</p>
<p>Performance is one of the key advantages. Because gradients are rendered by the browser's painting engine, they require no network request and scale to any screen density. A gradient background adds effectively zero kilobytes to your page weight, compared to a raster image that might be 50-200KB. For responsive designs, gradients eliminate the need for multiple resolution-specific background images.</p>
<p>When combining gradients with other techniques, you can layer multiple gradient values in a single <code>background</code> declaration, separating them with commas. This opens up patterns like mesh gradients, noise overlays, and complex geometric backgrounds. The <code>background-blend-mode</code> property adds another dimension, allowing gradients to interact with each other and with background images through blend modes like <code>multiply</code>, <code>screen</code>, and <code>overlay</code>.</p>

<h2>Browser Support for CSS Gradients</h2>
<p>Linear and radial gradients have been supported in all major browsers since 2012. Internet Explorer 10 was the last browser to add support, and with IE's end-of-life in June 2022, vendor prefixes for gradients are no longer strictly necessary. Conic gradients reached broad support in 2020 with Safari 12.1, Chrome 69, and Firefox 83. As of March 2026, all modern browsers support all three gradient types without prefixes.</p>
<p>If you need to support older environments, this tool includes a vendor prefix toggle that adds <code>-webkit-</code> prefixed versions of your gradient. The <code>-moz-</code> prefix is no longer needed since Firefox dropped it after version 16. For truly legacy browsers, providing a solid fallback color before the gradient declaration ensures the element remains visible even when gradient support is absent.</p>

<div class="cg-faq" itemscope itemtype="https://schema.org/FAQPage">
<h2>Frequently Asked Questions</h2>

<div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How do I use the generated CSS on my website?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Click the "Copy CSS" button to copy the generated gradient code to your clipboard. Then paste it into your CSS file as a property of the element you want to style. The most common usage is as a background property, like <code>background: linear-gradient(90deg, #6C5CE7, #00ff88);</code> applied to a div, section, or body element. You can also use it for border-image, list-style-image, or anywhere CSS accepts an image value.</p>
</div>
</div>

<div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is the difference between linear, radial, and conic gradients?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Linear gradients transition colors along a straight line at a specified angle. Radial gradients emanate from a center point outward in a circle or ellipse. Conic gradients rotate colors around a center point like slices of a pie. Each type produces a distinct visual effect, and the choice depends on the design context. Linear gradients are the most common for section backgrounds, radial gradients for spotlight or vignette effects, and conic gradients for color wheels and pie-chart-like patterns.</p>
</div>
</div>

<div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Can I add more than two colors to a gradient?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Yes. CSS gradients support any number of color stops. This tool allows up to 10 stops per gradient. Click "Add Stop" to insert additional colors, drag the handles on the color bar to reposition them, and use the color picker to change each stop's color. More color stops allow you to create complex multi-hue transitions, rainbow effects, or precise color bands.</p>
</div>
</div>

<div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Do I still need vendor prefixes for CSS gradients?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">For the vast majority of projects in 2026, vendor prefixes are unnecessary. All modern browsers support unprefixed linear-gradient, radial-gradient, and conic-gradient. However, if your analytics show traffic from very old browsers or WebView implementations, you can enable the vendor prefix toggle in this tool to add -webkit- prefixed fallbacks. The -moz- prefix has not been needed since Firefox 16.</p>
</div>
</div>

<div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How do repeating gradients work?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Repeating gradients tile the gradient pattern infinitely in both directions. The pattern's size is determined by your color stop positions. For example, a repeating-linear-gradient with stops at 0px and 20px will create a 20px-wide stripe that repeats across the entire element. This is useful for creating striped backgrounds, barber-pole effects, and progress bar animations without needing image files.</p>
</div>
</div>

</div>
</div>

<div class="cg-related">
<h2>Related Tools</h2>
<ul>
<li><a href="/tools/color-picker/">Color Picker</a> -- Extract exact hex, RGB, and HSL codes from any image</li>
<li><a href="/tools/color-palette-generator/">Color Palette Generator</a> -- Create harmonious color schemes and export as CSS</li>
<li><a href="/tools/meta-tag-generator/">Meta Tag Generator</a> -- Generate SEO meta tags for your web pages</li>
<li><a href="/tools/markdown-editor/">Markdown Editor</a> -- Write and preview Markdown with live rendering</li>
</ul>
</div>

<div class="cg-author">
<div class="cg-author-avatar">ML</div>
<div>
<div class="cg-author-name">Michael Lip</div>
<div class="cg-author-bio">Developer and tools engineer at <a href="https://zovo.one">Zovo</a>. Building free developer and productivity tools.</div>
</div>
</div>

<footer class="cg-footer">
<p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
</footer>

</div>

<script>
(function(){
"use strict";

var PRESETS = [
  {stops:[{c:"#6C5CE7",p:0},{c:"#00ff88",p:100}],angle:135,type:"linear",label:"Zovo"},
  {stops:[{c:"#667eea",p:0},{c:"#764ba2",p:100}],angle:135,type:"linear",label:"Twilight"},
  {stops:[{c:"#f093fb",p:0},{c:"#f5576c",p:100}],angle:135,type:"linear",label:"Flamingo"},
  {stops:[{c:"#4facfe",p:0},{c:"#00f2fe",p:100}],angle:135,type:"linear",label:"Sky"},
  {stops:[{c:"#43e97b",p:0},{c:"#38f9d7",p:100}],angle:135,type:"linear",label:"Mint"},
  {stops:[{c:"#fa709a",p:0},{c:"#fee140",p:100}],angle:135,type:"linear",label:"Sunrise"},
  {stops:[{c:"#a18cd1",p:0},{c:"#fbc2eb",p:100}],angle:135,type:"linear",label:"Lavender"},
  {stops:[{c:"#fccb90",p:0},{c:"#d57eeb",p:100}],angle:135,type:"linear",label:"Peach"},
  {stops:[{c:"#e0c3fc",p:0},{c:"#8ec5fc",p:100}],angle:135,type:"linear",label:"Cotton"},
  {stops:[{c:"#f5f7fa",p:0},{c:"#c3cfe2",p:100}],angle:135,type:"linear",label:"Fog"},
  {stops:[{c:"#0c0c0c",p:0},{c:"#434343",p:100}],angle:135,type:"linear",label:"Charcoal"},
  {stops:[{c:"#ff0844",p:0},{c:"#ffb199",p:100}],angle:135,type:"linear",label:"Coral"},
  {stops:[{c:"#00c6fb",p:0},{c:"#005bea",p:100}],angle:135,type:"linear",label:"Ocean"},
  {stops:[{c:"#f83600",p:0},{c:"#f9d423",p:100}],angle:135,type:"linear",label:"Fire"},
  {stops:[{c:"#b721ff",p:0},{c:"#21d4fd",p:100}],angle:135,type:"linear",label:"Neon"},
  {stops:[{c:"#09203f",p:0},{c:"#537895",p:100}],angle:135,type:"linear",label:"Midnight"},
  {stops:[{c:"#ddd6f3",p:0},{c:"#faaca8",p:100}],angle:135,type:"linear",label:"Rose"},
  {stops:[{c:"#96fbc4",p:0},{c:"#f9f586",p:100}],angle:135,type:"linear",label:"Spring"},
  {stops:[{c:"#2b5876",p:0},{c:"#4e4376",p:100}],angle:135,type:"linear",label:"Dusk"},
  {stops:[{c:"#ff6a00",p:0},{c:"#ee0979",p:100}],angle:135,type:"linear",label:"Sunset"},
  {stops:[{c:"#6C5CE7",p:0},{c:"#00ff88",p:33},{c:"#ff6b6b",p:66},{c:"#ffd93d",p:100}],angle:90,type:"linear",label:"Rainbow"},
  {stops:[{c:"#1a1a2e",p:0},{c:"#16213e",p:50},{c:"#0f3460",p:100}],angle:180,type:"linear",label:"Deep"},
  {stops:[{c:"#fc5c7d",p:0},{c:"#6a82fb",p:100}],angle:45,type:"linear",label:"Candy"},
  {stops:[{c:"#7f00ff",p:0},{c:"#e100ff",p:100}],angle:90,type:"linear",label:"Purple"}
];

var state = {
  type: "linear",
  angle: 90,
  radialShape: "ellipse",
  radialPos: "center",
  conicAngle: 0,
  conicPos: "center",
  stops: [
    {c:"#6C5CE7",p:0},
    {c:"#00ff88",p:100}
  ],
  vendor: false,
  repeating: false,
  activeStop: 0
};

var draggingIdx = -1;

function clamp(v,min,max){return Math.max(min,Math.min(max,v));}

function buildGradientCSS(){
  var stops = state.stops.slice().sort(function(a,b){return a.p-b.p;});
  var stopStr = stops.map(function(s){return s.c+" "+s.p+"%";}).join(", ");
  var fn,args;
  var rep = state.repeating?"repeating-":"";

  if(state.type==="linear"){
    fn = rep+"linear-gradient";
    args = state.angle+"deg, "+stopStr;
  } else if(state.type==="radial"){
    fn = rep+"radial-gradient";
    args = state.radialShape+" at "+state.radialPos+", "+stopStr;
  } else {
    fn = rep+"conic-gradient";
    args = "from "+state.conicAngle+"deg at "+state.conicPos+", "+stopStr;
  }

  return fn+"("+args+")";
}

function buildFullCSS(){
  var grad = buildGradientCSS();
  var lines = [];
  lines.push("background: "+state.stops[0].c+";");
  if(state.vendor){
    var webkitGrad = grad.replace(/^(repeating-)?/,function(m){return "-webkit-"+m;});
    lines.push("background: "+webkitGrad+";");
  }
  lines.push("background: "+grad+";");
  return lines;
}

function syntaxHighlight(lines){
  return lines.map(function(line){
    return line.replace(/([\w-]+)(\s*:\s*)(.*)(;)/,function(_,prop,sep,val,semi){
      return '<span class="hl-prop">'+prop+'</span><span class="hl-punc">'+sep+'</span><span class="hl-val">'+val+'</span><span class="hl-punc">'+semi+'</span>';
    });
  }).join("\n");
}

function updatePreview(){
  var grad = buildGradientCSS();
  document.getElementById("cgPreview").style.background = grad;
}

function updateStopBar(){
  var stops = state.stops.slice().sort(function(a,b){return a.p-b.p;});
  var barGrad = "linear-gradient(90deg, "+stops.map(function(s){return s.c+" "+s.p+"%";}).join(", ")+")";
  document.getElementById("cgStopBarBg").style.background = barGrad;

  // Remove old handles
  var bar = document.getElementById("cgStopBar");
  bar.querySelectorAll(".cg-stop-handle").forEach(function(h){h.remove();});

  // Add handles
  state.stops.forEach(function(stop,idx){
    var h = document.createElement("div");
    h.className = "cg-stop-handle"+(idx===state.activeStop?" active":"");
    h.style.left = stop.p+"%";
    h.style.background = stop.c;
    h.dataset.idx = idx;

    h.addEventListener("mousedown",function(e){
      e.preventDefault();
      e.stopPropagation();
      state.activeStop = idx;
      draggingIdx = idx;
      h.classList.add("dragging");
      renderStopEditors();
      updateStopBar();
    });

    bar.appendChild(h);
  });
}

function renderStopEditors(){
  var html = "";
  state.stops.forEach(function(stop,idx){
    var isActive = idx===state.activeStop?"border-color:var(--cg-primary);":"";
    html += '<div class="cg-stop-editor" style="'+isActive+'" data-idx="'+idx+'">';
    html += '<input type="color" class="cg-stop-color-input" value="'+stop.c+'" data-idx="'+idx+'" onchange="cgStopColorChange(this)">';
    html += '<input type="number" class="cg-stop-pos" value="'+stop.p+'" min="0" max="100" data-idx="'+idx+'" onchange="cgStopPosChange(this)"> <span style="color:var(--cg-text-dim);font-size:0.8rem;">%</span>';
    if(state.stops.length>2){
      html += '<span style="flex:1;"></span>';
      html += '<button class="cg-stop-delete" data-idx="'+idx+'" onclick="cgDeleteStop('+idx+')" title="Remove stop"><svg width="12" height="12" viewBox="0 0 12 12" fill="none"><path d="M2 2l8 8M10 2l-8 8" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg></button>';
    }
    html += '</div>';
  });
  document.getElementById("cgStopEditors").innerHTML = html;
}

function updateCode(){
  var lines = buildFullCSS();
  document.getElementById("cgCodeBlock").innerHTML = syntaxHighlight(lines);
}

function updateAngleDisplay(){
  document.getElementById("cgAngleVal").textContent = state.angle+"deg";
  document.getElementById("cgConicAngleVal").textContent = state.conicAngle+"deg";
}

window.cgUpdate = function(){
  state.angle = parseInt(document.getElementById("cgAngle").value,10);
  state.radialShape = document.getElementById("cgRadialShape").value;
  state.radialPos = document.getElementById("cgRadialPos").value;
  state.conicAngle = parseInt(document.getElementById("cgConicAngle").value,10);
  state.conicPos = document.getElementById("cgConicPos").value;
  updateAngleDisplay();
  updatePreview();
  updateStopBar();
  updateCode();
};

window.cgSetType = function(type,btn){
  state.type = type;
  document.querySelectorAll(".cg-type-btn").forEach(function(b){b.classList.remove("active");});
  btn.classList.add("active");
  document.getElementById("cgLinearCtrl").style.display = type==="linear"?"block":"none";
  document.getElementById("cgRadialCtrl").style.display = type==="radial"?"block":"none";
  document.getElementById("cgConicCtrl").style.display = type==="conic"?"block":"none";
  cgUpdate();
};

window.cgAddStop = function(){
  if(state.stops.length>=10) return;
  // find gap
  var sorted = state.stops.slice().sort(function(a,b){return a.p-b.p;});
  var maxGap=0, gapPos=50, gapC1=sorted[0].c, gapC2=sorted[sorted.length-1].c;
  for(var i=0;i<sorted.length-1;i++){
    var gap=sorted[i+1].p-sorted[i].p;
    if(gap>maxGap){
      maxGap=gap;
      gapPos=Math.round((sorted[i].p+sorted[i+1].p)/2);
      gapC1=sorted[i].c;
      gapC2=sorted[i+1].c;
    }
  }
  // mix colors
  var nc = mixColors(gapC1,gapC2,0.5);
  state.stops.push({c:nc,p:gapPos});
  state.activeStop = state.stops.length-1;
  cgUpdate();
  renderStopEditors();
};

function mixColors(c1,c2,t){
  var r1=parseInt(c1.slice(1,3),16),g1=parseInt(c1.slice(3,5),16),b1=parseInt(c1.slice(5,7),16);
  var r2=parseInt(c2.slice(1,3),16),g2=parseInt(c2.slice(3,5),16),b2=parseInt(c2.slice(5,7),16);
  var r=Math.round(r1+(r2-r1)*t),g=Math.round(g1+(g2-g1)*t),b=Math.round(b1+(b2-b1)*t);
  return "#"+((1<<24)+(r<<16)+(g<<8)+b).toString(16).slice(1);
}

window.cgDeleteStop = function(idx){
  if(state.stops.length<=2) return;
  state.stops.splice(idx,1);
  if(state.activeStop>=state.stops.length) state.activeStop=state.stops.length-1;
  cgUpdate();
  renderStopEditors();
};

window.cgStopColorChange = function(el){
  var idx = parseInt(el.dataset.idx,10);
  state.stops[idx].c = el.value;
  cgUpdate();
};

window.cgStopPosChange = function(el){
  var idx = parseInt(el.dataset.idx,10);
  state.stops[idx].p = clamp(parseInt(el.value,10)||0,0,100);
  cgUpdate();
};

window.cgBarClick = function(e){
  if(e.target.classList.contains("cg-stop-handle")) return;
  if(state.stops.length>=10) return;
  var bar = document.getElementById("cgStopBar");
  var rect = bar.getBoundingClientRect();
  var pct = Math.round(((e.clientX-rect.left)/rect.width)*100);
  pct = clamp(pct,0,100);
  // determine color at position by finding nearest stops
  var sorted = state.stops.slice().sort(function(a,b){return a.p-b.p;});
  var c = sorted[0].c;
  for(var i=0;i<sorted.length-1;i++){
    if(pct>=sorted[i].p && pct<=sorted[i+1].p){
      var range = sorted[i+1].p-sorted[i].p;
      var t = range>0?(pct-sorted[i].p)/range:0.5;
      c = mixColors(sorted[i].c,sorted[i+1].c,t);
      break;
    }
  }
  if(pct>sorted[sorted.length-1].p) c=sorted[sorted.length-1].c;
  state.stops.push({c:c,p:pct});
  state.activeStop = state.stops.length-1;
  cgUpdate();
  renderStopEditors();
};

window.cgToggleVendor = function(btn){
  state.vendor = !state.vendor;
  btn.classList.toggle("on",state.vendor);
  updateCode();
};

window.cgToggleRepeat = function(btn){
  state.repeating = !state.repeating;
  btn.classList.toggle("on",state.repeating);
  cgUpdate();
};

window.cgCopyCSS = function(){
  var lines = buildFullCSS();
  var text = lines.join("\n");
  navigator.clipboard.writeText(text).then(function(){
    showToast("CSS copied to clipboard");
  });
};

window.cgRandomGradient = function(){
  var numStops = 2+Math.floor(Math.random()*3);
  state.stops = [];
  for(var i=0;i<numStops;i++){
    state.stops.push({
      c: "#"+Math.floor(Math.random()*16777215).toString(16).padStart(6,"0"),
      p: Math.round((i/(numStops-1))*100)
    });
  }
  state.angle = Math.floor(Math.random()*360);
  document.getElementById("cgAngle").value = state.angle;
  state.activeStop = 0;
  cgUpdate();
  renderStopEditors();
};

function showToast(msg){
  var t = document.getElementById("cgToast");
  t.textContent = msg;
  t.classList.add("show");
  clearTimeout(t._tid);
  t._tid = setTimeout(function(){t.classList.remove("show");},1800);
}

// Drag handling
document.addEventListener("mousemove",function(e){
  if(draggingIdx<0) return;
  var bar = document.getElementById("cgStopBar");
  var rect = bar.getBoundingClientRect();
  var pct = Math.round(((e.clientX-rect.left)/rect.width)*100);
  state.stops[draggingIdx].p = clamp(pct,0,100);
  cgUpdate();
  // update position input
  var editors = document.querySelectorAll(".cg-stop-pos");
  editors.forEach(function(el){
    if(parseInt(el.dataset.idx,10)===draggingIdx) el.value=state.stops[draggingIdx].p;
  });
});

document.addEventListener("mouseup",function(){
  if(draggingIdx>=0){
    var handles = document.querySelectorAll(".cg-stop-handle");
    handles.forEach(function(h){h.classList.remove("dragging");});
    draggingIdx = -1;
  }
});

// Render presets
function renderPresets(){
  var grid = document.getElementById("cgPresetsGrid");
  var html = "";
  PRESETS.forEach(function(preset,idx){
    var stops = preset.stops.map(function(s){return s.c+" "+s.p+"%";}).join(", ");
    var grad = "linear-gradient("+(preset.angle||135)+"deg, "+stops+")";
    html += '<div class="cg-preset" style="background:'+grad+';" data-idx="'+idx+'" onclick="cgLoadPreset('+idx+')" title="'+preset.label+'"></div>';
  });
  grid.innerHTML = html;
}

window.cgLoadPreset = function(idx){
  var preset = PRESETS[idx];
  state.stops = preset.stops.map(function(s){return {c:s.c,p:s.p};});
  state.angle = preset.angle||90;
  state.type = preset.type||"linear";
  state.activeStop = 0;
  document.getElementById("cgAngle").value = state.angle;

  // Update type buttons
  document.querySelectorAll(".cg-type-btn").forEach(function(b){
    b.classList.toggle("active",b.dataset.type===state.type);
  });
  document.getElementById("cgLinearCtrl").style.display = state.type==="linear"?"block":"none";
  document.getElementById("cgRadialCtrl").style.display = state.type==="radial"?"block":"none";
  document.getElementById("cgConicCtrl").style.display = state.type==="conic"?"block":"none";

  cgUpdate();
  renderStopEditors();
};

// Init
renderPresets();
renderStopEditors();
cgUpdate();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "CSS Gradient Generator",
      "url": "https://theluckystrike.github.io/tools/css-gradient-generator/",
      "applicationCategory": "DeveloperApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19",
      "description": "Create beautiful CSS gradients with a visual editor. Generate linear, radial, and conic gradients with multiple color stops, angle control, and live preview."
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "CSS Gradient Generator", "item": "https://theluckystrike.github.io/tools/css-gradient-generator/" }
      ]
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How do I use the generated CSS on my website?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Click the Copy CSS button to copy the generated gradient code to your clipboard. Then paste it into your CSS file as a property of the element you want to style."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between linear, radial, and conic gradients?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Linear gradients transition colors along a straight line at a specified angle. Radial gradients emanate from a center point outward in a circle or ellipse. Conic gradients rotate colors around a center point like slices of a pie."
          }
        },
        {
          "@type": "Question",
          "name": "Can I add more than two colors to a gradient?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. CSS gradients support any number of color stops. This tool allows up to 10 stops per gradient. Click Add Stop to insert additional colors."
          }
        },
        {
          "@type": "Question",
          "name": "Do I still need vendor prefixes for CSS gradients?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For the vast majority of projects in 2026, vendor prefixes are unnecessary. All modern browsers support unprefixed linear-gradient, radial-gradient, and conic-gradient."
          }
        },
        {
          "@type": "Question",
          "name": "How do repeating gradients work?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Repeating gradients tile the gradient pattern infinitely in both directions. The pattern size is determined by your color stop positions."
          }
        }
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
