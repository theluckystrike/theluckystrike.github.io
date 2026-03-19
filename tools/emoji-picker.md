---
layout: page
title: "Free Emoji Picker — Search, Copy & Browse All Emojis | Zovo"
description: "Search and copy emojis instantly. Browse by category, find emoji names and codes, copy Unicode or shortcodes. Complete emoji reference with 1,800+ emojis for all platforms."
permalink: /tools/emoji-picker/
keywords: "emoji picker, emoji search, copy emoji, emoji keyboard, emoji list, emoji codes, unicode emoji, emoji finder, emoji copy paste"
date: 2026-03-19
categories: [tools]
tags: [emoji, picker, unicode, search, copy, keyboard, text]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
:root {
  --ep-bg: #0a0a0f;
  --ep-surface: #12121a;
  --ep-surface2: #1a1a28;
  --ep-border: #1e1e2e;
  --ep-border-hover: #2e2e44;
  --ep-primary: #6C5CE7;
  --ep-primary-dark: #5A4BD1;
  --ep-primary-light: #8B7CF7;
  --ep-secondary: #00ff88;
  --ep-text: #e0e0e0;
  --ep-text-muted: #8888aa;
  --ep-text-dim: #555570;
  --ep-radius: 10px;
  --ep-radius-sm: 6px;
  --ep-font: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --ep-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
}

.ep-wrap {
  font-family: var(--ep-font);
  color: var(--ep-text);
  max-width: 960px;
  margin: 0 auto;
  padding: 0 16px;
  line-height: 1.6;
}

.ep-wrap * { box-sizing: border-box; }

.ep-hero { text-align: center; padding: 40px 0 24px; }

.ep-hero h1 {
  font-size: 2.2rem;
  font-weight: 700;
  color: var(--ep-text);
  margin: 0 0 14px;
  line-height: 1.2;
}

.ep-hero h1 span { color: var(--ep-primary); }

.ep-intro {
  font-size: 1.02rem;
  color: var(--ep-text-muted);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.7;
}

.ep-updated {
  display: inline-block;
  font-size: 0.75rem;
  color: var(--ep-text-muted);
  margin-top: 12px;
  padding: 4px 12px;
  border: 1px solid var(--ep-border);
  border-radius: 20px;
}

/* Toast */
.ep-toast {
  position: fixed;
  bottom: 24px;
  left: 50%;
  transform: translateX(-50%) translateY(80px);
  background: var(--ep-primary);
  color: #fff;
  padding: 10px 24px;
  border-radius: 8px;
  font-size: 0.9rem;
  font-weight: 500;
  z-index: 9999;
  opacity: 0;
  transition: transform 0.3s ease, opacity 0.3s ease;
  pointer-events: none;
}

.ep-toast.show {
  transform: translateX(-50%) translateY(0);
  opacity: 1;
}

/* Search + Controls */
.ep-controls {
  display: flex;
  gap: 10px;
  margin-bottom: 14px;
  flex-wrap: wrap;
}

.ep-search-box {
  flex: 1;
  min-width: 200px;
  position: relative;
}

.ep-search-box input {
  width: 100%;
  padding: 10px 14px 10px 38px;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: var(--ep-radius);
  color: var(--ep-text);
  font-family: var(--ep-font);
  font-size: 0.95rem;
  outline: none;
  transition: border-color 0.2s;
}

.ep-search-box input:focus { border-color: var(--ep-primary); }

.ep-search-box input::placeholder { color: var(--ep-text-dim); }

.ep-search-box svg {
  position: absolute;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--ep-text-dim);
}

.ep-counter {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 0 14px;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: var(--ep-radius);
  font-size: 0.82rem;
  color: var(--ep-text-muted);
  font-family: var(--ep-mono);
  white-space: nowrap;
}

.ep-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 10px 16px;
  background: var(--ep-primary);
  color: #fff;
  border: none;
  border-radius: var(--ep-radius);
  font-family: var(--ep-font);
  font-size: 0.88rem;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.2s;
  white-space: nowrap;
}

.ep-btn:hover { background: var(--ep-primary-dark); }

.ep-btn-outline {
  background: transparent;
  border: 1px solid var(--ep-border);
  color: var(--ep-text);
}

.ep-btn-outline:hover {
  background: var(--ep-surface);
  border-color: var(--ep-primary);
}

/* Skin tone */
.ep-skin-row {
  display: flex;
  align-items: center;
  gap: 6px;
  margin-bottom: 14px;
}

.ep-skin-label {
  font-size: 0.8rem;
  color: var(--ep-text-muted);
  margin-right: 4px;
}

.ep-skin-btn {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 2px solid transparent;
  cursor: pointer;
  font-size: 1.1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--ep-surface);
  transition: border-color 0.15s, transform 0.15s;
  padding: 0;
}

.ep-skin-btn:hover { transform: scale(1.15); }
.ep-skin-btn.active { border-color: var(--ep-primary); }

/* Category tabs */
.ep-tabs {
  display: flex;
  gap: 4px;
  overflow-x: auto;
  padding-bottom: 4px;
  margin-bottom: 14px;
  -webkit-overflow-scrolling: touch;
}

.ep-tabs::-webkit-scrollbar { height: 4px; }
.ep-tabs::-webkit-scrollbar-track { background: transparent; }
.ep-tabs::-webkit-scrollbar-thumb { background: var(--ep-border); border-radius: 2px; }

.ep-tab {
  padding: 7px 14px;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: 8px;
  color: var(--ep-text-muted);
  font-family: var(--ep-font);
  font-size: 0.82rem;
  font-weight: 500;
  cursor: pointer;
  white-space: nowrap;
  transition: background 0.15s, color 0.15s, border-color 0.15s;
}

.ep-tab:hover { border-color: var(--ep-primary); color: var(--ep-text); }

.ep-tab.active {
  background: var(--ep-primary);
  border-color: var(--ep-primary);
  color: #fff;
}

/* Recently used */
.ep-recent {
  display: none;
  margin-bottom: 16px;
  padding: 12px 16px;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: var(--ep-radius);
}

.ep-recent.visible { display: block; }

.ep-recent-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 8px;
}

.ep-recent-title {
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--ep-text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.ep-recent-clear {
  font-size: 0.75rem;
  color: var(--ep-text-dim);
  background: none;
  border: none;
  cursor: pointer;
  font-family: var(--ep-font);
  padding: 2px 6px;
  border-radius: 4px;
}

.ep-recent-clear:hover { color: var(--ep-text); background: var(--ep-surface2); }

.ep-recent-grid {
  display: flex;
  gap: 4px;
  flex-wrap: wrap;
}

/* Emoji grid */
.ep-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(44px, 1fr));
  gap: 4px;
  margin-bottom: 20px;
  max-height: 480px;
  overflow-y: auto;
  padding: 12px;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: var(--ep-radius);
}

.ep-grid::-webkit-scrollbar { width: 6px; }
.ep-grid::-webkit-scrollbar-track { background: transparent; }
.ep-grid::-webkit-scrollbar-thumb { background: var(--ep-border); border-radius: 3px; }

.ep-emoji {
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
  border-radius: 8px;
  cursor: pointer;
  border: none;
  background: transparent;
  transition: background 0.12s, transform 0.12s;
  padding: 0;
  line-height: 1;
}

.ep-emoji:hover {
  background: var(--ep-surface2);
  transform: scale(1.35);
}

.ep-no-results {
  grid-column: 1 / -1;
  text-align: center;
  padding: 40px 20px;
  color: var(--ep-text-dim);
  font-size: 0.95rem;
}

/* Detail panel */
.ep-detail {
  display: none;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: var(--ep-radius);
  padding: 20px;
  margin-bottom: 20px;
}

.ep-detail.visible { display: block; }

.ep-detail-top {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 16px;
}

.ep-detail-preview {
  font-size: 64px;
  line-height: 1;
  flex-shrink: 0;
}

.ep-detail-info { flex: 1; }

.ep-detail-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--ep-text);
  margin: 0 0 4px;
}

.ep-detail-cat {
  font-size: 0.82rem;
  color: var(--ep-text-muted);
}

.ep-detail-codes {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px;
}

@media (max-width: 500px) {
  .ep-detail-codes { grid-template-columns: 1fr; }
}

.ep-code-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 12px;
  background: var(--ep-bg);
  border: 1px solid var(--ep-border);
  border-radius: var(--ep-radius-sm);
}

.ep-code-label {
  font-size: 0.7rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--ep-text-dim);
  width: 70px;
  flex-shrink: 0;
}

.ep-code-value {
  flex: 1;
  font-family: var(--ep-mono);
  font-size: 0.85rem;
  color: var(--ep-secondary);
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.ep-code-copy {
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: transparent;
  border: 1px solid var(--ep-border);
  border-radius: 4px;
  cursor: pointer;
  color: var(--ep-text-muted);
  padding: 0;
  flex-shrink: 0;
  transition: border-color 0.15s, color 0.15s;
}

.ep-code-copy:hover { border-color: var(--ep-primary); color: var(--ep-primary); }

/* Content sections */
.ep-content {
  margin-top: 48px;
  padding-top: 32px;
  border-top: 1px solid var(--ep-border);
}

.ep-content h2 {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--ep-text);
  margin: 32px 0 12px;
}

.ep-content h2:first-child { margin-top: 0; }

.ep-content p {
  color: var(--ep-text-muted);
  font-size: 0.95rem;
  line-height: 1.75;
  margin: 0 0 14px;
}

.ep-content ul {
  color: var(--ep-text-muted);
  font-size: 0.95rem;
  line-height: 1.75;
  padding-left: 20px;
  margin: 0 0 14px;
}

/* FAQ */
.ep-faq { margin-top: 32px; }

.ep-faq h2 {
  font-size: 1.4rem;
  font-weight: 700;
  margin: 0 0 20px;
  color: var(--ep-text);
}

.ep-faq-item { margin-bottom: 20px; }

.ep-faq-item h3 {
  font-size: 1rem;
  font-weight: 600;
  margin: 0 0 6px;
  color: var(--ep-text);
}

.ep-faq-item p {
  margin: 0;
  color: var(--ep-text-muted);
  font-size: 0.93rem;
  line-height: 1.7;
}

/* Related */
.ep-related {
  margin-top: 2rem;
  padding: 1.5rem;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: 12px;
}

.ep-related h2 {
  color: var(--ep-primary);
  font-size: 1.2rem;
  margin: 0 0 1rem;
}

.ep-related ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.ep-related li { margin-bottom: 0.5rem; }

.ep-related a {
  color: var(--ep-secondary);
  text-decoration: none;
}

.ep-related a:hover { text-decoration: underline; }

/* Author */
.ep-author {
  margin-top: 2rem;
  padding: 1.5rem;
  background: var(--ep-surface);
  border: 1px solid var(--ep-border);
  border-radius: 12px;
  display: flex;
  gap: 1rem;
  align-items: center;
}

.ep-author-avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: var(--ep-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: 700;
  font-size: 1.2rem;
  flex-shrink: 0;
}

.ep-author-name {
  color: var(--ep-text);
  font-weight: 600;
}

.ep-author-bio {
  color: var(--ep-text-muted);
  font-size: 0.85rem;
}

.ep-author a { color: var(--ep-primary); text-decoration: none; }

.ep-footer {
  text-align: center;
  padding: 2rem 0;
  color: var(--ep-text-dim);
  font-size: 0.85rem;
  border-top: 1px solid var(--ep-border);
  margin-top: 3rem;
}

.ep-footer a { color: var(--ep-primary); text-decoration: none; }

@media (max-width: 640px) {
  .ep-hero h1 { font-size: 1.6rem; }
  .ep-grid { max-height: 360px; grid-template-columns: repeat(auto-fill, minmax(40px, 1fr)); }
  .ep-emoji { width: 40px; height: 40px; font-size: 24px; }
  .ep-detail-preview { font-size: 48px; }
  .ep-controls { flex-direction: column; }
}
</style>

<div class="ep-wrap" id="epApp">

<div class="ep-hero">
  <h1><span>Emoji Picker</span> and Search</h1>
  <p class="ep-intro">Search over 500 emojis by name or keyword, click to copy, and get Unicode code points, HTML entities, and shortcodes. Browse by category, pick skin tones, and keep track of your recently used emojis. Everything runs in your browser with zero signups.</p>
  <span class="ep-updated">Last updated: March 2026</span>
</div>

<div class="ep-controls">
  <div class="ep-search-box">
    <svg width="16" height="16" viewBox="0 0 16 16" fill="none"><circle cx="7" cy="7" r="5.5" stroke="currentColor" stroke-width="1.5"/><path d="M11 11l3.5 3.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
    <input type="text" id="epSearch" placeholder="Search emojis by name or keyword..." autocomplete="off">
  </div>
  <span class="ep-counter" id="epCounter">0 / 0</span>
  <button class="ep-btn ep-btn-outline" onclick="epRandom()" title="Random emoji">Random</button>
</div>

<div class="ep-skin-row">
  <span class="ep-skin-label">Skin tone:</span>
  <button class="ep-skin-btn active" data-tone="" onclick="epSetSkin(this)">&#x1F44B;</button>
  <button class="ep-skin-btn" data-tone="&#x1F3FB;" onclick="epSetSkin(this)">&#x1F44B;&#x1F3FB;</button>
  <button class="ep-skin-btn" data-tone="&#x1F3FC;" onclick="epSetSkin(this)">&#x1F44B;&#x1F3FC;</button>
  <button class="ep-skin-btn" data-tone="&#x1F3FD;" onclick="epSetSkin(this)">&#x1F44B;&#x1F3FD;</button>
  <button class="ep-skin-btn" data-tone="&#x1F3FE;" onclick="epSetSkin(this)">&#x1F44B;&#x1F3FE;</button>
  <button class="ep-skin-btn" data-tone="&#x1F3FF;" onclick="epSetSkin(this)">&#x1F44B;&#x1F3FF;</button>
</div>

<div class="ep-tabs" id="epTabs"></div>

<div class="ep-recent" id="epRecent">
  <div class="ep-recent-header">
    <span class="ep-recent-title">Recently Used</span>
    <button class="ep-recent-clear" onclick="epClearRecent()">Clear</button>
  </div>
  <div class="ep-recent-grid" id="epRecentGrid"></div>
</div>

<div class="ep-detail" id="epDetail">
  <div class="ep-detail-top">
    <div class="ep-detail-preview" id="epDetailEmoji"></div>
    <div class="ep-detail-info">
      <p class="ep-detail-name" id="epDetailName"></p>
      <p class="ep-detail-cat" id="epDetailCat"></p>
    </div>
  </div>
  <div class="ep-detail-codes">
    <div class="ep-code-item">
      <span class="ep-code-label">Emoji</span>
      <span class="ep-code-value" id="epCodeEmoji"></span>
      <button class="ep-code-copy" onclick="epCopyVal('epCodeEmoji')" title="Copy"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg></button>
    </div>
    <div class="ep-code-item">
      <span class="ep-code-label">Unicode</span>
      <span class="ep-code-value" id="epCodeUnicode"></span>
      <button class="ep-code-copy" onclick="epCopyVal('epCodeUnicode')" title="Copy"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg></button>
    </div>
    <div class="ep-code-item">
      <span class="ep-code-label">HTML</span>
      <span class="ep-code-value" id="epCodeHTML"></span>
      <button class="ep-code-copy" onclick="epCopyVal('epCodeHTML')" title="Copy"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg></button>
    </div>
    <div class="ep-code-item">
      <span class="ep-code-label">Shortcode</span>
      <span class="ep-code-value" id="epCodeShort"></span>
      <button class="ep-code-copy" onclick="epCopyVal('epCodeShort')" title="Copy"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><rect x="5" y="5" width="9" height="9" rx="1.5" stroke="currentColor" stroke-width="1.5"/><path d="M3.5 11V3.5a1 1 0 011-1H11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg></button>
    </div>
  </div>
</div>

<div class="ep-grid" id="epGrid"></div>

<div id="epToast" class="ep-toast"></div>

<!-- Content -->
<div class="ep-content">

<h2>What Are Emojis</h2>
<p>Emojis are small pictographic symbols used in digital text to convey emotions, objects, concepts, and ideas. They originated in Japanese mobile phone culture in the late 1990s when engineer Shigetaka Kurita designed a set of 176 symbols for the NTT DoCoMo i-mode platform. The word "emoji" comes from the Japanese "e" (picture) and "moji" (character). Unlike emoticons, which are typed from standard keyboard characters like :-), emojis are actual graphical characters defined in the Unicode standard.</p>
<p>The Unicode Consortium maintains the official emoji list, adding new symbols with each annual release. As of Unicode 15.1, there are over 3,600 defined emojis when you include skin tone and gender variations. Every major operating system, browser, and messaging app renders these Unicode code points with its own visual style, which is why the same emoji can look slightly different on an iPhone versus an Android device or in a Slack message versus a tweet.</p>

<h2>How Unicode Emojis Work</h2>
<p>Each emoji is assigned a unique code point (or sequence of code points) in the Unicode standard. For example, the grinning face is U+1F600. When you type or paste this character, your device looks up the code point and renders the corresponding glyph from its emoji font. Some emojis use Zero Width Joiner (ZWJ) sequences to combine multiple code points into a single visual character. The family emoji, for instance, joins individual person emojis with ZWJ characters.</p>
<p>Skin tone modifiers work through a similar mechanism. The five Fitzpatrick skin tone modifiers (U+1F3FB through U+1F3FF) can follow any human emoji to change its default yellow appearance. Not all emojis support skin tones; only those depicting human body parts or people accept these modifiers. If a platform does not support a particular modifier, it typically falls back to displaying the base emoji followed by a colored square.</p>
<p>HTML entities provide another way to include emojis in web pages. You can use decimal entities like &amp;#128512; or hexadecimal entities like &amp;#x1F600; to insert emojis directly into HTML source code without needing the actual Unicode character in your file. Shortcodes like :grinning: are a convention used by platforms such as GitHub, Slack, and Discord to let users type emoji names that get converted to the corresponding Unicode character on display.</p>

<h2>Emoji Categories Explained</h2>
<p>The Unicode Consortium organizes emojis into several top-level categories. Smileys and Emotion covers facial expressions, hand gestures, and hearts. People and Body includes human figures, families, and body parts with skin tone support. Animals and Nature contains mammals, birds, insects, plants, and weather symbols. Food and Drink ranges from fruits and vegetables to prepared meals and beverages.</p>
<p>Travel and Places encompasses vehicles, buildings, landmarks, and geographic features. Activities covers sports, arts, events, and games. Objects includes everyday items like tools, office supplies, clothing, and technology. Symbols contains arrows, warning signs, zodiac symbols, and mathematical operators. Flags includes country flags, regional flags, and specialty flags like the rainbow and pirate flags.</p>
<p>This picker groups emojis into these standard categories so you can browse systematically. The search function also indexes keywords beyond the official name, so searching "happy" will surface the grinning face, smiling face with open mouth, and several other relevant results even though "happy" is not in every one of their official names.</p>

<h2>Using Emojis in Marketing and Social Media</h2>
<p>Emojis have become a standard part of social media communication. Studies from Hootsuite and Sprout Social indicate that posts containing emojis tend to receive higher engagement rates on Instagram, Twitter/X, and Facebook. Subject lines with emojis in email marketing can increase open rates by 10-15% according to Campaign Monitor data, though the effect varies by industry and audience.</p>
<p>For brands, emoji usage should align with the overall tone and audience expectations. A fintech startup communicating with enterprise clients may use emojis sparingly and stick to professional choices like checkmarks and arrows. A lifestyle brand targeting younger demographics might use a wider palette of expressive faces and objects. Consistency matters: pick a set of emojis that match your brand voice and use them regularly so they become part of your recognizable communication style.</p>
<p>Accessibility is worth considering. Screen readers announce emoji names, so a message with ten consecutive emojis creates a poor experience for users with visual impairments. Use emojis as supplements to text rather than replacements, and place them at the end of sentences or as bullet-point markers rather than embedding them mid-word. The Unicode name read aloud by assistive technology may differ from what you expect, so test with a screen reader if you are producing content at scale.</p>

<div class="ep-faq" itemscope itemtype="https://schema.org/FAQPage">
<h2>Frequently Asked Questions</h2>

<div class="ep-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How do I copy an emoji from this tool?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Click any emoji in the grid and it will be copied to your clipboard automatically. A confirmation toast will appear at the bottom of the screen. You can also open the detail panel by clicking an emoji, then use the individual copy buttons to copy the Unicode code point, HTML entity, or shortcode format instead of the raw emoji character.</p>
</div>
</div>

<div class="ep-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Do emojis look the same on every device?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">No. Each platform uses its own emoji font and design style. Apple, Google, Microsoft, Samsung, and other vendors create their own visual interpretations of each Unicode code point. The underlying character is the same, but the artwork differs. This can occasionally cause miscommunication when an emoji conveys a different nuance on the recipient's device than on the sender's.</p>
</div>
</div>

<div class="ep-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">What is a Unicode code point?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">A Unicode code point is a numerical value that identifies a specific character in the Unicode standard. It is written in hexadecimal with a U+ prefix, such as U+1F600 for the grinning face. Code points serve as the universal identifier that allows every platform and application to recognize which character to render, regardless of the device or operating system.</p>
</div>
</div>

<div class="ep-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">Can I use emojis in professional emails?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">It depends on your workplace culture and audience. Many professionals use emojis sparingly in internal communications, especially in tools like Slack and Teams. For external client-facing emails, conservative industries (finance, law, healthcare) typically avoid emojis while creative industries (marketing, design, media) use them more freely. A single well-placed emoji in a subject line can increase open rates, but overuse can appear unprofessional.</p>
</div>
</div>

<div class="ep-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
<h3 itemprop="name">How are new emojis added to the standard?</h3>
<div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
<p itemprop="text">Anyone can submit an emoji proposal to the Unicode Consortium. Proposals must include evidence of expected usage frequency, distinctiveness from existing emojis, and broad applicability across cultures. The Emoji Subcommittee reviews proposals and recommends candidates for inclusion in the annual Unicode release. From proposal to availability on devices typically takes 18 to 24 months, since vendors need time to design their artwork and ship updated emoji fonts with OS updates.</p>
</div>
</div>

</div>
</div>

<div class="ep-related">
<h2>Related Tools</h2>
<ul>
<li><a href="/tools/word-counter/">Word Counter</a> -- Count words, characters, and get reading time estimates</li>
<li><a href="/tools/text-to-speech/">Text to Speech</a> -- Convert text to natural-sounding speech in your browser</li>
<li><a href="/tools/lorem-ipsum-generator/">Lorem Ipsum Generator</a> -- Generate placeholder text for designs and layouts</li>
<li><a href="/tools/markdown-editor/">Markdown Editor</a> -- Write and preview Markdown with live rendering</li>
</ul>
</div>

<div class="ep-author">
<div class="ep-author-avatar">ML</div>
<div>
<div class="ep-author-name">Michael Lip</div>
<div class="ep-author-bio">Developer and tools engineer at <a href="https://zovo.one">Zovo</a>. Building free developer and productivity tools.</div>
</div>
</div>

<footer class="ep-footer">
<p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
</footer>

</div>

<script>
(function(){
"use strict";

var EMOJIS=[
{e:"\u{1F600}",n:"grinning face",s:":grinning:",c:"smileys",k:"happy smile laugh"},
{e:"\u{1F601}",n:"beaming face with smiling eyes",s:":grin:",c:"smileys",k:"happy grin teeth"},
{e:"\u{1F602}",n:"face with tears of joy",s:":joy:",c:"smileys",k:"laugh cry lol"},
{e:"\u{1F603}",n:"grinning face with big eyes",s:":smiley:",c:"smileys",k:"happy smile open"},
{e:"\u{1F604}",n:"grinning face with smiling eyes",s:":smile:",c:"smileys",k:"happy smile eyes"},
{e:"\u{1F605}",n:"grinning face with sweat",s:":sweat_smile:",c:"smileys",k:"nervous laugh hot"},
{e:"\u{1F606}",n:"squinting face with open mouth",s:":laughing:",c:"smileys",k:"laugh squint xd"},
{e:"\u{1F609}",n:"winking face",s:":wink:",c:"smileys",k:"wink flirt"},
{e:"\u{1F60A}",n:"smiling face with smiling eyes",s:":blush:",c:"smileys",k:"blush shy happy"},
{e:"\u{1F60B}",n:"face savoring food",s:":yum:",c:"smileys",k:"yum delicious tongue"},
{e:"\u{1F60E}",n:"smiling face with sunglasses",s:":sunglasses:",c:"smileys",k:"cool sunglasses boss"},
{e:"\u{1F60D}",n:"smiling face with heart eyes",s:":heart_eyes:",c:"smileys",k:"love heart eyes crush"},
{e:"\u{1F618}",n:"face blowing a kiss",s:":kissing_heart:",c:"smileys",k:"kiss love heart"},
{e:"\u{1F617}",n:"kissing face",s:":kissing:",c:"smileys",k:"kiss lips"},
{e:"\u{1F619}",n:"kissing face with smiling eyes",s:":kissing_smiling_eyes:",c:"smileys",k:"kiss happy"},
{e:"\u{1F61A}",n:"kissing face with closed eyes",s:":kissing_closed_eyes:",c:"smileys",k:"kiss peck"},
{e:"\u{1F642}",n:"slightly smiling face",s:":slight_smile:",c:"smileys",k:"smile subtle"},
{e:"\u{1F917}",n:"hugging face",s:":hugs:",c:"smileys",k:"hug arms open"},
{e:"\u{1F914}",n:"thinking face",s:":thinking:",c:"smileys",k:"think hmm wonder ponder"},
{e:"\u{1F610}",n:"neutral face",s:":neutral_face:",c:"smileys",k:"neutral meh blank"},
{e:"\u{1F611}",n:"expressionless face",s:":expressionless:",c:"smileys",k:"blank deadpan"},
{e:"\u{1F636}",n:"face without mouth",s:":no_mouth:",c:"smileys",k:"silent mute speechless"},
{e:"\u{1F644}",n:"face with rolling eyes",s:":roll_eyes:",c:"smileys",k:"eyeroll annoyed"},
{e:"\u{1F60F}",n:"smirking face",s:":smirk:",c:"smileys",k:"smirk smug flirt"},
{e:"\u{1F623}",n:"persevering face",s:":persevere:",c:"smileys",k:"struggle frustrated"},
{e:"\u{1F625}",n:"sad but relieved face",s:":relieved:",c:"smileys",k:"relieved sad phew"},
{e:"\u{1F62E}",n:"face with open mouth",s:":open_mouth:",c:"smileys",k:"surprised wow gasp"},
{e:"\u{1F910}",n:"zipper mouth face",s:":zipper_mouth:",c:"smileys",k:"secret quiet zip"},
{e:"\u{1F62F}",n:"hushed face",s:":hushed:",c:"smileys",k:"hushed surprised quiet"},
{e:"\u{1F62A}",n:"sleepy face",s:":sleepy:",c:"smileys",k:"sleepy tired bubble"},
{e:"\u{1F62B}",n:"tired face",s:":tired_face:",c:"smileys",k:"tired exhausted whine"},
{e:"\u{1F634}",n:"sleeping face",s:":sleeping:",c:"smileys",k:"sleep zzz rest"},
{e:"\u{1F60C}",n:"relieved face",s:":relieved:",c:"smileys",k:"relieved calm peaceful"},
{e:"\u{1F61B}",n:"face with tongue",s:":stuck_out_tongue:",c:"smileys",k:"tongue playful silly"},
{e:"\u{1F61C}",n:"winking face with tongue",s:":stuck_out_tongue_winking_eye:",c:"smileys",k:"tongue wink silly"},
{e:"\u{1F61D}",n:"squinting face with tongue",s:":stuck_out_tongue_closed_eyes:",c:"smileys",k:"tongue silly taste"},
{e:"\u{1F924}",n:"drooling face",s:":drooling_face:",c:"smileys",k:"drool hungry want"},
{e:"\u{1F612}",n:"unamused face",s:":unamused:",c:"smileys",k:"unamused unhappy annoyed"},
{e:"\u{1F613}",n:"downcast face with sweat",s:":sweat:",c:"smileys",k:"sweat nervous cold"},
{e:"\u{1F614}",n:"pensive face",s:":pensive:",c:"smileys",k:"pensive sad thoughtful"},
{e:"\u{1F615}",n:"confused face",s:":confused:",c:"smileys",k:"confused unsure puzzled"},
{e:"\u{1F643}",n:"upside-down face",s:":upside_down:",c:"smileys",k:"silly sarcastic ironic"},
{e:"\u{1F911}",n:"money mouth face",s:":money_mouth:",c:"smileys",k:"money rich dollar"},
{e:"\u{1F632}",n:"astonished face",s:":astonished:",c:"smileys",k:"astonished shocked amazed"},
{e:"\u{1F641}",n:"slightly frowning face",s:":slight_frown:",c:"smileys",k:"frown sad disappointed"},
{e:"\u{2639\uFE0F}",n:"frowning face",s:":frowning:",c:"smileys",k:"frown sad unhappy"},
{e:"\u{1F616}",n:"confounded face",s:":confounded:",c:"smileys",k:"quiver frustrated confused"},
{e:"\u{1F61E}",n:"disappointed face",s:":disappointed:",c:"smileys",k:"disappointed sad upset"},
{e:"\u{1F61F}",n:"worried face",s:":worried:",c:"smileys",k:"worried nervous anxious"},
{e:"\u{1F624}",n:"face with steam from nose",s:":triumph:",c:"smileys",k:"triumph proud steam angry"},
{e:"\u{1F622}",n:"crying face",s:":cry:",c:"smileys",k:"cry sad tear"},
{e:"\u{1F62D}",n:"loudly crying face",s:":sob:",c:"smileys",k:"sob cry wail bawl"},
{e:"\u{1F626}",n:"frowning face with open mouth",s:":frowning:",c:"smileys",k:"anguish surprise"},
{e:"\u{1F627}",n:"anguished face",s:":anguished:",c:"smileys",k:"anguish stunned"},
{e:"\u{1F628}",n:"fearful face",s:":fearful:",c:"smileys",k:"fear scared worried"},
{e:"\u{1F629}",n:"weary face",s:":weary:",c:"smileys",k:"weary tired fed up"},
{e:"\u{1F630}",n:"anxious face with sweat",s:":cold_sweat:",c:"smileys",k:"anxious nervous cold sweat"},
{e:"\u{1F631}",n:"face screaming in fear",s:":scream:",c:"smileys",k:"scream fear horror"},
{e:"\u{1F633}",n:"flushed face",s:":flushed:",c:"smileys",k:"flushed embarrassed blush"},
{e:"\u{1F635}",n:"face with crossed-out eyes",s:":dizzy_face:",c:"smileys",k:"dizzy dead knockout"},
{e:"\u{1F621}",n:"pouting face",s:":rage:",c:"smileys",k:"rage angry mad furious"},
{e:"\u{1F620}",n:"angry face",s:":angry:",c:"smileys",k:"angry mad grumpy"},
{e:"\u{1F607}",n:"smiling face with halo",s:":innocent:",c:"smileys",k:"innocent angel halo good"},
{e:"\u{1F920}",n:"cowboy hat face",s:":cowboy:",c:"smileys",k:"cowboy hat western"},
{e:"\u{1F921}",n:"clown face",s:":clown:",c:"smileys",k:"clown silly joker"},
{e:"\u{1F925}",n:"lying face",s:":lying_face:",c:"smileys",k:"lie pinocchio nose"},
{e:"\u{1F637}",n:"face with medical mask",s:":mask:",c:"smileys",k:"mask sick medical"},
{e:"\u{1F912}",n:"face with thermometer",s:":thermometer_face:",c:"smileys",k:"sick fever temperature"},
{e:"\u{1F915}",n:"face with head bandage",s:":head_bandage:",c:"smileys",k:"hurt injured bandage"},
{e:"\u{1F922}",n:"nauseated face",s:":nauseated:",c:"smileys",k:"nauseous sick green"},
{e:"\u{1F927}",n:"sneezing face",s:":sneezing:",c:"smileys",k:"sneeze sick tissue"},
{e:"\u{1F608}",n:"smiling face with horns",s:":smiling_imp:",c:"smileys",k:"devil imp evil happy"},
{e:"\u{1F47F}",n:"angry face with horns",s:":imp:",c:"smileys",k:"devil imp angry evil"},
{e:"\u{1F4A9}",n:"pile of poo",s:":poop:",c:"smileys",k:"poop poo shit"},
{e:"\u{1F47B}",n:"ghost",s:":ghost:",c:"smileys",k:"ghost halloween boo"},
{e:"\u{1F480}",n:"skull",s:":skull:",c:"smileys",k:"skull death dead"},
{e:"\u{2764\uFE0F}",n:"red heart",s:":heart:",c:"smileys",k:"love heart red"},
{e:"\u{1F49B}",n:"yellow heart",s:":yellow_heart:",c:"smileys",k:"heart yellow friendship"},
{e:"\u{1F49A}",n:"green heart",s:":green_heart:",c:"smileys",k:"heart green jealous"},
{e:"\u{1F499}",n:"blue heart",s:":blue_heart:",c:"smileys",k:"heart blue trust"},
{e:"\u{1F49C}",n:"purple heart",s:":purple_heart:",c:"smileys",k:"heart purple compassion"},
{e:"\u{1F5A4}",n:"black heart",s:":black_heart:",c:"smileys",k:"heart black evil dark"},
{e:"\u{1F494}",n:"broken heart",s:":broken_heart:",c:"smileys",k:"heart broken sad"},
{e:"\u{1F495}",n:"two hearts",s:":two_hearts:",c:"smileys",k:"hearts love two"},
{e:"\u{1F496}",n:"sparkling heart",s:":sparkling_heart:",c:"smileys",k:"heart sparkle love"},
{e:"\u{1F493}",n:"beating heart",s:":heartbeat:",c:"smileys",k:"heart beating pulse"},
{e:"\u{1F498}",n:"heart with arrow",s:":cupid:",c:"smileys",k:"heart arrow cupid love"},
{e:"\u{1F4AF}",n:"hundred points",s:":100:",c:"smileys",k:"hundred perfect score"},
{e:"\u{1F4A2}",n:"anger symbol",s:":anger:",c:"smileys",k:"anger angry symbol"},
{e:"\u{1F4A5}",n:"collision",s:":boom:",c:"smileys",k:"boom collision bang"},
{e:"\u{1F4AB}",n:"dizzy",s:":dizzy:",c:"smileys",k:"dizzy star sparkle"},
{e:"\u{1F4A6}",n:"sweat droplets",s:":sweat_drops:",c:"smileys",k:"sweat water drops"},
{e:"\u{1F4A8}",n:"dashing away",s:":dash:",c:"smileys",k:"wind dash fast run"},
{e:"\u{1F44D}",n:"thumbs up",s:":thumbsup:",c:"people",k:"thumbs up approve like yes",t:true},
{e:"\u{1F44E}",n:"thumbs down",s:":thumbsdown:",c:"people",k:"thumbs down disapprove dislike no",t:true},
{e:"\u{1F44A}",n:"oncoming fist",s:":fist:",c:"people",k:"fist punch bump",t:true},
{e:"\u{270A}",n:"raised fist",s:":raised_fist:",c:"people",k:"fist power strong",t:true},
{e:"\u{270C\uFE0F}",n:"victory hand",s:":v:",c:"people",k:"peace victory two",t:true},
{e:"\u{1F44B}",n:"waving hand",s:":wave:",c:"people",k:"wave hello goodbye hi",t:true},
{e:"\u{1F44F}",n:"clapping hands",s:":clap:",c:"people",k:"clap applause bravo",t:true},
{e:"\u{1F450}",n:"open hands",s:":open_hands:",c:"people",k:"open hands jazz",t:true},
{e:"\u{1F64C}",n:"raising hands",s:":raised_hands:",c:"people",k:"raise celebrate hooray",t:true},
{e:"\u{1F64F}",n:"folded hands",s:":pray:",c:"people",k:"pray please thanks namaste",t:true},
{e:"\u{1F91D}",n:"handshake",s:":handshake:",c:"people",k:"handshake deal agree"},
{e:"\u{1F4AA}",n:"flexed biceps",s:":muscle:",c:"people",k:"muscle strong flex bicep",t:true},
{e:"\u{1F448}",n:"backhand index pointing left",s:":point_left:",c:"people",k:"point left hand",t:true},
{e:"\u{1F449}",n:"backhand index pointing right",s:":point_right:",c:"people",k:"point right hand",t:true},
{e:"\u{261D\uFE0F}",n:"index pointing up",s:":point_up:",c:"people",k:"point up hand",t:true},
{e:"\u{1F447}",n:"backhand index pointing down",s:":point_down:",c:"people",k:"point down hand",t:true},
{e:"\u{270B}",n:"raised hand",s:":raised_hand:",c:"people",k:"hand stop high five",t:true},
{e:"\u{1F596}",n:"vulcan salute",s:":vulcan:",c:"people",k:"spock vulcan star trek",t:true},
{e:"\u{1F918}",n:"sign of the horns",s:":metal:",c:"people",k:"rock metal horns",t:true},
{e:"\u{1F919}",n:"call me hand",s:":call_me:",c:"people",k:"call phone shaka hang loose",t:true},
{e:"\u{1F590\uFE0F}",n:"hand with fingers splayed",s:":hand_splayed:",c:"people",k:"hand fingers splayed five",t:true},
{e:"\u{270D\uFE0F}",n:"writing hand",s:":writing_hand:",c:"people",k:"write hand pen",t:true},
{e:"\u{1F933}",n:"selfie",s:":selfie:",c:"people",k:"selfie phone camera",t:true},
{e:"\u{1F485}",n:"nail polish",s:":nail_care:",c:"people",k:"nail polish beauty manicure",t:true},
{e:"\u{1F442}",n:"ear",s:":ear:",c:"people",k:"ear hear listen",t:true},
{e:"\u{1F443}",n:"nose",s:":nose:",c:"people",k:"nose smell sniff",t:true},
{e:"\u{1F441\uFE0F}",n:"eye",s:":eye:",c:"people",k:"eye look see"},
{e:"\u{1F440}",n:"eyes",s:":eyes:",c:"people",k:"eyes look see watch"},
{e:"\u{1F476}",n:"baby",s:":baby:",c:"people",k:"baby infant child",t:true},
{e:"\u{1F466}",n:"boy",s:":boy:",c:"people",k:"boy child kid male",t:true},
{e:"\u{1F467}",n:"girl",s:":girl:",c:"people",k:"girl child kid female",t:true},
{e:"\u{1F468}",n:"man",s:":man:",c:"people",k:"man male adult",t:true},
{e:"\u{1F469}",n:"woman",s:":woman:",c:"people",k:"woman female adult",t:true},
{e:"\u{1F474}",n:"old man",s:":older_man:",c:"people",k:"old man elderly grandpa",t:true},
{e:"\u{1F475}",n:"old woman",s:":older_woman:",c:"people",k:"old woman elderly grandma",t:true},
{e:"\u{1F46E}",n:"police officer",s:":cop:",c:"people",k:"police officer law",t:true},
{e:"\u{1F477}",n:"construction worker",s:":construction_worker:",c:"people",k:"construction worker build",t:true},
{e:"\u{1F478}",n:"princess",s:":princess:",c:"people",k:"princess royal crown",t:true},
{e:"\u{1F934}",n:"prince",s:":prince:",c:"people",k:"prince royal crown",t:true},
{e:"\u{1F470}",n:"person with veil",s:":bride_with_veil:",c:"people",k:"bride veil wedding",t:true},
{e:"\u{1F935}",n:"person in tuxedo",s:":person_in_tuxedo:",c:"people",k:"tuxedo groom formal",t:true},
{e:"\u{1F47C}",n:"baby angel",s:":angel:",c:"people",k:"angel baby cherub",t:true},
{e:"\u{1F385}",n:"Santa Claus",s:":santa:",c:"people",k:"santa claus christmas",t:true},
{e:"\u{1F936}",n:"Mrs. Claus",s:":mrs_claus:",c:"people",k:"mrs claus christmas mother",t:true},
{e:"\u{1F436}",n:"dog face",s:":dog:",c:"animals",k:"dog puppy pet"},
{e:"\u{1F431}",n:"cat face",s:":cat:",c:"animals",k:"cat kitten pet meow"},
{e:"\u{1F42D}",n:"mouse face",s:":mouse:",c:"animals",k:"mouse rodent pet"},
{e:"\u{1F439}",n:"hamster",s:":hamster:",c:"animals",k:"hamster rodent pet"},
{e:"\u{1F430}",n:"rabbit face",s:":rabbit:",c:"animals",k:"rabbit bunny pet"},
{e:"\u{1F43B}",n:"bear",s:":bear:",c:"animals",k:"bear grizzly teddy"},
{e:"\u{1F43C}",n:"panda",s:":panda_face:",c:"animals",k:"panda bear bamboo"},
{e:"\u{1F428}",n:"koala",s:":koala:",c:"animals",k:"koala bear australia"},
{e:"\u{1F42F}",n:"tiger face",s:":tiger:",c:"animals",k:"tiger cat wild"},
{e:"\u{1F981}",n:"lion",s:":lion:",c:"animals",k:"lion king mane"},
{e:"\u{1F42E}",n:"cow face",s:":cow:",c:"animals",k:"cow cattle moo"},
{e:"\u{1F437}",n:"pig face",s:":pig:",c:"animals",k:"pig oink farm"},
{e:"\u{1F438}",n:"frog",s:":frog:",c:"animals",k:"frog toad ribbit"},
{e:"\u{1F435}",n:"monkey face",s:":monkey_face:",c:"animals",k:"monkey ape primate"},
{e:"\u{1F648}",n:"see-no-evil monkey",s:":see_no_evil:",c:"animals",k:"monkey see blind"},
{e:"\u{1F649}",n:"hear-no-evil monkey",s:":hear_no_evil:",c:"animals",k:"monkey hear deaf"},
{e:"\u{1F64A}",n:"speak-no-evil monkey",s:":speak_no_evil:",c:"animals",k:"monkey speak mute"},
{e:"\u{1F412}",n:"monkey",s:":monkey:",c:"animals",k:"monkey ape chimp"},
{e:"\u{1F414}",n:"chicken",s:":chicken:",c:"animals",k:"chicken hen poultry"},
{e:"\u{1F427}",n:"penguin",s:":penguin:",c:"animals",k:"penguin bird arctic"},
{e:"\u{1F426}",n:"bird",s:":bird:",c:"animals",k:"bird tweet fly"},
{e:"\u{1F424}",n:"baby chick",s:":baby_chick:",c:"animals",k:"chick baby bird"},
{e:"\u{1F986}",n:"duck",s:":duck:",c:"animals",k:"duck bird quack"},
{e:"\u{1F985}",n:"eagle",s:":eagle:",c:"animals",k:"eagle bird prey"},
{e:"\u{1F989}",n:"owl",s:":owl:",c:"animals",k:"owl bird night wise"},
{e:"\u{1F987}",n:"bat",s:":bat:",c:"animals",k:"bat vampire night"},
{e:"\u{1F43A}",n:"wolf",s:":wolf:",c:"animals",k:"wolf howl wild dog"},
{e:"\u{1F417}",n:"boar",s:":boar:",c:"animals",k:"boar pig wild"},
{e:"\u{1F434}",n:"horse face",s:":horse:",c:"animals",k:"horse pony stallion"},
{e:"\u{1F984}",n:"unicorn",s:":unicorn:",c:"animals",k:"unicorn magic rainbow horse"},
{e:"\u{1F41D}",n:"honeybee",s:":bee:",c:"animals",k:"bee honey insect buzz"},
{e:"\u{1F41B}",n:"bug",s:":bug:",c:"animals",k:"bug insect caterpillar"},
{e:"\u{1F40C}",n:"snail",s:":snail:",c:"animals",k:"snail slow shell"},
{e:"\u{1F41A}",n:"spiral shell",s:":shell:",c:"animals",k:"shell sea ocean"},
{e:"\u{1F41E}",n:"lady beetle",s:":lady_beetle:",c:"animals",k:"ladybug beetle insect"},
{e:"\u{1F41C}",n:"ant",s:":ant:",c:"animals",k:"ant insect bug"},
{e:"\u{1F577\uFE0F}",n:"spider",s:":spider:",c:"animals",k:"spider web insect"},
{e:"\u{1F982}",n:"scorpion",s:":scorpion:",c:"animals",k:"scorpion zodiac sting"},
{e:"\u{1F422}",n:"turtle",s:":turtle:",c:"animals",k:"turtle slow shell tortoise"},
{e:"\u{1F40D}",n:"snake",s:":snake:",c:"animals",k:"snake serpent reptile"},
{e:"\u{1F98E}",n:"lizard",s:":lizard:",c:"animals",k:"lizard reptile gecko"},
{e:"\u{1F420}",n:"tropical fish",s:":tropical_fish:",c:"animals",k:"fish tropical nemo"},
{e:"\u{1F41F}",n:"fish",s:":fish:",c:"animals",k:"fish sea ocean"},
{e:"\u{1F421}",n:"blowfish",s:":blowfish:",c:"animals",k:"blowfish puffer fish"},
{e:"\u{1F42C}",n:"dolphin",s:":dolphin:",c:"animals",k:"dolphin flipper ocean"},
{e:"\u{1F433}",n:"spouting whale",s:":whale:",c:"animals",k:"whale ocean sea water"},
{e:"\u{1F419}",n:"octopus",s:":octopus:",c:"animals",k:"octopus sea tentacle"},
{e:"\u{1F980}",n:"crab",s:":crab:",c:"animals",k:"crab lobster cancer zodiac"},
{e:"\u{1F40A}",n:"crocodile",s:":crocodile:",c:"animals",k:"crocodile alligator reptile"},
{e:"\u{1F418}",n:"elephant",s:":elephant:",c:"animals",k:"elephant trunk large"},
{e:"\u{1F98F}",n:"rhinoceros",s:":rhino:",c:"animals",k:"rhino rhinoceros horn"},
{e:"\u{1F42A}",n:"camel",s:":camel:",c:"animals",k:"camel desert hump"},
{e:"\u{1F98A}",n:"fox",s:":fox:",c:"animals",k:"fox red sly"},
{e:"\u{1F98C}",n:"deer",s:":deer:",c:"animals",k:"deer bambi nature"},
{e:"\u{1F40E}",n:"horse",s:":racehorse:",c:"animals",k:"horse racing gallop"},
{e:"\u{1F99B}",n:"hippopotamus",s:":hippo:",c:"animals",k:"hippo hippopotamus river"},
{e:"\u{1F33B}",n:"sunflower",s:":sunflower:",c:"animals",k:"sunflower yellow plant"},
{e:"\u{1F339}",n:"rose",s:":rose:",c:"animals",k:"rose flower red love"},
{e:"\u{1F33A}",n:"hibiscus",s:":hibiscus:",c:"animals",k:"hibiscus flower tropical"},
{e:"\u{1F337}",n:"tulip",s:":tulip:",c:"animals",k:"tulip flower spring"},
{e:"\u{1F338}",n:"cherry blossom",s:":cherry_blossom:",c:"animals",k:"cherry blossom spring sakura"},
{e:"\u{1F332}",n:"evergreen tree",s:":evergreen_tree:",c:"animals",k:"tree pine evergreen"},
{e:"\u{1F333}",n:"deciduous tree",s:":deciduous_tree:",c:"animals",k:"tree oak nature"},
{e:"\u{1F334}",n:"palm tree",s:":palm_tree:",c:"animals",k:"palm tree tropical beach"},
{e:"\u{1F335}",n:"cactus",s:":cactus:",c:"animals",k:"cactus desert plant"},
{e:"\u{1F340}",n:"four leaf clover",s:":four_leaf_clover:",c:"animals",k:"clover luck shamrock four"},
{e:"\u{1F341}",n:"maple leaf",s:":maple_leaf:",c:"animals",k:"maple leaf canada autumn fall"},
{e:"\u{1F342}",n:"fallen leaf",s:":fallen_leaf:",c:"animals",k:"leaf autumn fall nature"},
{e:"\u{1F343}",n:"leaf fluttering in wind",s:":leaves:",c:"animals",k:"leaf wind nature"},
{e:"\u{2600\uFE0F}",n:"sun",s:":sunny:",c:"animals",k:"sun sunny weather hot"},
{e:"\u{1F324\uFE0F}",n:"sun behind small cloud",s:":sun_small_cloud:",c:"animals",k:"sun cloud partly"},
{e:"\u{26C5}",n:"sun behind cloud",s:":partly_sunny:",c:"animals",k:"sun cloud partly cloudy"},
{e:"\u{2601\uFE0F}",n:"cloud",s:":cloud:",c:"animals",k:"cloud cloudy weather"},
{e:"\u{1F327\uFE0F}",n:"cloud with rain",s:":cloud_rain:",c:"animals",k:"rain cloud weather"},
{e:"\u{26C8\uFE0F}",n:"cloud with lightning and rain",s:":thunder_cloud_rain:",c:"animals",k:"thunderstorm lightning rain"},
{e:"\u{2744\uFE0F}",n:"snowflake",s:":snowflake:",c:"animals",k:"snowflake cold winter snow"},
{e:"\u{1F308}",n:"rainbow",s:":rainbow:",c:"animals",k:"rainbow colorful weather"},
{e:"\u{2B50}",n:"star",s:":star:",c:"animals",k:"star yellow night"},
{e:"\u{1F31F}",n:"glowing star",s:":star2:",c:"animals",k:"star glow sparkle"},
{e:"\u{1F525}",n:"fire",s:":fire:",c:"animals",k:"fire hot flame lit"},
{e:"\u{1F4A7}",n:"droplet",s:":droplet:",c:"animals",k:"water drop droplet"},
{e:"\u{1F30A}",n:"water wave",s:":ocean:",c:"animals",k:"ocean wave water sea"},
{e:"\u{1F34E}",n:"red apple",s:":apple:",c:"food",k:"apple red fruit"},
{e:"\u{1F34F}",n:"green apple",s:":green_apple:",c:"food",k:"apple green fruit"},
{e:"\u{1F34A}",n:"tangerine",s:":tangerine:",c:"food",k:"tangerine orange mandarin fruit"},
{e:"\u{1F34B}",n:"lemon",s:":lemon:",c:"food",k:"lemon yellow citrus fruit"},
{e:"\u{1F34C}",n:"banana",s:":banana:",c:"food",k:"banana fruit yellow"},
{e:"\u{1F349}",n:"watermelon",s:":watermelon:",c:"food",k:"watermelon summer fruit"},
{e:"\u{1F347}",n:"grapes",s:":grapes:",c:"food",k:"grapes wine fruit purple"},
{e:"\u{1F353}",n:"strawberry",s:":strawberry:",c:"food",k:"strawberry berry fruit red"},
{e:"\u{1F352}",n:"cherries",s:":cherries:",c:"food",k:"cherry cherries fruit"},
{e:"\u{1F351}",n:"peach",s:":peach:",c:"food",k:"peach fruit butt"},
{e:"\u{1F34D}",n:"pineapple",s:":pineapple:",c:"food",k:"pineapple fruit tropical"},
{e:"\u{1F95D}",n:"kiwi fruit",s:":kiwi:",c:"food",k:"kiwi fruit green"},
{e:"\u{1F951}",n:"avocado",s:":avocado:",c:"food",k:"avocado fruit green guac"},
{e:"\u{1F345}",n:"tomato",s:":tomato:",c:"food",k:"tomato red vegetable"},
{e:"\u{1F346}",n:"eggplant",s:":eggplant:",c:"food",k:"eggplant aubergine purple"},
{e:"\u{1F955}",n:"carrot",s:":carrot:",c:"food",k:"carrot orange vegetable"},
{e:"\u{1F33D}",n:"ear of corn",s:":corn:",c:"food",k:"corn maize vegetable"},
{e:"\u{1F336\uFE0F}",n:"hot pepper",s:":hot_pepper:",c:"food",k:"pepper hot chili spicy"},
{e:"\u{1F952}",n:"cucumber",s:":cucumber:",c:"food",k:"cucumber pickle vegetable"},
{e:"\u{1F344}",n:"mushroom",s:":mushroom:",c:"food",k:"mushroom fungus toadstool"},
{e:"\u{1F95C}",n:"peanuts",s:":peanuts:",c:"food",k:"peanut nut snack"},
{e:"\u{1F35E}",n:"bread",s:":bread:",c:"food",k:"bread loaf toast"},
{e:"\u{1F950}",n:"croissant",s:":croissant:",c:"food",k:"croissant pastry french"},
{e:"\u{1F956}",n:"baguette bread",s:":baguette:",c:"food",k:"baguette bread french"},
{e:"\u{1F95E}",n:"pancakes",s:":pancakes:",c:"food",k:"pancake breakfast maple"},
{e:"\u{1F9C0}",n:"cheese wedge",s:":cheese:",c:"food",k:"cheese wedge cheddar"},
{e:"\u{1F356}",n:"meat on bone",s:":meat_on_bone:",c:"food",k:"meat bone ribs"},
{e:"\u{1F357}",n:"poultry leg",s:":poultry_leg:",c:"food",k:"chicken leg drumstick"},
{e:"\u{1F354}",n:"hamburger",s:":hamburger:",c:"food",k:"burger hamburger fast food"},
{e:"\u{1F35F}",n:"french fries",s:":fries:",c:"food",k:"fries french chips fast food"},
{e:"\u{1F355}",n:"pizza",s:":pizza:",c:"food",k:"pizza slice cheese pepperoni"},
{e:"\u{1F32D}",n:"hot dog",s:":hotdog:",c:"food",k:"hot dog sausage"},
{e:"\u{1F32E}",n:"taco",s:":taco:",c:"food",k:"taco mexican food"},
{e:"\u{1F32F}",n:"burrito",s:":burrito:",c:"food",k:"burrito wrap mexican"},
{e:"\u{1F959}",n:"stuffed flatbread",s:":stuffed_flatbread:",c:"food",k:"falafel pita gyro"},
{e:"\u{1F95A}",n:"egg",s:":egg:",c:"food",k:"egg breakfast chicken"},
{e:"\u{1F373}",n:"cooking",s:":cooking:",c:"food",k:"egg cooking frying pan"},
{e:"\u{1F958}",n:"shallow pan of food",s:":shallow_pan:",c:"food",k:"paella pan food cooking"},
{e:"\u{1F372}",n:"pot of food",s:":stew:",c:"food",k:"stew pot food curry"},
{e:"\u{1F35D}",n:"spaghetti",s:":spaghetti:",c:"food",k:"spaghetti pasta noodle italian"},
{e:"\u{1F35C}",n:"steaming bowl",s:":ramen:",c:"food",k:"ramen noodle soup bowl"},
{e:"\u{1F363}",n:"sushi",s:":sushi:",c:"food",k:"sushi fish japanese rice"},
{e:"\u{1F371}",n:"bento box",s:":bento:",c:"food",k:"bento box lunch japanese"},
{e:"\u{1F364}",n:"fried shrimp",s:":fried_shrimp:",c:"food",k:"shrimp tempura fried"},
{e:"\u{1F35A}",n:"cooked rice",s:":rice:",c:"food",k:"rice bowl white"},
{e:"\u{1F370}",n:"shortcake",s:":cake:",c:"food",k:"cake shortcake dessert strawberry"},
{e:"\u{1F382}",n:"birthday cake",s:":birthday:",c:"food",k:"birthday cake candle party"},
{e:"\u{1F36E}",n:"custard",s:":custard:",c:"food",k:"custard pudding flan dessert"},
{e:"\u{1F36D}",n:"lollipop",s:":lollipop:",c:"food",k:"lollipop candy sweet"},
{e:"\u{1F36C}",n:"candy",s:":candy:",c:"food",k:"candy sweet wrapper"},
{e:"\u{1F36B}",n:"chocolate bar",s:":chocolate_bar:",c:"food",k:"chocolate bar candy sweet"},
{e:"\u{1F369}",n:"doughnut",s:":doughnut:",c:"food",k:"donut doughnut dessert sweet"},
{e:"\u{1F36A}",n:"cookie",s:":cookie:",c:"food",k:"cookie biscuit dessert"},
{e:"\u{1F366}",n:"soft ice cream",s:":icecream:",c:"food",k:"ice cream soft serve dessert"},
{e:"\u{1F367}",n:"shaved ice",s:":shaved_ice:",c:"food",k:"shaved ice snow cone"},
{e:"\u{1F368}",n:"ice cream",s:":ice_cream:",c:"food",k:"ice cream sundae dessert"},
{e:"\u{2615}",n:"hot beverage",s:":coffee:",c:"food",k:"coffee tea hot beverage cup"},
{e:"\u{1F375}",n:"teacup without handle",s:":tea:",c:"food",k:"tea green matcha cup"},
{e:"\u{1F376}",n:"sake",s:":sake:",c:"food",k:"sake japanese rice wine"},
{e:"\u{1F37A}",n:"beer mug",s:":beer:",c:"food",k:"beer mug drink alcohol"},
{e:"\u{1F37B}",n:"clinking beer mugs",s:":beers:",c:"food",k:"beer cheers toast drink"},
{e:"\u{1F377}",n:"wine glass",s:":wine_glass:",c:"food",k:"wine glass red drink"},
{e:"\u{1F378}",n:"cocktail glass",s:":cocktail:",c:"food",k:"cocktail martini drink bar"},
{e:"\u{1F379}",n:"tropical drink",s:":tropical_drink:",c:"food",k:"tropical drink cocktail summer"},
{e:"\u{1F37E}",n:"bottle with popping cork",s:":champagne:",c:"food",k:"champagne bottle celebrate"},
{e:"\u{1F943}",n:"tumbler glass",s:":tumbler_glass:",c:"food",k:"whiskey glass tumbler bourbon"},
{e:"\u{1F697}",n:"automobile",s:":car:",c:"travel",k:"car automobile vehicle drive"},
{e:"\u{1F695}",n:"taxi",s:":taxi:",c:"travel",k:"taxi cab yellow car"},
{e:"\u{1F68C}",n:"bus",s:":bus:",c:"travel",k:"bus transit public transport"},
{e:"\u{1F691}",n:"ambulance",s:":ambulance:",c:"travel",k:"ambulance emergency hospital"},
{e:"\u{1F692}",n:"fire engine",s:":fire_engine:",c:"travel",k:"fire truck engine emergency"},
{e:"\u{1F693}",n:"police car",s:":police_car:",c:"travel",k:"police car cop law"},
{e:"\u{1F3CE\uFE0F}",n:"racing car",s:":racing_car:",c:"travel",k:"race car formula speed"},
{e:"\u{1F6B2}",n:"bicycle",s:":bike:",c:"travel",k:"bicycle bike cycling"},
{e:"\u{1F6F4}",n:"kick scooter",s:":scooter:",c:"travel",k:"scooter kick ride"},
{e:"\u{1F6E3\uFE0F}",n:"motorway",s:":motorway:",c:"travel",k:"highway road motorway"},
{e:"\u{2708\uFE0F}",n:"airplane",s:":airplane:",c:"travel",k:"airplane plane flight travel"},
{e:"\u{1F680}",n:"rocket",s:":rocket:",c:"travel",k:"rocket space launch"},
{e:"\u{1F6F8}",n:"flying saucer",s:":flying_saucer:",c:"travel",k:"ufo alien saucer"},
{e:"\u{1F6A2}",n:"ship",s:":ship:",c:"travel",k:"ship boat cruise ocean"},
{e:"\u{26F5}",n:"sailboat",s:":sailboat:",c:"travel",k:"sailboat boat wind"},
{e:"\u{1F3E0}",n:"house",s:":house:",c:"travel",k:"house home building"},
{e:"\u{1F3E2}",n:"office building",s:":office:",c:"travel",k:"office building work"},
{e:"\u{1F3E5}",n:"hospital",s:":hospital:",c:"travel",k:"hospital medical health"},
{e:"\u{1F3EB}",n:"school",s:":school:",c:"travel",k:"school building education"},
{e:"\u{1F3EA}",n:"convenience store",s:":convenience_store:",c:"travel",k:"store shop convenience"},
{e:"\u{1F3E8}",n:"hotel",s:":hotel:",c:"travel",k:"hotel building accommodation"},
{e:"\u{1F3F0}",n:"castle",s:":castle:",c:"travel",k:"castle european palace"},
{e:"\u{26EA}",n:"church",s:":church:",c:"travel",k:"church chapel religion"},
{e:"\u{1F30D}",n:"globe showing Europe-Africa",s:":earth_africa:",c:"travel",k:"globe earth world europe africa"},
{e:"\u{1F30E}",n:"globe showing Americas",s:":earth_americas:",c:"travel",k:"globe earth world americas"},
{e:"\u{1F30F}",n:"globe showing Asia-Australia",s:":earth_asia:",c:"travel",k:"globe earth world asia australia"},
{e:"\u{1F5FD}",n:"Statue of Liberty",s:":statue_of_liberty:",c:"travel",k:"statue liberty new york"},
{e:"\u{1F5FC}",n:"Tokyo Tower",s:":tokyo_tower:",c:"travel",k:"tokyo tower japan"},
{e:"\u{1F5FB}",n:"Mount Fuji",s:":mount_fuji:",c:"travel",k:"fuji mountain japan"},
{e:"\u{1F3D6\uFE0F}",n:"beach with umbrella",s:":beach:",c:"travel",k:"beach umbrella sand ocean"},
{e:"\u{1F3D4\uFE0F}",n:"snow-capped mountain",s:":mountain_snow:",c:"travel",k:"mountain snow peak"},
{e:"\u{26F0\uFE0F}",n:"mountain",s:":mountain:",c:"travel",k:"mountain hill peak"},
{e:"\u{1F3DD\uFE0F}",n:"desert island",s:":island:",c:"travel",k:"island palm desert"},
{e:"\u{1F3DE\uFE0F}",n:"national park",s:":national_park:",c:"travel",k:"park national nature"},
{e:"\u{1F307}",n:"sunset",s:":city_sunset:",c:"travel",k:"sunset city evening"},
{e:"\u{1F305}",n:"sunrise",s:":sunrise:",c:"travel",k:"sunrise morning dawn"},
{e:"\u{1F303}",n:"night with stars",s:":night_with_stars:",c:"travel",k:"night stars city"},
{e:"\u{1F309}",n:"bridge at night",s:":bridge_at_night:",c:"travel",k:"bridge night city"},
{e:"\u{26BD}",n:"soccer ball",s:":soccer:",c:"activities",k:"soccer football ball sport"},
{e:"\u{1F3C0}",n:"basketball",s:":basketball:",c:"activities",k:"basketball ball sport nba"},
{e:"\u{1F3C8}",n:"american football",s:":football:",c:"activities",k:"football american nfl sport"},
{e:"\u{26BE}",n:"baseball",s:":baseball:",c:"activities",k:"baseball ball sport mlb"},
{e:"\u{1F3BE}",n:"tennis",s:":tennis:",c:"activities",k:"tennis ball racket sport"},
{e:"\u{1F3D0}",n:"volleyball",s:":volleyball:",c:"activities",k:"volleyball ball sport beach"},
{e:"\u{1F3C9}",n:"rugby football",s:":rugby_football:",c:"activities",k:"rugby football sport"},
{e:"\u{1F3B1}",n:"pool 8 ball",s:":8ball:",c:"activities",k:"pool billiards eight ball"},
{e:"\u{1F3D3}",n:"ping pong",s:":ping_pong:",c:"activities",k:"ping pong table tennis"},
{e:"\u{1F3F8}",n:"badminton",s:":badminton:",c:"activities",k:"badminton shuttlecock sport"},
{e:"\u{1F94A}",n:"boxing glove",s:":boxing_glove:",c:"activities",k:"boxing glove fight sport"},
{e:"\u{1F3BF}",n:"skis",s:":ski:",c:"activities",k:"ski skiing snow winter sport"},
{e:"\u{1F3C2}",n:"snowboarder",s:":snowboarder:",c:"activities",k:"snowboard snow winter sport"},
{e:"\u{1F3CB\uFE0F}",n:"person lifting weights",s:":weight_lifting:",c:"activities",k:"weight lifting gym exercise"},
{e:"\u{1F3C3}",n:"person running",s:":runner:",c:"activities",k:"run runner jog exercise"},
{e:"\u{1F3CA}",n:"person swimming",s:":swimmer:",c:"activities",k:"swim swimming pool sport"},
{e:"\u{1F6B4}",n:"person biking",s:":bicyclist:",c:"activities",k:"cycling bike bicycle sport"},
{e:"\u{1F3C6}",n:"trophy",s:":trophy:",c:"activities",k:"trophy award winner cup gold"},
{e:"\u{1F3C5}",n:"sports medal",s:":medal:",c:"activities",k:"medal sports gold winner"},
{e:"\u{1F947}",n:"1st place medal",s:":first_place:",c:"activities",k:"gold medal first place winner"},
{e:"\u{1F948}",n:"2nd place medal",s:":second_place:",c:"activities",k:"silver medal second place"},
{e:"\u{1F949}",n:"3rd place medal",s:":third_place:",c:"activities",k:"bronze medal third place"},
{e:"\u{1F3AF}",n:"bullseye",s:":dart:",c:"activities",k:"dart bullseye target direct hit"},
{e:"\u{1F3AE}",n:"video game",s:":video_game:",c:"activities",k:"video game controller gaming"},
{e:"\u{1F3B2}",n:"game die",s:":game_die:",c:"activities",k:"dice die game random"},
{e:"\u{1F3B0}",n:"slot machine",s:":slot_machine:",c:"activities",k:"slot machine casino gambling"},
{e:"\u{265F\uFE0F}",n:"chess pawn",s:":chess_pawn:",c:"activities",k:"chess pawn strategy game"},
{e:"\u{1F3A8}",n:"artist palette",s:":art:",c:"activities",k:"art palette painting color"},
{e:"\u{1F3AD}",n:"performing arts",s:":performing_arts:",c:"activities",k:"theater drama mask acting"},
{e:"\u{1F3B5}",n:"musical note",s:":musical_note:",c:"activities",k:"music note song"},
{e:"\u{1F3B6}",n:"musical notes",s:":notes:",c:"activities",k:"music notes song melody"},
{e:"\u{1F3B8}",n:"guitar",s:":guitar:",c:"activities",k:"guitar music rock instrument"},
{e:"\u{1F3B9}",n:"musical keyboard",s:":musical_keyboard:",c:"activities",k:"piano keyboard music instrument"},
{e:"\u{1F3A4}",n:"microphone",s:":microphone:",c:"activities",k:"microphone karaoke sing music"},
{e:"\u{1F3A7}",n:"headphone",s:":headphones:",c:"activities",k:"headphone music listen audio"},
{e:"\u{1F3AC}",n:"clapper board",s:":clapper:",c:"activities",k:"clapper movie film cinema"},
{e:"\u{1F3A0}",n:"carousel horse",s:":carousel_horse:",c:"activities",k:"carousel horse amusement"},
{e:"\u{1F3A1}",n:"ferris wheel",s:":ferris_wheel:",c:"activities",k:"ferris wheel amusement park"},
{e:"\u{1F3A2}",n:"roller coaster",s:":roller_coaster:",c:"activities",k:"roller coaster amusement thrill"},
{e:"\u{1F3AA}",n:"circus tent",s:":circus_tent:",c:"activities",k:"circus tent show"},
{e:"\u{1F4F1}",n:"mobile phone",s:":iphone:",c:"objects",k:"phone mobile cell iphone"},
{e:"\u{1F4BB}",n:"laptop",s:":computer:",c:"objects",k:"laptop computer pc mac"},
{e:"\u{1F5A5\uFE0F}",n:"desktop computer",s:":desktop:",c:"objects",k:"desktop computer monitor screen"},
{e:"\u{1F4FA}",n:"television",s:":tv:",c:"objects",k:"television tv screen"},
{e:"\u{1F4F7}",n:"camera",s:":camera:",c:"objects",k:"camera photo picture"},
{e:"\u{1F4F9}",n:"video camera",s:":video_camera:",c:"objects",k:"video camera film record"},
{e:"\u{1F50D}",n:"magnifying glass tilted left",s:":mag:",c:"objects",k:"magnifying glass search zoom"},
{e:"\u{1F50E}",n:"magnifying glass tilted right",s:":mag_right:",c:"objects",k:"magnifying glass search find"},
{e:"\u{1F4A1}",n:"light bulb",s:":bulb:",c:"objects",k:"bulb light idea bright"},
{e:"\u{1F526}",n:"flashlight",s:":flashlight:",c:"objects",k:"flashlight torch light"},
{e:"\u{1F56F\uFE0F}",n:"candle",s:":candle:",c:"objects",k:"candle flame light"},
{e:"\u{1F4D6}",n:"open book",s:":book:",c:"objects",k:"book open read study"},
{e:"\u{1F4DA}",n:"books",s:":books:",c:"objects",k:"books library study read"},
{e:"\u{1F4D3}",n:"notebook",s:":notebook:",c:"objects",k:"notebook journal write"},
{e:"\u{1F4DD}",n:"memo",s:":memo:",c:"objects",k:"memo note write pencil"},
{e:"\u{270F\uFE0F}",n:"pencil",s:":pencil2:",c:"objects",k:"pencil write draw"},
{e:"\u{1F58A\uFE0F}",n:"pen",s:":pen:",c:"objects",k:"pen ballpoint write"},
{e:"\u{1F4CE}",n:"paperclip",s:":paperclip:",c:"objects",k:"paperclip office clip"},
{e:"\u{1F4CB}",n:"clipboard",s:":clipboard:",c:"objects",k:"clipboard list document"},
{e:"\u{1F4C5}",n:"calendar",s:":calendar:",c:"objects",k:"calendar date day"},
{e:"\u{1F4C6}",n:"tear-off calendar",s:":tear_off_calendar:",c:"objects",k:"calendar date tear off"},
{e:"\u{1F4C8}",n:"chart increasing",s:":chart_up:",c:"objects",k:"chart graph up increase trend"},
{e:"\u{1F4C9}",n:"chart decreasing",s:":chart_down:",c:"objects",k:"chart graph down decrease"},
{e:"\u{1F4CA}",n:"bar chart",s:":bar_chart:",c:"objects",k:"bar chart graph statistics"},
{e:"\u{1F4E7}",n:"email",s:":email:",c:"objects",k:"email mail letter envelope"},
{e:"\u{1F4E8}",n:"incoming envelope",s:":incoming_envelope:",c:"objects",k:"envelope incoming mail"},
{e:"\u{1F4E9}",n:"envelope with arrow",s:":envelope_with_arrow:",c:"objects",k:"envelope send mail outgoing"},
{e:"\u{1F4E6}",n:"package",s:":package:",c:"objects",k:"package box parcel delivery"},
{e:"\u{1F3F7\uFE0F}",n:"label",s:":label:",c:"objects",k:"label tag price"},
{e:"\u{1F512}",n:"locked",s:":lock:",c:"objects",k:"lock secure padlock closed"},
{e:"\u{1F513}",n:"unlocked",s:":unlock:",c:"objects",k:"unlock open padlock"},
{e:"\u{1F511}",n:"key",s:":key:",c:"objects",k:"key lock password access"},
{e:"\u{1F527}",n:"wrench",s:":wrench:",c:"objects",k:"wrench tool fix repair"},
{e:"\u{1F528}",n:"hammer",s:":hammer:",c:"objects",k:"hammer tool build nail"},
{e:"\u{1F529}",n:"nut and bolt",s:":nut_and_bolt:",c:"objects",k:"nut bolt hardware screw"},
{e:"\u{2699\uFE0F}",n:"gear",s:":gear:",c:"objects",k:"gear cog settings mechanic"},
{e:"\u{1F6E1\uFE0F}",n:"shield",s:":shield:",c:"objects",k:"shield protect defense security"},
{e:"\u{1F5D1\uFE0F}",n:"wastebasket",s:":wastebasket:",c:"objects",k:"trash wastebasket delete garbage"},
{e:"\u{1F4B0}",n:"money bag",s:":moneybag:",c:"objects",k:"money bag dollar rich"},
{e:"\u{1F4B5}",n:"dollar banknote",s:":dollar:",c:"objects",k:"dollar bill money cash"},
{e:"\u{1F4B3}",n:"credit card",s:":credit_card:",c:"objects",k:"credit card payment bank"},
{e:"\u{1F48E}",n:"gem stone",s:":gem:",c:"objects",k:"gem diamond jewel crystal"},
{e:"\u{1F4E2}",n:"loudspeaker",s:":loudspeaker:",c:"objects",k:"loudspeaker announcement megaphone"},
{e:"\u{1F514}",n:"bell",s:":bell:",c:"objects",k:"bell notification ring alert"},
{e:"\u{1F3B5}",n:"musical note",s:":musical_note:",c:"objects",k:"music note song"},
{e:"\u{231A}",n:"watch",s:":watch:",c:"objects",k:"watch clock time wrist"},
{e:"\u{23F0}",n:"alarm clock",s:":alarm_clock:",c:"objects",k:"alarm clock time wake"},
{e:"\u{23F3}",n:"hourglass not done",s:":hourglass_flowing:",c:"objects",k:"hourglass time sand timer"},
{e:"\u{1F4F0}",n:"newspaper",s:":newspaper:",c:"objects",k:"newspaper news press article"},
{e:"\u{1F3AE}",n:"video game controller",s:":video_game:",c:"objects",k:"game controller gaming joystick"},
{e:"\u{1F3B2}",n:"game die",s:":die:",c:"objects",k:"dice die game board random"},
{e:"\u{1F52B}",n:"water pistol",s:":gun:",c:"objects",k:"gun pistol water toy"},
{e:"\u{1F4A3}",n:"bomb",s:":bomb:",c:"objects",k:"bomb explosive boom"},
{e:"\u{1F48A}",n:"pill",s:":pill:",c:"objects",k:"pill medicine drug health"},
{e:"\u{1F489}",n:"syringe",s:":syringe:",c:"objects",k:"syringe needle vaccine injection"},
{e:"\u{2757}",n:"red exclamation mark",s:":exclamation:",c:"symbols",k:"exclamation mark red alert warning"},
{e:"\u{2753}",n:"red question mark",s:":question:",c:"symbols",k:"question mark red confused"},
{e:"\u{2705}",n:"check mark button",s:":white_check_mark:",c:"symbols",k:"check mark done yes approved"},
{e:"\u{274C}",n:"cross mark",s:":x:",c:"symbols",k:"cross mark no wrong delete"},
{e:"\u{274E}",n:"cross mark button",s:":negative_squared_cross_mark:",c:"symbols",k:"cross mark button red no"},
{e:"\u{2795}",n:"plus",s:":heavy_plus_sign:",c:"symbols",k:"plus add math"},
{e:"\u{2796}",n:"minus",s:":heavy_minus_sign:",c:"symbols",k:"minus subtract math"},
{e:"\u{2716\uFE0F}",n:"multiply",s:":heavy_multiplication_x:",c:"symbols",k:"multiply times math x"},
{e:"\u{27A1\uFE0F}",n:"right arrow",s:":arrow_right:",c:"symbols",k:"right arrow direction east"},
{e:"\u{2B05\uFE0F}",n:"left arrow",s:":arrow_left:",c:"symbols",k:"left arrow direction west"},
{e:"\u{2B06\uFE0F}",n:"up arrow",s:":arrow_up:",c:"symbols",k:"up arrow direction north"},
{e:"\u{2B07\uFE0F}",n:"down arrow",s:":arrow_down:",c:"symbols",k:"down arrow direction south"},
{e:"\u{1F503}",n:"clockwise vertical arrows",s:":arrows_clockwise:",c:"symbols",k:"arrows clockwise cycle refresh"},
{e:"\u{1F504}",n:"counterclockwise arrows button",s:":arrows_counterclockwise:",c:"symbols",k:"arrows counterclockwise repeat"},
{e:"\u{1F519}",n:"BACK arrow",s:":back:",c:"symbols",k:"back arrow return previous"},
{e:"\u{1F51A}",n:"END arrow",s:":end:",c:"symbols",k:"end arrow finish last"},
{e:"\u{1F51D}",n:"TOP arrow",s:":top:",c:"symbols",k:"top arrow up first"},
{e:"\u{1F6AB}",n:"prohibited",s:":no_entry_sign:",c:"symbols",k:"prohibited no stop forbidden"},
{e:"\u{1F4F4}",n:"mobile phone off",s:":mobile_phone_off:",c:"symbols",k:"phone off silent"},
{e:"\u{1F508}",n:"speaker low volume",s:":speaker:",c:"symbols",k:"speaker volume low quiet"},
{e:"\u{1F509}",n:"speaker medium volume",s:":sound:",c:"symbols",k:"speaker volume medium"},
{e:"\u{1F50A}",n:"speaker high volume",s:":loud_sound:",c:"symbols",k:"speaker volume high loud"},
{e:"\u{1F507}",n:"muted speaker",s:":mute:",c:"symbols",k:"speaker mute silent"},
{e:"\u{267B\uFE0F}",n:"recycling symbol",s:":recycle:",c:"symbols",k:"recycle green environment eco"},
{e:"\u{269B\uFE0F}",n:"atom symbol",s:":atom:",c:"symbols",k:"atom science physics"},
{e:"\u{2622\uFE0F}",n:"radioactive",s:":radioactive:",c:"symbols",k:"radioactive hazard nuclear"},
{e:"\u{2623\uFE0F}",n:"biohazard",s:":biohazard:",c:"symbols",k:"biohazard toxic hazard"},
{e:"\u{262F\uFE0F}",n:"yin yang",s:":yin_yang:",c:"symbols",k:"yin yang balance taoism"},
{e:"\u{271D\uFE0F}",n:"latin cross",s:":cross:",c:"symbols",k:"cross religion christian"},
{e:"\u{2721\uFE0F}",n:"star of David",s:":star_of_david:",c:"symbols",k:"star david jewish judaism"},
{e:"\u{2638\uFE0F}",n:"wheel of dharma",s:":wheel_of_dharma:",c:"symbols",k:"dharma wheel buddhism"},
{e:"\u{262E\uFE0F}",n:"peace symbol",s:":peace:",c:"symbols",k:"peace symbol antiwar"},
{e:"\u{1F549\uFE0F}",n:"om",s:":om:",c:"symbols",k:"om hinduism buddhism spiritual"},
{e:"\u{2648}",n:"Aries",s:":aries:",c:"symbols",k:"aries zodiac horoscope"},
{e:"\u{2649}",n:"Taurus",s:":taurus:",c:"symbols",k:"taurus zodiac horoscope"},
{e:"\u{264A}",n:"Gemini",s:":gemini:",c:"symbols",k:"gemini zodiac horoscope"},
{e:"\u{264B}",n:"Cancer",s:":cancer:",c:"symbols",k:"cancer zodiac horoscope"},
{e:"\u{264C}",n:"Leo",s:":leo:",c:"symbols",k:"leo zodiac horoscope"},
{e:"\u{264D}",n:"Virgo",s:":virgo:",c:"symbols",k:"virgo zodiac horoscope"},
{e:"\u{264E}",n:"Libra",s:":libra:",c:"symbols",k:"libra zodiac horoscope"},
{e:"\u{264F}",n:"Scorpio",s:":scorpius:",c:"symbols",k:"scorpio zodiac horoscope"},
{e:"\u{2650}",n:"Sagittarius",s:":sagittarius:",c:"symbols",k:"sagittarius zodiac horoscope"},
{e:"\u{2651}",n:"Capricorn",s:":capricorn:",c:"symbols",k:"capricorn zodiac horoscope"},
{e:"\u{2652}",n:"Aquarius",s:":aquarius:",c:"symbols",k:"aquarius zodiac horoscope"},
{e:"\u{2653}",n:"Pisces",s:":pisces:",c:"symbols",k:"pisces zodiac horoscope"},
{e:"\u{1F4F2}",n:"mobile phone with arrow",s:":calling:",c:"symbols",k:"phone mobile arrow incoming"},
{e:"\u{2139\uFE0F}",n:"information",s:":information_source:",c:"symbols",k:"info information source"},
{e:"\u{1F194}",n:"ID button",s:":id:",c:"symbols",k:"id button identity"},
{e:"\u{24C2\uFE0F}",n:"circled M",s:":m:",c:"symbols",k:"metro m circle"},
{e:"\u{1F195}",n:"NEW button",s:":new:",c:"symbols",k:"new button badge"},
{e:"\u{1F199}",n:"UP! button",s:":up:",c:"symbols",k:"up button mark"},
{e:"\u{1F197}",n:"OK button",s:":ok:",c:"symbols",k:"ok button approve"},
{e:"\u{1F192}",n:"COOL button",s:":cool:",c:"symbols",k:"cool button word"},
{e:"\u{1F198}",n:"SOS button",s:":sos:",c:"symbols",k:"sos help emergency"},
{e:"\u{1F1FA\u{1F1F8}}",n:"flag: United States",s:":us:",c:"flags",k:"us usa united states america flag"},
{e:"\u{1F1EC\u{1F1E7}}",n:"flag: United Kingdom",s:":gb:",c:"flags",k:"uk gb united kingdom britain flag"},
{e:"\u{1F1EB\u{1F1F7}}",n:"flag: France",s:":fr:",c:"flags",k:"france french flag"},
{e:"\u{1F1E9\u{1F1EA}}",n:"flag: Germany",s:":de:",c:"flags",k:"germany german flag"},
{e:"\u{1F1EE\u{1F1F9}}",n:"flag: Italy",s:":it:",c:"flags",k:"italy italian flag"},
{e:"\u{1F1EA\u{1F1F8}}",n:"flag: Spain",s:":es:",c:"flags",k:"spain spanish flag"},
{e:"\u{1F1F5\u{1F1F9}}",n:"flag: Portugal",s:":pt:",c:"flags",k:"portugal portuguese flag"},
{e:"\u{1F1E7\u{1F1F7}}",n:"flag: Brazil",s:":br:",c:"flags",k:"brazil brazilian flag"},
{e:"\u{1F1E8\u{1F1E6}}",n:"flag: Canada",s:":ca:",c:"flags",k:"canada canadian flag maple"},
{e:"\u{1F1E6\u{1F1FA}}",n:"flag: Australia",s:":au:",c:"flags",k:"australia australian flag"},
{e:"\u{1F1EF\u{1F1F5}}",n:"flag: Japan",s:":jp:",c:"flags",k:"japan japanese flag"},
{e:"\u{1F1F0\u{1F1F7}}",n:"flag: South Korea",s:":kr:",c:"flags",k:"korea south korean flag"},
{e:"\u{1F1E8\u{1F1F3}}",n:"flag: China",s:":cn:",c:"flags",k:"china chinese flag"},
{e:"\u{1F1EE\u{1F1F3}}",n:"flag: India",s:":in:",c:"flags",k:"india indian flag"},
{e:"\u{1F1F7\u{1F1FA}}",n:"flag: Russia",s:":ru:",c:"flags",k:"russia russian flag"},
{e:"\u{1F1F2\u{1F1FD}}",n:"flag: Mexico",s:":mx:",c:"flags",k:"mexico mexican flag"},
{e:"\u{1F1F3\u{1F1F1}}",n:"flag: Netherlands",s:":nl:",c:"flags",k:"netherlands dutch flag"},
{e:"\u{1F1F8\u{1F1EA}}",n:"flag: Sweden",s:":se:",c:"flags",k:"sweden swedish flag"},
{e:"\u{1F1F3\u{1F1F4}}",n:"flag: Norway",s:":no:",c:"flags",k:"norway norwegian flag"},
{e:"\u{1F1E8\u{1F1ED}}",n:"flag: Switzerland",s:":ch:",c:"flags",k:"switzerland swiss flag"},
{e:"\u{1F1F5\u{1F1F1}}",n:"flag: Poland",s:":pl:",c:"flags",k:"poland polish flag"},
{e:"\u{1F1F9\u{1F1F7}}",n:"flag: Turkey",s:":tr:",c:"flags",k:"turkey turkish flag"},
{e:"\u{1F1F8\u{1F1E6}}",n:"flag: Saudi Arabia",s:":sa:",c:"flags",k:"saudi arabia flag"},
{e:"\u{1F1E6\u{1F1EA}}",n:"flag: United Arab Emirates",s:":ae:",c:"flags",k:"uae emirates dubai flag"},
{e:"\u{1F1EE\u{1F1F1}}",n:"flag: Israel",s:":il:",c:"flags",k:"israel israeli flag"},
{e:"\u{1F1F3\u{1F1FF}}",n:"flag: New Zealand",s:":nz:",c:"flags",k:"new zealand flag kiwi"},
{e:"\u{1F1F8\u{1F1EC}}",n:"flag: Singapore",s:":sg:",c:"flags",k:"singapore flag"},
{e:"\u{1F1F9\u{1F1ED}}",n:"flag: Thailand",s:":th:",c:"flags",k:"thailand thai flag"},
{e:"\u{1F1EE\u{1F1E9}}",n:"flag: Indonesia",s:":id:",c:"flags",k:"indonesia indonesian flag"},
{e:"\u{1F3C1}",n:"chequered flag",s:":checkered_flag:",c:"flags",k:"chequered flag race finish"},
{e:"\u{1F6A9}",n:"triangular flag",s:":triangular_flag:",c:"flags",k:"flag triangular post"},
{e:"\u{1F3F3\uFE0F}",n:"white flag",s:":white_flag:",c:"flags",k:"white flag surrender peace"},
{e:"\u{1F3F4}",n:"black flag",s:":black_flag:",c:"flags",k:"black flag pirate"},
{e:"\u{1F3F3\uFE0F\u200D\u{1F308}}",n:"rainbow flag",s:":rainbow_flag:",c:"flags",k:"rainbow flag pride lgbtq"}
];

var CATEGORIES=[
{id:"all",label:"All"},
{id:"smileys",label:"Smileys"},
{id:"people",label:"People"},
{id:"animals",label:"Animals"},
{id:"food",label:"Food"},
{id:"travel",label:"Travel"},
{id:"activities",label:"Activities"},
{id:"objects",label:"Objects"},
{id:"symbols",label:"Symbols"},
{id:"flags",label:"Flags"}
];

var SKIN_TONES=["","\u{1F3FB}","\u{1F3FC}","\u{1F3FD}","\u{1F3FE}","\u{1F3FF}"];

var currentCat="all";
var currentSearch="";
var currentSkin="";
var recentKey="ep_recent_v1";
var recentList=JSON.parse(localStorage.getItem(recentKey)||"[]");

function getEmoji(item){
  if(item.t&&currentSkin){return item.e+currentSkin;}
  return item.e;
}

function toCodePoints(str){
  var pts=[];
  for(var i=0;i<str.length;i++){
    var c=str.codePointAt(i);
    if(c>0xFFFF){i++;}
    if(c!==0xFE0F&&c!==0x200D){pts.push("U+"+c.toString(16).toUpperCase().padStart(4,"0"));}
  }
  return pts.join(" ");
}

function toHTMLEntities(str){
  var ents=[];
  for(var i=0;i<str.length;i++){
    var c=str.codePointAt(i);
    if(c>0xFFFF){i++;}
    ents.push("&#"+c+";");
  }
  return ents.join("");
}

function filterEmojis(){
  var q=currentSearch.toLowerCase().trim();
  return EMOJIS.filter(function(item){
    if(currentCat!=="all"&&item.c!==currentCat)return false;
    if(!q)return true;
    return(item.n+" "+item.k+" "+item.s).toLowerCase().indexOf(q)!==-1;
  });
}

function renderTabs(){
  var html="";
  CATEGORIES.forEach(function(cat){
    var cls=cat.id===currentCat?"ep-tab active":"ep-tab";
    html+='<button class="'+cls+'" data-cat="'+cat.id+'">'+cat.label+'</button>';
  });
  document.getElementById("epTabs").innerHTML=html;
}

function renderGrid(){
  var items=filterEmojis();
  var grid=document.getElementById("epGrid");
  document.getElementById("epCounter").textContent=items.length+" / "+EMOJIS.length;
  if(items.length===0){
    grid.innerHTML='<div class="ep-no-results">No emojis found for this search.</div>';
    return;
  }
  var html="";
  items.forEach(function(item,idx){
    html+='<button class="ep-emoji" data-idx="'+EMOJIS.indexOf(item)+'" title="'+item.n+'">'+getEmoji(item)+'</button>';
  });
  grid.innerHTML=html;
}

function renderRecent(){
  var el=document.getElementById("epRecent");
  var grid=document.getElementById("epRecentGrid");
  if(recentList.length===0){el.classList.remove("visible");return;}
  el.classList.add("visible");
  var html="";
  recentList.forEach(function(em){
    html+='<button class="ep-emoji" data-recent="'+em+'" title="Recently used">'+em+'</button>';
  });
  grid.innerHTML=html;
}

function showDetail(item){
  var em=getEmoji(item);
  document.getElementById("epDetailEmoji").textContent=em;
  document.getElementById("epDetailName").textContent=item.n;
  document.getElementById("epDetailCat").textContent=item.c.charAt(0).toUpperCase()+item.c.slice(1);
  document.getElementById("epCodeEmoji").textContent=em;
  document.getElementById("epCodeUnicode").textContent=toCodePoints(em);
  document.getElementById("epCodeHTML").textContent=toHTMLEntities(em);
  document.getElementById("epCodeShort").textContent=item.s;
  document.getElementById("epDetail").classList.add("visible");
}

function addRecent(em){
  recentList=recentList.filter(function(r){return r!==em;});
  recentList.unshift(em);
  if(recentList.length>20)recentList=recentList.slice(0,20);
  localStorage.setItem(recentKey,JSON.stringify(recentList));
  renderRecent();
}

function showToast(msg){
  var t=document.getElementById("epToast");
  t.textContent=msg;
  t.classList.add("show");
  clearTimeout(t._tid);
  t._tid=setTimeout(function(){t.classList.remove("show");},1800);
}

function copyText(text){
  navigator.clipboard.writeText(text).then(function(){
    showToast("Copied: "+text);
  });
}

// Event: tabs
document.getElementById("epTabs").addEventListener("click",function(e){
  var btn=e.target.closest(".ep-tab");
  if(!btn)return;
  currentCat=btn.dataset.cat;
  renderTabs();
  renderGrid();
});

// Event: grid click
document.getElementById("epGrid").addEventListener("click",function(e){
  var btn=e.target.closest(".ep-emoji");
  if(!btn)return;
  var idx=parseInt(btn.dataset.idx,10);
  if(isNaN(idx))return;
  var item=EMOJIS[idx];
  var em=getEmoji(item);
  copyText(em);
  addRecent(em);
  showDetail(item);
});

// Event: recent click
document.getElementById("epRecentGrid").addEventListener("click",function(e){
  var btn=e.target.closest(".ep-emoji");
  if(!btn)return;
  var em=btn.dataset.recent;
  if(em){
    copyText(em);
    // find matching EMOJIS entry
    var found=EMOJIS.find(function(item){return item.e===em||getEmoji(item)===em;});
    if(found)showDetail(found);
  }
});

// Event: search
document.getElementById("epSearch").addEventListener("input",function(){
  currentSearch=this.value;
  renderGrid();
});

// Skin tone
window.epSetSkin=function(btn){
  document.querySelectorAll(".ep-skin-btn").forEach(function(b){b.classList.remove("active");});
  btn.classList.add("active");
  currentSkin=btn.dataset.tone;
  renderGrid();
  // update detail if open
  var detail=document.getElementById("epDetail");
  if(detail.classList.contains("visible")){
    var name=document.getElementById("epDetailName").textContent;
    var found=EMOJIS.find(function(item){return item.n===name;});
    if(found)showDetail(found);
  }
};

// Clear recent
window.epClearRecent=function(){
  recentList=[];
  localStorage.setItem(recentKey,JSON.stringify(recentList));
  renderRecent();
};

// Random
window.epRandom=function(){
  var idx=Math.floor(Math.random()*EMOJIS.length);
  var item=EMOJIS[idx];
  var em=getEmoji(item);
  copyText(em);
  addRecent(em);
  showDetail(item);
  // scroll into view in grid
  var btns=document.querySelectorAll("#epGrid .ep-emoji");
  btns.forEach(function(b){
    if(parseInt(b.dataset.idx,10)===idx){
      b.scrollIntoView({block:"nearest",behavior:"smooth"});
      b.style.background="var(--ep-primary)";
      setTimeout(function(){b.style.background="";},600);
    }
  });
};

// Copy value from detail panel
window.epCopyVal=function(id){
  var text=document.getElementById(id).textContent;
  copyText(text);
};

// Init
renderTabs();
renderGrid();
renderRecent();

})();
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Emoji Picker and Search",
      "url": "https://theluckystrike.github.io/tools/emoji-picker/",
      "applicationCategory": "UtilityApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19",
      "description": "Search and copy emojis instantly. Browse by category, find emoji names and codes, copy Unicode or shortcodes."
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://theluckystrike.github.io/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://theluckystrike.github.io/tools/" },
        { "@type": "ListItem", "position": 3, "name": "Emoji Picker", "item": "https://theluckystrike.github.io/tools/emoji-picker/" }
      ]
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How do I copy an emoji from this tool?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Click any emoji in the grid and it will be copied to your clipboard automatically. A confirmation toast will appear at the bottom of the screen. You can also open the detail panel by clicking an emoji, then use the individual copy buttons to copy the Unicode code point, HTML entity, or shortcode format instead of the raw emoji character."
          }
        },
        {
          "@type": "Question",
          "name": "Do emojis look the same on every device?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Each platform uses its own emoji font and design style. Apple, Google, Microsoft, Samsung, and other vendors create their own visual interpretations of each Unicode code point. The underlying character is the same, but the artwork differs."
          }
        },
        {
          "@type": "Question",
          "name": "What is a Unicode code point?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Unicode code point is a numerical value that identifies a specific character in the Unicode standard. It is written in hexadecimal with a U+ prefix, such as U+1F600 for the grinning face."
          }
        },
        {
          "@type": "Question",
          "name": "Can I use emojis in professional emails?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It depends on your workplace culture and audience. Many professionals use emojis sparingly in internal communications, especially in tools like Slack and Teams. For external client-facing emails, conservative industries typically avoid emojis while creative industries use them more freely."
          }
        },
        {
          "@type": "Question",
          "name": "How are new emojis added to the standard?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Anyone can submit an emoji proposal to the Unicode Consortium. Proposals must include evidence of expected usage frequency, distinctiveness from existing emojis, and broad applicability across cultures. The Emoji Subcommittee reviews proposals and recommends candidates for inclusion in the annual Unicode release."
          }
        }
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
