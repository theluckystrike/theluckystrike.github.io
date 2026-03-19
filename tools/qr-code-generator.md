---
layout: page
title: "Free QR Code Generator — Custom Colors, Logos & Bulk Export | Zovo"
description: "Generate QR codes for URLs, text, WiFi, vCards, email, and phone numbers. Customize colors, add logos, adjust size and error correction. Free bulk QR code generator with PNG and SVG download."
permalink: /tools/qr-code-generator/
keywords: "qr code generator, qr code maker, create qr code, free qr code, custom qr code, qr code with logo, bulk qr code generator, wifi qr code"
date: 2026-03-19
categories: [tools]
tags: [qr-code, generator, barcode, url, wifi, vcard, custom]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>
:root{--qr-primary:#6C5CE7;--qr-primary-dark:#5A4BD1;--qr-primary-light:#A29BFE;--qr-green:#00ff88;--qr-bg:#0a0a0f;--qr-surface:#12121a;--qr-surface2:#1a1a28;--qr-border:#1e1e2e;--qr-border2:#2a2a3e;--qr-text:#e0e0e0;--qr-muted:#8888aa;--qr-radius:12px}
.qr-wrap{font-family:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;color:var(--qr-text);max-width:1100px;margin:0 auto;padding:0 16px;line-height:1.6}
.qr-wrap *{box-sizing:border-box}
.qr-hero{text-align:center;padding:40px 0 28px}
.qr-hero h1{font-size:2.2rem;font-weight:700;color:var(--qr-text);margin:0 0 16px;line-height:1.2}
.qr-hero h1 span{color:var(--qr-primary)}
.qr-intro{font-size:1.02rem;color:var(--qr-muted);max-width:700px;margin:0 auto;line-height:1.7}
.qr-app{display:grid;grid-template-columns:1fr 380px;gap:24px;margin-bottom:32px}
.qr-left{display:flex;flex-direction:column;gap:16px}
.qr-card{background:var(--qr-surface);border:1px solid var(--qr-border);border-radius:var(--qr-radius);padding:20px;box-shadow:0 2px 12px rgba(108,92,231,0.06)}
.qr-tabs{display:flex;gap:4px;flex-wrap:wrap;margin-bottom:16px}
.qr-tab{padding:8px 14px;border:1px solid var(--qr-border);border-radius:8px;background:transparent;color:var(--qr-muted);font-family:'Inter',sans-serif;font-size:0.82rem;font-weight:500;cursor:pointer;transition:all 0.15s}
.qr-tab:hover{border-color:var(--qr-primary);color:var(--qr-text)}
.qr-tab.active{background:var(--qr-primary);color:#fff;border-color:var(--qr-primary)}
.qr-pane{display:none}
.qr-pane.active{display:block}
.qr-field{margin-bottom:14px}
.qr-field label{display:block;font-size:0.8rem;font-weight:600;color:var(--qr-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:6px}
.qr-field input[type="text"],.qr-field input[type="email"],.qr-field input[type="tel"],.qr-field input[type="url"],.qr-field input[type="number"],.qr-field textarea,.qr-field select{width:100%;font-family:'Inter',sans-serif;font-size:0.92rem;padding:10px 14px;border:1.5px solid var(--qr-border);border-radius:8px;background:var(--qr-bg);color:var(--qr-text);transition:border-color 0.2s;outline:none}
.qr-field input:focus,.qr-field textarea:focus,.qr-field select:focus{border-color:var(--qr-primary);box-shadow:0 0 0 3px rgba(108,92,231,0.15)}
.qr-field textarea{resize:vertical;min-height:80px}
.qr-field select{appearance:auto}
.qr-row{display:flex;gap:12px}
.qr-row .qr-field{flex:1}
.qr-toggle-row{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.qr-toggle{position:relative;width:42px;height:24px;background:var(--qr-border2);border-radius:12px;cursor:pointer;transition:background 0.2s;border:none;padding:0}
.qr-toggle.on{background:var(--qr-primary)}
.qr-toggle::after{content:'';position:absolute;top:3px;left:3px;width:18px;height:18px;background:#fff;border-radius:50%;transition:transform 0.2s}
.qr-toggle.on::after{transform:translateX(18px)}
.qr-toggle-label{font-size:0.88rem;color:var(--qr-muted)}
.qr-section-title{font-size:0.85rem;font-weight:600;color:var(--qr-text);margin:0 0 14px;padding-bottom:8px;border-bottom:1px solid var(--qr-border)}
.qr-color-row{display:flex;gap:16px;margin-bottom:14px}
.qr-color-group{display:flex;align-items:center;gap:8px}
.qr-color-group label{font-size:0.8rem;color:var(--qr-muted);white-space:nowrap}
.qr-color-group input[type="color"]{width:36px;height:36px;border:2px solid var(--qr-border);border-radius:8px;cursor:pointer;background:none;padding:2px}
.qr-slider-row{margin-bottom:14px}
.qr-slider-row label{display:flex;justify-content:space-between;font-size:0.8rem;font-weight:600;color:var(--qr-muted);text-transform:uppercase;letter-spacing:0.5px;margin-bottom:6px}
.qr-slider-row label span{color:var(--qr-primary);font-weight:700}
.qr-slider-row input[type="range"]{width:100%;accent-color:var(--qr-primary);height:6px;cursor:pointer}
.qr-ec-row{display:flex;gap:6px;margin-bottom:14px}
.qr-ec-btn{flex:1;padding:8px 6px;border:1.5px solid var(--qr-border);border-radius:8px;background:transparent;color:var(--qr-muted);font-family:'Inter',sans-serif;font-size:0.78rem;font-weight:500;cursor:pointer;transition:all 0.15s;text-align:center}
.qr-ec-btn:hover{border-color:var(--qr-primary);color:var(--qr-text)}
.qr-ec-btn.active{background:var(--qr-primary);color:#fff;border-color:var(--qr-primary)}
.qr-logo-upload{position:relative}
.qr-logo-upload input[type="file"]{display:none}
.qr-logo-btn{display:inline-flex;align-items:center;gap:6px;padding:8px 16px;border:1.5px dashed var(--qr-border2);border-radius:8px;background:transparent;color:var(--qr-muted);font-family:'Inter',sans-serif;font-size:0.85rem;cursor:pointer;transition:all 0.15s}
.qr-logo-btn:hover{border-color:var(--qr-primary);color:var(--qr-text)}
.qr-logo-preview{display:inline-flex;align-items:center;gap:8px;margin-top:8px}
.qr-logo-preview img{width:32px;height:32px;border-radius:4px;object-fit:cover}
.qr-logo-remove{background:none;border:none;color:var(--qr-muted);cursor:pointer;font-size:0.8rem;text-decoration:underline}
.qr-right{display:flex;flex-direction:column;gap:16px}
.qr-preview-card{background:var(--qr-surface);border:1px solid var(--qr-border);border-radius:var(--qr-radius);padding:20px;text-align:center}
.qr-canvas-wrap{background:#ffffff;border-radius:8px;padding:16px;display:inline-block;margin-bottom:16px}
.qr-canvas-wrap canvas{display:block;max-width:100%;height:auto}
.qr-placeholder{color:var(--qr-muted);font-size:0.9rem;padding:60px 20px}
.qr-dl-row{display:flex;gap:8px;justify-content:center;flex-wrap:wrap}
.qr-btn{display:inline-flex;align-items:center;gap:6px;padding:9px 18px;border:none;border-radius:8px;font-family:'Inter',sans-serif;font-size:0.85rem;font-weight:600;cursor:pointer;transition:all 0.15s;white-space:nowrap}
.qr-btn-primary{background:var(--qr-primary);color:#fff}
.qr-btn-primary:hover{background:var(--qr-primary-dark)}
.qr-btn-outline{background:transparent;color:var(--qr-primary);border:1.5px solid var(--qr-primary)}
.qr-btn-outline:hover{background:rgba(108,92,231,0.1)}
.qr-btn-green{background:var(--qr-green);color:#0a0a0f;font-weight:700}
.qr-btn-green:hover{background:#00dd77}
.qr-btn.copied{background:var(--qr-green);color:#0a0a0f;border-color:var(--qr-green)}
.qr-history-card{background:var(--qr-surface);border:1px solid var(--qr-border);border-radius:var(--qr-radius);padding:16px}
.qr-history-title{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
.qr-history-title h3{font-size:0.85rem;font-weight:600;color:var(--qr-text);margin:0;text-transform:uppercase;letter-spacing:0.5px}
.qr-history-clear{background:none;border:none;color:var(--qr-muted);font-family:'Inter',sans-serif;font-size:0.75rem;cursor:pointer;text-decoration:underline}
.qr-history-list{display:flex;flex-direction:column;gap:8px;max-height:300px;overflow-y:auto}
.qr-history-item{display:flex;align-items:center;gap:10px;padding:8px;background:var(--qr-bg);border-radius:8px;cursor:pointer;transition:background 0.15s}
.qr-history-item:hover{background:var(--qr-surface2)}
.qr-history-item canvas{width:40px;height:40px;border-radius:4px;flex-shrink:0}
.qr-history-item .qr-hist-info{flex:1;min-width:0}
.qr-history-item .qr-hist-type{font-size:0.7rem;color:var(--qr-primary);font-weight:600;text-transform:uppercase}
.qr-history-item .qr-hist-val{font-size:0.78rem;color:var(--qr-muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.qr-history-empty{font-size:0.82rem;color:var(--qr-muted);text-align:center;padding:16px 0}
.qr-bulk-card{background:var(--qr-surface);border:1px solid var(--qr-border);border-radius:var(--qr-radius);padding:20px;margin-bottom:24px}
.qr-bulk-card h3{font-size:0.95rem;font-weight:600;color:var(--qr-text);margin:0 0 12px}
.qr-bulk-results{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:12px;margin-top:16px}
.qr-bulk-item{background:var(--qr-bg);border-radius:8px;padding:10px;text-align:center}
.qr-bulk-item canvas{max-width:100%;height:auto;border-radius:4px}
.qr-bulk-item p{font-size:0.72rem;color:var(--qr-muted);margin:6px 0 0;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.qr-bulk-item .qr-bulk-dl{font-size:0.72rem;color:var(--qr-primary);background:none;border:none;cursor:pointer;font-family:'Inter',sans-serif;text-decoration:underline;margin-top:4px}
.qr-content{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--qr-border)}
.qr-content h2{font-size:1.4rem;font-weight:700;color:var(--qr-text);margin:32px 0 12px}
.qr-content h2:first-child{margin-top:0}
.qr-content p{font-size:0.95rem;color:var(--qr-muted);line-height:1.75;margin:0 0 14px}
.qr-content ul{margin:0 0 14px;padding-left:20px;color:var(--qr-muted);font-size:0.95rem;line-height:1.75}
.qr-content ul li{margin-bottom:6px}
.qr-faq{max-width:820px;margin:40px auto 0;padding-top:32px;border-top:1px solid var(--qr-border)}
.qr-faq h2{font-size:1.4rem;font-weight:700;color:var(--qr-text);margin:0 0 20px}
.qr-faq-item{border:1px solid var(--qr-border);border-radius:var(--qr-radius);padding:18px 22px;margin-bottom:12px;background:var(--qr-surface)}
.qr-faq-item h3{font-size:1rem;font-weight:600;margin:0 0 8px;color:var(--qr-text)}
.qr-faq-item p{margin:0;font-size:0.92rem;color:var(--qr-muted);line-height:1.7}
.qr-mode-switch{display:flex;gap:6px;margin-bottom:20px}
.qr-mode-btn{padding:8px 18px;border:1.5px solid var(--qr-border);border-radius:8px;background:transparent;color:var(--qr-muted);font-family:'Inter',sans-serif;font-size:0.85rem;font-weight:600;cursor:pointer;transition:all 0.15s}
.qr-mode-btn.active{background:var(--qr-primary);color:#fff;border-color:var(--qr-primary)}
.qr-mode-btn:hover{border-color:var(--qr-primary);color:var(--qr-text)}
@media(max-width:800px){
.qr-app{grid-template-columns:1fr}
.qr-right{order:-1}
.qr-hero h1{font-size:1.6rem}
.qr-row{flex-direction:column;gap:0}
.qr-tabs{gap:3px}
.qr-tab{padding:6px 10px;font-size:0.76rem}
.qr-ec-row{flex-wrap:wrap}
}
</style>

<div class="qr-wrap" itemscope itemtype="https://schema.org/WebApplication">
<meta itemprop="name" content="Free QR Code Generator">
<meta itemprop="applicationCategory" content="UtilityApplication">
<meta itemprop="operatingSystem" content="Any">
<meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
<meta itemprop="price" content="0">

<div class="qr-hero">
<h1>Free <span>QR Code</span> Generator</h1>
<p class="qr-intro">Generate scannable QR codes for URLs, text, WiFi credentials, contacts, email, and phone numbers. Customize colors, add your logo, pick the error correction level, and download as PNG or SVG. Everything runs in your browser -- nothing is uploaded anywhere.</p>
</div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

<div class="qr-mode-switch">
<button class="qr-mode-btn active" onclick="qrSetMode('single')">Single QR</button>
<button class="qr-mode-btn" onclick="qrSetMode('bulk')">Bulk Mode</button>
</div>

<div id="qrSingleMode">
<div class="qr-app">
<div class="qr-left">
<div class="qr-card">
<div class="qr-tabs" id="qrTabs">
<button class="qr-tab active" data-type="url">URL</button>
<button class="qr-tab" data-type="text">Text</button>
<button class="qr-tab" data-type="wifi">WiFi</button>
<button class="qr-tab" data-type="vcard">vCard</button>
<button class="qr-tab" data-type="email">Email</button>
<button class="qr-tab" data-type="phone">Phone</button>
<button class="qr-tab" data-type="sms">SMS</button>
</div>

<div id="pane-url" class="qr-pane active">
<div class="qr-field"><label>URL</label><input type="url" id="qrUrl" placeholder="https://example.com" value="https://zovo.one"></div>
</div>
<div id="pane-text" class="qr-pane">
<div class="qr-field"><label>Text</label><textarea id="qrText" placeholder="Enter any text..." rows="4"></textarea></div>
</div>
<div id="pane-wifi" class="qr-pane">
<div class="qr-field"><label>Network Name (SSID)</label><input type="text" id="qrWifiSsid" placeholder="MyNetwork"></div>
<div class="qr-field"><label>Password</label><input type="text" id="qrWifiPass" placeholder="password123"></div>
<div class="qr-row">
<div class="qr-field"><label>Security</label><select id="qrWifiSec"><option value="WPA">WPA/WPA2</option><option value="WEP">WEP</option><option value="nopass">None</option></select></div>
</div>
<div class="qr-toggle-row"><button class="qr-toggle" id="qrWifiHidden" onclick="this.classList.toggle('on');qrGenerate()"></button><span class="qr-toggle-label">Hidden network</span></div>
</div>
<div id="pane-vcard" class="qr-pane">
<div class="qr-row"><div class="qr-field"><label>First Name</label><input type="text" id="qrVcFirst" placeholder="John"></div><div class="qr-field"><label>Last Name</label><input type="text" id="qrVcLast" placeholder="Doe"></div></div>
<div class="qr-row"><div class="qr-field"><label>Phone</label><input type="tel" id="qrVcPhone" placeholder="+1234567890"></div><div class="qr-field"><label>Email</label><input type="email" id="qrVcEmail" placeholder="john@example.com"></div></div>
<div class="qr-field"><label>Organization</label><input type="text" id="qrVcOrg" placeholder="Acme Inc."></div>
<div class="qr-field"><label>Website</label><input type="url" id="qrVcUrl" placeholder="https://example.com"></div>
<div class="qr-field"><label>Address</label><input type="text" id="qrVcAddr" placeholder="123 Main St, City, Country"></div>
</div>
<div id="pane-email" class="qr-pane">
<div class="qr-field"><label>Recipient</label><input type="email" id="qrEmailTo" placeholder="hello@example.com"></div>
<div class="qr-field"><label>Subject</label><input type="text" id="qrEmailSubj" placeholder="Hello"></div>
<div class="qr-field"><label>Body</label><textarea id="qrEmailBody" placeholder="Message body..." rows="3"></textarea></div>
</div>
<div id="pane-phone" class="qr-pane">
<div class="qr-field"><label>Phone Number</label><input type="tel" id="qrPhone" placeholder="+1234567890"></div>
</div>
<div id="pane-sms" class="qr-pane">
<div class="qr-field"><label>Phone Number</label><input type="tel" id="qrSmsPhone" placeholder="+1234567890"></div>
<div class="qr-field"><label>Message</label><textarea id="qrSmsBody" placeholder="Message text..." rows="3"></textarea></div>
</div>
</div>

<div class="qr-card">
<div class="qr-section-title">Customization</div>
<div class="qr-color-row">
<div class="qr-color-group"><label>Foreground</label><input type="color" id="qrFg" value="#000000"></div>
<div class="qr-color-group"><label>Background</label><input type="color" id="qrBg" value="#ffffff"></div>
</div>
<div class="qr-slider-row"><label>Size <span id="qrSizeVal">400px</span></label><input type="range" id="qrSize" min="200" max="1000" value="400" step="50"></div>
<div class="qr-slider-row"><label>Margin <span id="qrMarginVal">4</span></label><input type="range" id="qrMargin" min="0" max="4" value="4" step="1"></div>
<label style="font-size:0.8rem;font-weight:600;color:var(--qr-muted);text-transform:uppercase;letter-spacing:0.5px;display:block;margin-bottom:8px">Error Correction</label>
<div class="qr-ec-row">
<button class="qr-ec-btn" data-ec="L" onclick="qrSetEc(this)">L (7%)</button>
<button class="qr-ec-btn active" data-ec="M" onclick="qrSetEc(this)">M (15%)</button>
<button class="qr-ec-btn" data-ec="Q" onclick="qrSetEc(this)">Q (25%)</button>
<button class="qr-ec-btn" data-ec="H" onclick="qrSetEc(this)">H (30%)</button>
</div>
<div class="qr-logo-upload">
<label style="font-size:0.8rem;font-weight:600;color:var(--qr-muted);text-transform:uppercase;letter-spacing:0.5px;display:block;margin-bottom:8px">Logo (optional)</label>
<button class="qr-logo-btn" onclick="document.getElementById('qrLogoFile').click()">+ Upload Logo</button>
<input type="file" id="qrLogoFile" accept="image/*">
<div class="qr-logo-preview" id="qrLogoPreview" style="display:none"><img id="qrLogoImg"><button class="qr-logo-remove" onclick="qrRemoveLogo()">Remove</button></div>
</div>
</div>
</div>

<div class="qr-right">
<div class="qr-preview-card">
<div class="qr-canvas-wrap" id="qrCanvasWrap">
<canvas id="qrCanvas" width="400" height="400"></canvas>
</div>
<div class="qr-dl-row">
<button class="qr-btn qr-btn-primary" onclick="qrDownload('png')">PNG</button>
<button class="qr-btn qr-btn-outline" onclick="qrDownload('svg')">SVG</button>
<button class="qr-btn qr-btn-outline" id="qrCopyBtn" onclick="qrCopyClipboard()">Copy</button>
</div>
</div>
<div class="qr-history-card">
<div class="qr-history-title"><h3>History</h3><button class="qr-history-clear" onclick="qrClearHistory()">Clear</button></div>
<div class="qr-history-list" id="qrHistoryList"><div class="qr-history-empty">No QR codes generated yet</div></div>
</div>
</div>
</div>
</div>

<div id="qrBulkMode" style="display:none">
<div class="qr-bulk-card">
<h3>Bulk QR Code Generator</h3>
<p style="font-size:0.88rem;color:var(--qr-muted);margin:0 0 14px">Enter one URL or text per line. Each line becomes a separate QR code.</p>
<div class="qr-field"><textarea id="qrBulkInput" rows="8" placeholder="https://example.com&#10;https://google.com&#10;Hello World"></textarea></div>
<div style="display:flex;gap:8px;flex-wrap:wrap">
<button class="qr-btn qr-btn-primary" onclick="qrBulkGenerate()">Generate All</button>
<button class="qr-btn qr-btn-outline" onclick="qrBulkDownloadAll()">Download All (ZIP)</button>
</div>
<div class="qr-bulk-results" id="qrBulkResults"></div>
</div>
</div>

<div class="qr-content">
<h2>What Is a QR Code</h2>
<p>A QR code (Quick Response code) is a two-dimensional barcode that stores data in a grid of black and white squares. Denso Wave, a subsidiary of the Toyota supplier Denso, invented the format in 1994 for tracking automotive parts during manufacturing. Unlike traditional barcodes that only encode data horizontally, QR codes encode data both horizontally and vertically, allowing them to store significantly more information in a smaller space.</p>
<p>QR codes can hold up to 7,089 numeric characters or 4,296 alphanumeric characters. They are readable by smartphone cameras, dedicated scanners, and most modern camera apps without requiring a separate scanning application. The format is an open standard (ISO/IEC 18004), which means anyone can generate and read QR codes without licensing fees.</p>

<h2>How QR Codes Work</h2>
<p>A QR code consists of several functional components. Three large squares in the corners (finder patterns) help scanners locate and orient the code regardless of rotation. Timing patterns (alternating black and white modules between the finder patterns) help the scanner determine the grid dimensions. The data itself is encoded using one of four modes: numeric, alphanumeric, byte, or kanji. Each mode uses a different number of bits per character to maximize efficiency.</p>
<p>After the raw data is encoded, Reed-Solomon error correction codes are appended. These allow the QR code to remain readable even when portions of the symbol are damaged, obscured, or dirty. The error correction level determines how much of the code can be lost while still being readable, ranging from 7% to 30%. Finally, a masking pattern is applied to the data area to balance the distribution of black and white modules, preventing large blocks of same-color modules that would confuse scanners.</p>

<h2>Types of QR Code Content</h2>
<p>QR codes can encode different types of structured data, not just plain text. The content type determines what happens when someone scans the code:</p>
<ul>
<li>URL: Opens a website in the default browser. This is the most common use case for marketing, packaging, and print media.</li>
<li>Plain text: Displays a text string on screen. Useful for serial numbers, reference codes, or short messages.</li>
<li>WiFi: Automatically connects the scanning device to a wireless network. The QR code encodes the SSID, password, and encryption type in a standard format that Android and iOS both recognize.</li>
<li>vCard: Creates a new contact entry with name, phone number, email, organization, website, and address fields pre-filled.</li>
<li>Email: Opens a pre-composed email with the recipient address, subject line, and body text already filled in.</li>
<li>Phone: Initiates a phone call to the encoded number.</li>
<li>SMS: Opens the messaging app with the recipient number and message body pre-filled.</li>
</ul>

<h2>Error Correction Levels Explained</h2>
<p>QR codes use Reed-Solomon error correction, which adds redundant data to the encoded content. If part of the QR code is damaged, smudged, or covered (for example, by a logo placed in the center), the scanner can reconstruct the missing data from the redundant information. There are four error correction levels:</p>
<ul>
<li>Level L (Low): Recovers up to 7% of data. Produces the smallest QR codes with the least redundancy. Best for clean digital displays where damage is unlikely.</li>
<li>Level M (Medium): Recovers up to 15% of data. The default level, offering a good balance between size and resilience. Suitable for most general-purpose QR codes.</li>
<li>Level Q (Quartile): Recovers up to 25% of data. Good for printed materials that may get folded, scratched, or partially obscured.</li>
<li>Level H (High): Recovers up to 30% of data. Required when placing a logo over the center of the QR code, since the logo physically obscures a portion of the data modules. Also recommended for outdoor or industrial environments.</li>
</ul>

<h2>Best Practices for QR Code Design</h2>
<p>Keep the content short. Shorter data produces smaller, simpler QR codes that scan more reliably from a distance. If you need to encode a long URL, use a URL shortener first. When choosing colors, maintain high contrast between the foreground and background. Dark foreground on light background works best -- avoid low-contrast combinations like light gray on white. The foreground color should always be darker than the background because scanners look for dark modules on a light field.</p>
<p>Leave sufficient quiet zone (margin) around the QR code. The quiet zone is the blank space surrounding the code that helps scanners distinguish the QR code from its surroundings. Two to four modules of margin is standard. When printing, ensure the QR code is large enough for the intended scanning distance. A general rule is that the scanning distance is roughly ten times the width of the QR code, so a 2.5 cm (1 inch) QR code works at about 25 cm (10 inches).</p>
<p>Test every QR code before deploying it. Scan it with at least two different devices and apps, under different lighting conditions, and from the distances your users will actually use. If you add a logo, always use the H (High) error correction level and keep the logo to no more than 20% of the total QR code area.</p>

<h2>How to Scan QR Codes</h2>
<p>Most smartphones made after 2017 can scan QR codes directly through the default camera app without installing a third-party scanner. On iPhone, open the Camera app and point it at the QR code -- a notification banner appears with the encoded content. On Android, the Google Lens integration in most camera apps provides the same functionality. Samsung, Pixel, OnePlus, and other major brands all support native QR scanning through their camera apps.</p>
<p>For desktop use, browser extensions and built-in features handle QR scanning. Google Chrome on Android can scan QR codes from the address bar. Some password managers and authenticator apps include QR scanners for specific use cases like two-factor authentication setup. If the QR code contains a URL, the device will typically offer to open it in the browser. For WiFi codes, the device prompts to join the network. For contact cards, it offers to save the contact information.</p>
</div>

<div class="qr-faq" itemscope itemtype="https://schema.org/FAQPage">
<h2>Frequently Asked Questions</h2>

<div class="qr-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Is this QR code generator free to use?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Yes, completely free with no account required, no watermarks, and no limits on the number of QR codes you can generate. The tool runs entirely in your browser using JavaScript, so your data never leaves your device. There are no ads, no tracking, and no premium tier.</p>
</div>
</div>

<div class="qr-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Do the QR codes expire?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">No. QR codes generated here are static, meaning the data is encoded directly into the image. They do not expire and do not depend on any server or subscription. As long as the encoded content remains valid (for example, the URL still works), the QR code will continue to function indefinitely.</p>
</div>
</div>

<div class="qr-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Can I put my logo in the center of the QR code?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Yes. Upload a logo image using the logo upload button in the customization panel. The tool automatically switches to H (High) error correction when a logo is added, which provides 30% data redundancy. This allows the scanner to read the QR code despite the logo covering some of the data modules. Keep the logo relatively small compared to the overall QR code for best results.</p>
</div>
</div>

<div class="qr-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is the difference between PNG and SVG download?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">PNG is a raster image format with fixed resolution. The QR code is exported at the pixel size you set with the size slider. PNG works well for web use, social media, and documents. SVG is a vector format that scales to any size without losing quality. SVG is the better choice for print materials, large format displays, and any situation where you need to resize the QR code after generating it.</p>
</div>
</div>

<div class="qr-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How much data can a QR code hold?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">The maximum capacity depends on the data type and error correction level. At the lowest error correction (L), a QR code can store up to 7,089 numeric digits, 4,296 alphanumeric characters, or 2,953 bytes of binary data. Higher error correction levels reduce the available capacity because more space is used for redundancy. In practice, keeping content under 300 characters produces QR codes that are small, clean, and scan reliably at a distance.</p>
</div>
</div>

<div class="qr-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Why is my QR code not scanning?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">The most common causes are low contrast between foreground and background colors, insufficient quiet zone (margin), the QR code being printed too small for the scanning distance, or encoding too much data which creates a very dense grid. Try increasing the size, using standard black on white colors, adding more margin, or shortening the encoded content. Also ensure the foreground color is darker than the background, as inverted QR codes are not supported by all scanners.</p>
</div>
</div>
</div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/barcode-generator/" style="color:#00ff88;text-decoration:none;">Barcode Generator</a> - Create barcodes in multiple formats</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/password-generator/" style="color:#00ff88;text-decoration:none;">Password Generator</a> - Generate secure random passwords</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/color-picker/" style="color:#00ff88;text-decoration:none;">Color Picker</a> - Extract colors from images</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/ai-detector/" style="color:#00ff88;text-decoration:none;">AI Content Detector</a> - Analyze text for AI-generated patterns</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>


<footer style="text-align:center;padding:2rem 0;color:var(--qr-muted);font-size:0.85rem;border-top:1px solid var(--qr-border);margin-top:3rem;">
<p>Built by <a href="https://zovo.one" style="color:var(--qr-primary);text-decoration:none;">Michael Lip</a> at <a href="https://zovo.one" style="color:var(--qr-primary);text-decoration:none;">zovo.one</a></p>
</footer>

</div>

<script>
(function(){
"use strict";

// ============================================================
// INLINE QR CODE ENCODER - Full implementation
// Supports versions 1-40, EC levels L/M/Q/H, byte mode encoding
// Reed-Solomon error correction, masking, format/version info
// ============================================================

var QRGen = (function(){

// Error correction level constants
var EC_L=0,EC_M=1,EC_Q=2,EC_H=3;
var EC_MAP={L:EC_L,M:EC_M,Q:EC_Q,H:EC_H};

// Number of error correction codewords per block for each version and EC level
// [version][ecLevel] = [numBlocks, ecCodewordsPerBlock]
// Derived from ISO/IEC 18004 tables
var EC_TABLE=[
null,
// V1
[[1,7],[1,10],[1,13],[1,17]],
[[1,10],[1,16],[1,22],[1,28]],
[[1,15],[1,26],[2,18],[2,22]],
[[1,20],[2,18],[2,26],[4,16]],
[[1,26],[2,24],[2,18,2,22],[2,22,2,24]],
[[2,18],[4,16],[4,18],[4,28]],
[[2,20],[4,18],[2,26,4,18],[4,18,1,22]],
[[2,24],[2,22,2,26],[4,18,2,24],[4,22,2,24]],
[[2,30],[3,22,2,24],[4,20,4,24],[4,20,4,28]],
//V10
[[2,18,2,20],[4,26,1,28],[6,24,2,28],[6,26,2,28]],
[[4,20],[1,30,4,28],[4,28,3,24],[3,24,8,28]],
[[2,24,2,26],[6,26,2,28],[4,26,6,28],[7,28,4,24]],
[[4,26],[8,24,1,28],[8,24,4,26],[12,22,4,26]],
[[3,30,1,28],[4,24,5,26],[11,24,5,20],[11,24,5,28]],
[[5,24,1,26],[5,24,5,28],[5,24,7,28],[11,24,7,24]],
[[5,28,1,26],[7,24,3,28],[15,20,2,24],[3,28,13,24]],
[[1,30,5,28],[10,24,1,28],[1,22,15,24],[2,28,17,24]],
[[5,28,1,30],[9,24,4,28],[17,22,1,24],[2,28,19,28]],
[[3,28,4,30],[3,26,11,28],[17,24,4,20],[9,24,16,28]],
//V20
[[3,28,5,30],[3,26,13,28],[15,24,5,26],[15,28,10,24]],
[[4,28,4,30],[17,28],[17,22,6,24],[19,26,6,28]],
[[2,30,7,28],[17,28],[7,24,16,24],[34,24]],
[[4,30,5,28],[4,28,14,26],[11,24,14,22],[16,28,14,24]],
[[6,30,4,28],[6,28,14,26],[11,24,16,24],[30,24,2,28]],
[[8,30,4,26],[8,28,13,26],[7,24,22,22],[22,28,13,24]],
[[10,28,2,30],[19,26,4,28],[28,22,6,24],[33,24,4,28]],
[[8,30,4,28],[22,26,3,28],[8,24,26,22],[12,28,28,24]],
[[3,30,10,28],[3,26,23,28],[4,24,31,24],[11,28,31,24]],
[[7,30,7,28],[21,28,7,26],[1,24,37,22],[19,28,26,24]],
//V30
[[5,30,10,28],[19,28,10,26],[15,24,25,24],[23,28,25,24]],
[[13,30,3,28],[2,28,29,26],[42,24,1,22],[23,28,28,24]],
[[17,30],[10,28,23,26],[10,24,35,22],[19,28,35,24]],
[[17,30,1,28],[14,28,21,26],[29,24,19,24],[11,28,46,24]],
[[13,30,6,28],[14,28,23,26],[44,24,7,22],[59,24,1,28]],
[[12,30,7,28],[12,28,26,26],[39,24,14,22],[22,28,41,24]],
[[6,30,14,28],[6,28,34,26],[46,24,10,24],[2,28,64,24]],
[[17,30,4,28],[29,26,14,28],[49,24,10,22],[24,28,46,24]],
[[4,30,18,28],[13,26,32,28],[48,24,14,22],[42,28,32,24]],
[[20,30,4,28],[40,26,7,28],[43,24,22,22],[10,28,67,24]],
//V40
[[19,30,6,28],[18,26,31,28],[34,24,34,24],[20,28,61,24]]
];

// Data capacity (total data codewords) for each version and EC level
var DCWS=[null];
(function(){
var totalCW=[null,26,44,70,100,134,172,196,242,292,346,404,466,532,581,655,733,815,901,991,1085,1183,1285,1391,1501,1615,1733,1855,1981,2111,2245,2383,2525,2671,2821,2975,3133,3295,3461,3631,3805];
for(var v=1;v<=40;v++){
var row=EC_TABLE[v];
var arr=[];
for(var e=0;e<4;e++){
var spec=row[e];
var ecCW=0;
if(spec.length===2){ecCW=spec[0]*spec[1]}
else if(spec.length===4){ecCW=spec[0]*spec[1]+spec[2]*spec[3]}
arr.push(totalCW[v]-ecCW);
}
DCWS.push(arr);
}
})();

// Alignment pattern locations per version
var ALIGN_POS=[null,[],
[6,18],[6,22],[6,26],[6,30],[6,34],
[6,22,38],[6,24,42],[6,26,46],[6,28,50],
[6,30,54],[6,32,58],[6,34,62],[6,26,46,66],
[6,26,48,70],[6,26,50,74],[6,30,54,78],
[6,30,56,82],[6,30,58,86],[6,34,62,90],
[6,28,50,72,94],[6,26,50,74,98],[6,30,54,78,102],
[6,28,54,80,106],[6,32,58,84,110],[6,30,58,86,114],
[6,34,62,90,118],[6,26,50,74,98,122],[6,30,54,78,102,126],
[6,26,52,78,104,130],[6,30,56,82,108,134],[6,34,60,86,112,138],
[6,30,58,86,114,142],[6,34,62,90,118,146],[6,30,54,78,102,126,150],
[6,24,50,76,102,128,154],[6,28,54,80,106,132,158],[6,32,58,84,110,136,162],
[6,26,54,82,110,138,166],[6,30,58,86,114,142,170]
];

// Format information bits (15 bits) for each EC level and mask pattern
// Pre-computed with BCH(15,5) error correction
var FORMAT_BITS = [];
(function(){
// Generator polynomial for format info: x^10 + x^8 + x^5 + x^4 + x^2 + x + 1
var G = 0x537;
var MASK = 0x5412;
for(var ec=0;ec<4;ec++){
FORMAT_BITS[ec]=[];
for(var mask=0;mask<8;mask++){
var data;
if(ec===EC_L) data = (0x01 << 3) | mask; // L=01
else if(ec===EC_M) data = (0x00 << 3) | mask; // M=00
else if(ec===EC_Q) data = (0x03 << 3) | mask; // Q=11
else data = (0x02 << 3) | mask; // H=10
var bits = data << 10;
for(var i=14;i>=10;i--){
if(bits & (1 << i)) bits ^= G << (i-10);
}
FORMAT_BITS[ec][mask] = ((data << 10) | bits) ^ MASK;
}
}
})();

// Version info bits for versions 7-40
var VERSION_BITS=[];
(function(){
var G=0x1F25;
for(var v=7;v<=40;v++){
var data=v<<12;
var bits=data;
for(var i=17;i>=12;i--){
if(bits&(1<<i)) bits^=G<<(i-12);
}
VERSION_BITS[v]=data|bits;
}
})();

// Galois Field GF(256) with primitive polynomial x^8+x^4+x^3+x^2+1
var GF_EXP=new Uint8Array(512);
var GF_LOG=new Uint8Array(256);
(function(){
var x=1;
for(var i=0;i<255;i++){
GF_EXP[i]=x;
GF_LOG[x]=i;
x<<=1;
if(x>=256) x^=0x11d;
}
for(var i=255;i<512;i++) GF_EXP[i]=GF_EXP[i-255];
})();

function gfMul(a,b){
if(a===0||b===0) return 0;
return GF_EXP[GF_LOG[a]+GF_LOG[b]];
}

// Generate Reed-Solomon error correction codewords
function rsEncode(data,ecCount){
var gen=new Uint8Array(ecCount+1);
gen[0]=1;
for(var i=0;i<ecCount;i++){
var ng=new Uint8Array(ecCount+1);
for(var j=0;j<=i+1;j++){
ng[j]=0;
if(j<=i) ng[j]^=gfMul(gen[j],GF_EXP[i]);
if(j>0) ng[j]^=gen[j-1];
}
gen=ng;
}
var rem=new Uint8Array(ecCount);
for(var i=0;i<data.length;i++){
var coef=data[i]^rem[0];
for(var j=0;j<ecCount-1;j++) rem[j]=rem[j+1];
rem[ecCount-1]=0;
if(coef!==0){
for(var j=0;j<ecCount;j++){
rem[j]^=gfMul(gen[ecCount-j],coef);
}
}
}
return rem;
}

// Parse EC_TABLE entry into block specs
function parseBlocks(spec){
var blocks=[];
if(spec.length===2){
for(var i=0;i<spec[0];i++) blocks.push(spec[1]);
} else if(spec.length===4){
for(var i=0;i<spec[0];i++) blocks.push(spec[1]);
for(var i=0;i<spec[2];i++) blocks.push(spec[3]);
}
return blocks;
}

// Choose minimum version for given data length and EC level
function chooseVersion(dataLen,ecLevel){
for(var v=1;v<=40;v++){
var cap=DCWS[v][ecLevel];
if(dataLen<=cap) return v;
}
return -1;
}

// Get size of QR symbol
function getSize(version){return 17+4*version}

// Encode data in byte mode
function encodeData(text,version,ecLevel){
var bytes=[];
for(var i=0;i<text.length;i++){
var c=text.charCodeAt(i);
if(c<0x80) bytes.push(c);
else if(c<0x800){bytes.push(0xc0|(c>>6),0x80|(c&0x3f))}
else if(c>=0xd800&&c<=0xdbff&&i+1<text.length){
var c2=text.charCodeAt(i+1);
if(c2>=0xdc00&&c2<=0xdfff){
var cp=((c-0xd800)<<10)+(c2-0xdc00)+0x10000;
bytes.push(0xf0|(cp>>18),0x80|((cp>>12)&0x3f),0x80|((cp>>6)&0x3f),0x80|(cp&0x3f));
i++;
}
} else {bytes.push(0xe0|(c>>12),0x80|((c>>6)&0x3f),0x80|(c&0x3f))}
}

var dcws=DCWS[version][ecLevel];
var charCountBits=version<=9?8:(version<=26?16:16);
var bits=[];
// Mode indicator: byte mode = 0100
bits.push(0,1,0,0);
// Character count
for(var i=charCountBits-1;i>=0;i--) bits.push((bytes.length>>i)&1);
// Data
for(var i=0;i<bytes.length;i++){
for(var b=7;b>=0;b--) bits.push((bytes[i]>>b)&1);
}
// Terminator (up to 4 bits)
var maxBits=dcws*8;
for(var i=0;i<4&&bits.length<maxBits;i++) bits.push(0);
// Pad to byte boundary
while(bits.length%8!==0&&bits.length<maxBits) bits.push(0);
// Pad bytes
var padBytes=[0xEC,0x11];
var pi=0;
while(bits.length<maxBits){
var pb=padBytes[pi%2];
for(var b=7;b>=0;b--) bits.push((pb>>b)&1);
pi++;
}

var codewords=new Uint8Array(dcws);
for(var i=0;i<dcws;i++){
var val=0;
for(var b=0;b<8;b++) val=(val<<1)|(bits[i*8+b]||0);
codewords[i]=val;
}
return codewords;
}

// Build final message with error correction interleaving
function buildMessage(codewords,version,ecLevel){
var spec=EC_TABLE[version][ecLevel];
var ecPerBlock=parseBlocks(spec);
var numBlocks=ecPerBlock.length;
var totalDcws=codewords.length;

// Split data into blocks
var dcwPerBlock=[];
var remaining=totalDcws;
// For the EC table, all blocks of same group have same EC codewords
// Data codewords per block = (totalDataCodewords / numBlocks) floor/ceil
var baseDcw=Math.floor(totalDcws/numBlocks);
var extra=totalDcws%numBlocks;
for(var i=0;i<numBlocks;i++){
dcwPerBlock.push(baseDcw+(i>=numBlocks-extra?1:0));
}

var dataBlocks=[];
var ecBlocks=[];
var offset=0;
for(var i=0;i<numBlocks;i++){
var blockData=codewords.slice(offset,offset+dcwPerBlock[i]);
offset+=dcwPerBlock[i];
var ecCW=ecPerBlock[i];
var ecData=rsEncode(blockData,ecCW);
dataBlocks.push(blockData);
ecBlocks.push(ecData);
}

// Interleave data codewords
var result=[];
var maxDcw=0;
for(var i=0;i<numBlocks;i++) if(dcwPerBlock[i]>maxDcw) maxDcw=dcwPerBlock[i];
for(var j=0;j<maxDcw;j++){
for(var i=0;i<numBlocks;i++){
if(j<dataBlocks[i].length) result.push(dataBlocks[i][j]);
}
}

// Interleave EC codewords
var maxEc=0;
for(var i=0;i<numBlocks;i++) if(ecBlocks[i].length>maxEc) maxEc=ecBlocks[i].length;
for(var j=0;j<maxEc;j++){
for(var i=0;i<numBlocks;i++){
if(j<ecBlocks[i].length) result.push(ecBlocks[i][j]);
}
}

return result;
}

// Create the QR matrix
function createMatrix(version){
var sz=getSize(version);
var mod=[];
var func=[];
for(var y=0;y<sz;y++){
mod[y]=new Uint8Array(sz);
func[y]=new Uint8Array(sz);
}

// Place finder patterns
function placeFinder(cy,cx){
for(var dy=-4;dy<=4;dy++){
for(var dx=-4;dx<=4;dx++){
var y=cy+dy,x=cx+dx;
if(y<0||y>=sz||x<0||x>=sz) continue;
var ady=Math.abs(dy),adx=Math.abs(dx);
var v;
if(ady===4||adx===4) v=0; // separator
else if(ady===3||adx===3) v=1;
else if(ady===2||adx===2) v=0;
else if(ady<=1&&adx<=1) v=1;
else v=1;
mod[y][x]=v;
func[y][x]=1;
}
}
}
placeFinder(3,3);
placeFinder(3,sz-4);
placeFinder(sz-4,3);

// Timing patterns
for(var i=8;i<sz-8;i++){
mod[6][i]=i%2===0?1:0;
func[6][i]=1;
mod[i][6]=i%2===0?1:0;
func[i][6]=1;
}

// Alignment patterns
var ap=ALIGN_POS[version];
if(ap.length>0){
for(var i=0;i<ap.length;i++){
for(var j=0;j<ap.length;j++){
var cy=ap[i],cx=ap[j];
// Skip if overlapping finder patterns
if(func[cy][cx]) continue;
for(var dy=-2;dy<=2;dy++){
for(var dx=-2;dx<=2;dx++){
var v=(Math.abs(dy)===2||Math.abs(dx)===2)?1:(dy===0&&dx===0)?1:0;
mod[cy+dy][cx+dx]=v;
func[cy+dy][cx+dx]=1;
}
}
}
}
}

// Dark module
mod[sz-8][8]=1;
func[sz-8][8]=1;

// Reserve format info areas
for(var i=0;i<9;i++){
if(i<sz){func[8][i]=1;func[i][8]=1}
}
for(var i=0;i<8;i++){
func[8][sz-1-i]=1;
func[sz-1-i][8]=1;
}

// Reserve version info areas (versions 7+)
if(version>=7){
for(var i=0;i<6;i++){
for(var j=0;j<3;j++){
func[i][sz-11+j]=1;
func[sz-11+j][i]=1;
}
}
}

return {mod:mod,func:func,sz:sz};
}

// Place data bits into the matrix
function placeData(matrix,message){
var sz=matrix.sz;
var mod=matrix.mod;
var func=matrix.func;

// Convert message to bit array
var bits=[];
for(var i=0;i<message.length;i++){
for(var b=7;b>=0;b--) bits.push((message[i]>>b)&1);
}

// Remainder bits
var remBits=[0,0,7,7,7,7,7,0,0,0,0,0,0,0,3,3,3,3,3,3,3,4,4,4,4,4,4,4,3,3,3,3,3,3,3,0,0,0,0,0,0];
var rem=remBits[matrix.version]||0;
for(var i=0;i<rem;i++) bits.push(0);

var bitIdx=0;
var upward=true;
for(var right=sz-1;right>=1;right-=2){
if(right===6) right=5; // skip vertical timing pattern
for(var cnt=0;cnt<sz;cnt++){
var y=upward?sz-1-cnt:cnt;
for(var dx=0;dx<=1;dx++){
var x=right-dx;
if(x<0||x>=sz) continue;
if(func[y][x]) continue;
if(bitIdx<bits.length){
mod[y][x]=bits[bitIdx];
bitIdx++;
} else {
mod[y][x]=0;
}
}
}
upward=!upward;
}
}

// Masking functions
var MASK_FNS=[
function(y,x){return(y+x)%2===0},
function(y,x){return y%2===0},
function(y,x){return x%3===0},
function(y,x){return(y+x)%3===0},
function(y,x){return(Math.floor(y/2)+Math.floor(x/3))%2===0},
function(y,x){return(y*x)%2+(y*x)%3===0},
function(y,x){return((y*x)%2+(y*x)%3)%2===0},
function(y,x){return((y+x)%2+(y*x)%3)%2===0}
];

function applyMask(matrix,maskIdx){
var sz=matrix.sz;
var fn=MASK_FNS[maskIdx];
for(var y=0;y<sz;y++){
for(var x=0;x<sz;x++){
if(!matrix.func[y][x]){
if(fn(y,x)) matrix.mod[y][x]^=1;
}
}
}
}

// Place format info
function placeFormatInfo(matrix,ecLevel,maskIdx){
var sz=matrix.sz;
var bits=FORMAT_BITS[ecLevel][maskIdx];
// Around top-left finder
for(var i=0;i<6;i++) matrix.mod[8][i]=(bits>>(14-i))&1;
matrix.mod[8][7]=(bits>>8)&1;
matrix.mod[8][8]=(bits>>7)&1;
matrix.mod[7][8]=(bits>>6)&1;
for(var i=0;i<6;i++) matrix.mod[5-i][8]=(bits>>(5-i))&1;
// Around bottom-left and top-right finders
for(var i=0;i<7;i++) matrix.mod[sz-1-i][8]=(bits>>i)&1;
for(var i=0;i<8;i++) matrix.mod[8][sz-8+i]=(bits>>(7-i))&1;
}

// Place version info
function placeVersionInfo(matrix){
var v=matrix.version;
if(v<7) return;
var bits=VERSION_BITS[v];
for(var i=0;i<18;i++){
var bit=(bits>>i)&1;
var row=Math.floor(i/3);
var col=i%3;
matrix.mod[row][matrix.sz-11+col]=bit;
matrix.mod[matrix.sz-11+col][row]=bit;
}
}

// Penalty scoring
function penalty(matrix){
var sz=matrix.sz;
var mod=matrix.mod;
var score=0;

// Rule 1: runs of same color
for(var y=0;y<sz;y++){
var cnt=1;
for(var x=1;x<sz;x++){
if(mod[y][x]===mod[y][x-1]){cnt++;if(x===sz-1&&cnt>=5)score+=cnt-2}
else{if(cnt>=5)score+=cnt-2;cnt=1}
}
}
for(var x=0;x<sz;x++){
var cnt=1;
for(var y=1;y<sz;y++){
if(mod[y][x]===mod[y-1][x]){cnt++;if(y===sz-1&&cnt>=5)score+=cnt-2}
else{if(cnt>=5)score+=cnt-2;cnt=1}
}
}

// Rule 2: 2x2 blocks
for(var y=0;y<sz-1;y++){
for(var x=0;x<sz-1;x++){
var v=mod[y][x];
if(v===mod[y][x+1]&&v===mod[y+1][x]&&v===mod[y+1][x+1]) score+=3;
}
}

// Rule 3: finder-like patterns
for(var y=0;y<sz;y++){
for(var x=0;x<sz-10;x++){
if(mod[y][x]===1&&mod[y][x+1]===0&&mod[y][x+2]===1&&mod[y][x+3]===1&&mod[y][x+4]===1&&mod[y][x+5]===0&&mod[y][x+6]===1&&mod[y][x+7]===0&&mod[y][x+8]===0&&mod[y][x+9]===0&&mod[y][x+10]===0) score+=40;
if(mod[y][x]===0&&mod[y][x+1]===0&&mod[y][x+2]===0&&mod[y][x+3]===0&&mod[y][x+4]===1&&mod[y][x+5]===0&&mod[y][x+6]===1&&mod[y][x+7]===1&&mod[y][x+8]===1&&mod[y][x+9]===0&&mod[y][x+10]===1) score+=40;
}
}
for(var x=0;x<sz;x++){
for(var y=0;y<sz-10;y++){
if(mod[y][x]===1&&mod[y+1][x]===0&&mod[y+2][x]===1&&mod[y+3][x]===1&&mod[y+4][x]===1&&mod[y+5][x]===0&&mod[y+6][x]===1&&mod[y+7][x]===0&&mod[y+8][x]===0&&mod[y+9][x]===0&&mod[y+10][x]===0) score+=40;
if(mod[y][x]===0&&mod[y+1][x]===0&&mod[y+2][x]===0&&mod[y+3][x]===0&&mod[y+4][x]===1&&mod[y+5][x]===0&&mod[y+6][x]===1&&mod[y+7][x]===1&&mod[y+8][x]===1&&mod[y+9][x]===0&&mod[y+10][x]===1) score+=40;
}
}

// Rule 4: proportion of dark modules
var dark=0;
for(var y=0;y<sz;y++) for(var x=0;x<sz;x++) if(mod[y][x]) dark++;
var pct=dark*100/(sz*sz);
var prev=Math.abs(Math.floor(pct/5)*5-50)/5;
var next=Math.abs(Math.ceil(pct/5)*5-50)/5;
score+=Math.min(prev,next)*10;

return score;
}

// Deep copy matrix
function copyMatrix(m){
var c={sz:m.sz,version:m.version,mod:[],func:[]};
for(var y=0;y<m.sz;y++){
c.mod[y]=new Uint8Array(m.mod[y]);
c.func[y]=new Uint8Array(m.func[y]);
}
return c;
}

// Main generate function
function generate(text,ecLevelStr){
var ecLevel=EC_MAP[ecLevelStr||'M'];
if(ecLevel===undefined) ecLevel=EC_M;

// Encode as UTF-8 bytes
var utf8=[];
for(var i=0;i<text.length;i++){
var c=text.charCodeAt(i);
if(c<0x80) utf8.push(c);
else if(c<0x800){utf8.push(0xc0|(c>>6),0x80|(c&0x3f))}
else if(c>=0xd800&&c<=0xdbff&&i+1<text.length){
var c2=text.charCodeAt(i+1);
if(c2>=0xdc00&&c2<=0xdfff){
var cp=((c-0xd800)<<10)+(c2-0xdc00)+0x10000;
utf8.push(0xf0|(cp>>18),0x80|((cp>>12)&0x3f),0x80|((cp>>6)&0x3f),0x80|(cp&0x3f));
i++;
}
} else {utf8.push(0xe0|(c>>12),0x80|((c>>6)&0x3f),0x80|(c&0x3f))}
}

// Mode indicator (4 bits) + char count bits + data
var overhead;
var testVer=1;
for(;;){
var ccBits=testVer<=9?8:(testVer<=26?16:16);
overhead=Math.ceil((4+ccBits+utf8.length*8)/8);
var v=chooseVersion(overhead,ecLevel);
if(v<0) throw new Error("Data too long for QR code");
if(v<=9&&testVer<=9){testVer=v;break}
if(v<=26&&testVer<=26&&testVer>9){testVer=v;break}
if(v>26&&testVer>26){testVer=v;break}
if(testVer<=9&&v>9){testVer=10;continue}
if(testVer<=26&&v>26){testVer=27;continue}
testVer=v;break;
}
var version=testVer;

var codewords=encodeData(text,version,ecLevel);
var message=buildMessage(codewords,version,ecLevel);

// Create matrix and try all 8 mask patterns
var bestMatrix=null;
var bestPenalty=Infinity;
for(var m=0;m<8;m++){
var mat=createMatrix(version);
mat.version=version;
placeData(mat,message);
applyMask(mat,m);
placeFormatInfo(mat,ecLevel,m);
placeVersionInfo(mat);
var p=penalty(mat);
if(p<bestPenalty){bestPenalty=p;bestMatrix=copyMatrix(mat)}
}

return bestMatrix;
}

return{generate:generate,getSize:getSize};
})();

// ============================================================
// APP STATE AND UI
// ============================================================

var state={
type:'url',
mode:'single',
ec:'M',
fg:'#000000',
bg:'#ffffff',
size:400,
margin:4,
logo:null,
history:JSON.parse(localStorage.getItem('qr_history')||'[]')
};

// Tabs
document.getElementById('qrTabs').addEventListener('click',function(e){
var btn=e.target.closest('.qr-tab');
if(!btn) return;
var type=btn.dataset.type;
state.type=type;
document.querySelectorAll('.qr-tab').forEach(function(t){t.classList.remove('active')});
btn.classList.add('active');
document.querySelectorAll('.qr-pane').forEach(function(p){p.classList.remove('active')});
document.getElementById('pane-'+type).classList.add('active');
qrGenerate();
});

// Mode switch
window.qrSetMode=function(m){
state.mode=m;
document.querySelectorAll('.qr-mode-btn').forEach(function(b){b.classList.toggle('active',b.textContent.toLowerCase().indexOf(m)!==-1)});
document.getElementById('qrSingleMode').style.display=m==='single'?'':'none';
document.getElementById('qrBulkMode').style.display=m==='bulk'?'':'none';
};

// EC buttons
window.qrSetEc=function(btn){
state.ec=btn.dataset.ec;
document.querySelectorAll('.qr-ec-btn').forEach(function(b){b.classList.remove('active')});
btn.classList.add('active');
qrGenerate();
};

// Sliders
document.getElementById('qrSize').addEventListener('input',function(){
state.size=parseInt(this.value);
document.getElementById('qrSizeVal').textContent=this.value+'px';
qrGenerate();
});
document.getElementById('qrMargin').addEventListener('input',function(){
state.margin=parseInt(this.value);
document.getElementById('qrMarginVal').textContent=this.value;
qrGenerate();
});

// Colors
document.getElementById('qrFg').addEventListener('input',function(){state.fg=this.value;qrGenerate()});
document.getElementById('qrBg').addEventListener('input',function(){state.bg=this.value;qrGenerate()});

// Logo upload
document.getElementById('qrLogoFile').addEventListener('change',function(e){
var file=e.target.files[0];
if(!file) return;
var reader=new FileReader();
reader.onload=function(ev){
state.logo=ev.target.result;
document.getElementById('qrLogoImg').src=state.logo;
document.getElementById('qrLogoPreview').style.display='inline-flex';
// Force H error correction
state.ec='H';
document.querySelectorAll('.qr-ec-btn').forEach(function(b){b.classList.toggle('active',b.dataset.ec==='H')});
qrGenerate();
};
reader.readAsDataURL(file);
});

window.qrRemoveLogo=function(){
state.logo=null;
document.getElementById('qrLogoFile').value='';
document.getElementById('qrLogoPreview').style.display='none';
qrGenerate();
};

// Get data string from current inputs
function getData(){
var type=state.type;
if(type==='url'){
var v=document.getElementById('qrUrl').value.trim();
if(v&&!/^https?:\/\//i.test(v)) v='https://'+v;
return v;
}
if(type==='text') return document.getElementById('qrText').value;
if(type==='wifi'){
var ssid=document.getElementById('qrWifiSsid').value;
var pass=document.getElementById('qrWifiPass').value;
var sec=document.getElementById('qrWifiSec').value;
var hidden=document.getElementById('qrWifiHidden').classList.contains('on');
var esc=function(s){return s.replace(/[\\;,:""]/g,function(c){return'\\'+c})};
return 'WIFI:T:'+sec+';S:'+esc(ssid)+';P:'+esc(pass)+';H:'+(hidden?'true':'false')+';;';
}
if(type==='vcard'){
var fn=document.getElementById('qrVcFirst').value;
var ln=document.getElementById('qrVcLast').value;
var ph=document.getElementById('qrVcPhone').value;
var em=document.getElementById('qrVcEmail').value;
var org=document.getElementById('qrVcOrg').value;
var url=document.getElementById('qrVcUrl').value;
var addr=document.getElementById('qrVcAddr').value;
var lines=['BEGIN:VCARD','VERSION:3.0'];
if(fn||ln) lines.push('N:'+ln+';'+fn+';;;');
if(fn||ln) lines.push('FN:'+(fn?fn+' ':'')+ln);
if(ph) lines.push('TEL:'+ph);
if(em) lines.push('EMAIL:'+em);
if(org) lines.push('ORG:'+org);
if(url) lines.push('URL:'+url);
if(addr) lines.push('ADR:;;'+addr+';;;;');
lines.push('END:VCARD');
return lines.join('\n');
}
if(type==='email'){
var to=document.getElementById('qrEmailTo').value;
var subj=document.getElementById('qrEmailSubj').value;
var body=document.getElementById('qrEmailBody').value;
var mailto='mailto:'+encodeURIComponent(to);
var params=[];
if(subj) params.push('subject='+encodeURIComponent(subj));
if(body) params.push('body='+encodeURIComponent(body));
if(params.length) mailto+='?'+params.join('&');
return mailto;
}
if(type==='phone') return 'tel:'+document.getElementById('qrPhone').value;
if(type==='sms'){
var ph=document.getElementById('qrSmsPhone').value;
var body=document.getElementById('qrSmsBody').value;
return 'sms:'+ph+(body?'?body='+encodeURIComponent(body):'');
}
return '';
}

// Render QR to canvas
function renderQR(canvas,data,opts){
opts=opts||{};
var size=opts.size||400;
var fg=opts.fg||'#000000';
var bg=opts.bg||'#ffffff';
var margin=opts.margin!==undefined?opts.margin:4;
var ec=opts.ec||'M';
var logo=opts.logo||null;

if(!data){
canvas.width=size;canvas.height=size;
var ctx=canvas.getContext('2d');
ctx.fillStyle=bg;ctx.fillRect(0,0,size,size);
ctx.fillStyle='#888';ctx.font='14px Inter,sans-serif';ctx.textAlign='center';
ctx.fillText('Enter data to generate QR code',size/2,size/2);
return null;
}

try{
var mat=QRGen.generate(data,ec);
var sz=mat.sz;
var totalMod=sz+margin*2;
var modSize=size/totalMod;

canvas.width=size;canvas.height=size;
var ctx=canvas.getContext('2d');
ctx.fillStyle=bg;ctx.fillRect(0,0,size,size);
ctx.fillStyle=fg;

for(var y=0;y<sz;y++){
for(var x=0;x<sz;x++){
if(mat.mod[y][x]){
var px=(x+margin)*modSize;
var py=(y+margin)*modSize;
ctx.fillRect(Math.round(px),Math.round(py),Math.ceil(modSize),Math.ceil(modSize));
}
}
}

// Draw logo
if(logo){
var img=new Image();
img.onload=function(){
var logoSize=size*0.2;
var lx=(size-logoSize)/2;
var ly=(size-logoSize)/2;
var pad=4;
ctx.fillStyle=bg;
ctx.fillRect(lx-pad,ly-pad,logoSize+pad*2,logoSize+pad*2);
ctx.drawImage(img,lx,ly,logoSize,logoSize);
};
img.src=logo;
}

return mat;
}catch(e){
canvas.width=size;canvas.height=size;
var ctx=canvas.getContext('2d');
ctx.fillStyle=bg;ctx.fillRect(0,0,size,size);
ctx.fillStyle='#ff4444';ctx.font='13px Inter,sans-serif';ctx.textAlign='center';
ctx.fillText('Error: '+e.message,size/2,size/2);
return null;
}
}

// Main generate function
var genTimer=null;
window.qrGenerate=function(){
clearTimeout(genTimer);
genTimer=setTimeout(function(){
var data=getData();
var canvas=document.getElementById('qrCanvas');
var mat=renderQR(canvas,data,{
size:state.size,fg:state.fg,bg:state.bg,margin:state.margin,ec:state.ec,logo:state.logo
});
if(mat&&data){
addToHistory(state.type,data);
}
},150);
};

// Listen to all inputs for live preview
document.querySelectorAll('.qr-pane input,.qr-pane textarea,.qr-pane select').forEach(function(el){
el.addEventListener('input',qrGenerate);
el.addEventListener('change',qrGenerate);
});

// Download
window.qrDownload=function(fmt){
var data=getData();
if(!data) return;
if(fmt==='png'){
var canvas=document.getElementById('qrCanvas');
canvas.toBlob(function(blob){
var url=URL.createObjectURL(blob);
var a=document.createElement('a');
a.href=url;a.download='qrcode.png';
document.body.appendChild(a);a.click();document.body.removeChild(a);
URL.revokeObjectURL(url);
},'image/png');
} else if(fmt==='svg'){
try{
var mat=QRGen.generate(data,state.ec);
var sz=mat.sz;
var margin=state.margin;
var total=sz+margin*2;
var modSize=10;
var svgSize=total*modSize;
var svg='<svg xmlns="http://www.w3.org/2000/svg" width="'+svgSize+'" height="'+svgSize+'" viewBox="0 0 '+svgSize+' '+svgSize+'">';
svg+='<rect width="'+svgSize+'" height="'+svgSize+'" fill="'+state.bg+'"/>';
for(var y=0;y<sz;y++){
for(var x=0;x<sz;x++){
if(mat.mod[y][x]){
svg+='<rect x="'+((x+margin)*modSize)+'" y="'+((y+margin)*modSize)+'" width="'+modSize+'" height="'+modSize+'" fill="'+state.fg+'"/>';
}
}
}
svg+='</svg>';
var blob=new Blob([svg],{type:'image/svg+xml'});
var url=URL.createObjectURL(blob);
var a=document.createElement('a');
a.href=url;a.download='qrcode.svg';
document.body.appendChild(a);a.click();document.body.removeChild(a);
URL.revokeObjectURL(url);
}catch(e){}
}
};

// Copy to clipboard
window.qrCopyClipboard=function(){
var canvas=document.getElementById('qrCanvas');
canvas.toBlob(function(blob){
if(!blob) return;
try{
var item=new ClipboardItem({"image/png":blob});
navigator.clipboard.write([item]).then(function(){
var btn=document.getElementById('qrCopyBtn');
btn.classList.add('copied');btn.textContent='Copied';
setTimeout(function(){btn.classList.remove('copied');btn.textContent='Copy'},2000);
});
}catch(e){}
},'image/png');
};

// History
function addToHistory(type,data){
var item={type:type,data:data.substring(0,200),time:Date.now()};
// Remove duplicate
state.history=state.history.filter(function(h){return h.data!==item.data});
state.history.unshift(item);
if(state.history.length>10) state.history=state.history.slice(0,10);
localStorage.setItem('qr_history',JSON.stringify(state.history));
renderHistory();
}

function renderHistory(){
var list=document.getElementById('qrHistoryList');
if(state.history.length===0){
list.innerHTML='<div class="qr-history-empty">No QR codes generated yet</div>';
return;
}
list.innerHTML='';
state.history.forEach(function(h){
var div=document.createElement('div');
div.className='qr-history-item';
var c=document.createElement('canvas');
c.width=40;c.height=40;
renderQR(c,h.data,{size:40,margin:1,ec:'M',fg:'#000',bg:'#fff'});
var info=document.createElement('div');
info.className='qr-hist-info';
info.innerHTML='<div class="qr-hist-type">'+h.type+'</div><div class="qr-hist-val">'+h.data.substring(0,50)+'</div>';
div.appendChild(c);
div.appendChild(info);
div.addEventListener('click',function(){
state.type=h.type;
document.querySelectorAll('.qr-tab').forEach(function(t){t.classList.toggle('active',t.dataset.type===h.type)});
document.querySelectorAll('.qr-pane').forEach(function(p){p.classList.toggle('active',p.id==='pane-'+h.type)});
// Restore data to first input of that pane
var pane=document.getElementById('pane-'+h.type);
var inp=pane.querySelector('input,textarea');
if(inp) inp.value=h.data;
qrGenerate();
});
list.appendChild(div);
});
}

window.qrClearHistory=function(){
state.history=[];
localStorage.removeItem('qr_history');
renderHistory();
};

// Bulk mode
window.qrBulkGenerate=function(){
var lines=document.getElementById('qrBulkInput').value.split('\n').filter(function(l){return l.trim()});
var container=document.getElementById('qrBulkResults');
container.innerHTML='';
lines.forEach(function(line,i){
var data=line.trim();
if(!data) return;
var item=document.createElement('div');
item.className='qr-bulk-item';
var c=document.createElement('canvas');
renderQR(c,data,{size:280,margin:state.margin,ec:state.ec,fg:state.fg,bg:state.bg});
var p=document.createElement('p');
p.textContent=data.substring(0,30);
var dl=document.createElement('button');
dl.className='qr-bulk-dl';
dl.textContent='Download';
dl.addEventListener('click',function(){
c.toBlob(function(blob){
var url=URL.createObjectURL(blob);
var a=document.createElement('a');
a.href=url;a.download='qr-'+(i+1)+'.png';
document.body.appendChild(a);a.click();document.body.removeChild(a);
URL.revokeObjectURL(url);
},'image/png');
});
item.appendChild(c);
item.appendChild(p);
item.appendChild(dl);
container.appendChild(item);
});
};

window.qrBulkDownloadAll=function(){
var lines=document.getElementById('qrBulkInput').value.split('\n').filter(function(l){return l.trim()});
if(!lines.length) return;
// Download individually (ZIP requires external lib, so we just do sequential downloads)
lines.forEach(function(line,i){
var data=line.trim();
if(!data) return;
var c=document.createElement('canvas');
renderQR(c,data,{size:state.size,margin:state.margin,ec:state.ec,fg:state.fg,bg:state.bg});
setTimeout(function(){
c.toBlob(function(blob){
var url=URL.createObjectURL(blob);
var a=document.createElement('a');
a.href=url;a.download='qr-'+(i+1)+'.png';
document.body.appendChild(a);a.click();document.body.removeChild(a);
URL.revokeObjectURL(url);
},'image/png');
},i*300);
});
};

// Init
renderHistory();
qrGenerate();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "QR Code Generator",
      "url": "https://theluckystrike.github.io/tools/qr-code-generator/",
      "applicationCategory": "UtilityApplication",
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
        { "@type": "ListItem", "position": 3, "name": "QR Code Generator", "item": "https://theluckystrike.github.io/tools/qr-code-generator/" }
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
