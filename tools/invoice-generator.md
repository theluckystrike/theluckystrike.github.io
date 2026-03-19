---
layout: page
title: "Free Invoice Generator — Create Professional Invoices Online | Zovo"
description: "Create and download professional invoices for free. Add your logo, line items, taxes, and discounts. Generate PDF-ready invoices with automatic calculations and customizable templates."
permalink: /tools/invoice-generator/
keywords: "invoice generator, free invoice maker, create invoice online, invoice template, invoice creator, billing generator, receipt maker, professional invoice"
date: 2026-03-19
categories: [tools]
tags: [invoice, generator, billing, business, finance, pdf, receipt]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --inv-primary: #6C5CE7;
    --inv-primary-dark: #5A4BD1;
    --inv-primary-light: #A29BFE;
    --inv-bg: #0a0a0f;
    --inv-surface: #12121a;
    --inv-surface-alt: #181824;
    --inv-border: #1e1e2e;
    --inv-text: #e0e0e0;
    --inv-text-muted: #8888aa;
    --inv-green: #00ff88;
    --inv-green-dark: #00cc6a;
    --inv-red: #ff4466;
    --inv-radius: 12px;
    --inv-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .inv-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--inv-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .inv-wrapper * {
    box-sizing: border-box;
  }

  .inv-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .inv-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--inv-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .inv-hero h1 span {
    color: var(--inv-primary);
  }

  .inv-intro {
    font-size: 1.05rem;
    color: var(--inv-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Layout */
  .inv-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    align-items: start;
    margin-bottom: 32px;
  }

  /* Card */
  .inv-card {
    background: var(--inv-surface);
    border: 1px solid var(--inv-border);
    border-radius: var(--inv-radius);
    padding: 24px;
    box-shadow: var(--inv-shadow);
  }

  .inv-card-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--inv-text-muted);
    margin: 0 0 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .inv-card-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--inv-primary);
    border-radius: 2px;
  }

  /* Fields */
  .inv-field {
    margin-bottom: 14px;
  }

  .inv-field:last-child {
    margin-bottom: 0;
  }

  .inv-label {
    display: block;
    font-size: 0.82rem;
    font-weight: 500;
    color: var(--inv-text-muted);
    margin-bottom: 5px;
  }

  .inv-input, .inv-textarea, .inv-select {
    width: 100%;
    padding: 9px 12px;
    background: var(--inv-bg);
    border: 1px solid var(--inv-border);
    border-radius: 8px;
    color: var(--inv-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
  }

  .inv-input:focus, .inv-textarea:focus, .inv-select:focus {
    border-color: var(--inv-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .inv-input.mono {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
  }

  .inv-textarea {
    resize: vertical;
    min-height: 60px;
    font-size: 0.85rem;
  }

  .inv-select {
    cursor: pointer;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%238888aa' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    padding-right: 32px;
  }

  .inv-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .inv-row-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 12px;
  }

  /* Logo Upload */
  .inv-logo-zone {
    width: 100%;
    height: 80px;
    border: 2px dashed var(--inv-border);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: border-color 0.2s ease;
    position: relative;
    overflow: hidden;
  }

  .inv-logo-zone:hover {
    border-color: var(--inv-primary);
  }

  .inv-logo-zone img {
    max-height: 70px;
    max-width: 100%;
    object-fit: contain;
  }

  .inv-logo-zone span {
    font-size: 0.8rem;
    color: var(--inv-text-muted);
  }

  .inv-logo-zone input {
    position: absolute;
    inset: 0;
    opacity: 0;
    cursor: pointer;
  }

  /* Line Items Table */
  .inv-items-table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 12px;
  }

  .inv-items-table th {
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--inv-text-muted);
    padding: 8px 6px;
    text-align: left;
    border-bottom: 1px solid var(--inv-border);
  }

  .inv-items-table th:nth-child(2),
  .inv-items-table th:nth-child(3),
  .inv-items-table th:nth-child(4) {
    text-align: right;
    width: 100px;
  }

  .inv-items-table th:last-child {
    width: 36px;
    text-align: center;
  }

  .inv-items-table td {
    padding: 6px;
    vertical-align: middle;
  }

  .inv-items-table td:nth-child(2),
  .inv-items-table td:nth-child(3),
  .inv-items-table td:nth-child(4) {
    text-align: right;
  }

  .inv-items-table td:last-child {
    text-align: center;
  }

  .inv-items-table .inv-input {
    padding: 7px 8px;
    font-size: 0.82rem;
  }

  .inv-items-table .inv-input.mono {
    text-align: right;
  }

  .inv-item-amount {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--inv-text);
    padding-right: 8px;
  }

  .inv-remove-btn {
    background: none;
    border: none;
    color: var(--inv-text-muted);
    cursor: pointer;
    font-size: 1rem;
    padding: 4px;
    border-radius: 4px;
    transition: color 0.2s ease, background 0.2s ease;
    line-height: 1;
  }

  .inv-remove-btn:hover {
    color: var(--inv-red);
    background: rgba(255, 68, 102, 0.1);
  }

  .inv-add-row-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 14px;
    background: transparent;
    border: 1px dashed var(--inv-border);
    border-radius: 8px;
    color: var(--inv-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    cursor: pointer;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .inv-add-row-btn:hover {
    border-color: var(--inv-primary);
    color: var(--inv-primary-light);
  }

  /* Summary */
  .inv-summary {
    margin-top: 20px;
    border-top: 1px solid var(--inv-border);
    padding-top: 16px;
  }

  .inv-summary-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 6px 0;
    font-size: 0.88rem;
  }

  .inv-summary-row .inv-summary-label {
    color: var(--inv-text-muted);
  }

  .inv-summary-row .inv-summary-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
  }

  .inv-summary-row.total {
    border-top: 2px solid var(--inv-border);
    margin-top: 8px;
    padding-top: 12px;
  }

  .inv-summary-row.total .inv-summary-label {
    color: var(--inv-text);
    font-weight: 700;
    font-size: 0.95rem;
  }

  .inv-summary-row.total .inv-summary-value {
    color: var(--inv-green);
    font-weight: 700;
    font-size: 1.1rem;
  }

  .inv-disc-row {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .inv-disc-row .inv-input {
    width: 80px;
    text-align: right;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
  }

  .inv-disc-row .inv-select {
    width: 60px;
    font-size: 0.8rem;
    padding: 6px 8px;
  }

  /* Action Buttons */
  .inv-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 20px;
  }

  .inv-btn {
    padding: 10px 20px;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
    border: none;
  }

  .inv-btn-primary {
    background: var(--inv-primary);
    color: white;
  }

  .inv-btn-primary:hover {
    background: var(--inv-primary-dark);
  }

  .inv-btn-outline {
    background: transparent;
    border: 1px solid var(--inv-border);
    color: var(--inv-text-muted);
  }

  .inv-btn-outline:hover {
    border-color: var(--inv-primary);
    color: var(--inv-text);
  }

  .inv-btn-danger {
    background: transparent;
    border: 1px solid rgba(255, 68, 102, 0.3);
    color: var(--inv-red);
  }

  .inv-btn-danger:hover {
    background: rgba(255, 68, 102, 0.08);
    border-color: var(--inv-red);
  }

  /* Drafts Panel */
  .inv-drafts-bar {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 24px;
    align-items: center;
  }

  .inv-draft-chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 12px;
    background: var(--inv-surface);
    border: 1px solid var(--inv-border);
    border-radius: 20px;
    font-size: 0.78rem;
    color: var(--inv-text-muted);
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .inv-draft-chip:hover {
    border-color: var(--inv-primary);
    color: var(--inv-text);
  }

  .inv-draft-chip .inv-draft-del {
    color: var(--inv-text-muted);
    font-size: 0.7rem;
    cursor: pointer;
    margin-left: 2px;
  }

  .inv-draft-chip .inv-draft-del:hover {
    color: var(--inv-red);
  }

  .inv-drafts-label {
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--inv-text-muted);
    margin-right: 4px;
  }

  /* Invoice Preview */
  .inv-preview-wrap {
    position: sticky;
    top: 20px;
  }

  .inv-preview {
    background: #ffffff;
    border-radius: var(--inv-radius);
    padding: 40px;
    color: #1a1a2e;
    font-family: 'Inter', sans-serif;
    box-shadow: var(--inv-shadow);
    min-height: 600px;
  }

  .inv-preview-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 32px;
    padding-bottom: 20px;
    border-bottom: 2px solid #6C5CE7;
  }

  .inv-preview-logo img {
    max-height: 60px;
    max-width: 180px;
    object-fit: contain;
  }

  .inv-preview-logo .inv-preview-biz-name {
    font-size: 1.4rem;
    font-weight: 700;
    color: #1a1a2e;
    margin: 0;
  }

  .inv-preview-title {
    text-align: right;
  }

  .inv-preview-title h2 {
    font-size: 1.6rem;
    font-weight: 700;
    color: #6C5CE7;
    margin: 0 0 4px;
    letter-spacing: 0.02em;
  }

  .inv-preview-title p {
    font-size: 0.85rem;
    color: #666;
    margin: 2px 0;
  }

  .inv-preview-parties {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 32px;
    margin-bottom: 28px;
  }

  .inv-preview-party-label {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: #999;
    margin: 0 0 8px;
  }

  .inv-preview-party-name {
    font-size: 1rem;
    font-weight: 600;
    color: #1a1a2e;
    margin: 0 0 4px;
  }

  .inv-preview-party-detail {
    font-size: 0.82rem;
    color: #555;
    margin: 2px 0;
    line-height: 1.5;
  }

  .inv-preview-details {
    display: flex;
    gap: 24px;
    flex-wrap: wrap;
    margin-bottom: 24px;
    padding: 12px 16px;
    background: #f7f7fb;
    border-radius: 8px;
  }

  .inv-preview-detail-item {
    flex: 1;
    min-width: 120px;
  }

  .inv-preview-detail-label {
    font-size: 0.68rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: #999;
    margin: 0 0 2px;
  }

  .inv-preview-detail-value {
    font-size: 0.88rem;
    font-weight: 600;
    color: #1a1a2e;
    margin: 0;
  }

  /* Preview Table */
  .inv-preview-table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 24px;
  }

  .inv-preview-table th {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: #999;
    padding: 10px 8px;
    text-align: left;
    border-bottom: 2px solid #eee;
  }

  .inv-preview-table th:nth-child(2),
  .inv-preview-table th:nth-child(3),
  .inv-preview-table th:nth-child(4) {
    text-align: right;
  }

  .inv-preview-table td {
    padding: 10px 8px;
    font-size: 0.85rem;
    color: #333;
    border-bottom: 1px solid #f0f0f0;
  }

  .inv-preview-table td:nth-child(2),
  .inv-preview-table td:nth-child(3),
  .inv-preview-table td:nth-child(4) {
    text-align: right;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
  }

  .inv-preview-summary {
    display: flex;
    justify-content: flex-end;
    margin-bottom: 28px;
  }

  .inv-preview-summary-inner {
    width: 260px;
  }

  .inv-preview-sum-row {
    display: flex;
    justify-content: space-between;
    padding: 5px 0;
    font-size: 0.85rem;
    color: #555;
  }

  .inv-preview-sum-row span:last-child {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
  }

  .inv-preview-sum-total {
    display: flex;
    justify-content: space-between;
    padding: 10px 0;
    margin-top: 6px;
    border-top: 2px solid #1a1a2e;
    font-size: 1rem;
    font-weight: 700;
    color: #1a1a2e;
  }

  .inv-preview-sum-total span:last-child {
    font-family: 'JetBrains Mono', monospace;
    color: #6C5CE7;
    font-size: 1.1rem;
  }

  .inv-preview-notes {
    margin-top: 28px;
    padding-top: 16px;
    border-top: 1px solid #eee;
  }

  .inv-preview-notes-label {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: #999;
    margin: 0 0 6px;
  }

  .inv-preview-notes-text {
    font-size: 0.82rem;
    color: #555;
    line-height: 1.6;
    white-space: pre-wrap;
  }

  .inv-preview-footer {
    margin-top: 32px;
    text-align: center;
    font-size: 0.72rem;
    color: #bbb;
  }

  /* Print Styles */
  @media print {
    body * { visibility: hidden; }
    .inv-preview, .inv-preview * { visibility: visible; }
    .inv-preview {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      padding: 20px 40px;
      box-shadow: none;
      border-radius: 0;
    }
    .inv-wrapper, .inv-hero, .inv-editor-col, .inv-drafts-bar,
    .inv-cross-links, .inv-content, .inv-faq, .inv-author-box,
    .inv-footer, .inv-updated, .inv-actions { display: none; }
  }

  /* Cross Links */
  .inv-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .inv-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--inv-surface);
    border: 1px solid var(--inv-border);
    border-radius: 8px;
    color: var(--inv-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .inv-cross-link:hover {
    border-color: var(--inv-primary);
    color: var(--inv-text);
  }

  /* Content */
  .inv-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .inv-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 2.5rem 0 1rem;
    color: var(--inv-text);
  }

  .inv-content p {
    font-size: 0.95rem;
    color: var(--inv-text-muted);
    line-height: 1.8;
    margin: 0 0 1rem;
  }

  .inv-content ul, .inv-content ol {
    color: var(--inv-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 1.5rem;
    margin: 0 0 1rem;
  }

  .inv-content li {
    margin-bottom: 0.4rem;
  }

  .inv-formula-block {
    background: var(--inv-surface);
    border: 1px solid var(--inv-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin: 1rem 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--inv-primary-light);
    overflow-x: auto;
  }

  /* Author Box */
  .inv-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--inv-surface);
    border: 1px solid var(--inv-border);
    border-radius: var(--inv-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .inv-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--inv-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .inv-author-info { flex: 1; }

  .inv-author-name {
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--inv-text);
    margin: 0 0 4px;
  }

  .inv-author-bio {
    font-size: 0.82rem;
    color: var(--inv-text-muted);
    line-height: 1.6;
    margin: 0;
  }

  /* FAQ */
  .inv-faq {
    max-width: 780px;
    margin: 2.5rem auto 0;
  }

  .inv-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--inv-text);
    margin: 0 0 1.2rem;
  }

  .inv-faq-item {
    border-bottom: 1px solid var(--inv-border);
    padding: 1rem 0;
  }

  .inv-faq-item:last-child {
    border-bottom: none;
  }

  .inv-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--inv-text);
    margin: 0 0 8px;
  }

  .inv-faq-item p {
    font-size: 0.9rem;
    color: var(--inv-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Updated */
  .inv-updated {
    text-align: center;
    font-size: 0.8rem;
    color: var(--inv-text-muted);
    margin-top: 16px;
  }

  /* Footer */
  .inv-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--inv-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--inv-border);
    margin-top: 3rem;
  }

  .inv-footer a {
    color: var(--inv-primary);
    text-decoration: none;
  }

  .inv-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 900px) {
    .inv-layout {
      grid-template-columns: 1fr;
    }
    .inv-preview-wrap {
      position: static;
    }
    .inv-hero h1 { font-size: 1.6rem; }
    .inv-preview { padding: 24px; }
    .inv-preview-parties { grid-template-columns: 1fr; gap: 16px; }
    .inv-row, .inv-row-3 { grid-template-columns: 1fr; }
    .inv-items-table th:nth-child(2),
    .inv-items-table th:nth-child(3) { width: 70px; }
  }

  @media (max-width: 600px) {
    .inv-hero h1 { font-size: 1.3rem; }
    .inv-card { padding: 16px; }
    .inv-preview { padding: 16px; }
    .inv-preview-header { flex-direction: column; gap: 12px; }
    .inv-preview-title { text-align: left; }
    .inv-preview-details { flex-direction: column; gap: 8px; }
    .inv-author-box { flex-direction: column; text-align: center; align-items: center; }
  }
</style>

<div class="inv-wrapper">

  <div class="inv-hero">
    <h1>Free <span>Invoice Generator</span></h1>
    <p class="inv-intro">Create professional invoices directly in your browser. Add your business details, line items, taxes, and discounts. Preview the result in real time and download a PDF-ready copy. No account needed, no data leaves your device.</p>
  </div>

  <!-- Saved Drafts -->
  <div class="inv-drafts-bar" id="invDraftsBar" style="display:none;">
    <span class="inv-drafts-label">Saved Drafts:</span>
  </div>

  <div class="inv-layout">

    <!-- Editor Column -->
    <div class="inv-editor-col">

      <!-- Your Business -->
      <div class="inv-card" style="margin-bottom:16px;">
        <div class="inv-card-title">Your Business</div>
        <div class="inv-field">
          <label class="inv-label">Logo</label>
          <div class="inv-logo-zone" id="invLogoZone">
            <span id="invLogoPlaceholder">Click or drag to upload logo</span>
            <img id="invLogoPreview" style="display:none;" alt="Business logo">
            <input type="file" accept="image/*" id="invLogoInput">
          </div>
        </div>
        <div class="inv-field">
          <label class="inv-label">Business Name</label>
          <input type="text" class="inv-input" id="invBizName" placeholder="Your Company Name">
        </div>
        <div class="inv-field">
          <label class="inv-label">Address</label>
          <input type="text" class="inv-input" id="invBizAddress" placeholder="123 Main St, City, State, ZIP">
        </div>
        <div class="inv-row">
          <div class="inv-field">
            <label class="inv-label">Phone</label>
            <input type="text" class="inv-input" id="invBizPhone" placeholder="(555) 123-4567">
          </div>
          <div class="inv-field">
            <label class="inv-label">Email</label>
            <input type="email" class="inv-input" id="invBizEmail" placeholder="you@company.com">
          </div>
        </div>
      </div>

      <!-- Client Info -->
      <div class="inv-card" style="margin-bottom:16px;">
        <div class="inv-card-title">Client Information</div>
        <div class="inv-field">
          <label class="inv-label">Client Name</label>
          <input type="text" class="inv-input" id="invClientName" placeholder="Client or Company Name">
        </div>
        <div class="inv-field">
          <label class="inv-label">Client Address</label>
          <input type="text" class="inv-input" id="invClientAddress" placeholder="456 Oak Ave, City, State, ZIP">
        </div>
        <div class="inv-field">
          <label class="inv-label">Client Email</label>
          <input type="email" class="inv-input" id="invClientEmail" placeholder="client@example.com">
        </div>
      </div>

      <!-- Invoice Details -->
      <div class="inv-card" style="margin-bottom:16px;">
        <div class="inv-card-title">Invoice Details</div>
        <div class="inv-row">
          <div class="inv-field">
            <label class="inv-label">Invoice Number</label>
            <input type="text" class="inv-input mono" id="invNumber" value="INV-0001">
          </div>
          <div class="inv-field">
            <label class="inv-label">Currency</label>
            <select class="inv-select" id="invCurrency">
              <option value="USD">USD ($)</option>
              <option value="EUR">EUR (&euro;)</option>
              <option value="GBP">GBP (&pound;)</option>
              <option value="CAD">CAD (C$)</option>
              <option value="AUD">AUD (A$)</option>
              <option value="JPY">JPY (&yen;)</option>
              <option value="INR">INR (&rupee;)</option>
              <option value="CHF">CHF (Fr)</option>
              <option value="CNY">CNY (&yen;)</option>
              <option value="BRL">BRL (R$)</option>
              <option value="MXN">MXN (Mex$)</option>
              <option value="SEK">SEK (kr)</option>
              <option value="NZD">NZD (NZ$)</option>
              <option value="SGD">SGD (S$)</option>
              <option value="HKD">HKD (HK$)</option>
              <option value="KRW">KRW (&won;)</option>
            </select>
          </div>
        </div>
        <div class="inv-row-3">
          <div class="inv-field">
            <label class="inv-label">Issue Date</label>
            <input type="date" class="inv-input" id="invIssueDate">
          </div>
          <div class="inv-field">
            <label class="inv-label">Due Date</label>
            <input type="date" class="inv-input" id="invDueDate">
          </div>
          <div class="inv-field">
            <label class="inv-label">Payment Terms</label>
            <select class="inv-select" id="invTerms">
              <option value="net30">Net 30</option>
              <option value="net15">Net 15</option>
              <option value="net60">Net 60</option>
              <option value="receipt">Due on Receipt</option>
            </select>
          </div>
        </div>
      </div>

      <!-- Line Items -->
      <div class="inv-card" style="margin-bottom:16px;">
        <div class="inv-card-title">Line Items</div>
        <table class="inv-items-table">
          <thead>
            <tr>
              <th>Description</th>
              <th>Qty</th>
              <th>Price</th>
              <th>Amount</th>
              <th></th>
            </tr>
          </thead>
          <tbody id="invItemsBody">
            <tr>
              <td><input type="text" class="inv-input inv-item-desc" placeholder="Service or product"></td>
              <td><input type="number" class="inv-input mono inv-item-qty" value="1" min="0" step="1"></td>
              <td><input type="number" class="inv-input mono inv-item-price" value="0" min="0" step="0.01"></td>
              <td class="inv-item-amount">0.00</td>
              <td><button type="button" class="inv-remove-btn" onclick="invRemoveRow(this)">&times;</button></td>
            </tr>
          </tbody>
        </table>
        <button type="button" class="inv-add-row-btn" onclick="invAddRow()">+ Add Line Item</button>

        <!-- Summary -->
        <div class="inv-summary">
          <div class="inv-summary-row">
            <span class="inv-summary-label">Subtotal</span>
            <span class="inv-summary-value" id="invSubtotal">0.00</span>
          </div>
          <div class="inv-summary-row">
            <div class="inv-disc-row">
              <span class="inv-summary-label">Discount</span>
              <input type="number" class="inv-input" id="invDiscount" value="0" min="0" step="0.01">
              <select class="inv-select" id="invDiscType">
                <option value="%">%</option>
                <option value="fixed">Fixed</option>
              </select>
            </div>
            <span class="inv-summary-value" id="invDiscAmt">-0.00</span>
          </div>
          <div class="inv-summary-row">
            <div class="inv-disc-row">
              <span class="inv-summary-label">Tax Rate</span>
              <input type="number" class="inv-input" id="invTaxRate" value="0" min="0" step="0.01">
              <span style="color:var(--inv-text-muted);font-size:0.82rem;">%</span>
            </div>
            <span class="inv-summary-value" id="invTaxAmt">0.00</span>
          </div>
          <div class="inv-summary-row total">
            <span class="inv-summary-label">Total</span>
            <span class="inv-summary-value" id="invTotal">0.00</span>
          </div>
        </div>
      </div>

      <!-- Notes -->
      <div class="inv-card" style="margin-bottom:16px;">
        <div class="inv-card-title">Notes / Terms</div>
        <div class="inv-field">
          <textarea class="inv-textarea" id="invNotes" rows="3" placeholder="Payment instructions, late fee policy, thank you note..."></textarea>
        </div>
      </div>

      <!-- Action Buttons -->
      <div class="inv-actions">
        <button type="button" class="inv-btn inv-btn-primary" onclick="invDownloadPDF()">Download PDF</button>
        <button type="button" class="inv-btn inv-btn-outline" onclick="invSaveDraft()">Save Draft</button>
        <button type="button" class="inv-btn inv-btn-danger" onclick="invClearAll()">Clear All</button>
      </div>

    </div>

    <!-- Preview Column -->
    <div class="inv-preview-wrap">
      <div class="inv-preview" id="invPreview">

        <div class="inv-preview-header">
          <div class="inv-preview-logo">
            <img id="invPreviewLogo" style="display:none;" alt="Logo">
            <p class="inv-preview-biz-name" id="invPreviewBizName">Your Business</p>
          </div>
          <div class="inv-preview-title">
            <h2>INVOICE</h2>
            <p id="invPreviewNumber">INV-0001</p>
          </div>
        </div>

        <div class="inv-preview-parties">
          <div>
            <p class="inv-preview-party-label">From</p>
            <p class="inv-preview-party-name" id="invPreviewFromName">Your Business</p>
            <p class="inv-preview-party-detail" id="invPreviewFromAddress"></p>
            <p class="inv-preview-party-detail" id="invPreviewFromContact"></p>
          </div>
          <div>
            <p class="inv-preview-party-label">Bill To</p>
            <p class="inv-preview-party-name" id="invPreviewToName">Client Name</p>
            <p class="inv-preview-party-detail" id="invPreviewToAddress"></p>
            <p class="inv-preview-party-detail" id="invPreviewToEmail"></p>
          </div>
        </div>

        <div class="inv-preview-details">
          <div class="inv-preview-detail-item">
            <p class="inv-preview-detail-label">Issue Date</p>
            <p class="inv-preview-detail-value" id="invPreviewIssue">-</p>
          </div>
          <div class="inv-preview-detail-item">
            <p class="inv-preview-detail-label">Due Date</p>
            <p class="inv-preview-detail-value" id="invPreviewDue">-</p>
          </div>
          <div class="inv-preview-detail-item">
            <p class="inv-preview-detail-label">Payment Terms</p>
            <p class="inv-preview-detail-value" id="invPreviewTerms">Net 30</p>
          </div>
        </div>

        <table class="inv-preview-table">
          <thead>
            <tr>
              <th>Description</th>
              <th>Qty</th>
              <th>Price</th>
              <th>Amount</th>
            </tr>
          </thead>
          <tbody id="invPreviewItems">
            <tr>
              <td>-</td>
              <td>1</td>
              <td>0.00</td>
              <td>0.00</td>
            </tr>
          </tbody>
        </table>

        <div class="inv-preview-summary">
          <div class="inv-preview-summary-inner">
            <div class="inv-preview-sum-row">
              <span>Subtotal</span>
              <span id="invPreviewSubtotal">0.00</span>
            </div>
            <div class="inv-preview-sum-row" id="invPreviewDiscRow" style="display:none;">
              <span>Discount</span>
              <span id="invPreviewDisc">-0.00</span>
            </div>
            <div class="inv-preview-sum-row" id="invPreviewTaxRow" style="display:none;">
              <span>Tax (<span id="invPreviewTaxPct">0</span>%)</span>
              <span id="invPreviewTax">0.00</span>
            </div>
            <div class="inv-preview-sum-total">
              <span>Total</span>
              <span id="invPreviewTotal">0.00</span>
            </div>
          </div>
        </div>

        <div class="inv-preview-notes" id="invPreviewNotesWrap" style="display:none;">
          <p class="inv-preview-notes-label">Notes / Terms</p>
          <p class="inv-preview-notes-text" id="invPreviewNotes"></p>
        </div>

        <div class="inv-preview-footer">Generated with Zovo Invoice Generator</div>

      </div>
    </div>

  </div>

  <div class="inv-updated">Last updated: March 2026</div>

  <!-- Cross Links -->
  <div class="inv-cross-links">
    <a href="/tools/compound-interest-calculator/" class="inv-cross-link">Compound Interest Calculator</a>
    <a href="/tools/percentage-calculator/" class="inv-cross-link">Percentage Calculator</a>
    <a href="/tools/loan-calculator/" class="inv-cross-link">Loan Calculator</a>
  </div>

  <!-- SEO Content -->
  <div class="inv-content">

<h2>What Is an Invoice</h2>

<p>An invoice is a commercial document that a seller issues to a buyer. It records a transaction: what was provided, the agreed price, payment terms, and identifying information for both parties. Unlike a receipt, which confirms that payment has been made, an invoice is a request for payment. It creates a paper trail that both sides can reference if questions arise later.</p>

<p>Invoices serve several overlapping purposes. They act as legal evidence of a sale, provide data for accounting and tax reporting, track accounts receivable, and set expectations around when payment should arrive. For freelancers and small businesses, a well-structured invoice can also convey professionalism. A document that clearly states who owes what, by when, and how to pay reduces back-and-forth and speeds up collections.</p>

<p>The basic concept is simple, but the details matter. An invoice missing a due date or containing an incorrect total can delay payment by weeks. An invoice without a unique number makes it difficult to match against bank deposits. The generator above handles these details automatically, assigning sequential numbers, computing line-item totals, and applying tax and discount calculations so the math is always correct.</p>

<h2>Essential Invoice Elements</h2>

<p>Every professional invoice should contain a set of standard elements. These fields exist because they solve specific problems in the payment process.</p>

<ul>
  <li>Unique invoice number. This is the primary identifier for the transaction. Without it, matching payments to invoices becomes guesswork. Sequential numbering (INV-0001, INV-0002) is the most common approach. Some businesses prefix numbers with the year or client code for easier filtering.</li>
  <li>Issue date. The date the invoice was created. This anchors the payment terms. If terms are Net 30 and the issue date is March 1, payment is expected by March 31.</li>
  <li>Due date. The explicit deadline for payment. Stating this directly removes ambiguity, even when payment terms are also listed.</li>
  <li>Seller and buyer information. Names, addresses, and contact details for both parties. This is necessary for record-keeping, tax compliance, and resolving disputes. For registered businesses, include your tax ID or VAT number where required.</li>
  <li>Line items with quantities and prices. Each product or service should appear as a separate line with its description, quantity, unit price, and total. This level of detail lets the buyer verify what they are being charged for.</li>
  <li>Subtotal, taxes, discounts, and total. The math section. The subtotal is the sum of all line items before adjustments. Tax and discount calculations follow. The total is the final amount due. Showing each step makes the invoice auditable.</li>
  <li>Payment instructions. Bank account details, accepted payment methods, or a payment link. The easier you make it to pay, the faster you get paid.</li>
</ul>

<p>The generator on this page includes all of these fields. It computes line-item amounts, applies discount logic (percentage or fixed), calculates tax on the post-discount subtotal, and renders everything into a clean preview. You can add a logo and notes, select your currency, and download the result as a printable PDF.</p>

<h2>Invoice Payment Terms Explained</h2>

<p>Payment terms define when the buyer should pay and, in some cases, what happens if they pay early or late. The most common terms are expressed as "Net" followed by a number of days.</p>

<p>Net 30 means the full amount is due within 30 calendar days of the invoice date. This is the default in many industries because it gives the buyer enough time to process the invoice through their accounts payable department while keeping the seller's cash flow within a reasonable window. Net 15 shortens that window, and Net 60 extends it. Due on Receipt means payment is expected immediately when the invoice is delivered.</p>

<p>Some businesses offer early payment discounts, written as 2/10 Net 30. This means the buyer can take a 2% discount if they pay within 10 days; otherwise, the full amount is due in 30 days. The economics are compelling: 2% over 20 extra days works out to an annualized rate above 36%, so buyers with available cash often take the discount.</p>

<p>Late payment fees are another common term. A typical clause reads "1.5% per month on overdue balances." Including this on the invoice (in the notes section) provides a contractual basis for charging interest on late payments. Whether you actually enforce it is a business decision, but having it on the invoice gives you the option.</p>

<p>Choose terms that match your industry norms and cash flow needs. Freelancers working with individual clients often use Net 15 or Due on Receipt. Businesses invoicing other businesses typically use Net 30. Large enterprise contracts sometimes extend to Net 60 or Net 90.</p>

<h2>Tips for Professional Invoicing</h2>

<p>Getting paid on time depends partly on how you invoice. A few practical habits reduce payment delays.</p>

<p>Send the invoice promptly. The longer you wait after completing work, the less urgently the client feels about paying. Ideally, send the invoice the same day the work ships or the milestone is reached.</p>

<p>Use clear, specific descriptions in your line items. "Consulting services" is vague. "Website redesign: homepage wireframe and prototype (March 2026)" tells the client exactly what the charge covers. Specificity reduces questions that delay payment.</p>

<p>Always include a due date, not just payment terms. Some people will read "Net 30" and start counting from when they opened the email, not the invoice date. An explicit due date like "Due: April 18, 2026" removes all ambiguity.</p>

<p>Follow up. If the due date passes without payment, send a polite reminder within 2-3 days. Many late payments are simply oversights, and a short email resolves them. Automate this if your volume warrants it.</p>

<p>Save every invoice you issue. The generator on this page stores drafts in your browser's local storage so you can return to previous invoices. For long-term records, download the PDF and store it in your accounting system or file structure.</p>

<p>Match your invoice style to your brand. Including your logo, using consistent colors, and maintaining a clean layout signals that you run a professional operation. The preview panel on this page uses a white background with clean typography specifically because that is what recipients expect from a business document.</p>

  </div>

  <!-- FAQ Section -->
  <div class="inv-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="inv-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is this invoice generator really free?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. There are no hidden fees, no account required, and no watermarks on the generated PDF. The tool runs entirely in your browser using JavaScript. No data is sent to any server. You can use it as many times as you need.</p>
      </div>
    </div>

    <div class="inv-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does the PDF download work?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Clicking "Download PDF" triggers your browser's print dialog with the invoice preview formatted for paper. Select "Save as PDF" as the destination in the print dialog. The print-specific CSS hides the editor interface and presents only the clean invoice document, sized for standard letter or A4 paper.</p>
      </div>
    </div>

    <div class="inv-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I save invoices and come back to them later?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The "Save Draft" button stores the current invoice data in your browser's localStorage. Saved drafts appear as clickable chips at the top of the page. Click any draft to reload it. Note that localStorage is tied to the browser and device you used. Clearing browser data will remove saved drafts, so download PDFs of finalized invoices as a permanent record.</p>
      </div>
    </div>

    <div class="inv-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between an invoice and a receipt?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">An invoice is a request for payment issued before or at the time of a transaction. A receipt is confirmation that payment has been received. The invoice says "you owe this amount." The receipt says "you paid this amount." Both serve as financial records, but they appear at different stages of the payment cycle.</p>
      </div>
    </div>

    <div class="inv-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How are tax and discount calculated?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The calculator first sums all line items to get the subtotal. If a discount is applied, it is subtracted next (either as a flat amount or a percentage of the subtotal). Tax is then calculated on the post-discount amount. The total equals the post-discount subtotal plus tax. This order (discount before tax) is the standard accounting practice in most jurisdictions.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="inv-author-box">
    <div class="inv-author-avatar">ML</div>
    <div class="inv-author-info">
      <p class="inv-author-name">Michael Lip</p>
      <p class="inv-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="inv-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script>
(function() {
  "use strict";

  var CURRENCY_SYMBOLS = {
    USD: "$", EUR: "\u20AC", GBP: "\u00A3", CAD: "C$", AUD: "A$",
    JPY: "\u00A5", INR: "\u20B9", CHF: "Fr", CNY: "\u00A5", BRL: "R$",
    MXN: "Mex$", SEK: "kr", NZD: "NZ$", SGD: "S$", HKD: "HK$", KRW: "\u20A9"
  };

  var TERMS_LABELS = {
    net30: "Net 30", net15: "Net 15", net60: "Net 60", receipt: "Due on Receipt"
  };

  var TERMS_DAYS = { net30: 30, net15: 15, net60: 60, receipt: 0 };

  var elBizName = document.getElementById("invBizName");
  var elBizAddress = document.getElementById("invBizAddress");
  var elBizPhone = document.getElementById("invBizPhone");
  var elBizEmail = document.getElementById("invBizEmail");
  var elClientName = document.getElementById("invClientName");
  var elClientAddress = document.getElementById("invClientAddress");
  var elClientEmail = document.getElementById("invClientEmail");
  var elNumber = document.getElementById("invNumber");
  var elCurrency = document.getElementById("invCurrency");
  var elIssueDate = document.getElementById("invIssueDate");
  var elDueDate = document.getElementById("invDueDate");
  var elTerms = document.getElementById("invTerms");
  var elItemsBody = document.getElementById("invItemsBody");
  var elDiscount = document.getElementById("invDiscount");
  var elDiscType = document.getElementById("invDiscType");
  var elTaxRate = document.getElementById("invTaxRate");
  var elNotes = document.getElementById("invNotes");
  var elLogoInput = document.getElementById("invLogoInput");
  var elLogoPreview = document.getElementById("invLogoPreview");
  var elLogoPlaceholder = document.getElementById("invLogoPlaceholder");

  var logoDataURL = null;
  var nextInvoiceNum = 1;
  var debounceTimer = null;

  // --- Set default dates ---
  var today = new Date();
  var todayStr = today.toISOString().split("T")[0];
  elIssueDate.value = todayStr;
  updateDueDateFromTerms();

  // --- Logo upload ---
  elLogoInput.addEventListener("change", function(e) {
    var file = e.target.files[0];
    if (!file) return;
    var reader = new FileReader();
    reader.onload = function(ev) {
      logoDataURL = ev.target.result;
      elLogoPreview.src = logoDataURL;
      elLogoPreview.style.display = "block";
      elLogoPlaceholder.style.display = "none";
      updatePreview();
    };
    reader.readAsDataURL(file);
  });

  // --- Payment terms -> due date ---
  elTerms.addEventListener("change", function() {
    updateDueDateFromTerms();
    updatePreview();
  });

  elIssueDate.addEventListener("change", function() {
    updateDueDateFromTerms();
    updatePreview();
  });

  function updateDueDateFromTerms() {
    var terms = elTerms.value;
    var days = TERMS_DAYS[terms] || 30;
    var issue = elIssueDate.value ? new Date(elIssueDate.value + "T00:00:00") : new Date();
    var due = new Date(issue);
    due.setDate(due.getDate() + days);
    elDueDate.value = due.toISOString().split("T")[0];
  }

  // --- Line items ---
  window.invAddRow = function() {
    var tr = document.createElement("tr");
    tr.innerHTML = '<td><input type="text" class="inv-input inv-item-desc" placeholder="Service or product"></td>' +
      '<td><input type="number" class="inv-input mono inv-item-qty" value="1" min="0" step="1"></td>' +
      '<td><input type="number" class="inv-input mono inv-item-price" value="0" min="0" step="0.01"></td>' +
      '<td class="inv-item-amount">0.00</td>' +
      '<td><button type="button" class="inv-remove-btn" onclick="invRemoveRow(this)">&times;</button></td>';
    elItemsBody.appendChild(tr);
    attachRowListeners(tr);
    updateCalc();
  };

  window.invRemoveRow = function(btn) {
    var rows = elItemsBody.querySelectorAll("tr");
    if (rows.length <= 1) return;
    btn.closest("tr").remove();
    updateCalc();
  };

  function attachRowListeners(tr) {
    var inputs = tr.querySelectorAll("input");
    for (var i = 0; i < inputs.length; i++) {
      inputs[i].addEventListener("input", debouncedCalc);
    }
  }

  // Attach to initial row
  var initialRows = elItemsBody.querySelectorAll("tr");
  for (var r = 0; r < initialRows.length; r++) {
    attachRowListeners(initialRows[r]);
  }

  // --- Calculations ---
  function getItems() {
    var rows = elItemsBody.querySelectorAll("tr");
    var items = [];
    for (var i = 0; i < rows.length; i++) {
      var desc = rows[i].querySelector(".inv-item-desc").value;
      var qty = parseFloat(rows[i].querySelector(".inv-item-qty").value) || 0;
      var price = parseFloat(rows[i].querySelector(".inv-item-price").value) || 0;
      var amount = qty * price;
      items.push({ desc: desc, qty: qty, price: price, amount: amount });
      rows[i].querySelector(".inv-item-amount").textContent = formatNum(amount);
    }
    return items;
  }

  function getCurrencySymbol() {
    return CURRENCY_SYMBOLS[elCurrency.value] || "$";
  }

  function formatNum(n) {
    if (elCurrency.value === "JPY" || elCurrency.value === "KRW") {
      return Math.round(n).toLocaleString("en-US");
    }
    return n.toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ",");
  }

  function formatCurr(n) {
    return getCurrencySymbol() + formatNum(n);
  }

  function updateCalc() {
    var items = getItems();
    var subtotal = 0;
    for (var i = 0; i < items.length; i++) {
      subtotal += items[i].amount;
    }

    var discVal = parseFloat(elDiscount.value) || 0;
    var discType = elDiscType.value;
    var discAmt = discType === "%" ? subtotal * (discVal / 100) : discVal;
    if (discAmt > subtotal) discAmt = subtotal;

    var afterDisc = subtotal - discAmt;

    var taxRate = parseFloat(elTaxRate.value) || 0;
    var taxAmt = afterDisc * (taxRate / 100);

    var total = afterDisc + taxAmt;

    document.getElementById("invSubtotal").textContent = formatCurr(subtotal);
    document.getElementById("invDiscAmt").textContent = "-" + formatCurr(discAmt);
    document.getElementById("invTaxAmt").textContent = formatCurr(taxAmt);
    document.getElementById("invTotal").textContent = formatCurr(total);

    updatePreview(items, subtotal, discAmt, taxRate, taxAmt, total);
  }

  function debouncedCalc() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(updateCalc, 120);
  }

  // --- Preview ---
  function updatePreview(items, subtotal, discAmt, taxRate, taxAmt, total) {
    if (!items) {
      items = getItems();
      subtotal = 0;
      for (var j = 0; j < items.length; j++) subtotal += items[j].amount;
      var dv = parseFloat(elDiscount.value) || 0;
      var dt = elDiscType.value;
      discAmt = dt === "%" ? subtotal * (dv / 100) : dv;
      if (discAmt > subtotal) discAmt = subtotal;
      var ad = subtotal - discAmt;
      taxRate = parseFloat(elTaxRate.value) || 0;
      taxAmt = ad * (taxRate / 100);
      total = ad + taxAmt;
    }

    // Logo
    var previewLogo = document.getElementById("invPreviewLogo");
    var previewBizName = document.getElementById("invPreviewBizName");
    if (logoDataURL) {
      previewLogo.src = logoDataURL;
      previewLogo.style.display = "block";
      previewBizName.style.display = elBizName.value ? "block" : "none";
    } else {
      previewLogo.style.display = "none";
      previewBizName.style.display = "block";
    }

    previewBizName.textContent = elBizName.value || "Your Business";
    document.getElementById("invPreviewNumber").textContent = elNumber.value || "-";

    document.getElementById("invPreviewFromName").textContent = elBizName.value || "Your Business";
    document.getElementById("invPreviewFromAddress").textContent = elBizAddress.value || "";
    var contact = [];
    if (elBizPhone.value) contact.push(elBizPhone.value);
    if (elBizEmail.value) contact.push(elBizEmail.value);
    document.getElementById("invPreviewFromContact").textContent = contact.join(" | ");

    document.getElementById("invPreviewToName").textContent = elClientName.value || "Client Name";
    document.getElementById("invPreviewToAddress").textContent = elClientAddress.value || "";
    document.getElementById("invPreviewToEmail").textContent = elClientEmail.value || "";

    document.getElementById("invPreviewIssue").textContent = formatDate(elIssueDate.value);
    document.getElementById("invPreviewDue").textContent = formatDate(elDueDate.value);
    document.getElementById("invPreviewTerms").textContent = TERMS_LABELS[elTerms.value] || "Net 30";

    // Items table
    var tbody = document.getElementById("invPreviewItems");
    tbody.innerHTML = "";
    for (var i = 0; i < items.length; i++) {
      var tr = document.createElement("tr");
      tr.innerHTML = "<td>" + escapeHtml(items[i].desc || "-") + "</td>" +
        "<td>" + items[i].qty + "</td>" +
        "<td>" + formatCurr(items[i].price) + "</td>" +
        "<td>" + formatCurr(items[i].amount) + "</td>";
      tbody.appendChild(tr);
    }

    // Summary
    document.getElementById("invPreviewSubtotal").textContent = formatCurr(subtotal);

    var discRow = document.getElementById("invPreviewDiscRow");
    if (discAmt > 0) {
      discRow.style.display = "flex";
      document.getElementById("invPreviewDisc").textContent = "-" + formatCurr(discAmt);
    } else {
      discRow.style.display = "none";
    }

    var taxRow = document.getElementById("invPreviewTaxRow");
    if (taxRate > 0) {
      taxRow.style.display = "flex";
      document.getElementById("invPreviewTaxPct").textContent = taxRate;
      document.getElementById("invPreviewTax").textContent = formatCurr(taxAmt);
    } else {
      taxRow.style.display = "none";
    }

    document.getElementById("invPreviewTotal").textContent = formatCurr(total);

    // Notes
    var notesWrap = document.getElementById("invPreviewNotesWrap");
    if (elNotes.value.trim()) {
      notesWrap.style.display = "block";
      document.getElementById("invPreviewNotes").textContent = elNotes.value;
    } else {
      notesWrap.style.display = "none";
    }
  }

  function formatDate(dateStr) {
    if (!dateStr) return "-";
    var parts = dateStr.split("-");
    var months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];
    return months[parseInt(parts[1], 10) - 1] + " " + parseInt(parts[2], 10) + ", " + parts[0];
  }

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.appendChild(document.createTextNode(str));
    return div.innerHTML;
  }

  // --- PDF Download ---
  window.invDownloadPDF = function() {
    window.print();
  };

  // --- Save Draft ---
  window.invSaveDraft = function() {
    var data = gatherData();
    var drafts = JSON.parse(localStorage.getItem("invDrafts") || "[]");
    var draftName = data.number || ("Draft " + (drafts.length + 1));
    data._draftName = draftName;
    data._savedAt = new Date().toISOString();

    // Check if draft with same number exists, update it
    var found = false;
    for (var i = 0; i < drafts.length; i++) {
      if (drafts[i].number === data.number) {
        drafts[i] = data;
        found = true;
        break;
      }
    }
    if (!found) drafts.push(data);

    localStorage.setItem("invDrafts", JSON.stringify(drafts));
    renderDrafts();

    // Auto-increment invoice number for next invoice
    var numMatch = data.number.match(/(\d+)$/);
    if (numMatch) {
      var nextNum = parseInt(numMatch[1], 10) + 1;
      var prefix = data.number.replace(/\d+$/, "");
      var padded = String(nextNum).padStart(numMatch[1].length, "0");
      elNumber.value = prefix + padded;
      updatePreview();
    }
  };

  function gatherData() {
    var items = [];
    var rows = elItemsBody.querySelectorAll("tr");
    for (var i = 0; i < rows.length; i++) {
      items.push({
        desc: rows[i].querySelector(".inv-item-desc").value,
        qty: rows[i].querySelector(".inv-item-qty").value,
        price: rows[i].querySelector(".inv-item-price").value
      });
    }
    return {
      bizName: elBizName.value,
      bizAddress: elBizAddress.value,
      bizPhone: elBizPhone.value,
      bizEmail: elBizEmail.value,
      clientName: elClientName.value,
      clientAddress: elClientAddress.value,
      clientEmail: elClientEmail.value,
      number: elNumber.value,
      currency: elCurrency.value,
      issueDate: elIssueDate.value,
      dueDate: elDueDate.value,
      terms: elTerms.value,
      items: items,
      discount: elDiscount.value,
      discType: elDiscType.value,
      taxRate: elTaxRate.value,
      notes: elNotes.value,
      logo: logoDataURL
    };
  }

  function loadData(data) {
    elBizName.value = data.bizName || "";
    elBizAddress.value = data.bizAddress || "";
    elBizPhone.value = data.bizPhone || "";
    elBizEmail.value = data.bizEmail || "";
    elClientName.value = data.clientName || "";
    elClientAddress.value = data.clientAddress || "";
    elClientEmail.value = data.clientEmail || "";
    elNumber.value = data.number || "INV-0001";
    elCurrency.value = data.currency || "USD";
    elIssueDate.value = data.issueDate || "";
    elDueDate.value = data.dueDate || "";
    elTerms.value = data.terms || "net30";
    elDiscount.value = data.discount || "0";
    elDiscType.value = data.discType || "%";
    elTaxRate.value = data.taxRate || "0";
    elNotes.value = data.notes || "";

    if (data.logo) {
      logoDataURL = data.logo;
      elLogoPreview.src = logoDataURL;
      elLogoPreview.style.display = "block";
      elLogoPlaceholder.style.display = "none";
    } else {
      logoDataURL = null;
      elLogoPreview.style.display = "none";
      elLogoPlaceholder.style.display = "block";
    }

    // Rebuild items
    elItemsBody.innerHTML = "";
    var items = data.items || [{ desc: "", qty: "1", price: "0" }];
    for (var i = 0; i < items.length; i++) {
      var tr = document.createElement("tr");
      tr.innerHTML = '<td><input type="text" class="inv-input inv-item-desc" placeholder="Service or product" value="' + escapeAttr(items[i].desc) + '"></td>' +
        '<td><input type="number" class="inv-input mono inv-item-qty" value="' + (items[i].qty || 1) + '" min="0" step="1"></td>' +
        '<td><input type="number" class="inv-input mono inv-item-price" value="' + (items[i].price || 0) + '" min="0" step="0.01"></td>' +
        '<td class="inv-item-amount">0.00</td>' +
        '<td><button type="button" class="inv-remove-btn" onclick="invRemoveRow(this)">&times;</button></td>';
      elItemsBody.appendChild(tr);
      attachRowListeners(tr);
    }

    updateCalc();
  }

  function escapeAttr(str) {
    return (str || "").replace(/&/g, "&amp;").replace(/"/g, "&quot;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  // --- Render Drafts ---
  function renderDrafts() {
    var bar = document.getElementById("invDraftsBar");
    var drafts = JSON.parse(localStorage.getItem("invDrafts") || "[]");
    if (drafts.length === 0) {
      bar.style.display = "none";
      return;
    }
    bar.style.display = "flex";
    // Clear old chips (keep label)
    while (bar.children.length > 1) {
      bar.removeChild(bar.lastChild);
    }
    for (var i = 0; i < drafts.length; i++) {
      var chip = document.createElement("span");
      chip.className = "inv-draft-chip";
      chip.setAttribute("data-idx", i);
      chip.innerHTML = escapeHtml(drafts[i]._draftName || ("Draft " + (i + 1))) +
        ' <span class="inv-draft-del" data-delidx="' + i + '">&times;</span>';
      chip.addEventListener("click", (function(idx) {
        return function(e) {
          if (e.target.classList.contains("inv-draft-del")) return;
          var d = JSON.parse(localStorage.getItem("invDrafts") || "[]");
          if (d[idx]) loadData(d[idx]);
        };
      })(i));
      var del = chip.querySelector(".inv-draft-del");
      del.addEventListener("click", (function(idx) {
        return function(e) {
          e.stopPropagation();
          var d = JSON.parse(localStorage.getItem("invDrafts") || "[]");
          d.splice(idx, 1);
          localStorage.setItem("invDrafts", JSON.stringify(d));
          renderDrafts();
        };
      })(i));
      bar.appendChild(chip);
    }
  }

  // --- Clear All ---
  window.invClearAll = function() {
    elBizName.value = "";
    elBizAddress.value = "";
    elBizPhone.value = "";
    elBizEmail.value = "";
    elClientName.value = "";
    elClientAddress.value = "";
    elClientEmail.value = "";
    elNumber.value = "INV-0001";
    elCurrency.value = "USD";
    elIssueDate.value = todayStr;
    elTerms.value = "net30";
    updateDueDateFromTerms();
    elDiscount.value = "0";
    elDiscType.value = "%";
    elTaxRate.value = "0";
    elNotes.value = "";
    logoDataURL = null;
    elLogoPreview.style.display = "none";
    elLogoPlaceholder.style.display = "block";

    elItemsBody.innerHTML = "";
    var tr = document.createElement("tr");
    tr.innerHTML = '<td><input type="text" class="inv-input inv-item-desc" placeholder="Service or product"></td>' +
      '<td><input type="number" class="inv-input mono inv-item-qty" value="1" min="0" step="1"></td>' +
      '<td><input type="number" class="inv-input mono inv-item-price" value="0" min="0" step="0.01"></td>' +
      '<td class="inv-item-amount">0.00</td>' +
      '<td><button type="button" class="inv-remove-btn" onclick="invRemoveRow(this)">&times;</button></td>';
    elItemsBody.appendChild(tr);
    attachRowListeners(tr);

    updateCalc();
  };

  // --- Listen to all editor inputs ---
  var allInputs = document.querySelectorAll(".inv-editor-col .inv-input, .inv-editor-col .inv-select, .inv-editor-col .inv-textarea");
  for (var i = 0; i < allInputs.length; i++) {
    allInputs[i].addEventListener("input", debouncedCalc);
    allInputs[i].addEventListener("change", debouncedCalc);
  }

  // --- Init ---
  renderDrafts();
  updateCalc();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Invoice Generator",
      "description": "Create and download professional invoices for free. Add your logo, line items, taxes, and discounts. Generate PDF-ready invoices with automatic calculations.",
      "url": "https://theluckystrike.github.io/tools/invoice-generator/",
      "applicationCategory": "BusinessApplication",
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
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/"},
        {"@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/"},
        {"@type": "ListItem", "position": 3, "name": "Invoice Generator", "item": "https://theluckystrike.github.io/tools/invoice-generator/"}
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://theluckystrike.github.io/assets/images/zovo-logo.png"
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Is this invoice generator really free?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. There are no hidden fees, no account required, and no watermarks on the generated PDF. The tool runs entirely in your browser using JavaScript. No data is sent to any server."
          }
        },
        {
          "@type": "Question",
          "name": "How does the PDF download work?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Clicking Download PDF triggers your browser's print dialog with the invoice preview formatted for paper. Select Save as PDF as the destination in the print dialog."
          }
        },
        {
          "@type": "Question",
          "name": "Can I save invoices and come back to them later?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. The Save Draft button stores the current invoice data in your browser's localStorage. Saved drafts appear as clickable chips at the top of the page."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between an invoice and a receipt?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "An invoice is a request for payment issued before or at the time of a transaction. A receipt is confirmation that payment has been received."
          }
        },
        {
          "@type": "Question",
          "name": "How are tax and discount calculated?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The calculator first sums all line items to get the subtotal. Discount is subtracted next. Tax is then calculated on the post-discount amount. The total equals the post-discount subtotal plus tax."
          }
        }
      ]
    }
  ]
}
</script>
