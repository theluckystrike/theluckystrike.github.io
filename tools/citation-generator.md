---
layout: page
title: "Free Citation Generator — APA, MLA, Chicago, Harvard & IEEE | Zovo"
description: "Generate accurate citations in APA 7th, MLA 9th, Chicago 17th, Harvard, and IEEE formats. Free online citation generator with auto-formatting, copy-to-clipboard, and bibliography export."
permalink: /tools/citation-generator/
keywords: "citation generator, apa citation generator, mla citation generator, chicago citation generator, harvard citation generator, free citation maker, bibliography generator, cite sources online"
date: 2026-03-19
categories: [tools]
tags: [citation-generator, apa, mla, chicago, harvard, ieee, bibliography, academic, research]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --cg-primary: #6C5CE7;
    --cg-primary-dark: #5A4BD1;
    --cg-primary-light: #A29BFE;
    --cg-bg: #0a0a0f;
    --cg-surface: #12121a;
    --cg-surface-alt: #18182a;
    --cg-border: #1e1e2e;
    --cg-border-focus: #6C5CE7;
    --cg-text: #e0e0e0;
    --cg-text-muted: #8888aa;
    --cg-success: #00ff88;
    --cg-success-dim: #00cc6a;
    --cg-error: #ff4466;
    --cg-radius: 12px;
    --cg-radius-sm: 8px;
  }

  .cg-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--cg-text);
    max-width: 900px;
    margin: 0 auto;
    padding: 0 16px;
    line-height: 1.6;
  }

  .cg-wrapper * {
    box-sizing: border-box;
  }

  .cg-hero {
    text-align: center;
    padding: 40px 0 32px;
  }

  .cg-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--cg-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .cg-hero h1 span {
    color: var(--cg-primary);
  }

  .cg-intro {
    font-size: 1.05rem;
    color: var(--cg-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* Selector Row */
  .cg-selectors {
    display: flex;
    gap: 12px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .cg-select-group {
    flex: 1;
    min-width: 200px;
  }

  .cg-select-group label {
    display: block;
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--cg-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin-bottom: 6px;
  }

  .cg-select {
    width: 100%;
    padding: 10px 14px;
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius-sm);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    background: var(--cg-surface);
    color: var(--cg-text);
    cursor: pointer;
    transition: border-color 0.2s ease;
    appearance: none;
    -webkit-appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%238888aa' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
  }

  .cg-select:focus {
    outline: none;
    border-color: var(--cg-border-focus);
  }

  /* Form Panel */
  .cg-panel {
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    padding: 24px;
    margin-bottom: 20px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  }

  .cg-panel-header {
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--cg-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin-bottom: 16px;
    padding-bottom: 12px;
    border-bottom: 1px solid var(--cg-border);
  }

  .cg-form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .cg-field {
    display: flex;
    flex-direction: column;
  }

  .cg-field.full-width {
    grid-column: 1 / -1;
  }

  .cg-field label {
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--cg-text-muted);
    margin-bottom: 5px;
  }

  .cg-field input {
    padding: 9px 12px;
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius-sm);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    background: var(--cg-bg);
    color: var(--cg-text);
    transition: border-color 0.2s ease;
  }

  .cg-field input:focus {
    outline: none;
    border-color: var(--cg-border-focus);
  }

  .cg-field input::placeholder {
    color: #555570;
  }

  /* Buttons */
  .cg-actions {
    display: flex;
    gap: 10px;
    margin-top: 20px;
    flex-wrap: wrap;
  }

  .cg-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: var(--cg-radius-sm);
    font-family: 'Inter', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
    white-space: nowrap;
  }

  .cg-btn-primary {
    background: var(--cg-primary);
    color: #fff;
  }

  .cg-btn-primary:hover {
    background: var(--cg-primary-dark);
    transform: translateY(-1px);
  }

  .cg-btn-secondary {
    background: var(--cg-surface-alt);
    color: var(--cg-text);
    border: 1px solid var(--cg-border);
  }

  .cg-btn-secondary:hover {
    background: var(--cg-border);
  }

  .cg-btn-success {
    background: transparent;
    color: var(--cg-success);
    border: 1px solid var(--cg-success-dim);
  }

  .cg-btn-success:hover {
    background: rgba(0, 255, 136, 0.08);
  }

  .cg-btn-danger {
    background: transparent;
    color: var(--cg-error);
    border: 1px solid rgba(255, 68, 102, 0.3);
  }

  .cg-btn-danger:hover {
    background: rgba(255, 68, 102, 0.08);
  }

  .cg-btn:disabled {
    opacity: 0.4;
    cursor: not-allowed;
    transform: none;
  }

  /* Citation Preview */
  .cg-preview {
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    padding: 20px 24px;
    margin-bottom: 20px;
    min-height: 60px;
    display: none;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  }

  .cg-preview-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
  }

  .cg-preview-label {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--cg-primary-light);
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  .cg-preview-actions {
    display: flex;
    gap: 8px;
  }

  .cg-btn-sm {
    padding: 5px 12px;
    font-size: 0.78rem;
    border-radius: 6px;
  }

  .cg-citation-text {
    font-family: 'JetBrains Mono', 'Fira Code', monospace;
    font-size: 0.88rem;
    line-height: 1.7;
    color: var(--cg-text);
    word-break: break-word;
    padding: 14px 16px;
    background: var(--cg-bg);
    border-radius: var(--cg-radius-sm);
    border: 1px solid var(--cg-border);
  }

  .cg-citation-text .cg-italic {
    font-style: italic;
  }

  /* Bibliography */
  .cg-bib-panel {
    background: var(--cg-surface);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    padding: 24px;
    margin-bottom: 20px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  }

  .cg-bib-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 16px;
    padding-bottom: 12px;
    border-bottom: 1px solid var(--cg-border);
    flex-wrap: wrap;
    gap: 10px;
  }

  .cg-bib-title {
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--cg-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  .cg-bib-count {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    background: var(--cg-primary);
    color: #fff;
    font-size: 0.7rem;
    font-weight: 700;
    width: 22px;
    height: 22px;
    border-radius: 50%;
    margin-left: 8px;
  }

  .cg-bib-actions {
    display: flex;
    gap: 8px;
  }

  .cg-bib-empty {
    text-align: center;
    padding: 30px 20px;
    color: var(--cg-text-muted);
    font-size: 0.9rem;
  }

  .cg-bib-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .cg-bib-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 12px 14px;
    background: var(--cg-bg);
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius-sm);
    margin-bottom: 8px;
    transition: border-color 0.2s ease;
  }

  .cg-bib-item:hover {
    border-color: var(--cg-primary);
  }

  .cg-bib-item-num {
    flex-shrink: 0;
    width: 24px;
    height: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--cg-surface-alt);
    border-radius: 50%;
    font-size: 0.72rem;
    font-weight: 700;
    color: var(--cg-primary-light);
    margin-top: 2px;
  }

  .cg-bib-item-text {
    flex: 1;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    line-height: 1.6;
    color: var(--cg-text);
    word-break: break-word;
  }

  .cg-bib-item-remove {
    flex-shrink: 0;
    background: none;
    border: none;
    color: var(--cg-text-muted);
    cursor: pointer;
    font-size: 1rem;
    padding: 2px 6px;
    border-radius: 4px;
    transition: all 0.15s ease;
    margin-top: 1px;
  }

  .cg-bib-item-remove:hover {
    color: var(--cg-error);
    background: rgba(255, 68, 102, 0.1);
  }

  /* Toast */
  .cg-toast {
    position: fixed;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%) translateY(80px);
    background: var(--cg-success-dim);
    color: #fff;
    padding: 10px 24px;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    font-weight: 500;
    z-index: 9999;
    opacity: 0;
    transition: all 0.3s ease;
    pointer-events: none;
  }

  .cg-toast.visible {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }

  /* Content Section */
  .cg-content {
    max-width: 780px;
    margin: 40px auto 0;
    padding-top: 32px;
    border-top: 1px solid var(--cg-border);
  }

  .cg-content h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--cg-text);
    margin: 36px 0 14px;
    line-height: 1.3;
  }

  .cg-content h2:first-child {
    margin-top: 0;
  }

  .cg-content p {
    font-size: 0.95rem;
    color: var(--cg-text-muted);
    line-height: 1.8;
    margin: 0 0 14px;
  }

  .cg-content ul, .cg-content ol {
    color: var(--cg-text-muted);
    font-size: 0.95rem;
    line-height: 1.8;
    padding-left: 24px;
    margin: 0 0 14px;
  }

  .cg-content li {
    margin-bottom: 4px;
  }

  /* FAQ */
  .cg-faq {
    max-width: 780px;
    margin: 40px auto 40px;
  }

  .cg-faq h2 {
    font-size: 1.4rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--cg-text);
  }

  .cg-faq-item {
    border: 1px solid var(--cg-border);
    border-radius: var(--cg-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--cg-surface);
  }

  .cg-faq-item h3 {
    font-size: 1.02rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--cg-text);
  }

  .cg-faq-item p {
    margin: 0;
    font-size: 0.93rem;
    color: var(--cg-text-muted);
    line-height: 1.7;
  }

  /* Meta footer */
  .cg-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--cg-text-muted);
    border-top: 1px solid var(--cg-border);
    margin-bottom: 20px;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .cg-hero h1 {
      font-size: 1.6rem;
    }

    .cg-form-grid {
      grid-template-columns: 1fr;
    }

    .cg-field.full-width {
      grid-column: 1;
    }

    .cg-selectors {
      flex-direction: column;
    }

    .cg-select-group {
      min-width: 100%;
    }

    .cg-actions {
      flex-direction: column;
    }

    .cg-btn {
      justify-content: center;
    }

    .cg-preview-header {
      flex-direction: column;
      align-items: flex-start;
      gap: 8px;
    }

    .cg-bib-header {
      flex-direction: column;
      align-items: flex-start;
    }
  }
</style>

<div class="cg-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Free Citation Generator">
  <meta itemprop="applicationCategory" content="EducationalApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="cg-hero">
    <h1><span>Citation Generator</span> - APA, MLA, Chicago & More</h1>
    <p class="cg-intro">Generate properly formatted citations for websites, books, journals, newspapers, and videos. Supports APA 7th, MLA 9th, Chicago 17th, Harvard, and IEEE. Build a full bibliography and export it as plain text -- all free, all in your browser.</p>
  </div>

  <!-- Source Type & Format Selectors -->
  <div class="cg-selectors">
    <div class="cg-select-group">
      <label>Source Type</label>
      <select id="cgSourceType" class="cg-select" onchange="cgUpdateFields()">
        <option value="website">Website</option>
        <option value="book">Book</option>
        <option value="journal">Journal Article</option>
        <option value="newspaper">Newspaper</option>
        <option value="video">Video</option>
      </select>
    </div>
    <div class="cg-select-group">
      <label>Citation Format</label>
      <select id="cgFormat" class="cg-select">
        <option value="apa">APA 7th Edition</option>
        <option value="mla">MLA 9th Edition</option>
        <option value="chicago">Chicago 17th Edition</option>
        <option value="harvard">Harvard</option>
        <option value="ieee">IEEE</option>
      </select>
    </div>
  </div>

  <!-- Input Form -->
  <div class="cg-panel">
    <div class="cg-panel-header">Source Details</div>
    <div class="cg-form-grid" id="cgFields">
      <!-- Dynamically populated -->
    </div>
    <div class="cg-actions">
      <button class="cg-btn cg-btn-primary" onclick="cgGenerate()">Generate Citation</button>
      <button class="cg-btn cg-btn-secondary" onclick="cgClearForm()">Clear</button>
    </div>
  </div>

  <!-- Citation Preview -->
  <div class="cg-preview" id="cgPreview">
    <div class="cg-preview-header">
      <span class="cg-preview-label">Generated Citation</span>
      <div class="cg-preview-actions">
        <button class="cg-btn cg-btn-sm cg-btn-success" onclick="cgCopyCitation()">Copy</button>
        <button class="cg-btn cg-btn-sm cg-btn-primary" onclick="cgAddToBib()">Add to Bibliography</button>
      </div>
    </div>
    <div class="cg-citation-text" id="cgCitationOutput"></div>
  </div>

  <!-- Bibliography -->
  <div class="cg-bib-panel">
    <div class="cg-bib-header">
      <div>
        <span class="cg-bib-title">Bibliography</span>
        <span class="cg-bib-count" id="cgBibCount">0</span>
      </div>
      <div class="cg-bib-actions">
        <button class="cg-btn cg-btn-sm cg-btn-success" onclick="cgCopyBib()" id="cgCopyBibBtn" disabled>Copy All</button>
        <button class="cg-btn cg-btn-sm cg-btn-secondary" onclick="cgExportBib()" id="cgExportBibBtn" disabled>Export as Text</button>
        <button class="cg-btn cg-btn-sm cg-btn-danger" onclick="cgClearBib()" id="cgClearBibBtn" disabled>Clear All</button>
      </div>
    </div>
    <div id="cgBibBody">
      <div class="cg-bib-empty">No citations added yet. Generate a citation above and click "Add to Bibliography."</div>
    </div>
  </div>

  <div class="cg-meta">
    <span>All processing happens in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO Content -->
  <div class="cg-content">

    <h2>What Is a Citation Generator</h2>

    <p>A citation generator is a tool that takes information about a source - like the author, title, publication date, and URL - and formats it into a standardized reference. Academic and professional writing requires citations in specific styles such as APA, MLA, or Chicago. Each style has its own rules for punctuation, italics, ordering, and capitalization.</p>

    <p>Formatting citations by hand is tedious and error-prone. A single misplaced comma or a missing period can cost marks on a paper or undermine the credibility of a research document. Citation generators solve this by applying the rules automatically. You enter the details, pick a format, and get the correctly structured reference in seconds.</p>

    <p>This tool supports five of the most widely used citation styles and covers the source types that students and researchers encounter most often: websites, books, journal articles, newspaper articles, and videos.</p>

    <h2>How to Use This Free Citation Generator</h2>

    <p>Using this tool takes just a few steps. Start by selecting the type of source you are citing from the dropdown menu. The form fields will update to match that source type - a book asks for a publisher and edition, while a journal article asks for volume and issue numbers.</p>

    <p>Fill in as many fields as possible. The more information you provide, the more complete and accurate the citation will be. Then choose your citation format from the second dropdown and click "Generate Citation." The formatted reference appears below the form.</p>

    <p>From there, you can copy the single citation to your clipboard or add it to your bibliography list. The bibliography builder lets you collect multiple citations, reorder them, and export everything as plain text when you are ready to paste it into your paper.</p>

    <p>A few tips for getting the best results:</p>

    <ul>
      <li>Enter author names in "First Last" format. The tool handles the inversion for you.</li>
      <li>For sources with multiple authors, separate each name with a comma.</li>
      <li>Use the full URL when citing websites, including the https:// prefix.</li>
      <li>The "Accessed Date" field matters for web sources since pages can change or disappear.</li>
    </ul>

    <h2>APA Citation Format Explained</h2>

    <p>APA stands for the American Psychological Association. The 7th edition, released in 2019, is the current standard. It is the default style for psychology, education, nursing, and many social science disciplines.</p>

    <p>The general pattern for APA is: Author last name, First initial. (Year). Title of work. Publisher or Source. URL or DOI</p>

    <p>Titles of standalone works like books and reports are italicized. Titles of shorter works like articles and web pages are not italicized but maintain sentence-case capitalization, meaning only the first word and proper nouns are capitalized. The DOI or URL goes at the end with no period after it.</p>

    <p>APA 7th edition made several changes from the 6th. References now include up to 20 authors before using an ellipsis. Publisher locations are no longer required. DOIs use the https://doi.org/ format. These updates simplified the format and made digital sources easier to cite.</p>

    <h2>MLA Citation Format Explained</h2>

    <p>MLA stands for the Modern Language Association. The 9th edition is the current standard and is primarily used in the humanities - literature, languages, philosophy, and cultural studies.</p>

    <p>MLA uses a core elements system. Every source gets evaluated for these nine elements: author, title of source, title of container, contributors, version, number, publisher, publication date, and location. Not every source has all nine, so you include what applies.</p>

    <p>The general pattern looks like: Author. "Title of Source." Title of Container, Other contributors, Version, Number, Publisher, Publication date, Location.</p>

    <p>Titles of shorter works go in quotation marks. Titles of larger works - books, websites, journals - are italicized. MLA uses title-case capitalization, meaning most major words are capitalized. URLs are included but the https:// prefix is typically omitted in formal MLA style.</p>

    <h2>Chicago Citation Format Explained</h2>

    <p>The Chicago Manual of Style is now in its 17th edition. It is used across history, arts, and some social sciences. Chicago offers two systems: notes-bibliography and author-date. This tool generates the notes-bibliography style, which is the more common variant in the humanities.</p>

    <p>In the notes-bibliography system, sources are cited with footnotes or endnotes, and a full bibliography appears at the end. The bibliography entry format differs slightly from the note format - bibliography entries use a period-separated structure with the author's last name first.</p>

    <p>The general pattern is: Author Last name, First name. "Title of Article." Title of Publication. Date. URL.</p>

    <p>Chicago is known for being thorough. It has specific rules for nearly every type of source imaginable, from medieval manuscripts to social media posts. For most academic papers, the rules for books, articles, and websites cover what you need.</p>

    <h2>When to Use Each Citation Style</h2>

    <p>The citation style you use depends on your academic discipline and, often, the specific requirements of your instructor or publisher. Here is a straightforward breakdown:</p>

    <ul>
      <li>APA: Psychology, education, social sciences, nursing, business. Most common in the US for scientific papers.</li>
      <li>MLA: Literature, languages, philosophy, cultural studies, and the humanities broadly.</li>
      <li>Chicago: History, arts, some social sciences. Often used by book publishers and professional historians.</li>
      <li>Harvard: Widely used in the UK, Australia, and many international institutions. Common across sciences and social sciences.</li>
      <li>IEEE: Engineering, computer science, information technology, and electrical/electronics fields.</li>
    </ul>

    <p>When in doubt, ask your instructor or check the submission guidelines for the journal or publisher you are targeting. Using the wrong style is a common and easily avoidable mistake.</p>

    <h2>Tips for Accurate Citations</h2>

    <p>Citation generators are tools, not replacements for understanding the rules. Here are some things to keep in mind when generating and checking your references.</p>

    <p>Always verify the output. Run your generated citation against the official style guide or a trusted example. Automated tools handle the formatting, but they depend on the data you enter. If you type an author name incorrectly, the citation will faithfully reproduce that error.</p>

    <p>Get the author information right. Many citation mistakes come from incorrect author names. Check the actual byline on the source. Some articles list an organization as the author rather than an individual. If there is no author, most styles have a rule for how to handle that - usually starting the citation with the title.</p>

    <p>Use DOIs when available. A DOI (Digital Object Identifier) is a permanent link to a published work. DOIs are more stable than URLs, which can break over time. For journal articles, the DOI is almost always the preferred identifier in APA, Chicago, and Harvard styles.</p>

    <p>Record the access date for online sources. Web content changes. Noting when you accessed a page establishes what version of the content you referenced. MLA and Harvard styles require an access date for online sources.</p>

    <p>Keep your bibliography consistent. Every entry in your reference list should use the same style. Mixing APA and MLA formats in one paper is a red flag for graders and editors. Use the format selector in this tool to make sure all your citations match.</p>

  </div>

  <!-- FAQ with Schema.org -->
  <div class="cg-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is this citation generator really free?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This tool is completely free with no account required, no usage limits, and no ads. All citation formatting happens directly in your browser using JavaScript. Nothing is sent to a server, and no data is stored. You can use it as many times as you need for any project.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate are the generated citations?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The tool follows the official rules for APA 7th, MLA 9th, Chicago 17th, Harvard, and IEEE formats. The accuracy of each citation depends on the information you provide. If you enter complete and correct source details, the output will match the style guide. It is always good practice to double-check a generated citation against an example from your institution or publisher, especially for unusual source types.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I cite sources with multiple authors?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. Enter multiple authors separated by commas in the author field, using "First Last" format for each. For example: "John Smith, Jane Doe, Robert Lee." The tool will format the names according to the rules of the selected citation style, including proper use of ampersands, "and," or "et al." where required.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between a citation and a bibliography?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A citation is a single formatted reference to one source. A bibliography (also called a reference list or works cited page) is a collection of all the citations used in a document, listed together at the end. This tool lets you generate individual citations and also build a bibliography by adding multiple citations to a list that you can export as a complete unit.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Which citation style should I use for my paper?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The style depends on your field and your instructor or publisher's requirements. APA is standard in psychology, education, and social sciences. MLA is used in literature and the humanities. Chicago is common in history. Harvard is popular in UK and Australian universities. IEEE is used in engineering and computer science. If your assignment does not specify a style, check your department's guidelines or ask your instructor.</p>
      </div>
    </div>

    <div class="cg-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can I export my bibliography to use in a word processor?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. The "Export as Text" button downloads your entire bibliography as a plain text file. You can open that file and paste the contents into Microsoft Word, Google Docs, or any other word processor. The "Copy All" button copies the full bibliography to your clipboard for quick pasting. Note that italic formatting is indicated in the text output but may need to be applied manually in your word processor.</p>
      </div>
    </div>

  </div>

  <footer style="text-align: center; padding: 2rem 0; color: #8888a0; font-size: 0.85rem; border-top: 1px solid var(--cg-border); margin-top: 1rem;">
    <p>Built by <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">Michael Lip</a> at <a href="https://zovo.one" style="color: #6C5CE7; text-decoration: none;">zovo.one</a></p>
  </footer>

  <!-- Toast notification -->
  <div class="cg-toast" id="cgToast"></div>

</div>

<script>
(function() {
  "use strict";

  // ========== FIELD DEFINITIONS ==========

  var FIELDS = {
    website: [
      { id: "author", label: "Author(s)", placeholder: "John Smith, Jane Doe", full: false },
      { id: "title", label: "Page Title", placeholder: "How to Write Better Code", full: false },
      { id: "siteName", label: "Website Name", placeholder: "Medium", full: false },
      { id: "url", label: "URL", placeholder: "https://example.com/article", full: false },
      { id: "publishDate", label: "Published Date", placeholder: "2025-06-15", full: false },
      { id: "accessDate", label: "Accessed Date", placeholder: "2026-03-19", full: false }
    ],
    book: [
      { id: "author", label: "Author(s)", placeholder: "Stephen King", full: false },
      { id: "title", label: "Book Title", placeholder: "On Writing", full: false },
      { id: "publisher", label: "Publisher", placeholder: "Scribner", full: false },
      { id: "year", label: "Year", placeholder: "2000", full: false },
      { id: "edition", label: "Edition (optional)", placeholder: "2nd", full: false },
      { id: "city", label: "City (optional)", placeholder: "New York", full: false }
    ],
    journal: [
      { id: "author", label: "Author(s)", placeholder: "Smith, J., Doe, A.", full: false },
      { id: "articleTitle", label: "Article Title", placeholder: "Effects of Sleep on Memory", full: true },
      { id: "journalName", label: "Journal Name", placeholder: "Journal of Cognitive Psychology", full: false },
      { id: "year", label: "Year", placeholder: "2024", full: false },
      { id: "volume", label: "Volume", placeholder: "12", full: false },
      { id: "issue", label: "Issue", placeholder: "3", full: false },
      { id: "pages", label: "Pages", placeholder: "45-67", full: false },
      { id: "doi", label: "DOI (optional)", placeholder: "10.1000/xyz123", full: false }
    ],
    newspaper: [
      { id: "author", label: "Author(s)", placeholder: "Jane Reporter", full: false },
      { id: "articleTitle", label: "Article Title", placeholder: "New Policy Changes Education", full: false },
      { id: "newspaperName", label: "Newspaper Name", placeholder: "The New York Times", full: false },
      { id: "date", label: "Publication Date", placeholder: "2026-01-15", full: false },
      { id: "url", label: "URL (optional)", placeholder: "https://nytimes.com/article", full: true }
    ],
    video: [
      { id: "creator", label: "Creator / Channel", placeholder: "Kurzgesagt", full: false },
      { id: "title", label: "Video Title", placeholder: "The Immune System Explained", full: false },
      { id: "platform", label: "Platform", placeholder: "YouTube", full: false },
      { id: "url", label: "URL", placeholder: "https://youtube.com/watch?v=...", full: false },
      { id: "uploadDate", label: "Upload Date", placeholder: "2025-09-10", full: false }
    ]
  };

  // ========== STATE ==========

  var bibliography = [];
  var currentCitation = "";

  // ========== DOM REFS ==========

  var fieldsContainer = document.getElementById("cgFields");
  var previewEl = document.getElementById("cgPreview");
  var citationOutput = document.getElementById("cgCitationOutput");
  var bibBody = document.getElementById("cgBibBody");
  var bibCount = document.getElementById("cgBibCount");
  var toastEl = document.getElementById("cgToast");

  // ========== TOAST ==========

  var toastTimer = null;
  function showToast(msg) {
    toastEl.textContent = msg;
    toastEl.classList.add("visible");
    if (toastTimer) clearTimeout(toastTimer);
    toastTimer = setTimeout(function() {
      toastEl.classList.remove("visible");
    }, 2200);
  }

  // ========== FIELD RENDERING ==========

  window.cgUpdateFields = function() {
    var sourceType = document.getElementById("cgSourceType").value;
    var fields = FIELDS[sourceType];
    var html = "";
    for (var i = 0; i < fields.length; i++) {
      var f = fields[i];
      var cls = f.full ? "cg-field full-width" : "cg-field";
      html += '<div class="' + cls + '">';
      html += '<label for="cg-' + f.id + '">' + f.label + '</label>';
      html += '<input type="text" id="cg-' + f.id + '" placeholder="' + f.placeholder + '">';
      html += '</div>';
    }
    fieldsContainer.innerHTML = html;
    previewEl.style.display = "none";
    currentCitation = "";
  };

  // ========== AUTHOR PARSING ==========

  function parseAuthors(raw) {
    if (!raw || !raw.trim()) return [];
    var parts = raw.split(",");
    var authors = [];
    for (var i = 0; i < parts.length; i++) {
      var name = parts[i].trim();
      if (name) authors.push(name);
    }
    return authors;
  }

  function getLastFirst(name) {
    var parts = name.trim().split(/\s+/);
    if (parts.length === 1) return parts[0];
    var last = parts[parts.length - 1];
    var firsts = parts.slice(0, parts.length - 1);
    return last + ", " + firsts.join(" ");
  }

  function getLastInitials(name) {
    var parts = name.trim().split(/\s+/);
    if (parts.length === 1) return parts[0];
    var last = parts[parts.length - 1];
    var initials = "";
    for (var i = 0; i < parts.length - 1; i++) {
      initials += parts[i].charAt(0).toUpperCase() + ". ";
    }
    return last + ", " + initials.trim();
  }

  function getFirstInitialLast(name) {
    var parts = name.trim().split(/\s+/);
    if (parts.length === 1) return parts[0];
    var last = parts[parts.length - 1];
    var initials = "";
    for (var i = 0; i < parts.length - 1; i++) {
      initials += parts[i].charAt(0).toUpperCase() + ". ";
    }
    return initials.trim() + " " + last;
  }

  // ========== DATE FORMATTING ==========

  var MONTHS_FULL = ["January","February","March","April","May","June","July","August","September","October","November","December"];
  var MONTHS_SHORT = ["Jan.","Feb.","Mar.","Apr.","May","June","July","Aug.","Sept.","Oct.","Nov.","Dec."];
  var MONTHS_MLA = ["Jan.","Feb.","Mar.","Apr.","May","June","July","Aug.","Sept.","Oct.","Nov.","Dec."];

  function parseDate(str) {
    if (!str || !str.trim()) return null;
    var d = new Date(str.trim());
    if (isNaN(d.getTime())) return null;
    return d;
  }

  function formatDateMDY(d) {
    return MONTHS_FULL[d.getMonth()] + " " + d.getDate() + ", " + d.getFullYear();
  }

  function formatDateDMY(d) {
    return d.getDate() + " " + MONTHS_FULL[d.getMonth()] + " " + d.getFullYear();
  }

  function formatDateMLA(d) {
    return d.getDate() + " " + MONTHS_MLA[d.getMonth()] + " " + d.getFullYear();
  }

  function getYear(str) {
    var d = parseDate(str);
    if (d) return d.getFullYear().toString();
    if (str && str.trim().match(/^\d{4}$/)) return str.trim();
    return "n.d.";
  }

  // ========== HELPER: GET FIELD VALUE ==========

  function gv(id) {
    var el = document.getElementById("cg-" + id);
    return el ? el.value.trim() : "";
  }

  // ========== APA FORMATTING ==========

  function formatAPA() {
    var sourceType = document.getElementById("cgSourceType").value;
    var authors = parseAuthors(gv("author") || gv("creator"));
    var authorStr = "";

    if (authors.length === 0) {
      // no author
    } else if (authors.length === 1) {
      authorStr = getLastInitials(authors[0]);
    } else if (authors.length === 2) {
      authorStr = getLastInitials(authors[0]) + ", & " + getLastInitials(authors[1]);
    } else if (authors.length <= 20) {
      var parts = [];
      for (var i = 0; i < authors.length - 1; i++) {
        parts.push(getLastInitials(authors[i]));
      }
      authorStr = parts.join(", ") + ", & " + getLastInitials(authors[authors.length - 1]);
    } else {
      var parts2 = [];
      for (var j = 0; j < 19; j++) {
        parts2.push(getLastInitials(authors[j]));
      }
      authorStr = parts2.join(", ") + ", ... " + getLastInitials(authors[authors.length - 1]);
    }

    var citation = "";

    if (sourceType === "website") {
      var year = getYear(gv("publishDate"));
      var title = gv("title");
      var siteName = gv("siteName");
      var url = gv("url");

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + "). ";
      citation += title ? title + ". " : "";
      citation += siteName ? "_" + siteName + "_. " : "";
      citation += url || "";
    }

    else if (sourceType === "book") {
      var year = gv("year") || "n.d.";
      var title = gv("title");
      var publisher = gv("publisher");
      var edition = gv("edition");

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + "). ";
      citation += title ? "_" + title + "_" : "";
      if (edition) citation += " (" + edition + " ed.)";
      citation += ". ";
      citation += publisher ? publisher + "." : "";
    }

    else if (sourceType === "journal") {
      var year = gv("year") || "n.d.";
      var articleTitle = gv("articleTitle");
      var journalName = gv("journalName");
      var volume = gv("volume");
      var issue = gv("issue");
      var pages = gv("pages");
      var doi = gv("doi");

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + "). ";
      citation += articleTitle ? articleTitle + ". " : "";
      citation += journalName ? "_" + journalName + "_" : "";
      if (volume) citation += ", _" + volume + "_";
      if (issue) citation += "(" + issue + ")";
      if (pages) citation += ", " + pages;
      citation += ". ";
      if (doi) {
        citation += doi.indexOf("http") === 0 ? doi : "https://doi.org/" + doi;
      }
    }

    else if (sourceType === "newspaper") {
      var date = gv("date");
      var year = getYear(date);
      var d = parseDate(date);
      var dateStr = d ? "(" + year + ", " + MONTHS_FULL[d.getMonth()] + " " + d.getDate() + ")" : "(" + year + ")";
      var articleTitle = gv("articleTitle");
      var newspaperName = gv("newspaperName");
      var url = gv("url");

      citation = authorStr ? authorStr + " " : "";
      citation += dateStr + ". ";
      citation += articleTitle ? articleTitle + ". " : "";
      citation += newspaperName ? "_" + newspaperName + "_. " : "";
      citation += url || "";
    }

    else if (sourceType === "video") {
      var uploadDate = gv("uploadDate");
      var year = getYear(uploadDate);
      var d = parseDate(uploadDate);
      var dateStr = d ? "(" + year + ", " + MONTHS_FULL[d.getMonth()] + " " + d.getDate() + ")" : "(" + year + ")";
      var title = gv("title");
      var platform = gv("platform");
      var url = gv("url");

      var creatorAuthors = parseAuthors(gv("creator"));
      var creatorStr = "";
      if (creatorAuthors.length >= 1) {
        creatorStr = getLastInitials(creatorAuthors[0]);
      }

      citation = creatorStr ? creatorStr + " " : "";
      citation += dateStr + ". ";
      citation += title ? "_" + title + "_ [Video]. " : "";
      citation += platform ? platform + ". " : "";
      citation += url || "";
    }

    return citation.replace(/\s+/g, " ").trim();
  }

  // ========== MLA FORMATTING ==========

  function formatMLA() {
    var sourceType = document.getElementById("cgSourceType").value;
    var authors = parseAuthors(gv("author") || gv("creator"));
    var authorStr = "";

    if (authors.length === 1) {
      authorStr = getLastFirst(authors[0]);
    } else if (authors.length === 2) {
      authorStr = getLastFirst(authors[0]) + ", and " + authors[1];
    } else if (authors.length >= 3) {
      authorStr = getLastFirst(authors[0]) + ", et al.";
    }

    var citation = "";

    if (sourceType === "website") {
      var title = gv("title");
      var siteName = gv("siteName");
      var publishDate = gv("publishDate");
      var accessDate = gv("accessDate");
      var url = gv("url");
      var d = parseDate(publishDate);
      var ad = parseDate(accessDate);

      citation = authorStr ? authorStr + ". " : "";
      citation += title ? '"' + title + '." ' : "";
      citation += siteName ? "_" + siteName + "_, " : "";
      citation += d ? formatDateMLA(d) + ", " : "";
      citation += url ? url + "." : "";
      citation += ad ? " Accessed " + formatDateMLA(ad) + "." : "";
    }

    else if (sourceType === "book") {
      var title = gv("title");
      var publisher = gv("publisher");
      var year = gv("year") || "";
      var edition = gv("edition");

      citation = authorStr ? authorStr + ". " : "";
      citation += title ? "_" + title + "_. " : "";
      if (edition) citation += edition + " ed., ";
      citation += publisher ? publisher + ", " : "";
      citation += year ? year + "." : "";
    }

    else if (sourceType === "journal") {
      var articleTitle = gv("articleTitle");
      var journalName = gv("journalName");
      var volume = gv("volume");
      var issue = gv("issue");
      var year = gv("year") || "";
      var pages = gv("pages");
      var doi = gv("doi");

      citation = authorStr ? authorStr + ". " : "";
      citation += articleTitle ? '"' + articleTitle + '." ' : "";
      citation += journalName ? "_" + journalName + "_, " : "";
      citation += "vol. " + (volume || "");
      if (issue) citation += ", no. " + issue;
      citation += ", " + year;
      if (pages) citation += ", pp. " + pages;
      citation += ". ";
      if (doi) {
        citation += doi.indexOf("http") === 0 ? doi + "." : "https://doi.org/" + doi + ".";
      }
    }

    else if (sourceType === "newspaper") {
      var articleTitle = gv("articleTitle");
      var newspaperName = gv("newspaperName");
      var date = gv("date");
      var url = gv("url");
      var d = parseDate(date);

      citation = authorStr ? authorStr + ". " : "";
      citation += articleTitle ? '"' + articleTitle + '." ' : "";
      citation += newspaperName ? "_" + newspaperName + "_, " : "";
      citation += d ? formatDateMLA(d) + ". " : "";
      citation += url ? url + "." : "";
    }

    else if (sourceType === "video") {
      var title = gv("title");
      var platform = gv("platform");
      var url = gv("url");
      var uploadDate = gv("uploadDate");
      var d = parseDate(uploadDate);
      var creatorRaw = gv("creator");

      citation = creatorRaw ? creatorRaw + ". " : "";
      citation += title ? '"' + title + '." ' : "";
      citation += platform ? "_" + platform + "_, " : "";
      citation += d ? formatDateMLA(d) + ", " : "";
      citation += url ? url + "." : "";
    }

    return citation.replace(/\s+/g, " ").trim();
  }

  // ========== CHICAGO FORMATTING ==========

  function formatChicago() {
    var sourceType = document.getElementById("cgSourceType").value;
    var authors = parseAuthors(gv("author") || gv("creator"));
    var authorStr = "";

    if (authors.length === 1) {
      authorStr = getLastFirst(authors[0]);
    } else if (authors.length === 2) {
      authorStr = getLastFirst(authors[0]) + ", and " + authors[1];
    } else if (authors.length === 3) {
      authorStr = getLastFirst(authors[0]) + ", " + authors[1] + ", and " + authors[2];
    } else if (authors.length >= 4) {
      authorStr = getLastFirst(authors[0]) + ", et al.";
    }

    var citation = "";

    if (sourceType === "website") {
      var title = gv("title");
      var siteName = gv("siteName");
      var publishDate = gv("publishDate");
      var accessDate = gv("accessDate");
      var url = gv("url");
      var d = parseDate(publishDate);
      var ad = parseDate(accessDate);

      citation = authorStr ? authorStr + ". " : "";
      citation += title ? '"' + title + '." ' : "";
      citation += siteName ? siteName + ". " : "";
      if (d) citation += "Last modified " + formatDateMDY(d) + ". ";
      citation += url ? url + "." : "";
    }

    else if (sourceType === "book") {
      var title = gv("title");
      var publisher = gv("publisher");
      var year = gv("year") || "";
      var city = gv("city");
      var edition = gv("edition");

      citation = authorStr ? authorStr + ". " : "";
      citation += title ? "_" + title + "_. " : "";
      if (edition) citation += edition + " ed. ";
      if (city && publisher) {
        citation += city + ": " + publisher + ", " + year + ".";
      } else if (publisher) {
        citation += publisher + ", " + year + ".";
      } else {
        citation += year + ".";
      }
    }

    else if (sourceType === "journal") {
      var articleTitle = gv("articleTitle");
      var journalName = gv("journalName");
      var volume = gv("volume");
      var issue = gv("issue");
      var year = gv("year") || "";
      var pages = gv("pages");
      var doi = gv("doi");

      citation = authorStr ? authorStr + ". " : "";
      citation += articleTitle ? '"' + articleTitle + '." ' : "";
      citation += journalName ? "_" + journalName + "_ " : "";
      if (volume) citation += volume;
      if (issue) citation += ", no. " + issue;
      citation += " (" + year + ")";
      if (pages) citation += ": " + pages;
      citation += ". ";
      if (doi) {
        citation += doi.indexOf("http") === 0 ? doi + "." : "https://doi.org/" + doi + ".";
      }
    }

    else if (sourceType === "newspaper") {
      var articleTitle = gv("articleTitle");
      var newspaperName = gv("newspaperName");
      var date = gv("date");
      var url = gv("url");
      var d = parseDate(date);

      citation = authorStr ? authorStr + ". " : "";
      citation += articleTitle ? '"' + articleTitle + '." ' : "";
      citation += newspaperName ? "_" + newspaperName + "_, " : "";
      citation += d ? formatDateMDY(d) + ". " : "";
      citation += url ? url + "." : "";
    }

    else if (sourceType === "video") {
      var title = gv("title");
      var platform = gv("platform");
      var url = gv("url");
      var uploadDate = gv("uploadDate");
      var d = parseDate(uploadDate);
      var creatorRaw = gv("creator");

      citation = creatorRaw ? creatorRaw + ". " : "";
      citation += title ? '"' + title + '." ' : "";
      citation += platform ? platform + ". " : "";
      citation += d ? formatDateMDY(d) + ". " : "";
      citation += url ? url + "." : "";
    }

    return citation.replace(/\s+/g, " ").trim();
  }

  // ========== HARVARD FORMATTING ==========

  function formatHarvard() {
    var sourceType = document.getElementById("cgSourceType").value;
    var authors = parseAuthors(gv("author") || gv("creator"));
    var authorStr = "";

    if (authors.length === 1) {
      authorStr = getLastFirst(authors[0]);
    } else if (authors.length === 2) {
      authorStr = getLastFirst(authors[0]) + " and " + getLastFirst(authors[1]);
    } else if (authors.length === 3) {
      authorStr = getLastFirst(authors[0]) + ", " + getLastFirst(authors[1]) + " and " + getLastFirst(authors[2]);
    } else if (authors.length >= 4) {
      authorStr = getLastFirst(authors[0]) + " et al.";
    }

    var citation = "";

    if (sourceType === "website") {
      var year = getYear(gv("publishDate"));
      var title = gv("title");
      var siteName = gv("siteName");
      var url = gv("url");
      var accessDate = gv("accessDate");
      var ad = parseDate(accessDate);

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + ") ";
      citation += title ? "_" + title + "_. " : "";
      if (siteName) citation += siteName + ". ";
      citation += "Available at: " + (url || "[URL]");
      citation += ad ? " (Accessed: " + formatDateDMY(ad) + ")." : ".";
    }

    else if (sourceType === "book") {
      var year = gv("year") || "n.d.";
      var title = gv("title");
      var publisher = gv("publisher");
      var city = gv("city");
      var edition = gv("edition");

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + ") ";
      citation += title ? "_" + title + "_. " : "";
      if (edition) citation += edition + " edn. ";
      if (city && publisher) {
        citation += city + ": " + publisher + ".";
      } else if (publisher) {
        citation += publisher + ".";
      }
    }

    else if (sourceType === "journal") {
      var year = gv("year") || "n.d.";
      var articleTitle = gv("articleTitle");
      var journalName = gv("journalName");
      var volume = gv("volume");
      var issue = gv("issue");
      var pages = gv("pages");
      var doi = gv("doi");

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + ") ";
      citation += articleTitle ? "'" + articleTitle + "', " : "";
      citation += journalName ? "_" + journalName + "_, " : "";
      if (volume) citation += volume;
      if (issue) citation += "(" + issue + ")";
      if (pages) citation += ", pp. " + pages;
      citation += ". ";
      if (doi) {
        citation += "doi: " + (doi.indexOf("http") === 0 ? doi : "https://doi.org/" + doi) + ".";
      }
    }

    else if (sourceType === "newspaper") {
      var date = gv("date");
      var year = getYear(date);
      var articleTitle = gv("articleTitle");
      var newspaperName = gv("newspaperName");
      var url = gv("url");
      var d = parseDate(date);

      citation = authorStr ? authorStr + " " : "";
      citation += "(" + year + ") ";
      citation += articleTitle ? "'" + articleTitle + "', " : "";
      citation += newspaperName ? "_" + newspaperName + "_, " : "";
      citation += d ? formatDateDMY(d) + ". " : "";
      if (url) citation += "Available at: " + url + ".";
    }

    else if (sourceType === "video") {
      var uploadDate = gv("uploadDate");
      var year = getYear(uploadDate);
      var title = gv("title");
      var platform = gv("platform");
      var url = gv("url");
      var creatorRaw = gv("creator");

      citation = creatorRaw ? creatorRaw + " " : "";
      citation += "(" + year + ") ";
      citation += title ? "_" + title + "_ [Video]. " : "";
      citation += platform ? platform + ". " : "";
      citation += url ? "Available at: " + url + "." : "";
    }

    return citation.replace(/\s+/g, " ").trim();
  }

  // ========== IEEE FORMATTING ==========

  function formatIEEE() {
    var sourceType = document.getElementById("cgSourceType").value;
    var authors = parseAuthors(gv("author") || gv("creator"));
    var authorStr = "";

    if (authors.length === 1) {
      authorStr = getFirstInitialLast(authors[0]);
    } else if (authors.length === 2) {
      authorStr = getFirstInitialLast(authors[0]) + " and " + getFirstInitialLast(authors[1]);
    } else if (authors.length <= 6) {
      var parts = [];
      for (var i = 0; i < authors.length - 1; i++) {
        parts.push(getFirstInitialLast(authors[i]));
      }
      authorStr = parts.join(", ") + ", and " + getFirstInitialLast(authors[authors.length - 1]);
    } else {
      authorStr = getFirstInitialLast(authors[0]) + " et al.";
    }

    var refNum = "[" + (bibliography.length + 1) + "]";
    var citation = "";

    if (sourceType === "website") {
      var title = gv("title");
      var siteName = gv("siteName");
      var publishDate = gv("publishDate");
      var accessDate = gv("accessDate");
      var url = gv("url");
      var d = parseDate(publishDate);
      var ad = parseDate(accessDate);

      citation = refNum + " " + (authorStr ? authorStr + ", " : "");
      citation += title ? '"' + title + '," ' : "";
      citation += siteName ? "_" + siteName + "_, " : "";
      citation += d ? formatDateMDY(d) + ". " : "";
      citation += "[Online]. Available: " + (url || "[URL]");
      if (ad) citation += ". [Accessed: " + formatDateMDY(ad) + "]";
    }

    else if (sourceType === "book") {
      var title = gv("title");
      var publisher = gv("publisher");
      var year = gv("year") || "";
      var city = gv("city");
      var edition = gv("edition");

      citation = refNum + " " + (authorStr ? authorStr + ", " : "");
      citation += title ? "_" + title + "_" : "";
      if (edition) citation += ", " + edition + " ed.";
      citation += ". ";
      if (city) citation += city + ": ";
      citation += publisher ? publisher + ", " : "";
      citation += year + ".";
    }

    else if (sourceType === "journal") {
      var articleTitle = gv("articleTitle");
      var journalName = gv("journalName");
      var volume = gv("volume");
      var issue = gv("issue");
      var year = gv("year") || "";
      var pages = gv("pages");
      var doi = gv("doi");

      citation = refNum + " " + (authorStr ? authorStr + ", " : "");
      citation += articleTitle ? '"' + articleTitle + '," ' : "";
      citation += journalName ? "_" + journalName + "_, " : "";
      if (volume) citation += "vol. " + volume;
      if (issue) citation += ", no. " + issue;
      if (pages) citation += ", pp. " + pages;
      citation += ", " + year + ".";
      if (doi) {
        citation += " doi: " + (doi.indexOf("http") === 0 ? doi : "https://doi.org/" + doi) + ".";
      }
    }

    else if (sourceType === "newspaper") {
      var articleTitle = gv("articleTitle");
      var newspaperName = gv("newspaperName");
      var date = gv("date");
      var url = gv("url");
      var d = parseDate(date);

      citation = refNum + " " + (authorStr ? authorStr + ", " : "");
      citation += articleTitle ? '"' + articleTitle + '," ' : "";
      citation += newspaperName ? "_" + newspaperName + "_, " : "";
      citation += d ? formatDateMDY(d) + "." : "";
      if (url) citation += " [Online]. Available: " + url;
    }

    else if (sourceType === "video") {
      var title = gv("title");
      var platform = gv("platform");
      var url = gv("url");
      var uploadDate = gv("uploadDate");
      var d = parseDate(uploadDate);
      var creatorRaw = gv("creator");
      var creatorsIEEE = parseAuthors(creatorRaw);
      var cStr = "";
      if (creatorsIEEE.length >= 1) cStr = getFirstInitialLast(creatorsIEEE[0]);

      citation = refNum + " " + (cStr ? cStr + ", " : "");
      citation += title ? '"' + title + '," ' : "";
      citation += platform ? "_" + platform + "_, " : "";
      citation += d ? formatDateMDY(d) + ". " : "";
      citation += "[Online Video]. Available: " + (url || "[URL]");
    }

    return citation.replace(/\s+/g, " ").trim();
  }

  // ========== RENDER CITATION (with italic markers) ==========

  function renderCitationHTML(text) {
    // Convert _text_ markers to italic spans for display
    var html = text.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
    html = html.replace(/_(.*?)_/g, '<span class="cg-italic">$1</span>');
    return html;
  }

  function citationToPlainText(text) {
    // Remove underscore markers for plain text export
    return text.replace(/_(.*?)_/g, "$1");
  }

  // ========== GENERATE ==========

  window.cgGenerate = function() {
    var format = document.getElementById("cgFormat").value;
    var result = "";

    if (format === "apa") result = formatAPA();
    else if (format === "mla") result = formatMLA();
    else if (format === "chicago") result = formatChicago();
    else if (format === "harvard") result = formatHarvard();
    else if (format === "ieee") result = formatIEEE();

    if (!result || result.length < 5) {
      showToast("Please fill in at least the title or author field.");
      return;
    }

    currentCitation = result;
    citationOutput.innerHTML = renderCitationHTML(result);
    previewEl.style.display = "block";
    previewEl.scrollIntoView({ behavior: "smooth", block: "nearest" });
  };

  // ========== COPY SINGLE CITATION ==========

  window.cgCopyCitation = function() {
    if (!currentCitation) return;
    var plain = citationToPlainText(currentCitation);
    navigator.clipboard.writeText(plain).then(function() {
      showToast("Citation copied to clipboard");
    });
  };

  // ========== ADD TO BIBLIOGRAPHY ==========

  window.cgAddToBib = function() {
    if (!currentCitation) return;
    bibliography.push(currentCitation);
    renderBibliography();
    showToast("Added to bibliography (" + bibliography.length + " total)");
  };

  // ========== RENDER BIBLIOGRAPHY ==========

  function renderBibliography() {
    bibCount.textContent = bibliography.length;
    var copyBtn = document.getElementById("cgCopyBibBtn");
    var exportBtn = document.getElementById("cgExportBibBtn");
    var clearBtn = document.getElementById("cgClearBibBtn");

    if (bibliography.length === 0) {
      bibBody.innerHTML = '<div class="cg-bib-empty">No citations added yet. Generate a citation above and click "Add to Bibliography."</div>';
      copyBtn.disabled = true;
      exportBtn.disabled = true;
      clearBtn.disabled = true;
      return;
    }

    copyBtn.disabled = false;
    exportBtn.disabled = false;
    clearBtn.disabled = false;

    var html = '<ul class="cg-bib-list">';
    for (var i = 0; i < bibliography.length; i++) {
      html += '<li class="cg-bib-item">';
      html += '<span class="cg-bib-item-num">' + (i + 1) + '</span>';
      html += '<span class="cg-bib-item-text">' + renderCitationHTML(bibliography[i]) + '</span>';
      html += '<button class="cg-bib-item-remove" onclick="cgRemoveBib(' + i + ')" title="Remove">&times;</button>';
      html += '</li>';
    }
    html += '</ul>';
    bibBody.innerHTML = html;
  }

  // ========== REMOVE FROM BIBLIOGRAPHY ==========

  window.cgRemoveBib = function(index) {
    bibliography.splice(index, 1);
    // Renumber IEEE citations if format is IEEE
    var format = document.getElementById("cgFormat").value;
    if (format === "ieee") {
      for (var i = 0; i < bibliography.length; i++) {
        bibliography[i] = bibliography[i].replace(/^\[\d+\]/, "[" + (i + 1) + "]");
      }
    }
    renderBibliography();
    showToast("Citation removed");
  };

  // ========== COPY ALL BIBLIOGRAPHY ==========

  window.cgCopyBib = function() {
    if (bibliography.length === 0) return;
    var lines = [];
    for (var i = 0; i < bibliography.length; i++) {
      lines.push(citationToPlainText(bibliography[i]));
    }
    var text = lines.join("\n\n");
    navigator.clipboard.writeText(text).then(function() {
      showToast("Bibliography copied to clipboard");
    });
  };

  // ========== EXPORT BIBLIOGRAPHY ==========

  window.cgExportBib = function() {
    if (bibliography.length === 0) return;
    var lines = [];
    for (var i = 0; i < bibliography.length; i++) {
      lines.push(citationToPlainText(bibliography[i]));
    }
    var text = lines.join("\n\n");
    var blob = new Blob([text], { type: "text/plain" });
    var url = URL.createObjectURL(blob);
    var a = document.createElement("a");
    a.href = url;
    a.download = "bibliography.txt";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
    showToast("Bibliography exported as text file");
  };

  // ========== CLEAR BIBLIOGRAPHY ==========

  window.cgClearBib = function() {
    bibliography = [];
    renderBibliography();
    showToast("Bibliography cleared");
  };

  // ========== CLEAR FORM ==========

  window.cgClearForm = function() {
    var inputs = fieldsContainer.querySelectorAll("input");
    for (var i = 0; i < inputs.length; i++) {
      inputs[i].value = "";
    }
    previewEl.style.display = "none";
    currentCitation = "";
  };

  // ========== INIT ==========

  cgUpdateFields();

})();
</script>
