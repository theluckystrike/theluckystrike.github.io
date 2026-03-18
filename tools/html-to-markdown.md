---
layout: page
title: "HTML to Markdown Converter - Free Online Tool | Zovo"
description: "Convert HTML to Markdown instantly -- paste HTML and get clean Markdown output. Handles headings, links, images, tables, code blocks, lists, and more. Free, private, no signup."
permalink: /tools/html-to-markdown/
keywords: "html to markdown, html to markdown converter, convert html to markdown, html to md, html markdown converter online, html to markdown online"
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --hm-primary: #6C5CE7;
    --hm-primary-dark: #5A4BD1;
    --hm-primary-light: #A29BFE;
    --hm-bg: #F8F9FE;
    --hm-surface: #FFFFFF;
    --hm-text: #2D3436;
    --hm-text-muted: #636E72;
    --hm-border: #DFE6E9;
    --hm-success: #00B894;
    --hm-error: #D63031;
    --hm-radius: 12px;
  }

  .hm-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--hm-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .hm-wrapper * {
    box-sizing: border-box;
  }

  .hm-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .hm-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--hm-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .hm-hero h1 span {
    color: var(--hm-primary);
  }

  .hm-intro {
    font-size: 1.05rem;
    color: var(--hm-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Toolbar */
  .hm-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
  }

  .hm-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .hm-btn-primary {
    background: var(--hm-primary);
    color: #fff;
  }

  .hm-btn-primary:hover {
    background: var(--hm-primary-dark);
  }

  .hm-btn-secondary {
    background: var(--hm-bg);
    color: var(--hm-text);
    border: 1px solid var(--hm-border);
  }

  .hm-btn-secondary:hover {
    background: var(--hm-border);
  }

  .hm-btn-success {
    background: var(--hm-success);
    color: #fff;
  }

  .hm-btn-success:hover {
    background: #00A383;
  }

  .hm-btn.copied {
    background: var(--hm-success);
    color: #fff;
  }

  .hm-toolbar-spacer {
    flex: 1;
  }

  /* Editor Layout */
  .hm-editor {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }

  .hm-panel {
    background: var(--hm-surface);
    border: 1px solid var(--hm-border);
    border-radius: var(--hm-radius);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 12px rgba(108, 92, 231, 0.06);
  }

  .hm-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--hm-bg);
    border-bottom: 1px solid var(--hm-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--hm-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .hm-panel-header span {
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }

  .hm-input-area {
    width: 100%;
    min-height: 420px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    resize: vertical;
    color: var(--hm-text);
    background: var(--hm-surface);
    outline: none;
    tab-size: 2;
  }

  .hm-input-area::placeholder {
    color: #B2BEC3;
  }

  .hm-output-area {
    width: 100%;
    min-height: 420px;
    padding: 16px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
    font-size: 0.85rem;
    line-height: 1.6;
    overflow: auto;
    white-space: pre-wrap;
    word-wrap: break-word;
    background: var(--hm-surface);
    color: var(--hm-text);
  }

  /* Status Bar */
  .hm-status {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 24px;
  }

  .hm-status-msg {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.875rem;
    font-weight: 500;
    padding: 6px 14px;
    border-radius: 20px;
  }

  .hm-status-valid {
    background: rgba(0, 184, 148, 0.1);
    color: #00B894;
  }

  .hm-status-invalid {
    background: rgba(214, 48, 49, 0.1);
    color: #D63031;
  }

  .hm-status-empty {
    background: var(--hm-bg);
    color: var(--hm-text-muted);
  }

  .hm-stats {
    display: flex;
    gap: 16px;
    font-size: 0.825rem;
    color: var(--hm-text-muted);
  }

  .hm-stat {
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .hm-stat strong {
    color: var(--hm-text);
    font-weight: 600;
  }

  /* Meta footer */
  .hm-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--hm-text-muted);
    border-top: 1px solid var(--hm-border);
    margin-bottom: 40px;
  }

  /* FAQ Section */
  .hm-faq {
    max-width: 820px;
    margin: 0 auto 60px;
  }

  .hm-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--hm-text);
  }

  .hm-faq-item {
    border: 1px solid var(--hm-border);
    border-radius: var(--hm-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--hm-surface);
    box-shadow: 0 1px 4px rgba(108, 92, 231, 0.04);
  }

  .hm-faq-item h3 {
    font-size: 1rem;
    font-weight: 600;
    margin: 0 0 8px;
    color: var(--hm-text);
  }

  .hm-faq-item p {
    font-size: 0.925rem;
    color: var(--hm-text-muted);
    margin: 0;
    line-height: 1.7;
  }

  /* Content section */
  .hm-content {
    max-width: 820px;
    margin: 0 auto 40px;
  }

  .hm-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 32px 0 12px;
    color: var(--hm-text);
  }

  .hm-content h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin: 24px 0 8px;
    color: var(--hm-text);
  }

  .hm-content p {
    font-size: 0.95rem;
    color: var(--hm-text-muted);
    margin: 0 0 16px;
    line-height: 1.7;
  }

  .hm-content ul {
    padding-left: 20px;
    margin: 0 0 16px;
  }

  .hm-content li {
    font-size: 0.95rem;
    color: var(--hm-text-muted);
    line-height: 1.7;
    margin-bottom: 4px;
  }

  .hm-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    background: var(--hm-bg);
    padding: 2px 6px;
    border-radius: 4px;
    color: var(--hm-primary);
  }

  /* Options bar */
  .hm-options {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 12px;
    font-size: 0.85rem;
    color: var(--hm-text-muted);
  }

  .hm-options label {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    font-weight: 500;
  }

  .hm-options input[type="checkbox"] {
    accent-color: var(--hm-primary);
  }

  .hm-options select {
    padding: 4px 8px;
    border: 1px solid var(--hm-border);
    border-radius: 6px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    background: var(--hm-surface);
    color: var(--hm-text);
    cursor: pointer;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .hm-editor {
      grid-template-columns: 1fr;
    }
    .hm-hero h1 {
      font-size: 1.6rem;
    }
    .hm-input-area,
    .hm-output-area {
      min-height: 280px;
    }
    .hm-toolbar {
      justify-content: center;
    }
    .hm-status {
      justify-content: center;
      text-align: center;
    }
    .hm-stats {
      justify-content: center;
    }
    .hm-meta {
      flex-direction: column;
      text-align: center;
      gap: 8px;
    }
    .hm-options {
      justify-content: center;
    }
  }
</style>

<div class="hm-wrapper">

  <div class="hm-hero">
    <h1><span>HTML to Markdown</span> Converter</h1>
    <p class="hm-intro">Paste any HTML and instantly get clean, readable Markdown. Handles headings, bold, italic, links, images, lists, tables, code blocks, and blockquotes. Runs entirely in your browser -- your data never leaves your device.</p>
  </div>

  <!-- Toolbar -->
  <div class="hm-toolbar">
    <button class="hm-btn hm-btn-primary" onclick="hmConvert()">&#9654; Convert</button>
    <button class="hm-btn hm-btn-secondary" onclick="hmLoadSample()">&#128203; Sample</button>
    <button class="hm-btn hm-btn-secondary" onclick="hmClear()">&#10005; Clear</button>
    <div class="hm-toolbar-spacer"></div>
    <button class="hm-btn hm-btn-secondary" id="hmCopyBtn" onclick="hmCopy()">&#128203; <span id="hmCopyLabel">Copy</span></button>
    <button class="hm-btn hm-btn-success" onclick="hmDownload()">&#11015; Download .md</button>
  </div>

  <!-- Options -->
  <div class="hm-options">
    <label><input type="checkbox" id="hmOptHeadingAtx" checked> ATX headings (#)</label>
    <label><input type="checkbox" id="hmOptHr" checked> Horizontal rules</label>
    <label>
      Link style:
      <select id="hmOptLinkStyle">
        <option value="inline">Inline</option>
        <option value="reference">Reference</option>
      </select>
    </label>
    <label>
      Code block:
      <select id="hmOptCodeFence">
        <option value="backtick">Backticks ```</option>
        <option value="tilde">Tildes ~~~</option>
      </select>
    </label>
  </div>

  <!-- Editor -->
  <div class="hm-editor">
    <div class="hm-panel">
      <div class="hm-panel-header">
        <span>&#128196; HTML Input</span>
        <span id="hmInputSize">0 B</span>
      </div>
      <textarea class="hm-input-area" id="hmInput" placeholder="Paste your HTML here...&#10;&#10;Examples:&#10;<h1>Hello World</h1>&#10;<p>This is a <strong>bold</strong> paragraph.</p>&#10;<a href=&quot;https://example.com&quot;>Link</a>" spellcheck="false"></textarea>
    </div>
    <div class="hm-panel">
      <div class="hm-panel-header">
        <span>&#128221; Markdown Output</span>
        <span id="hmOutputSize">0 B</span>
      </div>
      <pre class="hm-output-area" id="hmOutput"></pre>
    </div>
  </div>

  <!-- Status -->
  <div class="hm-status">
    <span class="hm-status-msg hm-status-empty" id="hmStatusMsg">Paste HTML and click Convert</span>
    <div class="hm-stats">
      <span class="hm-stat">Elements: <strong id="hmStatElements">0</strong></span>
      <span class="hm-stat">Lines: <strong id="hmStatLines">0</strong></span>
    </div>
  </div>

  <!-- Meta -->
  <div class="hm-meta">
    <span>Processing happens entirely in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- FAQ with Schema.org markup -->
  <div class="hm-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="hm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What HTML elements can this converter handle?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This HTML to Markdown converter supports all commonly used HTML elements including headings (h1 through h6), paragraphs, bold and italic text, hyperlinks, images, ordered and unordered lists, nested lists, HTML tables, preformatted code blocks with language hints, inline code, blockquotes, horizontal rules, line breaks, and strikethrough text. It handles nested elements correctly and produces clean, readable Markdown that works in GitHub, GitLab, and any standard Markdown renderer.</p>
      </div>
    </div>

    <div class="hm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does client-side HTML to Markdown conversion work?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The converter parses your HTML using the browser's built-in DOM parser, then walks through each node in the document tree. For each element it encounters, it applies the appropriate Markdown syntax -- for example, wrapping text inside a strong tag with double asterisks, or prefixing heading text with hash symbols. The entire process runs in JavaScript within your browser tab. No data is sent to any server, which makes it safe for converting HTML that contains private or sensitive content.</p>
      </div>
    </div>

    <div class="hm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between ATX and Setext heading styles?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">ATX headings use hash symbols before the text (for example, ## Second Level Heading), while Setext headings underline the text with equals signs or dashes. ATX is the more common style because it supports all six heading levels and is easier to type. This converter defaults to ATX headings since they are the standard on platforms like GitHub, Stack Overflow, and most documentation systems. ATX headings are also easier to scan in source form because the number of hash symbols immediately tells you the nesting depth.</p>
      </div>
    </div>

    <div class="hm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I convert HTML tables to Markdown tables?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The converter reads HTML table elements -- including thead, tbody, tr, th, and td -- and generates GitHub Flavored Markdown (GFM) table syntax with pipe-delimited columns and a separator row of dashes. Column alignment is preserved when specified via CSS or the align attribute. For tables with complex cell content like nested lists or images, the converter flattens the content into a single line per cell, which matches how Markdown table cells work in practice.</p>
      </div>
    </div>

    <div class="hm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my HTML data safe when using this converter?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This tool processes everything inside your browser using JavaScript. Your HTML input is never transmitted over the network, stored on a server, or logged anywhere. You can verify this by opening your browser developer tools and monitoring the Network tab while converting -- no requests are made. This makes it safe for converting internal documentation, emails, CMS exports, or any HTML content that contains confidential information.</p>
      </div>
    </div>

    <div class="hm-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How do I convert HTML to Markdown for GitHub README files?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Paste your HTML source into the input panel and click Convert. The output uses GitHub Flavored Markdown (GFM) syntax including fenced code blocks with language identifiers, pipe tables, task lists, and strikethrough. Copy the result or download it as a .md file and add it directly to your repository. The converter preserves link URLs, image references, and heading structure so your README renders correctly on GitHub without manual cleanup.</p>
      </div>
    </div>

  </div>

  <!-- SEO Content -->
  <div class="hm-content">
    <h2>How to Convert HTML to Markdown</h2>
    <p>Converting HTML to Markdown is a common task for developers, technical writers, and content managers who need to move content between web platforms, content management systems, and documentation repositories. This free converter turns any HTML fragment or full document into clean Markdown with a single click.</p>

    <h3>Supported Conversions</h3>
    <ul>
      <li><strong>Headings</strong> -- <code>&lt;h1&gt;</code> through <code>&lt;h6&gt;</code> become <code>#</code> through <code>######</code></li>
      <li><strong>Bold and italic</strong> -- <code>&lt;strong&gt;</code> and <code>&lt;em&gt;</code> wrap text with <code>**</code> and <code>*</code></li>
      <li><strong>Links</strong> -- <code>&lt;a href="..."&gt;</code> becomes <code>[text](url)</code></li>
      <li><strong>Images</strong> -- <code>&lt;img&gt;</code> becomes <code>![alt](src)</code></li>
      <li><strong>Lists</strong> -- <code>&lt;ul&gt;</code> and <code>&lt;ol&gt;</code> with nested list support</li>
      <li><strong>Tables</strong> -- full GFM table syntax with header separator row</li>
      <li><strong>Code</strong> -- inline <code>&lt;code&gt;</code> and fenced <code>&lt;pre&gt;</code> blocks with language detection</li>
      <li><strong>Blockquotes</strong> -- <code>&lt;blockquote&gt;</code> becomes <code>&gt;</code> prefixed lines</li>
      <li><strong>Horizontal rules</strong> -- <code>&lt;hr&gt;</code> becomes <code>---</code></li>
    </ul>

    <h3>Common Use Cases</h3>
    <p>Web developers use HTML to Markdown conversion when migrating content from WordPress or other CMS platforms into static site generators like Jekyll, Hugo, or Gatsby. Technical writers convert HTML documentation exports into Markdown for version-controlled repositories on GitHub or GitLab. Content teams convert email newsletters and web page copy into Markdown for archiving and repurposing across platforms that natively support Markdown syntax.</p>

    <h2>Why Markdown Over HTML</h2>
    <p>Markdown is simpler to read and write than HTML. A Markdown document carries no tag overhead -- headings are just lines starting with hash symbols, bold text is wrapped in asterisks, and lists are plain dashes or numbers. This makes Markdown files roughly 40-60% shorter than their HTML equivalents, easier to diff in version control, and more portable across platforms. Most developer tools, documentation systems, and collaboration platforms render Markdown natively.</p>
  </div>

</div>

<script>
(function() {
  "use strict";

  var SAMPLE = '<h1>HTML to Markdown Example</h1>\n<p>This is a <strong>bold</strong> and <em>italic</em> paragraph with a <a href="https://example.com">link</a>.</p>\n<h2>Features</h2>\n<ul>\n  <li>Unordered list item one</li>\n  <li>Unordered list item two</li>\n  <li>Nested list:\n    <ul>\n      <li>Sub-item A</li>\n      <li>Sub-item B</li>\n    </ul>\n  </li>\n</ul>\n<h3>Ordered List</h3>\n<ol>\n  <li>First item</li>\n  <li>Second item</li>\n  <li>Third item</li>\n</ol>\n<h3>Code Example</h3>\n<pre><code class="language-javascript">function greet(name) {\n  return "Hello, " + name + "!";\n}</code></pre>\n<p>Inline code: <code>console.log("hi")</code></p>\n<blockquote><p>This is a blockquote with <strong>bold</strong> text.</p></blockquote>\n<h3>Table</h3>\n<table>\n  <thead>\n    <tr><th>Name</th><th>Type</th><th>Description</th></tr>\n  </thead>\n  <tbody>\n    <tr><td>id</td><td>integer</td><td>Unique identifier</td></tr>\n    <tr><td>title</td><td>string</td><td>Display name</td></tr>\n    <tr><td>active</td><td>boolean</td><td>Whether item is enabled</td></tr>\n  </tbody>\n</table>\n<hr>\n<p>Image example: <img src="https://example.com/photo.jpg" alt="Sample image"></p>\n<p>Text with <del>strikethrough</del> formatting.</p>';

  var inputEl = document.getElementById("hmInput");
  var outputEl = document.getElementById("hmOutput");
  var statusEl = document.getElementById("hmStatusMsg");

  // --- Helpers ---

  function byteSize(str) {
    return new Blob([str]).size;
  }

  function formatBytes(bytes) {
    if (bytes === 0) return "0 B";
    if (bytes < 1024) return bytes + " B";
    return (bytes / 1024).toFixed(1) + " KB";
  }

  function updateInputSize() {
    document.getElementById("hmInputSize").textContent = formatBytes(byteSize(inputEl.value));
  }

  function updateOutputSize(text) {
    document.getElementById("hmOutputSize").textContent = formatBytes(byteSize(text || ""));
  }

  function setStatus(type, msg) {
    statusEl.className = "hm-status-msg";
    if (type === "valid") statusEl.classList.add("hm-status-valid");
    else if (type === "invalid") statusEl.classList.add("hm-status-invalid");
    else statusEl.classList.add("hm-status-empty");
    statusEl.textContent = msg;
  }

  function resetCopyBtn() {
    var btn = document.getElementById("hmCopyBtn");
    var label = document.getElementById("hmCopyLabel");
    btn.classList.remove("copied");
    label.textContent = "Copy";
  }

  // --- HTML to Markdown Converter Engine ---

  function htmlToMarkdown(html) {
    var parser = new DOMParser();
    var doc = parser.parseFromString(html, "text/html");
    var refs = [];
    var refIndex = 0;
    var useRefLinks = document.getElementById("hmOptLinkStyle").value === "reference";
    var codeFence = document.getElementById("hmOptCodeFence").value === "tilde" ? "~~~" : "```";

    function escapeMarkdown(text) {
      return text.replace(/([\\`*_\[\]])/g, "\\$1");
    }

    function trimLines(str) {
      return str.replace(/\n{3,}/g, "\n\n").trim();
    }

    function getTextContent(node) {
      var result = "";
      for (var i = 0; i < node.childNodes.length; i++) {
        var child = node.childNodes[i];
        if (child.nodeType === 3) {
          result += child.textContent;
        } else if (child.nodeType === 1) {
          result += convertNode(child);
        }
      }
      return result;
    }

    function convertChildren(node) {
      var result = "";
      for (var i = 0; i < node.childNodes.length; i++) {
        var child = node.childNodes[i];
        if (child.nodeType === 3) {
          var text = child.textContent;
          // Collapse whitespace in inline context
          text = text.replace(/[ \t]+/g, " ");
          result += text;
        } else if (child.nodeType === 1) {
          result += convertNode(child);
        }
      }
      return result;
    }

    function convertListItems(node, ordered) {
      var items = [];
      var index = 1;
      for (var i = 0; i < node.children.length; i++) {
        var child = node.children[i];
        if (child.tagName === "LI") {
          var content = "";
          var sublist = "";
          for (var j = 0; j < child.childNodes.length; j++) {
            var sub = child.childNodes[j];
            if (sub.nodeType === 1 && (sub.tagName === "UL" || sub.tagName === "OL")) {
              sublist += "\n" + convertNode(sub);
            } else if (sub.nodeType === 1) {
              content += convertNode(sub);
            } else if (sub.nodeType === 3) {
              content += sub.textContent.replace(/[ \t]+/g, " ");
            }
          }
          var prefix = ordered ? (index + ". ") : "- ";
          var itemText = prefix + content.trim();
          if (sublist) {
            // Indent sublists
            var indented = sublist.split("\n").map(function(line) {
              return line ? "    " + line : line;
            }).join("\n");
            itemText += indented;
          }
          items.push(itemText);
          index++;
        }
      }
      return items.join("\n");
    }

    function convertTable(node) {
      var rows = [];
      var allTrs = node.querySelectorAll("tr");
      for (var i = 0; i < allTrs.length; i++) {
        var cells = [];
        var cellEls = allTrs[i].querySelectorAll("th, td");
        for (var j = 0; j < cellEls.length; j++) {
          cells.push(convertChildren(cellEls[j]).trim().replace(/\|/g, "\\|").replace(/\n/g, " "));
        }
        rows.push(cells);
      }
      if (rows.length === 0) return "";

      // Determine column widths
      var colCount = 0;
      for (var r = 0; r < rows.length; r++) {
        if (rows[r].length > colCount) colCount = rows[r].length;
      }

      // Pad rows to same column count
      for (var r = 0; r < rows.length; r++) {
        while (rows[r].length < colCount) rows[r].push("");
      }

      var lines = [];
      // Header row
      lines.push("| " + rows[0].join(" | ") + " |");
      // Separator
      var sep = "|";
      for (var c = 0; c < colCount; c++) sep += " --- |";
      lines.push(sep);
      // Data rows
      for (var r = 1; r < rows.length; r++) {
        lines.push("| " + rows[r].join(" | ") + " |");
      }
      return lines.join("\n");
    }

    function convertNode(node) {
      if (node.nodeType === 3) {
        return node.textContent;
      }
      if (node.nodeType !== 1) return "";

      var tag = node.tagName;
      var content;

      switch (tag) {
        case "H1": return "\n\n# " + convertChildren(node).trim() + "\n\n";
        case "H2": return "\n\n## " + convertChildren(node).trim() + "\n\n";
        case "H3": return "\n\n### " + convertChildren(node).trim() + "\n\n";
        case "H4": return "\n\n#### " + convertChildren(node).trim() + "\n\n";
        case "H5": return "\n\n##### " + convertChildren(node).trim() + "\n\n";
        case "H6": return "\n\n###### " + convertChildren(node).trim() + "\n\n";

        case "P":
          content = convertChildren(node).trim();
          return content ? "\n\n" + content + "\n\n" : "";

        case "BR":
          return "  \n";

        case "HR":
          return "\n\n---\n\n";

        case "STRONG":
        case "B":
          content = convertChildren(node).trim();
          return content ? "**" + content + "**" : "";

        case "EM":
        case "I":
          content = convertChildren(node).trim();
          return content ? "*" + content + "*" : "";

        case "DEL":
        case "S":
        case "STRIKE":
          content = convertChildren(node).trim();
          return content ? "~~" + content + "~~" : "";

        case "A":
          content = convertChildren(node).trim();
          var href = node.getAttribute("href") || "";
          var title = node.getAttribute("title");
          if (!content) content = href;
          if (useRefLinks) {
            refIndex++;
            var refId = refIndex;
            if (title) {
              refs.push("[" + refId + "]: " + href + ' "' + title + '"');
            } else {
              refs.push("[" + refId + "]: " + href);
            }
            return "[" + content + "][" + refId + "]";
          } else {
            if (title) {
              return "[" + content + "](" + href + ' "' + title + '")';
            }
            return "[" + content + "](" + href + ")";
          }

        case "IMG":
          var alt = node.getAttribute("alt") || "";
          var src = node.getAttribute("src") || "";
          var imgTitle = node.getAttribute("title");
          if (imgTitle) {
            return "![" + alt + "](" + src + ' "' + imgTitle + '")';
          }
          return "![" + alt + "](" + src + ")";

        case "CODE":
          // Check if parent is PRE (handled by PRE case)
          if (node.parentNode && node.parentNode.tagName === "PRE") {
            return node.textContent;
          }
          content = node.textContent;
          // Use double backticks if content contains backtick
          if (content.indexOf("`") !== -1) {
            return "`` " + content + " ``";
          }
          return "`" + content + "`";

        case "PRE":
          var codeEl = node.querySelector("code");
          var codeText = codeEl ? codeEl.textContent : node.textContent;
          var lang = "";
          if (codeEl) {
            var cls = codeEl.className || "";
            var langMatch = cls.match(/(?:language-|lang-)(\S+)/);
            if (langMatch) lang = langMatch[1];
          }
          return "\n\n" + codeFence + lang + "\n" + codeText + "\n" + codeFence + "\n\n";

        case "BLOCKQUOTE":
          content = convertChildren(node).trim();
          var bqLines = content.split("\n");
          var quoted = bqLines.map(function(line) {
            return "> " + line;
          }).join("\n");
          return "\n\n" + quoted + "\n\n";

        case "UL":
          return "\n\n" + convertListItems(node, false) + "\n\n";

        case "OL":
          return "\n\n" + convertListItems(node, true) + "\n\n";

        case "TABLE":
          return "\n\n" + convertTable(node) + "\n\n";

        case "THEAD":
        case "TBODY":
        case "TFOOT":
        case "TR":
        case "TH":
        case "TD":
          // Handled by convertTable
          return convertChildren(node);

        case "DIV":
        case "SECTION":
        case "ARTICLE":
        case "MAIN":
        case "HEADER":
        case "FOOTER":
        case "NAV":
        case "ASIDE":
          return "\n\n" + convertChildren(node).trim() + "\n\n";

        case "SPAN":
          return convertChildren(node);

        case "SCRIPT":
        case "STYLE":
        case "HEAD":
        case "META":
        case "LINK":
          return "";

        default:
          return convertChildren(node);
      }
    }

    // Convert from body
    var body = doc.body;
    var markdown = convertChildren(body);

    // Append reference links if used
    if (refs.length > 0) {
      markdown += "\n\n" + refs.join("\n") + "\n";
    }

    return trimLines(markdown);
  }

  // --- Core actions ---

  window.hmConvert = function() {
    var raw = inputEl.value.trim();
    resetCopyBtn();
    if (!raw) {
      setStatus("empty", "Paste HTML and click Convert");
      outputEl.textContent = "";
      document.getElementById("hmStatElements").textContent = "0";
      document.getElementById("hmStatLines").textContent = "0";
      updateOutputSize("");
      return;
    }
    try {
      var markdown = htmlToMarkdown(raw);
      outputEl.textContent = markdown;
      outputEl.setAttribute("data-text", markdown);
      setStatus("valid", "Converted successfully");
      // Count elements
      var parser = new DOMParser();
      var tempDoc = parser.parseFromString(raw, "text/html");
      var elCount = tempDoc.body.querySelectorAll("*").length;
      document.getElementById("hmStatElements").textContent = elCount;
      document.getElementById("hmStatLines").textContent = markdown.split("\n").length;
      updateOutputSize(markdown);
    } catch (e) {
      setStatus("invalid", "Conversion error: " + e.message);
      outputEl.textContent = "";
      updateOutputSize("");
    }
    updateInputSize();
  };

  window.hmCopy = function() {
    var text = outputEl.getAttribute("data-text");
    if (!text) return;
    navigator.clipboard.writeText(text).then(function() {
      var btn = document.getElementById("hmCopyBtn");
      var label = document.getElementById("hmCopyLabel");
      btn.classList.add("copied");
      label.textContent = "Copied!";
      setTimeout(function() {
        resetCopyBtn();
      }, 2000);
    });
  };

  window.hmDownload = function() {
    var text = outputEl.getAttribute("data-text");
    if (!text) return;
    var blob = new Blob([text], { type: "text/markdown;charset=utf-8" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "converted.md";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  window.hmClear = function() {
    inputEl.value = "";
    outputEl.textContent = "";
    outputEl.removeAttribute("data-text");
    setStatus("empty", "Paste HTML and click Convert");
    document.getElementById("hmStatElements").textContent = "0";
    document.getElementById("hmStatLines").textContent = "0";
    updateInputSize();
    updateOutputSize("");
    resetCopyBtn();
  };

  window.hmLoadSample = function() {
    inputEl.value = SAMPLE;
    updateInputSize();
    hmConvert();
  };

  // Auto-update input size on typing
  inputEl.addEventListener("input", function() {
    updateInputSize();
  });

  // Ctrl/Cmd + Enter to convert
  inputEl.addEventListener("keydown", function(e) {
    if (e.key === "Enter" && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      hmConvert();
    }
  });

})();
</script>
