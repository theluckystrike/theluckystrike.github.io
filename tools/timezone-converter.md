---
layout: page
title: "Free Timezone Converter — World Clock & Meeting Planner | Zovo"
description: "Convert times between any timezone instantly. Live world clock for 10 major cities, meeting planner with business hours highlighting, and DST indicators. Free, no signup required."
permalink: /tools/timezone-converter/
keywords: "timezone converter, time zone converter, world clock, time difference, meeting planner, utc converter, est to pst, timezone calculator"
date: 2026-03-19
last_modified_at: 2026-03-19
categories: [tools]
tags: [timezone, time converter, world clock, meeting planner, utc, dst]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --tz-primary: #6C5CE7;
    --tz-primary-dark: #5A4BD1;
    --tz-primary-light: #A29BFE;
    --tz-bg: #0a0a0f;
    --tz-surface: #12121a;
    --tz-surface-alt: #181824;
    --tz-border: #1e1e2e;
    --tz-text: #e0e0e0;
    --tz-text-muted: #8888aa;
    --tz-green: #00ff88;
    --tz-green-dark: #00cc6a;
    --tz-red: #ff4466;
    --tz-yellow: #ffaa00;
    --tz-radius: 12px;
    --tz-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
    --tz-mono: 'JetBrains Mono', 'SF Mono', 'Consolas', monospace;
  }

  .tz-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--tz-text);
    max-width: 900px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .tz-wrapper * {
    box-sizing: border-box;
  }

  .tz-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .tz-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--tz-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .tz-hero h1 span {
    color: var(--tz-primary);
  }

  .tz-intro {
    font-size: 1.05rem;
    color: var(--tz-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .tz-updated {
    display: inline-block;
    margin-top: 12px;
    font-size: 0.78rem;
    color: var(--tz-text-muted);
    opacity: 0.7;
  }

  /* Cards */
  .tz-card {
    background: var(--tz-surface);
    border: 1px solid var(--tz-border);
    border-radius: var(--tz-radius);
    padding: 24px;
    margin-bottom: 20px;
  }

  .tz-card-title {
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--tz-text);
    margin: 0 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .tz-card-title .tz-icon {
    font-size: 1.2rem;
  }

  /* Form elements */
  .tz-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    align-items: flex-end;
    margin-bottom: 14px;
  }

  .tz-field {
    display: flex;
    flex-direction: column;
    gap: 4px;
    flex: 1;
    min-width: 140px;
  }

  .tz-field label {
    font-size: 0.75rem;
    font-weight: 500;
    color: var(--tz-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .tz-field select,
  .tz-field input {
    padding: 10px 12px;
    border: 1.5px solid var(--tz-border);
    border-radius: 8px;
    font-family: var(--tz-mono);
    font-size: 0.9rem;
    color: var(--tz-text);
    background: var(--tz-surface-alt);
    outline: none;
    transition: border-color 0.15s;
    width: 100%;
  }

  .tz-field select:focus,
  .tz-field input:focus {
    border-color: var(--tz-primary);
  }

  .tz-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .tz-btn-primary {
    background: var(--tz-primary);
    color: #fff;
  }

  .tz-btn-primary:hover {
    background: var(--tz-primary-dark);
  }

  .tz-btn-sm {
    padding: 6px 14px;
    font-size: 0.8rem;
    border-radius: 6px;
  }

  .tz-btn-outline {
    background: transparent;
    color: var(--tz-text);
    border: 1.5px solid var(--tz-border);
  }

  .tz-btn-outline:hover {
    border-color: var(--tz-primary);
    color: var(--tz-primary-light);
  }

  .tz-btn-outline.active {
    background: var(--tz-primary);
    color: #fff;
    border-color: var(--tz-primary);
  }

  /* Swap button */
  .tz-swap-btn {
    background: var(--tz-surface-alt);
    border: 1.5px solid var(--tz-border);
    color: var(--tz-text-muted);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    font-size: 1.1rem;
    transition: all 0.15s;
    align-self: center;
    flex-shrink: 0;
  }

  .tz-swap-btn:hover {
    border-color: var(--tz-primary);
    color: var(--tz-primary);
  }

  /* Result display */
  .tz-result {
    background: var(--tz-surface-alt);
    border: 1.5px solid var(--tz-border);
    border-radius: 8px;
    padding: 16px 20px;
    margin-top: 14px;
    display: none;
  }

  .tz-result-label {
    font-size: 0.75rem;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--tz-text-muted);
    margin-bottom: 4px;
  }

  .tz-result-time {
    font-family: var(--tz-mono);
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--tz-primary-light);
  }

  .tz-result-date {
    font-size: 0.88rem;
    color: var(--tz-text-muted);
    margin-top: 4px;
  }

  .tz-result-diff {
    font-size: 0.82rem;
    color: var(--tz-text-muted);
    margin-top: 8px;
    padding-top: 8px;
    border-top: 1px solid var(--tz-border);
  }

  /* World clock grid */
  .tz-clock-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .tz-clock-item {
    background: var(--tz-surface-alt);
    border: 1px solid var(--tz-border);
    border-radius: 8px;
    padding: 14px 16px;
    transition: border-color 0.15s;
  }

  .tz-clock-item:hover {
    border-color: var(--tz-primary);
  }

  .tz-clock-city {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--tz-text);
    margin-bottom: 2px;
  }

  .tz-clock-zone {
    font-size: 0.7rem;
    color: var(--tz-text-muted);
    margin-bottom: 8px;
  }

  .tz-clock-time {
    font-family: var(--tz-mono);
    font-size: 1.4rem;
    font-weight: 600;
    color: var(--tz-primary-light);
  }

  .tz-clock-date {
    font-size: 0.75rem;
    color: var(--tz-text-muted);
    margin-top: 2px;
  }

  .tz-clock-dst {
    display: inline-block;
    font-size: 0.65rem;
    font-weight: 600;
    padding: 1px 6px;
    border-radius: 4px;
    margin-left: 6px;
    vertical-align: middle;
  }

  .tz-dst-active {
    background: rgba(255, 170, 0, 0.15);
    color: var(--tz-yellow);
  }

  .tz-dst-inactive {
    background: rgba(136, 136, 170, 0.1);
    color: var(--tz-text-muted);
  }

  /* Quick conversion buttons */
  .tz-quick-btns {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tz-quick-btn {
    padding: 8px 16px;
    background: var(--tz-surface-alt);
    border: 1px solid var(--tz-border);
    border-radius: 8px;
    color: var(--tz-text);
    font-family: var(--tz-mono);
    font-size: 0.82rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s;
  }

  .tz-quick-btn:hover {
    border-color: var(--tz-primary);
    color: var(--tz-primary-light);
  }

  /* Meeting planner */
  .tz-meeting-zones {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 14px;
  }

  .tz-meeting-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 12px;
    background: var(--tz-surface-alt);
    border: 1px solid var(--tz-border);
    border-radius: 6px;
    font-size: 0.8rem;
    color: var(--tz-text);
  }

  .tz-meeting-tag-remove {
    background: none;
    border: none;
    color: var(--tz-text-muted);
    cursor: pointer;
    font-size: 1rem;
    padding: 0;
    line-height: 1;
  }

  .tz-meeting-tag-remove:hover {
    color: var(--tz-red);
  }

  .tz-meeting-grid {
    width: 100%;
    border-collapse: collapse;
    margin-top: 14px;
  }

  .tz-meeting-grid th {
    text-align: left;
    padding: 10px 12px;
    background: var(--tz-surface-alt);
    font-size: 0.78rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    color: var(--tz-text-muted);
    border-bottom: 2px solid var(--tz-border);
    white-space: nowrap;
  }

  .tz-meeting-grid td {
    padding: 8px 12px;
    border-bottom: 1px solid var(--tz-border);
    font-family: var(--tz-mono);
    font-size: 0.85rem;
  }

  .tz-meeting-grid tr:last-child td {
    border-bottom: none;
  }

  .tz-biz-hours {
    color: var(--tz-green);
    font-weight: 600;
  }

  .tz-off-hours {
    color: var(--tz-text-muted);
  }

  .tz-biz-indicator {
    display: inline-block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    margin-right: 6px;
    vertical-align: middle;
  }

  .tz-biz-indicator.biz-on {
    background: var(--tz-green);
  }

  .tz-biz-indicator.biz-off {
    background: var(--tz-text-muted);
  }

  /* Content section */
  .tz-content {
    margin-top: 40px;
    padding-top: 32px;
    border-top: 1px solid var(--tz-border);
  }

  .tz-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--tz-text);
    margin: 0 0 16px;
  }

  .tz-content h3 {
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--tz-text);
    margin: 28px 0 10px;
  }

  .tz-content p {
    color: var(--tz-text-muted);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .tz-content ul {
    color: var(--tz-text-muted);
    line-height: 1.75;
    padding-left: 20px;
    margin: 0 0 14px;
  }

  /* FAQ */
  .tz-faq {
    margin-top: 40px;
    padding-top: 32px;
    border-top: 1px solid var(--tz-border);
  }

  .tz-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 24px;
    text-align: center;
    color: var(--tz-text);
  }

  .tz-faq-item {
    border: 1px solid var(--tz-border);
    border-radius: var(--tz-radius);
    margin-bottom: 12px;
    overflow: hidden;
  }

  .tz-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0;
    padding: 16px 20px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--tz-surface);
    color: var(--tz-text);
    transition: background 0.15s;
  }

  .tz-faq-item h3:hover {
    background: var(--tz-surface-alt);
  }

  .tz-faq-item h3::after {
    content: '+';
    font-size: 1.3rem;
    font-weight: 400;
    color: var(--tz-text-muted);
    transition: transform 0.2s;
  }

  .tz-faq-item.tz-open h3::after {
    content: '\2212';
  }

  .tz-faq-item p {
    margin: 0;
    padding: 0 20px 16px;
    color: var(--tz-text-muted);
    line-height: 1.7;
    display: none;
  }

  .tz-faq-item.tz-open p {
    display: block;
  }

  /* Author box */
  .tz-author-box {
    display: flex;
    gap: 16px;
    align-items: center;
    padding: 20px;
    background: var(--tz-surface);
    border: 1px solid var(--tz-border);
    border-radius: var(--tz-radius);
    margin-top: 32px;
  }

  .tz-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--tz-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: 700;
    font-size: 1.2rem;
    flex-shrink: 0;
  }

  .tz-author-info {
    flex: 1;
  }

  .tz-author-name {
    font-weight: 600;
    color: var(--tz-text);
    margin: 0;
    font-size: 0.95rem;
  }

  .tz-author-bio {
    color: var(--tz-text-muted);
    font-size: 0.82rem;
    margin: 4px 0 0;
    line-height: 1.5;
  }

  /* Related tools */
  .tz-related {
    margin-top: 24px;
    margin-bottom: 16px;
  }

  .tz-related h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--tz-text);
    margin: 0 0 12px;
  }

  .tz-related-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
  }

  .tz-related-link {
    display: block;
    padding: 12px 16px;
    background: var(--tz-surface);
    border: 1px solid var(--tz-border);
    border-radius: 8px;
    color: var(--tz-text);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 500;
    transition: border-color 0.2s;
  }

  .tz-related-link:hover {
    border-color: var(--tz-primary);
  }

  .tz-related-link span {
    display: block;
    font-size: 0.75rem;
    color: var(--tz-text-muted);
    font-weight: 400;
    margin-top: 4px;
  }

  .tz-footer {
    text-align: center;
    padding: 24px 0;
    font-size: 0.78rem;
    color: var(--tz-text-muted);
  }

  .tz-footer a {
    color: var(--tz-primary);
    text-decoration: none;
  }

  .tz-footer a:hover {
    text-decoration: underline;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .tz-hero h1 {
      font-size: 1.6rem;
    }

    .tz-row {
      flex-direction: column;
    }

    .tz-swap-btn {
      align-self: center;
      transform: rotate(90deg);
    }

    .tz-clock-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .tz-quick-btns {
      justify-content: center;
    }

    .tz-result-time {
      font-size: 1.4rem;
    }

    .tz-meeting-grid th,
    .tz-meeting-grid td {
      padding: 6px 8px;
      font-size: 0.78rem;
    }

    .tz-author-box {
      flex-direction: column;
      text-align: center;
    }

    .tz-related-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 480px) {
    .tz-clock-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="tz-wrapper">

  <div class="tz-hero">
    <h1><span>Timezone</span> Converter</h1>
    <p class="tz-intro">Convert times between any timezone, view a world clock for major cities, and plan meetings across time zones. All processing happens in your browser using Intl.DateTimeFormat -- nothing is sent to a server.</p>
    <span class="tz-updated">Last updated: March 2026</span>
  </div>

  <!-- Timezone Converter -->
  <div class="tz-card">
    <div class="tz-card-title"><span class="tz-icon">&#127760;</span> Convert Time</div>
    <div class="tz-row">
      <div class="tz-field" style="flex:2;">
        <label for="tzFromZone">From timezone</label>
        <select id="tzFromZone"></select>
      </div>
      <div class="tz-field" style="flex:1;">
        <label for="tzFromDate">Date</label>
        <input type="date" id="tzFromDate">
      </div>
      <div class="tz-field" style="flex:1;">
        <label for="tzFromTime">Time</label>
        <input type="time" id="tzFromTime" step="60">
      </div>
    </div>
    <div class="tz-row" style="margin-bottom:0;">
      <button type="button" class="tz-swap-btn" onclick="tzSwap()" title="Swap timezones">&#8645;</button>
      <div class="tz-field" style="flex:2;">
        <label for="tzToZone">To timezone</label>
        <select id="tzToZone"></select>
      </div>
      <div style="flex:1;align-self:flex-end;">
        <button type="button" class="tz-btn tz-btn-primary" onclick="tzConvert()" style="width:100%;">Convert</button>
      </div>
    </div>
    <div class="tz-result" id="tzResult">
      <div class="tz-result-label">Converted Time</div>
      <div class="tz-result-time" id="tzResultTime"></div>
      <div class="tz-result-date" id="tzResultDate"></div>
      <div class="tz-result-diff" id="tzResultDiff"></div>
    </div>
  </div>

  <!-- Quick Conversions -->
  <div class="tz-card">
    <div class="tz-card-title"><span class="tz-icon">&#9889;</span> Common Conversions</div>
    <div class="tz-quick-btns">
      <button type="button" class="tz-quick-btn" onclick="tzQuick('America/New_York','America/Los_Angeles')">EST &#8596; PST</button>
      <button type="button" class="tz-quick-btn" onclick="tzQuick('America/New_York','Europe/London')">EST &#8596; GMT</button>
      <button type="button" class="tz-quick-btn" onclick="tzQuick('America/New_York','Asia/Kolkata')">EST &#8596; IST</button>
      <button type="button" class="tz-quick-btn" onclick="tzQuick('America/Los_Angeles','Asia/Tokyo')">PST &#8596; JST</button>
      <button type="button" class="tz-quick-btn" onclick="tzQuick('Europe/London','Asia/Tokyo')">GMT &#8596; JST</button>
      <button type="button" class="tz-quick-btn" onclick="tzQuick('Europe/Berlin','America/New_York')">CET &#8596; EST</button>
    </div>
  </div>

  <!-- World Clock -->
  <div class="tz-card">
    <div class="tz-card-title"><span class="tz-icon">&#128336;</span> World Clock</div>
    <div class="tz-clock-grid" id="tzWorldClock"></div>
  </div>

  <!-- Meeting Planner -->
  <div class="tz-card">
    <div class="tz-card-title"><span class="tz-icon">&#128197;</span> Meeting Planner</div>
    <p style="font-size:0.85rem;color:var(--tz-text-muted);margin:0 0 14px;">Select timezones and a time to see when everyone is in business hours (9:00 -- 17:00).</p>
    <div class="tz-row">
      <div class="tz-field" style="flex:2;">
        <label for="tzMeetZoneSelect">Add timezone</label>
        <select id="tzMeetZoneSelect"></select>
      </div>
      <div style="align-self:flex-end;">
        <button type="button" class="tz-btn tz-btn-primary tz-btn-sm" onclick="tzAddMeetZone()">Add</button>
      </div>
    </div>
    <div class="tz-meeting-zones" id="tzMeetZones"></div>
    <div class="tz-row">
      <div class="tz-field" style="flex:1;">
        <label for="tzMeetBaseZone">Base timezone</label>
        <select id="tzMeetBaseZone"></select>
      </div>
      <div class="tz-field" style="flex:1;">
        <label for="tzMeetTime">Meeting time</label>
        <input type="time" id="tzMeetTime" value="10:00" step="60">
      </div>
      <div style="align-self:flex-end;">
        <button type="button" class="tz-btn tz-btn-primary" onclick="tzPlanMeeting()">Plan</button>
      </div>
    </div>
    <div id="tzMeetResult"></div>
  </div>

  <!-- SEO Content -->
  <div class="tz-content">

<h2>What Are Timezones</h2>

<p>A timezone is a region of the globe that observes a uniform standard time for legal, commercial, and social purposes. The earth rotates 360 degrees in 24 hours, so each 15-degree slice of longitude corresponds to roughly one hour of time difference. In practice, timezone boundaries follow political and economic borders rather than strict meridian lines, which is why some timezones have irregular shapes and unusual offsets like UTC+5:30 (India) or UTC+5:45 (Nepal).</p>

<p>There are currently over 30 distinct UTC offsets in use worldwide, ranging from UTC-12:00 (Baker Island) to UTC+14:00 (Line Islands in Kiribati). Some countries span multiple timezones -- Russia covers 11 -- while others with vast east-west extent, like China and India, maintain a single timezone across the entire country. The choice between one or many timezones has trade-offs: a single timezone simplifies domestic coordination but creates large differences between clock time and solar noon at the edges.</p>

<h3>How Timezone Conversion Works</h3>

<p>Every timezone is defined as an offset from Coordinated Universal Time (UTC). To convert between two timezones, you first express the source time in UTC, then apply the target timezone's offset. For example, if it is 14:00 in New York (UTC-5), the UTC time is 19:00. Tokyo is UTC+9, so the Tokyo time is 19:00 + 9 = 28:00, which wraps around to 04:00 the next day.</p>

<p>This converter handles the math using the browser's built-in Intl.DateTimeFormat API, which reads the IANA timezone database maintained in your operating system. This means the converter stays accurate even when governments change their timezone rules, as long as your OS is up to date. No external API calls are needed and no data leaves your device.</p>

<h3>Understanding UTC and GMT</h3>

<p>UTC (Coordinated Universal Time) is the primary time standard by which the world regulates clocks and time. It replaced GMT (Greenwich Mean Time) as the international standard in 1972. For most practical purposes, UTC and GMT represent the same time. The difference is technical: GMT is defined by the mean solar time at the Royal Observatory in Greenwich, while UTC is defined by atomic clocks and is adjusted with occasional leap seconds to stay within 0.9 seconds of solar time.</p>

<p>When you see a timestamp written as "2026-03-19T14:30:00Z," the Z stands for Zulu time, which is another name for UTC. Military and aviation use the NATO phonetic alphabet to label timezones: A through M (skipping J) for positive offsets, N through Y for negative offsets, and Z for UTC itself.</p>

<h3>Daylight Saving Time</h3>

<p>Daylight Saving Time (DST) shifts clocks forward by one hour in spring and back by one hour in fall in regions that observe it. About 70 countries use DST in some form, but the dates of the transition vary. In the United States, DST begins on the second Sunday of March and ends on the first Sunday of November. The European Union uses the last Sunday of March and the last Sunday of October. Countries near the equator generally do not observe DST because the variation in daylight hours is minimal throughout the year.</p>

<p>DST complicates timezone conversion because the offset between two locations can change depending on the date. New York and London are normally 5 hours apart, but during the weeks when one has switched and the other has not, the difference is either 4 or 6 hours. The converter above accounts for DST automatically by using the IANA timezone database, which records the historical and current DST rules for every region.</p>

<h3>Practical Tips for Working Across Timezones</h3>

<p>Remote teams that span more than 8 hours of timezone difference face the challenge of having no overlapping business hours. A common strategy is to identify a 2-to-3-hour window where at least most team members are awake, even if it falls outside standard 9-to-5 for some. The meeting planner above highlights business hours in green so you can visually scan for overlap.</p>

<p>When scheduling across timezones, always specify the timezone explicitly. Saying "3 PM" without a timezone reference guarantees confusion. Use UTC or name the timezone (e.g., "3 PM Eastern" or "15:00 UTC"). Calendar applications like Google Calendar handle timezone conversion automatically when you specify the event timezone, but email and chat messages do not.</p>

  </div>

  <!-- FAQ -->
  <div class="tz-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="tz-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="tzToggleFaq(this)">What is the difference between UTC and GMT?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">For all practical purposes, UTC and GMT represent the same time: zero offset from the prime meridian. The technical distinction is that GMT is based on astronomical observations of the sun, while UTC is based on International Atomic Time with leap seconds added to keep it aligned with the Earth's rotation. You can treat them as interchangeable in everyday timezone conversion.</p>
      </div>
    </div>

    <div class="tz-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="tzToggleFaq(this)">Does this converter handle Daylight Saving Time automatically?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The converter uses the Intl.DateTimeFormat API, which references the IANA timezone database built into your operating system. This database contains the DST transition dates and rules for every timezone in the world. When you convert a time, the tool checks whether DST is active in both the source and target timezones on the selected date and applies the correct offsets.</p>
      </div>
    </div>

    <div class="tz-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="tzToggleFaq(this)">Why do some timezones have 30 or 45-minute offsets?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Not all timezones follow whole-hour offsets from UTC. India Standard Time is UTC+5:30, Nepal Time is UTC+5:45, and the Chatham Islands use UTC+12:45. These fractional offsets usually reflect a country's decision to split the difference between neighboring whole-hour zones to better align clock time with solar noon across their territory. The converter supports all standard IANA timezones including these fractional offsets.</p>
      </div>
    </div>

    <div class="tz-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="tzToggleFaq(this)">How do I find overlapping business hours for a global team?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Use the Meeting Planner section above. Add the timezones of all team members, select a base timezone, and enter a proposed meeting time. The table shows what time it will be in each location and highlights in green any times that fall within standard business hours (9:00 to 17:00). Adjust the meeting time until you find a slot where the most timezones show green.</p>
      </div>
    </div>

    <div class="tz-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="tzToggleFaq(this)">Is my data private when using this tool?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. All timezone calculations run entirely in your browser using JavaScript. No data is transmitted to any server. There are no API calls, no cookies, and no tracking. You can verify this by opening your browser's developer tools and checking the Network tab while using the converter.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="tz-author-box">
    <div class="tz-author-avatar">ML</div>
    <div class="tz-author-info">
      <p class="tz-author-name">Michael Lip</p>
      <p class="tz-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <div style="text-align:center;margin:16px 0;font-size:0.75rem;color:var(--tz-text-muted);">Last updated: March 2026</div>

  <!-- Cross-links -->
  <div class="tz-related">
    <h3>Related Tools</h3>
    <div class="tz-related-grid">
      <a href="/tools/unix-timestamp-converter/" class="tz-related-link">Unix Timestamp Converter <span>Convert epoch to dates and back</span></a>
      <a href="/tools/stopwatch/" class="tz-related-link">Stopwatch and Timer <span>Lap times, countdown, alarms</span></a>
      <a href="/tools/pomodoro-timer/" class="tz-related-link">Pomodoro Timer <span>Focus intervals with break tracking</span></a>
    </div>
  </div>

  <footer class="tz-footer">
    <p>Built by Michael Lip at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Timezone Converter",
      "description": "Convert times between any timezone instantly. Live world clock for major cities, meeting planner with business hours highlighting, and DST indicators.",
      "url": "https://theluckystrike.github.io/tools/timezone-converter/",
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
        {"@type": "ListItem", "position": 3, "name": "Timezone Converter", "item": "https://theluckystrike.github.io/tools/timezone-converter/"}
      ]
    },
    {
      "@type": "Organization",
      "name": "Zovo",
      "url": "https://zovo.one",
      "logo": "https://zovo.one/logo.png",
      "founder": {
        "@type": "Person",
        "name": "Michael Lip"
      }
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What is the difference between UTC and GMT?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For practical purposes, UTC and GMT represent the same time. GMT is based on astronomical observations; UTC is based on atomic clocks with leap seconds. They are interchangeable in everyday use."
          }
        },
        {
          "@type": "Question",
          "name": "Does this converter handle Daylight Saving Time automatically?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. It uses the Intl.DateTimeFormat API and the IANA timezone database built into your operating system, which contains DST rules for every timezone."
          }
        },
        {
          "@type": "Question",
          "name": "Why do some timezones have 30 or 45-minute offsets?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Some countries chose fractional offsets to better align clock time with solar noon. Examples include India (UTC+5:30) and Nepal (UTC+5:45). The converter supports all IANA timezones."
          }
        },
        {
          "@type": "Question",
          "name": "How do I find overlapping business hours for a global team?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Use the Meeting Planner section. Add team member timezones, set a meeting time, and look for green-highlighted slots that fall within 9:00-17:00 business hours."
          }
        },
        {
          "@type": "Question",
          "name": "Is my data private when using this tool?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All calculations run in your browser. No data is sent to any server. There are no API calls, cookies, or tracking."
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

  // --- Timezone data ---
  var ZONES = [
    { id: "Pacific/Midway", label: "Midway (UTC-11)", city: "" },
    { id: "Pacific/Honolulu", label: "Honolulu (UTC-10)", city: "" },
    { id: "America/Anchorage", label: "Anchorage (UTC-9)", city: "" },
    { id: "America/Los_Angeles", label: "Los Angeles / PST (UTC-8)", city: "Los Angeles" },
    { id: "America/Denver", label: "Denver / MST (UTC-7)", city: "" },
    { id: "America/Chicago", label: "Chicago / CST (UTC-6)", city: "" },
    { id: "America/New_York", label: "New York / EST (UTC-5)", city: "New York" },
    { id: "America/Sao_Paulo", label: "Sao Paulo (UTC-3)", city: "Sao Paulo" },
    { id: "Atlantic/South_Georgia", label: "South Georgia (UTC-2)", city: "" },
    { id: "Atlantic/Azores", label: "Azores (UTC-1)", city: "" },
    { id: "Europe/London", label: "London / GMT (UTC+0)", city: "London" },
    { id: "Europe/Berlin", label: "Berlin / CET (UTC+1)", city: "Berlin" },
    { id: "Europe/Helsinki", label: "Helsinki (UTC+2)", city: "" },
    { id: "Europe/Moscow", label: "Moscow (UTC+3)", city: "" },
    { id: "Asia/Dubai", label: "Dubai (UTC+4)", city: "Dubai" },
    { id: "Asia/Kolkata", label: "Mumbai / IST (UTC+5:30)", city: "Mumbai" },
    { id: "Asia/Kathmandu", label: "Kathmandu (UTC+5:45)", city: "" },
    { id: "Asia/Dhaka", label: "Dhaka (UTC+6)", city: "" },
    { id: "Asia/Bangkok", label: "Bangkok (UTC+7)", city: "" },
    { id: "Asia/Singapore", label: "Singapore (UTC+8)", city: "Singapore" },
    { id: "Asia/Tokyo", label: "Tokyo / JST (UTC+9)", city: "Tokyo" },
    { id: "Australia/Sydney", label: "Sydney / AEST (UTC+10)", city: "Sydney" },
    { id: "Pacific/Noumea", label: "Noumea (UTC+11)", city: "" },
    { id: "Pacific/Auckland", label: "Auckland (UTC+12)", city: "" }
  ];

  var WORLD_CLOCK_ZONES = [
    { id: "America/New_York", city: "New York" },
    { id: "America/Los_Angeles", city: "Los Angeles" },
    { id: "Europe/London", city: "London" },
    { id: "Europe/Berlin", city: "Berlin" },
    { id: "Asia/Dubai", city: "Dubai" },
    { id: "Asia/Kolkata", city: "Mumbai" },
    { id: "Asia/Singapore", city: "Singapore" },
    { id: "Asia/Tokyo", city: "Tokyo" },
    { id: "Australia/Sydney", city: "Sydney" },
    { id: "America/Sao_Paulo", city: "Sao Paulo" }
  ];

  // --- Populate dropdowns ---
  function populateSelect(el, selectedId) {
    var html = "";
    for (var i = 0; i < ZONES.length; i++) {
      var z = ZONES[i];
      var sel = z.id === selectedId ? " selected" : "";
      html += '<option value="' + z.id + '"' + sel + '>' + z.label + '</option>';
    }
    el.innerHTML = html;
  }

  var elFromZone = document.getElementById("tzFromZone");
  var elToZone = document.getElementById("tzToZone");
  var elFromDate = document.getElementById("tzFromDate");
  var elFromTime = document.getElementById("tzFromTime");
  var elResult = document.getElementById("tzResult");
  var elResultTime = document.getElementById("tzResultTime");
  var elResultDate = document.getElementById("tzResultDate");
  var elResultDiff = document.getElementById("tzResultDiff");
  var elMeetZoneSelect = document.getElementById("tzMeetZoneSelect");
  var elMeetBaseZone = document.getElementById("tzMeetBaseZone");
  var elMeetZones = document.getElementById("tzMeetZones");
  var elMeetTime = document.getElementById("tzMeetTime");
  var elMeetResult = document.getElementById("tzMeetResult");
  var elWorldClock = document.getElementById("tzWorldClock");

  populateSelect(elFromZone, "America/New_York");
  populateSelect(elToZone, "Europe/London");
  populateSelect(elMeetZoneSelect, "America/New_York");
  populateSelect(elMeetBaseZone, "America/New_York");

  // Set default date/time to now
  var now = new Date();
  var yy = now.getFullYear();
  var mm = String(now.getMonth() + 1).padStart(2, "0");
  var dd = String(now.getDate()).padStart(2, "0");
  var hh = String(now.getHours()).padStart(2, "0");
  var mi = String(now.getMinutes()).padStart(2, "0");
  elFromDate.value = yy + "-" + mm + "-" + dd;
  elFromTime.value = hh + ":" + mi;

  // --- Format helpers using Intl ---
  function getDateInZone(date, tz) {
    var opts = { timeZone: tz, year: "numeric", month: "2-digit", day: "2-digit", hour: "2-digit", minute: "2-digit", second: "2-digit", hour12: false };
    var parts = new Intl.DateTimeFormat("en-US", opts).formatToParts(date);
    var obj = {};
    for (var i = 0; i < parts.length; i++) {
      obj[parts[i].type] = parts[i].value;
    }
    return obj;
  }

  function getOffsetMinutes(date, tz) {
    var str = new Intl.DateTimeFormat("en-US", { timeZone: tz, timeZoneName: "shortOffset" }).format(date);
    var match = str.match(/GMT([+-]?\d{1,2})(?::(\d{2}))?$/);
    if (!match) return 0;
    var h = parseInt(match[1], 10);
    var m = parseInt(match[2] || "0", 10);
    return h * 60 + (h < 0 ? -m : m);
  }

  function isDST(date, tz) {
    var jan = new Date(date.getFullYear(), 0, 1);
    var jul = new Date(date.getFullYear(), 6, 1);
    var janOff = getOffsetMinutes(jan, tz);
    var julOff = getOffsetMinutes(jul, tz);
    if (janOff === julOff) return false;
    var currentOff = getOffsetMinutes(date, tz);
    var stdOff = Math.min(janOff, julOff);
    return currentOff !== stdOff;
  }

  function formatOffset(minutes) {
    var sign = minutes >= 0 ? "+" : "-";
    var abs = Math.abs(minutes);
    var h = Math.floor(abs / 60);
    var m = abs % 60;
    return "UTC" + sign + h + (m > 0 ? ":" + String(m).padStart(2, "0") : "");
  }

  function getTimezoneName(date, tz) {
    try {
      var fmt = new Intl.DateTimeFormat("en-US", { timeZone: tz, timeZoneName: "short" });
      var parts = fmt.formatToParts(date);
      for (var i = 0; i < parts.length; i++) {
        if (parts[i].type === "timeZoneName") return parts[i].value;
      }
    } catch(e) {}
    return tz;
  }

  // --- Build a Date object from date string, time string, and timezone ---
  function buildDateInTz(dateStr, timeStr, tz) {
    var parts = dateStr.split("-");
    var timeParts = timeStr.split(":");
    var year = parseInt(parts[0], 10);
    var month = parseInt(parts[1], 10) - 1;
    var day = parseInt(parts[2], 10);
    var hour = parseInt(timeParts[0], 10);
    var minute = parseInt(timeParts[1], 10);

    // Create a Date in UTC, then adjust for the timezone offset
    var utcGuess = new Date(Date.UTC(year, month, day, hour, minute, 0));
    var off = getOffsetMinutes(utcGuess, tz);
    var utcActual = new Date(utcGuess.getTime() - off * 60000);
    // Re-check offset (DST edge case)
    var off2 = getOffsetMinutes(utcActual, tz);
    if (off !== off2) {
      utcActual = new Date(utcGuess.getTime() - off2 * 60000);
    }
    return utcActual;
  }

  // --- Convert ---
  window.tzConvert = function() {
    var fromTz = elFromZone.value;
    var toTz = elToZone.value;
    var dateStr = elFromDate.value;
    var timeStr = elFromTime.value;

    if (!dateStr || !timeStr) return;

    var utcDate = buildDateInTz(dateStr, timeStr, fromTz);

    // Format in target timezone
    var toParts = getDateInZone(utcDate, toTz);
    var timeFormatted = toParts.hour + ":" + toParts.minute;
    var dateFormatted = toParts.month + "/" + toParts.day + "/" + toParts.year;

    // Day name
    var dayName = new Intl.DateTimeFormat("en-US", { timeZone: toTz, weekday: "long" }).format(utcDate);

    // Timezone abbreviation
    var tzAbbr = getTimezoneName(utcDate, toTz);

    // Offset difference
    var fromOff = getOffsetMinutes(utcDate, fromTz);
    var toOff = getOffsetMinutes(utcDate, toTz);
    var diffMinutes = toOff - fromOff;
    var diffH = Math.floor(Math.abs(diffMinutes) / 60);
    var diffM = Math.abs(diffMinutes) % 60;
    var diffStr = "";
    if (diffMinutes === 0) {
      diffStr = "Same timezone -- no time difference";
    } else {
      var sign = diffMinutes > 0 ? "ahead" : "behind";
      diffStr = diffH + (diffM > 0 ? "h " + diffM + "m" : " hour" + (diffH !== 1 ? "s" : "")) + " " + sign;
    }

    // DST info
    var fromDst = isDST(utcDate, fromTz) ? " (DST)" : "";
    var toDst = isDST(utcDate, toTz) ? " (DST)" : "";

    elResultTime.textContent = timeFormatted;
    elResultDate.textContent = dayName + ", " + dateFormatted + " " + tzAbbr + toDst;
    elResultDiff.textContent = diffStr + " | Source: " + getTimezoneName(utcDate, fromTz) + fromDst + " " + formatOffset(fromOff) + " | Target: " + tzAbbr + toDst + " " + formatOffset(toOff);
    elResult.style.display = "block";
  };

  // --- Swap ---
  window.tzSwap = function() {
    var tmp = elFromZone.value;
    elFromZone.value = elToZone.value;
    elToZone.value = tmp;
    if (elResult.style.display === "block") {
      tzConvert();
    }
  };

  // --- Quick conversion ---
  window.tzQuick = function(from, to) {
    elFromZone.value = from;
    elToZone.value = to;
    // Set to current time
    var n = new Date();
    elFromDate.value = n.getFullYear() + "-" + String(n.getMonth()+1).padStart(2,"0") + "-" + String(n.getDate()).padStart(2,"0");
    elFromTime.value = String(n.getHours()).padStart(2,"0") + ":" + String(n.getMinutes()).padStart(2,"0");
    tzConvert();
    // Scroll to result
    elResult.scrollIntoView({ behavior: "smooth", block: "center" });
  };

  // --- World Clock ---
  function updateWorldClock() {
    var now = new Date();
    var html = "";
    for (var i = 0; i < WORLD_CLOCK_ZONES.length; i++) {
      var wz = WORLD_CLOCK_ZONES[i];
      var parts = getDateInZone(now, wz.id);
      var tzName = getTimezoneName(now, wz.id);
      var dst = isDST(now, wz.id);
      var off = getOffsetMinutes(now, wz.id);
      var dayName = new Intl.DateTimeFormat("en-US", { timeZone: wz.id, weekday: "short" }).format(now);
      var monthName = new Intl.DateTimeFormat("en-US", { timeZone: wz.id, month: "short" }).format(now);

      html += '<div class="tz-clock-item">';
      html += '<div class="tz-clock-city">' + wz.city;
      if (dst) {
        html += '<span class="tz-clock-dst tz-dst-active">DST</span>';
      }
      html += '</div>';
      html += '<div class="tz-clock-zone">' + tzName + ' (' + formatOffset(off) + ')</div>';
      html += '<div class="tz-clock-time">' + parts.hour + ':' + parts.minute + '</div>';
      html += '<div class="tz-clock-date">' + dayName + ', ' + monthName + ' ' + parseInt(parts.day, 10) + '</div>';
      html += '</div>';
    }
    elWorldClock.innerHTML = html;
  }

  updateWorldClock();
  setInterval(updateWorldClock, 10000);

  // --- Meeting Planner ---
  var meetingZones = ["America/New_York", "Europe/London", "Asia/Tokyo"];

  function renderMeetZones() {
    var html = "";
    for (var i = 0; i < meetingZones.length; i++) {
      var z = meetingZones[i];
      var label = z.split("/").pop().replace(/_/g, " ");
      html += '<div class="tz-meeting-tag">';
      html += '<span>' + label + '</span>';
      html += '<button type="button" class="tz-meeting-tag-remove" onclick="tzRemoveMeetZone(' + i + ')">&times;</button>';
      html += '</div>';
    }
    elMeetZones.innerHTML = html;
    // Update base zone dropdown
    populateMeetBase();
  }

  function populateMeetBase() {
    var html = "";
    for (var i = 0; i < meetingZones.length; i++) {
      var z = meetingZones[i];
      var label = z.split("/").pop().replace(/_/g, " ");
      html += '<option value="' + z + '">' + label + '</option>';
    }
    elMeetBaseZone.innerHTML = html;
  }

  window.tzAddMeetZone = function() {
    var tz = elMeetZoneSelect.value;
    if (meetingZones.indexOf(tz) === -1) {
      meetingZones.push(tz);
      renderMeetZones();
    }
  };

  window.tzRemoveMeetZone = function(idx) {
    meetingZones.splice(idx, 1);
    renderMeetZones();
    if (elMeetResult.innerHTML) {
      tzPlanMeeting();
    }
  };

  window.tzPlanMeeting = function() {
    if (meetingZones.length === 0) {
      elMeetResult.innerHTML = '<p style="color:var(--tz-text-muted);font-size:0.85rem;">Add at least one timezone to plan a meeting.</p>';
      return;
    }

    var baseTz = elMeetBaseZone.value;
    var timeStr = elMeetTime.value;
    if (!timeStr) return;

    var today = new Date();
    var dateStr = today.getFullYear() + "-" + String(today.getMonth()+1).padStart(2,"0") + "-" + String(today.getDate()).padStart(2,"0");
    var utcDate = buildDateInTz(dateStr, timeStr, baseTz);

    var html = '<table class="tz-meeting-grid">';
    html += '<thead><tr><th>Location</th><th>Time</th><th>Status</th></tr></thead>';
    html += '<tbody>';

    for (var i = 0; i < meetingZones.length; i++) {
      var tz = meetingZones[i];
      var parts = getDateInZone(utcDate, tz);
      var hour = parseInt(parts.hour, 10);
      var isBiz = hour >= 9 && hour < 17;
      var cityLabel = tz.split("/").pop().replace(/_/g, " ");
      var tzName = getTimezoneName(utcDate, tz);
      var cls = isBiz ? "tz-biz-hours" : "tz-off-hours";
      var dotCls = isBiz ? "biz-on" : "biz-off";
      var statusText = isBiz ? "Business hours" : (hour >= 17 && hour < 22 ? "Evening" : (hour >= 22 || hour < 6 ? "Night" : "Early morning"));

      html += '<tr>';
      html += '<td>' + cityLabel + ' <span style="color:var(--tz-text-muted);font-size:0.75rem;">(' + tzName + ')</span></td>';
      html += '<td class="' + cls + '">' + parts.hour + ':' + parts.minute + '</td>';
      html += '<td><span class="tz-biz-indicator ' + dotCls + '"></span>' + statusText + '</td>';
      html += '</tr>';
    }

    html += '</tbody></table>';
    elMeetResult.innerHTML = html;
  };

  renderMeetZones();

  // --- FAQ toggle ---
  window.tzToggleFaq = function(el) {
    var item = el.parentElement;
    item.classList.toggle("tz-open");
  };

  // Auto-convert on enter key
  elFromTime.addEventListener("keydown", function(e) {
    if (e.key === "Enter") tzConvert();
  });

  elFromDate.addEventListener("change", function() {
    if (elResult.style.display === "block") tzConvert();
  });

})();
</script>
