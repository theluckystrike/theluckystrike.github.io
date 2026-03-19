---
layout: page
title: "Free Aspect Ratio Calculator — Resize, Scale & Convert | Zovo"
description: "Calculate and convert aspect ratios for images, video, and screens. Lock ratios, resize dimensions, see common resolutions, get social media sizes, and calculate crop areas. Free online tool."
permalink: /tools/aspect-ratio-calculator/
keywords: "aspect ratio calculator, 16:9 calculator, image resize calculator, video aspect ratio, screen resolution calculator, aspect ratio converter"
date: 2026-03-19
categories: [tools]
tags: [aspect-ratio, calculator, image, video, resolution, social-media, resize]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
:root{--ar-primary:#6C5CE7;--ar-primary-dark:#5A4BD1;--ar-primary-light:#A29BFE;--ar-bg:#0a0a0f;--ar-surface:#12121a;--ar-surface2:#1a1a28;--ar-border:#1e1e2e;--ar-border2:#2a2a3e;--ar-text:#e0e0e0;--ar-muted:#8888aa;--ar-green:#00ff88;--ar-green-dark:#00dd77;--ar-red:#ff4757;--ar-radius:12px;--ar-shadow:0 4px 24px rgba(0,0,0,0.3)}
.ar-wrap{font-family:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;color:var(--ar-text);max-width:1100px;margin:0 auto;padding:0 16px;line-height:1.6}
.ar-wrap *{box-sizing:border-box}
.ar-hero{text-align:center;padding:40px 0 28px}
.ar-hero h1{font-size:2.2rem;font-weight:700;color:var(--ar-text);margin:0 0 16px;line-height:1.2}
.ar-hero h1 span{color:var(--ar-primary)}
.ar-intro{font-size:1.02rem;color:var(--ar-muted);max-width:700px;margin:0 auto;line-height:1.7}
.ar-updated{display:inline-block;font-size:0.75rem;color:var(--ar-muted);margin-top:12px;padding:4px 12px;border:1px solid var(--ar-border);border-radius:20px}

/* Cards */
.ar-card{background:var(--ar-surface);border:1px solid var(--ar-border);border-radius:var(--ar-radius);padding:24px;box-shadow:var(--ar-shadow);margin-bottom:24px}
.ar-card h3{font-size:0.85rem;font-weight:600;color:var(--ar-text);margin:0 0 16px;padding-bottom:10px;border-bottom:1px solid var(--ar-border);text-transform:uppercase;letter-spacing:0.5px}

/* Grid layout */
.ar-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px;margin-bottom:24px}
.ar-grid-3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:24px;margin-bottom:24px}

/* Fields */
.ar-field{margin-bottom:14px}
.ar-field:last-child{margin-bottom:0}
.ar-field label{display:block;font-size:0.78rem;font-weight:600;color:var(--ar-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:6px}
.ar-field input[type="number"],.ar-field select{width:100%;font-family:'Inter',sans-serif;font-size:0.9rem;padding:9px 12px;border:1.5px solid var(--ar-border);border-radius:8px;background:var(--ar-bg);color:var(--ar-text);outline:none;transition:border-color 0.2s}
.ar-field input:focus,.ar-field select:focus{border-color:var(--ar-primary);box-shadow:0 0 0 3px rgba(108,92,231,0.15)}
.ar-field select{appearance:auto}

/* Result display */
.ar-result{text-align:center;padding:20px;background:var(--ar-bg);border-radius:var(--ar-radius);border:1px solid var(--ar-border);margin-bottom:16px}
.ar-result-ratio{font-family:'JetBrains Mono',monospace;font-size:2.4rem;font-weight:700;color:var(--ar-primary);margin:0}
.ar-result-label{font-size:0.8rem;color:var(--ar-muted);margin:4px 0 0;text-transform:uppercase;letter-spacing:0.5px}
.ar-result-decimal{font-family:'JetBrains Mono',monospace;font-size:1rem;color:var(--ar-text);margin:6px 0 0}

/* Dimension inputs row */
.ar-dim-row{display:flex;gap:12px;align-items:flex-end}
.ar-dim-row .ar-field{flex:1}
.ar-lock-btn{display:flex;align-items:center;justify-content:center;width:42px;height:42px;background:var(--ar-bg);border:1.5px solid var(--ar-border);border-radius:8px;cursor:pointer;transition:all 0.15s;color:var(--ar-muted);font-size:1.1rem;flex-shrink:0;margin-bottom:0}
.ar-lock-btn.locked{background:rgba(108,92,231,0.15);border-color:var(--ar-primary);color:var(--ar-primary)}
.ar-lock-btn:hover{border-color:var(--ar-primary)}

/* Preset buttons */
.ar-presets{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:16px}
.ar-preset{padding:7px 14px;background:var(--ar-bg);border:1.5px solid var(--ar-border);border-radius:8px;color:var(--ar-muted);font-family:'JetBrains Mono',monospace;font-size:0.8rem;font-weight:500;cursor:pointer;transition:all 0.15s}
.ar-preset:hover{border-color:var(--ar-primary);color:var(--ar-text)}
.ar-preset.active{background:var(--ar-primary);border-color:var(--ar-primary);color:#fff}

/* Preview box */
.ar-preview-container{display:flex;align-items:center;justify-content:center;min-height:200px;padding:20px;background:var(--ar-bg);border-radius:var(--ar-radius);border:1px solid var(--ar-border)}
.ar-preview-rect{border:2px solid var(--ar-primary);border-radius:4px;background:rgba(108,92,231,0.08);transition:all 0.3s ease;position:relative;display:flex;align-items:center;justify-content:center}
.ar-preview-rect span{font-family:'JetBrains Mono',monospace;font-size:0.75rem;color:var(--ar-primary-light);white-space:nowrap}

/* Resolution table */
.ar-res-table{width:100%;border-collapse:collapse}
.ar-res-table th,.ar-res-table td{padding:8px 12px;text-align:left;font-size:0.82rem;border:1px solid var(--ar-border)}
.ar-res-table th{background:var(--ar-surface2);color:var(--ar-text);font-weight:600;font-size:0.72rem;text-transform:uppercase;letter-spacing:0.5px}
.ar-res-table td{color:var(--ar-muted);font-family:'JetBrains Mono',monospace;font-size:0.8rem}
.ar-res-table tr:hover td{background:var(--ar-surface2)}

/* Social media cards */
.ar-social-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:10px}
.ar-social-item{background:var(--ar-bg);border:1px solid var(--ar-border);border-radius:8px;padding:12px;cursor:pointer;transition:border-color 0.15s}
.ar-social-item:hover{border-color:var(--ar-primary)}
.ar-social-name{font-size:0.82rem;font-weight:600;color:var(--ar-text);margin:0 0 4px}
.ar-social-size{font-family:'JetBrains Mono',monospace;font-size:0.78rem;color:var(--ar-primary-light);margin:0 0 2px}
.ar-social-ratio{font-size:0.72rem;color:var(--ar-muted);margin:0}

/* Crop calculator */
.ar-crop-result{padding:14px;background:var(--ar-bg);border-radius:8px;border:1px solid var(--ar-border);margin-top:12px;display:none}
.ar-crop-result p{margin:0 0 4px;font-size:0.85rem;color:var(--ar-muted)}
.ar-crop-result .ar-crop-val{font-family:'JetBrains Mono',monospace;color:var(--ar-green);font-weight:600}

/* Buttons */
.ar-btn{display:inline-flex;align-items:center;gap:6px;padding:9px 16px;border:none;border-radius:8px;font-family:'Inter',sans-serif;font-size:0.83rem;font-weight:600;cursor:pointer;transition:all 0.15s;white-space:nowrap}
.ar-btn-primary{background:var(--ar-primary);color:#fff}
.ar-btn-primary:hover{background:var(--ar-primary-dark)}
.ar-btn-green{background:var(--ar-green);color:#0a0a0f;font-weight:700}
.ar-btn-green:hover{background:var(--ar-green-dark)}
.ar-btn-outline{background:transparent;color:var(--ar-primary);border:1.5px solid var(--ar-primary)}
.ar-btn-outline:hover{background:rgba(108,92,231,0.1)}

/* Cross links */
.ar-cross-links{display:flex;flex-wrap:wrap;gap:8px;margin-top:32px}
.ar-cross-link{display:inline-block;padding:8px 16px;background:var(--ar-surface);border:1px solid var(--ar-border);border-radius:8px;color:var(--ar-muted);font-size:0.82rem;text-decoration:none;transition:border-color 0.15s,color 0.15s}
.ar-cross-link:hover{border-color:var(--ar-primary);color:var(--ar-text)}

/* Content */
.ar-content{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--ar-border)}
.ar-content h2{font-size:1.4rem;font-weight:700;color:var(--ar-text);margin:32px 0 12px}
.ar-content h2:first-child{margin-top:0}
.ar-content p{font-size:0.95rem;color:var(--ar-muted);line-height:1.75;margin:0 0 14px}
.ar-content ul,.ar-content ol{margin:0 0 14px;padding-left:20px;color:var(--ar-muted);font-size:0.95rem;line-height:1.75}
.ar-content ul li,.ar-content ol li{margin-bottom:6px}
.ar-content table{width:100%;border-collapse:collapse;margin:0 0 14px}
.ar-content th,.ar-content td{padding:10px 14px;text-align:left;font-size:0.88rem;border:1px solid var(--ar-border)}
.ar-content th{background:var(--ar-surface);color:var(--ar-text);font-weight:600;font-size:0.78rem;text-transform:uppercase;letter-spacing:0.5px}
.ar-content td{color:var(--ar-muted)}

/* FAQ */
.ar-faq{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--ar-border)}
.ar-faq h2{font-size:1.4rem;font-weight:700;color:var(--ar-text);margin:0 0 20px}
.ar-faq-item{border:1px solid var(--ar-border);border-radius:var(--ar-radius);padding:18px 22px;margin-bottom:12px;background:var(--ar-surface)}
.ar-faq-item h3{font-size:1rem;font-weight:600;margin:0 0 8px;color:var(--ar-text)}
.ar-faq-item p{margin:0;font-size:0.92rem;color:var(--ar-muted);line-height:1.7}

/* Author */
.ar-author-box{display:flex;gap:16px;align-items:center;padding:20px;background:var(--ar-surface);border:1px solid var(--ar-border);border-radius:var(--ar-radius);margin-top:32px;max-width:820px;margin-left:auto;margin-right:auto}
.ar-author-avatar{width:56px;height:56px;border-radius:50%;background:var(--ar-primary);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:1.1rem;color:#fff;flex-shrink:0}
.ar-author-info{flex:1}
.ar-author-name{font-size:0.95rem;font-weight:600;color:var(--ar-text);margin:0 0 4px}
.ar-author-bio{font-size:0.82rem;color:var(--ar-muted);margin:0;line-height:1.6}

/* Footer */
.ar-footer{text-align:center;padding:24px 0 8px;margin-top:32px;border-top:1px solid var(--ar-border);max-width:820px;margin-left:auto;margin-right:auto}
.ar-footer p{font-size:0.8rem;color:var(--ar-muted);margin:0}
.ar-footer a{color:var(--ar-primary);text-decoration:none}
.ar-footer a:hover{text-decoration:underline}

/* Responsive */
@media(max-width:768px){
.ar-hero h1{font-size:1.6rem}
.ar-grid,.ar-grid-3{grid-template-columns:1fr}
.ar-social-grid{grid-template-columns:1fr 1fr}
.ar-dim-row{flex-direction:column}
.ar-lock-btn{align-self:center}
.ar-author-box{flex-direction:column;align-items:center;text-align:center}
}
@media(max-width:480px){
.ar-social-grid{grid-template-columns:1fr}
.ar-presets{gap:4px}
.ar-preset{padding:5px 10px;font-size:0.72rem}
}
</style>

<div class="ar-wrap" id="arApp">

<div class="ar-hero">
<h1>Free <span>Aspect Ratio</span> Calculator</h1>
<p class="ar-intro">Enter width and height to find the simplified aspect ratio. Lock the ratio and resize in either direction. View common resolutions, social media dimensions, and calculate crop areas. Runs entirely in your browser.</p>
<div class="ar-updated">Last updated: March 19, 2026</div>
</div>

<!-- Main Calculator -->
<div class="ar-grid">
<div>

<div class="ar-card">
<h3>Dimensions</h3>

<div class="ar-dim-row">
<div class="ar-field">
<label for="arWidth">Width (px)</label>
<input type="number" id="arWidth" value="1920" min="1" step="1">
</div>
<button class="ar-lock-btn" id="arLockBtn" title="Lock aspect ratio">
<svg id="arLockIcon" width="20" height="20" viewBox="0 0 20 20" fill="none"><rect x="3" y="9" width="14" height="9" rx="2" stroke="currentColor" stroke-width="1.5" fill="none"/><path d="M6 9V6a4 4 0 0 1 8 0v3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" fill="none"/></svg>
</button>
<div class="ar-field">
<label for="arHeight">Height (px)</label>
<input type="number" id="arHeight" value="1080" min="1" step="1">
</div>
</div>
</div>

<div class="ar-result">
<p class="ar-result-label">Aspect Ratio</p>
<p class="ar-result-ratio" id="arRatioDisplay">16:9</p>
<p class="ar-result-decimal" id="arDecimalDisplay">1.7778</p>
</div>

<div class="ar-card">
<h3>Presets</h3>
<div class="ar-presets" id="arPresets">
<button class="ar-preset" data-w="16" data-h="9">16:9</button>
<button class="ar-preset" data-w="4" data-h="3">4:3</button>
<button class="ar-preset" data-w="1" data-h="1">1:1</button>
<button class="ar-preset" data-w="21" data-h="9">21:9</button>
<button class="ar-preset" data-w="9" data-h="16">9:16</button>
<button class="ar-preset" data-w="3" data-h="2">3:2</button>
<button class="ar-preset" data-w="5" data-h="4">5:4</button>
<button class="ar-preset" data-w="2" data-h="1">2:1</button>
</div>
</div>

</div>

<div>

<div class="ar-card">
<h3>Visual Preview</h3>
<div class="ar-preview-container" id="arPreviewContainer">
<div class="ar-preview-rect" id="arPreviewRect"><span id="arPreviewLabel">1920 x 1080</span></div>
</div>
</div>

<div class="ar-card">
<h3>Resolutions for this Ratio</h3>
<table class="ar-res-table">
<thead><tr><th>Name</th><th>Resolution</th></tr></thead>
<tbody id="arResBody"></tbody>
</table>
</div>

</div>
</div>

<!-- Social Media Sizes -->
<div class="ar-card">
<h3>Social Media Sizes</h3>
<div class="ar-social-grid" id="arSocialGrid"></div>
</div>

<!-- Crop Calculator -->
<div class="ar-card">
<h3>Crop Calculator</h3>
<p style="font-size:0.85rem;color:var(--ar-muted);margin:0 0 14px;">Enter source dimensions and a target aspect ratio to calculate the largest crop area that fits.</p>
<div class="ar-grid-3">
<div class="ar-field">
<label for="arCropSrcW">Source Width</label>
<input type="number" id="arCropSrcW" value="4000" min="1" step="1">
</div>
<div class="ar-field">
<label for="arCropSrcH">Source Height</label>
<input type="number" id="arCropSrcH" value="3000" min="1" step="1">
</div>
<div class="ar-field">
<label for="arCropTarget">Target Ratio</label>
<select id="arCropTarget">
<option value="16:9">16:9</option>
<option value="4:3">4:3</option>
<option value="1:1">1:1</option>
<option value="21:9">21:9</option>
<option value="9:16">9:16</option>
<option value="3:2">3:2</option>
<option value="5:4">5:4</option>
<option value="2:1">2:1</option>
</select>
</div>
</div>
<button class="ar-btn ar-btn-primary" id="arCropCalcBtn">Calculate Crop</button>
<div class="ar-crop-result" id="arCropResult">
<p>Crop size: <span class="ar-crop-val" id="arCropSize">-</span></p>
<p>Pixels removed: <span class="ar-crop-val" id="arCropRemoved">-</span></p>
<p>Offset: <span class="ar-crop-val" id="arCropOffset">-</span></p>
</div>
</div>

<!-- Cross Links -->
<div class="ar-cross-links">
<a href="/tools/image-compressor/" class="ar-cross-link">Image Compressor</a>
<a href="/tools/screenshot-mockup/" class="ar-cross-link">Screenshot Mockup</a>
<a href="/tools/unit-converter/" class="ar-cross-link">Unit Converter</a>
<a href="/tools/pixel-converter/" class="ar-cross-link">Pixel Converter</a>
</div>

<!-- SEO Content -->
<div class="ar-content">

<h2>What Is Aspect Ratio</h2>

<p>An aspect ratio describes the proportional relationship between the width and height of a rectangle. It is written as two numbers separated by a colon, such as 16:9 or 4:3. The first number represents the width, and the second represents the height. A 16:9 rectangle is 16 units wide for every 9 units tall, regardless of the actual size. A 1920x1080 screen and a 3840x2160 screen both share the 16:9 aspect ratio because their width-to-height proportions are identical.</p>

<p>Aspect ratios matter because they determine how content fits within a frame. A 16:9 video played inside a 4:3 container will show black bars (letterboxing) above and below the image. A 4:3 video inside a 16:9 frame will show bars on the sides (pillarboxing). Matching the aspect ratio of your content to the display area eliminates wasted space and avoids distortion.</p>

<p>To calculate an aspect ratio, divide both the width and the height by their greatest common divisor (GCD). For 1920x1080, the GCD is 120. Dividing both values by 120 gives 16:9. The calculator above performs this reduction automatically. For dimensions that do not simplify to familiar ratios, the tool shows the exact reduced form alongside the decimal equivalent.</p>

<h2>Common Aspect Ratios</h2>

<p>16:9 is the standard for modern displays, television broadcasts, and online video platforms. YouTube, Vimeo, and most streaming services expect 16:9 content. Resolutions include 1280x720 (HD), 1920x1080 (Full HD), 2560x1440 (QHD), 3840x2160 (4K UHD), and 7680x4320 (8K UHD). If you are creating video content or web graphics, 16:9 is the default starting point.</p>

<p>4:3 was the standard television aspect ratio before the widescreen transition. CRT monitors, early digital cameras, and standard-definition broadcasts used 4:3. It is still used in some presentation slides and iPad screens (though newer iPads have moved closer to 4:3 variants). Common 4:3 resolutions include 640x480, 800x600, 1024x768, and 2048x1536.</p>

<p>1:1 produces a square. Instagram popularized the square format for photo posts, and it remains common in social media, profile pictures, and album art. The standard size for Instagram square posts is 1080x1080 pixels.</p>

<p>21:9 (or more precisely 64:27 in cinema) is the ultrawide format. Ultrawide monitors typically run at 2560x1080 or 3440x1440. Cinematic films use similar wide ratios (2.39:1 or 2.35:1) to create an immersive horizontal field of view.</p>

<p>9:16 is 16:9 rotated to portrait orientation. It is the native format for smartphone screens held vertically and is required by TikTok, Instagram Reels, YouTube Shorts, and Snapchat. The standard resolution is 1080x1920.</p>

<p>3:2 is used by many DSLR cameras and some laptops (including several MacBook models and Microsoft Surface devices). It provides slightly more vertical space than 16:9 without reaching the boxy proportions of 4:3. Common resolutions include 2160x1440 and 3000x2000.</p>

<h2>Aspect Ratios for Social Media</h2>

<p>Each social media platform specifies recommended image dimensions for different content types. Using the correct dimensions prevents the platform from cropping or scaling your image in unexpected ways.</p>

<ul>
<li>Instagram Post: 1080x1080 (1:1), 1080x1350 (4:5 portrait), or 1080x566 (1.91:1 landscape)</li>
<li>Instagram Story / Reels: 1080x1920 (9:16)</li>
<li>Twitter/X Header: 1500x500 (3:1)</li>
<li>Twitter/X Post Image: 1200x675 (16:9)</li>
<li>Facebook Cover: 851x315 (approximately 2.7:1)</li>
<li>YouTube Thumbnail: 1280x720 (16:9)</li>
<li>LinkedIn Banner: 1584x396 (4:1)</li>
<li>Pinterest Pin: 1000x1500 (2:3)</li>
</ul>

<p>These dimensions change occasionally as platforms update their design. The sizes listed above reflect current specifications as of March 2026. When preparing assets for multiple platforms, create the largest version first (typically 4K or at least 2x the display size) and scale down for each target, preserving quality.</p>

<h2>How to Calculate Aspect Ratio</h2>

<p>The manual calculation involves finding the greatest common divisor of the width and height, then dividing both numbers by it. For example, take a 2560x1440 display. Start by finding the GCD of 2560 and 1440. Using the Euclidean algorithm: 2560 mod 1440 = 1120; 1440 mod 1120 = 320; 1120 mod 320 = 160; 320 mod 160 = 0. The GCD is 160. Divide both dimensions: 2560/160 = 16, 1440/160 = 9. The aspect ratio is 16:9.</p>

<p>For dimensions that do not reduce to a familiar ratio, the result may be a pair of larger numbers. A 1366x768 screen reduces to 683:384, which does not correspond to a standard named ratio. In practice, this resolution is treated as approximately 16:9 (the exact decimal is 1.7786, compared to 1.7778 for true 16:9). The calculator above shows both the exact simplified ratio and the decimal value so you can identify near-matches.</p>

<p>When resizing an image while preserving its aspect ratio, you only need to know one of the target dimensions. Multiply the known dimension by the ratio factor to get the other. If a 16:9 image needs to be 800 pixels wide, the height is 800 x (9/16) = 450 pixels. The lock feature in the calculator above automates this: enter one dimension and the other updates to match the locked ratio.</p>

</div>

<!-- FAQ -->
<div class="ar-faq" itemscope itemtype="https://schema.org/FAQPage">

<h2>Frequently Asked Questions</h2>

<div class="ar-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What aspect ratio is 1920x1080?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">1920x1080 has an aspect ratio of 16:9. This is the most common widescreen ratio, used by Full HD displays, most laptops, and the majority of video content on YouTube, Netflix, and other streaming platforms. Dividing both 1920 and 1080 by their greatest common divisor (120) gives 16 and 9.</p>
</div>
</div>

<div class="ar-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How do I resize an image without distortion?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Keep the aspect ratio constant. If the original image is 4000x3000 (4:3) and you need it to be 800 pixels wide, calculate the height as 800 x (3/4) = 600 pixels. Changing both width and height independently will stretch or squish the image. Use the lock feature in this calculator to automatically maintain the correct proportions when adjusting one dimension.</p>
</div>
</div>

<div class="ar-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is the best aspect ratio for YouTube videos?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">YouTube uses 16:9 as its default player ratio. Upload at 1920x1080 (1080p) or 3840x2160 (4K) for the best results. Videos with other ratios will play but may show black bars. For YouTube Shorts, use 9:16 vertical format at 1080x1920. YouTube thumbnails should be 1280x720 at 16:9.</p>
</div>
</div>

<div class="ar-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is the difference between 16:9 and 16:10?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">16:10 is slightly taller than 16:9. At the same width, a 16:10 display has about 11% more vertical pixels. Resolutions like 1920x1200 and 2560x1600 are 16:10. This ratio was common on early widescreen laptops and is used by some MacBook models. For video playback, 16:9 content on a 16:10 screen shows small black bars at the top and bottom.</p>
</div>
</div>

<div class="ar-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Why does my phone camera produce images at 4:3 instead of 16:9?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Most smartphone camera sensors are natively 4:3. When you select 16:9 mode in the camera app, the sensor crops the top and bottom of the frame rather than using a different sensor area. Shooting in 4:3 captures the full sensor area and produces the highest resolution image. You can crop to 16:9 afterward without losing data you might have wanted to keep.</p>
</div>
</div>

</div>

<!-- Author Box -->
<div class="ar-author-box">
<div class="ar-author-avatar">ML</div>
<div class="ar-author-info">
<p class="ar-author-name">Michael Lip</p>
<p class="ar-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
</div>
</div>

<footer class="ar-footer">
<p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
</footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Free Aspect Ratio Calculator",
      "url": "https://theluckystrike.github.io/tools/aspect-ratio-calculator/",
      "applicationCategory": "DesignApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "description": "Calculate and convert aspect ratios for images, video, and screens. Lock ratios, resize dimensions, see common resolutions, get social media sizes, and calculate crop areas.",
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Aspect Ratio Calculator", "item": "https://theluckystrike.github.io/tools/aspect-ratio-calculator/" }
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
          "name": "What aspect ratio is 1920x1080?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "1920x1080 has an aspect ratio of 16:9. This is the most common widescreen ratio, used by Full HD displays, most laptops, and the majority of video content on YouTube, Netflix, and other streaming platforms."
          }
        },
        {
          "@type": "Question",
          "name": "How do I resize an image without distortion?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Keep the aspect ratio constant. If the original image is 4000x3000 (4:3) and you need it to be 800 pixels wide, calculate the height as 800 x (3/4) = 600 pixels. Use the lock feature in this calculator to automatically maintain the correct proportions."
          }
        },
        {
          "@type": "Question",
          "name": "What is the best aspect ratio for YouTube videos?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "YouTube uses 16:9 as its default player ratio. Upload at 1920x1080 (1080p) or 3840x2160 (4K) for the best results. For YouTube Shorts, use 9:16 vertical format at 1080x1920."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between 16:9 and 16:10?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "16:10 is slightly taller than 16:9. At the same width, a 16:10 display has about 11% more vertical pixels. Resolutions like 1920x1200 and 2560x1600 are 16:10."
          }
        },
        {
          "@type": "Question",
          "name": "Why does my phone camera produce images at 4:3 instead of 16:9?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most smartphone camera sensors are natively 4:3. When you select 16:9 mode in the camera app, the sensor crops the top and bottom of the frame. Shooting in 4:3 captures the full sensor area and the highest resolution image."
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

// State
var locked = false;
var lockedRatioW = 16;
var lockedRatioH = 9;

// DOM
var widthInput = document.getElementById("arWidth");
var heightInput = document.getElementById("arHeight");
var ratioDisplay = document.getElementById("arRatioDisplay");
var decimalDisplay = document.getElementById("arDecimalDisplay");
var lockBtn = document.getElementById("arLockBtn");
var previewRect = document.getElementById("arPreviewRect");
var previewLabel = document.getElementById("arPreviewLabel");
var previewContainer = document.getElementById("arPreviewContainer");
var resBody = document.getElementById("arResBody");
var socialGrid = document.getElementById("arSocialGrid");
var presetsContainer = document.getElementById("arPresets");

// GCD
function gcd(a, b) {
  a = Math.abs(Math.round(a));
  b = Math.abs(Math.round(b));
  while (b) { var t = b; b = a % b; a = t; }
  return a;
}

// Resolution database by ratio key
var RESOLUTIONS = {
  "16:9": [
    ["nHD", "640x360"],
    ["HD", "1280x720"],
    ["Full HD", "1920x1080"],
    ["QHD", "2560x1440"],
    ["4K UHD", "3840x2160"],
    ["8K UHD", "7680x4320"]
  ],
  "4:3": [
    ["VGA", "640x480"],
    ["SVGA", "800x600"],
    ["XGA", "1024x768"],
    ["SXGA+", "1400x1050"],
    ["UXGA", "1600x1200"],
    ["QXGA", "2048x1536"]
  ],
  "1:1": [
    ["Small", "256x256"],
    ["Medium", "512x512"],
    ["Instagram", "1080x1080"],
    ["Large", "2048x2048"],
    ["4K Square", "4096x4096"]
  ],
  "21:9": [
    ["UWHD", "2560x1080"],
    ["UWQHD", "3440x1440"],
    ["UW5K", "5120x2160"]
  ],
  "9:16": [
    ["Mobile SD", "360x640"],
    ["Mobile HD", "720x1280"],
    ["Mobile FHD", "1080x1920"],
    ["Mobile QHD", "1440x2560"]
  ],
  "3:2": [
    ["WQXGA", "2160x1440"],
    ["Surface", "2736x1824"],
    ["3K", "3000x2000"],
    ["Retina", "3240x2160"]
  ],
  "5:4": [
    ["SXGA", "1280x1024"],
    ["QSXGA", "2560x2048"]
  ],
  "2:1": [
    ["Univisium", "1998x999"],
    ["Wide 1080", "2160x1080"],
    ["Wide 4K", "4320x2160"]
  ]
};

// Social media sizes
var SOCIAL = [
  { name: "Instagram Post", w: 1080, h: 1080, ratio: "1:1" },
  { name: "Instagram Portrait", w: 1080, h: 1350, ratio: "4:5" },
  { name: "Instagram Story", w: 1080, h: 1920, ratio: "9:16" },
  { name: "Twitter/X Header", w: 1500, h: 500, ratio: "3:1" },
  { name: "Twitter/X Post", w: 1200, h: 675, ratio: "16:9" },
  { name: "Facebook Cover", w: 851, h: 315, ratio: "2.7:1" },
  { name: "YouTube Thumbnail", w: 1280, h: 720, ratio: "16:9" },
  { name: "LinkedIn Banner", w: 1584, h: 396, ratio: "4:1" },
  { name: "Pinterest Pin", w: 1000, h: 1500, ratio: "2:3" },
  { name: "TikTok Video", w: 1080, h: 1920, ratio: "9:16" },
  { name: "Snapchat Ad", w: 1080, h: 1920, ratio: "9:16" },
  { name: "Facebook Post", w: 1200, h: 630, ratio: "1.91:1" }
];

function calcRatio() {
  var w = parseInt(widthInput.value) || 0;
  var h = parseInt(heightInput.value) || 0;
  if (w <= 0 || h <= 0) {
    ratioDisplay.textContent = "-";
    decimalDisplay.textContent = "";
    return;
  }

  var d = gcd(w, h);
  var rw = w / d;
  var rh = h / d;
  ratioDisplay.textContent = rw + ":" + rh;
  decimalDisplay.textContent = (w / h).toFixed(4);

  updatePreview(w, h);
  updateResolutions(rw, rh);
  updatePresetActive(rw, rh);
}

function updatePreview(w, h) {
  var containerW = previewContainer.clientWidth - 40;
  var containerH = 180;
  var scale = Math.min(containerW / w, containerH / h, 1);
  var drawW = Math.max(Math.round(w * scale), 30);
  var drawH = Math.max(Math.round(h * scale), 30);

  // Ensure minimum visible size
  if (drawW < 30 || drawH < 30) {
    var ratio = w / h;
    if (ratio >= 1) {
      drawW = Math.min(containerW, 260);
      drawH = Math.round(drawW / ratio);
      if (drawH < 20) drawH = 20;
    } else {
      drawH = Math.min(containerH, 180);
      drawW = Math.round(drawH * ratio);
      if (drawW < 20) drawW = 20;
    }
  }

  previewRect.style.width = drawW + "px";
  previewRect.style.height = drawH + "px";
  previewLabel.textContent = w + " x " + h;
}

function updateResolutions(rw, rh) {
  var key = rw + ":" + rh;
  resBody.innerHTML = "";

  var resolutions = RESOLUTIONS[key];
  if (!resolutions) {
    var tr = document.createElement("tr");
    var td = document.createElement("td");
    td.colSpan = 2;
    td.textContent = "No standard resolutions for " + key;
    td.style.textAlign = "center";
    td.style.fontFamily = "Inter, sans-serif";
    tr.appendChild(td);
    resBody.appendChild(tr);
    return;
  }

  for (var i = 0; i < resolutions.length; i++) {
    var tr = document.createElement("tr");
    var td1 = document.createElement("td");
    td1.textContent = resolutions[i][0];
    td1.style.fontFamily = "Inter, sans-serif";
    var td2 = document.createElement("td");
    td2.textContent = resolutions[i][1];
    tr.appendChild(td1);
    tr.appendChild(td2);
    resBody.appendChild(tr);
  }
}

function updatePresetActive(rw, rh) {
  var btns = presetsContainer.querySelectorAll(".ar-preset");
  for (var i = 0; i < btns.length; i++) {
    var pw = parseInt(btns[i].getAttribute("data-w"));
    var ph = parseInt(btns[i].getAttribute("data-h"));
    if (pw === rw && ph === rh) {
      btns[i].classList.add("active");
    } else {
      btns[i].classList.remove("active");
    }
  }
}

// Build social grid
function buildSocialGrid() {
  socialGrid.innerHTML = "";
  for (var i = 0; i < SOCIAL.length; i++) {
    var s = SOCIAL[i];
    var div = document.createElement("div");
    div.className = "ar-social-item";
    div.setAttribute("data-w", s.w);
    div.setAttribute("data-h", s.h);
    div.innerHTML = '<p class="ar-social-name">' + s.name + '</p>' +
                    '<p class="ar-social-size">' + s.w + ' x ' + s.h + '</p>' +
                    '<p class="ar-social-ratio">' + s.ratio + '</p>';
    div.addEventListener("click", function() {
      var sw = parseInt(this.getAttribute("data-w"));
      var sh = parseInt(this.getAttribute("data-h"));
      widthInput.value = sw;
      heightInput.value = sh;
      locked = false;
      lockBtn.classList.remove("locked");
      calcRatio();
    });
    socialGrid.appendChild(div);
  }
}

// Lock toggle
lockBtn.addEventListener("click", function() {
  locked = !locked;
  if (locked) {
    lockBtn.classList.add("locked");
    var w = parseInt(widthInput.value) || 1;
    var h = parseInt(heightInput.value) || 1;
    lockedRatioW = w;
    lockedRatioH = h;
  } else {
    lockBtn.classList.remove("locked");
  }
});

// Width input
widthInput.addEventListener("input", function() {
  if (locked) {
    var w = parseInt(widthInput.value) || 0;
    if (w > 0) {
      heightInput.value = Math.round(w * lockedRatioH / lockedRatioW);
    }
  }
  calcRatio();
});

// Height input
heightInput.addEventListener("input", function() {
  if (locked) {
    var h = parseInt(heightInput.value) || 0;
    if (h > 0) {
      widthInput.value = Math.round(h * lockedRatioW / lockedRatioH);
    }
  }
  calcRatio();
});

// Preset clicks
var presetBtns = presetsContainer.querySelectorAll(".ar-preset");
for (var i = 0; i < presetBtns.length; i++) {
  presetBtns[i].addEventListener("click", function() {
    var pw = parseInt(this.getAttribute("data-w"));
    var ph = parseInt(this.getAttribute("data-h"));
    // Set to a common resolution for this ratio
    var key = pw + ":" + ph;
    if (RESOLUTIONS[key] && RESOLUTIONS[key].length > 0) {
      // Pick FHD-range resolution
      var picked = RESOLUTIONS[key][0];
      for (var j = 0; j < RESOLUTIONS[key].length; j++) {
        var parts = RESOLUTIONS[key][j][1].split("x");
        var rw = parseInt(parts[0]);
        if (rw >= 1000 && rw <= 2000) {
          picked = RESOLUTIONS[key][j];
          break;
        }
      }
      var parts = picked[1].split("x");
      widthInput.value = parts[0];
      heightInput.value = parts[1];
    } else {
      // Scale to roughly 1080 width
      var scale = Math.round(1080 / pw);
      if (scale < 1) scale = 1;
      widthInput.value = pw * scale;
      heightInput.value = ph * scale;
    }
    locked = false;
    lockBtn.classList.remove("locked");
    calcRatio();
  });
}

// Crop calculator
var cropBtn = document.getElementById("arCropCalcBtn");
var cropResult = document.getElementById("arCropResult");
var cropSize = document.getElementById("arCropSize");
var cropRemoved = document.getElementById("arCropRemoved");
var cropOffset = document.getElementById("arCropOffset");

cropBtn.addEventListener("click", function() {
  var srcW = parseInt(document.getElementById("arCropSrcW").value) || 0;
  var srcH = parseInt(document.getElementById("arCropSrcH").value) || 0;
  var target = document.getElementById("arCropTarget").value;

  if (srcW <= 0 || srcH <= 0) return;

  var parts = target.split(":");
  var tw = parseFloat(parts[0]);
  var th = parseFloat(parts[1]);
  var targetRatio = tw / th;

  var cropW, cropH;
  if (srcW / srcH > targetRatio) {
    // Source is wider, crop width
    cropH = srcH;
    cropW = Math.round(srcH * targetRatio);
  } else {
    // Source is taller, crop height
    cropW = srcW;
    cropH = Math.round(srcW / targetRatio);
  }

  var removedPixels = (srcW * srcH) - (cropW * cropH);
  var offsetX = Math.round((srcW - cropW) / 2);
  var offsetY = Math.round((srcH - cropH) / 2);

  cropSize.textContent = cropW + " x " + cropH + " px";
  cropRemoved.textContent = removedPixels.toLocaleString() + " px (" + ((removedPixels / (srcW * srcH)) * 100).toFixed(1) + "%)";
  cropOffset.textContent = "x: " + offsetX + "px, y: " + offsetY + "px (centered)";
  cropResult.style.display = "block";
});

// Init
buildSocialGrid();
calcRatio();

})();
</script>
