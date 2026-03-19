---
layout: page
title: "Free Image Compressor — Reduce File Size Without Quality Loss | Zovo"
description: "Compress images online for free. Reduce JPEG, PNG, and WebP file sizes using client-side Canvas API. Adjust quality, resize dimensions, and batch process multiple images. No uploads to any server."
permalink: /tools/image-compressor/
keywords: "image compressor, compress image online, reduce image size, image optimizer, jpeg compressor, png compressor, webp converter, image resizer, bulk image compression"
date: 2026-03-19
categories: [tools]
tags: [image, compressor, optimizer, jpeg, png, webp, resize, compression]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root{--ic-primary:#6C5CE7;--ic-primary-dark:#5A4BD1;--ic-primary-light:#A29BFE;--ic-green:#00ff88;--ic-green-dark:#00dd77;--ic-bg:#0a0a0f;--ic-surface:#12121a;--ic-surface2:#1a1a28;--ic-border:#1e1e2e;--ic-border2:#2a2a3e;--ic-text:#e0e0e0;--ic-muted:#8888aa;--ic-radius:12px;--ic-red:#ff4757}
.ic-wrap{font-family:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;color:var(--ic-text);max-width:1100px;margin:0 auto;padding:0 16px;line-height:1.6}
.ic-wrap *{box-sizing:border-box}
.ic-hero{text-align:center;padding:40px 0 28px}
.ic-hero h1{font-size:2.2rem;font-weight:700;color:var(--ic-text);margin:0 0 16px;line-height:1.2}
.ic-hero h1 span{color:var(--ic-primary)}
.ic-intro{font-size:1.02rem;color:var(--ic-muted);max-width:700px;margin:0 auto;line-height:1.7}

/* Privacy badge */
.ic-privacy{display:inline-flex;align-items:center;gap:8px;padding:8px 16px;background:rgba(0,255,136,0.08);border:1px solid rgba(0,255,136,0.2);border-radius:20px;font-size:0.82rem;color:var(--ic-green);margin-top:16px}
.ic-privacy svg{flex-shrink:0}

/* Drop zone */
.ic-dropzone{border:2px dashed var(--ic-border2);border-radius:var(--ic-radius);padding:52px 24px;text-align:center;cursor:pointer;transition:border-color 0.2s,background 0.2s;margin-bottom:24px;position:relative;background:var(--ic-surface)}
.ic-dropzone:hover,.ic-dropzone.dragover{border-color:var(--ic-primary);background:rgba(108,92,231,0.06)}
.ic-dropzone input[type="file"]{position:absolute;inset:0;opacity:0;cursor:pointer}
.ic-dropzone-icon{display:block;margin:0 auto 12px}
.ic-dropzone-title{font-size:1.1rem;font-weight:600;color:var(--ic-text);margin:0 0 6px}
.ic-dropzone-hint{font-size:0.85rem;color:var(--ic-muted);margin:0}

/* Controls panel */
.ic-controls{background:var(--ic-surface);border:1px solid var(--ic-border);border-radius:var(--ic-radius);padding:20px;margin-bottom:24px;display:none}
.ic-controls-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px}
.ic-field{margin-bottom:0}
.ic-field label{display:block;font-size:0.78rem;font-weight:600;color:var(--ic-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:6px}
.ic-field select,.ic-field input[type="number"]{width:100%;font-family:'Inter',sans-serif;font-size:0.9rem;padding:9px 12px;border:1.5px solid var(--ic-border);border-radius:8px;background:var(--ic-bg);color:var(--ic-text);outline:none;transition:border-color 0.2s}
.ic-field select:focus,.ic-field input[type="number"]:focus{border-color:var(--ic-primary);box-shadow:0 0 0 3px rgba(108,92,231,0.15)}
.ic-field select{appearance:auto}

/* Quality slider */
.ic-slider-row{margin-bottom:0}
.ic-slider-row label{display:flex;justify-content:space-between;font-size:0.78rem;font-weight:600;color:var(--ic-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:6px}
.ic-slider-row label span{color:var(--ic-primary);font-weight:700;font-family:'JetBrains Mono',monospace}
.ic-slider-row input[type="range"]{width:100%;accent-color:var(--ic-primary);height:6px;cursor:pointer}

/* Checkbox row */
.ic-check-row{display:flex;align-items:center;gap:8px;margin-top:6px}
.ic-check-row input[type="checkbox"]{accent-color:var(--ic-primary);width:16px;height:16px;cursor:pointer}
.ic-check-row label{font-size:0.85rem;color:var(--ic-muted);cursor:pointer}

/* Batch actions */
.ic-batch-bar{display:none;align-items:center;justify-content:space-between;gap:12px;margin-bottom:20px;padding:14px 18px;background:var(--ic-surface);border:1px solid var(--ic-border);border-radius:var(--ic-radius);flex-wrap:wrap}
.ic-batch-info{font-size:0.88rem;color:var(--ic-muted)}
.ic-batch-info strong{color:var(--ic-green);font-family:'JetBrains Mono',monospace}
.ic-batch-actions{display:flex;gap:8px;flex-wrap:wrap}

/* Buttons */
.ic-btn{display:inline-flex;align-items:center;gap:6px;padding:9px 18px;border:none;border-radius:8px;font-family:'Inter',sans-serif;font-size:0.85rem;font-weight:600;cursor:pointer;transition:all 0.15s;white-space:nowrap}
.ic-btn-primary{background:var(--ic-primary);color:#fff}
.ic-btn-primary:hover{background:var(--ic-primary-dark)}
.ic-btn-green{background:var(--ic-green);color:#0a0a0f;font-weight:700}
.ic-btn-green:hover{background:var(--ic-green-dark)}
.ic-btn-outline{background:transparent;color:var(--ic-primary);border:1.5px solid var(--ic-primary)}
.ic-btn-outline:hover{background:rgba(108,92,231,0.1)}
.ic-btn-sm{padding:6px 12px;font-size:0.78rem}
.ic-btn-red{background:transparent;color:var(--ic-red);border:1.5px solid var(--ic-red)}
.ic-btn-red:hover{background:rgba(255,71,87,0.1)}

/* Results list */
.ic-results{display:flex;flex-direction:column;gap:16px;margin-bottom:24px}

/* Single result card */
.ic-result-card{background:var(--ic-surface);border:1px solid var(--ic-border);border-radius:var(--ic-radius);overflow:hidden}
.ic-result-header{display:flex;align-items:center;justify-content:space-between;padding:12px 16px;border-bottom:1px solid var(--ic-border);background:var(--ic-bg)}
.ic-result-filename{font-size:0.85rem;color:var(--ic-text);font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;max-width:300px}
.ic-result-actions{display:flex;gap:6px;align-items:center}
.ic-result-remove{background:none;border:none;color:var(--ic-muted);cursor:pointer;padding:4px;font-size:1rem;line-height:1;transition:color 0.15s}
.ic-result-remove:hover{color:var(--ic-red)}

/* Preview comparison */
.ic-preview-wrap{position:relative;overflow:hidden;height:280px;cursor:col-resize;user-select:none;background:var(--ic-bg)}
.ic-preview-wrap img{position:absolute;top:0;left:0;width:100%;height:100%;object-fit:contain}
.ic-preview-original{z-index:1}
.ic-preview-compressed{z-index:2}
.ic-preview-slider{position:absolute;top:0;bottom:0;width:3px;background:var(--ic-primary);z-index:3;cursor:col-resize}
.ic-preview-slider::after{content:'';position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);width:28px;height:28px;background:var(--ic-primary);border-radius:50%;border:2px solid #fff;box-shadow:0 2px 8px rgba(0,0,0,0.4)}
.ic-preview-label{position:absolute;top:8px;padding:3px 10px;font-size:0.7rem;font-weight:600;text-transform:uppercase;letter-spacing:0.5px;border-radius:4px;z-index:4;pointer-events:none}
.ic-preview-label-orig{left:8px;background:rgba(136,136,170,0.8);color:#fff}
.ic-preview-label-comp{right:8px;background:rgba(108,92,231,0.8);color:#fff}

/* Stats row */
.ic-stats{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--ic-border);border-top:1px solid var(--ic-border)}
.ic-stat{background:var(--ic-surface);padding:12px 14px;text-align:center}
.ic-stat-label{font-size:0.68rem;text-transform:uppercase;letter-spacing:0.5px;color:var(--ic-muted);margin-bottom:3px}
.ic-stat-value{font-family:'JetBrains Mono',monospace;font-size:0.88rem;font-weight:600;color:var(--ic-text)}
.ic-stat-value.ic-savings{color:var(--ic-green)}

/* Content */
.ic-content{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--ic-border)}
.ic-content h2{font-size:1.4rem;font-weight:700;color:var(--ic-text);margin:32px 0 12px}
.ic-content h2:first-child{margin-top:0}
.ic-content p{font-size:0.95rem;color:var(--ic-muted);line-height:1.75;margin:0 0 14px}
.ic-content ul,.ic-content ol{margin:0 0 14px;padding-left:20px;color:var(--ic-muted);font-size:0.95rem;line-height:1.75}
.ic-content ul li,.ic-content ol li{margin-bottom:6px}
.ic-content table{width:100%;border-collapse:collapse;margin:0 0 14px}
.ic-content th,.ic-content td{padding:10px 14px;text-align:left;font-size:0.88rem;border:1px solid var(--ic-border)}
.ic-content th{background:var(--ic-surface);color:var(--ic-text);font-weight:600;font-size:0.78rem;text-transform:uppercase;letter-spacing:0.5px}
.ic-content td{color:var(--ic-muted)}

/* FAQ */
.ic-faq{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--ic-border)}
.ic-faq h2{font-size:1.4rem;font-weight:700;color:var(--ic-text);margin:0 0 20px}
.ic-faq-item{border:1px solid var(--ic-border);border-radius:var(--ic-radius);padding:18px 22px;margin-bottom:12px;background:var(--ic-surface)}
.ic-faq-item h3{font-size:1rem;font-weight:600;margin:0 0 8px;color:var(--ic-text)}
.ic-faq-item p{margin:0;font-size:0.92rem;color:var(--ic-muted);line-height:1.7}

/* Responsive */
@media(max-width:768px){
.ic-hero h1{font-size:1.6rem}
.ic-controls-grid{grid-template-columns:1fr}
.ic-stats{grid-template-columns:repeat(2,1fr)}
.ic-preview-wrap{height:200px}
.ic-batch-bar{flex-direction:column;text-align:center}
.ic-dropzone{padding:36px 16px}
.ic-result-filename{max-width:160px}
}
@media(max-width:480px){
.ic-stats{grid-template-columns:1fr 1fr}
.ic-result-header{flex-direction:column;gap:8px;align-items:flex-start}
}
</style>

<div class="ic-wrap" id="icApp">

<div class="ic-hero">
<h1>Free <span>Image Compressor</span></h1>
<p class="ic-intro">Reduce JPEG, PNG, and WebP file sizes without uploading anything. Adjust quality, resize dimensions, convert formats, and batch process multiple images. Everything runs locally in your browser using the Canvas API.</p>
<div class="ic-privacy">
<svg width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M8 1L2 4v4c0 3.5 2.6 6.4 6 7 3.4-.6 6-3.5 6-7V4L8 1z" stroke="currentColor" stroke-width="1.5" fill="none"/><path d="M5.5 8l2 2 3.5-3.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
Your images never leave your browser
</div>
</div>

<p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

<!-- Drop zone -->
<div class="ic-dropzone" id="icDropzone">
<svg class="ic-dropzone-icon" width="48" height="48" viewBox="0 0 48 48" fill="none"><rect x="6" y="10" width="36" height="28" rx="4" stroke="#6C5CE7" stroke-width="2.5" fill="none"/><circle cx="18" cy="22" r="4" stroke="#6C5CE7" stroke-width="2"/><path d="M6 34l10-10 8 8 6-6 12 12" stroke="#6C5CE7" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" fill="none"/><path d="M24 4v6M24 4l-3 3M24 4l3 3" stroke="#A29BFE" stroke-width="2" stroke-linecap="round"/></svg>
<p class="ic-dropzone-title">Drop images here or click to browse</p>
<p class="ic-dropzone-hint">Supports JPEG, PNG, WebP, GIF, BMP, TIFF -- select multiple files at once</p>
<input type="file" id="icFileInput" accept="image/*" multiple>
</div>

<!-- Controls -->
<div class="ic-controls" id="icControls">
<div class="ic-controls-grid">
<div class="ic-slider-row">
<label>Quality <span id="icQualityVal">80%</span></label>
<input type="range" id="icQuality" min="1" max="100" value="80">
</div>
<div class="ic-field">
<label>Output Format</label>
<select id="icFormat">
<option value="image/jpeg">JPEG</option>
<option value="image/png">PNG</option>
<option value="image/webp">WebP</option>
</select>
</div>
<div class="ic-field">
<label>Max Width (px)</label>
<input type="number" id="icMaxWidth" placeholder="Original" min="1" max="10000">
</div>
<div class="ic-field">
<label>Max Height (px)</label>
<input type="number" id="icMaxHeight" placeholder="Original" min="1" max="10000">
</div>
<div class="ic-field">
<label>Scale (%)</label>
<input type="number" id="icScale" placeholder="100" min="1" max="200" value="">
</div>
<div style="display:flex;flex-direction:column;justify-content:flex-end">
<div class="ic-check-row">
<input type="checkbox" id="icAspect" checked>
<label for="icAspect">Maintain aspect ratio</label>
</div>
</div>
</div>
<div style="margin-top:16px;display:flex;gap:8px;flex-wrap:wrap">
<button class="ic-btn ic-btn-primary" onclick="icRecompress()">Re-compress All</button>
<button class="ic-btn ic-btn-outline" onclick="icResetSettings()">Reset Settings</button>
</div>
</div>

<!-- Batch summary bar -->
<div class="ic-batch-bar" id="icBatchBar">
<div class="ic-batch-info" id="icBatchInfo">
<span id="icBatchCount">0</span> images | Saved <strong id="icBatchSaved">0 KB</strong> | Avg compression <strong id="icBatchRatio">0%</strong>
</div>
<div class="ic-batch-actions">
<button class="ic-btn ic-btn-green ic-btn-sm" onclick="icDownloadAll()">Download All (.zip)</button>
<button class="ic-btn ic-btn-red ic-btn-sm" onclick="icClearAll()">Clear All</button>
</div>
</div>

<!-- Results -->
<div class="ic-results" id="icResults"></div>

<!-- Content section -->
<div class="ic-content">

<h2>What Is Image Compression</h2>

<p>Image compression reduces file size by removing redundant or less important data from an image. Every digital photo contains far more information than the human eye can distinguish, especially in areas with gradual color transitions or fine grain detail. Compression algorithms identify and discard this excess data, or represent it more efficiently, to produce a smaller file that still looks acceptable at normal viewing sizes.</p>

<p>There are two broad categories: lossy and lossless. Both serve different purposes depending on whether you prioritize file size or pixel-perfect accuracy. The right choice depends on where the image will be used and how much quality reduction is tolerable for your use case.</p>

<h2>Lossy vs Lossless Compression</h2>

<p>Lossy compression permanently removes data to achieve smaller files. When you export a JPEG at 80% quality, the encoder analyzes 8x8 pixel blocks using the discrete cosine transform (DCT), quantizes the frequency coefficients, and throws away the high-frequency detail that contributes least to perceived quality. The result is a file that can be 10-20x smaller than the raw pixel data, with artifacts that are barely visible at moderate quality settings.</p>

<p>Lossless compression preserves every single pixel exactly. PNG uses the DEFLATE algorithm -- a combination of LZ77 dictionary matching and Huffman coding -- to represent the same pixel data in fewer bytes. The trade-off is that lossless files are significantly larger than lossy equivalents, typically achieving only 2-3x compression on photographic content. Lossless compression works best on images with large areas of flat color, like screenshots, diagrams, and logos.</p>

<p>The practical difference: a 5 MB photograph compressed to JPEG at 80% quality might be 400 KB. The same image saved as a lossless PNG would be around 3.5 MB. For web publishing, lossy compression at the right quality level produces files that load faster with no visible difference at normal screen sizes.</p>

<h2>JPEG vs PNG vs WebP</h2>

<table>
<thead>
<tr><th>Format</th><th>Type</th><th>Best For</th><th>Transparency</th><th>Browser Support</th></tr>
</thead>
<tbody>
<tr><td>JPEG</td><td>Lossy</td><td>Photographs, gradients, complex scenes</td><td>No</td><td>Universal</td></tr>
<tr><td>PNG</td><td>Lossless</td><td>Screenshots, logos, text, UI elements</td><td>Yes (alpha)</td><td>Universal</td></tr>
<tr><td>WebP</td><td>Both</td><td>All web images (best overall compression)</td><td>Yes (alpha)</td><td>96%+ browsers</td></tr>
</tbody>
</table>

<p>JPEG remains the default for photographic content due to universal support and predictable quality-to-size ratios. PNG is the standard for anything that requires transparency or pixel-exact reproduction. WebP, developed by Google and based on the VP8 video codec, typically produces files 25-35% smaller than JPEG at equivalent visual quality, and supports both lossy and lossless modes with alpha transparency. As of 2026, WebP is supported by every major browser including Safari, Chrome, Firefox, and Edge.</p>

<h2>How This Tool Compresses Images</h2>

<p>This compressor uses the HTML5 Canvas API, which is built into every modern browser. The process works in four steps:</p>

<ol>
<li>The FileReader API loads your selected image into memory as a data URL. No network request is made -- the file stays entirely within your browser's process.</li>
<li>An off-screen Image element decodes the pixel data. If you set resize options, the tool calculates new dimensions while respecting the aspect ratio constraint.</li>
<li>A Canvas element is created at the target dimensions. The image is drawn onto the canvas using drawImage(), which handles the resampling when scaling.</li>
<li>The canvas calls toBlob() with your selected format and quality parameter. For JPEG and WebP, the quality value (0.0 to 1.0) controls the quantization level. For PNG, the browser re-encodes the pixel data losslessly -- the main size savings come from switching format or reducing dimensions.</li>
</ol>

<p>The before-and-after preview lets you visually compare quality at different compression levels. Drag the slider left and right to see exactly where compression artifacts appear, which helps you find the lowest file size that meets your quality threshold.</p>

<h2>Optimal Image Sizes for Web</h2>

<p>Serving correctly sized images is one of the most impactful performance optimizations for any website. Google's Core Web Vitals metrics, particularly Largest Contentful Paint (LCP), are directly affected by image file sizes. These are general guidelines for common image use cases:</p>

<ul>
<li>Hero images and full-width banners: 1200-1600px wide, JPEG/WebP at 75-85% quality, target under 200 KB</li>
<li>Blog post images: 800-1000px wide, JPEG/WebP at 80% quality, target under 100 KB</li>
<li>Thumbnail galleries: 300-400px wide, JPEG/WebP at 70-80% quality, target under 30 KB</li>
<li>Product photos (e-commerce): 800-1200px wide, JPEG/WebP at 85% quality for detail retention</li>
<li>Icons and logos: SVG when possible, otherwise PNG at the exact display size</li>
<li>Social media sharing images: 1200x630px (Open Graph), JPEG at 80% quality</li>
</ul>

<p>A rule of thumb: if your page loads more than 1 MB of total image data, there is room to optimize. This tool lets you experiment with quality settings and dimensions to find the right balance for each image without needing to install desktop software or upload files to a third-party service.</p>

</div>

<!-- FAQ -->
<div class="ic-faq">
<h2>Frequently Asked Questions</h2>

<div class="ic-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Are my images uploaded to a server when I use this tool?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">No. Every step of the compression process runs locally in your browser using the Canvas API. Your images are never sent over the network. The file data stays in your browser's memory and is discarded when you close the tab or clear the images. This makes the tool safe for sensitive or private photos.</p>
</div>
</div>

<div class="ic-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is the best quality setting for web images?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">For most web usage, 75-85% quality provides a good balance between file size and visual fidelity. Below 70%, JPEG and WebP artifacts become noticeable on close inspection, particularly around sharp edges and text. Above 90%, file sizes increase significantly with minimal visible improvement. Use the before-and-after slider to compare at different quality levels and find the threshold for your specific image.</p>
</div>
</div>

<div class="ic-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Why does PNG compression produce larger files than JPEG?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">PNG is a lossless format, meaning it preserves every pixel exactly. For photographic images with complex color gradients, lossless encoding simply cannot match the compression ratios of lossy formats like JPEG or WebP. If you convert a photograph from JPEG to PNG, the file will almost always grow larger. PNG compression is most effective on images with large areas of identical color, such as screenshots, diagrams, and vector-style graphics. Use PNG when you need transparency or exact reproduction, and JPEG or WebP when file size matters more.</p>
</div>
</div>

<div class="ic-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Can I compress multiple images at once?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Yes. Select multiple files from the file picker, or drag and drop a batch of images onto the drop zone. Each image is processed individually with the same quality, format, and resize settings. The batch summary bar shows the total space saved and average compression ratio. You can download each compressed image individually or use the Download All button to get a ZIP archive containing every result.</p>
</div>
</div>

<div class="ic-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Should I use WebP instead of JPEG for my website?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">In most cases, yes. WebP produces files 25-35% smaller than JPEG at equivalent visual quality, and it supports alpha transparency. As of 2026, browser support exceeds 96%, covering Chrome, Firefox, Safari, Edge, and all major mobile browsers. The main reason to keep JPEG is if you need to support very old browsers or email clients that do not render WebP. For modern websites, WebP is the better default choice.</p>
</div>
</div>

<div class="ic-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Does resizing an image before compression help reduce file size?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Significantly. Reducing dimensions has a multiplicative effect on file size because the number of pixels scales with width times height. Halving both dimensions reduces the pixel count by 75%, which typically results in a file that is 3-4x smaller even before quality compression is applied. If your images are larger than the display size on your website, resizing them to the actual rendered dimensions is the single most effective optimization you can make.</p>
</div>
</div>

</div>

<!-- Related Tools -->
<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/qr-code-generator/" style="color:#00ff88;text-decoration:none;">QR Code Generator</a> - Create custom QR codes with colors and logos</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/color-picker/" style="color:#00ff88;text-decoration:none;">Color Picker from Image</a> - Extract hex, RGB, and HSL codes from any photo</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/color-palette-generator/" style="color:#00ff88;text-decoration:none;">Color Palette Generator</a> - Generate harmonious color schemes for design</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/base64-encoder-decoder/" style="color:#00ff88;text-decoration:none;">Base64 Encoder/Decoder</a> - Encode images and files to Base64 strings</li>
</ul>
</div>

<!-- Author box -->
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

var dropzone=document.getElementById("icDropzone");
var fileInput=document.getElementById("icFileInput");
var controlsEl=document.getElementById("icControls");
var resultsEl=document.getElementById("icResults");
var batchBar=document.getElementById("icBatchBar");
var qualitySlider=document.getElementById("icQuality");
var qualityVal=document.getElementById("icQualityVal");
var formatSelect=document.getElementById("icFormat");
var maxWidthInput=document.getElementById("icMaxWidth");
var maxHeightInput=document.getElementById("icMaxHeight");
var scaleInput=document.getElementById("icScale");
var aspectCheck=document.getElementById("icAspect");

var imageItems=[];
var zipScriptLoaded=false;

// Quality slider display
qualitySlider.addEventListener("input",function(){
qualityVal.textContent=this.value+"%";
});

// File input
fileInput.addEventListener("change",function(){
if(this.files&&this.files.length){handleFiles(this.files);}
});

// Drag and drop
dropzone.addEventListener("dragover",function(e){
e.preventDefault();
dropzone.classList.add("dragover");
});
dropzone.addEventListener("dragleave",function(){
dropzone.classList.remove("dragover");
});
dropzone.addEventListener("drop",function(e){
e.preventDefault();
dropzone.classList.remove("dragover");
if(e.dataTransfer.files&&e.dataTransfer.files.length){
handleFiles(e.dataTransfer.files);
}
});

// Paste support
document.addEventListener("paste",function(e){
var items=e.clipboardData&&e.clipboardData.items;
if(!items)return;
var files=[];
for(var i=0;i<items.length;i++){
if(items[i].type.match(/^image\//)){
files.push(items[i].getAsFile());
}
}
if(files.length){e.preventDefault();handleFiles(files);}
});

function handleFiles(fileList){
var files=Array.from(fileList).filter(function(f){return f.type.match(/^image\//);});
if(!files.length)return;
controlsEl.style.display="block";
files.forEach(function(f){processFile(f);});
}

function getSettings(){
return{
quality:parseInt(qualitySlider.value)/100,
format:formatSelect.value,
maxWidth:maxWidthInput.value?parseInt(maxWidthInput.value):0,
maxHeight:maxHeightInput.value?parseInt(maxHeightInput.value):0,
scale:scaleInput.value?parseInt(scaleInput.value)/100:0,
keepAspect:aspectCheck.checked
};
}

function formatBytes(b){
if(b<1024)return b+" B";
if(b<1048576)return(b/1024).toFixed(1)+" KB";
return(b/1048576).toFixed(2)+" MB";
}

function formatExt(mime){
if(mime==="image/jpeg")return".jpg";
if(mime==="image/png")return".png";
if(mime==="image/webp")return".webp";
return".jpg";
}

function calcDimensions(origW,origH,s){
var w=origW,h=origH;
// Apply scale first
if(s.scale>0&&s.scale!==1){
w=Math.round(w*s.scale);
h=Math.round(h*s.scale);
}
// Apply max constraints
if(s.maxWidth>0&&w>s.maxWidth){
if(s.keepAspect){h=Math.round(h*(s.maxWidth/w));}
w=s.maxWidth;
}
if(s.maxHeight>0&&h>s.maxHeight){
if(s.keepAspect){w=Math.round(w*(s.maxHeight/h));}
h=s.maxHeight;
}
return{w:Math.max(1,w),h:Math.max(1,h)};
}

function processFile(file){
var reader=new FileReader();
reader.onload=function(e){
var img=new Image();
img.onload=function(){
compressImage(img,file,e.target.result);
};
img.src=e.target.result;
};
reader.readAsDataURL(file);
}

function compressImage(img,file,originalDataUrl){
var s=getSettings();
var dim=calcDimensions(img.naturalWidth,img.naturalHeight,s);

var canvas=document.createElement("canvas");
canvas.width=dim.w;
canvas.height=dim.h;
var ctx=canvas.getContext("2d");
ctx.drawImage(img,0,0,dim.w,dim.h);

canvas.toBlob(function(blob){
if(!blob)return;
var compUrl=URL.createObjectURL(blob);
var item={
id:Date.now()+"_"+Math.random().toString(36).substr(2,6),
file:file,
originalDataUrl:originalDataUrl,
origWidth:img.naturalWidth,
origHeight:img.naturalHeight,
newWidth:dim.w,
newHeight:dim.h,
originalSize:file.size,
compressedSize:blob.size,
compressedBlob:blob,
compressedUrl:compUrl,
format:s.format
};
imageItems.push(item);
renderResult(item);
updateBatchBar();
},s.format,s.format==="image/png"?undefined:s.quality);
}

function recompressItem(item){
var s=getSettings();
var img=new Image();
img.onload=function(){
var dim=calcDimensions(img.naturalWidth,img.naturalHeight,s);
var canvas=document.createElement("canvas");
canvas.width=dim.w;
canvas.height=dim.h;
var ctx=canvas.getContext("2d");
ctx.drawImage(img,0,0,dim.w,dim.h);
canvas.toBlob(function(blob){
if(!blob)return;
if(item.compressedUrl)URL.revokeObjectURL(item.compressedUrl);
item.newWidth=dim.w;
item.newHeight=dim.h;
item.compressedSize=blob.size;
item.compressedBlob=blob;
item.compressedUrl=URL.createObjectURL(blob);
item.format=s.format;
renderResult(item);
updateBatchBar();
},s.format,s.format==="image/png"?undefined:s.quality);
};
img.src=item.originalDataUrl;
}

function renderResult(item){
var existing=document.getElementById("ic-card-"+item.id);
var savings=((1-item.compressedSize/item.originalSize)*100);
if(savings<0)savings=0;
var savingsText=savings.toFixed(1)+"%";

var html='<div class="ic-result-header">';
html+='<span class="ic-result-filename" title="'+item.file.name+'">'+item.file.name+'</span>';
html+='<div class="ic-result-actions">';
html+='<button class="ic-btn ic-btn-green ic-btn-sm" onclick="icDownloadOne(\''+item.id+'\')">Download</button>';
html+='<button class="ic-result-remove" onclick="icRemoveItem(\''+item.id+'\')" title="Remove">&times;</button>';
html+='</div></div>';

html+='<div class="ic-preview-wrap" id="ic-preview-'+item.id+'">';
html+='<img class="ic-preview-original" src="'+item.originalDataUrl+'" alt="Original">';
html+='<img class="ic-preview-compressed" src="'+item.compressedUrl+'" alt="Compressed" style="clip-path:inset(0 0 0 50%)">';
html+='<div class="ic-preview-slider" style="left:50%" id="ic-slider-'+item.id+'"></div>';
html+='<span class="ic-preview-label ic-preview-label-orig">Original</span>';
html+='<span class="ic-preview-label ic-preview-label-comp">Compressed</span>';
html+='</div>';

html+='<div class="ic-stats">';
html+='<div class="ic-stat"><div class="ic-stat-label">Original</div><div class="ic-stat-value">'+formatBytes(item.originalSize)+'</div></div>';
html+='<div class="ic-stat"><div class="ic-stat-label">Compressed</div><div class="ic-stat-value">'+formatBytes(item.compressedSize)+'</div></div>';
html+='<div class="ic-stat"><div class="ic-stat-label">Savings</div><div class="ic-stat-value ic-savings">'+savingsText+'</div></div>';
html+='<div class="ic-stat"><div class="ic-stat-label">Dimensions</div><div class="ic-stat-value">'+item.newWidth+'x'+item.newHeight+'</div></div>';
html+='</div>';

if(existing){
existing.innerHTML=html;
}else{
var card=document.createElement("div");
card.className="ic-result-card";
card.id="ic-card-"+item.id;
card.innerHTML=html;
resultsEl.appendChild(card);
}

// Attach slider interaction
initSlider(item.id);
}

function initSlider(itemId){
var wrap=document.getElementById("ic-preview-"+itemId);
var slider=document.getElementById("ic-slider-"+itemId);
if(!wrap||!slider)return;

var dragging=false;

function moveSlider(clientX){
var rect=wrap.getBoundingClientRect();
var x=clientX-rect.left;
var pct=Math.max(0,Math.min(1,x/rect.width));
slider.style.left=(pct*100)+"%";
var comp=wrap.querySelector(".ic-preview-compressed");
if(comp)comp.style.clipPath="inset(0 0 0 "+(pct*100)+"%)";
}

slider.addEventListener("mousedown",function(e){
e.preventDefault();dragging=true;
});
wrap.addEventListener("mousedown",function(e){
dragging=true;moveSlider(e.clientX);
});
document.addEventListener("mousemove",function(e){
if(dragging)moveSlider(e.clientX);
});
document.addEventListener("mouseup",function(){dragging=false;});

// Touch support
slider.addEventListener("touchstart",function(e){
e.preventDefault();dragging=true;
},{passive:false});
wrap.addEventListener("touchstart",function(e){
dragging=true;moveSlider(e.touches[0].clientX);
});
document.addEventListener("touchmove",function(e){
if(dragging)moveSlider(e.touches[0].clientX);
});
document.addEventListener("touchend",function(){dragging=false;});
}

function updateBatchBar(){
if(imageItems.length===0){
batchBar.style.display="none";
return;
}
batchBar.style.display="flex";
var totalOrig=0,totalComp=0;
imageItems.forEach(function(it){
totalOrig+=it.originalSize;
totalComp+=it.compressedSize;
});
var totalSaved=totalOrig-totalComp;
if(totalSaved<0)totalSaved=0;
var avgRatio=totalOrig>0?((1-totalComp/totalOrig)*100):0;
if(avgRatio<0)avgRatio=0;

document.getElementById("icBatchCount").textContent=imageItems.length;
document.getElementById("icBatchSaved").textContent=formatBytes(totalSaved);
document.getElementById("icBatchRatio").textContent=avgRatio.toFixed(1)+"%";
}

function findItem(id){
for(var i=0;i<imageItems.length;i++){
if(imageItems[i].id===id)return imageItems[i];
}
return null;
}

// Global functions
window.icRemoveItem=function(id){
var card=document.getElementById("ic-card-"+id);
if(card)card.remove();
var item=findItem(id);
if(item&&item.compressedUrl)URL.revokeObjectURL(item.compressedUrl);
imageItems=imageItems.filter(function(it){return it.id!==id;});
updateBatchBar();
if(imageItems.length===0){controlsEl.style.display="none";}
};

window.icDownloadOne=function(id){
var item=findItem(id);
if(!item)return;
var a=document.createElement("a");
var baseName=item.file.name.replace(/\.[^.]+$/,"");
a.download=baseName+"_compressed"+formatExt(item.format);
a.href=item.compressedUrl;
document.body.appendChild(a);
a.click();
document.body.removeChild(a);
};

window.icDownloadAll=function(){
if(imageItems.length===0)return;
if(imageItems.length===1){
window.icDownloadOne(imageItems[0].id);
return;
}
// Load JSZip dynamically
if(!zipScriptLoaded){
var s=document.createElement("script");
s.src="https://cdn.jsdelivr.net/npm/jszip@3/dist/jszip.min.js";
s.onload=function(){zipScriptLoaded=true;buildZip();};
document.head.appendChild(s);
}else{
buildZip();
}
};

function buildZip(){
if(typeof JSZip==="undefined")return;
var zip=new JSZip();
var promises=[];
imageItems.forEach(function(item){
var baseName=item.file.name.replace(/\.[^.]+$/,"");
var fname=baseName+"_compressed"+formatExt(item.format);
zip.file(fname,item.compressedBlob);
});
zip.generateAsync({type:"blob"}).then(function(content){
var a=document.createElement("a");
a.download="compressed_images.zip";
a.href=URL.createObjectURL(content);
document.body.appendChild(a);
a.click();
document.body.removeChild(a);
URL.revokeObjectURL(a.href);
});
}

window.icClearAll=function(){
imageItems.forEach(function(it){
if(it.compressedUrl)URL.revokeObjectURL(it.compressedUrl);
});
imageItems=[];
resultsEl.innerHTML="";
updateBatchBar();
controlsEl.style.display="none";
fileInput.value="";
};

window.icRecompress=function(){
imageItems.forEach(function(item){
recompressItem(item);
});
};

window.icResetSettings=function(){
qualitySlider.value=80;
qualityVal.textContent="80%";
formatSelect.value="image/jpeg";
maxWidthInput.value="";
maxHeightInput.value="";
scaleInput.value="";
aspectCheck.checked=true;
};

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Free Image Compressor",
      "url": "https://theluckystrike.github.io/tools/image-compressor/",
      "applicationCategory": "MultimediaApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "description": "Compress images online for free. Reduce JPEG, PNG, and WebP file sizes using client-side Canvas API. Adjust quality, resize dimensions, and batch process multiple images.",
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Image Compressor", "item": "https://theluckystrike.github.io/tools/image-compressor/" }
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
          "name": "Are my images uploaded to a server when I use this tool?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Every step of the compression process runs locally in your browser using the Canvas API. Your images are never sent over the network. The file data stays in your browser's memory and is discarded when you close the tab or clear the images."
          }
        },
        {
          "@type": "Question",
          "name": "What is the best quality setting for web images?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For most web usage, 75-85% quality provides a good balance between file size and visual fidelity. Below 70%, JPEG and WebP artifacts become noticeable. Above 90%, file sizes increase significantly with minimal visible improvement."
          }
        },
        {
          "@type": "Question",
          "name": "Why does PNG compression produce larger files than JPEG?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "PNG is a lossless format that preserves every pixel exactly. For photographic images, lossless encoding cannot match the compression ratios of lossy formats like JPEG or WebP. PNG compression is most effective on images with large areas of identical color."
          }
        },
        {
          "@type": "Question",
          "name": "Can I compress multiple images at once?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Select multiple files from the file picker or drag and drop a batch onto the drop zone. Each image is processed individually with the same settings. Use the Download All button to get a ZIP archive of every result."
          }
        },
        {
          "@type": "Question",
          "name": "Should I use WebP instead of JPEG for my website?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "In most cases, yes. WebP produces files 25-35% smaller than JPEG at equivalent visual quality and supports alpha transparency. As of 2026, browser support exceeds 96%."
          }
        },
        {
          "@type": "Question",
          "name": "Does resizing an image before compression help reduce file size?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Significantly. Reducing dimensions has a multiplicative effect on file size. Halving both dimensions reduces pixel count by 75%, typically resulting in a file 3-4x smaller even before quality compression."
          }
        }
      ]
    }
  ]
}
</script>
