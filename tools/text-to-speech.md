---
layout: page
title: "Free Text to Speech — Convert Text to Audio Online | Zovo"
description: "Convert text to speech using your browser's built-in voices. Adjust speed, pitch, and volume. Choose from multiple languages and voices. Free online text-to-speech tool."
permalink: /tools/text-to-speech/
keywords: "text to speech, tts, text to speech online, text to audio, read aloud, speech synthesis, tts online free, text reader"
date: 2026-03-19
categories: [tools]
tags: [text-to-speech, tts, speech, audio, accessibility, reader]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  body {
    margin: 0;
    padding: 0;
    background: #0a0a0f !important;
  }

  :root {
    --tts-primary: #6C5CE7;
    --tts-primary-dark: #5A4BD1;
    --tts-primary-light: #A29BFE;
    --tts-bg: #0a0a0f;
    --tts-surface: #12121a;
    --tts-surface-alt: #181824;
    --tts-border: #1e1e2e;
    --tts-border-light: #2a2a3e;
    --tts-text: #e0e0e0;
    --tts-text-muted: #8888aa;
    --tts-green: #00ff88;
    --tts-green-dark: #00cc6a;
    --tts-yellow: #ffaa00;
    --tts-red: #ff4466;
    --tts-highlight: rgba(0, 255, 136, 0.2);
    --tts-highlight-word: #00ff88;
    --tts-radius: 12px;
  }

  .tts-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--tts-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px;
    line-height: 1.6;
  }

  .tts-wrapper * {
    box-sizing: border-box;
  }

  /* Hero */
  .tts-hero {
    text-align: center;
    padding: 48px 0 32px;
  }

  .tts-hero h1 {
    font-size: 2.4rem;
    font-weight: 800;
    color: #ffffff;
    margin: 0 0 16px;
    line-height: 1.15;
    letter-spacing: -0.02em;
  }

  .tts-hero h1 span {
    background: linear-gradient(135deg, var(--tts-primary), var(--tts-primary-light));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tts-intro {
    font-size: 1.05rem;
    color: var(--tts-text-muted);
    max-width: 680px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .tts-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--tts-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--tts-border);
    border-radius: 20px;
  }

  /* Controls Section */
  .tts-controls-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 16px;
  }

  .tts-control-group {
    background: var(--tts-surface);
    border: 1px solid var(--tts-border);
    border-radius: 10px;
    padding: 14px 16px;
  }

  .tts-control-group.full-width {
    grid-column: 1 / -1;
  }

  .tts-control-label {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 0.78rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--tts-text-muted);
    margin-bottom: 8px;
  }

  .tts-control-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    color: var(--tts-green);
  }

  .tts-select {
    width: 100%;
    padding: 9px 12px;
    background: var(--tts-bg);
    border: 1px solid var(--tts-border);
    border-radius: 8px;
    color: var(--tts-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.88rem;
    outline: none;
    cursor: pointer;
    appearance: auto;
    transition: border-color 0.2s;
  }

  .tts-select:focus {
    border-color: var(--tts-primary);
    box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.15);
  }

  .tts-slider {
    width: 100%;
    -webkit-appearance: none;
    appearance: none;
    height: 6px;
    background: var(--tts-border-light);
    border-radius: 3px;
    outline: none;
    cursor: pointer;
  }

  .tts-slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: var(--tts-primary);
    border: 2px solid var(--tts-primary-light);
    cursor: pointer;
    transition: transform 0.15s;
  }

  .tts-slider::-webkit-slider-thumb:hover {
    transform: scale(1.15);
  }

  .tts-slider::-moz-range-thumb {
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: var(--tts-primary);
    border: 2px solid var(--tts-primary-light);
    cursor: pointer;
  }

  /* Input Section */
  .tts-input-section {
    background: var(--tts-surface);
    border: 1px solid var(--tts-border);
    border-radius: var(--tts-radius);
    overflow: hidden;
    margin-bottom: 16px;
    box-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .tts-input-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 20px;
    border-bottom: 1px solid var(--tts-border);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--tts-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }

  .tts-char-count {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--tts-text-muted);
  }

  .tts-char-count .tts-count-warn {
    color: var(--tts-yellow);
  }

  .tts-char-count .tts-count-over {
    color: var(--tts-red);
  }

  .tts-textarea {
    width: 100%;
    min-height: 240px;
    border: none;
    padding: 20px;
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    line-height: 1.75;
    resize: vertical;
    color: var(--tts-text);
    background: var(--tts-surface);
    outline: none;
  }

  .tts-textarea::placeholder {
    color: #555570;
  }

  /* Highlighted text display */
  .tts-highlight-box {
    display: none;
    width: 100%;
    min-height: 240px;
    padding: 20px;
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    line-height: 1.75;
    color: var(--tts-text);
    background: var(--tts-surface);
    overflow-y: auto;
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .tts-highlight-box .tts-word-active {
    background: var(--tts-highlight);
    color: var(--tts-highlight-word);
    border-radius: 3px;
    padding: 1px 2px;
    font-weight: 600;
  }

  /* Playback Controls */
  .tts-playback {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
    flex-wrap: wrap;
  }

  .tts-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 28px;
    border: none;
    border-radius: 10px;
    font-family: 'Inter', sans-serif;
    font-size: 0.92rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
    white-space: nowrap;
  }

  .tts-btn-play {
    background: var(--tts-green);
    color: #0a0a0f;
    padding: 14px 36px;
    font-size: 1rem;
    border-radius: 12px;
    box-shadow: 0 0 20px rgba(0, 255, 136, 0.15);
  }

  .tts-btn-play:hover {
    background: var(--tts-green-dark);
    transform: translateY(-1px);
    box-shadow: 0 0 30px rgba(0, 255, 136, 0.25);
  }

  .tts-btn-play:disabled {
    opacity: 0.4;
    cursor: not-allowed;
    transform: none;
    box-shadow: none;
  }

  .tts-btn-pause {
    background: var(--tts-primary);
    color: #ffffff;
  }

  .tts-btn-pause:hover {
    background: var(--tts-primary-dark);
  }

  .tts-btn-stop {
    background: transparent;
    color: var(--tts-text-muted);
    border: 1px solid var(--tts-border);
  }

  .tts-btn-stop:hover {
    border-color: var(--tts-red);
    color: var(--tts-red);
  }

  .tts-btn-secondary {
    background: transparent;
    color: var(--tts-text-muted);
    border: 1px solid var(--tts-border);
    padding: 10px 20px;
    font-size: 0.85rem;
  }

  .tts-btn-secondary:hover {
    border-color: var(--tts-primary);
    color: var(--tts-primary-light);
  }

  .tts-btn-secondary.active {
    border-color: var(--tts-green);
    color: var(--tts-green);
  }

  /* Status Bar */
  .tts-status-bar {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 16px;
    background: var(--tts-surface);
    border: 1px solid var(--tts-border);
    border-radius: 8px;
    margin-bottom: 16px;
    font-size: 0.82rem;
    color: var(--tts-text-muted);
  }

  .tts-status-indicator {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--tts-border-light);
    flex-shrink: 0;
  }

  .tts-status-indicator.playing {
    background: var(--tts-green);
    box-shadow: 0 0 8px rgba(0, 255, 136, 0.5);
    animation: tts-pulse 1.5s infinite;
  }

  .tts-status-indicator.paused {
    background: var(--tts-yellow);
  }

  @keyframes tts-pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.5; }
  }

  .tts-status-text {
    flex: 1;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
  }

  /* Quick Phrases */
  .tts-quick-section {
    margin-bottom: 20px;
  }

  .tts-quick-label {
    font-size: 0.78rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    color: var(--tts-text-muted);
    margin-bottom: 8px;
    display: block;
  }

  .tts-quick-phrases {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .tts-quick-btn {
    padding: 6px 14px;
    background: var(--tts-surface-alt);
    border: 1px solid var(--tts-border);
    border-radius: 20px;
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    color: var(--tts-text-muted);
    cursor: pointer;
    transition: all 0.2s;
  }

  .tts-quick-btn:hover {
    border-color: var(--tts-primary);
    color: var(--tts-primary-light);
    background: rgba(108, 92, 231, 0.08);
  }

  /* Download Note */
  .tts-download-note {
    background: var(--tts-surface-alt);
    border: 1px solid var(--tts-border);
    border-left: 3px solid var(--tts-primary);
    border-radius: 8px;
    padding: 14px 18px;
    margin-bottom: 24px;
    font-size: 0.85rem;
    color: var(--tts-text-muted);
    line-height: 1.6;
  }

  .tts-download-note strong {
    color: var(--tts-text);
    font-weight: 600;
  }

  /* Cross-links */
  .tts-cross-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin: 28px 0;
    padding: 20px;
    background: var(--tts-surface);
    border: 1px solid var(--tts-border);
    border-radius: var(--tts-radius);
  }

  .tts-cross-links a {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    background: var(--tts-surface-alt);
    border: 1px solid var(--tts-border);
    border-radius: 8px;
    color: var(--tts-text-muted);
    text-decoration: none;
    font-size: 0.82rem;
    font-weight: 500;
    transition: all 0.2s;
  }

  .tts-cross-links a:hover {
    border-color: var(--tts-primary);
    color: var(--tts-primary-light);
    background: rgba(108, 92, 231, 0.06);
  }

  /* Content */
  .tts-content {
    padding: 20px 0;
    max-width: 780px;
  }

  .tts-content h2 {
    font-size: 1.45rem;
    font-weight: 700;
    color: #ffffff;
    margin: 36px 0 14px;
    line-height: 1.25;
  }

  .tts-content p {
    font-size: 0.95rem;
    color: var(--tts-text);
    line-height: 1.75;
    margin: 0 0 14px;
  }

  .tts-content table {
    width: 100%;
    border-collapse: collapse;
    margin: 16px 0 20px;
    font-size: 0.88rem;
  }

  .tts-content th,
  .tts-content td {
    padding: 10px 14px;
    border: 1px solid var(--tts-border);
    text-align: left;
  }

  .tts-content th {
    background: var(--tts-surface);
    color: var(--tts-text-muted);
    font-weight: 600;
    text-transform: uppercase;
    font-size: 0.75rem;
    letter-spacing: 0.05em;
  }

  .tts-content td {
    background: var(--tts-surface-alt);
  }

  /* FAQ */
  .tts-faq {
    padding: 20px 0;
    max-width: 780px;
  }

  .tts-faq h2 {
    font-size: 1.45rem;
    font-weight: 700;
    color: #ffffff;
    margin: 0 0 20px;
  }

  .tts-faq-item {
    background: var(--tts-surface);
    border: 1px solid var(--tts-border);
    border-radius: 10px;
    margin-bottom: 10px;
    overflow: hidden;
  }

  .tts-faq-item h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--tts-text);
    margin: 0;
    padding: 16px 20px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: color 0.2s;
  }

  .tts-faq-item h3:hover {
    color: var(--tts-primary-light);
  }

  .tts-faq-item h3::after {
    content: "+";
    font-size: 1.2rem;
    color: var(--tts-text-muted);
    font-weight: 400;
    transition: transform 0.2s;
  }

  .tts-faq-item.open h3::after {
    content: "-";
  }

  .tts-faq-answer {
    display: none;
    padding: 0 20px 16px;
  }

  .tts-faq-item.open .tts-faq-answer {
    display: block;
  }

  .tts-faq-answer p {
    font-size: 0.9rem;
    color: var(--tts-text-muted);
    line-height: 1.7;
    margin: 0;
  }

  /* Author Box */
  .tts-author-box {
    display: flex;
    align-items: center;
    gap: 16px;
    background: var(--tts-surface);
    border: 1px solid var(--tts-border);
    border-radius: var(--tts-radius);
    padding: 20px 24px;
    margin: 32px 0 20px;
    max-width: 780px;
  }

  .tts-author-avatar {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--tts-primary), var(--tts-primary-light));
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 0.9rem;
    color: #fff;
    flex-shrink: 0;
  }

  .tts-author-info {
    flex: 1;
  }

  .tts-author-name {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--tts-text);
    margin: 0 0 4px;
  }

  .tts-author-bio {
    font-size: 0.82rem;
    color: var(--tts-text-muted);
    margin: 0;
    line-height: 1.5;
  }

  /* Footer */
  .tts-footer {
    text-align: center;
    padding: 24px 0 40px;
    font-size: 0.82rem;
    color: var(--tts-text-muted);
    border-top: 1px solid var(--tts-border);
    margin-top: 20px;
  }

  .tts-footer a {
    color: var(--tts-primary-light);
    text-decoration: none;
  }

  .tts-footer a:hover {
    text-decoration: underline;
  }

  /* Scrollbar */
  .tts-wrapper ::-webkit-scrollbar {
    width: 6px;
  }

  .tts-wrapper ::-webkit-scrollbar-track {
    background: var(--tts-surface);
  }

  .tts-wrapper ::-webkit-scrollbar-thumb {
    background: var(--tts-border-light);
    border-radius: 3px;
  }

  /* Mobile */
  @media (max-width: 768px) {
    .tts-hero h1 {
      font-size: 1.7rem;
    }

    .tts-hero {
      padding: 32px 0 24px;
    }

    .tts-controls-grid {
      grid-template-columns: 1fr;
    }

    .tts-playback {
      flex-direction: column;
      align-items: stretch;
    }

    .tts-btn-play {
      text-align: center;
      justify-content: center;
    }

    .tts-textarea {
      min-height: 180px;
    }

    .tts-cross-links {
      flex-direction: column;
    }

    .tts-author-box {
      flex-direction: column;
      text-align: center;
    }
  }

  @media (max-width: 480px) {
    .tts-quick-phrases {
      flex-direction: column;
    }

    .tts-status-bar {
      flex-direction: column;
      text-align: center;
    }
  }
</style>

<div class="tts-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="Free Text to Speech Tool">
  <meta itemprop="applicationCategory" content="UtilityApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <!-- Hero -->
  <div class="tts-hero">
    <h1>Free <span>Text to Speech</span> Tool</h1>
    <p class="tts-intro">Type or paste text, pick a voice and language, adjust speed and pitch, then press play. Your browser handles all synthesis locally. No uploads, no accounts, no limits.</p>
    <span class="tts-updated">Last updated: March 19, 2026</span>
  </div>

  <!-- Voice / Language Controls -->
  <div class="tts-controls-grid">
    <div class="tts-control-group">
      <div class="tts-control-label">
        <span>Language</span>
      </div>
      <select class="tts-select" id="ttsLang" onchange="ttsFilterVoices()">
        <option value="all">All Languages</option>
      </select>
    </div>

    <div class="tts-control-group">
      <div class="tts-control-label">
        <span>Voice</span>
        <span class="tts-control-value" id="ttsVoiceCount">0 voices</span>
      </div>
      <select class="tts-select" id="ttsVoice">
        <option value="">Loading voices...</option>
      </select>
    </div>

    <div class="tts-control-group">
      <div class="tts-control-label">
        <span>Speed</span>
        <span class="tts-control-value" id="ttsSpeedVal">1.0x</span>
      </div>
      <input type="range" class="tts-slider" id="ttsSpeed" min="0.5" max="3" step="0.1" value="1">
    </div>

    <div class="tts-control-group">
      <div class="tts-control-label">
        <span>Pitch</span>
        <span class="tts-control-value" id="ttsPitchVal">1.0</span>
      </div>
      <input type="range" class="tts-slider" id="ttsPitch" min="0" max="2" step="0.1" value="1">
    </div>

    <div class="tts-control-group full-width">
      <div class="tts-control-label">
        <span>Volume</span>
        <span class="tts-control-value" id="ttsVolVal">100%</span>
      </div>
      <input type="range" class="tts-slider" id="ttsVolume" min="0" max="1" step="0.05" value="1">
    </div>
  </div>

  <!-- Text Input -->
  <div class="tts-input-section">
    <div class="tts-input-header">
      <span>Enter text to speak</span>
      <span class="tts-char-count" id="ttsCharCount">0 characters</span>
    </div>
    <textarea class="tts-textarea" id="ttsText" placeholder="Type or paste text here. Press the Play button to hear it spoken aloud using your browser's built-in speech synthesis."></textarea>
    <div class="tts-highlight-box" id="ttsHighlight"></div>
  </div>

  <!-- Playback Controls -->
  <div class="tts-playback">
    <button class="tts-btn tts-btn-play" id="ttsPlayBtn" onclick="ttsPlay()">Play</button>
    <button class="tts-btn tts-btn-pause" id="ttsPauseBtn" onclick="ttsPause()" style="display:none;">Pause</button>
    <button class="tts-btn tts-btn-stop" id="ttsStopBtn" onclick="ttsStop()">Stop</button>
    <button class="tts-btn tts-btn-secondary" id="ttsClearBtn" onclick="ttsClear()">Clear</button>
    <button class="tts-btn tts-btn-secondary" id="ttsRecordBtn" onclick="ttsToggleRecord()">Record Audio</button>
  </div>

  <!-- Status Bar -->
  <div class="tts-status-bar">
    <div class="tts-status-indicator" id="ttsIndicator"></div>
    <span class="tts-status-text" id="ttsStatus">Ready. Enter text and press Play.</span>
  </div>

  <!-- Quick Phrases -->
  <div class="tts-quick-section">
    <span class="tts-quick-label">Quick test phrases</span>
    <div class="tts-quick-phrases" id="ttsQuickPhrases">
      <button class="tts-quick-btn" onclick="ttsQuick('The quick brown fox jumps over the lazy dog.')">English: Quick brown fox</button>
      <button class="tts-quick-btn" onclick="ttsQuick('Hola, me llamo Zovo. Bienvenido a esta herramienta.')">Spanish: Greeting</button>
      <button class="tts-quick-btn" onclick="ttsQuick('Bonjour, bienvenue sur cet outil de synthese vocale.')">French: Welcome</button>
      <button class="tts-quick-btn" onclick="ttsQuick('Guten Tag. Willkommen bei diesem Sprachwerkzeug.')">German: Greeting</button>
      <button class="tts-quick-btn" onclick="ttsQuick('Pack my box with five dozen liquor jugs.')">English: Pangram</button>
    </div>
  </div>

  <!-- Download Note -->
  <div class="tts-download-note">
    <strong>About audio download:</strong> The Web Speech API does not produce a downloadable audio file directly. The Record Audio button above uses the MediaRecorder API with AudioContext to capture the speech output when your browser supports it. If recording is not available, you can use your operating system's built-in screen recording or a third-party tool to capture the audio while it plays.
  </div>

  <!-- Cross-links -->
  <div class="tts-cross-links">
    <a href="/tools/word-counter/">Word Counter</a>
    <a href="/tools/ai-detector/">AI Detector</a>
    <a href="/tools/lorem-ipsum-generator/">Lorem Ipsum Generator</a>
    <a href="/tools/diff-checker/">Diff Checker</a>
  </div>

  <!-- SEO Content -->
  <div class="tts-content">

<h2>What Is Text to Speech</h2>

<p>Text to speech (TTS) converts written text into spoken audio. The process takes a string of characters, analyzes the language structure, applies pronunciation rules, and generates a waveform that sounds like a human voice. Modern TTS systems use either concatenative synthesis (splicing recorded speech fragments) or parametric synthesis (generating audio from statistical models).</p>

<p>Browser-based TTS relies on the Web Speech API, specifically the SpeechSynthesis interface. This API ships with every major browser and uses the operating system's installed voices. On macOS, you get access to the system voices in System Settings. On Windows, you get the Microsoft voices. On Android and Chrome OS, you get Google's voices. No installation or plugin is required.</p>

<p>The result varies by platform. Some voices sound robotic and choppy. Others, particularly newer neural voices on Windows 11 and macOS Sonoma, sound close to natural speech. The quality depends entirely on which voices your OS provides.</p>

<h2>How Browser TTS Works</h2>

<p>The SpeechSynthesis API works through a queue system. You create a SpeechSynthesisUtterance object, set its text, voice, rate, pitch, and volume properties, and pass it to speechSynthesis.speak(). The browser adds it to a queue and starts processing. You can pause, resume, and cancel at any time.</p>

<p>Voice loading is asynchronous. Browsers load the voice list after the page renders, so the voice dropdown in this tool listens for the voiceschanged event before populating. Some browsers fire this event once, others fire it multiple times. The tool handles both cases.</p>

<p>Word-level highlighting works through the boundary event on the utterance object. When the speech engine reaches a word boundary, it fires an event containing the character index and length of the current word. The tool uses this data to highlight the active word in the text display. Not all browsers support boundary events with the same precision. Chrome and Edge provide word-level boundaries consistently. Safari and Firefox may only provide sentence-level boundaries or skip them entirely.</p>

<h2>Available Voices and Languages</h2>

<p>The number of available voices depends on your device and operating system. A typical setup provides between 20 and 200 voices across multiple languages. The language filter in this tool groups voices by their BCP 47 language tag (en-US, fr-FR, de-DE, etc.) so you can find voices for a specific locale quickly.</p>

<table>
  <thead>
    <tr>
      <th>Platform</th>
      <th>Typical Voice Count</th>
      <th>Notable Voices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>macOS 14+</td>
      <td>80-120</td>
      <td>Siri voices, enhanced Samantha</td>
    </tr>
    <tr>
      <td>Windows 11</td>
      <td>30-80</td>
      <td>Microsoft neural voices (Jenny, Aria)</td>
    </tr>
    <tr>
      <td>Chrome (all OS)</td>
      <td>20-40</td>
      <td>Google US/UK English, multilingual</td>
    </tr>
    <tr>
      <td>Android</td>
      <td>30-60</td>
      <td>Google TTS engine voices</td>
    </tr>
    <tr>
      <td>iOS / iPadOS</td>
      <td>60-100</td>
      <td>Siri voices, downloadable enhanced</td>
    </tr>
  </tbody>
</table>

<p>You can install additional voices through your operating system settings. On macOS, go to System Settings > Accessibility > Spoken Content > System Voice > Manage Voices. On Windows, go to Settings > Time & Language > Speech > Manage voices. New voices appear in the dropdown after installation and a page refresh.</p>

<h2>Accessibility Benefits of TTS</h2>

<p>TTS serves multiple accessibility needs. People with dyslexia often find it easier to process information when they can hear it read aloud while following along visually. The word highlighting in this tool supports that dual-channel approach by marking the current word as the voice speaks it.</p>

<p>People with visual impairments use screen readers for daily computer use, but TTS tools like this one offer a simpler interface for one-off tasks: reading an article, reviewing an email draft, or proofing a document. Hearing text read back often reveals errors that visual proofreading misses, such as repeated words, missing articles, or awkward phrasing.</p>

<p>Language learners use TTS to hear correct pronunciation. By selecting a native-language voice and adjusting the speed to a slower rate, learners can hear how words and phrases should sound. The pitch and speed controls let them customize the output to match their comprehension level.</p>

<h2>Tips for Natural Sounding Speech</h2>

<p>Speed has the largest effect on naturalness. The default rate of 1.0 is calibrated to a comfortable listening pace. Going above 1.5x makes most voices sound mechanical. Going below 0.7x introduces unnatural pauses between syllables. For most use cases, stay between 0.8x and 1.3x.</p>

<p>Pitch changes the fundamental frequency of the voice. A pitch of 1.0 is the voice's natural pitch. Values below 1.0 produce a deeper voice; values above 1.0 produce a higher one. Small adjustments (0.8 to 1.2) sound more natural than extreme values.</p>

<p>Punctuation affects pacing. Periods create longer pauses than commas. Semicolons and colons create medium pauses. Question marks change the intonation on most voices. If your text sounds too rushed, add commas or break long sentences into shorter ones. If it sounds choppy, combine short sentences.</p>

<p>Some voices handle proper nouns, abbreviations, and numbers better than others. If a voice mispronounces a word, try spelling it phonetically. For example, changing "nginx" to "engine X" or "GIF" to "jif" can fix pronunciation issues without changing the meaning.</p>

  </div>

  <!-- FAQ Section -->
  <div class="tts-faq" itemscope itemtype="https://schema.org/FAQPage">

    <h2>Frequently Asked Questions</h2>

    <div class="tts-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Does this tool work offline?</h3>
      <div class="tts-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes, once the page loads. The Web Speech API uses voices installed on your operating system, so no internet connection is needed for speech synthesis. The page itself needs to load initially, but after that, all processing is local. Some browser-provided voices (marked as "network" in the voice list) require an internet connection, but most system voices work fully offline.</p>
      </div>
    </div>

    <div class="tts-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Why do I see different voices on different devices?</h3>
      <div class="tts-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The Web Speech API exposes whatever voices the operating system and browser provide. macOS includes Siri and enhanced voices. Windows includes Microsoft voices. Chrome adds its own set of Google voices. Each combination of OS, browser, and installed language packs produces a different voice list. You can install additional voices through your OS accessibility or language settings.</p>
      </div>
    </div>

    <div class="tts-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Is there a character limit?</h3>
      <div class="tts-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool does not impose a character limit. However, some browsers cap individual utterances. Chrome, for example, stops speaking after roughly 15 minutes of continuous speech. For very long texts, the tool automatically splits the input into smaller chunks and queues them sequentially, so playback continues without interruption regardless of length.</p>
      </div>
    </div>

    <div class="tts-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Can I download the audio as an MP3?</h3>
      <div class="tts-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">The Web Speech API does not produce a downloadable audio stream by default. This tool offers a Record Audio button that uses the MediaRecorder API combined with AudioContext to capture the audio output in browsers that support this approach. The result downloads as a .webm file. If your browser does not support recording, you can use screen recording software to capture the audio while it plays.</p>
      </div>
    </div>

    <div class="tts-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name" onclick="this.parentElement.classList.toggle('open')">Is my text sent to any server?</h3>
      <div class="tts-faq-answer" itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">No. All processing runs entirely in your browser. The text never leaves your device. There are no analytics tracking input, no server-side processing, and no data stored anywhere. You can verify this by opening your browser's developer tools and monitoring the Network tab while using the tool.</p>
      </div>
    </div>

  </div>

  <!-- Author Box -->
  <div class="tts-author-box">
    <div class="tts-author-avatar">ML</div>
    <div class="tts-author-info">
      <p class="tts-author-name">Michael Lip</p>
      <p class="tts-author-bio">Michael builds free tools and writes guides at zovo.one. He focuses on practical utilities that run client-side, load fast, and respect user privacy.</p>
    </div>
  </div>

  <footer class="tts-footer">
    <p>Built by <a href="https://zovo.one">Michael Lip</a> at <a href="https://zovo.one">zovo.one</a></p>
  </footer>

</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "Text to Speech Tool",
      "description": "Convert text to speech using your browser's built-in voices. Adjust speed, pitch, and volume. Choose from multiple languages and voices.",
      "url": "https://theluckystrike.github.io/tools/text-to-speech/",
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
        {"@type": "ListItem", "position": 3, "name": "Text to Speech", "item": "https://theluckystrike.github.io/tools/text-to-speech/"}
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
          "name": "Does this tool work offline?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, once the page loads. The Web Speech API uses voices installed on your operating system, so no internet connection is needed for speech synthesis after the initial page load."
          }
        },
        {
          "@type": "Question",
          "name": "Why do I see different voices on different devices?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Web Speech API exposes whatever voices the operating system and browser provide. Each combination of OS, browser, and installed language packs produces a different voice list."
          }
        },
        {
          "@type": "Question",
          "name": "Is there a character limit?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "This tool does not impose a character limit. Some browsers cap individual utterances, but the tool splits long texts into chunks automatically."
          }
        },
        {
          "@type": "Question",
          "name": "Can I download the audio as an MP3?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Web Speech API does not produce a downloadable audio stream by default. This tool offers a Record Audio button using the MediaRecorder API to capture output when supported."
          }
        },
        {
          "@type": "Question",
          "name": "Is my text sent to any server?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. All processing runs entirely in your browser. The text never leaves your device."
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

  var synth = window.speechSynthesis;
  var allVoices = [];
  var currentUtterance = null;
  var isPlaying = false;
  var isPaused = false;
  var mediaRecorder = null;
  var recordedChunks = [];
  var isRecording = false;
  var audioCtx = null;
  var destNode = null;

  var elText = document.getElementById("ttsText");
  var elHighlight = document.getElementById("ttsHighlight");
  var elVoice = document.getElementById("ttsVoice");
  var elLang = document.getElementById("ttsLang");
  var elSpeed = document.getElementById("ttsSpeed");
  var elPitch = document.getElementById("ttsPitch");
  var elVolume = document.getElementById("ttsVolume");
  var elSpeedVal = document.getElementById("ttsSpeedVal");
  var elPitchVal = document.getElementById("ttsPitchVal");
  var elVolVal = document.getElementById("ttsVolVal");
  var elVoiceCount = document.getElementById("ttsVoiceCount");
  var elCharCount = document.getElementById("ttsCharCount");
  var elPlayBtn = document.getElementById("ttsPlayBtn");
  var elPauseBtn = document.getElementById("ttsPauseBtn");
  var elStopBtn = document.getElementById("ttsStopBtn");
  var elRecordBtn = document.getElementById("ttsRecordBtn");
  var elIndicator = document.getElementById("ttsIndicator");
  var elStatus = document.getElementById("ttsStatus");

  // Load voices
  function loadVoices() {
    allVoices = synth.getVoices();
    if (allVoices.length === 0) return;

    // Populate language filter
    var langs = {};
    for (var i = 0; i < allVoices.length; i++) {
      var v = allVoices[i];
      var langCode = v.lang.split("-")[0];
      var langName = getLangName(v.lang);
      if (!langs[langCode]) {
        langs[langCode] = langName;
      }
    }

    var langKeys = Object.keys(langs).sort(function(a, b) {
      return langs[a].localeCompare(langs[b]);
    });

    elLang.innerHTML = '<option value="all">All Languages (' + allVoices.length + ' voices)</option>';
    for (var j = 0; j < langKeys.length; j++) {
      var opt = document.createElement("option");
      opt.value = langKeys[j];
      opt.textContent = langs[langKeys[j]];
      elLang.appendChild(opt);
    }

    ttsFilterVoices();
  }

  function getLangName(code) {
    var map = {
      "en": "English", "es": "Spanish", "fr": "French", "de": "German",
      "it": "Italian", "pt": "Portuguese", "nl": "Dutch", "ru": "Russian",
      "ja": "Japanese", "ko": "Korean", "zh": "Chinese", "ar": "Arabic",
      "hi": "Hindi", "pl": "Polish", "sv": "Swedish", "da": "Danish",
      "fi": "Finnish", "no": "Norwegian", "tr": "Turkish", "cs": "Czech",
      "el": "Greek", "he": "Hebrew", "hu": "Hungarian", "id": "Indonesian",
      "ms": "Malay", "ro": "Romanian", "sk": "Slovak", "th": "Thai",
      "uk": "Ukrainian", "vi": "Vietnamese", "bg": "Bulgarian", "ca": "Catalan",
      "hr": "Croatian", "nb": "Norwegian Bokmal", "ta": "Tamil", "te": "Telugu"
    };
    var base = code.split("-")[0];
    return map[base] || base.toUpperCase();
  }

  window.ttsFilterVoices = function() {
    var langFilter = elLang.value;
    var filtered = allVoices;

    if (langFilter !== "all") {
      filtered = allVoices.filter(function(v) {
        return v.lang.split("-")[0] === langFilter;
      });
    }

    elVoice.innerHTML = "";
    for (var i = 0; i < filtered.length; i++) {
      var v = filtered[i];
      var opt = document.createElement("option");
      opt.value = i.toString();
      opt.dataset.voiceName = v.name;
      opt.dataset.voiceLang = v.lang;
      var label = v.name;
      if (v.localService) label += " (local)";
      else label += " (network)";
      label += " - " + v.lang;
      opt.textContent = label;
      elVoice.appendChild(opt);
    }

    elVoiceCount.textContent = filtered.length + " voice" + (filtered.length !== 1 ? "s" : "");
  };

  function getSelectedVoice() {
    var sel = elVoice.selectedOptions[0];
    if (!sel) return null;
    var name = sel.dataset.voiceName;
    var lang = sel.dataset.voiceLang;
    for (var i = 0; i < allVoices.length; i++) {
      if (allVoices[i].name === name && allVoices[i].lang === lang) {
        return allVoices[i];
      }
    }
    return null;
  }

  // Chunking for long text (Chrome limit workaround)
  function splitText(text, maxLen) {
    if (text.length <= maxLen) return [text];
    var chunks = [];
    var sentences = text.match(/[^.!?]+[.!?]+[\s]*/g) || [text];
    var current = "";
    for (var i = 0; i < sentences.length; i++) {
      if ((current + sentences[i]).length > maxLen && current.length > 0) {
        chunks.push(current.trim());
        current = sentences[i];
      } else {
        current += sentences[i];
      }
    }
    if (current.trim().length > 0) chunks.push(current.trim());
    return chunks;
  }

  // Play
  window.ttsPlay = function() {
    var text = elText.value.trim();
    if (!text) {
      setStatus("Enter text to speak.", "");
      return;
    }

    if (isPaused) {
      synth.resume();
      isPaused = false;
      isPlaying = true;
      elPlayBtn.style.display = "none";
      elPauseBtn.style.display = "";
      setStatus("Speaking...", "playing");
      return;
    }

    synth.cancel();

    var voice = getSelectedVoice();
    var rate = parseFloat(elSpeed.value);
    var pitch = parseFloat(elPitch.value);
    var volume = parseFloat(elVolume.value);

    // Show highlight box
    elHighlight.style.display = "block";
    elText.style.display = "none";

    var chunks = splitText(text, 3000);
    var chunkIdx = 0;
    var globalOffset = 0;

    function speakChunk() {
      if (chunkIdx >= chunks.length) {
        ttsStop();
        return;
      }

      var chunk = chunks[chunkIdx];
      var utt = new SpeechSynthesisUtterance(chunk);
      currentUtterance = utt;

      if (voice) utt.voice = voice;
      utt.rate = rate;
      utt.pitch = pitch;
      utt.volume = volume;

      utt.onboundary = function(e) {
        if (e.name === "word") {
          highlightWord(text, globalOffset + e.charIndex, e.charLength || 1);
        }
      };

      utt.onend = function() {
        globalOffset += chunk.length;
        chunkIdx++;
        speakChunk();
      };

      utt.onerror = function(e) {
        if (e.error !== "canceled") {
          setStatus("Error: " + e.error, "");
        }
      };

      synth.speak(utt);
    }

    isPlaying = true;
    isPaused = false;
    elPlayBtn.style.display = "none";
    elPauseBtn.style.display = "";
    setStatus("Speaking...", "playing");

    speakChunk();
  };

  function highlightWord(fullText, charIndex, charLength) {
    if (charIndex < 0 || charIndex >= fullText.length) return;
    // Find the full word around the boundary
    var start = charIndex;
    var end = charIndex + Math.max(charLength, 1);
    // Expand to word boundary
    while (end < fullText.length && fullText[end] !== " " && fullText[end] !== "\n") end++;

    var before = escapeHtml(fullText.substring(0, start));
    var word = escapeHtml(fullText.substring(start, end));
    var after = escapeHtml(fullText.substring(end));

    elHighlight.innerHTML = before + '<span class="tts-word-active">' + word + '</span>' + after;

    // Scroll highlighted word into view
    var activeEl = elHighlight.querySelector(".tts-word-active");
    if (activeEl) {
      var boxRect = elHighlight.getBoundingClientRect();
      var wordRect = activeEl.getBoundingClientRect();
      if (wordRect.bottom > boxRect.bottom || wordRect.top < boxRect.top) {
        activeEl.scrollIntoView({ block: "center", behavior: "smooth" });
      }
    }
  }

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.textContent = str;
    return div.innerHTML;
  }

  // Pause
  window.ttsPause = function() {
    if (isPlaying && !isPaused) {
      synth.pause();
      isPaused = true;
      isPlaying = false;
      elPlayBtn.style.display = "";
      elPlayBtn.textContent = "Resume";
      elPauseBtn.style.display = "none";
      setStatus("Paused", "paused");
    }
  };

  // Stop
  window.ttsStop = function() {
    synth.cancel();
    isPlaying = false;
    isPaused = false;
    currentUtterance = null;
    elPlayBtn.style.display = "";
    elPlayBtn.textContent = "Play";
    elPauseBtn.style.display = "none";
    elHighlight.style.display = "none";
    elText.style.display = "";
    elHighlight.innerHTML = "";
    setStatus("Ready. Enter text and press Play.", "");
  };

  // Clear
  window.ttsClear = function() {
    ttsStop();
    elText.value = "";
    updateCharCount();
    elText.focus();
  };

  // Quick phrase
  window.ttsQuick = function(phrase) {
    elText.value = phrase;
    updateCharCount();
    ttsPlay();
  };

  function setStatus(text, state) {
    elStatus.textContent = text;
    elIndicator.className = "tts-status-indicator";
    if (state === "playing") elIndicator.classList.add("playing");
    else if (state === "paused") elIndicator.classList.add("paused");
  }

  // Character count
  function updateCharCount() {
    var len = elText.value.length;
    var label = len.toLocaleString() + " character" + (len !== 1 ? "s" : "");
    if (len > 50000) {
      elCharCount.innerHTML = '<span class="tts-count-warn">' + label + '</span> (long text may take time)';
    } else {
      elCharCount.textContent = label;
    }
  }

  // Recording via MediaRecorder + AudioContext
  window.ttsToggleRecord = function() {
    if (isRecording) {
      stopRecording();
      return;
    }
    startRecording();
  };

  function startRecording() {
    try {
      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      destNode = audioCtx.createMediaStreamDestination();

      // Create an oscillator at zero gain to keep the stream alive
      var silentOsc = audioCtx.createOscillator();
      var silentGain = audioCtx.createGain();
      silentGain.gain.value = 0;
      silentOsc.connect(silentGain);
      silentGain.connect(destNode);
      silentOsc.start();

      mediaRecorder = new MediaRecorder(destNode.stream, { mimeType: "audio/webm" });
      recordedChunks = [];

      mediaRecorder.ondataavailable = function(e) {
        if (e.data.size > 0) recordedChunks.push(e.data);
      };

      mediaRecorder.onstop = function() {
        var blob = new Blob(recordedChunks, { type: "audio/webm" });
        var url = URL.createObjectURL(blob);
        var a = document.createElement("a");
        a.href = url;
        a.download = "tts-recording-" + Date.now() + ".webm";
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        URL.revokeObjectURL(url);
        silentOsc.stop();
        audioCtx.close();
      };

      mediaRecorder.start();
      isRecording = true;
      elRecordBtn.textContent = "Stop Recording";
      elRecordBtn.classList.add("active");
      setStatus("Recording audio... Press Play to speak, then Stop Recording to save.", "playing");

    } catch (err) {
      setStatus("Recording not supported in this browser. Use screen recording instead.", "");
    }
  }

  function stopRecording() {
    if (mediaRecorder && mediaRecorder.state !== "inactive") {
      mediaRecorder.stop();
    }
    isRecording = false;
    elRecordBtn.textContent = "Record Audio";
    elRecordBtn.classList.remove("active");
    setStatus("Recording saved.", "");
  }

  // Slider updates
  elSpeed.addEventListener("input", function() {
    elSpeedVal.textContent = parseFloat(this.value).toFixed(1) + "x";
  });

  elPitch.addEventListener("input", function() {
    elPitchVal.textContent = parseFloat(this.value).toFixed(1);
  });

  elVolume.addEventListener("input", function() {
    elVolVal.textContent = Math.round(parseFloat(this.value) * 100) + "%";
  });

  elText.addEventListener("input", function() {
    updateCharCount();
    // Auto-resize
    this.style.height = "auto";
    var newH = Math.max(240, this.scrollHeight);
    this.style.height = newH + "px";
  });

  // Load voices
  if (synth.getVoices().length > 0) {
    loadVoices();
  }
  synth.addEventListener("voiceschanged", loadVoices);

  // Init
  updateCharCount();

  // Handle page unload
  window.addEventListener("beforeunload", function() {
    synth.cancel();
  });

})();
</script>
