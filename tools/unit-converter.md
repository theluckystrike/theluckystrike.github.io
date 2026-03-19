---
layout: page
title: "Free Unit Converter — Length, Weight, Temperature, Speed & Volume | Zovo"
description: "Convert between units of length, weight, temperature, speed, volume, area, time, digital storage, and energy. Free online unit converter with instant results and conversion tables."
permalink: /tools/unit-converter/
keywords: "unit converter, convert units, length converter, weight converter, temperature converter, km to miles, kg to lbs, celsius to fahrenheit, unit conversion calculator"
date: 2026-03-19
categories: [tools]
tags: [unit-converter, measurement, length, weight, temperature, speed, volume, conversion]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --uc-primary: #6C5CE7;
    --uc-primary-dark: #5A4BD1;
    --uc-primary-light: #A29BFE;
    --uc-bg: #0a0a0f;
    --uc-surface: #12121a;
    --uc-surface-alt: #181824;
    --uc-border: #1e1e2e;
    --uc-text: #e0e0e0;
    --uc-text-muted: #8888aa;
    --uc-green: #00ff88;
    --uc-green-dark: #00cc6a;
    --uc-red: #ff4466;
    --uc-radius: 12px;
    --uc-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .uc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--uc-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .uc-wrapper * {
    box-sizing: border-box;
  }

  .uc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .uc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--uc-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .uc-hero h1 span {
    color: var(--uc-primary);
  }

  .uc-intro {
    font-size: 1.05rem;
    color: var(--uc-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .uc-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--uc-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--uc-border);
    border-radius: 20px;
  }

  /* Category Tabs */
  .uc-tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 24px;
    justify-content: center;
  }

  .uc-tab {
    padding: 8px 16px;
    background: var(--uc-surface);
    border: 1px solid var(--uc-border);
    border-radius: 8px;
    color: var(--uc-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    cursor: pointer;
    transition: border-color 0.2s ease, color 0.2s ease, background 0.2s ease;
    user-select: none;
  }

  .uc-tab:hover {
    border-color: var(--uc-primary);
    color: var(--uc-text);
  }

  .uc-tab.active {
    background: var(--uc-primary);
    border-color: var(--uc-primary);
    color: #fff;
  }

  /* Converter Card */
  .uc-card {
    background: var(--uc-surface);
    border: 1px solid var(--uc-border);
    border-radius: var(--uc-radius);
    padding: 24px;
    box-shadow: var(--uc-shadow);
    margin-bottom: 24px;
  }

  .uc-converter-row {
    display: flex;
    align-items: flex-end;
    gap: 12px;
  }

  .uc-field {
    flex: 1;
  }

  .uc-label {
    display: block;
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--uc-text-muted);
    margin-bottom: 6px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .uc-select {
    width: 100%;
    padding: 9px 12px;
    background: var(--uc-bg);
    border: 1px solid var(--uc-border);
    border-radius: 8px;
    color: var(--uc-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    outline: none;
    cursor: pointer;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    appearance: none;
    -webkit-appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%238888aa' d='M6 8.5L1 3.5h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    padding-right: 32px;
  }

  .uc-select:focus {
    border-color: var(--uc-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .uc-input {
    width: 100%;
    padding: 9px 12px;
    background: var(--uc-bg);
    border: 1px solid var(--uc-border);
    border-radius: 8px;
    color: var(--uc-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
    -moz-appearance: textfield;
  }

  .uc-input::-webkit-outer-spin-button,
  .uc-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  .uc-input:focus {
    border-color: var(--uc-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .uc-input-group {
    margin-top: 12px;
  }

  .uc-swap-col {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-bottom: 2px;
  }

  .uc-swap-btn {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: var(--uc-surface-alt);
    border: 1px solid var(--uc-border);
    color: var(--uc-text-muted);
    font-size: 1.1rem;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background 0.2s ease, border-color 0.2s ease, color 0.2s ease, transform 0.2s ease;
    flex-shrink: 0;
  }

  .uc-swap-btn:hover {
    background: var(--uc-primary);
    border-color: var(--uc-primary);
    color: #fff;
    transform: rotate(180deg);
  }

  /* Formula Display */
  .uc-formula {
    margin-top: 16px;
    padding: 12px 16px;
    background: var(--uc-surface-alt);
    border: 1px solid var(--uc-border);
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--uc-primary-light);
    overflow-x: auto;
  }

  .uc-formula-label {
    font-family: 'Inter', sans-serif;
    font-size: 0.75rem;
    font-weight: 500;
    color: var(--uc-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 4px;
  }

  /* Quick Convert Buttons */
  .uc-quick-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 16px;
  }

  .uc-quick-btn {
    padding: 6px 14px;
    background: var(--uc-surface-alt);
    border: 1px solid var(--uc-border);
    border-radius: 6px;
    color: var(--uc-text-muted);
    font-size: 0.78rem;
    font-weight: 500;
    cursor: pointer;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .uc-quick-btn:hover {
    border-color: var(--uc-primary);
    color: var(--uc-text);
  }

  .uc-quick-btn.active {
    border-color: var(--uc-primary);
    color: var(--uc-primary-light);
    background: rgba(108, 92, 231, 0.1);
  }

  /* Reference Table */
  .uc-ref-table {
    margin-top: 24px;
  }

  .uc-ref-title {
    font-size: 0.8rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--uc-text-muted);
    margin: 0 0 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .uc-ref-title::before {
    content: '';
    display: inline-block;
    width: 3px;
    height: 14px;
    background: var(--uc-primary);
    border-radius: 2px;
  }

  .uc-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.85rem;
  }

  .uc-table th {
    text-align: left;
    padding: 10px 14px;
    background: var(--uc-surface-alt);
    border-bottom: 1px solid var(--uc-border);
    color: var(--uc-text-muted);
    font-weight: 600;
    font-size: 0.78rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .uc-table td {
    padding: 9px 14px;
    border-bottom: 1px solid var(--uc-border);
    color: var(--uc-text);
  }

  .uc-table td:last-child {
    font-family: 'JetBrains Mono', monospace;
    color: var(--uc-green);
    font-size: 0.84rem;
  }

  .uc-table tr:last-child td {
    border-bottom: none;
  }

  .uc-table-wrap {
    background: var(--uc-surface);
    border: 1px solid var(--uc-border);
    border-radius: var(--uc-radius);
    overflow: hidden;
  }

  /* Cross Links */
  .uc-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .uc-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--uc-surface);
    border: 1px solid var(--uc-border);
    border-radius: 8px;
    color: var(--uc-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .uc-cross-link:hover {
    border-color: var(--uc-primary);
    color: var(--uc-text);
  }

  /* Content */
  .uc-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .uc-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 2.5rem 0 1rem;
    color: var(--uc-text);
  }

  .uc-content p {
    font-size: 0.95rem;
    color: var(--uc-text-muted);
    line-height: 1.8;
    margin: 0 0 1rem;
  }

  .uc-content ul, .uc-content ol {
    color: var(--uc-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 1.5rem;
    margin: 0 0 1rem;
  }

  .uc-content li {
    margin-bottom: 0.4rem;
  }

  .uc-formula-block {
    background: var(--uc-surface);
    border: 1px solid var(--uc-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin: 1rem 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--uc-primary-light);
    overflow-x: auto;
  }

  /* Author Box */
  .uc-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--uc-surface);
    border: 1px solid var(--uc-border);
    border-radius: var(--uc-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .uc-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--uc-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .uc-author-info {
    flex: 1;
  }

  .uc-author-name {
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--uc-text);
    margin: 0 0 4px;
  }

  .uc-author-bio {
    font-size: 0.82rem;
    color: var(--uc-text-muted);
    line-height: 1.6;
    margin: 0;
  }

  /* FAQ */
  .uc-faq {
    max-width: 780px;
    margin: 2.5rem auto 0;
  }

  .uc-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 1.2rem;
    color: var(--uc-text);
  }

  .uc-faq-item {
    padding: 16px 0;
    border-bottom: 1px solid var(--uc-border);
  }

  .uc-faq-item:last-child {
    border-bottom: none;
  }

  .uc-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--uc-text);
  }

  .uc-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--uc-text-muted);
    line-height: 1.7;
  }

  /* Footer */
  .uc-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--uc-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--uc-border);
    margin-top: 3rem;
  }

  .uc-footer a {
    color: var(--uc-primary);
    text-decoration: none;
  }

  .uc-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .uc-hero h1 {
      font-size: 1.6rem;
    }

    .uc-converter-row {
      flex-direction: column;
      align-items: stretch;
    }

    .uc-swap-col {
      padding: 4px 0;
    }

    .uc-swap-btn {
      transform: rotate(90deg);
    }

    .uc-swap-btn:hover {
      transform: rotate(270deg);
    }

    .uc-tabs {
      gap: 4px;
    }

    .uc-tab {
      padding: 6px 10px;
      font-size: 0.75rem;
    }

    .uc-author-box {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
  }
</style>

<div class="uc-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Unit Converter">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="uc-hero">
    <h1><span>Unit</span> Converter</h1>
    <p class="uc-intro">Convert between units of length, weight, temperature, speed, volume, area, time, digital storage, and energy. All calculations run in your browser. Nothing is sent to a server.</p>
    <div class="uc-updated">Last updated: March 19, 2026</div>
  </div>

  <!-- Category Tabs -->
  <div class="uc-tabs" id="ucTabs">
    <button class="uc-tab active" data-cat="length">Length</button>
    <button class="uc-tab" data-cat="weight">Weight / Mass</button>
    <button class="uc-tab" data-cat="temperature">Temperature</button>
    <button class="uc-tab" data-cat="speed">Speed</button>
    <button class="uc-tab" data-cat="volume">Volume</button>
    <button class="uc-tab" data-cat="area">Area</button>
    <button class="uc-tab" data-cat="time">Time</button>
    <button class="uc-tab" data-cat="digital">Digital Storage</button>
    <button class="uc-tab" data-cat="energy">Energy</button>
  </div>

  <!-- Converter Card -->
  <div class="uc-card">
    <div class="uc-converter-row">
      <div class="uc-field">
        <label class="uc-label" for="ucFromUnit">From</label>
        <select class="uc-select" id="ucFromUnit"></select>
        <div class="uc-input-group">
          <input type="number" id="ucFromVal" class="uc-input" value="1" step="any">
        </div>
      </div>

      <div class="uc-swap-col">
        <button class="uc-swap-btn" id="ucSwapBtn" title="Swap units" aria-label="Swap units">&#8596;</button>
      </div>

      <div class="uc-field">
        <label class="uc-label" for="ucToUnit">To</label>
        <select class="uc-select" id="ucToUnit"></select>
        <div class="uc-input-group">
          <input type="number" id="ucToVal" class="uc-input" step="any" value="">
        </div>
      </div>
    </div>

    <!-- Formula -->
    <div class="uc-formula" id="ucFormula">
      <div class="uc-formula-label">Formula</div>
      <div id="ucFormulaText"></div>
    </div>

    <!-- Quick Convert Buttons -->
    <div class="uc-quick-row" id="ucQuickBtns"></div>
  </div>

  <!-- Reference Table -->
  <div class="uc-ref-table" id="ucRefSection">
    <div class="uc-ref-title">Common Conversions</div>
    <div class="uc-table-wrap">
      <table class="uc-table">
        <thead>
          <tr>
            <th>From</th>
            <th>To</th>
            <th>Result</th>
          </tr>
        </thead>
        <tbody id="ucRefBody"></tbody>
      </table>
    </div>
  </div>

  <!-- Cross Links -->
  <div class="uc-cross-links" style="margin-top:32px;">
    <a href="/tools/percentage-calculator/" class="uc-cross-link">Percentage Calculator</a>
    <a href="/tools/compound-interest-calculator/" class="uc-cross-link">Compound Interest Calculator</a>
    <a href="/tools/unix-timestamp-converter/" class="uc-cross-link">Unix Timestamp Converter</a>
  </div>

  <!-- SEO Content -->
  <div class="uc-content">

<h2>What Is Unit Conversion</h2>

<p>Unit conversion is the process of expressing the same physical quantity using a different measurement unit. A distance of 1 kilometer is exactly the same distance as 1,000 meters or approximately 0.621 miles. The physical reality does not change; only the number and its label change. Every unit conversion relies on a known ratio between two units, called a conversion factor.</p>

<p>Conversion factors are either exact or approximate. The relationship between meters and kilometers is exact by definition: 1 km = 1,000 m. The relationship between miles and kilometers is also exact by modern definition: 1 international mile = 1.609344 km. Temperature conversions, on the other hand, involve both multiplication and addition because the scales have different zero points and different step sizes. The converter above handles all of these cases, including the offset math for temperature.</p>

<p>When converting manually, you multiply by a fraction that equals one. To convert 5 miles to kilometers, multiply 5 by (1.609344 km / 1 mile). The "miles" cancel, leaving kilometers. This dimensional analysis approach works for any unit conversion and prevents the most common mistake: multiplying when you should divide, or the reverse.</p>

<h2>The Metric System vs Imperial</h2>

<p>The metric system (SI) organizes units around powers of ten. A kilometer is 1,000 meters. A kilogram is 1,000 grams. A milliliter is one-thousandth of a liter. Prefixes like kilo-, centi-, milli-, and micro- apply uniformly across all measurement types, making conversions within the metric system straightforward arithmetic: move the decimal point.</p>

<p>The imperial and US customary systems evolved from older English measurement traditions. They rely on relationships that vary by measurement type: 12 inches per foot, 3 feet per yard, 5,280 feet per mile, 16 ounces per pound, 2,000 pounds per US ton. These ratios are not based on any single organizing principle, which makes mental conversion harder.</p>

<p>Most countries use the metric system for scientific, commercial, and everyday purposes. The United States, Liberia, and Myanmar are the three countries that have not officially adopted metric as their primary system, though the US uses metric in science, medicine, and military contexts. The United Kingdom uses a mix: speed limits in miles per hour, distances in miles on road signs, but liters at the fuel pump and kilograms in medical settings.</p>

<p>Cross-system conversion is where most people need a tool. Converting 72 kilograms to pounds, or 350 degrees Fahrenheit to Celsius, requires memorizing or looking up a conversion factor. This converter stores all the factors so you do not need to.</p>

<h2>How Temperature Conversion Works</h2>

<p>Temperature conversions are different from every other type in this tool because the scales do not share a common zero point. Length, weight, volume, and all other categories use proportional scales where zero means "none." Temperature scales have arbitrary zero points, so converting between them requires both multiplication and addition.</p>

<p>The Celsius scale sets 0 at the freezing point of water and 100 at its boiling point (at standard atmospheric pressure). The Fahrenheit scale sets 32 at the freezing point and 212 at the boiling point. Kelvin uses the same step size as Celsius but starts at absolute zero, the lowest theoretically possible temperature: 0 K = -273.15 C.</p>

<div class="uc-formula-block">
Fahrenheit = (Celsius x 9/5) + 32
Celsius = (Fahrenheit - 32) x 5/9
Kelvin = Celsius + 273.15
</div>

<p>The 9/5 factor accounts for the different step sizes: a one-degree step in Celsius equals a 1.8-degree step in Fahrenheit. The +32 offset accounts for the different zero points. These two adjustments are why you cannot simply multiply by a single conversion factor the way you can with kilometers and miles.</p>

<p>A useful reference: -40 is the same in both Fahrenheit and Celsius. Room temperature is about 20-22 C or 68-72 F. Normal body temperature is 37 C or 98.6 F. Water boils at 100 C or 212 F.</p>

<h2>Digital Storage Units Explained</h2>

<p>Digital storage units follow a hierarchy based on the bit, the smallest unit of information. A bit stores a single binary value: 0 or 1. Eight bits make one byte. From there, the standard SI prefixes apply: 1 kilobyte (KB) = 1,000 bytes, 1 megabyte (MB) = 1,000 KB, 1 gigabyte (GB) = 1,000 MB, 1 terabyte (TB) = 1,000 GB, 1 petabyte (PB) = 1,000 TB.</p>

<p>There is a historical complication. Early computer scientists used powers of 2 (1,024) instead of powers of 10 (1,000) for these prefixes because binary arithmetic made 1,024 a natural grouping. This means that in some contexts, 1 KB = 1,024 bytes, while in others, 1 KB = 1,000 bytes. The IEC introduced unambiguous binary prefixes (kibibyte, mebibyte, gibibyte) to resolve this, but they have not been widely adopted outside technical standards documents.</p>

<p>This converter uses SI (base-1000) prefixes, which is the standard used by storage manufacturers, networking equipment, and the SI system itself. If your operating system reports a 500 GB drive as 465 GB, it is using binary (base-1024) interpretation of the same prefix.</p>

<p>Data transfer speeds are measured in bits per second, not bytes. A 100 Mbit/s internet connection transfers 100 megabits per second, which equals 12.5 megabytes per second (divide by 8). This distinction between bits and bytes is a frequent source of confusion when comparing advertised speeds to actual download rates.</p>

<h2>Common Conversion Mistakes</h2>

<p>The most frequent conversion error is multiplying when you should divide, or vice versa. If 1 mile equals 1.609 km, then converting miles to kilometers requires multiplication, but converting kilometers to miles requires division. A quick sanity check: if the target unit is smaller (like converting meters to centimeters), the number should get larger. If the target unit is larger (centimeters to meters), the number should get smaller.</p>

<p>With temperature, people sometimes apply the formula in the wrong order. The Fahrenheit-to-Celsius conversion requires subtracting 32 first, then multiplying by 5/9. Reversing that order gives the wrong answer. Similarly, the Celsius-to-Fahrenheit conversion multiplies by 9/5 first, then adds 32.</p>

<p>Confusing US and UK measurements is another trap. A US gallon is 3.785 liters, while a UK (imperial) gallon is 4.546 liters. A US ton (short ton) is 2,000 pounds, while a metric ton (tonne) is 2,204.6 pounds. A stone is 14 pounds, used primarily in the UK and Ireland for body weight. This converter labels each unit clearly to prevent mix-ups.</p>

<p>Precision matters in scientific and engineering contexts. The converter displays up to six significant figures, which is sufficient for most practical purposes. For applications requiring higher precision (geodetic surveying, pharmaceutical dosing, aerospace engineering), consult the primary standards documents from NIST or BIPM.</p>

  </div>

  <!-- FAQ Section -->
  <div class="uc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="uc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I convert kilometers to miles?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Multiply the number of kilometers by 0.621371 to get miles. For example, 10 km x 0.621371 = 6.21 miles. For a rough estimate, multiply by 0.6. The converter above handles this automatically: select Length, set "From" to Kilometers and "To" to Miles, and type your value.</p>
      </div>
    </div>

    <div class="uc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the formula for Celsius to Fahrenheit?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Multiply the Celsius temperature by 9/5 (or 1.8), then add 32. The formula is F = (C x 9/5) + 32. For example, 25 C = (25 x 1.8) + 32 = 77 F. To go the other direction, subtract 32 first, then multiply by 5/9.</p>
      </div>
    </div>

    <div class="uc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why does my hard drive show less space than advertised?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Storage manufacturers use SI prefixes where 1 GB = 1,000,000,000 bytes. Operating systems like Windows use binary interpretation where 1 GB = 1,073,741,824 bytes. A drive advertised as 500 GB (500 billion bytes) shows as roughly 465 GB in Windows because 500,000,000,000 / 1,073,741,824 = 465.66.</p>
      </div>
    </div>

    <div class="uc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between a US gallon and a UK gallon?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A US gallon equals 3.785 liters, while a UK (imperial) gallon equals 4.546 liters. The UK gallon is about 20% larger. This difference also cascades to quarts and pints: a UK pint is 568 mL versus the US pint of 473 mL. When reading fuel economy figures, always check which gallon is being used.</p>
      </div>
    </div>

    <div class="uc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How many bytes are in a megabyte?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Using the SI (base-1000) standard, 1 megabyte (MB) = 1,000,000 bytes. Using the binary (base-1024) standard, 1 mebibyte (MiB) = 1,048,576 bytes. This converter uses SI prefixes. Network speeds, storage manufacturers, and the International System of Units all use base-1000.</p>
      </div>
    </div>

    <div class="uc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my data safe when using this converter?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All conversions run entirely in your web browser using JavaScript. No data is transmitted to any server, no information is stored, and no cookies are set. You can verify this by opening your browser's developer tools and monitoring the Network tab while using the converter.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="uc-author-box">
    <div class="uc-author-avatar">ML</div>
    <div class="uc-author-info">
      <p class="uc-author-name">Michael Lip</p>
      <p class="uc-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="uc-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Unit Converter",
      "description": "Convert between units of length, weight, temperature, speed, volume, area, time, digital storage, and energy. Free online unit converter with instant results and conversion tables.",
      "url": "https://theluckystrike.github.io/tools/unit-converter/",
      "applicationCategory": "UtilityApplication",
      "operatingSystem": "Any",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "USD"
      },
      "author": {
        "@type": "Person",
        "name": "Michael Lip",
        "url": "https://theluckystrike.github.io/about"
      }
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io"},
        {"@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/"},
        {"@type": "ListItem", "position": 3, "name": "Unit Converter", "item": "https://theluckystrike.github.io/tools/unit-converter/"}
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
          "name": "How do I convert kilometers to miles?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Multiply the number of kilometers by 0.621371 to get miles. For example, 10 km x 0.621371 = 6.21 miles. For a rough estimate, multiply by 0.6. The converter above handles this automatically: select Length, set \"From\" to Kilometers and \"To\" to Miles, and type your value."
          }
        },
        {
          "@type": "Question",
          "name": "What is the formula for Celsius to Fahrenheit?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Multiply the Celsius temperature by 9/5 (or 1.8), then add 32. The formula is F = (C x 9/5) + 32. For example, 25 C = (25 x 1.8) + 32 = 77 F. To go the other direction, subtract 32 first, then multiply by 5/9."
          }
        },
        {
          "@type": "Question",
          "name": "Why does my hard drive show less space than advertised?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Storage manufacturers use SI prefixes where 1 GB = 1,000,000,000 bytes. Operating systems like Windows use binary interpretation where 1 GB = 1,073,741,824 bytes. A drive advertised as 500 GB (500 billion bytes) shows as roughly 465 GB in Windows because 500,000,000,000 / 1,073,741,824 = 465.66."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between a US gallon and a UK gallon?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A US gallon equals 3.785 liters, while a UK (imperial) gallon equals 4.546 liters. The UK gallon is about 20% larger. This difference also cascades to quarts and pints: a UK pint is 568 mL versus the US pint of 473 mL."
          }
        },
        {
          "@type": "Question",
          "name": "How many bytes are in a megabyte?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Using the SI (base-1000) standard, 1 megabyte (MB) = 1,000,000 bytes. Using the binary (base-1024) standard, 1 mebibyte (MiB) = 1,048,576 bytes. This converter uses SI prefixes. Network speeds, storage manufacturers, and the International System of Units all use base-1000."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data safe when using this converter?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All conversions run entirely in your web browser using JavaScript. No data is transmitted to any server, no information is stored, and no cookies are set."
          }
        }
      ]
    }
  ]
}
</script>

<script>
(function() {
  "use strict";

  // =============================================
  // Unit Data: each category has units with a
  // toBase factor (multiply to get base unit)
  // Temperature is handled specially.
  // =============================================

  var CATEGORIES = {
    length: {
      name: "Length",
      base: "m",
      units: [
        { id: "mm", name: "Millimeter (mm)", factor: 0.001 },
        { id: "cm", name: "Centimeter (cm)", factor: 0.01 },
        { id: "m", name: "Meter (m)", factor: 1 },
        { id: "km", name: "Kilometer (km)", factor: 1000 },
        { id: "in", name: "Inch (in)", factor: 0.0254 },
        { id: "ft", name: "Foot (ft)", factor: 0.3048 },
        { id: "yd", name: "Yard (yd)", factor: 0.9144 },
        { id: "mi", name: "Mile (mi)", factor: 1609.344 },
        { id: "nmi", name: "Nautical Mile (nmi)", factor: 1852 },
        { id: "um", name: "Micrometer (\u00b5m)", factor: 0.000001 }
      ],
      defaultFrom: "km",
      defaultTo: "mi",
      quickPairs: [
        ["km", "mi", "km \u2194 mi"],
        ["m", "ft", "m \u2194 ft"],
        ["cm", "in", "cm \u2194 in"],
        ["mm", "in", "mm \u2194 in"],
        ["m", "yd", "m \u2194 yd"]
      ],
      refRows: [
        ["1 Kilometer", "Miles", "km", "mi", 1],
        ["1 Mile", "Kilometers", "mi", "km", 1],
        ["1 Meter", "Feet", "m", "ft", 1],
        ["1 Foot", "Centimeters", "ft", "cm", 1],
        ["1 Inch", "Centimeters", "in", "cm", 1],
        ["1 Yard", "Meters", "yd", "m", 1],
        ["1 Nautical Mile", "Kilometers", "nmi", "km", 1]
      ]
    },
    weight: {
      name: "Weight / Mass",
      base: "kg",
      units: [
        { id: "mg", name: "Milligram (mg)", factor: 0.000001 },
        { id: "g", name: "Gram (g)", factor: 0.001 },
        { id: "kg", name: "Kilogram (kg)", factor: 1 },
        { id: "t", name: "Metric Ton (t)", factor: 1000 },
        { id: "oz", name: "Ounce (oz)", factor: 0.028349523125 },
        { id: "lb", name: "Pound (lb)", factor: 0.45359237 },
        { id: "st", name: "Stone (st)", factor: 6.35029318 },
        { id: "uston", name: "US Ton (short ton)", factor: 907.18474 }
      ],
      defaultFrom: "kg",
      defaultTo: "lb",
      quickPairs: [
        ["kg", "lb", "kg \u2194 lbs"],
        ["g", "oz", "g \u2194 oz"],
        ["kg", "st", "kg \u2194 stone"],
        ["t", "uston", "t \u2194 US ton"],
        ["mg", "g", "mg \u2194 g"]
      ],
      refRows: [
        ["1 Kilogram", "Pounds", "kg", "lb", 1],
        ["1 Pound", "Kilograms", "lb", "kg", 1],
        ["1 Ounce", "Grams", "oz", "g", 1],
        ["1 Stone", "Kilograms", "st", "kg", 1],
        ["1 Metric Ton", "Pounds", "t", "lb", 1],
        ["1 US Ton", "Kilograms", "uston", "kg", 1]
      ]
    },
    temperature: {
      name: "Temperature",
      base: "c",
      units: [
        { id: "c", name: "Celsius (\u00b0C)", factor: 1 },
        { id: "f", name: "Fahrenheit (\u00b0F)", factor: 1 },
        { id: "k", name: "Kelvin (K)", factor: 1 }
      ],
      defaultFrom: "c",
      defaultTo: "f",
      quickPairs: [
        ["c", "f", "\u00b0C \u2194 \u00b0F"],
        ["c", "k", "\u00b0C \u2194 K"],
        ["f", "k", "\u00b0F \u2194 K"]
      ],
      refRows: [
        ["0 \u00b0C", "Fahrenheit", "c", "f", 0],
        ["100 \u00b0C", "Fahrenheit", "c", "f", 100],
        ["32 \u00b0F", "Celsius", "f", "c", 32],
        ["212 \u00b0F", "Celsius", "f", "c", 212],
        ["0 K", "Celsius", "k", "c", 0],
        ["298.15 K", "Celsius", "k", "c", 298.15]
      ]
    },
    speed: {
      name: "Speed",
      base: "ms",
      units: [
        { id: "ms", name: "Meters/second (m/s)", factor: 1 },
        { id: "kmh", name: "Kilometers/hour (km/h)", factor: 0.277777778 },
        { id: "mph", name: "Miles/hour (mph)", factor: 0.44704 },
        { id: "kn", name: "Knots (kn)", factor: 0.514444444 },
        { id: "fts", name: "Feet/second (ft/s)", factor: 0.3048 },
        { id: "mach", name: "Mach", factor: 340.29 }
      ],
      defaultFrom: "kmh",
      defaultTo: "mph",
      quickPairs: [
        ["kmh", "mph", "km/h \u2194 mph"],
        ["ms", "kmh", "m/s \u2194 km/h"],
        ["kn", "kmh", "kn \u2194 km/h"],
        ["mph", "kn", "mph \u2194 kn"],
        ["ms", "mach", "m/s \u2194 Mach"]
      ],
      refRows: [
        ["1 km/h", "mph", "kmh", "mph", 1],
        ["1 mph", "km/h", "mph", "kmh", 1],
        ["1 m/s", "km/h", "ms", "kmh", 1],
        ["1 Knot", "km/h", "kn", "kmh", 1],
        ["Mach 1", "km/h", "mach", "kmh", 1],
        ["100 km/h", "m/s", "kmh", "ms", 100]
      ]
    },
    volume: {
      name: "Volume",
      base: "l",
      units: [
        { id: "ml", name: "Milliliter (mL)", factor: 0.001 },
        { id: "l", name: "Liter (L)", factor: 1 },
        { id: "usgal", name: "US Gallon", factor: 3.785411784 },
        { id: "ukgal", name: "UK Gallon", factor: 4.54609 },
        { id: "usqt", name: "US Quart", factor: 0.946352946 },
        { id: "uspt", name: "US Pint", factor: 0.473176473 },
        { id: "uscup", name: "US Cup", factor: 0.2365882365 },
        { id: "usfloz", name: "US Fluid Ounce", factor: 0.0295735296 },
        { id: "tbsp", name: "Tablespoon", factor: 0.0147867648 },
        { id: "tsp", name: "Teaspoon", factor: 0.0049289216 },
        { id: "m3", name: "Cubic Meter (m\u00b3)", factor: 1000 },
        { id: "ft3", name: "Cubic Foot (ft\u00b3)", factor: 28.3168466 }
      ],
      defaultFrom: "l",
      defaultTo: "usgal",
      quickPairs: [
        ["l", "usgal", "L \u2194 US gal"],
        ["ml", "usfloz", "mL \u2194 fl oz"],
        ["l", "ukgal", "L \u2194 UK gal"],
        ["uscup", "ml", "cup \u2194 mL"],
        ["usgal", "l", "US gal \u2194 L"]
      ],
      refRows: [
        ["1 Liter", "US Gallons", "l", "usgal", 1],
        ["1 US Gallon", "Liters", "usgal", "l", 1],
        ["1 UK Gallon", "Liters", "ukgal", "l", 1],
        ["1 US Cup", "Milliliters", "uscup", "ml", 1],
        ["1 US Fluid Ounce", "Milliliters", "usfloz", "ml", 1],
        ["1 Cubic Meter", "Liters", "m3", "l", 1],
        ["1 Cubic Foot", "Liters", "ft3", "l", 1]
      ]
    },
    area: {
      name: "Area",
      base: "m2",
      units: [
        { id: "mm2", name: "Square Millimeter (mm\u00b2)", factor: 0.000001 },
        { id: "cm2", name: "Square Centimeter (cm\u00b2)", factor: 0.0001 },
        { id: "m2", name: "Square Meter (m\u00b2)", factor: 1 },
        { id: "km2", name: "Square Kilometer (km\u00b2)", factor: 1000000 },
        { id: "in2", name: "Square Inch (in\u00b2)", factor: 0.00064516 },
        { id: "ft2", name: "Square Foot (ft\u00b2)", factor: 0.09290304 },
        { id: "yd2", name: "Square Yard (yd\u00b2)", factor: 0.83612736 },
        { id: "acre", name: "Acre", factor: 4046.8564224 },
        { id: "ha", name: "Hectare (ha)", factor: 10000 },
        { id: "mi2", name: "Square Mile (mi\u00b2)", factor: 2589988.110336 }
      ],
      defaultFrom: "m2",
      defaultTo: "ft2",
      quickPairs: [
        ["m2", "ft2", "m\u00b2 \u2194 ft\u00b2"],
        ["km2", "mi2", "km\u00b2 \u2194 mi\u00b2"],
        ["acre", "ha", "acre \u2194 ha"],
        ["ha", "acre", "ha \u2194 acre"],
        ["ft2", "m2", "ft\u00b2 \u2194 m\u00b2"]
      ],
      refRows: [
        ["1 Square Meter", "Square Feet", "m2", "ft2", 1],
        ["1 Acre", "Square Meters", "acre", "m2", 1],
        ["1 Hectare", "Acres", "ha", "acre", 1],
        ["1 Square Kilometer", "Square Miles", "km2", "mi2", 1],
        ["1 Square Mile", "Square Kilometers", "mi2", "km2", 1],
        ["1 Square Foot", "Square Meters", "ft2", "m2", 1]
      ]
    },
    time: {
      name: "Time",
      base: "s",
      units: [
        { id: "ms", name: "Millisecond (ms)", factor: 0.001 },
        { id: "s", name: "Second (s)", factor: 1 },
        { id: "min", name: "Minute (min)", factor: 60 },
        { id: "h", name: "Hour (h)", factor: 3600 },
        { id: "d", name: "Day (d)", factor: 86400 },
        { id: "wk", name: "Week (wk)", factor: 604800 },
        { id: "mo", name: "Month (30d)", factor: 2592000 },
        { id: "yr", name: "Year (365d)", factor: 31536000 }
      ],
      defaultFrom: "h",
      defaultTo: "min",
      quickPairs: [
        ["h", "min", "h \u2194 min"],
        ["d", "h", "d \u2194 h"],
        ["wk", "d", "wk \u2194 d"],
        ["yr", "d", "yr \u2194 d"],
        ["min", "s", "min \u2194 s"]
      ],
      refRows: [
        ["1 Hour", "Minutes", "h", "min", 1],
        ["1 Day", "Hours", "d", "h", 1],
        ["1 Week", "Days", "wk", "d", 1],
        ["1 Month (30d)", "Days", "mo", "d", 1],
        ["1 Year (365d)", "Days", "yr", "d", 1],
        ["1 Year (365d)", "Hours", "yr", "h", 1]
      ]
    },
    digital: {
      name: "Digital Storage",
      base: "byte",
      units: [
        { id: "bit", name: "Bit (b)", factor: 0.125 },
        { id: "byte", name: "Byte (B)", factor: 1 },
        { id: "kb", name: "Kilobyte (KB)", factor: 1000 },
        { id: "mb", name: "Megabyte (MB)", factor: 1000000 },
        { id: "gb", name: "Gigabyte (GB)", factor: 1000000000 },
        { id: "tb", name: "Terabyte (TB)", factor: 1000000000000 },
        { id: "pb", name: "Petabyte (PB)", factor: 1000000000000000 },
        { id: "kbit", name: "Kilobit (Kb)", factor: 125 },
        { id: "mbit", name: "Megabit (Mb)", factor: 125000 },
        { id: "gbit", name: "Gigabit (Gb)", factor: 125000000 }
      ],
      defaultFrom: "gb",
      defaultTo: "mb",
      quickPairs: [
        ["gb", "mb", "GB \u2194 MB"],
        ["tb", "gb", "TB \u2194 GB"],
        ["mb", "kb", "MB \u2194 KB"],
        ["byte", "bit", "B \u2194 b"],
        ["mbit", "mb", "Mbit \u2194 MB"]
      ],
      refRows: [
        ["1 Kilobyte", "Bytes", "kb", "byte", 1],
        ["1 Megabyte", "Kilobytes", "mb", "kb", 1],
        ["1 Gigabyte", "Megabytes", "gb", "mb", 1],
        ["1 Terabyte", "Gigabytes", "tb", "gb", 1],
        ["1 Petabyte", "Terabytes", "pb", "tb", 1],
        ["1 Byte", "Bits", "byte", "bit", 1],
        ["1 Megabit", "Megabytes", "mbit", "mb", 1]
      ]
    },
    energy: {
      name: "Energy",
      base: "j",
      units: [
        { id: "j", name: "Joule (J)", factor: 1 },
        { id: "kj", name: "Kilojoule (kJ)", factor: 1000 },
        { id: "cal", name: "Calorie (cal)", factor: 4.184 },
        { id: "kcal", name: "Kilocalorie (kcal)", factor: 4184 },
        { id: "wh", name: "Watt-hour (Wh)", factor: 3600 },
        { id: "kwh", name: "Kilowatt-hour (kWh)", factor: 3600000 },
        { id: "btu", name: "BTU", factor: 1055.06 },
        { id: "ev", name: "Electronvolt (eV)", factor: 1.602176634e-19 }
      ],
      defaultFrom: "kcal",
      defaultTo: "kj",
      quickPairs: [
        ["kcal", "kj", "kcal \u2194 kJ"],
        ["kwh", "j", "kWh \u2194 J"],
        ["btu", "kj", "BTU \u2194 kJ"],
        ["cal", "j", "cal \u2194 J"],
        ["wh", "kj", "Wh \u2194 kJ"]
      ],
      refRows: [
        ["1 Kilocalorie", "Kilojoules", "kcal", "kj", 1],
        ["1 BTU", "Joules", "btu", "j", 1],
        ["1 Kilowatt-hour", "Kilojoules", "kwh", "kj", 1],
        ["1 Calorie", "Joules", "cal", "j", 1],
        ["1 Watt-hour", "Kilojoules", "wh", "kj", 1],
        ["1 Kilojoule", "Calories", "kj", "cal", 1]
      ]
    }
  };

  // =============================================
  // Temperature conversion functions
  // =============================================
  function tempToBase(val, fromId) {
    // Convert to Celsius as base
    if (fromId === "c") return val;
    if (fromId === "f") return (val - 32) * 5 / 9;
    if (fromId === "k") return val - 273.15;
    return val;
  }

  function tempFromBase(val, toId) {
    // Convert from Celsius to target
    if (toId === "c") return val;
    if (toId === "f") return (val * 9 / 5) + 32;
    if (toId === "k") return val + 273.15;
    return val;
  }

  // =============================================
  // Core conversion function
  // =============================================
  function convert(val, fromId, toId, catKey) {
    if (isNaN(val)) return NaN;
    if (fromId === toId) return val;

    if (catKey === "temperature") {
      var base = tempToBase(val, fromId);
      return tempFromBase(base, toId);
    }

    var cat = CATEGORIES[catKey];
    var fromUnit = null, toUnit = null;
    for (var i = 0; i < cat.units.length; i++) {
      if (cat.units[i].id === fromId) fromUnit = cat.units[i];
      if (cat.units[i].id === toId) toUnit = cat.units[i];
    }
    if (!fromUnit || !toUnit) return NaN;

    // Convert: from -> base -> to
    var baseVal = val * fromUnit.factor;
    return baseVal / toUnit.factor;
  }

  // =============================================
  // Format numbers nicely
  // =============================================
  function formatNum(n) {
    if (isNaN(n) || !isFinite(n)) return "";
    var abs = Math.abs(n);
    var digits;
    if (abs === 0) digits = 0;
    else if (abs >= 1000000) digits = 2;
    else if (abs >= 100) digits = 4;
    else if (abs >= 1) digits = 6;
    else if (abs >= 0.001) digits = 8;
    else digits = 12;

    // Use toPrecision for very small or very large numbers
    if (abs !== 0 && (abs < 0.000001 || abs > 999999999999)) {
      return n.toExponential(6);
    }

    var s = n.toFixed(digits);
    // Remove trailing zeros after decimal
    if (s.indexOf(".") !== -1) {
      s = s.replace(/0+$/, "").replace(/\.$/, "");
    }
    return s;
  }

  // =============================================
  // Build formula string
  // =============================================
  function getFormulaText(fromId, toId, catKey, fromVal, result) {
    if (catKey === "temperature") {
      var fv = formatNum(fromVal);
      var rv = formatNum(result);
      if (fromId === "c" && toId === "f") return fv + " \u00d7 (9/5) + 32 = " + rv;
      if (fromId === "f" && toId === "c") return "(" + fv + " - 32) \u00d7 (5/9) = " + rv;
      if (fromId === "c" && toId === "k") return fv + " + 273.15 = " + rv;
      if (fromId === "k" && toId === "c") return fv + " - 273.15 = " + rv;
      if (fromId === "f" && toId === "k") return "(" + fv + " - 32) \u00d7 (5/9) + 273.15 = " + rv;
      if (fromId === "k" && toId === "f") return "(" + fv + " - 273.15) \u00d7 (9/5) + 32 = " + rv;
      return fv + " = " + rv;
    }

    var cat = CATEGORIES[catKey];
    var fromUnit = null, toUnit = null;
    for (var i = 0; i < cat.units.length; i++) {
      if (cat.units[i].id === fromId) fromUnit = cat.units[i];
      if (cat.units[i].id === toId) toUnit = cat.units[i];
    }
    if (!fromUnit || !toUnit) return "";

    var factor = fromUnit.factor / toUnit.factor;
    return formatNum(fromVal) + " \u00d7 " + formatNum(factor) + " = " + formatNum(result);
  }

  // =============================================
  // State
  // =============================================
  var currentCat = "length";
  var lastEditedField = "from"; // "from" or "to"

  // =============================================
  // DOM references
  // =============================================
  var elFromUnit = document.getElementById("ucFromUnit");
  var elToUnit = document.getElementById("ucToUnit");
  var elFromVal = document.getElementById("ucFromVal");
  var elToVal = document.getElementById("ucToVal");
  var elFormulaText = document.getElementById("ucFormulaText");
  var elQuickBtns = document.getElementById("ucQuickBtns");
  var elRefBody = document.getElementById("ucRefBody");
  var elTabs = document.getElementById("ucTabs");

  // =============================================
  // Populate dropdowns
  // =============================================
  function populateDropdowns() {
    var cat = CATEGORIES[currentCat];
    elFromUnit.innerHTML = "";
    elToUnit.innerHTML = "";

    for (var i = 0; i < cat.units.length; i++) {
      var u = cat.units[i];
      var opt1 = document.createElement("option");
      opt1.value = u.id;
      opt1.textContent = u.name;
      elFromUnit.appendChild(opt1);

      var opt2 = document.createElement("option");
      opt2.value = u.id;
      opt2.textContent = u.name;
      elToUnit.appendChild(opt2);
    }

    elFromUnit.value = cat.defaultFrom;
    elToUnit.value = cat.defaultTo;
  }

  // =============================================
  // Build quick convert buttons
  // =============================================
  function buildQuickButtons() {
    var cat = CATEGORIES[currentCat];
    elQuickBtns.innerHTML = "";

    for (var i = 0; i < cat.quickPairs.length; i++) {
      var pair = cat.quickPairs[i];
      var btn = document.createElement("button");
      btn.className = "uc-quick-btn";
      btn.textContent = pair[2];
      btn.setAttribute("data-from", pair[0]);
      btn.setAttribute("data-to", pair[1]);
      btn.addEventListener("click", function(e) {
        var f = this.getAttribute("data-from");
        var t = this.getAttribute("data-to");
        elFromUnit.value = f;
        elToUnit.value = t;
        updateQuickActive();
        doConvert();
      });
      elQuickBtns.appendChild(btn);
    }

    updateQuickActive();
  }

  function updateQuickActive() {
    var btns = elQuickBtns.querySelectorAll(".uc-quick-btn");
    for (var i = 0; i < btns.length; i++) {
      var f = btns[i].getAttribute("data-from");
      var t = btns[i].getAttribute("data-to");
      if (f === elFromUnit.value && t === elToUnit.value) {
        btns[i].classList.add("active");
      } else {
        btns[i].classList.remove("active");
      }
    }
  }

  // =============================================
  // Build reference table
  // =============================================
  function buildRefTable() {
    var cat = CATEGORIES[currentCat];
    elRefBody.innerHTML = "";

    for (var i = 0; i < cat.refRows.length; i++) {
      var row = cat.refRows[i];
      var result = convert(row[4], row[2], row[3], currentCat);
      var tr = document.createElement("tr");

      var td1 = document.createElement("td");
      td1.textContent = row[0];
      tr.appendChild(td1);

      var td2 = document.createElement("td");
      td2.textContent = row[1];
      tr.appendChild(td2);

      var td3 = document.createElement("td");
      td3.textContent = formatNum(result);
      tr.appendChild(td3);

      elRefBody.appendChild(tr);
    }
  }

  // =============================================
  // Perform conversion
  // =============================================
  function doConvert() {
    var fromId = elFromUnit.value;
    var toId = elToUnit.value;

    if (lastEditedField === "from") {
      var fromVal = parseFloat(elFromVal.value);
      if (isNaN(fromVal)) {
        elToVal.value = "";
        elFormulaText.textContent = "";
        return;
      }
      var result = convert(fromVal, fromId, toId, currentCat);
      elToVal.value = formatNum(result);
      elFormulaText.textContent = getFormulaText(fromId, toId, currentCat, fromVal, result);
    } else {
      var toVal = parseFloat(elToVal.value);
      if (isNaN(toVal)) {
        elFromVal.value = "";
        elFormulaText.textContent = "";
        return;
      }
      var resultRev = convert(toVal, toId, fromId, currentCat);
      elFromVal.value = formatNum(resultRev);
      elFormulaText.textContent = getFormulaText(toId, fromId, currentCat, toVal, resultRev);
    }

    updateQuickActive();
  }

  // =============================================
  // Switch category
  // =============================================
  function switchCategory(catKey) {
    currentCat = catKey;
    lastEditedField = "from";

    // Update tab styling
    var tabs = elTabs.querySelectorAll(".uc-tab");
    for (var i = 0; i < tabs.length; i++) {
      if (tabs[i].getAttribute("data-cat") === catKey) {
        tabs[i].classList.add("active");
      } else {
        tabs[i].classList.remove("active");
      }
    }

    populateDropdowns();
    buildQuickButtons();
    buildRefTable();

    elFromVal.value = "1";
    elToVal.value = "";
    doConvert();
  }

  // =============================================
  // Event listeners
  // =============================================

  // Tab clicks
  var tabButtons = elTabs.querySelectorAll(".uc-tab");
  for (var t = 0; t < tabButtons.length; t++) {
    tabButtons[t].addEventListener("click", function() {
      switchCategory(this.getAttribute("data-cat"));
    });
  }

  // From input
  elFromVal.addEventListener("input", function() {
    lastEditedField = "from";
    doConvert();
  });
  elFromVal.addEventListener("change", function() {
    lastEditedField = "from";
    doConvert();
  });

  // To input (bidirectional)
  elToVal.addEventListener("input", function() {
    lastEditedField = "to";
    doConvert();
  });
  elToVal.addEventListener("change", function() {
    lastEditedField = "to";
    doConvert();
  });

  // Dropdown changes
  elFromUnit.addEventListener("change", function() {
    doConvert();
  });
  elToUnit.addEventListener("change", function() {
    doConvert();
  });

  // Swap button
  document.getElementById("ucSwapBtn").addEventListener("click", function() {
    var tmpUnit = elFromUnit.value;
    elFromUnit.value = elToUnit.value;
    elToUnit.value = tmpUnit;

    var tmpVal = elFromVal.value;
    elFromVal.value = elToVal.value;
    elToVal.value = tmpVal;

    lastEditedField = "from";
    doConvert();
  });

  // =============================================
  // Initialize
  // =============================================
  switchCategory("length");

})();
</script>
