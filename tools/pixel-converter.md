---
layout: page
title: "Free Pixel Converter — PX to REM, EM, PT & Viewport Units | Zovo"
description: "Convert pixels to rem, em, pt, vh, vw, and percentages. Calculate DPI and PPI from physical dimensions. Print size calculator and batch conversion. Free online CSS unit converter."
permalink: /tools/pixel-converter/
keywords: "px to rem, pixel to rem, px to em, css unit converter, pixel to point, dpi calculator, ppi calculator, px to vh vw"
date: 2026-03-19
categories: [tools]
tags: [pixel, converter, rem, em, pt, viewport, dpi, ppi, css-units]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
:root{--px-primary:#6C5CE7;--px-primary-dark:#5A4BD1;--px-primary-light:#A29BFE;--px-bg:#0a0a0f;--px-surface:#12121a;--px-surface2:#1a1a28;--px-border:#1e1e2e;--px-border2:#2a2a3e;--px-text:#e0e0e0;--px-muted:#8888aa;--px-green:#00ff88;--px-green-dark:#00dd77;--px-red:#ff4757;--px-radius:12px;--px-shadow:0 4px 24px rgba(0,0,0,0.3)}
.px-wrap{font-family:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;color:var(--px-text);max-width:1100px;margin:0 auto;padding:0 16px;line-height:1.6}
.px-wrap *{box-sizing:border-box}
.px-hero{text-align:center;padding:40px 0 28px}
.px-hero h1{font-size:2.2rem;font-weight:700;color:var(--px-text);margin:0 0 16px;line-height:1.2}
.px-hero h1 span{color:var(--px-primary)}
.px-intro{font-size:1.02rem;color:var(--px-muted);max-width:700px;margin:0 auto;line-height:1.7}
.px-updated{display:inline-block;font-size:0.75rem;color:var(--px-muted);margin-top:12px;padding:4px 12px;border:1px solid var(--px-border);border-radius:20px}

/* Cards */
.px-card{background:var(--px-surface);border:1px solid var(--px-border);border-radius:var(--px-radius);padding:24px;box-shadow:var(--px-shadow);margin-bottom:16px}
.px-card h3{font-size:0.85rem;font-weight:600;color:var(--px-text);margin:0 0 16px;padding-bottom:10px;border-bottom:1px solid var(--px-border);text-transform:uppercase;letter-spacing:0.5px}

/* Grid */
.px-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:24px}
.px-grid-3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:16px;margin-bottom:16px}

/* Fields */
.px-field{margin-bottom:14px}
.px-field:last-child{margin-bottom:0}
.px-field label{display:block;font-size:0.78rem;font-weight:600;color:var(--px-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:6px}
.px-field input[type="number"],.px-field input[type="text"],.px-field select,.px-field textarea{width:100%;font-family:'Inter',sans-serif;font-size:0.9rem;padding:9px 12px;border:1.5px solid var(--px-border);border-radius:8px;background:var(--px-bg);color:var(--px-text);outline:none;transition:border-color 0.2s}
.px-field input:focus,.px-field select:focus,.px-field textarea:focus{border-color:var(--px-primary);box-shadow:0 0 0 3px rgba(108,92,231,0.15)}
.px-field select{appearance:auto}
.px-field textarea{min-height:80px;resize:vertical;font-family:'JetBrains Mono',monospace;font-size:0.82rem;line-height:1.6}

/* Result output */
.px-output{font-family:'JetBrains Mono',monospace;font-size:1.3rem;font-weight:600;color:var(--px-green);background:var(--px-bg);border:1px solid var(--px-border);border-radius:8px;padding:12px 16px;text-align:center;margin-top:8px;min-height:44px;display:flex;align-items:center;justify-content:center}
.px-output-sm{font-size:1rem}

/* Converter section */
.px-converter{display:flex;gap:12px;align-items:flex-end}
.px-converter .px-field{flex:1}
.px-arrow{display:flex;align-items:center;justify-content:center;color:var(--px-primary);font-size:1.2rem;margin-bottom:12px;flex-shrink:0}

/* Buttons */
.px-btn{display:inline-flex;align-items:center;gap:6px;padding:9px 16px;border:none;border-radius:8px;font-family:'Inter',sans-serif;font-size:0.83rem;font-weight:600;cursor:pointer;transition:all 0.15s;white-space:nowrap}
.px-btn-primary{background:var(--px-primary);color:#fff}
.px-btn-primary:hover{background:var(--px-primary-dark)}
.px-btn-green{background:var(--px-green);color:#0a0a0f;font-weight:700}
.px-btn-green:hover{background:var(--px-green-dark)}
.px-btn-outline{background:transparent;color:var(--px-primary);border:1.5px solid var(--px-primary)}
.px-btn-outline:hover{background:rgba(108,92,231,0.1)}

/* Copy feedback */
.px-copy-btn{background:none;border:1px solid var(--px-border);border-radius:6px;color:var(--px-muted);padding:4px 10px;font-size:0.72rem;font-family:'Inter',sans-serif;cursor:pointer;transition:all 0.15s;margin-left:8px}
.px-copy-btn:hover{border-color:var(--px-primary);color:var(--px-primary)}

/* Reference table */
.px-ref-table{width:100%;border-collapse:collapse}
.px-ref-table th,.px-ref-table td{padding:8px 12px;text-align:left;font-size:0.82rem;border:1px solid var(--px-border)}
.px-ref-table th{background:var(--px-surface2);color:var(--px-text);font-weight:600;font-size:0.72rem;text-transform:uppercase;letter-spacing:0.5px}
.px-ref-table td{color:var(--px-muted);font-family:'JetBrains Mono',monospace;font-size:0.8rem}
.px-ref-table tr:hover td{background:var(--px-surface2)}

/* Batch output */
.px-batch-output{font-family:'JetBrains Mono',monospace;font-size:0.82rem;color:var(--px-green);background:var(--px-bg);border:1px solid var(--px-border);border-radius:8px;padding:12px 16px;min-height:80px;white-space:pre-wrap;line-height:1.8}

/* Cross links */
.px-cross-links{display:flex;flex-wrap:wrap;gap:8px;margin-top:32px}
.px-cross-link{display:inline-block;padding:8px 16px;background:var(--px-surface);border:1px solid var(--px-border);border-radius:8px;color:var(--px-muted);font-size:0.82rem;text-decoration:none;transition:border-color 0.15s,color 0.15s}
.px-cross-link:hover{border-color:var(--px-primary);color:var(--px-text)}

/* Content */
.px-content{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--px-border)}
.px-content h2{font-size:1.4rem;font-weight:700;color:var(--px-text);margin:32px 0 12px}
.px-content h2:first-child{margin-top:0}
.px-content p{font-size:0.95rem;color:var(--px-muted);line-height:1.75;margin:0 0 14px}
.px-content ul,.px-content ol{margin:0 0 14px;padding-left:20px;color:var(--px-muted);font-size:0.95rem;line-height:1.75}
.px-content ul li,.px-content ol li{margin-bottom:6px}
.px-content code{font-family:'JetBrains Mono',monospace;font-size:0.85rem;background:var(--px-surface);padding:2px 6px;border-radius:4px;color:var(--px-primary-light)}
.px-content table{width:100%;border-collapse:collapse;margin:0 0 14px}
.px-content th,.px-content td{padding:10px 14px;text-align:left;font-size:0.88rem;border:1px solid var(--px-border)}
.px-content th{background:var(--px-surface);color:var(--px-text);font-weight:600;font-size:0.78rem;text-transform:uppercase;letter-spacing:0.5px}
.px-content td{color:var(--px-muted)}

/* FAQ */
.px-faq{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--px-border)}
.px-faq h2{font-size:1.4rem;font-weight:700;color:var(--px-text);margin:0 0 20px}
.px-faq-item{border:1px solid var(--px-border);border-radius:var(--px-radius);padding:18px 22px;margin-bottom:12px;background:var(--px-surface)}
.px-faq-item h3{font-size:1rem;font-weight:600;margin:0 0 8px;color:var(--px-text)}
.px-faq-item p{margin:0;font-size:0.92rem;color:var(--px-muted);line-height:1.7}

/* Author */
.px-author-box{display:flex;gap:16px;align-items:center;padding:20px;background:var(--px-surface);border:1px solid var(--px-border);border-radius:var(--px-radius);margin-top:32px;max-width:820px;margin-left:auto;margin-right:auto}
.px-author-avatar{width:56px;height:56px;border-radius:50%;background:var(--px-primary);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:1.1rem;color:#fff;flex-shrink:0}
.px-author-info{flex:1}
.px-author-name{font-size:0.95rem;font-weight:600;color:var(--px-text);margin:0 0 4px}
.px-author-bio{font-size:0.82rem;color:var(--px-muted);margin:0;line-height:1.6}

/* Footer */
.px-footer{text-align:center;padding:24px 0 8px;margin-top:32px;border-top:1px solid var(--px-border);max-width:820px;margin-left:auto;margin-right:auto}
.px-footer p{font-size:0.8rem;color:var(--px-muted);margin:0}
.px-footer a{color:var(--px-primary);text-decoration:none}
.px-footer a:hover{text-decoration:underline}

/* Responsive */
@media(max-width:768px){
.px-hero h1{font-size:1.6rem}
.px-grid,.px-grid-3{grid-template-columns:1fr}
.px-converter{flex-direction:column}
.px-arrow{transform:rotate(90deg);margin:0}
.px-author-box{flex-direction:column;align-items:center;text-align:center}
}
</style>

<div class="px-wrap" id="pxApp">

<div class="px-hero">
<h1>Free <span>Pixel Converter</span></h1>
<p class="px-intro">Convert pixels to rem, em, pt, viewport units, and percentages. Calculate DPI and PPI from physical dimensions. Batch convert multiple values at once. All calculations run in your browser.</p>
<div class="px-updated">Last updated: March 19, 2026</div>
</div>

<!-- Main converter grid -->
<div class="px-grid">

<!-- PX to REM -->
<div class="px-card">
<h3>PX to REM</h3>
<div class="px-field">
<label for="pxRemInput">Pixels</label>
<input type="number" id="pxRemInput" value="16" min="0" step="any">
</div>
<div class="px-field">
<label for="pxRemBase">Base Font Size (px)</label>
<input type="number" id="pxRemBase" value="16" min="1" step="any">
</div>
<div class="px-output" id="pxRemOutput">1rem</div>
</div>

<!-- PX to EM -->
<div class="px-card">
<h3>PX to EM</h3>
<div class="px-field">
<label for="pxEmInput">Pixels</label>
<input type="number" id="pxEmInput" value="24" min="0" step="any">
</div>
<div class="px-field">
<label for="pxEmParent">Parent Font Size (px)</label>
<input type="number" id="pxEmParent" value="16" min="1" step="any">
</div>
<div class="px-output" id="pxEmOutput">1.5em</div>
</div>

<!-- PX to PT -->
<div class="px-card">
<h3>PX to PT</h3>
<div class="px-field">
<label for="pxPtInput">Pixels</label>
<input type="number" id="pxPtInput" value="16" min="0" step="any">
</div>
<div class="px-field">
<label for="pxPtDpi">Screen DPI</label>
<input type="number" id="pxPtDpi" value="96" min="1" step="any">
</div>
<div class="px-output" id="pxPtOutput">12pt</div>
</div>

<!-- PX to Viewport -->
<div class="px-card">
<h3>PX to Viewport Units</h3>
<div class="px-field">
<label for="pxVwInput">Pixels</label>
<input type="number" id="pxVwInput" value="192" min="0" step="any">
</div>
<div class="px-grid" style="gap:8px;margin-bottom:0">
<div class="px-field">
<label for="pxVwWidth">Viewport Width</label>
<input type="number" id="pxVwWidth" value="1920" min="1" step="1">
</div>
<div class="px-field">
<label for="pxVwHeight">Viewport Height</label>
<input type="number" id="pxVwHeight" value="1080" min="1" step="1">
</div>
</div>
<div class="px-output px-output-sm" id="pxVwOutput">10vw / 17.78vh</div>
</div>

<!-- PX to Percentage -->
<div class="px-card">
<h3>PX to Percentage</h3>
<div class="px-field">
<label for="pxPctInput">Pixels</label>
<input type="number" id="pxPctInput" value="480" min="0" step="any">
</div>
<div class="px-field">
<label for="pxPctParent">Parent Width (px)</label>
<input type="number" id="pxPctParent" value="1920" min="1" step="any">
</div>
<div class="px-output" id="pxPctOutput">25%</div>
</div>

<!-- DPI/PPI Calculator -->
<div class="px-card">
<h3>DPI / PPI Calculator</h3>
<div class="px-grid" style="gap:8px;margin-bottom:8px">
<div class="px-field">
<label for="pxDpiW">Width (px)</label>
<input type="number" id="pxDpiW" value="2560" min="1" step="1">
</div>
<div class="px-field">
<label for="pxDpiH">Height (px)</label>
<input type="number" id="pxDpiH" value="1440" min="1" step="1">
</div>
</div>
<div class="px-field">
<label for="pxDpiDiag">Screen Diagonal (inches)</label>
<input type="number" id="pxDpiDiag" value="27" min="0.1" step="any">
</div>
<div class="px-output" id="pxDpiOutput">109 PPI</div>
</div>

</div>

<!-- Print Size Calculator -->
<div class="px-card">
<h3>Print Size Calculator</h3>
<p style="font-size:0.85rem;color:var(--px-muted);margin:0 0 14px;">Enter pixel dimensions and DPI to calculate the physical print size.</p>
<div class="px-grid-3">
<div class="px-field">
<label for="pxPrintW">Width (px)</label>
<input type="number" id="pxPrintW" value="3000" min="1" step="1">
</div>
<div class="px-field">
<label for="pxPrintH">Height (px)</label>
<input type="number" id="pxPrintH" value="2000" min="1" step="1">
</div>
<div class="px-field">
<label for="pxPrintDpi">DPI</label>
<input type="number" id="pxPrintDpi" value="300" min="1" step="1">
</div>
</div>
<div class="px-grid" style="margin-bottom:0">
<div class="px-output px-output-sm" id="pxPrintInches">10 x 6.67 inches</div>
<div class="px-output px-output-sm" id="pxPrintCm">25.4 x 16.93 cm</div>
</div>
</div>

<!-- Reference Table -->
<div class="px-card">
<h3>Common Conversions (Base: 16px)</h3>
<div style="overflow-x:auto">
<table class="px-ref-table">
<thead>
<tr><th>PX</th><th>REM</th><th>EM</th><th>PT</th><th>% of 1920</th></tr>
</thead>
<tbody id="pxRefBody"></tbody>
</table>
</div>
</div>

<!-- Batch Converter -->
<div class="px-card">
<h3>Batch Converter</h3>
<p style="font-size:0.85rem;color:var(--px-muted);margin:0 0 14px;">Paste multiple pixel values (one per line or comma-separated) to convert them all at once.</p>
<div class="px-grid">
<div>
<div class="px-field">
<label for="pxBatchInput">Pixel Values</label>
<textarea id="pxBatchInput" placeholder="12&#10;14&#10;16&#10;18&#10;24&#10;32&#10;48">12
14
16
18
24
32
48</textarea>
</div>
<div class="px-grid" style="gap:8px;margin-bottom:8px">
<div class="px-field">
<label for="pxBatchTarget">Convert To</label>
<select id="pxBatchTarget">
<option value="rem">REM</option>
<option value="em">EM</option>
<option value="pt">PT</option>
<option value="vw">VW</option>
<option value="vh">VH</option>
<option value="pct">%</option>
</select>
</div>
<div class="px-field">
<label for="pxBatchBase">Base / Reference</label>
<input type="number" id="pxBatchBase" value="16" min="1" step="any">
</div>
</div>
<button class="px-btn px-btn-primary" id="pxBatchBtn" style="width:100%">Convert All</button>
</div>
<div>
<div class="px-field">
<label>Results <button class="px-copy-btn" id="pxBatchCopy">Copy</button></label>
<div class="px-batch-output" id="pxBatchOutput"></div>
</div>
</div>
</div>
</div>

<!-- Cross Links -->
<div class="px-cross-links">
<a href="/tools/unit-converter/" class="px-cross-link">Unit Converter</a>
<a href="/tools/css-gradient-generator/" class="px-cross-link">CSS Gradient Generator</a>
<a href="/tools/color-palette-generator/" class="px-cross-link">Color Palette Generator</a>
<a href="/tools/aspect-ratio-calculator/" class="px-cross-link">Aspect Ratio Calculator</a>
</div>

<!-- SEO Content -->
<div class="px-content">

<h2>What Are CSS Units</h2>

<p>CSS uses two categories of units: absolute and relative. Absolute units have a fixed size regardless of context. The pixel (px) is the most common absolute unit on screens, and the point (pt) is the standard in print. Relative units scale based on a reference value. REM is relative to the root font size. EM is relative to the parent element's font size. Viewport units (vw, vh) are relative to the browser window dimensions. Percentages are relative to the parent element's size.</p>

<p>Choosing between these units affects how a layout responds to user settings and device differences. A heading set to 32px will always render at 32px, even if the user has changed their browser's default font size. The same heading set to 2rem will scale proportionally when the user adjusts their base font size from 16px to 20px, growing from 32px to 40px. This distinction is central to building accessible, responsive interfaces.</p>

<p>The pixel itself is not as straightforward as it once was. On standard displays, 1 CSS pixel maps to 1 physical device pixel. On high-DPI (Retina) screens, 1 CSS pixel may map to 2 or 3 physical pixels. The browser handles this mapping through the device pixel ratio, so CSS pixels remain a consistent reference point for layout regardless of screen density.</p>

<h2>Understanding PX, REM, and EM</h2>

<p>The pixel (px) is the baseline unit for screen design. It provides predictable, consistent sizing. When you set an element to 400px wide, it is 400px wide on every screen (in CSS terms). The drawback is rigidity. Pixel values do not respond to user preferences or scale with context, which can create accessibility problems for users who rely on larger text sizes.</p>

<p>REM stands for "root em." It is calculated relative to the <code>html</code> element's font size. Most browsers default to 16px, so 1rem = 16px by default. The conversion formula is straightforward: rem = px / base. A 24px value at 16px base = 1.5rem. A 14px value = 0.875rem. The advantage of REM is that changing the root font size scales every REM-based measurement proportionally across the entire page. This makes responsive typography and spacing efficient to maintain.</p>

<p>EM works like REM but references the parent element's font size rather than the root. If a paragraph has a font size of 18px and you set its padding to 1em, the padding is 18px. If a child element inside that paragraph also uses EM, it references the paragraph's computed font size. This cascading behavior makes EM powerful for component-level scaling but harder to predict in deeply nested structures. In practice, many developers use REM for global sizing and EM for local, component-relative spacing.</p>

<p>Points (pt) originate from traditional typography. One point equals 1/72 of an inch. At the standard screen resolution of 96 DPI, 1pt = 1.333px (or equivalently, 1px = 0.75pt). Points are primarily used in print stylesheets and PDF generation. For screen design, pixels and REM are more appropriate.</p>

<h2>DPI vs PPI</h2>

<p>DPI (dots per inch) and PPI (pixels per inch) are often used interchangeably, but they refer to different things. PPI measures the pixel density of a screen. A 27-inch monitor with a 2560x1440 resolution has approximately 109 PPI. Higher PPI means sharper images because more pixels are packed into each inch of display area.</p>

<p>DPI measures the dot density of a printed output. A 300 DPI printer places 300 individual dots of ink per inch. For high-quality photo printing, 300 DPI is the standard minimum. Everyday documents print acceptably at 150 DPI. Billboard and large-format printing can drop to 72 DPI or lower because the viewing distance is greater.</p>

<p>The PPI of a screen determines how crisp text and images appear. A 24-inch 1080p monitor has about 92 PPI. The same resolution on a 15.6-inch laptop screen yields about 141 PPI. Apple's Retina displays typically exceed 200 PPI (a 14-inch MacBook Pro at 3024x1964 hits approximately 254 PPI). Android flagships often reach 400+ PPI.</p>

<p>To calculate PPI, find the diagonal pixel count using the Pythagorean theorem (square root of width squared plus height squared) and divide by the physical diagonal in inches. The calculator above handles this arithmetic.</p>

<h2>Choosing the Right CSS Unit</h2>

<p>Use px for borders, shadows, and fixed-layout elements where precise pixel control matters. A 1px border should stay 1px. A box-shadow offset of 4px 4px is intentionally exact.</p>

<p>Use rem for font sizes, margins, and padding in most cases. This ensures your layout respects the user's font size preference and scales uniformly. Set the root font size once (on the html element) and everything else adjusts proportionally.</p>

<p>Use em for component-internal spacing that should scale with the component's own font size. A button that uses 0.75em padding will maintain proportional padding whether the button text is 14px or 20px.</p>

<p>Use vw and vh for full-screen layouts, hero sections, and elements that should relate to the viewport. A hero banner set to 100vh fills the viewport height. A section width of 50vw takes half the browser width. Combine viewport units with clamp() or min/max functions to prevent extreme sizes on very small or very large screens.</p>

<p>Use percentages for fluid widths within a container. A child element set to 50% takes half of its parent's width, regardless of the parent's pixel size. This is the foundation of flexible grid systems.</p>

</div>

<!-- FAQ -->
<div class="px-faq" itemscope itemtype="https://schema.org/FAQPage">

<h2>Frequently Asked Questions</h2>

<div class="px-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How do I convert px to rem?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Divide the pixel value by the root font size. With the default browser font size of 16px, 24px becomes 24 / 16 = 1.5rem. If you have set a different root font size (for example, 10px using the 62.5% technique), divide by that value instead. The converter above lets you adjust the base font size to match your project's configuration.</p>
</div>
</div>

<div class="px-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is the difference between rem and em?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">REM is always relative to the root (html) element's font size. EM is relative to the font size of the current element's parent. If you nest elements that each use EM-based sizing, the computed size compounds at each level, which can lead to unexpected results. REM avoids this compounding because it always refers back to a single root value, making it more predictable for page-wide sizing.</p>
</div>
</div>

<div class="px-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What DPI should I use for printing?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">For high-quality photo prints and professional publications, use 300 DPI. For standard office documents and reports, 150 DPI is sufficient. For large-format prints like banners and posters viewed from several feet away, 72-150 DPI works well because the viewing distance compensates for the lower resolution. Use the print size calculator above to check whether your image has enough pixels for your target print size and DPI.</p>
</div>
</div>

<div class="px-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Why do designers use a 16px base font size?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">16px is the default font size in all major browsers (Chrome, Firefox, Safari, Edge). Using 16px as the base means that 1rem = 16px without any custom configuration. This convention makes REM calculations straightforward: 12px = 0.75rem, 14px = 0.875rem, 18px = 1.125rem, 24px = 1.5rem, 32px = 2rem. Some developers set the html font size to 62.5% (10px) to make the math easier (1rem = 10px), but this requires explicitly setting body text back to 1.6rem to maintain readable size.</p>
</div>
</div>

<div class="px-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How do viewport units (vw and vh) work?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">1vw equals 1% of the viewport width. 1vh equals 1% of the viewport height. On a 1920px wide browser window, 10vw = 192px. On a 1080px tall window, 50vh = 540px. Viewport units resize dynamically as the browser window changes size. They are useful for full-screen sections, responsive typography (often combined with clamp()), and layouts that need to fill the visible area precisely.</p>
</div>
</div>

</div>

<!-- Author Box -->
<div class="px-author-box">
<div class="px-author-avatar">ML</div>
<div class="px-author-info">
<p class="px-author-name">Michael Lip</p>
<p class="px-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
</div>
</div>

<footer class="px-footer">
<p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
</footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Free Pixel Converter",
      "url": "https://theluckystrike.github.io/tools/pixel-converter/",
      "applicationCategory": "DeveloperApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "description": "Convert pixels to rem, em, pt, vh, vw, and percentages. Calculate DPI and PPI from physical dimensions. Print size calculator and batch conversion.",
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Pixel Converter", "item": "https://theluckystrike.github.io/tools/pixel-converter/" }
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
          "name": "How do I convert px to rem?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Divide the pixel value by the root font size. With the default browser font size of 16px, 24px becomes 24 / 16 = 1.5rem. If you have set a different root font size, divide by that value instead."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between rem and em?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "REM is always relative to the root (html) element's font size. EM is relative to the font size of the current element's parent. REM avoids compounding because it always refers back to a single root value."
          }
        },
        {
          "@type": "Question",
          "name": "What DPI should I use for printing?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For high-quality photo prints, use 300 DPI. For standard documents, 150 DPI is sufficient. For large-format prints viewed from a distance, 72-150 DPI works well."
          }
        },
        {
          "@type": "Question",
          "name": "Why do designers use a 16px base font size?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "16px is the default font size in all major browsers. Using 16px as the base means 1rem = 16px without any custom configuration, making REM calculations straightforward."
          }
        },
        {
          "@type": "Question",
          "name": "How do viewport units (vw and vh) work?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "1vw equals 1% of the viewport width. 1vh equals 1% of the viewport height. On a 1920px wide browser window, 10vw = 192px. They resize dynamically as the browser window changes size."
          }
        }
      ]
    }
  ]
}
</script>

<script>
(function(){
"use strict";

// ===== Utility =====
function round(n, d) {
  if (typeof d === "undefined") d = 4;
  var f = Math.pow(10, d);
  return Math.round(n * f) / f;
}

function stripTrailingZeros(s) {
  if (s.indexOf(".") === -1) return s;
  return s.replace(/\.?0+$/, "");
}

function fmt(n, d) {
  if (typeof d === "undefined") d = 4;
  return stripTrailingZeros(round(n, d).toFixed(d));
}

// ===== PX to REM =====
var remInput = document.getElementById("pxRemInput");
var remBase = document.getElementById("pxRemBase");
var remOutput = document.getElementById("pxRemOutput");

function calcRem() {
  var px = parseFloat(remInput.value);
  var base = parseFloat(remBase.value);
  if (isNaN(px) || isNaN(base) || base <= 0) { remOutput.textContent = "-"; return; }
  remOutput.textContent = fmt(px / base) + "rem";
}

remInput.addEventListener("input", calcRem);
remBase.addEventListener("input", calcRem);

// ===== PX to EM =====
var emInput = document.getElementById("pxEmInput");
var emParent = document.getElementById("pxEmParent");
var emOutput = document.getElementById("pxEmOutput");

function calcEm() {
  var px = parseFloat(emInput.value);
  var parent = parseFloat(emParent.value);
  if (isNaN(px) || isNaN(parent) || parent <= 0) { emOutput.textContent = "-"; return; }
  emOutput.textContent = fmt(px / parent) + "em";
}

emInput.addEventListener("input", calcEm);
emParent.addEventListener("input", calcEm);

// ===== PX to PT =====
var ptInput = document.getElementById("pxPtInput");
var ptDpi = document.getElementById("pxPtDpi");
var ptOutput = document.getElementById("pxPtOutput");

function calcPt() {
  var px = parseFloat(ptInput.value);
  var dpi = parseFloat(ptDpi.value);
  if (isNaN(px) || isNaN(dpi) || dpi <= 0) { ptOutput.textContent = "-"; return; }
  // 1pt = 1/72 inch, so pt = px * 72 / dpi
  var pt = px * 72 / dpi;
  ptOutput.textContent = fmt(pt) + "pt";
}

ptInput.addEventListener("input", calcPt);
ptDpi.addEventListener("input", calcPt);

// ===== PX to Viewport =====
var vwInput = document.getElementById("pxVwInput");
var vwWidth = document.getElementById("pxVwWidth");
var vwHeight = document.getElementById("pxVwHeight");
var vwOutput = document.getElementById("pxVwOutput");

function calcVw() {
  var px = parseFloat(vwInput.value);
  var vpw = parseFloat(vwWidth.value);
  var vph = parseFloat(vwHeight.value);
  if (isNaN(px) || isNaN(vpw) || isNaN(vph) || vpw <= 0 || vph <= 0) { vwOutput.textContent = "-"; return; }
  var vw = (px / vpw) * 100;
  var vh = (px / vph) * 100;
  vwOutput.textContent = fmt(vw, 2) + "vw / " + fmt(vh, 2) + "vh";
}

vwInput.addEventListener("input", calcVw);
vwWidth.addEventListener("input", calcVw);
vwHeight.addEventListener("input", calcVw);

// ===== PX to Percentage =====
var pctInput = document.getElementById("pxPctInput");
var pctParent = document.getElementById("pxPctParent");
var pctOutput = document.getElementById("pxPctOutput");

function calcPct() {
  var px = parseFloat(pctInput.value);
  var parent = parseFloat(pctParent.value);
  if (isNaN(px) || isNaN(parent) || parent <= 0) { pctOutput.textContent = "-"; return; }
  pctOutput.textContent = fmt((px / parent) * 100, 2) + "%";
}

pctInput.addEventListener("input", calcPct);
pctParent.addEventListener("input", calcPct);

// ===== DPI/PPI Calculator =====
var dpiW = document.getElementById("pxDpiW");
var dpiH = document.getElementById("pxDpiH");
var dpiDiag = document.getElementById("pxDpiDiag");
var dpiOutput = document.getElementById("pxDpiOutput");

function calcDpi() {
  var w = parseFloat(dpiW.value);
  var h = parseFloat(dpiH.value);
  var diag = parseFloat(dpiDiag.value);
  if (isNaN(w) || isNaN(h) || isNaN(diag) || w <= 0 || h <= 0 || diag <= 0) { dpiOutput.textContent = "-"; return; }
  var diagPx = Math.sqrt(w * w + h * h);
  var ppi = diagPx / diag;
  dpiOutput.textContent = Math.round(ppi) + " PPI";
}

dpiW.addEventListener("input", calcDpi);
dpiH.addEventListener("input", calcDpi);
dpiDiag.addEventListener("input", calcDpi);

// ===== Print Size Calculator =====
var printW = document.getElementById("pxPrintW");
var printH = document.getElementById("pxPrintH");
var printDpi = document.getElementById("pxPrintDpi");
var printInches = document.getElementById("pxPrintInches");
var printCm = document.getElementById("pxPrintCm");

function calcPrint() {
  var w = parseFloat(printW.value);
  var h = parseFloat(printH.value);
  var dpi = parseFloat(printDpi.value);
  if (isNaN(w) || isNaN(h) || isNaN(dpi) || w <= 0 || h <= 0 || dpi <= 0) {
    printInches.textContent = "-";
    printCm.textContent = "-";
    return;
  }
  var inW = w / dpi;
  var inH = h / dpi;
  var cmW = inW * 2.54;
  var cmH = inH * 2.54;
  printInches.textContent = fmt(inW, 2) + " x " + fmt(inH, 2) + " inches";
  printCm.textContent = fmt(cmW, 2) + " x " + fmt(cmH, 2) + " cm";
}

printW.addEventListener("input", calcPrint);
printH.addEventListener("input", calcPrint);
printDpi.addEventListener("input", calcPrint);

// ===== Reference Table =====
var refBody = document.getElementById("pxRefBody");
var refValues = [8, 10, 12, 14, 16, 18, 20, 24, 28, 32, 36, 40, 48, 56, 64, 72, 80, 96];

function buildRefTable() {
  refBody.innerHTML = "";
  for (var i = 0; i < refValues.length; i++) {
    var px = refValues[i];
    var tr = document.createElement("tr");

    var tdPx = document.createElement("td");
    tdPx.textContent = px + "px";
    tr.appendChild(tdPx);

    var tdRem = document.createElement("td");
    tdRem.textContent = fmt(px / 16) + "rem";
    tr.appendChild(tdRem);

    var tdEm = document.createElement("td");
    tdEm.textContent = fmt(px / 16) + "em";
    tr.appendChild(tdEm);

    var tdPt = document.createElement("td");
    tdPt.textContent = fmt(px * 72 / 96) + "pt";
    tr.appendChild(tdPt);

    var tdPct = document.createElement("td");
    tdPct.textContent = fmt((px / 1920) * 100, 2) + "%";
    tr.appendChild(tdPct);

    refBody.appendChild(tr);
  }
}

// ===== Batch Converter =====
var batchInput = document.getElementById("pxBatchInput");
var batchTarget = document.getElementById("pxBatchTarget");
var batchBase = document.getElementById("pxBatchBase");
var batchBtn = document.getElementById("pxBatchBtn");
var batchOutput = document.getElementById("pxBatchOutput");
var batchCopy = document.getElementById("pxBatchCopy");

function doBatch() {
  var raw = batchInput.value.trim();
  if (!raw) { batchOutput.textContent = ""; return; }

  var values = raw.split(/[\n,]+/).map(function(s) { return s.trim(); }).filter(function(s) { return s.length > 0; });
  var target = batchTarget.value;
  var base = parseFloat(batchBase.value) || 16;
  var lines = [];

  for (var i = 0; i < values.length; i++) {
    var px = parseFloat(values[i].replace(/px$/i, ""));
    if (isNaN(px)) {
      lines.push(values[i] + " -> invalid");
      continue;
    }

    var result;
    var unit;
    if (target === "rem") {
      result = px / base;
      unit = "rem";
    } else if (target === "em") {
      result = px / base;
      unit = "em";
    } else if (target === "pt") {
      result = px * 72 / 96;
      unit = "pt";
    } else if (target === "vw") {
      result = (px / base) * 100;
      unit = "vw";
    } else if (target === "vh") {
      result = (px / base) * 100;
      unit = "vh";
    } else if (target === "pct") {
      result = (px / base) * 100;
      unit = "%";
    }

    lines.push(px + "px -> " + fmt(result) + unit);
  }

  batchOutput.textContent = lines.join("\n");
}

batchBtn.addEventListener("click", doBatch);

// Update batch base label based on target
batchTarget.addEventListener("change", function() {
  var label = batchBase.parentNode.querySelector("label");
  var t = batchTarget.value;
  if (t === "rem" || t === "em") {
    label.textContent = "Base Font Size (px)";
    batchBase.value = 16;
  } else if (t === "pt") {
    label.textContent = "DPI";
    batchBase.value = 96;
  } else if (t === "vw") {
    label.textContent = "Viewport Width (px)";
    batchBase.value = 1920;
  } else if (t === "vh") {
    label.textContent = "Viewport Height (px)";
    batchBase.value = 1080;
  } else if (t === "pct") {
    label.textContent = "Parent Width (px)";
    batchBase.value = 1920;
  }
});

// Copy batch results
batchCopy.addEventListener("click", function() {
  var text = batchOutput.textContent;
  if (!text) return;
  if (navigator.clipboard && navigator.clipboard.writeText) {
    navigator.clipboard.writeText(text).then(function() {
      batchCopy.textContent = "Copied";
      setTimeout(function() { batchCopy.textContent = "Copy"; }, 1500);
    });
  } else {
    var ta = document.createElement("textarea");
    ta.value = text;
    document.body.appendChild(ta);
    ta.select();
    document.execCommand("copy");
    document.body.removeChild(ta);
    batchCopy.textContent = "Copied";
    setTimeout(function() { batchCopy.textContent = "Copy"; }, 1500);
  }
});

// ===== Init =====
calcRem();
calcEm();
calcPt();
calcVw();
calcPct();
calcDpi();
calcPrint();
buildRefTable();
doBatch();

})();
</script>
