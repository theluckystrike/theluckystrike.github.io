---
layout: page
title: "Unix Timestamp Converter - Epoch to Date Tool | Zovo"
description: "Free Unix timestamp converter -- convert epoch time to human-readable dates and dates to timestamps instantly. Shows UTC, local time, and ISO 8601 formats."
permalink: /tools/unix-timestamp-converter/
keywords: "unix timestamp converter, epoch converter, unix time converter, epoch to date, timestamp to date, date to timestamp, unix epoch converter"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [unix timestamp, epoch converter, date converter, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --ut-primary: #6C5CE7;
    --ut-primary-dark: #5A4BD1;
    --ut-primary-light: #A29BFE;
    --ut-bg: #F8F9FE;
    --ut-surface: #FFFFFF;
    --ut-text: #2D3436;
    --ut-text-muted: #636E72;
    --ut-border: #DFE6E9;
    --ut-success: #00B894;
    --ut-error: #D63031;
    --ut-radius: 12px;
    --ut-mono: 'JetBrains Mono', 'SF Mono', 'Consolas', monospace;
  }

  .ut-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ut-text);
    max-width: 900px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .ut-wrapper * {
    box-sizing: border-box;
  }

  .ut-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .ut-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ut-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .ut-hero h1 span {
    color: var(--ut-primary);
  }

  .ut-intro {
    font-size: 1.05rem;
    color: var(--ut-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Live Clock */
  .ut-live {
    background: linear-gradient(135deg, var(--ut-primary), var(--ut-primary-dark));
    color: #fff;
    border-radius: var(--ut-radius);
    padding: 24px;
    text-align: center;
    margin-bottom: 24px;
  }

  .ut-live-label {
    font-size: 0.85rem;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    opacity: 0.85;
    margin-bottom: 8px;
  }

  .ut-live-ts {
    font-family: var(--ut-mono);
    font-size: 2.4rem;
    font-weight: 700;
    letter-spacing: 0.02em;
    margin-bottom: 6px;
    cursor: pointer;
    transition: opacity 0.15s;
  }

  .ut-live-ts:hover {
    opacity: 0.85;
  }

  .ut-live-date {
    font-size: 0.95rem;
    opacity: 0.9;
  }

  .ut-live-hint {
    font-size: 0.78rem;
    opacity: 0.65;
    margin-top: 6px;
  }

  /* Section cards */
  .ut-card {
    background: var(--ut-surface);
    border: 1px solid var(--ut-border);
    border-radius: var(--ut-radius);
    padding: 24px;
    margin-bottom: 20px;
  }

  .ut-card h2 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 0 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .ut-card h2 .ut-icon {
    font-size: 1.3rem;
  }

  /* Form elements */
  .ut-input-group {
    display: flex;
    gap: 10px;
    margin-bottom: 14px;
    flex-wrap: wrap;
  }

  .ut-input {
    flex: 1;
    min-width: 200px;
    padding: 10px 14px;
    border: 1.5px solid var(--ut-border);
    border-radius: 8px;
    font-family: var(--ut-mono);
    font-size: 1rem;
    color: var(--ut-text);
    background: var(--ut-bg);
    outline: none;
    transition: border-color 0.15s;
  }

  .ut-input:focus {
    border-color: var(--ut-primary);
  }

  .ut-input::placeholder {
    color: #B2BEC3;
  }

  .ut-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .ut-btn-primary {
    background: var(--ut-primary);
    color: #fff;
  }

  .ut-btn-primary:hover {
    background: var(--ut-primary-dark);
  }

  .ut-btn-secondary {
    background: var(--ut-bg);
    color: var(--ut-text);
    border: 1.5px solid var(--ut-border);
  }

  .ut-btn-secondary:hover {
    background: var(--ut-border);
  }

  .ut-btn-sm {
    padding: 5px 12px;
    font-size: 0.8rem;
    border-radius: 6px;
  }

  /* Results table */
  .ut-results {
    width: 100%;
    border-collapse: collapse;
    margin-top: 12px;
  }

  .ut-results td {
    padding: 9px 12px;
    border-bottom: 1px solid var(--ut-border);
    font-size: 0.92rem;
  }

  .ut-results td:first-child {
    color: var(--ut-text-muted);
    font-weight: 500;
    width: 160px;
    white-space: nowrap;
  }

  .ut-results td:last-child {
    font-family: var(--ut-mono);
    font-size: 0.88rem;
    word-break: break-all;
  }

  .ut-results tr:last-child td {
    border-bottom: none;
  }

  .ut-copy-cell {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 8px;
  }

  .ut-copy-cell span {
    flex: 1;
  }

  /* Date picker row */
  .ut-date-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    align-items: flex-end;
    margin-bottom: 14px;
  }

  .ut-field {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .ut-field label {
    font-size: 0.78rem;
    font-weight: 500;
    color: var(--ut-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.04em;
  }

  .ut-field input, .ut-field select {
    padding: 9px 12px;
    border: 1.5px solid var(--ut-border);
    border-radius: 8px;
    font-family: var(--ut-mono);
    font-size: 0.92rem;
    color: var(--ut-text);
    background: var(--ut-bg);
    outline: none;
    transition: border-color 0.15s;
  }

  .ut-field input:focus, .ut-field select:focus {
    border-color: var(--ut-primary);
  }

  .ut-result-box {
    background: var(--ut-bg);
    border: 1.5px solid var(--ut-border);
    border-radius: 8px;
    padding: 14px 16px;
    font-family: var(--ut-mono);
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--ut-primary-dark);
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 12px;
  }

  /* Reference table */
  .ut-ref {
    width: 100%;
    border-collapse: collapse;
  }

  .ut-ref th {
    text-align: left;
    padding: 10px 12px;
    background: var(--ut-bg);
    font-size: 0.82rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    color: var(--ut-text-muted);
    border-bottom: 2px solid var(--ut-border);
  }

  .ut-ref td {
    padding: 10px 12px;
    border-bottom: 1px solid var(--ut-border);
    font-size: 0.9rem;
  }

  .ut-ref td:nth-child(2) {
    font-family: var(--ut-mono);
    font-size: 0.85rem;
  }

  .ut-ref tr:last-child td {
    border-bottom: none;
  }

  /* Error */
  .ut-error {
    background: #FFF5F5;
    border: 1px solid #FED7D7;
    color: var(--ut-error);
    border-radius: 8px;
    padding: 10px 14px;
    font-size: 0.88rem;
    margin-top: 10px;
    display: none;
  }

  /* Toast */
  .ut-toast {
    position: fixed;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%) translateY(80px);
    background: #2D3436;
    color: #fff;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 0.88rem;
    font-weight: 500;
    z-index: 9999;
    opacity: 0;
    transition: all 0.3s ease;
    pointer-events: none;
  }

  .ut-toast.ut-show {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }

  /* Meta & Footer */
  .ut-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 0;
    font-size: 0.82rem;
    color: var(--ut-text-muted);
    border-top: 1px solid var(--ut-border);
    margin-top: 8px;
  }

  /* FAQ */
  .ut-faq {
    margin-top: 40px;
    padding-top: 32px;
    border-top: 1px solid var(--ut-border);
  }

  .ut-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 24px;
    text-align: center;
  }

  .ut-faq-item {
    border: 1px solid var(--ut-border);
    border-radius: var(--ut-radius);
    margin-bottom: 12px;
    overflow: hidden;
  }

  .ut-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0;
    padding: 16px 20px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--ut-surface);
    transition: background 0.15s;
  }

  .ut-faq-item h3:hover {
    background: var(--ut-bg);
  }

  .ut-faq-item h3::after {
    content: '+';
    font-size: 1.3rem;
    font-weight: 400;
    color: var(--ut-text-muted);
    transition: transform 0.2s;
  }

  .ut-faq-item.ut-open h3::after {
    content: '−';
  }

  .ut-faq-item p {
    margin: 0;
    padding: 0 20px 16px;
    color: var(--ut-text-muted);
    line-height: 1.7;
    display: none;
  }

  .ut-faq-item.ut-open p {
    display: block;
  }

  /* Content section */
  .ut-content {
    margin-top: 40px;
    padding-top: 32px;
    border-top: 1px solid var(--ut-border);
  }

  .ut-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 16px;
  }

  .ut-content h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin: 24px 0 10px;
  }

  .ut-content p {
    color: var(--ut-text-muted);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .ut-content ul {
    color: var(--ut-text-muted);
    line-height: 1.75;
    padding-left: 20px;
    margin: 0 0 14px;
  }

  /* Responsive */
  @media (max-width: 640px) {
    .ut-hero h1 {
      font-size: 1.6rem;
    }

    .ut-live-ts {
      font-size: 1.6rem;
    }

    .ut-input-group {
      flex-direction: column;
    }

    .ut-date-row {
      flex-direction: column;
    }

    .ut-field {
      width: 100%;
    }

    .ut-results td:first-child {
      width: auto;
    }

    .ut-meta {
      flex-direction: column;
      gap: 6px;
      text-align: center;
    }

    .ut-ref th, .ut-ref td {
      padding: 8px 6px;
      font-size: 0.82rem;
    }
  }
</style>

<div class="ut-wrapper">

  <div class="ut-hero">
    <h1>Unix <span>Timestamp</span> Converter</h1>
    <p class="ut-intro">Convert Unix timestamps to human-readable dates and back. See results in UTC, your local timezone, and ISO 8601 -- all processed in your browser with nothing sent to a server.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <!-- Live Current Timestamp -->
  <div class="ut-live" onclick="utCopyLive()" title="Click to copy current timestamp">
    <div class="ut-live-label">Current Unix Timestamp</div>
    <div class="ut-live-ts" id="utLiveTs">--</div>
    <div class="ut-live-date" id="utLiveDate">--</div>
    <div class="ut-live-hint">Click to copy</div>
  </div>

  <!-- Timestamp → Date -->
  <div class="ut-card">
    <h2><span class="ut-icon">&#128197;</span> Timestamp → Date</h2>
    <div class="ut-input-group">
      <input type="text" id="utTsInput" class="ut-input" placeholder="Enter Unix timestamp (e.g. 1700000000)" inputmode="numeric">
      <button class="ut-btn ut-btn-primary" onclick="utConvertTs()">Convert</button>
      <button class="ut-btn ut-btn-secondary" onclick="utUseNow()">Now</button>
    </div>
    <div id="utTsError" class="ut-error"></div>
    <table class="ut-results" id="utTsResults" style="display:none;">
      <tr>
        <td>UTC</td>
        <td><div class="ut-copy-cell"><span id="utResUtc"></span><button class="ut-btn ut-btn-secondary ut-btn-sm" onclick="utCopyVal('utResUtc')">Copy</button></div></td>
      </tr>
      <tr>
        <td>Local Time</td>
        <td><div class="ut-copy-cell"><span id="utResLocal"></span><button class="ut-btn ut-btn-secondary ut-btn-sm" onclick="utCopyVal('utResLocal')">Copy</button></div></td>
      </tr>
      <tr>
        <td>ISO 8601</td>
        <td><div class="ut-copy-cell"><span id="utResIso"></span><button class="ut-btn ut-btn-secondary ut-btn-sm" onclick="utCopyVal('utResIso')">Copy</button></div></td>
      </tr>
      <tr>
        <td>Relative</td>
        <td><span id="utResRelative"></span></td>
      </tr>
      <tr>
        <td>Day of Year</td>
        <td><span id="utResDoy"></span></td>
      </tr>
      <tr>
        <td>Week Number</td>
        <td><span id="utResWeek"></span></td>
      </tr>
    </table>
  </div>

  <!-- Date → Timestamp -->
  <div class="ut-card">
    <h2><span class="ut-icon">&#9201;</span> Date → Timestamp</h2>
    <div class="ut-date-row">
      <div class="ut-field">
        <label for="utYear">Year</label>
        <input type="number" id="utYear" min="1970" max="2099" value="2026">
      </div>
      <div class="ut-field">
        <label for="utMonth">Month</label>
        <select id="utMonth">
          <option value="0">January</option>
          <option value="1">February</option>
          <option value="2" selected>March</option>
          <option value="3">April</option>
          <option value="4">May</option>
          <option value="5">June</option>
          <option value="6">July</option>
          <option value="7">August</option>
          <option value="8">September</option>
          <option value="9">October</option>
          <option value="10">November</option>
          <option value="11">December</option>
        </select>
      </div>
      <div class="ut-field">
        <label for="utDay">Day</label>
        <input type="number" id="utDay" min="1" max="31" value="18">
      </div>
      <div class="ut-field">
        <label for="utHour">Hour</label>
        <input type="number" id="utHour" min="0" max="23" value="0">
      </div>
      <div class="ut-field">
        <label for="utMin">Min</label>
        <input type="number" id="utMin" min="0" max="59" value="0">
      </div>
      <div class="ut-field">
        <label for="utSec">Sec</label>
        <input type="number" id="utSec" min="0" max="59" value="0">
      </div>
      <div class="ut-field">
        <label for="utTz">Timezone</label>
        <select id="utTz">
          <option value="utc" selected>UTC</option>
          <option value="local">Local</option>
        </select>
      </div>
    </div>
    <button class="ut-btn ut-btn-primary" onclick="utConvertDate()">Convert to Timestamp</button>
    <div id="utDateError" class="ut-error"></div>
    <div id="utDateResult" class="ut-result-box" style="display:none;">
      <span id="utDateTs"></span>
      <button class="ut-btn ut-btn-secondary ut-btn-sm" onclick="utCopyVal('utDateTs')">Copy</button>
    </div>
  </div>

  <!-- Common Timestamps Reference -->
  <div class="ut-card">
    <h2><span class="ut-icon">&#128218;</span> Common Timestamps Reference</h2>
    <table class="ut-ref">
      <thead>
        <tr>
          <th>Event</th>
          <th>Timestamp</th>
          <th>Date (UTC)</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Unix Epoch</td>
          <td>0</td>
          <td>Jan 1, 1970 00:00:00</td>
        </tr>
        <tr>
          <td>Billennium</td>
          <td>1000000000</td>
          <td>Sep 9, 2001 01:46:40</td>
        </tr>
        <tr>
          <td>Y2K</td>
          <td>946684800</td>
          <td>Jan 1, 2000 00:00:00</td>
        </tr>
        <tr>
          <td>1.5 Billion</td>
          <td>1500000000</td>
          <td>Jul 14, 2017 02:40:00</td>
        </tr>
        <tr>
          <td>2 Billion</td>
          <td>2000000000</td>
          <td>May 18, 2033 03:33:20</td>
        </tr>
        <tr>
          <td>Max 32-bit (Y2K38)</td>
          <td>2147483647</td>
          <td>Jan 19, 2038 03:14:07</td>
        </tr>
        <tr>
          <td>Max 32-bit unsigned</td>
          <td>4294967295</td>
          <td>Feb 7, 2106 06:28:15</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="ut-meta">
    <span>All conversions happen in your browser -- nothing is sent to a server</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO Content -->
  <div class="ut-content">
    <h2>How Unix Timestamps Work</h2>
    <p>A Unix timestamp (also called epoch time or POSIX time) counts the number of seconds that have elapsed since January 1, 1970, 00:00:00 UTC. This single integer is the standard way computers track time -- every operating system, programming language, and database understands it. When you see a value like <strong>1700000000</strong>, that maps to a precise moment: November 14, 2023 at 22:13:20 UTC.</p>

    <h3>Why developers use Unix timestamps</h3>
    <p>Timestamps avoid timezone ambiguity entirely. A value of 1700000000 means the same instant whether you read it in New York, Tokyo, or London. They sort naturally as integers, take minimal storage (4 or 8 bytes), and compare with simple math -- subtract two timestamps and you get the exact number of seconds between events. This makes them ideal for log files, API responses, database records, and cron scheduling.</p>

    <h3>Seconds vs. milliseconds</h3>
    <p>Most systems store Unix time in seconds (10 digits for dates between 2001 and 2286). JavaScript and Java use milliseconds (13 digits), so you may need to divide by 1000 to get a standard Unix timestamp. This converter handles both -- if you enter a 13-digit number, it recognizes you likely mean milliseconds and converts accordingly.</p>

    <h3>The Year 2038 problem</h3>
    <p>Systems that store Unix time in a signed 32-bit integer will overflow on January 19, 2038 at 03:14:07 UTC, when the timestamp reaches 2,147,483,647. After that, the value wraps to a negative number, causing the date to jump back to December 13, 1901. Most modern systems have moved to 64-bit integers, which pushes the overflow date more than 292 billion years into the future. If you work with embedded systems or legacy codebases, the 2038 problem is worth auditing.</p>

    <h3>Common operations</h3>
    <ul>
      <li><strong>Get current timestamp</strong> -- In JavaScript: <code>Math.floor(Date.now() / 1000)</code>. In Python: <code>import time; int(time.time())</code>. In Bash: <code>date +%s</code>.</li>
      <li><strong>Add one day</strong> -- Add 86400 (60 × 60 × 24 seconds).</li>
      <li><strong>Convert to date</strong> -- In JavaScript: <code>new Date(timestamp * 1000)</code>. In Python: <code>datetime.utcfromtimestamp(ts)</code>.</li>
      <li><strong>Difference between two timestamps</strong> -- Subtract the earlier from the later, then divide by 3600 for hours or 86400 for days.</li>
    </ul>
  </div>

  <!-- FAQ with Schema.org markup -->
  <div class="ut-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="ut-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="utToggleFaq(this)">What is a Unix timestamp?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A Unix timestamp is a single integer representing the number of seconds since January 1, 1970, 00:00:00 UTC -- an instant known as the Unix epoch. Every major programming language and operating system uses this format internally, which makes it the universal way to record when an event occurred. Because it is timezone-neutral, the same number maps to the same moment everywhere in the world.</p>
      </div>
    </div>

    <div class="ut-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="utToggleFaq(this)">How do I convert a Unix timestamp to a readable date?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Paste the numeric timestamp into the converter above and click Convert. You will immediately see the corresponding date and time in UTC, your local timezone, and ISO 8601 format. If you are working in code, multiply the timestamp by 1000 (to get milliseconds) and pass it to your language's Date constructor -- for example, <code>new Date(ts * 1000)</code> in JavaScript or <code>datetime.utcfromtimestamp(ts)</code> in Python.</p>
      </div>
    </div>

    <div class="ut-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="utToggleFaq(this)">Why does my timestamp have 13 digits instead of 10?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A 13-digit timestamp is in milliseconds rather than seconds. JavaScript's Date.now() and Java's System.currentTimeMillis() both return millisecond precision. To convert to a standard 10-digit Unix timestamp, divide by 1000 and drop the decimal. This converter detects 13-digit inputs automatically and handles the conversion for you so you always get the correct date.</p>
      </div>
    </div>

    <div class="ut-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="utToggleFaq(this)">What is the Year 2038 problem?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The Year 2038 problem affects systems that store Unix time in a signed 32-bit integer. The maximum value a signed 32-bit integer can hold is 2,147,483,647, which corresponds to January 19, 2038 at 03:14:07 UTC. One second later the value overflows to a negative number, making the system interpret the date as December 13, 1901. Modern 64-bit systems are not affected -- their integer range extends billions of years. If you maintain legacy 32-bit systems, embedded devices, or file formats with 32-bit timestamps, you should plan a migration before 2038.</p>
      </div>
    </div>

    <div class="ut-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="utToggleFaq(this)">Is my data safe in this converter?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This converter runs entirely in your browser using JavaScript. No data is transmitted to any server -- there are no API calls, no cookies, and no logging. You can verify this by opening your browser's developer tools and checking the Network tab while using the tool. It is safe to convert timestamps from logs, databases, or any other source without privacy concerns.</p>
      </div>
    </div>

    <div class="ut-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="utToggleFaq(this)">Does this tool handle negative timestamps?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Negative Unix timestamps represent dates before the epoch -- before January 1, 1970. For example, -86400 corresponds to December 31, 1969. This converter accepts negative values and will display the correct pre-1970 date in UTC, local time, and ISO 8601 format.</p>
      </div>
    </div>

  </div>

  <div style="margin: 2rem 0; padding: 1rem 1.25rem; background: #f3f0ff; border: 1px solid #6C5CE7; border-radius: 8px;">
<div style="font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.1em; color: #6C5CE7; margin-bottom: 0.5rem; font-weight: 600;">Related Guide</div>
<a href="/guides/creating-a-chrome-extension/" style="color: #1d1d1f; text-decoration: none; font-size: 0.95rem; font-weight: 500;">How to Create a Chrome Extension &rarr;</a>
</div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/cron-expression-generator/" style="color:#00ff88;text-decoration:none;">Cron Expression Generator</a> - Build cron expressions visually</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter/" style="color:#00ff88;text-decoration:none;">JSON Formatter</a> - Format and validate JSON data</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/uuid-generator/" style="color:#00ff88;text-decoration:none;">UUID Generator</a> - Generate random UUID v4 values</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/base64-encoder-decoder/" style="color:#00ff88;text-decoration:none;">Base64 Encoder Decoder</a> - Encode and decode Base64 strings</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>


  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid #2a2a3a; margin-top: 3rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

</div>

<!-- Toast notification -->
<div class="ut-toast" id="utToast"></div>

<script>
(function() {
  "use strict";

  // --- Live Clock ---
  var liveTs = document.getElementById("utLiveTs");
  var liveDate = document.getElementById("utLiveDate");

  function updateLive() {
    var now = Math.floor(Date.now() / 1000);
    liveTs.textContent = now;
    liveDate.textContent = new Date(now * 1000).toUTCString();
  }
  updateLive();
  setInterval(updateLive, 1000);

  // --- Toast ---
  var toastTimer;
  function showToast(msg) {
    var t = document.getElementById("utToast");
    t.textContent = msg;
    t.classList.add("ut-show");
    clearTimeout(toastTimer);
    toastTimer = setTimeout(function() { t.classList.remove("ut-show"); }, 2000);
  }

  // --- Copy helpers ---
  function copyText(text) {
    if (navigator.clipboard && navigator.clipboard.writeText) {
      navigator.clipboard.writeText(text).then(function() {
        showToast("Copied: " + text);
      });
    } else {
      var ta = document.createElement("textarea");
      ta.value = text;
      ta.style.position = "fixed";
      ta.style.left = "-9999px";
      document.body.appendChild(ta);
      ta.select();
      document.execCommand("copy");
      document.body.removeChild(ta);
      showToast("Copied: " + text);
    }
  }

  window.utCopyLive = function() {
    copyText(liveTs.textContent);
  };

  window.utCopyVal = function(id) {
    var el = document.getElementById(id);
    if (el) copyText(el.textContent);
  };

  // --- Timestamp to Date ---
  window.utConvertTs = function() {
    var raw = document.getElementById("utTsInput").value.trim();
    var errEl = document.getElementById("utTsError");
    var resEl = document.getElementById("utTsResults");

    errEl.style.display = "none";
    resEl.style.display = "none";

    if (!raw) {
      errEl.textContent = "Please enter a Unix timestamp.";
      errEl.style.display = "block";
      return;
    }

    var num = Number(raw);
    if (isNaN(num)) {
      errEl.textContent = "Invalid input -- enter a numeric timestamp.";
      errEl.style.display = "block";
      return;
    }

    // Auto-detect milliseconds (13+ digits)
    var ts = num;
    if (Math.abs(num) > 9999999999) {
      ts = Math.floor(num / 1000);
    }

    var d = new Date(ts * 1000);

    if (isNaN(d.getTime())) {
      errEl.textContent = "Timestamp out of range.";
      errEl.style.display = "block";
      return;
    }

    document.getElementById("utResUtc").textContent = d.toUTCString();
    document.getElementById("utResLocal").textContent = d.toString();
    document.getElementById("utResIso").textContent = d.toISOString();
    document.getElementById("utResRelative").textContent = relativeTime(ts);
    document.getElementById("utResDoy").textContent = dayOfYear(d);
    document.getElementById("utResWeek").textContent = weekNumber(d);

    resEl.style.display = "table";
  };

  window.utUseNow = function() {
    document.getElementById("utTsInput").value = Math.floor(Date.now() / 1000);
    window.utConvertTs();
  };

  // --- Date to Timestamp ---
  window.utConvertDate = function() {
    var y = parseInt(document.getElementById("utYear").value, 10);
    var mo = parseInt(document.getElementById("utMonth").value, 10);
    var day = parseInt(document.getElementById("utDay").value, 10);
    var h = parseInt(document.getElementById("utHour").value, 10);
    var mi = parseInt(document.getElementById("utMin").value, 10);
    var s = parseInt(document.getElementById("utSec").value, 10);
    var tz = document.getElementById("utTz").value;
    var errEl = document.getElementById("utDateError");
    var resEl = document.getElementById("utDateResult");

    errEl.style.display = "none";
    resEl.style.display = "none";

    if (isNaN(y) || isNaN(mo) || isNaN(day) || isNaN(h) || isNaN(mi) || isNaN(s)) {
      errEl.textContent = "Please fill in all date fields.";
      errEl.style.display = "block";
      return;
    }

    var d;
    if (tz === "utc") {
      d = new Date(Date.UTC(y, mo, day, h, mi, s));
    } else {
      d = new Date(y, mo, day, h, mi, s);
    }

    if (isNaN(d.getTime())) {
      errEl.textContent = "Invalid date.";
      errEl.style.display = "block";
      return;
    }

    var ts = Math.floor(d.getTime() / 1000);
    document.getElementById("utDateTs").textContent = ts;
    resEl.style.display = "flex";
  };

  // --- Relative time ---
  function relativeTime(ts) {
    var now = Math.floor(Date.now() / 1000);
    var diff = now - ts;
    var abs = Math.abs(diff);
    var suffix = diff >= 0 ? " ago" : " from now";

    if (abs < 60) return abs + " second" + (abs !== 1 ? "s" : "") + suffix;
    if (abs < 3600) { var m = Math.floor(abs / 60); return m + " minute" + (m !== 1 ? "s" : "") + suffix; }
    if (abs < 86400) { var h = Math.floor(abs / 3600); return h + " hour" + (h !== 1 ? "s" : "") + suffix; }
    if (abs < 2592000) { var d = Math.floor(abs / 86400); return d + " day" + (d !== 1 ? "s" : "") + suffix; }
    if (abs < 31536000) { var mo = Math.floor(abs / 2592000); return mo + " month" + (mo !== 1 ? "s" : "") + suffix; }
    var y = Math.floor(abs / 31536000);
    return y + " year" + (y !== 1 ? "s" : "") + suffix;
  }

  // --- Day of year ---
  function dayOfYear(d) {
    var start = new Date(d.getUTCFullYear(), 0, 0);
    var diff = d - start;
    var oneDay = 86400000;
    return Math.floor(diff / oneDay);
  }

  // --- ISO week number ---
  function weekNumber(d) {
    var date = new Date(Date.UTC(d.getUTCFullYear(), d.getUTCMonth(), d.getUTCDate()));
    date.setUTCDate(date.getUTCDate() + 4 - (date.getUTCDay() || 7));
    var yearStart = new Date(Date.UTC(date.getUTCFullYear(), 0, 1));
    return Math.ceil((((date - yearStart) / 86400000) + 1) / 7);
  }

  // --- FAQ toggle ---
  window.utToggleFaq = function(el) {
    var item = el.parentElement;
    item.classList.toggle("ut-open");
  };

  // --- Enter key support ---
  document.getElementById("utTsInput").addEventListener("keydown", function(e) {
    if (e.key === "Enter") window.utConvertTs();
  });

  // --- Set default date fields to today ---
  var now = new Date();
  document.getElementById("utYear").value = now.getUTCFullYear();
  document.getElementById("utMonth").value = now.getUTCMonth();
  document.getElementById("utDay").value = now.getUTCDate();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Unix Timestamp Converter",
      "url": "https://theluckystrike.github.io/tools/unix-timestamp-converter/",
      "applicationCategory": "DeveloperApplication",
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
        { "@type": "ListItem", "position": 3, "name": "Unix Timestamp Converter", "item": "https://theluckystrike.github.io/tools/unix-timestamp-converter/" }
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
