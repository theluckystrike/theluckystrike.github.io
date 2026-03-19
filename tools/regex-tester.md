---
layout: page
title: "Regex Tester Online - Free Regular Expression Tester | Zovo"
description: "Free regex tester online -- test regular expressions with live match highlighting, capture groups, and a quick-reference cheat sheet. Works in your browser."
permalink: /tools/regex-tester/
keywords: "regex tester, regex tester online, regular expression tester, regex checker, regex match, regex validator, test regex"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [regex tester, regular expression, regex validator, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
 :root {
 --rt-primary: #6C5CE7;
 --rt-primary-dark: #5A4BD1;
 --rt-primary-light: #A29BFE;
 --rt-bg: #F8F9FE;
 --rt-surface: #FFFFFF;
 --rt-text: #2D3436;
 --rt-text-muted: #636E72;
 --rt-border: #DFE6E9;
 --rt-success: #00B894;
 --rt-error: #D63031;
 --rt-highlight: rgba(108, 92, 231, 0.18);
 --rt-radius: 12px;
 }
 .rt-wrapper { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--rt-text); max-width: 1200px; margin: 0 auto; padding: 0 16px; line-height: 1.6; }
 .rt-wrapper * { box-sizing: border-box; }
 .rt-hero { text-align: center; padding: 40px 0 28px; }
 .rt-hero h1 { font-size: 2.2rem; font-weight: 700; margin: 0 0 16px; line-height: 1.2; }
 .rt-hero h1 span { color: var(--rt-primary); }
 .rt-intro { font-size: 1.05rem; color: var(--rt-text-muted); max-width: 720px; margin: 0 auto; line-height: 1.7; }
 .rt-main { display: grid; grid-template-columns: 1fr 300px; gap: 20px; margin-bottom: 24px; }
 .rt-editor { display: flex; flex-direction: column; gap: 16px; }
 .rt-panel { background: var(--rt-surface); border: 1px solid var(--rt-border); border-radius: var(--rt-radius); overflow: hidden; box-shadow: 0 2px 12px rgba(108,92,231,0.06); }
 .rt-panel-header { display: flex; align-items: center; justify-content: space-between; padding: 10px 16px; background: var(--rt-bg); border-bottom: 1px solid var(--rt-border); font-size: 0.8rem; font-weight: 600; color: var(--rt-text-muted); text-transform: uppercase; letter-spacing: 0.05em; }
 .rt-pattern-row { display: flex; align-items: center; gap: 8px; padding: 12px 16px; border-bottom: 1px solid var(--rt-border); }
 .rt-pattern-input { flex: 1; border: 1px solid var(--rt-border); border-radius: 8px; padding: 10px 14px; font-family: 'JetBrains Mono', monospace; font-size: 0.9rem; outline: none; transition: border-color 0.15s; }
 .rt-pattern-input:focus { border-color: var(--rt-primary); }
 .rt-flags { display: flex; gap: 4px; }
 .rt-flag { width: 36px; height: 36px; border: 1px solid var(--rt-border); border-radius: 8px; background: var(--rt-surface); font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; font-weight: 600; cursor: pointer; color: var(--rt-text-muted); transition: all 0.15s; display: flex; align-items: center; justify-content: center; }
 .rt-flag.active { background: var(--rt-primary); color: #fff; border-color: var(--rt-primary); }
 .rt-textarea { width: 100%; min-height: 200px; border: none; padding: 16px; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; line-height: 1.7; resize: vertical; outline: none; color: var(--rt-text); background: var(--rt-surface); }
 .rt-textarea::placeholder { color: #B2BEC3; }
 .rt-results { padding: 16px; min-height: 120px; }
 .rt-results-output { font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; line-height: 1.8; word-break: break-all; white-space: pre-wrap; }
 .rt-match { background: var(--rt-highlight); border-radius: 3px; padding: 1px 2px; border-bottom: 2px solid var(--rt-primary); }
 .rt-group-item { font-size: 0.85rem; padding: 6px 12px; border-bottom: 1px solid var(--rt-border); display: flex; justify-content: space-between; }
 .rt-group-item:last-child { border-bottom: none; }
 .rt-group-label { color: var(--rt-text-muted); font-family: 'JetBrains Mono', monospace; font-size: 0.8rem; }
 .rt-group-value { font-family: 'JetBrains Mono', monospace; font-weight: 500; color: var(--rt-primary); }
 .rt-status-bar { display: flex; align-items: center; gap: 16px; padding: 10px 16px; font-size: 0.85rem; color: var(--rt-text-muted); flex-wrap: wrap; }
 .rt-status-bar .rt-match-count { font-weight: 600; color: var(--rt-primary); }
 .rt-status-bar .rt-error-msg { color: var(--rt-error); font-weight: 500; }
 .rt-sidebar { display: flex; flex-direction: column; gap: 16px; }
 .rt-ref-panel { background: var(--rt-surface); border: 1px solid var(--rt-border); border-radius: var(--rt-radius); overflow: hidden; box-shadow: 0 2px 12px rgba(108,92,231,0.06); }
 .rt-ref-header { padding: 10px 16px; background: var(--rt-bg); border-bottom: 1px solid var(--rt-border); font-size: 0.8rem; font-weight: 600; color: var(--rt-text-muted); text-transform: uppercase; letter-spacing: 0.05em; }
 .rt-ref-list { padding: 8px 0; max-height: 520px; overflow-y: auto; }
 .rt-ref-item { display: flex; justify-content: space-between; padding: 6px 16px; font-size: 0.8rem; cursor: pointer; transition: background 0.1s; }
 .rt-ref-item:hover { background: var(--rt-bg); }
 .rt-ref-item code { font-family: 'JetBrains Mono', monospace; color: var(--rt-primary); font-weight: 500; font-size: 0.8rem; }
 .rt-ref-item span { color: var(--rt-text-muted); }
 .rt-btn { display: inline-flex; align-items: center; gap: 6px; padding: 8px 16px; border: none; border-radius: 8px; font-family: 'Inter', sans-serif; font-size: 0.875rem; font-weight: 500; cursor: pointer; transition: all 0.15s; }
 .rt-btn-secondary { background: var(--rt-bg); color: var(--rt-text); border: 1px solid var(--rt-border); }
 .rt-btn-secondary:hover { background: var(--rt-border); }
 .rt-meta { display: flex; justify-content: space-between; align-items: center; padding-top: 12px; font-size: 0.8rem; color: var(--rt-text-muted); border-top: 1px solid var(--rt-border); margin-bottom: 40px; }
 .rt-faq { max-width: 820px; margin: 0 auto 60px; }
 .rt-faq h2 { font-size: 1.5rem; font-weight: 700; margin: 0 0 24px; text-align: center; }
 .rt-faq-item { border: 1px solid var(--rt-border); border-radius: var(--rt-radius); padding: 20px 24px; margin-bottom: 12px; background: var(--rt-surface); box-shadow: 0 1px 4px rgba(108,92,231,0.04); }
 .rt-faq-item h3 { font-size: 1.05rem; font-weight: 600; margin: 0 0 10px; }
 .rt-faq-item p { margin: 0; font-size: 0.95rem; color: var(--rt-text-muted); line-height: 1.7; }
 @media (max-width: 768px) {
 .rt-hero h1 { font-size: 1.6rem; }
 .rt-main { grid-template-columns: 1fr; }
 .rt-pattern-row { flex-wrap: wrap; }
 .rt-ref-list { max-height: 300px; }
 }
</style>

<div class="rt-wrapper" itemscope itemtype="https://schema.org/WebApplication">
 <meta itemprop="name" content="Regex Tester Online">
 <meta itemprop="applicationCategory" content="DeveloperApplication">
 <meta itemprop="operatingSystem" content="Any">
 <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
 <meta itemprop="price" content="0">

 <div class="rt-hero">
 <h1><span>Regex Tester</span> Online</h1>
 <p class="rt-intro">Test your regular expressions with live match highlighting. This free regex tester online shows matches in real time, lists capture groups, and counts results, all inside your browser with zero data sent to any server.</p>
 </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

 <div class="rt-main">
 <div class="rt-editor">
 <div class="rt-panel">
 <div class="rt-panel-header"><span>Pattern & Flags</span></div>
 <div class="rt-pattern-row">
 <input type="text" id="rtPattern" class="rt-pattern-input" placeholder="Enter regex pattern, e.g. \d+">
 <div class="rt-flags">
 <button class="rt-flag active" id="rtFlagG" data-flag="g" title="Global">g</button>
 <button class="rt-flag" id="rtFlagI" data-flag="i" title="Case-insensitive">i</button>
 <button class="rt-flag" id="rtFlagM" data-flag="m" title="Multiline">m</button>
 </div>
 </div>
 <div class="rt-panel-header"><span>Test String</span><button class="rt-btn rt-btn-secondary" onclick="rtLoadSample()" style="padding:4px 10px;font-size:0.75rem;">Sample</button></div>
 <textarea id="rtTestString" class="rt-textarea" placeholder="Type or paste your test string here..."></textarea>
 </div>

 <div class="rt-panel">
 <div class="rt-panel-header"><span>Match Results</span></div>
 <div class="rt-status-bar">
 <span id="rtStatusMsg">Enter a pattern and test string</span>
 </div>
 <div class="rt-results">
 <div id="rtHighlighted" class="rt-results-output"></div>
 </div>
 </div>

 <div class="rt-panel" id="rtGroupsPanel" style="display:none;">
 <div class="rt-panel-header"><span>Capture Groups</span></div>
 <div id="rtGroups"></div>
 </div>
 </div>

 <div class="rt-sidebar">
 <div class="rt-ref-panel">
 <div class="rt-ref-header">Quick Reference</div>
 <div class="rt-ref-list" id="rtRefList">
 <div class="rt-ref-item" data-pattern="."><code>.</code> <span>Any character</span></div>
 <div class="rt-ref-item" data-pattern="\\d"><code>\d</code> <span>Digit [0-9]</span></div>
 <div class="rt-ref-item" data-pattern="\\D"><code>\D</code> <span>Non-digit</span></div>
 <div class="rt-ref-item" data-pattern="\\w"><code>\w</code> <span>Word char</span></div>
 <div class="rt-ref-item" data-pattern="\\W"><code>\W</code> <span>Non-word char</span></div>
 <div class="rt-ref-item" data-pattern="\\s"><code>\s</code> <span>Whitespace</span></div>
 <div class="rt-ref-item" data-pattern="\\S"><code>\S</code> <span>Non-whitespace</span></div>
 <div class="rt-ref-item" data-pattern="^"><code>^</code> <span>Start of string</span></div>
 <div class="rt-ref-item" data-pattern="$"><code>$</code> <span>End of string</span></div>
 <div class="rt-ref-item" data-pattern="\\b"><code>\b</code> <span>Word boundary</span></div>
 <div class="rt-ref-item" data-pattern=""><code></code> <span>0 or more</span></div>
 <div class="rt-ref-item" data-pattern="+"><code>+</code> <span>1 or more</span></div>
 <div class="rt-ref-item" data-pattern="?"><code>?</code> <span>0 or 1</span></div>
 <div class="rt-ref-item" data-pattern="{n}"><code>{n}</code> <span>Exactly n</span></div>
 <div class="rt-ref-item" data-pattern="{n,m}"><code>{n,m}</code> <span>Between n and m</span></div>
 <div class="rt-ref-item" data-pattern="[abc]"><code>[abc]</code> <span>Character set</span></div>
 <div class="rt-ref-item" data-pattern="[^abc]"><code>[^abc]</code> <span>Negated set</span></div>
 <div class="rt-ref-item" data-pattern="(...)"><code>(...)</code> <span>Capture group</span></div>
 <div class="rt-ref-item" data-pattern="(?:...)"><code>(?:...)</code> <span>Non-capture</span></div>
 <div class="rt-ref-item" data-pattern="a|b"><code>a|b</code> <span>Alternation</span></div>
 <div class="rt-ref-item" data-pattern="(?=...)"><code>(?=...)</code> <span>Lookahead</span></div>
 <div class="rt-ref-item" data-pattern="(?!...)"><code>(?!...)</code> <span>Neg. lookahead</span></div>
 </div>
 </div>

 <div class="rt-ref-panel">
 <div class="rt-ref-header">Common Patterns</div>
 <div class="rt-ref-list">
 <div class="rt-ref-item" onclick="rtInsertPattern('[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,}')"><code>Email</code> <span>Click to use</span></div>
 <div class="rt-ref-item" onclick="rtInsertPattern('https?://[^\\s]+')"><code>URL</code> <span>Click to use</span></div>
 <div class="rt-ref-item" onclick="rtInsertPattern('\\b\\d{1,3}\\.\\d{1,3}\\.\\d{1,3}\\.\\d{1,3}\\b')"><code>IPv4</code> <span>Click to use</span></div>
 <div class="rt-ref-item" onclick="rtInsertPattern('#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})')"><code>Hex Color</code> <span>Click to use</span></div>
 <div class="rt-ref-item" onclick="rtInsertPattern('\\d{4}-\\d{2}-\\d{2}')"><code>Date YYYY-MM-DD</code> <span>Click to use</span></div>
 <div class="rt-ref-item" onclick="rtInsertPattern('\\(?(\\d{3})\\)?[-.\\s]?(\\d{3})[-.\\s]?(\\d{4})')"><code>Phone US</code> <span>Click to use</span></div>
 </div>
 </div>
 </div>
 </div>

 <div class="rt-meta">
 <span>All processing happens in your browser</span>
 <span>Zovo Tools</span>
 </div>

 <div class="rt-faq" itemscope itemtype="https://schema.org/FAQPage">
 <h2>Frequently Asked Questions</h2>

 <div class="rt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
 <h3 itemprop="name">What is a regex tester?</h3>
 <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
 <p itemprop="text">A regex tester is a tool that lets you write a regular expression pattern and immediately see how it matches against a test string. This regex tester online highlights every match in real time, lists capture groups, and reports the total match count. It runs entirely in your browser, so nothing is sent to a server and your data stays private.</p>
 </div>
 </div>

 <div class="rt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
 <h3 itemprop="name">What do the g, i, and m flags mean?</h3>
 <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
 <p itemprop="text">The g (global) flag finds all matches instead of stopping at the first one. The i (case-insensitive) flag makes the pattern match regardless of letter casing, so /abc/i matches "ABC". The m (multiline) flag changes ^ and $ to match the start and end of each line rather than the entire string. You can combine any of these flags together.</p>
 </div>
 </div>

 <div class="rt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
 <h3 itemprop="name">What are capture groups in regex?</h3>
 <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
 <p itemprop="text">Capture groups are portions of a regex pattern enclosed in parentheses. When the pattern matches, each group captures the substring that matched its sub-pattern. For example, the pattern (\d{4})-(\d{2})-(\d{2}) applied to "2026-03-18" creates three groups: "2026", "03", and "18". This tool displays all capture groups for every match so you can verify your extraction logic.</p>
 </div>
 </div>

 <div class="rt-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
 <h3 itemprop="name">Is my data safe in this online regex tester?</h3>
 <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
 <p itemprop="text">Yes. This regular expression tester runs entirely in your browser using JavaScript. Your patterns and test strings are never transmitted to any server. You can verify this by watching the Network tab in your browser's developer tools, no requests are made when you type or test patterns. This makes it safe for testing patterns against sensitive data like log files, emails, or configuration values.</p>
 </div>
 </div>
 </div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/diff-checker/" style="color:#00ff88;text-decoration:none;">Diff Checker</a> - Compare two texts side by side</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter/" style="color:#00ff88;text-decoration:none;">JSON Formatter</a> - Format and validate JSON data</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/cron-expression-generator/" style="color:#00ff88;text-decoration:none;">Cron Expression Generator</a> - Build cron expressions visually</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/web-scraper/" style="color:#00ff88;text-decoration:none;">Web Scraper</a> - Extract data from HTML with CSS selectors</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>


 <footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid #2a2a3a;margin-top:3rem;">
 <p>Built by <a href="https://zovo.one" style="color:#6C5CE7;text-decoration:none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color:#6C5CE7;text-decoration:none;">zovo.one</a></p>
 </footer>
</div>

<script type="application/ld+json">
{
 "@context": "https://schema.org",
 "@type": "WebApplication",
 "name": "Regex Tester Online",
 "url": "https://zovo.one/tools/regex-tester/",
 "applicationCategory": "DeveloperApplication",
 "operatingSystem": "Any",
 "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
 "author": { "@type": "Person", "name": "Michael Lip" }
}
</script>

<script>
(function() {
 "use strict";

 var patternEl = document.getElementById("rtPattern");
 var testEl = document.getElementById("rtTestString");
 var highlightedEl = document.getElementById("rtHighlighted");
 var statusEl = document.getElementById("rtStatusMsg");
 var groupsPanel = document.getElementById("rtGroupsPanel");
 var groupsEl = document.getElementById("rtGroups");

 var flags = { g: true, i: false, m: false };

 function getFlags() {
 var f = "";
 if (flags.g) f += "g";
 if (flags.i) f += "i";
 if (flags.m) f += "m";
 return f;
 }

 document.querySelectorAll(".rt-flag").forEach(function(btn) {
 btn.addEventListener("click", function() {
 var f = this.getAttribute("data-flag");
 flags[f] = !flags[f];
 this.classList.toggle("active");
 runTest();
 });
 });

 function escapeHtml(str) {
 return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
 }

 function runTest() {
 var pattern = patternEl.value;
 var testStr = testEl.value;

 groupsPanel.style.display = "none";
 groupsEl.innerHTML = "";

 if (!pattern || !testStr) {
 highlightedEl.innerHTML = escapeHtml(testStr || "");
 statusEl.innerHTML = "Enter a pattern and test string";
 return;
 }

 var regex;
 try {
 regex = new RegExp(pattern, getFlags());
 } catch (e) {
 highlightedEl.innerHTML = escapeHtml(testStr);
 statusEl.innerHTML = '<span class="rt-error-msg">' + escapeHtml(e.message) + '</span>';
 return;
 }

 if (!flags.g) {
 var match = regex.exec(testStr);
 if (!match) {
 highlightedEl.innerHTML = escapeHtml(testStr);
 statusEl.innerHTML = "No matches found";
 return;
 }
 var result = escapeHtml(testStr.substring(0, match.index)) +
 '<span class="rt-match">' + escapeHtml(match[0]) + '</span>' +
 escapeHtml(testStr.substring(match.index + match[0].length));
 highlightedEl.innerHTML = result;
 statusEl.innerHTML = '<span class="rt-match-count">1 match</span> found';
 showGroups([match]);
 return;
 }

 var matches = [];
 var m;
 var safetyCount = 0;
 regex.lastIndex = 0;
 while ((m = regex.exec(testStr)) !== null && safetyCount < 10000) {
 matches.push({ index: m.index, length: m[0].length, value: m[0], groups: Array.from(m) });
 if (m[0].length === 0) { regex.lastIndex++; }
 safetyCount++;
 }

 if (matches.length === 0) {
 highlightedEl.innerHTML = escapeHtml(testStr);
 statusEl.innerHTML = "No matches found";
 return;
 }

 var html = "";
 var lastIndex = 0;
 for (var i = 0; i < matches.length; i++) {
 html += escapeHtml(testStr.substring(lastIndex, matches[i].index));
 html += '<span class="rt-match">' + escapeHtml(matches[i].value) + '</span>';
 lastIndex = matches[i].index + matches[i].length;
 }
 html += escapeHtml(testStr.substring(lastIndex));
 highlightedEl.innerHTML = html;

 var countLabel = matches.length === 1 ? "1 match" : matches.length + " matches";
 statusEl.innerHTML = '<span class="rt-match-count">' + countLabel + '</span> found';

 var groupMatches = matches.filter(function(m) { return m.groups.length > 1; });
 if (groupMatches.length > 0) {
 showGroups(groupMatches.map(function(m) { return m.groups; }));
 }
 }

 function showGroups(matchArrays) {
 var html = "";
 for (var i = 0; i < matchArrays.length; i++) {
 var groups = matchArrays[i];
 if (groups.length <= 1) continue;
 for (var g = 1; g < groups.length; g++) {
 html += '<div class="rt-group-item"><span class="rt-group-label">Match ' + (i + 1) + ', Group ' + g + '</span><span class="rt-group-value">' + escapeHtml(groups[g] || "(empty)") + '</span></div>';
 }
 }
 if (html) {
 groupsPanel.style.display = "block";
 groupsEl.innerHTML = html;
 }
 }

 patternEl.addEventListener("input", runTest);
 testEl.addEventListener("input", runTest);

 window.rtLoadSample = function() {
 patternEl.value = "(\\d{4})-(\\d{2})-(\\d{2})";
 testEl.value = "Today is 2026-03-18 and tomorrow is 2026-03-19.\nThe project started on 2025-01-15.";
 runTest();
 };

 window.rtInsertPattern = function(p) {
 patternEl.value = p;
 runTest();
 };

 document.querySelectorAll(".rt-ref-item[data-pattern]").forEach(function(el) {
 el.addEventListener("click", function() {
 var p = this.getAttribute("data-pattern");
 patternEl.value += p;
 runTest();
 });
 });
})();
</script>
