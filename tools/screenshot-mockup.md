---
layout: page
title: "Free Screenshot Mockup Generator — Browser, Phone & Laptop Frames | Zovo"
description: "Create beautiful screenshot mockups with browser, phone, laptop, and tablet frames. Add backgrounds, shadows, and padding. Free online mockup generator with PNG download."
permalink: /tools/screenshot-mockup/
keywords: "screenshot mockup, mockup generator, browser mockup, phone mockup, laptop mockup, screenshot frame, app screenshot, product mockup"
date: 2026-03-19
categories: [tools]
tags: [screenshot, mockup, browser, phone, design, presentation, marketing]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root{--sm-primary:#6C5CE7;--sm-primary-dark:#5A4BD1;--sm-primary-light:#A29BFE;--sm-green:#00ff88;--sm-green-dark:#00dd77;--sm-bg:#0a0a0f;--sm-surface:#12121a;--sm-surface2:#1a1a28;--sm-border:#1e1e2e;--sm-border2:#2a2a3e;--sm-text:#e0e0e0;--sm-muted:#8888aa;--sm-radius:12px;--sm-red:#ff4757}
.sm-wrap{font-family:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;color:var(--sm-text);max-width:1200px;margin:0 auto;padding:0 16px;line-height:1.6}
.sm-wrap *{box-sizing:border-box}
.sm-hero{text-align:center;padding:40px 0 28px}
.sm-hero h1{font-size:2.2rem;font-weight:700;color:var(--sm-text);margin:0 0 16px;line-height:1.2}
.sm-hero h1 span{color:var(--sm-primary)}
.sm-intro{font-size:1.02rem;color:var(--sm-muted);max-width:700px;margin:0 auto;line-height:1.7}

/* App Layout */
.sm-app{display:grid;grid-template-columns:320px 1fr;gap:24px;margin-bottom:32px}
.sm-sidebar{display:flex;flex-direction:column;gap:16px}

/* Panels */
.sm-panel{background:var(--sm-surface);border:1px solid var(--sm-border);border-radius:var(--sm-radius);padding:18px}
.sm-panel h3{font-size:0.85rem;font-weight:600;color:var(--sm-text);margin:0 0 14px;padding-bottom:10px;border-bottom:1px solid var(--sm-border)}
.sm-field{margin-bottom:14px}
.sm-field:last-child{margin-bottom:0}
.sm-field label{display:block;font-size:0.72rem;font-weight:600;color:var(--sm-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:5px}
.sm-field select,.sm-field input[type="text"],.sm-field input[type="number"]{width:100%;font-family:'Inter',sans-serif;font-size:0.85rem;padding:8px 10px;border:1.5px solid var(--sm-border);border-radius:8px;background:var(--sm-bg);color:var(--sm-text);outline:none;transition:border-color 0.2s}
.sm-field select:focus,.sm-field input:focus{border-color:var(--sm-primary);box-shadow:0 0 0 3px rgba(108,92,231,0.15)}
.sm-field select{appearance:auto}

/* Color input */
.sm-color-row{display:flex;gap:6px;align-items:center}
.sm-color-input{width:38px;height:32px;border:1.5px solid var(--sm-border);border-radius:6px;cursor:pointer;padding:2px;background:var(--sm-bg)}
.sm-color-hex{flex:1;font-family:'JetBrains Mono',monospace;font-size:0.8rem;padding:7px 8px;border:1.5px solid var(--sm-border);border-radius:6px;background:var(--sm-bg);color:var(--sm-text);outline:none}

/* Slider */
.sm-slider-row label{display:flex;justify-content:space-between;font-size:0.72rem;font-weight:600;color:var(--sm-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:5px}
.sm-slider-row label span{color:var(--sm-primary);font-weight:700;font-family:'JetBrains Mono',monospace}
.sm-slider-row input[type="range"]{width:100%;accent-color:var(--sm-primary);height:5px;cursor:pointer}

/* Checkbox */
.sm-check-row{display:flex;align-items:center;gap:8px;margin-top:4px}
.sm-check-row input[type="checkbox"]{accent-color:var(--sm-primary);width:15px;height:15px;cursor:pointer}
.sm-check-row label{font-size:0.8rem;color:var(--sm-muted);cursor:pointer}

/* Upload */
.sm-upload{border:2px dashed var(--sm-border2);border-radius:var(--sm-radius);padding:40px 20px;text-align:center;cursor:pointer;transition:border-color 0.2s,background 0.2s;position:relative;background:var(--sm-surface)}
.sm-upload:hover,.sm-upload.dragover{border-color:var(--sm-primary);background:rgba(108,92,231,0.06)}
.sm-upload input[type="file"]{position:absolute;inset:0;opacity:0;cursor:pointer}
.sm-upload-title{font-size:1rem;font-weight:600;color:var(--sm-text);margin:8px 0 4px}
.sm-upload-hint{font-size:0.8rem;color:var(--sm-muted);margin:0}

/* Frame selector */
.sm-frames{display:grid;grid-template-columns:repeat(5,1fr);gap:6px;margin-bottom:14px}
.sm-frame-btn{display:flex;flex-direction:column;align-items:center;gap:4px;padding:8px 4px;background:var(--sm-bg);border:1.5px solid var(--sm-border);border-radius:8px;cursor:pointer;transition:border-color 0.15s;font-family:inherit;color:var(--sm-muted);font-size:0.65rem;font-weight:500}
.sm-frame-btn.active{border-color:var(--sm-primary);color:var(--sm-primary);background:rgba(108,92,231,0.1)}
.sm-frame-btn:hover{border-color:var(--sm-primary)}
.sm-frame-btn svg{width:28px;height:28px}

/* Gradient controls */
.sm-gradient-row{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:8px}

/* Preview area */
.sm-preview-area{background:var(--sm-surface);border:1px solid var(--sm-border);border-radius:var(--sm-radius);min-height:500px;display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.sm-preview-empty{text-align:center;color:var(--sm-muted);padding:40px}
.sm-preview-empty svg{display:block;margin:0 auto 16px}
.sm-canvas-wrap{width:100%;height:100%;display:flex;align-items:center;justify-content:center;padding:20px}
.sm-canvas-wrap canvas{max-width:100%;max-height:600px;border-radius:4px}

/* Buttons */
.sm-btn{display:inline-flex;align-items:center;gap:6px;padding:9px 16px;border:none;border-radius:8px;font-family:'Inter',sans-serif;font-size:0.83rem;font-weight:600;cursor:pointer;transition:all 0.15s;white-space:nowrap}
.sm-btn-primary{background:var(--sm-primary);color:#fff}
.sm-btn-primary:hover{background:var(--sm-primary-dark)}
.sm-btn-green{background:var(--sm-green);color:#0a0a0f;font-weight:700}
.sm-btn-green:hover{background:var(--sm-green-dark)}
.sm-btn-outline{background:transparent;color:var(--sm-primary);border:1.5px solid var(--sm-primary)}
.sm-btn-outline:hover{background:rgba(108,92,231,0.1)}
.sm-btn-sm{padding:6px 12px;font-size:0.76rem}
.sm-btn-red{background:transparent;color:var(--sm-red);border:1.5px solid var(--sm-red)}
.sm-btn-red:hover{background:rgba(255,71,87,0.1)}

/* Actions bar */
.sm-actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}

/* Batch mode */
.sm-batch-panel{display:none;background:var(--sm-surface);border:1px solid var(--sm-border);border-radius:var(--sm-radius);padding:16px}
.sm-batch-panel h3{font-size:0.85rem;font-weight:600;color:var(--sm-text);margin:0 0 12px}
.sm-batch-list{display:flex;gap:8px;flex-wrap:wrap}
.sm-batch-thumb{width:80px;height:60px;border:1px solid var(--sm-border);border-radius:6px;overflow:hidden;position:relative;cursor:pointer;transition:border-color 0.15s}
.sm-batch-thumb:hover{border-color:var(--sm-primary)}
.sm-batch-thumb.active{border-color:var(--sm-green);border-width:2px}
.sm-batch-thumb img{width:100%;height:100%;object-fit:cover}
.sm-batch-thumb .sm-batch-remove{position:absolute;top:2px;right:2px;width:16px;height:16px;background:rgba(0,0,0,0.7);border:none;border-radius:50%;color:#fff;font-size:10px;line-height:16px;text-align:center;cursor:pointer;padding:0;display:none}
.sm-batch-thumb:hover .sm-batch-remove{display:block}

/* Content */
.sm-content{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--sm-border)}
.sm-content h2{font-size:1.4rem;font-weight:700;color:var(--sm-text);margin:32px 0 12px}
.sm-content h2:first-child{margin-top:0}
.sm-content p{font-size:0.95rem;color:var(--sm-muted);line-height:1.75;margin:0 0 14px}
.sm-content ul,.sm-content ol{margin:0 0 14px;padding-left:20px;color:var(--sm-muted);font-size:0.95rem;line-height:1.75}
.sm-content ul li,.sm-content ol li{margin-bottom:6px}

/* FAQ */
.sm-faq{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--sm-border)}
.sm-faq h2{font-size:1.4rem;font-weight:700;color:var(--sm-text);margin:0 0 20px}
.sm-faq-item{border:1px solid var(--sm-border);border-radius:var(--sm-radius);padding:18px 22px;margin-bottom:12px;background:var(--sm-surface)}
.sm-faq-item h3{font-size:1rem;font-weight:600;margin:0 0 8px;color:var(--sm-text)}
.sm-faq-item p{margin:0;font-size:0.92rem;color:var(--sm-muted);line-height:1.7}

/* Responsive */
@media(max-width:900px){
.sm-app{grid-template-columns:1fr}
.sm-preview-area{min-height:350px}
}
@media(max-width:480px){
.sm-hero h1{font-size:1.5rem}
.sm-frames{grid-template-columns:repeat(3,1fr)}
}
</style>

<div class="sm-wrap" id="smApp">

<div class="sm-hero">
<h1>Free <span>Screenshot Mockup</span> Generator</h1>
<p class="sm-intro">Frame your screenshots in browser windows, phone bezels, laptops, and tablets. Add backgrounds, shadows, and padding for presentation-ready mockups. Download as PNG. Everything runs in your browser.</p>
</div>

<p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

<div class="sm-app">

<!-- Sidebar Controls -->
<div class="sm-sidebar">

<!-- Upload -->
<div class="sm-upload" id="smUpload">
<svg width="40" height="40" viewBox="0 0 40 40" fill="none"><rect x="4" y="8" width="32" height="24" rx="4" stroke="#6C5CE7" stroke-width="2" fill="none"/><path d="M20 4v6M20 4l-3 3M20 4l3 3" stroke="#A29BFE" stroke-width="2" stroke-linecap="round"/></svg>
<p class="sm-upload-title">Drop screenshot here or click to browse</p>
<p class="sm-upload-hint">PNG, JPG, WebP. Drag-and-drop or select multiple for batch mode.</p>
<input type="file" id="smFileInput" accept="image/*" multiple>
</div>

<!-- Frame Selector -->
<div class="sm-panel">
<h3>Device Frame</h3>
<div class="sm-frames">
<button class="sm-frame-btn active" data-frame="browser" onclick="smSetFrame('browser')">
<svg viewBox="0 0 28 28" fill="none"><rect x="2" y="4" width="24" height="20" rx="3" stroke="currentColor" stroke-width="1.5"/><line x1="2" y1="10" x2="26" y2="10" stroke="currentColor" stroke-width="1.2"/><circle cx="6" cy="7" r="1.2" fill="currentColor"/><circle cx="10" cy="7" r="1.2" fill="currentColor"/><circle cx="14" cy="7" r="1.2" fill="currentColor"/></svg>
Browser
</button>
<button class="sm-frame-btn" data-frame="phone" onclick="smSetFrame('phone')">
<svg viewBox="0 0 28 28" fill="none"><rect x="7" y="2" width="14" height="24" rx="3" stroke="currentColor" stroke-width="1.5"/><rect x="11" y="4" width="6" height="2" rx="1" fill="currentColor" opacity="0.5"/><line x1="12" y1="23" x2="16" y2="23" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
Phone
</button>
<button class="sm-frame-btn" data-frame="laptop" onclick="smSetFrame('laptop')">
<svg viewBox="0 0 28 28" fill="none"><rect x="4" y="4" width="20" height="14" rx="2" stroke="currentColor" stroke-width="1.5"/><path d="M2 18h24l-2 4H4l-2-4z" stroke="currentColor" stroke-width="1.3" fill="none"/></svg>
Laptop
</button>
<button class="sm-frame-btn" data-frame="tablet" onclick="smSetFrame('tablet')">
<svg viewBox="0 0 28 28" fill="none"><rect x="4" y="2" width="20" height="24" rx="3" stroke="currentColor" stroke-width="1.5"/><circle cx="14" cy="23" r="1.3" stroke="currentColor" stroke-width="1"/></svg>
Tablet
</button>
<button class="sm-frame-btn" data-frame="none" onclick="smSetFrame('none')">
<svg viewBox="0 0 28 28" fill="none"><rect x="4" y="4" width="20" height="20" stroke="currentColor" stroke-width="1.5" stroke-dasharray="3 2"/></svg>
None
</button>
</div>

<!-- Browser URL -->
<div class="sm-field" id="smUrlField">
<label>URL Bar Text</label>
<input type="text" id="smUrlText" value="yoursite.com" placeholder="yoursite.com" oninput="smRender()">
</div>
</div>

<!-- Background -->
<div class="sm-panel">
<h3>Background</h3>
<div class="sm-field">
<label>Type</label>
<select id="smBgType" onchange="smToggleBgControls();smRender()">
<option value="solid">Solid Color</option>
<option value="gradient" selected>Gradient</option>
<option value="transparent">Transparent</option>
</select>
</div>
<div id="smBgSolid" style="display:none">
<div class="sm-field">
<label>Color</label>
<div class="sm-color-row">
<input type="color" class="sm-color-input" id="smBgSolidColor" value="#1a1a2e" oninput="smRender()">
<input type="text" class="sm-color-hex" id="smBgSolidHex" value="#1a1a2e" oninput="smSyncBgSolid();smRender()">
</div>
</div>
</div>
<div id="smBgGradient">
<div class="sm-gradient-row">
<div class="sm-field">
<label>Color 1</label>
<div class="sm-color-row">
<input type="color" class="sm-color-input" id="smGrad1" value="#6C5CE7" oninput="smRender()">
</div>
</div>
<div class="sm-field">
<label>Color 2</label>
<div class="sm-color-row">
<input type="color" class="sm-color-input" id="smGrad2" value="#a29bfe" oninput="smRender()">
</div>
</div>
</div>
<div class="sm-field" style="margin-top:8px">
<div class="sm-slider-row">
<label>Angle <span id="smGradAngleVal">135deg</span></label>
<input type="range" id="smGradAngle" min="0" max="360" value="135" oninput="document.getElementById('smGradAngleVal').textContent=this.value+'deg';smRender()">
</div>
</div>
</div>
</div>

<!-- Spacing & Effects -->
<div class="sm-panel">
<h3>Spacing & Effects</h3>
<div class="sm-field">
<div class="sm-slider-row">
<label>Padding <span id="smPadVal">60px</span></label>
<input type="range" id="smPadding" min="0" max="150" value="60" oninput="document.getElementById('smPadVal').textContent=this.value+'px';smRender()">
</div>
</div>
<div class="sm-field">
<div class="sm-check-row">
<input type="checkbox" id="smShadow" checked onchange="smRender()">
<label for="smShadow">Drop shadow</label>
</div>
</div>
<div class="sm-field" id="smShadowIntensityField">
<div class="sm-slider-row">
<label>Shadow Intensity <span id="smShadowVal">40%</span></label>
<input type="range" id="smShadowIntensity" min="10" max="100" value="40" oninput="document.getElementById('smShadowVal').textContent=this.value+'%';smRender()">
</div>
</div>
<div class="sm-field">
<div class="sm-slider-row">
<label>Border Radius <span id="smBorderRadVal">12px</span></label>
<input type="range" id="smBorderRadius" min="0" max="40" value="12" oninput="document.getElementById('smBorderRadVal').textContent=this.value+'px';smRender()">
</div>
</div>
<div class="sm-field">
<div class="sm-slider-row">
<label>Scale <span id="smScaleVal">100%</span></label>
<input type="range" id="smScale" min="25" max="200" value="100" oninput="document.getElementById('smScaleVal').textContent=this.value+'%';smRender()">
</div>
</div>
</div>

<!-- Download -->
<div class="sm-actions">
<button class="sm-btn sm-btn-green" onclick="smDownload()" id="smDownloadBtn" disabled>Download PNG</button>
<button class="sm-btn sm-btn-outline sm-btn-sm" onclick="smDownloadAll()" id="smDownloadAllBtn" style="display:none">Download All (ZIP)</button>
<button class="sm-btn sm-btn-red sm-btn-sm" onclick="smClear()">Clear</button>
</div>

</div>

<!-- Preview Canvas -->
<div class="sm-preview-area" id="smPreviewArea">
<div class="sm-preview-empty" id="smEmptyState">
<svg width="64" height="64" viewBox="0 0 64 64" fill="none"><rect x="8" y="12" width="48" height="36" rx="4" stroke="#2a2a3e" stroke-width="2"/><line x1="8" y1="22" x2="56" y2="22" stroke="#2a2a3e" stroke-width="1.5"/><circle cx="15" cy="17" r="2" fill="#2a2a3e"/><circle cx="21" cy="17" r="2" fill="#2a2a3e"/><circle cx="27" cy="17" r="2" fill="#2a2a3e"/><path d="M24 38l8-8 8 8" stroke="#2a2a3e" stroke-width="2" stroke-linecap="round"/><line x1="32" y1="30" x2="32" y2="44" stroke="#2a2a3e" stroke-width="2" stroke-linecap="round"/></svg>
<p style="font-size:1rem;font-weight:600;margin:0 0 6px">Upload a screenshot to begin</p>
<p style="font-size:0.82rem;margin:0">Drag and drop or click the upload area on the left</p>
</div>
<div class="sm-canvas-wrap" id="smCanvasWrap" style="display:none">
<canvas id="smCanvas"></canvas>
</div>
</div>

</div>

<!-- Batch Panel -->
<div class="sm-batch-panel" id="smBatchPanel">
<h3>Batch Images (<span id="smBatchCount">0</span>)</h3>
<div class="sm-batch-list" id="smBatchList"></div>
<div style="margin-top:10px;display:flex;gap:8px">
<button class="sm-btn sm-btn-primary sm-btn-sm" onclick="smApplyToAll()">Apply Frame to All</button>
<button class="sm-btn sm-btn-outline sm-btn-sm" onclick="smAddMore()">Add More</button>
</div>
</div>

<!-- Content -->
<div class="sm-content">

<h2>What Is a Screenshot Mockup</h2>

<p>A screenshot mockup is a screenshot placed inside a realistic device frame -- a browser window, phone bezel, laptop shell, or tablet border. The frame adds context and makes the screenshot look like a finished product rather than a raw screen capture. Mockups are used in product pages, app store listings, blog posts, pitch decks, social media announcements, and any situation where you want to present software or a website in its best light.</p>

<p>The alternative is pasting a bare screenshot, which lacks depth and looks unprofessional in most contexts. Device frames provide visual anchoring: viewers immediately understand that they are looking at a website in Chrome or an app on an iPhone, without any explanation needed. This generator handles the framing, backgrounds, shadows, and export so you do not need Figma, Photoshop, or any other design tool.</p>

<h2>Why Use Mockups for Marketing</h2>

<p>Landing pages that show product screenshots inside device frames convert better than pages with raw screenshots. The frame signals professionalism and builds trust before the visitor reads a single word of copy. This applies equally to SaaS dashboards, mobile apps, browser extensions, and e-commerce storefronts.</p>

<p>App store listings on the Apple App Store and Google Play Store require screenshots with specific dimensions. Framing those screenshots inside phone mockups with colored backgrounds is the standard practice for top-ranked apps. The mockup provides space for marketing text above or below the device, which is how most successful listings present their features.</p>

<p>Social media posts with mockup images see higher engagement than plain screenshots. A tweet or LinkedIn post showing a new feature inside a browser frame catches the eye while scrolling. The padding and shadow create negative space that separates the content from the feed background, making it more visually distinct.</p>

<p>Documentation and blog posts benefit as well. Technical tutorials that include framed screenshots help readers orient themselves -- they can see that the screenshot shows a browser tab, which clarifies whether the interface is a web app, desktop app, or mobile screen.</p>

<h2>Device Frame Types Explained</h2>

<p>This tool provides five frame options, each suited to different use cases:</p>

<ul>
<li>Browser frame: a Chrome-style window with traffic light dots, a tab bar, and an address bar showing your custom URL. Best for websites, web apps, dashboards, and SaaS products.</li>
<li>Phone frame: an iPhone-style bezel with a notch or dynamic island, rounded corners, and a home indicator bar at the bottom. Best for mobile app screenshots, responsive design previews, and app store listings.</li>
<li>Laptop frame: a MacBook-style shell with a screen bezel and keyboard base. Best for pitch decks, landing page hero images, and product marketing where you want to show the full device context.</li>
<li>Tablet frame: an iPad-style border with rounded corners and a home button indicator. Best for tablet-optimized apps, reading apps, and educational content.</li>
<li>None: no frame at all. The screenshot is placed on the background with padding and shadow applied directly. Useful when you want a clean presentation without implying a specific device.</li>
</ul>

<h2>Tips for Professional Screenshots</h2>

<p>Capture at native resolution. Retina and high-DPI displays produce screenshots at 2x or 3x pixel density, which results in the sharpest mockups. A 2880x1800 screenshot from a MacBook Pro looks significantly better inside a browser frame than a 1440x900 capture from a standard display. If your display is not high-DPI, capture at the largest window size possible.</p>

<p>Clean up before capturing. Close unnecessary tabs, hide bookmarks bars, clear notification badges, and use a clean browser profile with minimal extensions. These small details affect the perceived quality of the final mockup.</p>

<p>Use consistent backgrounds across a set of mockups. If you are creating multiple screenshots for a landing page or app store listing, pick one gradient or solid color and apply it to all of them. Visual consistency makes the set look intentional and polished.</p>

<p>Adjust padding based on context. More padding works well for social media and presentations where the mockup needs breathing room. Less padding is better for documentation and blog posts where screen real estate is at a premium. This tool lets you control padding from 0 to 150 pixels.</p>

<p>Export at the right scale. For web usage, 1x or 2x scale is sufficient. For print materials or large presentations, 2x scale ensures the output stays crisp when displayed on projectors or printed. The scale slider goes from 25% to 200%, giving you full control over the output resolution.</p>

</div>

<!-- FAQ -->
<div class="sm-faq">
<h2>Frequently Asked Questions</h2>

<div class="sm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What image formats can I upload?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">This mockup generator accepts PNG, JPEG, WebP, GIF, and BMP screenshots. PNG is recommended because it preserves sharp text and UI edges without compression artifacts. JPEG works fine for photographic content but may show artifacts around text and lines. All image processing happens locally in your browser using the Canvas API -- no files are uploaded to any server.</p>
</div>
</div>

<div class="sm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Can I create mockups with a transparent background?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Yes. Select "Transparent" from the background type dropdown. The exported PNG will have an alpha channel, which means you can place the mockup on top of any background in your design tool, website, or presentation. Transparent exports are useful when you need to layer the mockup over a custom background in Figma, Canva, or PowerPoint.</p>
</div>
</div>

<div class="sm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is batch mode and how does it work?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Batch mode activates when you upload multiple screenshots at once. Each image appears as a thumbnail at the bottom of the tool. Click any thumbnail to preview it in the canvas area. Use the "Apply Frame to All" button to render every screenshot with the same frame, background, padding, and shadow settings. You can then download all the processed mockups as a ZIP archive. This is useful for preparing sets of app store screenshots or landing page images.</p>
</div>
</div>

<div class="sm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What resolution should my screenshots be for the best results?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Higher resolution input produces better output. For browser mockups, screenshots captured on a Retina or high-DPI display (2560x1440 and above) work best. For phone mockups, use the device's native screenshot resolution -- 1170x2532 for iPhone 14 Pro or 1290x2796 for iPhone 15 Pro Max. The tool preserves the original resolution by default, and the scale slider lets you adjust the output size up to 200% of the input.</p>
</div>
</div>

<div class="sm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Is this tool free to use for commercial projects?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Yes. There are no restrictions on usage. The mockups you generate can be used for commercial products, client work, app store listings, social media, presentations, and any other purpose. There is no watermark on exported images. The tool is free, requires no account, and runs entirely in your browser with no server-side processing or data collection.</p>
</div>
</div>

</div>

<!-- Related Tools -->
<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/image-compressor/" style="color:#00ff88;text-decoration:none;">Image Compressor</a> - Compress your mockup PNGs for faster page loads</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/color-palette-generator/" style="color:#00ff88;text-decoration:none;">Color Palette Generator</a> - Generate background gradients and brand colors</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/favicon-generator/" style="color:#00ff88;text-decoration:none;">Favicon Generator</a> - Create favicons from text, emoji, or images</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/qr-code-generator/" style="color:#00ff88;text-decoration:none;">QR Code Generator</a> - Create custom QR codes with colors and logos</li>
</ul>
</div>

<!-- Author Box -->
<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;flex-shrink:0;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>

<footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid #2a2a3a;margin-top:3rem;">
<p>Built by <a href="https://zovo.one" style="color:#6C5CE7;text-decoration:none;">Michael Lip</a> at <a href="https://zovo.one" style="color:#6C5CE7;text-decoration:none;">zovo.one</a></p>
</footer>

</div>

<script>
(function(){
"use strict";

var canvas=document.getElementById("smCanvas");
var ctx=canvas.getContext("2d");
var uploadEl=document.getElementById("smUpload");
var fileInput=document.getElementById("smFileInput");
var previewArea=document.getElementById("smPreviewArea");
var emptyState=document.getElementById("smEmptyState");
var canvasWrap=document.getElementById("smCanvasWrap");
var batchPanel=document.getElementById("smBatchPanel");
var batchList=document.getElementById("smBatchList");
var downloadBtn=document.getElementById("smDownloadBtn");
var downloadAllBtn=document.getElementById("smDownloadAllBtn");

var currentFrame="browser";
var images=[];
var activeIndex=-1;
var zipLoaded=false;

// --- Frame selection ---
window.smSetFrame=function(frame){
currentFrame=frame;
document.querySelectorAll(".sm-frame-btn").forEach(function(b){b.classList.toggle("active",b.dataset.frame===frame);});
var urlField=document.getElementById("smUrlField");
urlField.style.display=(frame==="browser")?"block":"none";
smRender();
};

// --- Background controls ---
window.smToggleBgControls=function(){
var type=document.getElementById("smBgType").value;
document.getElementById("smBgSolid").style.display=(type==="solid")?"block":"none";
document.getElementById("smBgGradient").style.display=(type==="gradient")?"block":"none";
};

window.smSyncBgSolid=function(){
var hex=document.getElementById("smBgSolidHex").value;
if(/^#[0-9a-fA-F]{6}$/.test(hex))document.getElementById("smBgSolidColor").value=hex;
};

// --- File handling ---
fileInput.addEventListener("change",function(){
if(this.files&&this.files.length)handleFiles(this.files);
});

uploadEl.addEventListener("dragover",function(e){e.preventDefault();uploadEl.classList.add("dragover");});
uploadEl.addEventListener("dragleave",function(){uploadEl.classList.remove("dragover");});
uploadEl.addEventListener("drop",function(e){
e.preventDefault();uploadEl.classList.remove("dragover");
if(e.dataTransfer.files&&e.dataTransfer.files.length)handleFiles(e.dataTransfer.files);
});

document.addEventListener("paste",function(e){
var items=e.clipboardData&&e.clipboardData.items;
if(!items)return;
var files=[];
for(var i=0;i<items.length;i++){
if(items[i].type.match(/^image\//))files.push(items[i].getAsFile());
}
if(files.length){e.preventDefault();handleFiles(files);}
});

function handleFiles(fileList){
var newFiles=Array.from(fileList).filter(function(f){return f.type.match(/^image\//);});
if(!newFiles.length)return;
newFiles.forEach(function(f){loadImage(f);});
}

function loadImage(file){
var reader=new FileReader();
reader.onload=function(e){
var img=new Image();
img.onload=function(){
images.push({img:img,name:file.name,dataUrl:e.target.result});
if(images.length===1){
activeIndex=0;
showEditor();
}
updateBatch();
smRender();
};
img.src=e.target.result;
};
reader.readAsDataURL(file);
}

function showEditor(){
emptyState.style.display="none";
canvasWrap.style.display="flex";
uploadEl.style.display="none";
downloadBtn.disabled=false;
}

window.smAddMore=function(){
var tempInput=document.createElement("input");
tempInput.type="file";tempInput.accept="image/*";tempInput.multiple=true;
tempInput.onchange=function(){if(this.files&&this.files.length)handleFiles(this.files);};
tempInput.click();
};

function updateBatch(){
if(images.length<=1){
batchPanel.style.display="none";
downloadAllBtn.style.display="none";
return;
}
batchPanel.style.display="block";
downloadAllBtn.style.display="";
document.getElementById("smBatchCount").textContent=images.length;
var html="";
images.forEach(function(item,idx){
html+='<div class="sm-batch-thumb'+(idx===activeIndex?' active':'')+'" onclick="smSelectBatch('+idx+')">';
html+='<img src="'+item.dataUrl+'" alt="'+item.name+'">';
html+='<button class="sm-batch-remove" onclick="event.stopPropagation();smRemoveBatch('+idx+')">&times;</button>';
html+='</div>';
});
batchList.innerHTML=html;
}

window.smSelectBatch=function(idx){
activeIndex=idx;
updateBatch();
smRender();
};

window.smRemoveBatch=function(idx){
images.splice(idx,1);
if(images.length===0){
activeIndex=-1;
emptyState.style.display="";
canvasWrap.style.display="none";
uploadEl.style.display="";
downloadBtn.disabled=true;
}else{
if(activeIndex>=images.length)activeIndex=images.length-1;
}
updateBatch();
smRender();
};

window.smClear=function(){
images=[];
activeIndex=-1;
emptyState.style.display="";
canvasWrap.style.display="none";
uploadEl.style.display="";
downloadBtn.disabled=true;
batchPanel.style.display="none";
downloadAllBtn.style.display="none";
fileInput.value="";
};

// --- Render ---
window.smRender=function(){
if(activeIndex<0||!images[activeIndex])return;
var img=images[activeIndex].img;
renderMockup(canvas,ctx,img);
};

function renderMockup(cvs,context,img){
var scale=parseInt(document.getElementById("smScale").value)/100;
var padding=parseInt(document.getElementById("smPadding").value)*scale;
var borderRadius=parseInt(document.getElementById("smBorderRadius").value)*scale;
var showShadow=document.getElementById("smShadow").checked;
var shadowIntensity=parseInt(document.getElementById("smShadowIntensity").value)/100;
var bgType=document.getElementById("smBgType").value;

var imgW=img.naturalWidth*scale;
var imgH=img.naturalHeight*scale;

// Frame dimensions
var frameInfo=getFrameDimensions(imgW,imgH,scale);
var totalW=frameInfo.w+padding*2;
var totalH=frameInfo.h+padding*2;

// Shadow space
var shadowBlur=showShadow?Math.round(30*scale*shadowIntensity):0;
var shadowOffY=showShadow?Math.round(10*scale*shadowIntensity):0;
totalW+=shadowBlur*2;
totalH+=shadowBlur*2+shadowOffY;

cvs.width=Math.round(totalW);
cvs.height=Math.round(totalH);
context.clearRect(0,0,cvs.width,cvs.height);

// Background
if(bgType==="solid"){
context.fillStyle=document.getElementById("smBgSolidColor").value;
context.fillRect(0,0,cvs.width,cvs.height);
}else if(bgType==="gradient"){
var angle=parseInt(document.getElementById("smGradAngle").value)*Math.PI/180;
var cx=cvs.width/2,cy=cvs.height/2;
var len=Math.max(cvs.width,cvs.height);
var x1=cx-Math.cos(angle)*len/2;
var y1=cy-Math.sin(angle)*len/2;
var x2=cx+Math.cos(angle)*len/2;
var y2=cy+Math.sin(angle)*len/2;
var grad=context.createLinearGradient(x1,y1,x2,y2);
grad.addColorStop(0,document.getElementById("smGrad1").value);
grad.addColorStop(1,document.getElementById("smGrad2").value);
context.fillStyle=grad;
context.fillRect(0,0,cvs.width,cvs.height);
}

// Position
var fx=padding+shadowBlur;
var fy=padding+shadowBlur;

// Shadow
if(showShadow){
context.save();
context.shadowColor="rgba(0,0,0,"+shadowIntensity+")";
context.shadowBlur=shadowBlur;
context.shadowOffsetX=0;
context.shadowOffsetY=shadowOffY;
context.fillStyle="rgba(0,0,0,0.01)";
roundRectPath(context,fx,fy,frameInfo.w,frameInfo.h,borderRadius);
context.fill();
context.restore();
}

// Draw frame
drawFrame(context,fx,fy,imgW,imgH,frameInfo,borderRadius,scale,img);
}

function getFrameDimensions(imgW,imgH,scale){
var f=currentFrame;
if(f==="browser"){
var barH=Math.round(40*scale);
return{w:imgW,h:imgH+barH,barH:barH};
}
if(f==="phone"){
var topH=Math.round(50*scale);
var botH=Math.round(30*scale);
var sideW=Math.round(16*scale);
return{w:imgW+sideW*2,h:imgH+topH+botH,topH:topH,botH:botH,sideW:sideW};
}
if(f==="laptop"){
var topBar=Math.round(24*scale);
var baseH=Math.round(30*scale);
var sideP=Math.round(40*scale);
return{w:imgW+sideP*2,h:imgH+topBar+baseH,topBar:topBar,baseH:baseH,sideP:sideP};
}
if(f==="tablet"){
var tTop=Math.round(36*scale);
var tBot=Math.round(36*scale);
var tSide=Math.round(20*scale);
return{w:imgW+tSide*2,h:imgH+tTop+tBot,tTop:tTop,tBot:tBot,tSide:tSide};
}
return{w:imgW,h:imgH};
}

function drawFrame(context,fx,fy,imgW,imgH,info,br,scale,img){
var f=currentFrame;

if(f==="browser"){
// Browser chrome
context.save();
roundRectPath(context,fx,fy,info.w,info.h,br);
context.clip();
context.fillStyle="#1e1e2e";
context.fillRect(fx,fy,info.w,info.h);
// Title bar
context.fillStyle="#12121a";
context.fillRect(fx,fy,info.w,info.barH);
// Traffic lights
var dotY=fy+info.barH/2;
var dotR=Math.round(5*scale);
var dotX=fx+Math.round(16*scale);
var colors=["#ff5f57","#ffbd2e","#27c93f"];
colors.forEach(function(c,i){
context.beginPath();
context.arc(dotX+i*Math.round(14*scale),dotY,dotR,0,Math.PI*2);
context.fillStyle=c;
context.fill();
});
// Tab
var tabX=dotX+Math.round(52*scale);
var tabW=Math.round(130*scale);
var tabH=Math.round(24*scale);
var tabY=fy+(info.barH-tabH)/2;
context.fillStyle="#1e1e2e";
roundRectFill(context,tabX,tabY,tabW,tabH,Math.round(5*scale));
context.fillStyle="#8888aa";
context.font=Math.round(10*scale)+"px 'Inter',sans-serif";
context.textBaseline="middle";
context.fillText("My Website",tabX+Math.round(10*scale),tabY+tabH/2);
// URL bar
var urlX=tabX+tabW+Math.round(12*scale);
var urlW=info.w-urlX+fx-Math.round(16*scale);
var urlH=Math.round(22*scale);
var urlY=fy+(info.barH-urlH)/2;
if(urlW>0){
context.fillStyle="#0a0a0f";
roundRectFill(context,urlX,urlY,urlW,urlH,Math.round(4*scale));
context.fillStyle="#666680";
context.font=Math.round(9*scale)+"px 'JetBrains Mono',monospace";
var urlText=document.getElementById("smUrlText").value||"yoursite.com";
context.fillText(urlText,urlX+Math.round(8*scale),urlY+urlH/2);
}
// Separator line
context.fillStyle="#2a2a3e";
context.fillRect(fx,fy+info.barH-1,info.w,1);
// Screenshot
context.drawImage(img,fx,fy+info.barH,imgW,imgH);
context.restore();
return;
}

if(f==="phone"){
context.save();
var phoneR=Math.round(28*scale);
roundRectPath(context,fx,fy,info.w,info.h,phoneR);
context.clip();
// Phone body
context.fillStyle="#1a1a1a";
context.fillRect(fx,fy,info.w,info.h);
// Dynamic island
var diW=Math.round(80*scale);
var diH=Math.round(20*scale);
var diX=fx+info.w/2-diW/2;
var diY=fy+Math.round(12*scale);
context.fillStyle="#000";
roundRectFill(context,diX,diY,diW,diH,Math.round(10*scale));
// Screenshot
context.drawImage(img,fx+info.sideW,fy+info.topH,imgW,imgH);
// Home bar
var barW=Math.round(100*scale);
var barH2=Math.round(4*scale);
var barX=fx+info.w/2-barW/2;
var barY=fy+info.h-Math.round(14*scale);
context.fillStyle="#555";
roundRectFill(context,barX,barY,barW,barH2,Math.round(2*scale));
context.restore();
return;
}

if(f==="laptop"){
context.save();
// Screen bezel
var screenR=Math.round(8*scale);
roundRectPath(context,fx,fy,info.w,info.h-info.baseH,screenR);
context.clip();
context.fillStyle="#1a1a1a";
context.fillRect(fx,fy,info.w,info.h-info.baseH);
// Top bezel with camera dot
var camR=Math.round(3*scale);
context.beginPath();
context.arc(fx+info.w/2,fy+info.topBar/2,camR,0,Math.PI*2);
context.fillStyle="#333";
context.fill();
// Screenshot
context.drawImage(img,fx+info.sideP,fy+info.topBar,imgW,imgH);
context.restore();
// Base/keyboard
context.save();
var baseY=fy+info.h-info.baseH;
context.fillStyle="#2a2a2e";
context.beginPath();
context.moveTo(fx-Math.round(20*scale),baseY+info.baseH);
context.lineTo(fx+info.w+Math.round(20*scale),baseY+info.baseH);
context.lineTo(fx+info.w,baseY);
context.lineTo(fx,baseY);
context.closePath();
context.fill();
// Hinge line
context.fillStyle="#3a3a40";
context.fillRect(fx,baseY,info.w,Math.round(2*scale));
// Trackpad
var tpW=Math.round(80*scale);
var tpH=Math.round(12*scale);
context.fillStyle="#333";
roundRectFill(context,fx+info.w/2-tpW/2,baseY+info.baseH/2-tpH/2+Math.round(2*scale),tpW,tpH,Math.round(3*scale));
context.restore();
return;
}

if(f==="tablet"){
context.save();
var tabletR=Math.round(16*scale);
roundRectPath(context,fx,fy,info.w,info.h,tabletR);
context.clip();
context.fillStyle="#1a1a1a";
context.fillRect(fx,fy,info.w,info.h);
// Camera dot
context.beginPath();
context.arc(fx+info.w/2,fy+info.tTop/2,Math.round(3*scale),0,Math.PI*2);
context.fillStyle="#333";
context.fill();
// Screenshot
context.drawImage(img,fx+info.tSide,fy+info.tTop,imgW,imgH);
// Home indicator
var hiW=Math.round(60*scale);
var hiH2=Math.round(4*scale);
context.fillStyle="#555";
roundRectFill(context,fx+info.w/2-hiW/2,fy+info.h-Math.round(14*scale),hiW,hiH2,Math.round(2*scale));
context.restore();
return;
}

// None frame
context.save();
if(br>0){
roundRectPath(context,fx,fy,imgW,imgH,br);
context.clip();
}
context.drawImage(img,fx,fy,imgW,imgH);
context.restore();
}

function roundRectPath(ctx2,x,y,w,h,r){
r=Math.min(r,w/2,h/2);
ctx2.beginPath();
ctx2.moveTo(x+r,y);
ctx2.arcTo(x+w,y,x+w,y+h,r);
ctx2.arcTo(x+w,y+h,x,y+h,r);
ctx2.arcTo(x,y+h,x,y,r);
ctx2.arcTo(x,y,x+w,y,r);
ctx2.closePath();
}

function roundRectFill(ctx2,x,y,w,h,r){
ctx2.beginPath();
roundRectPath(ctx2,x,y,w,h,r);
ctx2.fill();
}

// --- Download ---
window.smDownload=function(){
if(activeIndex<0||!images[activeIndex])return;
var a=document.createElement("a");
var name=images[activeIndex].name.replace(/\.[^.]+$/,"");
a.download=name+"_mockup.png";
a.href=canvas.toDataURL("image/png");
document.body.appendChild(a);a.click();document.body.removeChild(a);
};

window.smDownloadAll=function(){
if(images.length<=1){smDownload();return;}
if(!zipLoaded){
var s=document.createElement("script");
s.src="https://cdn.jsdelivr.net/npm/jszip@3/dist/jszip.min.js";
s.onload=function(){zipLoaded=true;buildAllZip();};
document.head.appendChild(s);
}else{buildAllZip();}
};

function buildAllZip(){
if(typeof JSZip==="undefined")return;
var zip=new JSZip();
var tempCvs=document.createElement("canvas");
var tempCtx=tempCvs.getContext("2d");
images.forEach(function(item,idx){
renderMockup(tempCvs,tempCtx,item.img);
var dataUrl=tempCvs.toDataURL("image/png");
var base64=dataUrl.split(",")[1];
var name=item.name.replace(/\.[^.]+$/,"");
zip.file(name+"_mockup.png",base64,{base64:true});
});
zip.generateAsync({type:"blob"}).then(function(content){
var a=document.createElement("a");
a.download="mockups.zip";
a.href=URL.createObjectURL(content);
document.body.appendChild(a);a.click();document.body.removeChild(a);
URL.revokeObjectURL(a.href);
});
}

window.smApplyToAll=function(){
if(images.length===0)return;
// Just re-render current one; downloads will apply to all via buildAllZip
var orig=activeIndex;
alert("Frame settings applied. Use 'Download All (ZIP)' to export all "+images.length+" mockups with the current settings.");
activeIndex=orig;
smRender();
};

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Free Screenshot Mockup Generator",
      "url": "https://theluckystrike.github.io/tools/screenshot-mockup/",
      "applicationCategory": "DesignApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "description": "Create beautiful screenshot mockups with browser, phone, laptop, and tablet frames. Add backgrounds, shadows, and padding. Free online mockup generator with PNG download.",
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Screenshot Mockup Generator", "item": "https://theluckystrike.github.io/tools/screenshot-mockup/" }
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
          "name": "What image formats can I upload?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "This mockup generator accepts PNG, JPEG, WebP, GIF, and BMP screenshots. PNG is recommended because it preserves sharp text and UI edges without compression artifacts. All image processing happens locally in your browser -- no files are uploaded to any server."
          }
        },
        {
          "@type": "Question",
          "name": "Can I create mockups with a transparent background?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Select Transparent from the background type dropdown. The exported PNG will have an alpha channel, which means you can place the mockup on top of any background in your design tool, website, or presentation."
          }
        },
        {
          "@type": "Question",
          "name": "What is batch mode and how does it work?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Batch mode activates when you upload multiple screenshots at once. Each image appears as a thumbnail. Use Apply Frame to All to render every screenshot with the same settings, then download all processed mockups as a ZIP archive."
          }
        },
        {
          "@type": "Question",
          "name": "What resolution should my screenshots be for the best results?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Higher resolution input produces better output. For browser mockups, screenshots captured on a Retina display (2560x1440 and above) work best. For phone mockups, use the device's native screenshot resolution. The scale slider lets you adjust output size up to 200%."
          }
        },
        {
          "@type": "Question",
          "name": "Is this tool free to use for commercial projects?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. There are no restrictions on usage. The mockups you generate can be used for commercial products, client work, app store listings, social media, presentations, and any other purpose. There is no watermark, no account required, and no server-side processing."
          }
        }
      ]
    }
  ]
}
</script>
