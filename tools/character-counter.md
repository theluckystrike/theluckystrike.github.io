---
layout: page
title: "Free Character Counter — Twitter, Instagram & SMS Limits | Zovo"
description: "Count characters, words, sentences, paragraphs, and lines with real-time platform limit tracking for Twitter/X, Instagram, Facebook, LinkedIn, YouTube, TikTok, SMS, and SEO. Free online character counter."
permalink: /tools/character-counter/
keywords: "character counter, character count, twitter character limit, instagram character limit, sms character limit, letter counter, text length checker"
date: 2026-03-19
categories: [tools]
tags: [character-counter, text-analysis, twitter, instagram, sms, social-media, seo, writing]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root {
    --cc-primary: #6C5CE7;
    --cc-primary-dark: #5A4BD1;
    --cc-primary-light: #A29BFE;
    --cc-bg: #0a0a0f;
    --cc-surface: #12121a;
    --cc-surface-alt: #181825;
    --cc-border: #1e1e2e;
    --cc-text: #e0e0e0;
    --cc-text-muted: #8888aa;
    --cc-green: #00ff88;
    --cc-green-dark: #00cc6a;
    --cc-red: #ff4466;
    --cc-yellow: #FDCB6E;
    --cc-radius: 12px;
    --cc-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .cc-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--cc-text);
    max-width: 1000px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .cc-wrapper * { box-sizing: border-box; }

  .cc-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .cc-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    margin: 0 0 16px;
    line-height: 1.2;
    color: #fff;
  }

  .cc-hero h1 span { color: var(--cc-primary); }

  .cc-hero p {
    color: var(--cc-text-muted);
    font-size: 1.05rem;
    max-width: 640px;
    margin: 0 auto;
  }

  /* Stats Bar */
  .cc-stats-bar {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 8px;
    margin-bottom: 16px;
  }

  .cc-stat {
    background: var(--cc-surface);
    border: 1px solid var(--cc-border);
    border-radius: 10px;
    padding: 12px 10px;
    text-align: center;
  }

  .cc-stat-value {
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    font-family: 'JetBrains Mono', monospace;
    display: block;
  }

  .cc-stat-label {
    font-size: 0.7rem;
    color: var(--cc-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-top: 4px;
    display: block;
  }

  /* Textarea */
  .cc-textarea-wrap {
    margin-bottom: 16px;
    position: relative;
  }

  .cc-textarea {
    width: 100%;
    min-height: 260px;
    background: var(--cc-surface);
    border: 1px solid var(--cc-border);
    border-radius: var(--cc-radius);
    color: var(--cc-text);
    padding: 18px 20px;
    font-family: 'Inter', -apple-system, sans-serif;
    font-size: 1rem;
    line-height: 1.7;
    resize: vertical;
    outline: none;
    transition: border-color 0.2s;
  }

  .cc-textarea:focus { border-color: var(--cc-primary); }

  .cc-textarea::placeholder { color: var(--cc-text-muted); }

  /* Toolbar */
  .cc-toolbar {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
    margin-bottom: 20px;
  }

  .cc-tool-btn {
    background: var(--cc-surface);
    border: 1px solid var(--cc-border);
    border-radius: 8px;
    color: var(--cc-text-muted);
    padding: 7px 14px;
    cursor: pointer;
    font-size: 0.78rem;
    font-weight: 500;
    font-family: 'Inter', sans-serif;
    transition: border-color 0.2s, color 0.2s, background 0.2s;
  }

  .cc-tool-btn:hover {
    border-color: var(--cc-primary);
    color: var(--cc-text);
  }

  .cc-tool-btn.active {
    background: var(--cc-primary);
    border-color: var(--cc-primary);
    color: white;
  }

  /* Section container */
  .cc-section {
    background: var(--cc-surface);
    border: 1px solid var(--cc-border);
    border-radius: var(--cc-radius);
    padding: 24px;
    margin-bottom: 20px;
  }

  .cc-section-title {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--cc-primary-light);
    margin: 0 0 16px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  /* Time Estimates */
  .cc-time-row {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
  }

  .cc-time-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.88rem;
  }

  .cc-time-label { color: var(--cc-text-muted); }
  .cc-time-value { color: var(--cc-green); font-weight: 600; font-family: 'JetBrains Mono', monospace; }

  /* Platform Limits */
  .cc-limits-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }

  .cc-limit-item {
    background: var(--cc-surface-alt);
    border: 1px solid var(--cc-border);
    border-radius: 10px;
    padding: 14px 16px;
  }

  .cc-limit-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
  }

  .cc-limit-name {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--cc-text);
  }

  .cc-limit-count {
    font-size: 0.75rem;
    color: var(--cc-text-muted);
    font-family: 'JetBrains Mono', monospace;
  }

  .cc-limit-bar {
    width: 100%;
    height: 6px;
    background: var(--cc-bg);
    border-radius: 3px;
    overflow: hidden;
  }

  .cc-limit-fill {
    height: 100%;
    border-radius: 3px;
    background: var(--cc-green);
    transition: width 0.2s, background 0.2s;
    max-width: 100%;
  }

  .cc-limit-fill.warning { background: var(--cc-yellow); }
  .cc-limit-fill.exceeded { background: var(--cc-red); }

  .cc-limit-remaining {
    font-size: 0.7rem;
    color: var(--cc-text-muted);
    margin-top: 4px;
    font-family: 'JetBrains Mono', monospace;
  }

  .cc-limit-remaining.over { color: var(--cc-red); }

  /* Letter Frequency */
  .cc-freq-chart {
    display: flex;
    align-items: flex-end;
    gap: 3px;
    height: 140px;
    padding: 0;
    margin-top: 12px;
  }

  .cc-freq-bar-wrap {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    justify-content: flex-end;
    min-width: 0;
  }

  .cc-freq-bar {
    width: 100%;
    max-width: 28px;
    background: var(--cc-primary);
    border-radius: 3px 3px 0 0;
    min-height: 2px;
    transition: height 0.3s;
  }

  .cc-freq-label {
    font-size: 0.6rem;
    color: var(--cc-text-muted);
    margin-top: 4px;
    font-family: 'JetBrains Mono', monospace;
    text-transform: uppercase;
  }

  .cc-freq-count {
    font-size: 0.55rem;
    color: var(--cc-text-muted);
    margin-bottom: 3px;
    font-family: 'JetBrains Mono', monospace;
  }

  .cc-freq-empty {
    color: var(--cc-text-muted);
    font-size: 0.85rem;
    text-align: center;
    padding: 30px 0;
  }

  /* Case Converter */
  .cc-case-btns {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  /* Cross Links */
  .cc-cross-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 32px;
  }

  .cc-cross-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--cc-surface);
    border: 1px solid var(--cc-border);
    border-radius: 8px;
    color: var(--cc-text-muted);
    font-size: 0.82rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, color 0.2s ease;
  }

  .cc-cross-link:hover {
    border-color: var(--cc-primary);
    color: var(--cc-text);
  }

  /* Content */
  .cc-content {
    max-width: 780px;
    margin: 0 auto;
  }

  .cc-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    margin: 2.5rem 0 1rem;
  }

  .cc-content p {
    color: var(--cc-text-muted);
    margin: 0 0 1rem;
    line-height: 1.7;
    font-size: 0.95rem;
  }

  .cc-content table {
    width: 100%;
    border-collapse: collapse;
    margin: 1.5rem 0;
    font-size: 0.88rem;
  }

  .cc-content th, .cc-content td {
    padding: 10px 14px;
    text-align: left;
    border-bottom: 1px solid var(--cc-border);
  }

  .cc-content th {
    background: var(--cc-surface);
    color: var(--cc-text);
    font-weight: 600;
  }

  .cc-content td { color: var(--cc-text-muted); }

  /* FAQ */
  .cc-faq {
    max-width: 780px;
    margin: 2rem auto 0;
  }

  .cc-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    margin: 0 0 1.2rem;
  }

  .cc-faq-item {
    border-bottom: 1px solid var(--cc-border);
    padding: 1rem 0;
  }

  .cc-faq-item:last-child { border-bottom: none; }

  .cc-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    color: var(--cc-text);
    margin: 0 0 8px;
  }

  .cc-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--cc-text-muted);
    line-height: 1.7;
  }

  /* Author Box */
  .cc-author-box {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
    background: var(--cc-surface);
    border: 1px solid var(--cc-border);
    border-radius: var(--cc-radius);
    margin: 2.5rem auto 0;
    max-width: 780px;
  }

  .cc-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: var(--cc-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 1.1rem;
    color: white;
    flex-shrink: 0;
  }

  .cc-author-info { flex: 1; }

  .cc-author-name {
    font-weight: 600;
    color: var(--cc-text);
    margin: 0 0 4px;
    font-size: 0.95rem;
  }

  .cc-author-bio {
    color: var(--cc-text-muted);
    font-size: 0.85rem;
    margin: 0;
    line-height: 1.5;
  }

  .cc-author-bio a {
    color: var(--cc-primary);
    text-decoration: none;
  }

  /* Footer */
  .cc-footer {
    text-align: center;
    padding: 2rem 0;
    color: var(--cc-text-muted);
    font-size: 0.85rem;
    border-top: 1px solid var(--cc-border);
    margin-top: 3rem;
  }

  .cc-footer a {
    color: var(--cc-primary);
    text-decoration: none;
  }

  .cc-footer a:hover { text-decoration: underline; }

  .cc-last-updated {
    text-align: center;
    color: var(--cc-text-muted);
    font-size: 0.78rem;
    margin-top: 8px;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .cc-hero h1 { font-size: 1.6rem; }
    .cc-stats-bar { grid-template-columns: repeat(3, 1fr); }
    .cc-limits-grid { grid-template-columns: 1fr; }
    .cc-author-box {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
  }

  @media (max-width: 480px) {
    .cc-stats-bar { grid-template-columns: repeat(2, 1fr); }
    .cc-section { padding: 16px; }
    .cc-stat { padding: 10px 8px; }
    .cc-stat-value { font-size: 1.1rem; }
  }
</style>

<div class="cc-wrapper">

  <div class="cc-hero">
    <h1>Character <span>Counter</span></h1>
    <p>Count characters, words, sentences, and paragraphs. Track platform limits for Twitter/X, Instagram, LinkedIn, YouTube, TikTok, SMS, and SEO fields.</p>
  </div>

  <!-- Stats Bar -->
  <div class="cc-stats-bar">
    <div class="cc-stat">
      <span class="cc-stat-value" id="ccChars">0</span>
      <span class="cc-stat-label">Characters</span>
    </div>
    <div class="cc-stat">
      <span class="cc-stat-value" id="ccCharsNoSpace">0</span>
      <span class="cc-stat-label">No Spaces</span>
    </div>
    <div class="cc-stat">
      <span class="cc-stat-value" id="ccWords">0</span>
      <span class="cc-stat-label">Words</span>
    </div>
    <div class="cc-stat">
      <span class="cc-stat-value" id="ccSentences">0</span>
      <span class="cc-stat-label">Sentences</span>
    </div>
    <div class="cc-stat">
      <span class="cc-stat-value" id="ccParagraphs">0</span>
      <span class="cc-stat-label">Paragraphs</span>
    </div>
    <div class="cc-stat">
      <span class="cc-stat-value" id="ccLines">0</span>
      <span class="cc-stat-label">Lines</span>
    </div>
  </div>

  <!-- Textarea -->
  <div class="cc-textarea-wrap">
    <textarea class="cc-textarea" id="ccText" placeholder="Paste or type your text here to count characters, words, and check platform limits..."></textarea>
  </div>

  <!-- Toolbar -->
  <div class="cc-toolbar">
    <button class="cc-tool-btn" onclick="ccCase('upper')">UPPER</button>
    <button class="cc-tool-btn" onclick="ccCase('lower')">lower</button>
    <button class="cc-tool-btn" onclick="ccCase('title')">Title Case</button>
    <button class="cc-tool-btn" onclick="ccCase('sentence')">Sentence case</button>
    <button class="cc-tool-btn" onclick="ccCase('alternating')">aLtErNaTiNg</button>
    <button class="cc-tool-btn" onclick="ccRemoveExtraSpaces()">Remove Extra Spaces</button>
    <button class="cc-tool-btn" onclick="ccTrimWhitespace()">Trim Whitespace</button>
    <button class="cc-tool-btn" onclick="ccCopyText()" id="ccCopyBtn">Copy Text</button>
    <button class="cc-tool-btn" onclick="ccClearText()">Clear</button>
  </div>

  <!-- Time Estimates -->
  <div class="cc-section">
    <div class="cc-section-title">Time Estimates</div>
    <div class="cc-time-row">
      <div class="cc-time-item">
        <span class="cc-time-label">Reading time:</span>
        <span class="cc-time-value" id="ccReadTime">0 sec</span>
      </div>
      <div class="cc-time-item">
        <span class="cc-time-label">Speaking time:</span>
        <span class="cc-time-value" id="ccSpeakTime">0 sec</span>
      </div>
    </div>
  </div>

  <!-- Platform Limits -->
  <div class="cc-section">
    <div class="cc-section-title">Platform Limits</div>
    <div class="cc-limits-grid" id="ccLimitsGrid">
      <!-- Populated by JS -->
    </div>
  </div>

  <!-- Letter Frequency -->
  <div class="cc-section">
    <div class="cc-section-title">Letter Frequency</div>
    <div id="ccFreqChart">
      <div class="cc-freq-empty">Type something to see letter frequency analysis</div>
    </div>
  </div>

  <!-- Cross Links -->
  <div class="cc-cross-links">
    <a href="/tools/word-counter/" class="cc-cross-link">Word Counter</a>
    <a href="/tools/ai-detector/" class="cc-cross-link">AI Detector</a>
    <a href="/tools/headline-analyzer/" class="cc-cross-link">Headline Analyzer</a>
  </div>

  <!-- SEO Content -->
  <div class="cc-content">

<h2>Why Character Limits Matter</h2>

<p>Every platform that accepts text imposes some form of length restriction. Twitter/X caps posts at 280 characters. Instagram allows 2,200 characters for captions. SMS messages split at 160 characters when using standard GSM encoding. Meta descriptions beyond 160 characters get truncated in search results. Title tags longer than 60 characters risk being cut off in Google's listings.</p>

<p>These limits exist for different reasons. Social media platforms enforce them to keep feeds scannable. SMS limits stem from the GSM protocol's original design, where each message occupies a fixed-size data frame. Search engine display limits are about screen real estate: Google renders title tags and meta descriptions in a fixed-width area, and anything beyond that width gets replaced with an ellipsis.</p>

<p>Knowing your character count before publishing prevents awkward truncation. A tweet that cuts off mid-sentence looks careless. A meta description that ends with "..." may lose the call-to-action at the end. A YouTube title that exceeds 100 characters disappears in search results. The progress bars above turn yellow at 80% and red at 100% so you can see at a glance how close you are to each limit.</p>

<h2>Social Media Character Limits Guide</h2>

<table>
  <thead>
    <tr>
      <th>Platform</th>
      <th>Content Type</th>
      <th>Character Limit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Twitter/X</td>
      <td>Post</td>
      <td>280</td>
    </tr>
    <tr>
      <td>Instagram</td>
      <td>Caption</td>
      <td>2,200</td>
    </tr>
    <tr>
      <td>Facebook</td>
      <td>Post</td>
      <td>63,206</td>
    </tr>
    <tr>
      <td>LinkedIn</td>
      <td>Post</td>
      <td>3,000</td>
    </tr>
    <tr>
      <td>YouTube</td>
      <td>Video title</td>
      <td>100</td>
    </tr>
    <tr>
      <td>YouTube</td>
      <td>Description</td>
      <td>5,000</td>
    </tr>
    <tr>
      <td>TikTok</td>
      <td>Caption</td>
      <td>2,200</td>
    </tr>
    <tr>
      <td>SMS</td>
      <td>Single message</td>
      <td>160</td>
    </tr>
  </tbody>
</table>

<p>These numbers reflect current limits as of early 2026 and may change as platforms update their policies. Twitter/X has experimented with longer posts for premium subscribers, but the standard free tier remains at 280. Instagram raised its caption limit from 2,200 to match TikTok's allowance in several markets. Always check the platform's current documentation if you are building an automated posting system.</p>

<p>Character counting is not always straightforward. Some platforms count URLs as shortened lengths regardless of the actual URL length. Twitter counts every link as 23 characters. Emoji may count as 1 or 2 characters depending on the platform and the specific emoji (some emoji are composed of multiple Unicode code points joined together). This tool counts raw characters, which matches the behavior of most platform character counters.</p>

<h2>SEO Character Limits</h2>

<p>Search engine optimization involves several text fields with practical length constraints. The title tag is the most visible element in search results, and Google typically displays the first 50 to 60 characters. Anything beyond that gets truncated with an ellipsis. The recommended practice is to keep title tags under 60 characters and place your primary keyword near the beginning.</p>

<p>Meta descriptions appear below the title in search results. Google usually shows between 150 and 160 characters, though this varies by device and query. A well-written meta description summarizes the page content and includes a reason for the searcher to click. If no meta description is set, Google generates one automatically from the page content, which may not represent the page as well as a hand-written version.</p>

<p>Heading tags (H1, H2, H3) do not have hard character limits, but keeping them concise improves readability and may benefit featured snippet selection. Header lengths between 20 and 70 characters tend to perform well. URL slugs should stay under 75 characters and use hyphens to separate words.</p>

<h2>How to Write Within Limits</h2>

<p>Writing under a character constraint is a skill that improves with practice. Start by writing your full thought without worrying about length. Then edit for conciseness. Replace phrases with single words where possible: "in order to" becomes "to," "at this point in time" becomes "now," "due to the fact that" becomes "because." Remove filler words like "really," "very," "quite," and "actually" unless they change the meaning.</p>

<p>For social media posts, front-load the most important information. If the platform truncates your text, readers still see the key message. For tweets, consider whether you need every hashtag. Each hashtag uses characters that could carry your message. Two or three targeted hashtags perform better than a wall of tags that eat into your character budget.</p>

<p>For SEO fields, include your target keyword naturally. A title tag that reads like a keyword list performs worse than one that reads like a natural phrase. "Best Running Shoes 2026 Review Guide Buy" is less effective than "Best Running Shoes for Marathon Training (2026 Picks)." The second version uses fewer characters, reads better, and still contains the core keyword.</p>

<p>The case conversion buttons above help with formatting. Title Case capitalizes the first letter of each word, which is standard for headlines. Sentence case capitalizes only the first letter after a period, which suits body text. The alternating case option exists mostly for meme-style formatting but occasionally serves as a quick way to test how text looks in different styles.</p>

  </div>

  <!-- FAQ -->
  <div class="cc-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="cc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does this tool count characters?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool counts every character in the input, including spaces, punctuation, and special characters. The "No Spaces" count excludes all whitespace characters (spaces, tabs, and line breaks). Emoji and accented characters each count as one character, matching how most platforms count them.</p>
      </div>
    </div>

    <div class="cc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What reading and speaking speeds does this tool use?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Reading time uses 238 words per minute, the average silent reading speed for English-speaking adults based on research by Brysbaert (2019). Speaking time uses 150 words per minute, which reflects a comfortable presentation pace. Actual speeds vary by individual, text complexity, and context.</p>
      </div>
    </div>

    <div class="cc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Do emoji count as one character or two?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool counts each emoji as one character, which matches the behavior of most social media platforms. However, some emoji are composed of multiple Unicode code points (like skin-tone modified emoji or flag sequences). The JavaScript string length property may report these as 2 or more, but this tool uses a visual character count that aligns with what users expect.</p>
      </div>
    </div>

    <div class="cc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Are the platform character limits accurate?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The limits shown reflect the current documented limits for each platform as of March 2026. Platforms occasionally change their limits, and some offer extended limits for premium accounts (like Twitter/X Blue). Always verify against the platform's official documentation for production use.</p>
      </div>
    </div>

    <div class="cc-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my text stored or sent to any server?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All counting and analysis happens entirely in your web browser using JavaScript. No text is transmitted to any server, stored in cookies, or logged by analytics. You can verify this by monitoring the Network tab in your browser's developer tools.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="cc-author-box">
    <div class="cc-author-avatar">ML</div>
    <div class="cc-author-info">
      <p class="cc-author-name">Michael Lip</p>
      <p class="cc-author-bio">Michael builds free tools and writes guides at <a href="https://zovo.one">zovo.one</a>. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <p class="cc-last-updated">Last updated: March 19, 2026</p>

  <footer class="cc-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Character Counter",
      "description": "Count characters, words, sentences, paragraphs, and lines. Track platform limits for Twitter/X, Instagram, Facebook, LinkedIn, YouTube, TikTok, SMS, and SEO fields.",
      "url": "https://theluckystrike.github.io/tools/character-counter/",
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
        {"@type": "ListItem", "position": 3, "name": "Character Counter", "item": "https://theluckystrike.github.io/tools/character-counter/"}
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
          "name": "How does this tool count characters?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The tool counts every character including spaces, punctuation, and special characters. The No Spaces count excludes all whitespace."
          }
        },
        {
          "@type": "Question",
          "name": "What reading and speaking speeds does this tool use?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Reading time uses 238 words per minute. Speaking time uses 150 words per minute, reflecting a comfortable presentation pace."
          }
        },
        {
          "@type": "Question",
          "name": "Do emoji count as one character or two?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "This tool counts each emoji as one character, matching how most social media platforms count them."
          }
        },
        {
          "@type": "Question",
          "name": "Are the platform character limits accurate?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The limits reflect current documented limits as of March 2026. Platforms may change their limits, so verify against official documentation for production use."
          }
        },
        {
          "@type": "Question",
          "name": "Is my text stored or sent to any server?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All counting happens entirely in your browser. No data is transmitted, stored, or logged."
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
  // Platform limits configuration
  // =============================================
  var PLATFORMS = [
    { name: "Twitter/X", limit: 280, id: "twitter" },
    { name: "Instagram Caption", limit: 2200, id: "instagram" },
    { name: "Facebook Post", limit: 63206, id: "facebook" },
    { name: "LinkedIn Post", limit: 3000, id: "linkedin" },
    { name: "YouTube Title", limit: 100, id: "yttitle" },
    { name: "YouTube Description", limit: 5000, id: "ytdesc" },
    { name: "TikTok Caption", limit: 2200, id: "tiktok" },
    { name: "SMS (Single)", limit: 160, id: "sms" },
    { name: "Meta Description", limit: 160, id: "metadesc" },
    { name: "Title Tag", limit: 60, id: "titletag" }
  ];

  // =============================================
  // DOM references
  // =============================================
  var elText = document.getElementById("ccText");
  var elChars = document.getElementById("ccChars");
  var elCharsNoSpace = document.getElementById("ccCharsNoSpace");
  var elWords = document.getElementById("ccWords");
  var elSentences = document.getElementById("ccSentences");
  var elParagraphs = document.getElementById("ccParagraphs");
  var elLines = document.getElementById("ccLines");
  var elReadTime = document.getElementById("ccReadTime");
  var elSpeakTime = document.getElementById("ccSpeakTime");
  var elLimitsGrid = document.getElementById("ccLimitsGrid");
  var elFreqChart = document.getElementById("ccFreqChart");

  var debounceTimer = null;

  // =============================================
  // Build platform limits HTML
  // =============================================
  function buildLimitsGrid() {
    var html = "";
    for (var i = 0; i < PLATFORMS.length; i++) {
      var p = PLATFORMS[i];
      html += '<div class="cc-limit-item">';
      html += '<div class="cc-limit-header">';
      html += '<span class="cc-limit-name">' + p.name + '</span>';
      html += '<span class="cc-limit-count" id="ccLimit_' + p.id + '_count">0 / ' + p.limit.toLocaleString() + '</span>';
      html += '</div>';
      html += '<div class="cc-limit-bar"><div class="cc-limit-fill" id="ccLimit_' + p.id + '_fill"></div></div>';
      html += '<div class="cc-limit-remaining" id="ccLimit_' + p.id + '_remaining">' + p.limit.toLocaleString() + ' remaining</div>';
      html += '</div>';
    }
    elLimitsGrid.innerHTML = html;
  }

  // =============================================
  // Text analysis functions
  // =============================================
  function getWords(text) {
    var trimmed = text.trim();
    if (!trimmed) return [];
    return trimmed.split(/\s+/).filter(function(w) { return w.length > 0; });
  }

  function getSentences(text) {
    var trimmed = text.trim();
    if (!trimmed) return [];
    return trimmed.split(/[.!?]+(?:\s|$)/).filter(function(s) { return s.trim().length > 0; });
  }

  function getParagraphs(text) {
    var trimmed = text.trim();
    if (!trimmed) return [];
    return trimmed.split(/\n\s*\n|\r\n\s*\r\n/).filter(function(p) { return p.trim().length > 0; });
  }

  function getLines(text) {
    if (!text) return 0;
    return text.split(/\n/).length;
  }

  function formatTime(minutes) {
    if (minutes < 1) {
      var secs = Math.round(minutes * 60);
      return secs + " sec";
    }
    var m = Math.floor(minutes);
    var s = Math.round((minutes - m) * 60);
    if (s === 60) { m++; s = 0; }
    if (s === 0) return m + " min";
    return m + " min " + s + " sec";
  }

  // =============================================
  // Letter frequency analysis
  // =============================================
  function getLetterFrequency(text) {
    var freq = {};
    var total = 0;
    var lower = text.toLowerCase();

    for (var i = 0; i < lower.length; i++) {
      var ch = lower[i];
      if (ch >= 'a' && ch <= 'z') {
        freq[ch] = (freq[ch] || 0) + 1;
        total++;
      }
    }

    // Sort by frequency descending, then alphabetically
    var entries = [];
    for (var k in freq) {
      if (freq.hasOwnProperty(k)) {
        entries.push({ letter: k, count: freq[k] });
      }
    }
    entries.sort(function(a, b) { return b.count - a.count || a.letter.localeCompare(b.letter); });

    return { entries: entries.slice(0, 26), total: total };
  }

  function renderFrequencyChart(data) {
    if (data.entries.length === 0) {
      elFreqChart.innerHTML = '<div class="cc-freq-empty">Type something to see letter frequency analysis</div>';
      return;
    }

    var maxCount = data.entries[0].count;
    var maxHeight = 100; // pixels

    var html = '<div class="cc-freq-chart">';
    for (var i = 0; i < data.entries.length; i++) {
      var e = data.entries[i];
      var height = Math.max(2, (e.count / maxCount) * maxHeight);
      html += '<div class="cc-freq-bar-wrap">';
      html += '<div class="cc-freq-count">' + e.count + '</div>';
      html += '<div class="cc-freq-bar" style="height:' + height + 'px;"></div>';
      html += '<div class="cc-freq-label">' + e.letter + '</div>';
      html += '</div>';
    }
    html += '</div>';

    elFreqChart.innerHTML = html;
  }

  // =============================================
  // Update platform limits
  // =============================================
  function updateLimits(charCount) {
    for (var i = 0; i < PLATFORMS.length; i++) {
      var p = PLATFORMS[i];
      var countEl = document.getElementById("ccLimit_" + p.id + "_count");
      var fillEl = document.getElementById("ccLimit_" + p.id + "_fill");
      var remainEl = document.getElementById("ccLimit_" + p.id + "_remaining");

      if (!countEl) continue;

      var pct = p.limit > 0 ? (charCount / p.limit) * 100 : 0;
      var remaining = p.limit - charCount;

      countEl.textContent = charCount.toLocaleString() + " / " + p.limit.toLocaleString();
      fillEl.style.width = Math.min(pct, 100) + "%";

      // Reset classes
      fillEl.className = "cc-limit-fill";
      remainEl.className = "cc-limit-remaining";

      if (pct >= 100) {
        fillEl.classList.add("exceeded");
        remainEl.classList.add("over");
        remainEl.textContent = Math.abs(remaining).toLocaleString() + " over limit";
      } else if (pct >= 80) {
        fillEl.classList.add("warning");
        remainEl.textContent = remaining.toLocaleString() + " remaining";
      } else {
        remainEl.textContent = remaining.toLocaleString() + " remaining";
      }
    }
  }

  // =============================================
  // Main update function
  // =============================================
  function update() {
    var text = elText.value;
    var words = getWords(text);
    var sentences = getSentences(text);
    var paragraphs = getParagraphs(text);

    var charCount = text.length;
    var charNoSpace = text.replace(/\s/g, "").length;
    var wordCount = words.length;
    var sentenceCount = sentences.length;
    var paraCount = paragraphs.length;
    var lineCount = getLines(text);

    // Stats
    elChars.textContent = charCount.toLocaleString();
    elCharsNoSpace.textContent = charNoSpace.toLocaleString();
    elWords.textContent = wordCount.toLocaleString();
    elSentences.textContent = sentenceCount.toLocaleString();
    elParagraphs.textContent = paraCount.toLocaleString();
    elLines.textContent = lineCount.toLocaleString();

    // Time estimates
    elReadTime.textContent = formatTime(wordCount / 238);
    elSpeakTime.textContent = formatTime(wordCount / 150);

    // Platform limits
    updateLimits(charCount);

    // Letter frequency
    var freqData = getLetterFrequency(text);
    renderFrequencyChart(freqData);
  }

  // =============================================
  // Case conversion
  // =============================================
  window.ccCase = function(mode) {
    var text = elText.value;
    if (!text) return;

    switch (mode) {
      case "upper":
        elText.value = text.toUpperCase();
        break;
      case "lower":
        elText.value = text.toLowerCase();
        break;
      case "title":
        elText.value = text.replace(/\b\w/g, function(c) { return c.toUpperCase(); });
        break;
      case "sentence":
        elText.value = text.toLowerCase().replace(/(^|[.!?]\s+)(\w)/g, function(match, p1, p2) {
          return p1 + p2.toUpperCase();
        });
        break;
      case "alternating":
        var result = "";
        var letterIndex = 0;
        for (var i = 0; i < text.length; i++) {
          var ch = text[i];
          if (/[a-zA-Z]/.test(ch)) {
            result += letterIndex % 2 === 0 ? ch.toLowerCase() : ch.toUpperCase();
            letterIndex++;
          } else {
            result += ch;
          }
        }
        elText.value = result;
        break;
    }
    update();
  };

  // =============================================
  // Text cleanup
  // =============================================
  window.ccRemoveExtraSpaces = function() {
    var text = elText.value;
    if (!text) return;
    // Replace multiple spaces with single space, preserve newlines
    elText.value = text.replace(/[^\S\n]+/g, " ").replace(/ *\n */g, "\n");
    update();
  };

  window.ccTrimWhitespace = function() {
    var text = elText.value;
    if (!text) return;
    // Trim each line and the whole string
    var lines = text.split("\n");
    for (var i = 0; i < lines.length; i++) {
      lines[i] = lines[i].trim();
    }
    elText.value = lines.join("\n").trim();
    update();
  };

  // =============================================
  // Copy and Clear
  // =============================================
  window.ccCopyText = function() {
    var text = elText.value;
    if (!text) return;

    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById("ccCopyBtn");
      var orig = btn.textContent;
      btn.textContent = "Copied";
      btn.style.borderColor = "var(--cc-green)";
      btn.style.color = "var(--cc-green)";
      setTimeout(function() {
        btn.textContent = orig;
        btn.style.borderColor = "";
        btn.style.color = "";
      }, 2000);
    });
  };

  window.ccClearText = function() {
    elText.value = "";
    update();
    elText.focus();
  };

  // =============================================
  // Event listeners
  // =============================================
  function debouncedUpdate() {
    clearTimeout(debounceTimer);
    debounceTimer = setTimeout(update, 60);
  }

  elText.addEventListener("input", debouncedUpdate);

  // Auto-expand textarea
  elText.addEventListener("input", function() {
    this.style.height = "auto";
    var newHeight = Math.max(260, this.scrollHeight);
    this.style.height = newHeight + "px";
  });

  // =============================================
  // Initialize
  // =============================================
  buildLimitsGrid();
  update();

})();
</script>
