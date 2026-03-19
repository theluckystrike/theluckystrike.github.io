---
layout: page
title: "Free SQL Formatter — Beautify, Minify & Validate SQL Queries | Zovo"
description: "Free SQL formatter online -- beautify, minify, and format SQL queries with proper indentation, keyword casing, and dialect support. Runs in your browser, no signup needed."
permalink: /tools/sql-formatter/
keywords: "sql formatter, sql beautifier, sql formatter online, format sql query, sql pretty print, sql minifier, sql validator"
date: 2026-03-19
last_modified_at: 2026-03-19
categories: [tools]
tags: [sql formatter, sql beautifier, sql minifier, sql pretty print, developer tools, online tools]
target_keyword: "sql formatter"
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --sqf-primary: #6C5CE7;
    --sqf-primary-dark: #5A4BD1;
    --sqf-primary-light: #A29BFE;
    --sqf-bg: #0d0d14;
    --sqf-surface: #12121a;
    --sqf-surface-alt: #1a1a2e;
    --sqf-text: #e0e0e0;
    --sqf-text-muted: #8888aa;
    --sqf-border: #2a2a3a;
    --sqf-success: #00B894;
    --sqf-error: #D63031;
    --sqf-warning: #FDCB6E;
    --sqf-radius: 12px;
    --sqf-kw: #c792ea;
    --sqf-fn: #82aaff;
    --sqf-str: #c3e88d;
    --sqf-num: #f78c6c;
    --sqf-comment: #546e7a;
  }

  .sqf-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--sqf-text);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .sqf-wrapper * {
    box-sizing: border-box;
  }

  .sqf-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .sqf-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--sqf-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .sqf-hero h1 span {
    color: var(--sqf-primary);
  }

  .sqf-intro {
    font-size: 1.05rem;
    color: var(--sqf-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .sqf-toolbar {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
    margin-bottom: 16px;
    padding: 12px 16px;
    background: var(--sqf-surface);
    border: 1px solid var(--sqf-border);
    border-radius: var(--sqf-radius);
  }

  .sqf-toolbar-spacer {
    flex: 1;
  }

  .sqf-option-group {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 0.85rem;
    color: var(--sqf-text);
  }

  .sqf-option-group label {
    font-weight: 500;
    white-space: nowrap;
    color: var(--sqf-text-muted);
  }

  .sqf-option-group select {
    padding: 6px 10px;
    border: 1px solid var(--sqf-border);
    border-radius: 6px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    background: var(--sqf-surface-alt);
    color: var(--sqf-text);
    cursor: pointer;
  }

  .sqf-option-group select:focus {
    outline: none;
    border-color: var(--sqf-primary);
    box-shadow: 0 0 0 2px rgba(108, 92, 231, 0.25);
  }

  .sqf-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
  }

  .sqf-btn-primary {
    background: var(--sqf-primary);
    color: #fff;
  }

  .sqf-btn-primary:hover {
    background: var(--sqf-primary-dark);
  }

  .sqf-btn-secondary {
    background: var(--sqf-surface-alt);
    color: var(--sqf-text);
    border: 1px solid var(--sqf-border);
  }

  .sqf-btn-secondary:hover {
    background: var(--sqf-border);
  }

  .sqf-btn-success {
    background: var(--sqf-success);
    color: #fff;
  }

  .sqf-btn-success:hover {
    background: #00a884;
  }

  .sqf-btn-warning {
    background: var(--sqf-warning);
    color: #1a1a2e;
  }

  .sqf-btn-warning:hover {
    background: #f0c040;
  }

  .sqf-panel {
    background: var(--sqf-surface);
    border: 1px solid var(--sqf-border);
    border-radius: var(--sqf-radius);
    overflow: hidden;
    margin-bottom: 16px;
  }

  .sqf-panel-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 16px;
    background: var(--sqf-surface-alt);
    border-bottom: 1px solid var(--sqf-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--sqf-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .sqf-panel-actions {
    display: flex;
    gap: 6px;
  }

  .sqf-panel-actions button {
    padding: 4px 10px;
    font-size: 0.75rem;
    border-radius: 6px;
    border: 1px solid var(--sqf-border);
    background: var(--sqf-surface);
    color: var(--sqf-text-muted);
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: all 0.15s;
  }

  .sqf-panel-actions button:hover {
    background: var(--sqf-primary);
    color: #fff;
    border-color: var(--sqf-primary);
  }

  .sqf-editor-wrap {
    display: flex;
    position: relative;
  }

  .sqf-line-numbers {
    width: 44px;
    padding: 16px 8px 16px 4px;
    text-align: right;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    line-height: 1.55;
    color: #555;
    background: var(--sqf-bg);
    border-right: 1px solid var(--sqf-border);
    user-select: none;
    overflow: hidden;
  }

  .sqf-editor {
    flex: 1;
    width: 100%;
    min-height: 360px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    line-height: 1.55;
    resize: vertical;
    outline: none;
    color: var(--sqf-text);
    background: var(--sqf-surface);
    tab-size: 4;
  }

  .sqf-editor::placeholder {
    color: #555;
  }

  .sqf-output-wrap {
    display: flex;
    position: relative;
  }

  .sqf-output {
    flex: 1;
    width: 100%;
    min-height: 200px;
    border: none;
    padding: 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    line-height: 1.55;
    color: var(--sqf-text);
    background: var(--sqf-surface);
    white-space: pre-wrap;
    word-break: break-word;
    overflow-x: auto;
  }

  .sqf-output .kw { color: var(--sqf-kw); font-weight: 600; }
  .sqf-output .fn { color: var(--sqf-fn); }
  .sqf-output .str { color: var(--sqf-str); }
  .sqf-output .num { color: var(--sqf-num); }
  .sqf-output .cm { color: var(--sqf-comment); font-style: italic; }
  .sqf-output .op { color: #89ddff; }

  .sqf-status {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 14px;
    font-size: 0.82rem;
    border-top: 1px solid var(--sqf-border);
    background: var(--sqf-bg);
    min-height: 36px;
  }

  .sqf-status-valid { color: var(--sqf-success); }
  .sqf-status-error { color: var(--sqf-error); }
  .sqf-status-neutral { color: var(--sqf-text-muted); }

  .sqf-history {
    margin-bottom: 16px;
  }

  .sqf-history-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 8px;
  }

  .sqf-history-header span {
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--sqf-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .sqf-history-list {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .sqf-history-item {
    padding: 6px 12px;
    background: var(--sqf-surface);
    border: 1px solid var(--sqf-border);
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--sqf-text-muted);
    cursor: pointer;
    transition: all 0.15s;
    max-width: 280px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .sqf-history-item:hover {
    border-color: var(--sqf-primary);
    color: var(--sqf-text);
  }

  .sqf-content {
    max-width: 820px;
    margin: 48px auto 0;
  }

  .sqf-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 40px 0 16px;
    color: var(--sqf-text);
  }

  .sqf-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 12px;
    color: var(--sqf-text);
  }

  .sqf-content p {
    font-size: 0.95rem;
    color: var(--sqf-text-muted);
    line-height: 1.7;
    margin: 0 0 16px;
  }

  .sqf-content ul, .sqf-content ol {
    padding-left: 24px;
    margin: 0 0 16px;
  }

  .sqf-content li {
    font-size: 0.95rem;
    color: var(--sqf-text-muted);
    line-height: 1.7;
    margin-bottom: 6px;
  }

  .sqf-content code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    background: var(--sqf-surface-alt);
    padding: 2px 6px;
    border-radius: 4px;
    color: var(--sqf-primary-light);
  }

  .sqf-content pre {
    background: var(--sqf-surface);
    border: 1px solid var(--sqf-border);
    border-radius: 8px;
    padding: 16px;
    overflow-x: auto;
    margin: 0 0 16px;
  }

  .sqf-content pre code {
    background: none;
    padding: 0;
    font-size: 0.82rem;
    line-height: 1.6;
  }

  .sqf-faq {
    max-width: 820px;
    margin: 48px auto 60px;
  }

  .sqf-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
  }

  .sqf-faq-item {
    border: 1px solid var(--sqf-border);
    border-radius: var(--sqf-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--sqf-surface);
  }

  .sqf-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--sqf-text);
  }

  .sqf-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--sqf-text-muted);
    line-height: 1.7;
  }

  @media (max-width: 768px) {
    .sqf-hero h1 { font-size: 1.6rem; }
    .sqf-toolbar { flex-direction: column; align-items: stretch; gap: 12px; }
    .sqf-editor { min-height: 200px; }
  }
</style>

<div class="sqf-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="SQL Formatter Online">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="sqf-hero">
    <h1><span>SQL Formatter</span> Online</h1>
    <p class="sqf-intro">Format, beautify, and minify SQL queries with proper indentation and keyword casing. Supports multiple SQL dialects. Everything runs in your browser with zero data sent to any server.</p>
  </div>

  <p style="color:#8888aa;font-size:0.85rem;margin-bottom:2rem;">Last updated: March 2026 | Free to use, no signup required</p>

  <div class="sqf-toolbar">
    <div class="sqf-option-group">
      <label for="sqfDialect">Dialect:</label>
      <select id="sqfDialect">
        <option value="mysql">MySQL</option>
        <option value="postgresql" selected>PostgreSQL</option>
        <option value="sqlite">SQLite</option>
        <option value="sqlserver">SQL Server</option>
        <option value="oracle">Oracle</option>
      </select>
    </div>
    <div class="sqf-option-group">
      <label for="sqfIndent">Indent:</label>
      <select id="sqfIndent">
        <option value="2">2 spaces</option>
        <option value="4" selected>4 spaces</option>
        <option value="tab">Tab</option>
      </select>
    </div>
    <div class="sqf-option-group">
      <label for="sqfKeyCase">Keywords:</label>
      <select id="sqfKeyCase">
        <option value="upper" selected>UPPER</option>
        <option value="lower">lower</option>
        <option value="capitalize">Capitalize</option>
      </select>
    </div>
    <div class="sqf-toolbar-spacer"></div>
    <button class="sqf-btn sqf-btn-secondary" onclick="sqfLoadSample()">Sample Query</button>
    <button class="sqf-btn sqf-btn-secondary" onclick="sqfClear()">Clear</button>
  </div>

  <div class="sqf-panel">
    <div class="sqf-panel-header">
      <span>SQL Input</span>
      <div class="sqf-panel-actions">
        <button onclick="sqfCopyInput()">Copy</button>
      </div>
    </div>
    <div class="sqf-editor-wrap">
      <div class="sqf-line-numbers" id="sqfInputLines">1</div>
      <textarea class="sqf-editor" id="sqfInput" placeholder="Paste or type your SQL query here..." spellcheck="false"></textarea>
    </div>
    <div class="sqf-status" id="sqfInputStatus">
      <span class="sqf-status-neutral">Ready</span>
    </div>
  </div>

  <div style="display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px;">
    <button class="sqf-btn sqf-btn-primary" onclick="sqfFormat()">Format / Beautify</button>
    <button class="sqf-btn sqf-btn-warning" onclick="sqfMinify()">Minify</button>
    <button class="sqf-btn sqf-btn-secondary" onclick="sqfCopyOutput()">Copy Output</button>
    <button class="sqf-btn sqf-btn-secondary" onclick="sqfDownload()">Download .sql</button>
  </div>

  <div class="sqf-panel">
    <div class="sqf-panel-header">
      <span>Formatted Output</span>
      <div class="sqf-panel-actions">
        <button onclick="sqfCopyOutput()">Copy</button>
        <button onclick="sqfDownload()">Download</button>
      </div>
    </div>
    <div class="sqf-output-wrap">
      <div class="sqf-line-numbers" id="sqfOutputLines">1</div>
      <div class="sqf-output" id="sqfOutput"></div>
    </div>
    <div class="sqf-status" id="sqfOutputStatus">
      <span class="sqf-status-neutral">Ready</span>
    </div>
  </div>

  <div class="sqf-history" id="sqfHistorySection" style="display:none;">
    <div class="sqf-history-header">
      <span>Query History</span>
      <button class="sqf-btn sqf-btn-secondary" onclick="sqfClearHistory()" style="padding:4px 10px;font-size:0.75rem;">Clear</button>
    </div>
    <div class="sqf-history-list" id="sqfHistoryList"></div>
  </div>

  <div class="sqf-content">
    <h2>What Is SQL Formatting</h2>
    <p>SQL formatting is the process of restructuring a SQL query so that its clauses, keywords, and expressions follow a consistent visual pattern. A formatted query places each major clause on its own line, indents subqueries and conditions, and applies consistent casing to keywords. The goal is to make the query easier to read, review, and debug without changing what it does.</p>
    <p>Raw SQL often arrives as a single long line, especially when generated by an ORM, exported from a database tool, or copied from a log file. A query like <code>SELECT u.id,u.name FROM users u JOIN orders o ON u.id=o.user_id WHERE o.total>100 ORDER BY o.created_at DESC LIMIT 50</code> is technically valid but difficult to scan. Formatting breaks it into a structured layout where each clause starts on a new line and related conditions are grouped together.</p>

    <h2>Why Format SQL Queries</h2>
    <p>Readable SQL reduces the time it takes to understand what a query does. When reviewing a pull request, a well-formatted query lets the reviewer focus on logic rather than parsing syntax. When debugging a slow query, proper indentation makes it obvious which conditions apply to which joins and where a filter might be missing.</p>
    <p>Consistent formatting also prevents errors during editing. When each condition sits on its own line, adding or removing a WHERE clause is a one-line change rather than a careful insertion into the middle of a long string. Version control diffs become cleaner because a single logical change maps to a small number of changed lines rather than a full rewrite of the entire statement.</p>
    <p>Teams that adopt a shared SQL style guide spend less time discussing formatting during code review. This tool applies the most common formatting conventions automatically, matching the style recommended by the PostgreSQL documentation and widely used in professional codebases.</p>

    <h2>SQL Formatting Best Practices</h2>
    <p>There is no single correct way to format SQL, but a few conventions appear consistently across style guides from companies like GitLab, Mozilla, and the SQL Style Guide by Simon Holywell.</p>
    <ul>
      <li>Write SQL keywords in uppercase. <code>SELECT</code>, <code>FROM</code>, <code>WHERE</code>, <code>JOIN</code>, and other keywords stand out from table and column names when they are in a different case. This is the most widely adopted convention.</li>
      <li>Place each major clause on a new line. Starting <code>SELECT</code>, <code>FROM</code>, <code>WHERE</code>, <code>GROUP BY</code>, <code>HAVING</code>, <code>ORDER BY</code>, and <code>LIMIT</code> on separate lines creates a predictable vertical structure.</li>
      <li>Indent conditions and subqueries. Conditions under <code>WHERE</code> and <code>ON</code> clauses should be indented one level. Subqueries get their own indentation block, making it clear where they start and end.</li>
      <li>Align <code>AND</code>/<code>OR</code> operators at the same indentation level. This makes it easy to count conditions and spot logic errors.</li>
      <li>Use aliases consistently. Short aliases like <code>u</code> for <code>users</code> save horizontal space, but they should be assigned with <code>AS</code> for clarity, especially in longer queries.</li>
      <li>One column per line in SELECT for queries with more than three columns. This makes diffs cleaner and makes it easier to comment out individual columns during debugging.</li>
    </ul>

    <h3>Common SQL Clauses</h3>
    <p>Understanding the major SQL clauses helps when reading formatted output. Here is a reference of the clauses this formatter recognizes and how it handles each one.</p>
    <ul>
      <li><code>SELECT</code> -- retrieves columns. The formatter places it at the start and can list each column on a separate line.</li>
      <li><code>FROM</code> -- specifies the source table. Starts a new line at the base indentation level.</li>
      <li><code>JOIN</code> / <code>INNER JOIN</code> / <code>LEFT JOIN</code> / <code>RIGHT JOIN</code> / <code>FULL JOIN</code> / <code>CROSS JOIN</code> -- each join gets its own line with the <code>ON</code> condition indented beneath it.</li>
      <li><code>WHERE</code> -- filters rows. The keyword starts a new line, and each <code>AND</code>/<code>OR</code> condition is indented.</li>
      <li><code>GROUP BY</code> -- groups rows for aggregation. Starts a new line.</li>
      <li><code>HAVING</code> -- filters groups. Similar treatment to <code>WHERE</code>.</li>
      <li><code>ORDER BY</code> -- sorts the result set. Each sort expression can appear on its own line.</li>
      <li><code>LIMIT</code> / <code>OFFSET</code> / <code>FETCH</code> / <code>TOP</code> -- pagination clauses handled according to the selected dialect.</li>
      <li><code>UNION</code> / <code>INTERSECT</code> / <code>EXCEPT</code> -- set operators get their own line with a blank line above and below for visual separation.</li>
      <li><code>INSERT INTO</code> / <code>UPDATE</code> / <code>DELETE FROM</code> / <code>CREATE TABLE</code> -- DML and DDL statements follow the same indentation rules.</li>
    </ul>

    <h2>How This Formatter Works</h2>
    <p>This tool tokenizes the SQL input into keywords, identifiers, strings, numbers, operators, and punctuation. It then walks the token stream, applying formatting rules based on the selected dialect and options. Keywords are converted to the chosen case, newlines are inserted before major clauses, and indentation is added according to the nesting depth of parentheses and subqueries.</p>
    <p>The syntax highlighter in the output panel colorizes keywords, strings, numbers, functions, and comments. All processing runs in JavaScript inside your browser. No data is transmitted to any server. Query history is stored in your browser's localStorage and never leaves your machine.</p>
  </div>

  <div class="sqf-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="sqf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does the formatter change what my query does?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. The formatter only changes whitespace and keyword casing. It does not alter table names, column names, values, operators, or the logical structure of the query. The formatted output is semantically identical to the input and will produce the same results when run against your database.</p>
      </div>
    </div>

    <div class="sqf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Which SQL dialects are supported?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The formatter supports MySQL, PostgreSQL, SQLite, SQL Server, and Oracle. Each dialect has its own keyword list that includes dialect-specific functions and syntax. For example, SQL Server queries with TOP or NOLOCK are recognized, and MySQL-specific keywords like LIMIT or IFNULL are handled correctly. The core formatting logic is shared across all dialects.</p>
      </div>
    </div>

    <div class="sqf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is my SQL query stored anywhere?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool keeps the last 5 queries in your browser's localStorage for the history feature. This data never leaves your browser and is not sent to any server. You can clear the history at any time using the Clear button in the history section. If you use a private browsing window, history is discarded when the window closes.</p>
      </div>
    </div>

    <div class="sqf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I format stored procedures or DDL statements?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The formatter handles CREATE TABLE, ALTER TABLE, INSERT, UPDATE, DELETE, and other DDL/DML statements in addition to SELECT queries. Stored procedure syntax varies significantly between dialects, so the formatter applies general indentation rules to BEGIN/END blocks and conditional statements. For best results with complex procedures, format them one statement at a time.</p>
      </div>
    </div>

    <div class="sqf-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What does the Minify button do?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Minify compresses the SQL query into a single line by removing all unnecessary whitespace, including newlines, tabs, and extra spaces. It preserves spaces that are required for the query to be valid (such as between keywords and identifiers). Minified SQL is useful when you need to embed a query in a URL parameter, a configuration file, or a logging statement where line breaks would cause problems.</p>
      </div>
    </div>
  </div>

<div style="margin-top:3rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;">
<h2 style="color:#6C5CE7;font-size:1.3rem;margin-bottom:1rem;">Related Tools</h2>
<ul style="list-style:none;padding:0;margin:0;">
<li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter/" style="color:#00ff88;text-decoration:none;">JSON Formatter</a> - Format and validate JSON data</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/regex-tester/" style="color:#00ff88;text-decoration:none;">Regex Tester</a> - Test regular expressions with live matching</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/diff-checker/" style="color:#00ff88;text-decoration:none;">Diff Checker</a> - Compare two texts side by side</li>
<li style="margin-bottom:0.5rem;"><a href="/tools/csv-to-json-converter/" style="color:#00ff88;text-decoration:none;">CSV to JSON Converter</a> - Convert CSV files to JSON</li>
</ul>
</div>

<div style="margin-top:2rem;padding:1.5rem;background:#12121a;border:1px solid #1e1e2e;border-radius:12px;display:flex;gap:1rem;align-items:center;">
<div style="width:48px;height:48px;border-radius:50%;background:#6C5CE7;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;">ML</div>
<div><div style="color:#e0e0e0;font-weight:600;">Michael Lip</div><div style="color:#8888aa;font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:#6C5CE7;">Zovo</a>. Building free developer and productivity tools.</div></div>
</div>

<footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid #2a2a3a;margin-top:3rem;">
  <p>Built by Michael Lip at <a href="https://zovo.one" style="color:#6C5CE7;text-decoration:none;">zovo.one</a></p>
</footer>
</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "SQL Formatter Online",
  "url": "https://zovo.one/tools/sql-formatter/",
  "applicationCategory": "DeveloperApplication",
  "operatingSystem": "Any",
  "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
  "author": { "@type": "Person", "name": "Michael Lip" }
}
</script>

<script>
(function() {
  "use strict";

  var inputEl = document.getElementById("sqfInput");
  var outputEl = document.getElementById("sqfOutput");
  var inputLines = document.getElementById("sqfInputLines");
  var outputLines = document.getElementById("sqfOutputLines");
  var inputStatus = document.getElementById("sqfInputStatus");
  var outputStatus = document.getElementById("sqfOutputStatus");
  var dialectSelect = document.getElementById("sqfDialect");
  var indentSelect = document.getElementById("sqfIndent");
  var keyCaseSelect = document.getElementById("sqfKeyCase");
  var historySection = document.getElementById("sqfHistorySection");
  var historyList = document.getElementById("sqfHistoryList");

  var lastFormattedText = "";

  var baseKeywords = [
    "SELECT", "FROM", "WHERE", "AND", "OR", "NOT", "IN", "IS", "NULL",
    "LIKE", "BETWEEN", "EXISTS", "CASE", "WHEN", "THEN", "ELSE", "END",
    "AS", "ON", "JOIN", "INNER", "LEFT", "RIGHT", "FULL", "OUTER", "CROSS",
    "GROUP", "BY", "ORDER", "ASC", "DESC", "HAVING", "LIMIT", "OFFSET",
    "UNION", "ALL", "INTERSECT", "EXCEPT", "DISTINCT", "INTO", "VALUES",
    "SET", "UPDATE", "DELETE", "INSERT", "CREATE", "TABLE", "ALTER", "DROP",
    "INDEX", "VIEW", "TRIGGER", "IF", "BEGIN", "COMMIT", "ROLLBACK",
    "GRANT", "REVOKE", "WITH", "RECURSIVE", "FETCH", "NEXT", "ROWS",
    "ONLY", "CASCADE", "CONSTRAINT", "PRIMARY", "KEY", "FOREIGN",
    "REFERENCES", "DEFAULT", "CHECK", "UNIQUE", "AUTO_INCREMENT",
    "NOT", "NULL", "TRUE", "FALSE", "REPLACE", "TRUNCATE"
  ];

  var dialectExtras = {
    mysql: ["IFNULL", "COALESCE", "NOW", "CURDATE", "CONCAT", "GROUP_CONCAT", "SUBSTRING", "CHAR_LENGTH", "TRIM", "REPLACE", "MOD", "FLOOR", "CEIL", "ROUND", "RAND", "UUID", "JSON_EXTRACT", "JSON_ARRAY", "JSON_OBJECT", "SHOW", "DESCRIBE", "EXPLAIN", "USE", "DATABASE", "ENGINE", "CHARSET", "COLLATE", "UNSIGNED", "TINYINT", "SMALLINT", "MEDIUMINT", "BIGINT", "FLOAT", "DOUBLE", "DECIMAL", "VARCHAR", "TEXT", "BLOB", "DATE", "DATETIME", "TIMESTAMP", "ENUM"],
    postgresql: ["ILIKE", "SIMILAR", "RETURNING", "SERIAL", "BIGSERIAL", "BOOLEAN", "INTEGER", "BIGINT", "SMALLINT", "REAL", "NUMERIC", "TEXT", "VARCHAR", "CHAR", "DATE", "TIMESTAMP", "TIMESTAMPTZ", "INTERVAL", "JSONB", "JSON", "ARRAY", "UUID", "COALESCE", "NULLIF", "GREATEST", "LEAST", "NOW", "CURRENT_TIMESTAMP", "CURRENT_DATE", "EXTRACT", "TO_CHAR", "TO_DATE", "STRING_AGG", "ARRAY_AGG", "ROW_NUMBER", "RANK", "DENSE_RANK", "OVER", "PARTITION", "LATERAL", "MATERIALIZED", "CONCURRENTLY", "VACUUM", "ANALYZE", "EXPLAIN"],
    sqlite: ["AUTOINCREMENT", "GLOB", "IFNULL", "COALESCE", "TYPEOF", "LENGTH", "SUBSTR", "REPLACE", "TRIM", "UPPER", "LOWER", "ABS", "RANDOM", "ROUND", "DATE", "TIME", "DATETIME", "STRFTIME", "JULIANDAY", "GROUP_CONCAT", "TOTAL", "JSON_EXTRACT", "JSON_GROUP_ARRAY", "PRAGMA", "ATTACH", "DETACH", "VACUUM", "REINDEX", "EXPLAIN"],
    sqlserver: ["TOP", "NOLOCK", "IDENTITY", "NEWID", "GETDATE", "GETUTCDATE", "DATEADD", "DATEDIFF", "DATENAME", "DATEPART", "CONVERT", "CAST", "ISNULL", "COALESCE", "LEN", "CHARINDEX", "STUFF", "REPLACE", "LTRIM", "RTRIM", "UPPER", "LOWER", "ROW_NUMBER", "RANK", "DENSE_RANK", "OVER", "PARTITION", "MERGE", "OUTPUT", "DECLARE", "EXEC", "EXECUTE", "PROCEDURE", "FUNCTION", "NVARCHAR", "VARCHAR", "INT", "BIGINT", "BIT", "FLOAT", "MONEY", "UNIQUEIDENTIFIER", "XML", "GO", "USE", "PRINT", "RAISERROR"],
    oracle: ["ROWNUM", "ROWID", "NVL", "NVL2", "DECODE", "SYSDATE", "SYSTIMESTAMP", "TO_CHAR", "TO_DATE", "TO_NUMBER", "SUBSTR", "INSTR", "LENGTH", "REPLACE", "TRIM", "UPPER", "LOWER", "ROUND", "TRUNC", "MOD", "CEIL", "FLOOR", "LISTAGG", "CONNECT", "PRIOR", "START", "LEVEL", "NOCYCLE", "PIVOT", "UNPIVOT", "MERGE", "RETURNING", "SEQUENCE", "NEXTVAL", "CURRVAL", "DUAL", "VARCHAR2", "NUMBER", "CLOB", "NCLOB", "RAW", "LONG", "PLS_INTEGER", "PACKAGE", "BODY", "EXCEPTION", "PRAGMA"]
  };

  var builtinFunctions = [
    "COUNT", "SUM", "AVG", "MIN", "MAX", "ABS", "ROUND", "CEIL", "FLOOR",
    "UPPER", "LOWER", "TRIM", "LTRIM", "RTRIM", "LENGTH", "SUBSTRING",
    "SUBSTR", "REPLACE", "CONCAT", "COALESCE", "NULLIF", "CAST",
    "CONVERT", "NOW", "CURRENT_TIMESTAMP", "CURRENT_DATE", "EXTRACT",
    "DATE", "YEAR", "MONTH", "DAY", "HOUR", "MINUTE", "SECOND",
    "ROW_NUMBER", "RANK", "DENSE_RANK", "LEAD", "LAG", "FIRST_VALUE",
    "LAST_VALUE", "NTILE"
  ];

  var majorClauses = [
    "SELECT", "FROM", "WHERE", "GROUP BY", "HAVING", "ORDER BY",
    "LIMIT", "OFFSET", "FETCH", "INSERT INTO", "UPDATE", "DELETE FROM",
    "SET", "VALUES", "CREATE TABLE", "ALTER TABLE", "DROP TABLE",
    "CREATE INDEX", "DROP INDEX", "CREATE VIEW", "UNION", "UNION ALL",
    "INTERSECT", "EXCEPT", "WITH"
  ];

  var joinKeywords = [
    "JOIN", "INNER JOIN", "LEFT JOIN", "LEFT OUTER JOIN",
    "RIGHT JOIN", "RIGHT OUTER JOIN", "FULL JOIN", "FULL OUTER JOIN",
    "CROSS JOIN", "NATURAL JOIN"
  ];

  function getAllKeywords() {
    var dialect = dialectSelect.value;
    var all = baseKeywords.slice();
    if (dialectExtras[dialect]) {
      all = all.concat(dialectExtras[dialect]);
    }
    return all;
  }

  function getKeywordSet() {
    var kws = getAllKeywords();
    var set = {};
    for (var i = 0; i < kws.length; i++) set[kws[i].toUpperCase()] = true;
    return set;
  }

  function getFunctionSet() {
    var set = {};
    for (var i = 0; i < builtinFunctions.length; i++) set[builtinFunctions[i].toUpperCase()] = true;
    var dialect = dialectSelect.value;
    if (dialectExtras[dialect]) {
      for (var j = 0; j < dialectExtras[dialect].length; j++) {
        set[dialectExtras[dialect][j].toUpperCase()] = true;
      }
    }
    return set;
  }

  function getIndentStr() {
    var v = indentSelect.value;
    if (v === "tab") return "\t";
    var n = parseInt(v, 10);
    var s = "";
    for (var i = 0; i < n; i++) s += " ";
    return s;
  }

  function applyCase(word) {
    var mode = keyCaseSelect.value;
    if (mode === "upper") return word.toUpperCase();
    if (mode === "lower") return word.toLowerCase();
    return word.charAt(0).toUpperCase() + word.substring(1).toLowerCase();
  }

  /* ── Tokenizer ── */
  function tokenize(sql) {
    var tokens = [];
    var i = 0;
    var len = sql.length;

    while (i < len) {
      // whitespace
      if (/\s/.test(sql[i])) {
        var start = i;
        while (i < len && /\s/.test(sql[i])) i++;
        tokens.push({ type: "ws", value: sql.substring(start, i) });
        continue;
      }
      // single-line comment --
      if (sql[i] === "-" && i + 1 < len && sql[i + 1] === "-") {
        var start = i;
        while (i < len && sql[i] !== "\n") i++;
        tokens.push({ type: "comment", value: sql.substring(start, i) });
        continue;
      }
      // multi-line comment /* */
      if (sql[i] === "/" && i + 1 < len && sql[i + 1] === "*") {
        var start = i;
        i += 2;
        while (i < len - 1 && !(sql[i] === "*" && sql[i + 1] === "/")) i++;
        i += 2;
        tokens.push({ type: "comment", value: sql.substring(start, i) });
        continue;
      }
      // string 'xxx'
      if (sql[i] === "'") {
        var start = i;
        i++;
        while (i < len) {
          if (sql[i] === "'" && i + 1 < len && sql[i + 1] === "'") { i += 2; continue; }
          if (sql[i] === "'") { i++; break; }
          i++;
        }
        tokens.push({ type: "string", value: sql.substring(start, i) });
        continue;
      }
      // double-quoted identifier
      if (sql[i] === '"') {
        var start = i;
        i++;
        while (i < len && sql[i] !== '"') i++;
        if (i < len) i++;
        tokens.push({ type: "ident", value: sql.substring(start, i) });
        continue;
      }
      // backtick-quoted identifier
      if (sql[i] === "`") {
        var start = i;
        i++;
        while (i < len && sql[i] !== "`") i++;
        if (i < len) i++;
        tokens.push({ type: "ident", value: sql.substring(start, i) });
        continue;
      }
      // bracket-quoted identifier [xxx]
      if (sql[i] === "[") {
        var start = i;
        i++;
        while (i < len && sql[i] !== "]") i++;
        if (i < len) i++;
        tokens.push({ type: "ident", value: sql.substring(start, i) });
        continue;
      }
      // numbers
      if (/\d/.test(sql[i]) || (sql[i] === "." && i + 1 < len && /\d/.test(sql[i + 1]))) {
        var start = i;
        if (sql[i] === "0" && i + 1 < len && (sql[i + 1] === "x" || sql[i + 1] === "X")) {
          i += 2;
          while (i < len && /[0-9a-fA-F]/.test(sql[i])) i++;
        } else {
          while (i < len && /[\d.]/.test(sql[i])) i++;
          if (i < len && (sql[i] === "e" || sql[i] === "E")) {
            i++;
            if (i < len && (sql[i] === "+" || sql[i] === "-")) i++;
            while (i < len && /\d/.test(sql[i])) i++;
          }
        }
        tokens.push({ type: "number", value: sql.substring(start, i) });
        continue;
      }
      // operators and punctuation
      if ("(),;.=<>!+-*/%&|^~".indexOf(sql[i]) !== -1) {
        var ch = sql[i];
        if ((ch === "<" || ch === ">" || ch === "!" || ch === "=") && i + 1 < len && sql[i + 1] === "=") {
          tokens.push({ type: "op", value: sql.substring(i, i + 2) });
          i += 2;
        } else if (ch === "<" && i + 1 < len && sql[i + 1] === ">") {
          tokens.push({ type: "op", value: "<>" });
          i += 2;
        } else if (ch === "|" && i + 1 < len && sql[i + 1] === "|") {
          tokens.push({ type: "op", value: "||" });
          i += 2;
        } else if (ch === "(" || ch === ")") {
          tokens.push({ type: "paren", value: ch });
          i++;
        } else if (ch === ",") {
          tokens.push({ type: "comma", value: "," });
          i++;
        } else if (ch === ";") {
          tokens.push({ type: "semicolon", value: ";" });
          i++;
        } else if (ch === ".") {
          tokens.push({ type: "dot", value: "." });
          i++;
        } else {
          tokens.push({ type: "op", value: ch });
          i++;
        }
        continue;
      }
      // word (keyword or identifier)
      if (/[a-zA-Z_@#]/.test(sql[i])) {
        var start = i;
        while (i < len && /[a-zA-Z0-9_@#$]/.test(sql[i])) i++;
        var word = sql.substring(start, i);
        tokens.push({ type: "word", value: word });
        continue;
      }
      // anything else
      tokens.push({ type: "other", value: sql[i] });
      i++;
    }
    return tokens;
  }

  /* ── Formatter ── */
  function formatSQL(sql) {
    var tokens = tokenize(sql);
    var kwSet = getKeywordSet();
    var fnSet = getFunctionSet();
    var indent = getIndentStr();
    var depth = 0;
    var result = [];
    var lineStart = true;

    function indentStr(d) {
      var s = "";
      for (var i = 0; i < d; i++) s += indent;
      return s;
    }

    function pushNewline(d) {
      result.push("\n" + indentStr(d));
      lineStart = true;
    }

    function prevSignificant() {
      for (var i = result.length - 1; i >= 0; i--) {
        var t = result[i].trim();
        if (t !== "") return t;
      }
      return "";
    }

    // Classify tokens
    for (var i = 0; i < tokens.length; i++) {
      var tok = tokens[i];
      if (tok.type === "word") {
        var upper = tok.value.toUpperCase();
        // Check multi-word keywords
        var nextWord = "";
        for (var j = i + 1; j < tokens.length; j++) {
          if (tokens[j].type === "ws") continue;
          if (tokens[j].type === "word") nextWord = tokens[j].value.toUpperCase();
          break;
        }
        var twoWord = upper + " " + nextWord;
        var isMultiKeyword = false;

        // Check for compound clauses
        if (twoWord === "GROUP BY" || twoWord === "ORDER BY" || twoWord === "INSERT INTO" ||
            twoWord === "DELETE FROM" || twoWord === "CREATE TABLE" || twoWord === "ALTER TABLE" ||
            twoWord === "DROP TABLE" || twoWord === "CREATE INDEX" || twoWord === "DROP INDEX" ||
            twoWord === "CREATE VIEW" || twoWord === "UNION ALL" || twoWord === "LEFT JOIN" ||
            twoWord === "RIGHT JOIN" || twoWord === "FULL JOIN" || twoWord === "CROSS JOIN" ||
            twoWord === "INNER JOIN" || twoWord === "NATURAL JOIN") {
          isMultiKeyword = true;
        }

        // Three-word combos
        var thirdWord = "";
        if (isMultiKeyword) {
          for (var k = i + 1; k < tokens.length; k++) {
            if (tokens[k].type === "ws") continue;
            if (tokens[k].type === "word" && tokens[k].value.toUpperCase() === nextWord) {
              for (var m = k + 1; m < tokens.length; m++) {
                if (tokens[m].type === "ws") continue;
                if (tokens[m].type === "word") thirdWord = tokens[m].value.toUpperCase();
                break;
              }
            }
            break;
          }
        }

        var threeWord = upper + " " + nextWord + " " + thirdWord;
        var isThreeWordJoin = (threeWord === "LEFT OUTER JOIN" || threeWord === "RIGHT OUTER JOIN" || threeWord === "FULL OUTER JOIN");

        // Major clause newlines
        if (upper === "SELECT" || upper === "FROM" || upper === "WHERE" ||
            upper === "HAVING" || upper === "LIMIT" || upper === "OFFSET" ||
            upper === "SET" || upper === "VALUES" || upper === "WITH" || upper === "FETCH") {
          if (result.length > 0) pushNewline(depth);
          result.push(applyCase(upper));
          lineStart = false;
          continue;
        }

        if (isMultiKeyword && (twoWord === "GROUP BY" || twoWord === "ORDER BY" ||
            twoWord === "INSERT INTO" || twoWord === "DELETE FROM" ||
            twoWord === "CREATE TABLE" || twoWord === "ALTER TABLE" ||
            twoWord === "DROP TABLE" || twoWord === "CREATE INDEX" ||
            twoWord === "DROP INDEX" || twoWord === "CREATE VIEW")) {
          if (result.length > 0) pushNewline(depth);
          result.push(applyCase(twoWord));
          // skip the next word token and any whitespace between
          for (var sk = i + 1; sk < tokens.length; sk++) {
            if (tokens[sk].type === "ws") continue;
            if (tokens[sk].type === "word") { i = sk; break; }
            break;
          }
          lineStart = false;
          continue;
        }

        if (twoWord === "UNION ALL") {
          pushNewline(depth);
          result.push(applyCase("UNION ALL"));
          for (var sk = i + 1; sk < tokens.length; sk++) {
            if (tokens[sk].type === "ws") continue;
            if (tokens[sk].type === "word") { i = sk; break; }
            break;
          }
          lineStart = false;
          continue;
        }

        if (upper === "UNION" || upper === "INTERSECT" || upper === "EXCEPT") {
          pushNewline(depth);
          result.push(applyCase(upper));
          lineStart = false;
          continue;
        }

        // JOIN keywords
        if (isThreeWordJoin) {
          pushNewline(depth);
          result.push(applyCase(threeWord));
          // skip next two word tokens
          var skipped = 0;
          for (var sk = i + 1; sk < tokens.length && skipped < 2; sk++) {
            if (tokens[sk].type === "ws") continue;
            if (tokens[sk].type === "word") { i = sk; skipped++; }
          }
          lineStart = false;
          continue;
        }

        if (isMultiKeyword && (twoWord === "LEFT JOIN" || twoWord === "RIGHT JOIN" ||
            twoWord === "FULL JOIN" || twoWord === "CROSS JOIN" ||
            twoWord === "INNER JOIN" || twoWord === "NATURAL JOIN")) {
          pushNewline(depth);
          result.push(applyCase(twoWord));
          for (var sk = i + 1; sk < tokens.length; sk++) {
            if (tokens[sk].type === "ws") continue;
            if (tokens[sk].type === "word") { i = sk; break; }
            break;
          }
          lineStart = false;
          continue;
        }

        if (upper === "JOIN") {
          pushNewline(depth);
          result.push(applyCase("JOIN"));
          lineStart = false;
          continue;
        }

        if (upper === "ON") {
          pushNewline(depth + 1);
          result.push(applyCase("ON"));
          lineStart = false;
          continue;
        }

        if (upper === "AND" || upper === "OR") {
          pushNewline(depth + 1);
          result.push(applyCase(upper));
          lineStart = false;
          continue;
        }

        if (upper === "CASE") {
          result.push(" " + applyCase("CASE"));
          depth++;
          lineStart = false;
          continue;
        }

        if (upper === "WHEN" || upper === "ELSE") {
          pushNewline(depth);
          result.push(applyCase(upper));
          lineStart = false;
          continue;
        }

        if (upper === "THEN") {
          result.push(" " + applyCase("THEN"));
          lineStart = false;
          continue;
        }

        if (upper === "END") {
          depth = Math.max(0, depth - 1);
          pushNewline(depth + 1);
          result.push(applyCase("END"));
          lineStart = false;
          continue;
        }

        // Regular keyword or identifier
        if (kwSet[upper]) {
          if (!lineStart) result.push(" ");
          result.push(applyCase(upper));
        } else {
          if (!lineStart) result.push(" ");
          result.push(tok.value);
        }
        lineStart = false;
        continue;
      }

      if (tok.type === "ws") {
        continue;
      }

      if (tok.type === "paren") {
        if (tok.value === "(") {
          result.push(" (");
          depth++;
          pushNewline(depth);
        } else {
          depth = Math.max(0, depth - 1);
          pushNewline(depth);
          result.push(")");
        }
        lineStart = false;
        continue;
      }

      if (tok.type === "comma") {
        result.push(",");
        pushNewline(depth + 1);
        continue;
      }

      if (tok.type === "semicolon") {
        result.push(";");
        pushNewline(depth);
        result.push("");
        continue;
      }

      if (tok.type === "comment") {
        if (!lineStart) result.push(" ");
        result.push(tok.value);
        lineStart = false;
        continue;
      }

      if (tok.type === "string" || tok.type === "number" || tok.type === "ident" ||
          tok.type === "op" || tok.type === "dot" || tok.type === "other") {
        if (!lineStart && tok.type !== "dot") {
          var prev = result.length > 0 ? result[result.length - 1] : "";
          if (prev !== "" && !prev.endsWith(".") && !prev.endsWith("(") && tok.type !== "dot") {
            result.push(" ");
          }
        }
        result.push(tok.value);
        lineStart = false;
        continue;
      }
    }

    var formatted = result.join("").trim();
    // Clean up extra blank lines
    formatted = formatted.replace(/\n{3,}/g, "\n\n");
    // Clean up trailing whitespace on lines
    formatted = formatted.replace(/[ \t]+\n/g, "\n");
    return formatted;
  }

  /* ── Minifier ── */
  function minifySQL(sql) {
    var tokens = tokenize(sql);
    var kwSet = getKeywordSet();
    var parts = [];
    var needSpace = false;

    for (var i = 0; i < tokens.length; i++) {
      var tok = tokens[i];
      if (tok.type === "ws") {
        needSpace = true;
        continue;
      }
      if (tok.type === "comment") {
        continue;
      }
      if (tok.type === "comma" || tok.type === "semicolon" || tok.type === "dot") {
        parts.push(tok.value);
        needSpace = false;
        continue;
      }
      if (tok.type === "paren") {
        if (tok.value === "(") {
          parts.push("(");
          needSpace = false;
        } else {
          parts.push(")");
          needSpace = true;
        }
        continue;
      }
      if (needSpace && parts.length > 0) {
        var last = parts[parts.length - 1];
        if (last !== "(" && last !== ".") {
          parts.push(" ");
        }
      }
      if (tok.type === "word" && kwSet[tok.value.toUpperCase()]) {
        parts.push(applyCase(tok.value.toUpperCase()));
      } else {
        parts.push(tok.value);
      }
      needSpace = false;
    }
    return parts.join("");
  }

  /* ── Syntax Highlighter ── */
  function highlightSQL(sql) {
    var tokens = tokenize(sql);
    var kwSet = getKeywordSet();
    var fnSet = getFunctionSet();
    var html = "";

    for (var i = 0; i < tokens.length; i++) {
      var tok = tokens[i];
      var escaped = escapeHtml(tok.value);

      if (tok.type === "comment") {
        html += '<span class="cm">' + escaped + '</span>';
      } else if (tok.type === "string") {
        html += '<span class="str">' + escaped + '</span>';
      } else if (tok.type === "number") {
        html += '<span class="num">' + escaped + '</span>';
      } else if (tok.type === "word") {
        var upper = tok.value.toUpperCase();
        if (kwSet[upper]) {
          html += '<span class="kw">' + escaped + '</span>';
        } else if (fnSet[upper]) {
          html += '<span class="fn">' + escaped + '</span>';
        } else {
          html += escaped;
        }
      } else if (tok.type === "op") {
        html += '<span class="op">' + escaped + '</span>';
      } else {
        html += escaped;
      }
    }
    return html;
  }

  function escapeHtml(s) {
    return s.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  /* ── Line numbers ── */
  function updateInputLineNumbers() {
    var count = (inputEl.value.match(/\n/g) || []).length + 1;
    var nums = [];
    for (var i = 1; i <= count; i++) nums.push(i);
    inputLines.textContent = nums.join("\n");
  }

  function updateOutputLineNumbers(text) {
    var count = (text.match(/\n/g) || []).length + 1;
    var nums = [];
    for (var i = 1; i <= count; i++) nums.push(i);
    outputLines.textContent = nums.join("\n");
  }

  inputEl.addEventListener("input", updateInputLineNumbers);
  inputEl.addEventListener("scroll", function() {
    inputLines.style.transform = "translateY(-" + inputEl.scrollTop + "px)";
  });

  function setStatus(el, msg, type) {
    el.innerHTML = '<span class="sqf-status-' + type + '">' + escapeHtml(msg) + '</span>';
  }

  /* ── History ── */
  function loadHistory() {
    try {
      var data = localStorage.getItem("sqf_history");
      return data ? JSON.parse(data) : [];
    } catch (e) { return []; }
  }

  function saveHistory(sql) {
    var hist = loadHistory();
    var trimmed = sql.trim();
    if (!trimmed) return;
    // Remove duplicate
    hist = hist.filter(function(h) { return h !== trimmed; });
    hist.unshift(trimmed);
    if (hist.length > 5) hist = hist.slice(0, 5);
    try { localStorage.setItem("sqf_history", JSON.stringify(hist)); } catch (e) {}
    renderHistory();
  }

  function renderHistory() {
    var hist = loadHistory();
    if (hist.length === 0) {
      historySection.style.display = "none";
      return;
    }
    historySection.style.display = "block";
    var html = "";
    for (var i = 0; i < hist.length; i++) {
      var preview = hist[i].substring(0, 60).replace(/\n/g, " ");
      if (hist[i].length > 60) preview += "...";
      html += '<div class="sqf-history-item" data-idx="' + i + '">' + escapeHtml(preview) + '</div>';
    }
    historyList.innerHTML = html;
    historyList.querySelectorAll(".sqf-history-item").forEach(function(el) {
      el.addEventListener("click", function() {
        var idx = parseInt(this.getAttribute("data-idx"), 10);
        var hist = loadHistory();
        if (hist[idx]) {
          inputEl.value = hist[idx];
          updateInputLineNumbers();
          setStatus(inputStatus, "Loaded from history", "valid");
        }
      });
    });
  }

  /* ── Public functions ── */
  window.sqfFormat = function() {
    var sql = inputEl.value.trim();
    if (!sql) {
      setStatus(inputStatus, "No SQL input provided", "error");
      return;
    }
    try {
      var formatted = formatSQL(sql);
      lastFormattedText = formatted;
      outputEl.innerHTML = highlightSQL(formatted);
      updateOutputLineNumbers(formatted);
      saveHistory(sql);
      var lines = formatted.split("\n").length;
      setStatus(inputStatus, "Formatted successfully", "valid");
      setStatus(outputStatus, lines + " lines", "valid");
    } catch (e) {
      setStatus(outputStatus, "Error: " + e.message, "error");
    }
  };

  window.sqfMinify = function() {
    var sql = inputEl.value.trim();
    if (!sql) {
      setStatus(inputStatus, "No SQL input provided", "error");
      return;
    }
    try {
      var minified = minifySQL(sql);
      lastFormattedText = minified;
      outputEl.innerHTML = highlightSQL(minified);
      updateOutputLineNumbers(minified);
      saveHistory(sql);
      setStatus(inputStatus, "Minified successfully", "valid");
      setStatus(outputStatus, minified.length + " characters", "valid");
    } catch (e) {
      setStatus(outputStatus, "Error: " + e.message, "error");
    }
  };

  window.sqfCopyInput = function() {
    if (!inputEl.value) return;
    navigator.clipboard.writeText(inputEl.value).then(function() {
      setStatus(inputStatus, "Copied to clipboard", "valid");
    });
  };

  window.sqfCopyOutput = function() {
    if (!lastFormattedText) return;
    navigator.clipboard.writeText(lastFormattedText).then(function() {
      setStatus(outputStatus, "Copied to clipboard", "valid");
    });
  };

  window.sqfDownload = function() {
    if (!lastFormattedText) return;
    var blob = new Blob([lastFormattedText], { type: "text/sql" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "formatted-query.sql";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  };

  window.sqfClear = function() {
    inputEl.value = "";
    outputEl.innerHTML = "";
    lastFormattedText = "";
    updateInputLineNumbers();
    outputLines.textContent = "1";
    setStatus(inputStatus, "Ready", "neutral");
    setStatus(outputStatus, "Ready", "neutral");
  };

  window.sqfLoadSample = function() {
    var samples = [
      "SELECT u.id, u.username, u.email, p.display_name, COUNT(o.id) AS total_orders, SUM(o.amount) AS total_spent FROM users u INNER JOIN profiles p ON u.id = p.user_id LEFT JOIN orders o ON u.id = o.user_id WHERE u.created_at >= '2025-01-01' AND u.status = 'active' AND (o.amount > 50 OR o.is_premium = true) GROUP BY u.id, u.username, u.email, p.display_name HAVING COUNT(o.id) > 3 ORDER BY total_spent DESC LIMIT 25 OFFSET 0;",
      "WITH monthly_revenue AS (SELECT DATE_TRUNC('month', o.created_at) AS month, p.category, SUM(oi.quantity * oi.unit_price) AS revenue, COUNT(DISTINCT o.id) AS order_count FROM orders o JOIN order_items oi ON o.id = oi.order_id JOIN products p ON oi.product_id = p.id WHERE o.status = 'completed' AND o.created_at >= '2025-01-01' GROUP BY DATE_TRUNC('month', o.created_at), p.category) SELECT month, category, revenue, order_count, ROUND(revenue / order_count, 2) AS avg_order_value, LAG(revenue) OVER (PARTITION BY category ORDER BY month) AS prev_month_revenue FROM monthly_revenue ORDER BY month DESC, revenue DESC;",
      "SELECT e.employee_id, e.first_name, e.last_name, d.department_name, e.salary, CASE WHEN e.salary >= 100000 THEN 'Senior' WHEN e.salary >= 70000 THEN 'Mid-Level' WHEN e.salary >= 40000 THEN 'Junior' ELSE 'Entry' END AS salary_band FROM employees e JOIN departments d ON e.department_id = d.id WHERE d.department_name IN ('Engineering', 'Product', 'Design') AND e.hire_date < '2024-06-01' AND e.is_active = true ORDER BY d.department_name, e.salary DESC;"
    ];
    var idx = Math.floor(Math.random() * samples.length);
    inputEl.value = samples[idx];
    updateInputLineNumbers();
    setStatus(inputStatus, "Sample query loaded", "valid");
    outputEl.innerHTML = "";
    lastFormattedText = "";
    outputLines.textContent = "1";
    setStatus(outputStatus, "Ready", "neutral");
  };

  window.sqfClearHistory = function() {
    try { localStorage.removeItem("sqf_history"); } catch (e) {}
    renderHistory();
  };

  // Init
  updateInputLineNumbers();
  renderHistory();
})();
</script>
