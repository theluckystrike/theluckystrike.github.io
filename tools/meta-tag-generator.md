---
layout: page
title: "Free Meta Tag Generator — Title, Description, OG & Twitter Cards | Zovo"
description: "Generate SEO meta tags, Open Graph tags, Twitter Cards, and structured data for your website. Free meta tag generator with live Google SERP preview and character counting."
permalink: /tools/meta-tag-generator/
keywords: "meta tag generator, seo meta tags, open graph generator, twitter card generator, meta description generator, title tag generator, og tags, meta tags for seo"
date: 2026-03-19
categories: [tools]
tags: [meta-tags, seo, open-graph, twitter-cards, html, marketing]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  body {
    margin: 0;
    padding: 0;
    background: #0a0a0f !important;
  }

  :root {
    --mt-primary: #6C5CE7;
    --mt-primary-dark: #5A4BD1;
    --mt-primary-light: #A29BFE;
    --mt-bg: #0a0a0f;
    --mt-surface: #12121a;
    --mt-surface-alt: #181824;
    --mt-border: #1e1e2e;
    --mt-border-light: #2a2a3e;
    --mt-text: #e0e0e0;
    --mt-text-muted: #8888aa;
    --mt-green: #00ff88;
    --mt-green-dark: #00cc6a;
    --mt-yellow: #ffc107;
    --mt-red: #ff4466;
    --mt-radius: 12px;
    --mt-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .mt-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--mt-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .mt-wrapper * {
    box-sizing: border-box;
  }

  .mt-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .mt-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--mt-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .mt-hero h1 span {
    color: var(--mt-primary);
  }

  .mt-intro {
    font-size: 1.05rem;
    color: var(--mt-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .mt-card {
    background: var(--mt-surface);
    border: 1px solid var(--mt-border);
    border-radius: var(--mt-radius);
    padding: 24px;
    box-shadow: var(--mt-shadow);
    margin-bottom: 20px;
  }

  .mt-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--mt-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .mt-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--mt-primary);
    border-radius: 2px;
  }

  /* Grid layouts */
  .mt-input-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .mt-input-grid.three-col {
    grid-template-columns: 1fr 1fr 1fr;
  }

  @media (max-width: 700px) {
    .mt-input-grid, .mt-input-grid.three-col {
      grid-template-columns: 1fr;
    }
  }

  .mt-field {
    margin-bottom: 16px;
  }

  .mt-field:last-child {
    margin-bottom: 0;
  }

  .mt-field.full-width {
    grid-column: 1 / -1;
  }

  .mt-label {
    display: block;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--mt-text-muted);
    margin-bottom: 6px;
  }

  .mt-label-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .mt-char-counter {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    transition: color 0.2s ease;
  }

  .mt-char-counter.ok { color: var(--mt-green); }
  .mt-char-counter.warn { color: var(--mt-yellow); }
  .mt-char-counter.over { color: var(--mt-red); }

  .mt-input {
    width: 100%;
    padding: 10px 14px;
    background: var(--mt-bg);
    border: 1px solid var(--mt-border);
    border-radius: 8px;
    color: var(--mt-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
  }

  .mt-input:focus {
    border-color: var(--mt-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .mt-input::placeholder {
    color: #555;
  }

  .mt-textarea {
    width: 100%;
    padding: 10px 14px;
    background: var(--mt-bg);
    border: 1px solid var(--mt-border);
    border-radius: 8px;
    color: var(--mt-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    outline: none;
    resize: vertical;
    min-height: 72px;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
  }

  .mt-textarea:focus {
    border-color: var(--mt-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .mt-textarea::placeholder {
    color: #555;
  }

  .mt-select {
    width: 100%;
    padding: 10px 14px;
    background: var(--mt-bg);
    border: 1px solid var(--mt-border);
    border-radius: 8px;
    color: var(--mt-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    outline: none;
    cursor: pointer;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%238888aa' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    transition: border-color 0.2s ease;
  }

  .mt-select:focus {
    border-color: var(--mt-primary);
  }

  /* Checkboxes */
  .mt-checkbox-group {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
  }

  .mt-checkbox-label {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 0.88rem;
    color: var(--mt-text);
    cursor: pointer;
  }

  .mt-checkbox-label input[type="checkbox"] {
    accent-color: var(--mt-primary);
    width: 16px;
    height: 16px;
    cursor: pointer;
  }

  /* Keyword Chips */
  .mt-chips-wrap {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    padding: 8px;
    background: var(--mt-bg);
    border: 1px solid var(--mt-border);
    border-radius: 8px;
    min-height: 42px;
    align-items: center;
    cursor: text;
    transition: border-color 0.2s ease;
  }

  .mt-chips-wrap:focus-within {
    border-color: var(--mt-primary);
  }

  .mt-chip {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 3px 10px;
    background: rgba(108, 92, 231, 0.15);
    border: 1px solid rgba(108, 92, 231, 0.3);
    border-radius: 20px;
    font-size: 0.8rem;
    color: var(--mt-primary-light);
  }

  .mt-chip-remove {
    background: none;
    border: none;
    color: var(--mt-primary-light);
    cursor: pointer;
    font-size: 1rem;
    padding: 0;
    line-height: 1;
    opacity: 0.6;
    transition: opacity 0.15s ease;
  }

  .mt-chip-remove:hover {
    opacity: 1;
  }

  .mt-chip-input {
    border: none;
    outline: none;
    background: transparent;
    color: var(--mt-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    min-width: 120px;
    flex: 1;
    padding: 2px 4px;
  }

  .mt-chip-input::placeholder {
    color: #555;
  }

  /* OG Image Preview */
  .mt-og-preview {
    width: 80px;
    height: 80px;
    border-radius: 6px;
    border: 1px solid var(--mt-border);
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--mt-surface-alt);
    margin-top: 6px;
  }

  .mt-og-preview img {
    max-width: 100%;
    max-height: 100%;
    object-fit: cover;
  }

  .mt-og-preview-placeholder {
    font-size: 0.7rem;
    color: var(--mt-text-muted);
    text-align: center;
    padding: 4px;
  }

  /* Preview Section */
  .mt-preview-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 800px) {
    .mt-preview-grid {
      grid-template-columns: 1fr;
    }
  }

  /* Google SERP Preview */
  .mt-serp-preview {
    background: #fff;
    border-radius: 8px;
    padding: 18px;
  }

  .mt-serp-title {
    font-size: 1.1rem;
    color: #1a0dab;
    font-family: Arial, sans-serif;
    line-height: 1.3;
    margin-bottom: 2px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .mt-serp-url {
    font-size: 0.82rem;
    color: #006621;
    font-family: Arial, sans-serif;
    margin-bottom: 4px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .mt-serp-desc {
    font-size: 0.85rem;
    color: #545454;
    font-family: Arial, sans-serif;
    line-height: 1.45;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  /* Facebook Preview */
  .mt-fb-preview {
    background: #1c1c1c;
    border-radius: 8px;
    overflow: hidden;
    border: 1px solid #333;
  }

  .mt-fb-image {
    width: 100%;
    height: 150px;
    background: linear-gradient(135deg, var(--mt-surface-alt), var(--mt-border));
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .mt-fb-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .mt-fb-image-placeholder {
    font-size: 0.85rem;
    color: var(--mt-text-muted);
  }

  .mt-fb-bar {
    padding: 12px 16px;
    border-top: 1px solid #333;
  }

  .mt-fb-site {
    font-size: 0.72rem;
    color: #777;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    margin-bottom: 2px;
  }

  .mt-fb-title {
    font-size: 0.95rem;
    color: #e0e0e0;
    font-weight: 600;
    line-height: 1.3;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .mt-fb-desc {
    font-size: 0.8rem;
    color: #999;
    margin-top: 2px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  /* Twitter Preview */
  .mt-tw-preview {
    background: #000;
    border-radius: 16px;
    overflow: hidden;
    border: 1px solid #333;
  }

  .mt-tw-image {
    width: 100%;
    height: 130px;
    background: linear-gradient(135deg, var(--mt-surface-alt), var(--mt-border));
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .mt-tw-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .mt-tw-bar {
    padding: 10px 14px;
  }

  .mt-tw-title {
    font-size: 0.9rem;
    color: #e0e0e0;
    font-weight: 600;
    line-height: 1.3;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .mt-tw-desc {
    font-size: 0.8rem;
    color: #777;
    margin-top: 2px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .mt-tw-site {
    font-size: 0.75rem;
    color: #555;
    margin-top: 4px;
  }

  /* Code Output */
  .mt-code-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
    flex-wrap: wrap;
    gap: 8px;
  }

  .mt-code-actions {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .mt-code-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 7px 16px;
    background: transparent;
    border: 1px solid var(--mt-border);
    border-radius: 6px;
    color: var(--mt-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.82rem;
    cursor: pointer;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .mt-code-btn:hover {
    border-color: var(--mt-primary);
    color: var(--mt-primary-light);
  }

  .mt-code-btn.primary {
    background: var(--mt-primary);
    border-color: var(--mt-primary);
    color: #fff;
  }

  .mt-code-btn.primary:hover {
    background: var(--mt-primary-dark);
  }

  .mt-code-block {
    background: var(--mt-bg);
    border: 1px solid var(--mt-border);
    border-radius: 8px;
    padding: 16px;
    overflow-x: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    line-height: 1.65;
    color: var(--mt-text);
    white-space: pre;
    tab-size: 2;
    max-height: 500px;
    overflow-y: auto;
  }

  .mt-code-block .tag { color: var(--mt-red); }
  .mt-code-block .attr { color: var(--mt-yellow); }
  .mt-code-block .val { color: var(--mt-green); }
  .mt-code-block .comment { color: var(--mt-text-muted); }

  /* Toggle */
  .mt-toggle-row {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 12px;
  }

  .mt-toggle {
    position: relative;
    width: 40px;
    height: 22px;
    cursor: pointer;
  }

  .mt-toggle input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  .mt-toggle-slider {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background: var(--mt-border);
    border-radius: 22px;
    transition: background 0.2s ease;
  }

  .mt-toggle-slider::before {
    content: '';
    position: absolute;
    width: 16px;
    height: 16px;
    left: 3px;
    top: 3px;
    background: var(--mt-text-muted);
    border-radius: 50%;
    transition: transform 0.2s ease, background 0.2s ease;
  }

  .mt-toggle input:checked + .mt-toggle-slider {
    background: var(--mt-primary);
  }

  .mt-toggle input:checked + .mt-toggle-slider::before {
    transform: translateX(18px);
    background: #fff;
  }

  .mt-toggle-label {
    font-size: 0.85rem;
    color: var(--mt-text-muted);
  }

  /* Validation Warnings */
  .mt-warnings {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .mt-warnings li {
    padding: 10px 14px;
    border-bottom: 1px solid var(--mt-border);
    font-size: 0.88rem;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    color: var(--mt-text-muted);
  }

  .mt-warnings li:last-child {
    border-bottom: none;
  }

  .mt-warn-icon {
    flex-shrink: 0;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: 700;
    margin-top: 1px;
  }

  .mt-warn-icon.error {
    background: rgba(255, 68, 102, 0.12);
    color: var(--mt-red);
  }

  .mt-warn-icon.warning {
    background: rgba(255, 193, 7, 0.15);
    color: var(--mt-yellow);
  }

  .mt-warn-icon.success {
    background: rgba(0, 255, 136, 0.12);
    color: var(--mt-green);
  }

  /* Cross-links */
  .mt-crosslinks {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 12px;
    margin-top: 8px;
  }

  .mt-crosslink {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 14px 16px;
    background: var(--mt-surface-alt);
    border: 1px solid var(--mt-border);
    border-radius: 8px;
    text-decoration: none;
    color: var(--mt-text);
    font-size: 0.88rem;
    font-weight: 500;
    transition: border-color 0.2s ease, transform 0.15s ease;
  }

  .mt-crosslink:hover {
    border-color: var(--mt-primary);
    transform: translateY(-2px);
  }

  .mt-crosslink-icon {
    font-size: 1.2rem;
    flex-shrink: 0;
  }

  /* Author Box */
  .mt-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px;
    background: var(--mt-surface-alt);
    border: 1px solid var(--mt-border);
    border-radius: var(--mt-radius);
    margin-top: 24px;
  }

  .mt-author-avatar {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    background: var(--mt-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    flex-shrink: 0;
  }

  .mt-author-info h4 {
    margin: 0 0 4px;
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--mt-text);
  }

  .mt-author-info p {
    margin: 0;
    font-size: 0.82rem;
    color: var(--mt-text-muted);
    line-height: 1.5;
  }

  /* Content */
  .mt-content {
    margin-top: 48px;
  }

  .mt-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--mt-text);
    margin: 40px 0 16px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--mt-border);
  }

  .mt-content p {
    font-size: 0.98rem;
    color: var(--mt-text-muted);
    line-height: 1.75;
    margin: 0 0 16px;
  }

  .mt-content ul, .mt-content ol {
    color: var(--mt-text-muted);
    padding-left: 20px;
    margin: 0 0 16px;
    line-height: 1.75;
  }

  .mt-content li {
    margin-bottom: 6px;
    font-size: 0.95rem;
  }

  .mt-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    background: var(--mt-surface-alt);
    padding: 2px 6px;
    border-radius: 4px;
    color: var(--mt-primary-light);
  }

  /* FAQ */
  .mt-faq {
    margin-top: 40px;
  }

  .mt-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--mt-text);
    margin: 0 0 20px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--mt-border);
  }

  .mt-faq-item {
    border-bottom: 1px solid var(--mt-border);
    padding: 16px 0;
  }

  .mt-faq-item:last-child {
    border-bottom: none;
  }

  .mt-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--mt-text);
    margin: 0 0 8px;
  }

  .mt-faq-item p {
    font-size: 0.92rem;
    color: var(--mt-text-muted);
    margin: 0;
    line-height: 1.7;
  }

  /* Footer */
  .mt-footer {
    text-align: center;
    padding: 32px 0;
    border-top: 1px solid var(--mt-border);
    margin-top: 40px;
  }

  .mt-footer p {
    color: var(--mt-text-muted);
    font-size: 0.85rem;
    margin: 0;
  }

  .mt-footer a {
    color: var(--mt-primary-light);
    text-decoration: none;
  }

  .mt-footer a:hover {
    text-decoration: underline;
  }

  .mt-last-updated {
    font-size: 0.78rem;
    color: var(--mt-text-muted);
    text-align: center;
    margin-top: 8px;
  }
</style>

<div class="mt-wrapper">

  <!-- JSON-LD -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "WebApplication",
    "name": "Free Meta Tag Generator",
    "description": "Generate SEO meta tags, Open Graph tags, Twitter Cards, and structured data for your website. Free meta tag generator with live Google SERP preview and character counting.",
    "url": "https://theluckystrike.github.io/tools/meta-tag-generator/",
    "applicationCategory": "SEO Tool",
    "operatingSystem": "Any",
    "offers": {
      "@type": "Offer",
      "price": "0",
      "priceCurrency": "USD"
    },
    "author": {
      "@type": "Person",
      "name": "Michael Lip",
      "url": "https://zovo.one"
    },
    "datePublished": "2026-03-19",
    "dateModified": "2026-03-19"
  }
  </script>

  <div class="mt-hero">
    <h1>Free <span>Meta Tag Generator</span></h1>
    <p class="mt-intro">Generate complete SEO meta tags, Open Graph tags, and Twitter Cards for your website. See live Google, Facebook, and Twitter previews as you type.</p>
  </div>

  <!-- Basic SEO Section -->
  <div class="mt-card">
    <div class="mt-card-title">Basic SEO Meta Tags</div>
    <div class="mt-input-grid">
      <div class="mt-field full-width">
        <div class="mt-label-row">
          <label class="mt-label" for="mtTitle">Page Title</label>
          <span class="mt-char-counter" id="mtTitleCounter">0/60</span>
        </div>
        <input type="text" class="mt-input" id="mtTitle" placeholder="Your page title (50-60 characters ideal)" maxlength="200" autocomplete="off">
      </div>
      <div class="mt-field full-width">
        <div class="mt-label-row">
          <label class="mt-label" for="mtDesc">Meta Description</label>
          <span class="mt-char-counter" id="mtDescCounter">0/160</span>
        </div>
        <textarea class="mt-textarea" id="mtDesc" placeholder="Your meta description (150-160 characters ideal)" maxlength="500"></textarea>
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtUrl">Canonical URL</label>
        <input type="url" class="mt-input" id="mtUrl" placeholder="https://example.com/page" autocomplete="off">
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtAuthor">Author</label>
        <input type="text" class="mt-input" id="mtAuthor" placeholder="Author name" autocomplete="off">
      </div>
      <div class="mt-field full-width">
        <label class="mt-label">Keywords</label>
        <div class="mt-chips-wrap" id="mtChipsWrap" onclick="document.getElementById('mtKeywordInput').focus()">
          <input type="text" class="mt-chip-input" id="mtKeywordInput" placeholder="Type keyword and press Enter or comma">
        </div>
      </div>
      <div class="mt-field">
        <label class="mt-label">Robots Directives</label>
        <div class="mt-checkbox-group">
          <label class="mt-checkbox-label"><input type="checkbox" id="mtRobotIndex" checked> index</label>
          <label class="mt-checkbox-label"><input type="checkbox" id="mtRobotFollow" checked> follow</label>
          <label class="mt-checkbox-label"><input type="checkbox" id="mtRobotNoindex"> noindex</label>
          <label class="mt-checkbox-label"><input type="checkbox" id="mtRobotNofollow"> nofollow</label>
        </div>
      </div>
      <div class="mt-field">
        <div class="mt-input-grid" style="gap: 12px;">
          <div>
            <label class="mt-label" for="mtLang">Language</label>
            <select class="mt-select" id="mtLang">
              <option value="en">English</option>
              <option value="es">Spanish</option>
              <option value="fr">French</option>
              <option value="de">German</option>
              <option value="pt">Portuguese</option>
              <option value="it">Italian</option>
              <option value="nl">Dutch</option>
              <option value="ja">Japanese</option>
              <option value="ko">Korean</option>
              <option value="zh">Chinese</option>
              <option value="ru">Russian</option>
              <option value="ar">Arabic</option>
            </select>
          </div>
          <div>
            <label class="mt-label" for="mtCharset">Charset</label>
            <select class="mt-select" id="mtCharset">
              <option value="UTF-8">UTF-8</option>
              <option value="ISO-8859-1">ISO-8859-1</option>
              <option value="Windows-1252">Windows-1252</option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Open Graph Section -->
  <div class="mt-card">
    <div class="mt-card-title">Open Graph Tags</div>
    <div class="mt-input-grid">
      <div class="mt-field">
        <label class="mt-label" for="mtOgTitle">OG Title <span style="font-weight:400; color:#555;">(defaults to Page Title)</span></label>
        <input type="text" class="mt-input" id="mtOgTitle" placeholder="Leave blank to use page title" autocomplete="off">
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtOgType">OG Type</label>
        <select class="mt-select" id="mtOgType">
          <option value="website">website</option>
          <option value="article">article</option>
          <option value="product">product</option>
          <option value="profile">profile</option>
        </select>
      </div>
      <div class="mt-field full-width">
        <label class="mt-label" for="mtOgDesc">OG Description <span style="font-weight:400; color:#555;">(defaults to Meta Description)</span></label>
        <input type="text" class="mt-input" id="mtOgDesc" placeholder="Leave blank to use meta description" autocomplete="off">
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtOgImage">OG Image URL</label>
        <input type="url" class="mt-input" id="mtOgImage" placeholder="https://example.com/image.jpg" autocomplete="off">
        <div class="mt-og-preview" id="mtOgImgPreview">
          <span class="mt-og-preview-placeholder">No image</span>
        </div>
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtOgSiteName">OG Site Name</label>
        <input type="text" class="mt-input" id="mtOgSiteName" placeholder="Your Site Name" autocomplete="off">
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtOgLocale">OG Locale</label>
        <select class="mt-select" id="mtOgLocale">
          <option value="en_US">en_US</option>
          <option value="en_GB">en_GB</option>
          <option value="es_ES">es_ES</option>
          <option value="fr_FR">fr_FR</option>
          <option value="de_DE">de_DE</option>
          <option value="pt_BR">pt_BR</option>
          <option value="it_IT">it_IT</option>
          <option value="ja_JP">ja_JP</option>
          <option value="ko_KR">ko_KR</option>
          <option value="zh_CN">zh_CN</option>
        </select>
      </div>
    </div>
  </div>

  <!-- Twitter Card Section -->
  <div class="mt-card">
    <div class="mt-card-title">Twitter Card Tags</div>
    <div class="mt-input-grid">
      <div class="mt-field">
        <label class="mt-label" for="mtTwCard">Card Type</label>
        <select class="mt-select" id="mtTwCard">
          <option value="summary">summary</option>
          <option value="summary_large_image" selected>summary_large_image</option>
          <option value="app">app</option>
          <option value="player">player</option>
        </select>
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtTwSite">Twitter Site @handle</label>
        <input type="text" class="mt-input" id="mtTwSite" placeholder="@yoursite" autocomplete="off">
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtTwCreator">Twitter Creator @handle</label>
        <input type="text" class="mt-input" id="mtTwCreator" placeholder="@author" autocomplete="off">
      </div>
      <div class="mt-field">
        <label class="mt-label" for="mtTwImage">Twitter Image URL <span style="font-weight:400; color:#555;">(defaults to OG Image)</span></label>
        <input type="url" class="mt-input" id="mtTwImage" placeholder="Leave blank to use OG image" autocomplete="off">
      </div>
    </div>
  </div>

  <!-- Live Previews -->
  <div class="mt-card">
    <div class="mt-card-title">Live Previews</div>
    <div class="mt-preview-grid">
      <!-- Google SERP -->
      <div>
        <div style="font-size: 0.82rem; color: var(--mt-text-muted); margin-bottom: 8px; font-weight: 500;">Google Search Preview</div>
        <div class="mt-serp-preview">
          <div class="mt-serp-title" id="mtSerpTitle">Your Page Title</div>
          <div class="mt-serp-url" id="mtSerpUrl">https://example.com</div>
          <div class="mt-serp-desc" id="mtSerpDesc">Your meta description will appear here. Google typically shows 155-160 characters.</div>
        </div>
      </div>
      <!-- Facebook -->
      <div>
        <div style="font-size: 0.82rem; color: var(--mt-text-muted); margin-bottom: 8px; font-weight: 500;">Facebook Share Preview</div>
        <div class="mt-fb-preview">
          <div class="mt-fb-image" id="mtFbImage">
            <span class="mt-fb-image-placeholder">No OG Image Set</span>
          </div>
          <div class="mt-fb-bar">
            <div class="mt-fb-site" id="mtFbSite">example.com</div>
            <div class="mt-fb-title" id="mtFbTitle">Your Page Title</div>
            <div class="mt-fb-desc" id="mtFbDesc">Your description here</div>
          </div>
        </div>
      </div>
      <!-- Twitter -->
      <div>
        <div style="font-size: 0.82rem; color: var(--mt-text-muted); margin-bottom: 8px; font-weight: 500;">Twitter Card Preview</div>
        <div class="mt-tw-preview">
          <div class="mt-tw-image" id="mtTwImagePreview">
            <span class="mt-fb-image-placeholder">No Image Set</span>
          </div>
          <div class="mt-tw-bar">
            <div class="mt-tw-title" id="mtTwTitle">Your Page Title</div>
            <div class="mt-tw-desc" id="mtTwDesc">Your description here</div>
            <div class="mt-tw-site" id="mtTwSitePreview">example.com</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Validation Warnings -->
  <div class="mt-card">
    <div class="mt-card-title">Validation</div>
    <ul class="mt-warnings" id="mtWarnings">
      <li><span class="mt-warn-icon warning">&#9888;</span> Fill in the fields above to see validation results</li>
    </ul>
  </div>

  <!-- Generated Code Output -->
  <div class="mt-card">
    <div class="mt-card-title">Generated Meta Tags</div>
    <div class="mt-code-header">
      <div class="mt-toggle-row">
        <label class="mt-toggle">
          <input type="checkbox" id="mtIncludeOptional" checked onchange="mtGenerate()">
          <span class="mt-toggle-slider"></span>
        </label>
        <span class="mt-toggle-label">Include optional tags</span>
      </div>
      <div class="mt-code-actions">
        <button class="mt-code-btn primary" onclick="mtCopyCode()">Copy Code</button>
        <button class="mt-code-btn" onclick="mtDownloadCode()">Download .html</button>
      </div>
    </div>
    <div class="mt-code-block" id="mtCodeOutput"><span class="comment">&lt;!-- Fill in the fields above to generate meta tags --&gt;</span></div>
  </div>

  <!-- Cross-links -->
  <div class="mt-card" style="margin-top: 24px;">
    <div class="mt-card-title">Related Tools</div>
    <div class="mt-crosslinks">
      <a href="/tools/headline-analyzer/" class="mt-crosslink">
        <span class="mt-crosslink-icon">&#128221;</span> Headline Analyzer
      </a>
      <a href="/tools/web-scraper/" class="mt-crosslink">
        <span class="mt-crosslink-icon">&#127760;</span> Web Scraper
      </a>
      <a href="/tools/json-formatter/" class="mt-crosslink">
        <span class="mt-crosslink-icon">&#128230;</span> JSON Formatter
      </a>
      <a href="/tools/ai-detector/" class="mt-crosslink">
        <span class="mt-crosslink-icon">&#129302;</span> AI Content Detector
      </a>
    </div>
  </div>

  <!-- E-E-A-T Author Box -->
  <div class="mt-author-box">
    <div class="mt-author-avatar">ML</div>
    <div class="mt-author-info">
      <h4>Michael Lip</h4>
      <p>SEO tools developer building free, privacy-first web tools at <a href="https://zovo.one" style="color: var(--mt-primary-light); text-decoration: none;">zovo.one</a>. Focused on helping developers and marketers optimize their websites for search engines and social sharing.</p>
    </div>
  </div>

  <div class="mt-last-updated">Last updated: March 19, 2026</div>

  <!-- SEO Content -->
  <div class="mt-content">

<h2>What Are Meta Tags</h2>

<p>Meta tags are snippets of HTML code that provide structured information about a web page to search engines and social media platforms. They live in the <code>&lt;head&gt;</code> section of your HTML and are not visible to visitors browsing the page. Despite being invisible, they have a significant impact on how your page appears in search results, social shares, and browser tabs.</p>

<p>The most important meta tags for SEO are the title tag and the meta description. The title tag determines the clickable headline that appears in Google search results. The meta description provides the summary text below that headline. Together, they form your page's first impression in search results and directly influence click-through rates.</p>

<p>Beyond basic SEO, meta tags also control how your content appears when shared on social platforms through Open Graph (Facebook, LinkedIn) and Twitter Card tags. These protocols let you specify exactly what image, title, and description appear in social posts, rather than leaving it to the platform's scraper to guess.</p>

<h2>Essential Meta Tags for SEO</h2>

<p>The title tag is the single most important on-page SEO element. It should contain your primary keyword, accurately describe the page content, and stay within 50-60 characters to avoid truncation in search results. Google measures the title display width in pixels (approximately 580px), so titles with wider characters like uppercase W or M may truncate sooner than titles using narrower characters.</p>

<p>The meta description should summarize your page content in 150-160 characters. While Google does not use the meta description as a direct ranking factor, it heavily influences CTR. A compelling description that includes relevant keywords (which Google bolds in results) can meaningfully increase your organic traffic without changing your ranking position.</p>

<p>The canonical URL tag tells search engines which version of a page is the "official" one. This prevents duplicate content issues when the same page is accessible through multiple URLs (with or without www, with tracking parameters, etc.). Every page should have a canonical tag pointing to its preferred URL.</p>

<p>The robots meta tag controls how search engines index and follow links on your page. The default behavior is <code>index, follow</code>, meaning the page will be indexed and its links will be crawled. Use <code>noindex</code> for pages you want to keep out of search results, and <code>nofollow</code> to prevent search engines from following links on the page.</p>

<h2>Understanding Open Graph Tags</h2>

<p>Open Graph is a protocol originally created by Facebook that standardizes how web pages are represented when shared on social media. When someone shares a link on Facebook, LinkedIn, Pinterest, or most messaging apps, the platform reads the Open Graph tags to determine what image, title, and description to display in the share card.</p>

<p>The four required Open Graph properties are <code>og:title</code>, <code>og:type</code>, <code>og:image</code>, and <code>og:url</code>. The <code>og:description</code>, <code>og:site_name</code>, and <code>og:locale</code> properties are optional but recommended. If you omit OG tags, platforms will attempt to scrape the information from your page content, which often produces poor results -- a random image from the page, truncated text, or no preview at all.</p>

<p>The OG image is arguably the most impactful social tag because visual content dominates social feeds. Use an image that is at least 1200x630 pixels for optimal display across platforms. The image should be relevant to the page content and compelling enough to stop users from scrolling past.</p>

<h2>Twitter Card Types Explained</h2>

<p>Twitter Cards extend your tweets with rich media attachments. When someone shares a URL that has Twitter Card tags, Twitter displays a card below the tweet with the page's image, title, and description. There are four card types, each suited for different content.</p>

<p>The <code>summary</code> card shows a small square thumbnail next to the title and description. It works well for general articles and pages where the image is supplementary rather than central.</p>

<p>The <code>summary_large_image</code> card displays a large, prominent image above the title and description. This is the most popular type for blog posts, news articles, and landing pages because the large image captures more attention in the feed.</p>

<p>The <code>app</code> card is designed specifically for mobile applications, displaying a name, description, icon, rating, and a download button. The <code>player</code> card embeds playable media (video or audio) directly in the tweet. Both require approval from Twitter before they function.</p>

<p>Twitter falls back to Open Graph tags when its own card tags are not present. If you set <code>og:title</code>, <code>og:description</code>, and <code>og:image</code>, Twitter will use those values. Adding dedicated Twitter Card tags gives you more control over the Twitter-specific appearance.</p>

<h2>Best Practices for Meta Descriptions</h2>

<p>Write meta descriptions as a pitch to the searcher. They have already typed a query into Google. Your description needs to convince them that your page has the answer. Include your primary keyword naturally -- Google bolds matching terms in the description, which draws the eye.</p>

<p>Keep descriptions between 150 and 160 characters. Google truncates longer descriptions, and shorter ones waste valuable real estate. Use the full space to communicate your page's value proposition. Avoid filler phrases that do not add information.</p>

<p>Each page on your site should have a unique meta description. Duplicate descriptions across multiple pages make it harder for searchers to distinguish between your pages and can signal low-quality content to search engines. If writing unique descriptions for hundreds of pages seems impractical, prioritize your highest-traffic pages first.</p>

<p>Avoid using quotation marks in meta descriptions. Google sometimes truncates descriptions at the quotation mark. If you need to reference a quote, use single quotes or rephrase the text.</p>

<p>Do not stuff keywords into the meta description. Google's algorithm is sophisticated enough to understand topical relevance without keyword repetition. One or two instances of your primary keyword is sufficient. Focus the rest of the description on communicating value and encouraging the click.</p>

  </div>

  <!-- FAQ -->
  <div class="mt-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="mt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Are meta keywords still important for SEO?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Google has officially stated that it does not use the meta keywords tag as a ranking signal. It stopped using it in 2009. However, some smaller search engines like Yandex may still consider it. Including a few relevant keywords does not hurt, but do not invest significant time in the keywords meta tag. Focus your efforts on the title tag and meta description instead, as those directly impact how your page appears in search results.</p>
      </div>
    </div>

    <div class="mt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What happens if I do not set Open Graph tags?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">When OG tags are missing, social platforms will try to scrape your page content automatically. Facebook might pull a random image from your page (often a logo, sidebar image, or advertisement), and the title and description may be truncated or irrelevant. The result is an unappealing share card that gets fewer clicks. Setting explicit OG tags ensures you control exactly what appears when your content is shared.</p>
      </div>
    </div>

    <div class="mt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the ideal OG image size?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Facebook recommends 1200 x 630 pixels for optimal display across all devices. Twitter recommends a 2:1 aspect ratio for summary_large_image cards, with a minimum of 300 x 157 pixels and a maximum of 4096 x 4096 pixels. For best cross-platform results, create images at 1200 x 630 pixels. Keep file sizes under 5MB, and use JPG or PNG formats.</p>
      </div>
    </div>

    <div class="mt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can Google rewrite my title tag in search results?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Since 2021, Google has been actively rewriting title tags when it believes its version will be more useful to searchers. Common reasons for rewrites include titles that are too long, stuffed with keywords, do not match the page content, or use boilerplate formatting. To minimize rewrites, write concise and accurate titles under 60 characters that closely match your H1 heading and page content.</p>
      </div>
    </div>

    <div class="mt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Should I use the same title for the title tag and OG title?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Using the same title is perfectly fine and is the simplest approach. However, you may want different titles for each context. Your title tag should be optimized for search (including keywords, staying under 60 characters). Your OG title is optimized for social sharing, where you have slightly more character space and might use a more conversational or attention-grabbing format. This generator defaults the OG title to your page title but lets you customize it separately.</p>
      </div>
    </div>

    <div class="mt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe when using this tool?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This generator runs entirely in your web browser using JavaScript. No data is transmitted to any server, and nothing is stored beyond your current browser session. Your page titles, descriptions, URLs, and all other inputs remain on your device. You can verify this by checking the Network tab in your browser's developer tools while using the tool.</p>
      </div>
    </div>

  </div>

  <footer class="mt-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  // --- DOM Refs ---
  var elTitle = document.getElementById("mtTitle");
  var elDesc = document.getElementById("mtDesc");
  var elUrl = document.getElementById("mtUrl");
  var elAuthor = document.getElementById("mtAuthor");
  var elLang = document.getElementById("mtLang");
  var elCharset = document.getElementById("mtCharset");
  var elRobotIndex = document.getElementById("mtRobotIndex");
  var elRobotFollow = document.getElementById("mtRobotFollow");
  var elRobotNoindex = document.getElementById("mtRobotNoindex");
  var elRobotNofollow = document.getElementById("mtRobotNofollow");
  var elOgTitle = document.getElementById("mtOgTitle");
  var elOgDesc = document.getElementById("mtOgDesc");
  var elOgImage = document.getElementById("mtOgImage");
  var elOgType = document.getElementById("mtOgType");
  var elOgSiteName = document.getElementById("mtOgSiteName");
  var elOgLocale = document.getElementById("mtOgLocale");
  var elTwCard = document.getElementById("mtTwCard");
  var elTwSite = document.getElementById("mtTwSite");
  var elTwCreator = document.getElementById("mtTwCreator");
  var elTwImage = document.getElementById("mtTwImage");
  var elIncludeOptional = document.getElementById("mtIncludeOptional");

  var keywords = [];
  var debounceTimer = null;

  // --- Character Counters ---
  function updateTitleCounter() {
    var len = elTitle.value.length;
    var el = document.getElementById("mtTitleCounter");
    el.textContent = len + "/60";
    el.className = "mt-char-counter " + (len >= 50 && len <= 60 ? "ok" : (len > 60 ? "over" : (len > 0 ? "warn" : "")));
  }

  function updateDescCounter() {
    var len = elDesc.value.length;
    var el = document.getElementById("mtDescCounter");
    el.textContent = len + "/160";
    el.className = "mt-char-counter " + (len >= 150 && len <= 160 ? "ok" : (len > 160 ? "over" : (len > 0 ? "warn" : "")));
  }

  // --- Keyword Chips ---
  var chipInput = document.getElementById("mtKeywordInput");
  var chipsWrap = document.getElementById("mtChipsWrap");

  function renderChips() {
    var existing = chipsWrap.querySelectorAll(".mt-chip");
    for (var i = 0; i < existing.length; i++) {
      existing[i].remove();
    }
    for (var i = 0; i < keywords.length; i++) {
      var chip = document.createElement("span");
      chip.className = "mt-chip";
      chip.innerHTML = keywords[i] + ' <button class="mt-chip-remove" data-idx="' + i + '">&times;</button>';
      chipsWrap.insertBefore(chip, chipInput);
    }
  }

  chipInput.addEventListener("keydown", function(e) {
    if (e.key === "Enter" || e.key === ",") {
      e.preventDefault();
      addKeyword();
    }
    if (e.key === "Backspace" && chipInput.value === "" && keywords.length > 0) {
      keywords.pop();
      renderChips();
      debouncedGenerate();
    }
  });

  chipInput.addEventListener("blur", function() {
    addKeyword();
  });

  chipsWrap.addEventListener("click", function(e) {
    if (e.target.classList.contains("mt-chip-remove")) {
      var idx = parseInt(e.target.getAttribute("data-idx"));
      keywords.splice(idx, 1);
      renderChips();
      debouncedGenerate();
    }
  });

  function addKeyword() {
    var val = chipInput.value.replace(/,/g, "").trim();
    if (val && keywords.indexOf(val) === -1) {
      keywords.push(val);
      chipInput.value = "";
      renderChips();
      debouncedGenerate();
    } else {
      chipInput.value = "";
    }
  }

  // --- Robots checkbox mutual exclusion ---
  elRobotIndex.addEventListener("change", function() {
    if (this.checked) elRobotNoindex.checked = false;
    debouncedGenerate();
  });
  elRobotNoindex.addEventListener("change", function() {
    if (this.checked) elRobotIndex.checked = false;
    debouncedGenerate();
  });
  elRobotFollow.addEventListener("change", function() {
    if (this.checked) elRobotNofollow.checked = false;
    debouncedGenerate();
  });
  elRobotNofollow.addEventListener("change", function() {
    if (this.checked) elRobotFollow.checked = false;
    debouncedGenerate();
  });

  // --- OG Image Preview ---
  elOgImage.addEventListener("input", function() {
    var preview = document.getElementById("mtOgImgPreview");
    var val = this.value.trim();
    if (val && (val.indexOf("http://") === 0 || val.indexOf("https://") === 0)) {
      preview.innerHTML = '<img src="' + escHtml(val) + '" alt="OG preview" onerror="this.parentElement.innerHTML=\'<span class=mt-og-preview-placeholder>Load error</span>\'">';
    } else {
      preview.innerHTML = '<span class="mt-og-preview-placeholder">No image</span>';
    }
    debouncedGenerate();
  });

  // --- Escape HTML ---
  function escHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;");
  }

  function escAttr(str) {
    return str.replace(/&/g, "&amp;").replace(/"/g, "&quot;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  // --- Live Previews ---
  function updatePreviews() {
    var title = elTitle.value || "Your Page Title";
    var desc = elDesc.value || "Your meta description will appear here.";
    var url = elUrl.value || "https://example.com";
    var ogTitle = elOgTitle.value || title;
    var ogDesc = elOgDesc.value || desc;
    var ogImage = elOgImage.value.trim();
    var twImage = elTwImage.value.trim() || ogImage;
    var siteName = elOgSiteName.value || extractDomain(url);

    // Google SERP
    var serpTitle = title.length > 60 ? title.substring(0, 57) + "..." : title;
    document.getElementById("mtSerpTitle").textContent = serpTitle;
    document.getElementById("mtSerpUrl").textContent = url;
    var serpDesc = desc.length > 160 ? desc.substring(0, 157) + "..." : desc;
    document.getElementById("mtSerpDesc").textContent = serpDesc;

    // Facebook
    document.getElementById("mtFbTitle").textContent = ogTitle;
    document.getElementById("mtFbDesc").textContent = ogDesc;
    document.getElementById("mtFbSite").textContent = siteName;
    var fbImgEl = document.getElementById("mtFbImage");
    if (ogImage) {
      fbImgEl.innerHTML = '<img src="' + escHtml(ogImage) + '" alt="OG" onerror="this.parentElement.innerHTML=\'<span class=mt-fb-image-placeholder>Image failed to load</span>\'">';
    } else {
      fbImgEl.innerHTML = '<span class="mt-fb-image-placeholder">No OG Image Set</span>';
    }

    // Twitter
    document.getElementById("mtTwTitle").textContent = ogTitle;
    document.getElementById("mtTwDesc").textContent = ogDesc;
    document.getElementById("mtTwSitePreview").textContent = extractDomain(url);
    var twImgEl = document.getElementById("mtTwImagePreview");
    if (twImage) {
      twImgEl.innerHTML = '<img src="' + escHtml(twImage) + '" alt="Twitter" onerror="this.parentElement.innerHTML=\'<span class=mt-fb-image-placeholder>Image failed to load</span>\'">';
    } else {
      twImgEl.innerHTML = '<span class="mt-fb-image-placeholder">No Image Set</span>';
    }
  }

  function extractDomain(url) {
    try {
      var a = document.createElement("a");
      a.href = url;
      return a.hostname || "example.com";
    } catch(e) {
      return "example.com";
    }
  }

  // --- Validation ---
  function validate() {
    var warnings = [];
    var title = elTitle.value.trim();
    var desc = elDesc.value.trim();
    var url = elUrl.value.trim();
    var ogImage = elOgImage.value.trim();

    if (!title) {
      warnings.push({ type: "error", text: "Page title is missing. This is required for SEO." });
    } else if (title.length > 60) {
      warnings.push({ type: "warning", text: "Title is " + title.length + " characters. It may be truncated in Google search results (recommended: 50-60)." });
    } else if (title.length < 30) {
      warnings.push({ type: "warning", text: "Title is only " + title.length + " characters. Consider making it more descriptive (recommended: 50-60)." });
    } else {
      warnings.push({ type: "success", text: "Title length (" + title.length + " chars) is within the optimal range." });
    }

    if (!desc) {
      warnings.push({ type: "error", text: "Meta description is missing. This is important for CTR in search results." });
    } else if (desc.length > 160) {
      warnings.push({ type: "warning", text: "Description is " + desc.length + " characters. Google may truncate it (recommended: 150-160)." });
    } else if (desc.length < 120) {
      warnings.push({ type: "warning", text: "Description is only " + desc.length + " characters. You have room for more detail (recommended: 150-160)." });
    } else {
      warnings.push({ type: "success", text: "Description length (" + desc.length + " chars) is within the optimal range." });
    }

    if (!url) {
      warnings.push({ type: "warning", text: "No canonical URL set. Consider adding one to prevent duplicate content issues." });
    } else if (url.indexOf("https://") !== 0 && url.indexOf("http://") !== 0) {
      warnings.push({ type: "warning", text: "URL should start with https:// for proper canonical tag generation." });
    } else {
      warnings.push({ type: "success", text: "Canonical URL is set." });
    }

    if (!ogImage) {
      warnings.push({ type: "warning", text: "No OG image set. Social shares will lack a preview image, significantly reducing engagement." });
    } else {
      warnings.push({ type: "success", text: "OG image URL is set. Make sure it is at least 1200x630 pixels." });
    }

    if (keywords.length === 0) {
      warnings.push({ type: "warning", text: "No keywords set. While not a major ranking factor, keywords can help with some search engines." });
    }

    var warnEl = document.getElementById("mtWarnings");
    var html = "";
    for (var i = 0; i < warnings.length; i++) {
      var w = warnings[i];
      var iconChar = w.type === "success" ? "&#10003;" : (w.type === "error" ? "&#10007;" : "&#9888;");
      html += '<li><span class="mt-warn-icon ' + w.type + '">' + iconChar + '</span>' + escHtml(w.text) + '</li>';
    }
    warnEl.innerHTML = html;
  }

  // --- Code Generation ---
  function mtGenerateCode() {
    var title = elTitle.value.trim();
    var desc = elDesc.value.trim();
    var url = elUrl.value.trim();
    var author = elAuthor.value.trim();
    var lang = elLang.value;
    var charset = elCharset.value;
    var ogTitle = elOgTitle.value.trim() || title;
    var ogDesc = elOgDesc.value.trim() || desc;
    var ogImage = elOgImage.value.trim();
    var ogType = elOgType.value;
    var ogSiteName = elOgSiteName.value.trim();
    var ogLocale = elOgLocale.value;
    var twCard = elTwCard.value;
    var twSite = elTwSite.value.trim();
    var twCreator = elTwCreator.value.trim();
    var twImage = elTwImage.value.trim() || ogImage;
    var includeOptional = elIncludeOptional.checked;

    // Build robots
    var robotParts = [];
    if (elRobotIndex.checked) robotParts.push("index");
    if (elRobotNoindex.checked) robotParts.push("noindex");
    if (elRobotFollow.checked) robotParts.push("follow");
    if (elRobotNofollow.checked) robotParts.push("nofollow");
    var robotsStr = robotParts.join(", ");

    var lines = [];
    var raw = []; // for copy (no syntax highlighting)

    function addLine(rawStr) {
      raw.push(rawStr);
      // Syntax highlight
      var highlighted = rawStr
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/(&lt;\/?)([\w-]+)/g, '$1<span class="tag">$2</span>')
        .replace(/([\w-]+)(=)/g, '<span class="attr">$1</span>$2')
        .replace(/(=)(&quot;|")(.*?)(&quot;|")/g, '$1<span class="val">"$3"</span>');
      lines.push(highlighted);
    }

    function addComment(text) {
      raw.push("<!-- " + text + " -->");
      lines.push('<span class="comment">&lt;!-- ' + text + ' --&gt;</span>');
    }

    // Basic
    addComment("Basic Meta Tags");
    addLine('<meta charset="' + charset + '">');
    addLine('<meta name="viewport" content="width=device-width, initial-scale=1.0">');
    if (title) addLine('<title>' + title + '</title>');
    if (desc) addLine('<meta name="description" content="' + desc + '">');
    if (keywords.length > 0 && includeOptional) addLine('<meta name="keywords" content="' + keywords.join(", ") + '">');
    if (author && includeOptional) addLine('<meta name="author" content="' + author + '">');
    if (robotsStr) addLine('<meta name="robots" content="' + robotsStr + '">');
    if (url) addLine('<link rel="canonical" href="' + url + '">');
    if (includeOptional) addLine('<meta http-equiv="content-language" content="' + lang + '">');

    addLine("");
    addComment("Open Graph / Facebook");
    if (ogTitle) addLine('<meta property="og:title" content="' + ogTitle + '">');
    if (ogDesc) addLine('<meta property="og:description" content="' + ogDesc + '">');
    if (url) addLine('<meta property="og:url" content="' + url + '">');
    addLine('<meta property="og:type" content="' + ogType + '">');
    if (ogImage) addLine('<meta property="og:image" content="' + ogImage + '">');
    if (ogSiteName && includeOptional) addLine('<meta property="og:site_name" content="' + ogSiteName + '">');
    if (includeOptional) addLine('<meta property="og:locale" content="' + ogLocale + '">');

    addLine("");
    addComment("Twitter Card");
    addLine('<meta name="twitter:card" content="' + twCard + '">');
    if (ogTitle) addLine('<meta name="twitter:title" content="' + ogTitle + '">');
    if (ogDesc) addLine('<meta name="twitter:description" content="' + ogDesc + '">');
    if (twImage) addLine('<meta name="twitter:image" content="' + twImage + '">');
    if (twSite && includeOptional) addLine('<meta name="twitter:site" content="' + twSite + '">');
    if (twCreator && includeOptional) addLine('<meta name="twitter:creator" content="' + twCreator + '">');

    return { highlighted: lines.join("\n"), raw: raw.join("\n") };
  }

  window.mtGenerate = function() {
    var code = mtGenerateCode();
    document.getElementById("mtCodeOutput").innerHTML = code.highlighted;
    updatePreviews();
    validate();
  };

  window.mtCopyCode = function() {
    var code = mtGenerateCode();
    navigator.clipboard.writeText(code.raw).then(function() {
      var btns = document.querySelectorAll(".mt-code-btn.primary");
      if (btns.length > 0) {
        var btn = btns[0];
        var orig = btn.textContent;
        btn.textContent = "Copied";
        btn.style.background = "var(--mt-green-dark)";
        btn.style.borderColor = "var(--mt-green-dark)";
        setTimeout(function() {
          btn.textContent = orig;
          btn.style.background = "";
          btn.style.borderColor = "";
        }, 2000);
      }
    });
  };

  window.mtDownloadCode = function() {
    var code = mtGenerateCode();
    var blob = new Blob([code.raw], { type: "text/html" });
    var a = document.createElement("a");
    a.href = URL.createObjectURL(blob);
    a.download = "meta-tags.html";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(a.href);
  };

  // --- Debounced generation ---
  function debouncedGenerate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(function() {
      mtGenerate();
    }, 150);
  }

  // --- Attach listeners ---
  var allInputs = [elTitle, elDesc, elUrl, elAuthor, elOgTitle, elOgDesc, elOgImage,
    elOgSiteName, elTwSite, elTwCreator, elTwImage];

  for (var i = 0; i < allInputs.length; i++) {
    allInputs[i].addEventListener("input", debouncedGenerate);
  }

  var allSelects = [elLang, elCharset, elOgType, elOgLocale, elTwCard];
  for (var i = 0; i < allSelects.length; i++) {
    allSelects[i].addEventListener("change", debouncedGenerate);
  }

  elTitle.addEventListener("input", updateTitleCounter);
  elDesc.addEventListener("input", updateDescCounter);

  // Init
  updateTitleCounter();
  updateDescCounter();
  updatePreviews();

})();
</script>
