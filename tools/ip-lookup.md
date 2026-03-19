---
layout: page
title: "Free IP Address Lookup — Find Your IP, Location & ISP Info | Zovo"
description: "Look up any IP address to find geolocation, ISP, timezone, and network details. See your own public IP address instantly. Free IP lookup tool with map display."
permalink: /tools/ip-lookup/
keywords: "ip address lookup, what is my ip, ip location, ip geolocation, ip finder, ip address checker, my ip address, ip tracker"
date: 2026-03-19
categories: [tools]
tags: [ip-address, lookup, geolocation, network, isp, security]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  body { margin: 0; padding: 0; background: #0a0a0f !important; }

  :root {
    --ip-primary: #6C5CE7;
    --ip-primary-dark: #5A4BD1;
    --ip-primary-light: #A29BFE;
    --ip-bg: #0a0a0f;
    --ip-surface: #12121a;
    --ip-surface-alt: #181824;
    --ip-border: #1e1e2e;
    --ip-border-light: #2a2a3e;
    --ip-text: #e0e0e0;
    --ip-text-muted: #8888aa;
    --ip-green: #00ff88;
    --ip-green-dark: #00cc6a;
    --ip-red: #ff4466;
    --ip-yellow: #ffaa00;
    --ip-cyan: #00d4ff;
    --ip-radius: 12px;
    --ip-shadow: 0 4px 24px rgba(0, 0, 0, 0.3);
  }

  .ip-wrapper {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    color: var(--ip-text);
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px;
    line-height: 1.6;
  }

  .ip-wrapper * { box-sizing: border-box; }

  .ip-hero {
    text-align: center;
    padding: 40px 0 28px;
  }

  .ip-hero h1 {
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--ip-text);
    margin: 0 0 16px;
    line-height: 1.2;
  }

  .ip-hero h1 span { color: var(--ip-primary); }

  .ip-intro {
    font-size: 1.05rem;
    color: var(--ip-text-muted);
    max-width: 720px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .ip-updated {
    display: inline-block;
    font-size: 0.75rem;
    color: var(--ip-text-muted);
    margin-top: 12px;
    padding: 4px 12px;
    border: 1px solid var(--ip-border);
    border-radius: 20px;
  }

  /* Your IP display */
  .ip-your-ip {
    text-align: center;
    padding: 32px 24px;
    background: var(--ip-surface);
    border: 1px solid var(--ip-border);
    border-radius: var(--ip-radius);
    margin-bottom: 24px;
    box-shadow: var(--ip-shadow);
  }

  .ip-your-ip-label {
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--ip-text-muted);
    margin-bottom: 8px;
  }

  .ip-your-ip-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 2.4rem;
    font-weight: 700;
    color: var(--ip-green);
    margin-bottom: 8px;
    word-break: break-all;
  }

  .ip-your-ip-type {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 600;
    padding: 3px 10px;
    border-radius: 20px;
    background: rgba(108, 92, 231, 0.2);
    color: var(--ip-primary-light);
    margin-bottom: 12px;
  }

  .ip-copy-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 20px;
    border: 1px solid var(--ip-border-light);
    border-radius: 8px;
    background: var(--ip-surface-alt);
    color: var(--ip-text);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s;
  }

  .ip-copy-btn:hover {
    border-color: var(--ip-primary);
    background: rgba(108, 92, 231, 0.1);
  }

  .ip-copy-btn.copied {
    border-color: var(--ip-green);
    color: var(--ip-green);
  }

  /* Search bar */
  .ip-search {
    display: flex;
    gap: 8px;
    margin-bottom: 24px;
  }

  .ip-search-input {
    flex: 1;
    padding: 12px 16px;
    background: var(--ip-surface);
    border: 1px solid var(--ip-border);
    border-radius: 8px;
    color: var(--ip-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.15s;
  }

  .ip-search-input::placeholder { color: #555570; }
  .ip-search-input:focus { border-color: var(--ip-primary); }

  .ip-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
    white-space: nowrap;
  }

  .ip-btn-primary {
    background: var(--ip-primary);
    color: #fff;
  }

  .ip-btn-primary:hover {
    background: var(--ip-primary-dark);
    transform: translateY(-1px);
    box-shadow: 0 4px 16px rgba(108, 92, 231, 0.35);
  }

  .ip-btn-secondary {
    background: var(--ip-surface-alt);
    color: var(--ip-text);
    border: 1px solid var(--ip-border);
  }

  .ip-btn-secondary:hover {
    border-color: var(--ip-primary);
    background: rgba(108, 92, 231, 0.1);
  }

  /* Results cards */
  .ip-results {
    display: none;
    margin-bottom: 24px;
  }

  .ip-results.visible { display: block; }

  .ip-results-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 16px;
  }

  .ip-results-header h2 {
    font-size: 1.2rem;
    font-weight: 700;
    margin: 0;
    color: var(--ip-text);
  }

  .ip-results-ip {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    color: var(--ip-primary-light);
  }

  .ip-cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 12px;
    margin-bottom: 16px;
  }

  .ip-card {
    background: var(--ip-surface);
    border: 1px solid var(--ip-border);
    border-radius: 10px;
    padding: 16px;
    transition: border-color 0.15s;
  }

  .ip-card:hover { border-color: var(--ip-border-light); }

  .ip-card-label {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--ip-text-muted);
    margin-bottom: 4px;
  }

  .ip-card-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.95rem;
    color: var(--ip-text);
    word-break: break-all;
  }

  .ip-card-value.highlight { color: var(--ip-green); }

  .ip-error-msg {
    display: none;
    padding: 12px 16px;
    background: rgba(255, 68, 102, 0.1);
    border: 1px solid rgba(255, 68, 102, 0.3);
    border-radius: 8px;
    color: var(--ip-red);
    font-size: 0.9rem;
    margin-bottom: 16px;
  }

  .ip-error-msg.visible { display: block; }

  .ip-loading {
    display: none;
    text-align: center;
    padding: 24px;
    color: var(--ip-text-muted);
    font-size: 0.9rem;
  }

  .ip-loading.visible { display: block; }

  .ip-loading-spinner {
    display: inline-block;
    width: 20px;
    height: 20px;
    border: 2px solid var(--ip-border);
    border-top-color: var(--ip-primary);
    border-radius: 50%;
    animation: ipSpin 0.6s linear infinite;
    margin-right: 8px;
    vertical-align: middle;
  }

  @keyframes ipSpin {
    to { transform: rotate(360deg); }
  }

  /* Tabs for converter/subnet */
  .ip-tabs {
    display: flex;
    gap: 0;
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid var(--ip-border);
    margin-bottom: 20px;
  }

  .ip-tab-btn {
    flex: 1;
    padding: 10px 16px;
    background: var(--ip-bg);
    border: none;
    color: var(--ip-text-muted);
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
  }

  .ip-tab-btn:not(:last-child) { border-right: 1px solid var(--ip-border); }

  .ip-tab-btn.active {
    background: var(--ip-primary);
    color: #fff;
  }

  .ip-tab-btn:hover:not(.active) { background: var(--ip-surface); }

  .ip-tool-section {
    background: var(--ip-surface);
    border: 1px solid var(--ip-border);
    border-radius: var(--ip-radius);
    padding: 24px;
    margin-bottom: 24px;
    box-shadow: var(--ip-shadow);
  }

  .ip-tool-section h3 {
    font-size: 1rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--ip-text);
  }

  .ip-tab-panel { display: none; }
  .ip-tab-panel.active { display: block; }

  /* Converter */
  .ip-conv-row {
    display: flex;
    gap: 12px;
    margin-bottom: 12px;
    align-items: center;
  }

  .ip-conv-label {
    min-width: 80px;
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--ip-text-muted);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .ip-conv-value {
    flex: 1;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    padding: 10px 14px;
    background: var(--ip-surface-alt);
    border: 1px solid var(--ip-border);
    border-radius: 8px;
    color: var(--ip-text);
    word-break: break-all;
    user-select: all;
  }

  /* Subnet calc */
  .ip-subnet-input-row {
    display: flex;
    gap: 8px;
    margin-bottom: 16px;
    flex-wrap: wrap;
  }

  .ip-subnet-input {
    padding: 10px 14px;
    background: var(--ip-surface-alt);
    border: 1px solid var(--ip-border);
    border-radius: 8px;
    color: var(--ip-text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.15s;
  }

  .ip-subnet-input:focus { border-color: var(--ip-primary); }
  .ip-subnet-input::placeholder { color: #555570; }

  .ip-subnet-results {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .ip-subnet-item {
    padding: 10px 14px;
    background: var(--ip-surface-alt);
    border: 1px solid var(--ip-border);
    border-radius: 8px;
  }

  .ip-subnet-item-label {
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--ip-text-muted);
    margin-bottom: 2px;
  }

  .ip-subnet-item-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--ip-text);
  }

  /* Privacy info */
  .ip-privacy {
    background: var(--ip-surface);
    border: 1px solid var(--ip-border);
    border-radius: var(--ip-radius);
    padding: 24px;
    margin-bottom: 24px;
  }

  .ip-privacy h3 {
    font-size: 1rem;
    font-weight: 700;
    color: var(--ip-yellow);
    margin: 0 0 12px;
  }

  .ip-privacy p {
    color: var(--ip-text-muted);
    font-size: 0.9rem;
    line-height: 1.7;
    margin: 0 0 10px;
  }

  .ip-privacy p:last-child { margin-bottom: 0; }

  .ip-privacy ul {
    padding-left: 20px;
    margin: 0 0 10px;
    color: var(--ip-text-muted);
    font-size: 0.9rem;
    line-height: 1.8;
  }

  /* Content section */
  .ip-content {
    margin-top: 48px;
    max-width: 800px;
  }

  .ip-content h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--ip-text);
  }

  .ip-content h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin: 28px 0 10px;
    color: var(--ip-text);
  }

  .ip-content p {
    color: var(--ip-text-muted);
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .ip-content ul, .ip-content ol {
    color: var(--ip-text-muted);
    padding-left: 24px;
    margin: 0 0 16px;
    line-height: 1.8;
  }

  .ip-content code {
    background: var(--ip-surface-alt);
    padding: 2px 6px;
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85em;
    color: var(--ip-primary-light);
  }

  /* FAQ */
  .ip-faq {
    max-width: 820px;
    margin: 48px auto 40px;
  }

  .ip-faq h2 {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 0 0 24px;
    text-align: center;
    color: var(--ip-text);
  }

  .ip-faq-item {
    border: 1px solid var(--ip-border);
    border-radius: var(--ip-radius);
    padding: 20px 24px;
    margin-bottom: 12px;
    background: var(--ip-surface);
  }

  .ip-faq-item h3 {
    font-size: 1.05rem;
    font-weight: 600;
    margin: 0 0 10px;
    color: var(--ip-text);
  }

  .ip-faq-item p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--ip-text-muted);
    line-height: 1.7;
  }

  /* Meta footer */
  .ip-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 12px;
    font-size: 0.8rem;
    color: var(--ip-text-muted);
    border-top: 1px solid var(--ip-border);
    margin-bottom: 40px;
  }

  @media (max-width: 768px) {
    .ip-hero h1 { font-size: 1.6rem; }
    .ip-your-ip-value { font-size: 1.6rem; }
    .ip-search { flex-direction: column; }
    .ip-cards { grid-template-columns: 1fr; }
    .ip-conv-row { flex-direction: column; align-items: stretch; }
    .ip-conv-label { min-width: auto; }
    .ip-subnet-results { grid-template-columns: 1fr; }
    .ip-subnet-input-row { flex-direction: column; }
    .ip-subnet-input { width: 100%; }
    .ip-results-header { flex-direction: column; gap: 4px; align-items: flex-start; }
  }
</style>

<div class="ip-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="IP Address Lookup">
  <meta itemprop="applicationCategory" content="UtilitiesApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="ip-hero">
    <h1><span>IP Address</span> Lookup</h1>
    <p class="ip-intro">Find geolocation, ISP, timezone, and network details for any IP address. Your public IP is detected automatically on page load. Includes a binary/hex converter and subnet calculator.</p>
    <span class="ip-updated">Last updated: March 2026 | Free to use, no signup required</span>
  </div>

  <!-- Your IP -->
  <div class="ip-your-ip">
    <div class="ip-your-ip-label">Your Public IP Address</div>
    <div class="ip-your-ip-value" id="ipYourIp">Detecting...</div>
    <div id="ipYourType" class="ip-your-ip-type" style="display:none;"></div>
    <br>
    <button class="ip-copy-btn" id="ipCopyYourBtn" onclick="ipCopyYourIp()">Copy IP</button>
  </div>

  <!-- Search -->
  <div class="ip-search">
    <input type="text" class="ip-search-input" id="ipSearchInput" placeholder="Enter an IP address (e.g. 8.8.8.8 or 2001:4860:4860::8888)" spellcheck="false">
    <button class="ip-btn ip-btn-primary" onclick="ipLookup()">Lookup</button>
    <button class="ip-btn ip-btn-secondary" onclick="ipLookupSelf()">My IP</button>
  </div>

  <!-- Loading -->
  <div class="ip-loading" id="ipLoading">
    <span class="ip-loading-spinner"></span> Looking up IP information...
  </div>

  <!-- Error -->
  <div class="ip-error-msg" id="ipError"></div>

  <!-- Results -->
  <div class="ip-results" id="ipResults">
    <div class="ip-results-header">
      <h2>Lookup Results</h2>
      <span class="ip-results-ip" id="ipResultsIp"></span>
    </div>
    <div class="ip-cards" id="ipCards"></div>
  </div>

  <!-- Tools: Converter + Subnet -->
  <div class="ip-tool-section">
    <div class="ip-tabs">
      <button class="ip-tab-btn active" id="ipTabConv" onclick="ipSwitchTab('conv')">Binary / Hex Converter</button>
      <button class="ip-tab-btn" id="ipTabSubnet" onclick="ipSwitchTab('subnet')">Subnet Calculator</button>
    </div>

    <!-- Converter panel -->
    <div class="ip-tab-panel active" id="ipPanelConv">
      <div style="display:flex;gap:8px;margin-bottom:16px;flex-wrap:wrap;">
        <input type="text" class="ip-search-input" id="ipConvInput" placeholder="Enter IPv4 address (e.g. 192.168.1.1)" style="flex:1;min-width:200px;">
        <button class="ip-btn ip-btn-primary" onclick="ipConvert()">Convert</button>
      </div>
      <div id="ipConvResults" style="display:none;">
        <div class="ip-conv-row">
          <span class="ip-conv-label">Decimal</span>
          <div class="ip-conv-value" id="ipConvDecimal"></div>
        </div>
        <div class="ip-conv-row">
          <span class="ip-conv-label">Binary</span>
          <div class="ip-conv-value" id="ipConvBinary"></div>
        </div>
        <div class="ip-conv-row">
          <span class="ip-conv-label">Hex</span>
          <div class="ip-conv-value" id="ipConvHex"></div>
        </div>
        <div class="ip-conv-row">
          <span class="ip-conv-label">Integer</span>
          <div class="ip-conv-value" id="ipConvInt"></div>
        </div>
      </div>
    </div>

    <!-- Subnet panel -->
    <div class="ip-tab-panel" id="ipPanelSubnet">
      <div class="ip-subnet-input-row">
        <input type="text" class="ip-subnet-input" id="ipSubnetIp" placeholder="IP address (e.g. 192.168.1.100)" style="flex:1;min-width:200px;">
        <input type="text" class="ip-subnet-input" id="ipSubnetCidr" placeholder="CIDR (e.g. 24)" style="width:100px;">
        <button class="ip-btn ip-btn-primary" onclick="ipCalcSubnet()">Calculate</button>
      </div>
      <div class="ip-subnet-results" id="ipSubnetResults" style="display:none;">
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">Network Address</div>
          <div class="ip-subnet-item-value" id="ipSubNet"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">Broadcast Address</div>
          <div class="ip-subnet-item-value" id="ipSubBcast"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">Subnet Mask</div>
          <div class="ip-subnet-item-value" id="ipSubMask"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">Wildcard Mask</div>
          <div class="ip-subnet-item-value" id="ipSubWild"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">First Host</div>
          <div class="ip-subnet-item-value" id="ipSubFirst"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">Last Host</div>
          <div class="ip-subnet-item-value" id="ipSubLast"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">Total Hosts</div>
          <div class="ip-subnet-item-value" id="ipSubTotal"></div>
        </div>
        <div class="ip-subnet-item">
          <div class="ip-subnet-item-label">CIDR Notation</div>
          <div class="ip-subnet-item-value" id="ipSubCidrOut"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- Privacy Info -->
  <div class="ip-privacy">
    <h3>Protecting Your IP Privacy</h3>
    <p>Your IP address can reveal your approximate location, ISP, and network type. While it does not directly expose your street address, it gives enough information for regional targeting and basic identification. Here are ways to limit what your IP reveals:</p>
    <ul>
      <li>Use a VPN to mask your real IP with the VPN server's address</li>
      <li>Use Tor Browser to route traffic through multiple relays</li>
      <li>Use a proxy server as an intermediary for your requests</li>
      <li>Avoid clicking unknown links in emails, as they can log your IP</li>
      <li>Disable WebRTC in your browser to prevent IP leaks when using a VPN</li>
    </ul>
    <p>This tool uses third-party APIs (ipify for IP detection, ip-api.com for geolocation). The lookup request is sent from your browser directly to those services. No data is stored on our servers.</p>
  </div>

  <div class="ip-meta">
    <span>IP detection via ipify | Geolocation via ip-api.com</span>
    <span>Zovo Tools</span>
  </div>

  <!-- SEO Content -->
  <div class="ip-content">
    <h2>What Is an IP Address</h2>
    <p>An IP (Internet Protocol) address is a numerical label assigned to every device connected to a network that uses the Internet Protocol for communication. It serves two primary functions: identifying the host or network interface and providing the location of the host in the network topology. Every time you connect to the internet, your router is assigned a public IP by your Internet Service Provider (ISP), and that address is visible to every server you communicate with.</p>
    <p>There are two formats in use today. IPv4 addresses are 32 bits long and written as four decimal octets separated by dots, like <code>192.168.1.1</code>. IPv6 addresses are 128 bits long and written as eight groups of four hexadecimal digits separated by colons, like <code>2001:0db8:85a3:0000:0000:8a2e:0370:7334</code>. IPv6 was introduced because the roughly 4.3 billion addresses available in IPv4 are not enough for the growing number of internet-connected devices.</p>

    <h3>IPv4 vs IPv6</h3>
    <p>IPv4 has been the backbone of internet addressing since 1981. Its 32-bit format supports around 4.3 billion unique addresses. With network address translation (NAT), private address ranges like <code>10.0.0.0/8</code>, <code>172.16.0.0/12</code>, and <code>192.168.0.0/16</code> allow multiple devices to share a single public IP. IPv6, standardized in 1998, uses 128 bits to provide approximately 340 undecillion addresses, enough for every grain of sand on Earth to have its own address many times over. IPv6 also includes improvements such as built-in IPsec support, simplified header structure, and no need for NAT.</p>

    <h3>How IP Geolocation Works</h3>
    <p>IP geolocation maps an IP address to an approximate physical location. It works by maintaining databases that associate IP address ranges with geographic regions. ISPs are allocated blocks of IP addresses by Regional Internet Registries (RIRs) like ARIN, RIPE NCC, and APNIC. Since ISPs serve specific geographic areas, the allocated ranges correlate with locations. Geolocation databases combine this registry data with data from sources like GPS-enabled devices, Wi-Fi access point locations, and user-submitted corrections.</p>
    <p>Accuracy varies. Country-level detection is typically 95-99% accurate. City-level accuracy drops to about 50-80% depending on the region. IP geolocation cannot pinpoint a street address. For mobile users on cellular networks, the detected location may correspond to the carrier's regional gateway rather than the device's actual position.</p>

    <h3>Understanding Subnets and CIDR</h3>
    <p>A subnet is a logical subdivision of an IP network. Subnetting allows network administrators to divide a large network into smaller segments, improving security and reducing broadcast traffic. The subnet mask determines which portion of an IP address identifies the network and which portion identifies the host.</p>
    <p>CIDR (Classless Inter-Domain Routing) notation expresses an IP address and its subnet mask as a single value. For example, <code>192.168.1.0/24</code> means the first 24 bits define the network, leaving 8 bits for host addresses. That gives 256 total addresses (254 usable hosts, since the network address and broadcast address are reserved). A <code>/16</code> provides 65,534 hosts, while a <code>/30</code> provides just 2 hosts and is commonly used for point-to-point links between routers.</p>

    <h3>Common Private IP Ranges</h3>
    <ul>
      <li><code>10.0.0.0/8</code> (10.0.0.0 to 10.255.255.255) -- Class A private range, 16 million addresses</li>
      <li><code>172.16.0.0/12</code> (172.16.0.0 to 172.31.255.255) -- Class B private range, 1 million addresses</li>
      <li><code>192.168.0.0/16</code> (192.168.0.0 to 192.168.255.255) -- Class C private range, 65 thousand addresses</li>
      <li><code>127.0.0.0/8</code> -- Loopback addresses (localhost)</li>
      <li><code>169.254.0.0/16</code> -- Link-local addresses (auto-assigned when DHCP fails)</li>
    </ul>

    <h3>IP Addresses and Security</h3>
    <p>An IP address alone does not give an attacker direct access to your device, but it can be used in several ways. Attackers can use your IP to probe for open ports and running services using tools like Nmap. They can attempt denial-of-service attacks aimed at your IP. In targeted attacks, an IP address combined with other data points can help identify or locate an individual. Server administrators use IP addresses for rate limiting, geo-blocking, and access control. Firewalls and intrusion detection systems track IP addresses to identify and block malicious traffic patterns.</p>
  </div>

  <!-- FAQ -->
  <div class="ip-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="ip-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What can someone do with my IP address?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">An IP address reveals your approximate location (city or region), your ISP, and your connection type. Someone with your IP could attempt port scanning to find open services, launch denial-of-service attacks, or use it for geographic targeting. However, an IP address alone cannot be used to directly access your device, read your files, or learn your identity. Your ISP keeps the mapping between your IP and your account details, and only law enforcement with a legal order can request that information.</p>
      </div>
    </div>

    <div class="ip-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How accurate is IP geolocation?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Country-level accuracy is typically above 95%. City-level accuracy ranges from 50% to 80% depending on the region and the geolocation database. IP geolocation cannot determine a street address. For users on corporate VPNs, the detected location will be the VPN exit point. For mobile users on cellular data, the location may show the carrier's regional hub rather than the device's position. If you use a VPN, proxy, or Tor, the geolocation will reflect the server you are routing through, not your actual location.</p>
      </div>
    </div>

    <div class="ip-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is the difference between a public and private IP address?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A public IP address is assigned to your router by your ISP and is visible to every server you connect to on the internet. A private IP address is assigned to devices within your local network (like your laptop, phone, or smart TV) by your router. Private IPs use reserved ranges (10.x.x.x, 172.16-31.x.x, 192.168.x.x) and are not routable on the public internet. Your router uses Network Address Translation (NAT) to map traffic between your private devices and the single public IP.</p>
      </div>
    </div>

    <div class="ip-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Does my IP address change?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Most residential ISPs assign dynamic IP addresses, which means your public IP can change periodically, typically when your router restarts or when the DHCP lease expires. Some ISPs rarely change your IP, while others rotate it more frequently. Business accounts often include static IP addresses that remain constant. You can check whether your IP has changed by bookmarking this tool and comparing results over time. If you need a stable IP, contact your ISP about a static IP option.</p>
      </div>
    </div>

    <div class="ip-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Why does the lookup show a different city than where I am?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">IP geolocation databases map IP ranges to locations based on ISP registration data, which may not match your exact position. Your ISP might route your traffic through a hub in a nearby city. If you are using a VPN, the location shown will be the VPN server's location. Mobile carriers often show the city where their nearest network gateway is located rather than the tower you are connected to. Satellite internet services may show a location that is hundreds of miles away from you.</p>
      </div>
    </div>
  </div>

  <!-- Related Tools -->
  <div style="padding:1.5rem;background:var(--ip-surface);border:1px solid var(--ip-border);border-radius:12px;margin-bottom:20px;">
    <h2 style="color:var(--ip-primary);font-size:1.3rem;margin:0 0 1rem;">Related Tools</h2>
    <ul style="list-style:none;padding:0;margin:0;">
      <li style="margin-bottom:0.5rem;"><a href="/tools/url-encoder/" style="color:var(--ip-green);text-decoration:none;">URL Encoder/Decoder</a> -- Encode and decode URLs and query parameters</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/password-generator/" style="color:var(--ip-green);text-decoration:none;">Password Generator</a> -- Generate secure random passwords</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/json-formatter/" style="color:var(--ip-green);text-decoration:none;">JSON Formatter</a> -- Format and validate JSON data</li>
      <li style="margin-bottom:0.5rem;"><a href="/tools/uuid-generator/" style="color:var(--ip-green);text-decoration:none;">UUID Generator</a> -- Generate random UUID values</li>
    </ul>
  </div>

  <!-- Author Box -->
  <div style="padding:1.5rem;background:var(--ip-surface);border:1px solid var(--ip-border);border-radius:12px;display:flex;gap:1rem;align-items:center;margin-bottom:20px;">
    <div style="width:48px;height:48px;border-radius:50%;background:var(--ip-primary);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1.2rem;flex-shrink:0;">ML</div>
    <div>
      <div style="color:var(--ip-text);font-weight:600;">Michael Lip</div>
      <div style="color:var(--ip-text-muted);font-size:0.85rem;">Developer and tools engineer at <a href="https://zovo.one" style="color:var(--ip-primary);">Zovo</a>. Building free developer and productivity tools.</div>
    </div>
  </div>

  <footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid var(--ip-border);margin-top:1rem;">
    <p>Built by <a href="https://zovo.one" style="color:var(--ip-primary);text-decoration:none;">Michael Lip</a> at <a href="https://zovo.one" style="color:var(--ip-primary);text-decoration:none;">zovo.one</a></p>
  </footer>
</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebApplication",
      "name": "IP Address Lookup",
      "url": "https://zovo.one/tools/ip-lookup/",
      "applicationCategory": "UtilitiesApplication",
      "operatingSystem": "Any",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
      "author": { "@type": "Person", "name": "Michael Lip", "url": "https://zovo.one" },
      "datePublished": "2026-03-19",
      "dateModified": "2026-03-19"
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://zovo.one/" },
        { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://zovo.one/tools/" },
        { "@type": "ListItem", "position": 3, "name": "IP Address Lookup", "item": "https://zovo.one/tools/ip-lookup/" }
      ]
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What can someone do with my IP address?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "An IP address reveals your approximate location, ISP, and connection type. Someone with your IP could attempt port scanning, launch denial-of-service attacks, or use it for geographic targeting. However, it cannot be used to directly access your device or learn your identity."
          }
        },
        {
          "@type": "Question",
          "name": "How accurate is IP geolocation?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Country-level accuracy is above 95%. City-level accuracy ranges from 50% to 80%. IP geolocation cannot determine a street address. VPN, proxy, or Tor users will see the exit node location."
          }
        },
        {
          "@type": "Question",
          "name": "What is the difference between a public and private IP address?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A public IP is assigned by your ISP and visible on the internet. A private IP is assigned by your router to devices on your local network using reserved ranges like 192.168.x.x, and is not routable on the public internet."
          }
        },
        {
          "@type": "Question",
          "name": "Does my IP address change?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most residential ISPs assign dynamic IPs that can change when your router restarts or the DHCP lease expires. Business accounts often have static IPs. Check this tool periodically to see if yours has changed."
          }
        },
        {
          "@type": "Question",
          "name": "Why does the lookup show a different city than where I am?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Geolocation databases map IP ranges based on ISP registration data, which may not match your exact position. VPNs, mobile carriers, and satellite internet can all cause mismatches between your actual and detected location."
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

<script>
(function() {
  "use strict";

  var userIp = "";
  var countryFlags = {"AF":"\uD83C\uDDE6\uD83C\uDDEB","AL":"\uD83C\uDDE6\uD83C\uDDF1","DZ":"\uD83C\uDDE9\uD83C\uDDFF","AR":"\uD83C\uDDE6\uD83C\uDDF7","AU":"\uD83C\uDDE6\uD83C\uDDFA","AT":"\uD83C\uDDE6\uD83C\uDDF9","BE":"\uD83C\uDDE7\uD83C\uDDEA","BR":"\uD83C\uDDE7\uD83C\uDDF7","CA":"\uD83C\uDDE8\uD83C\uDDE6","CL":"\uD83C\uDDE8\uD83C\uDDF1","CN":"\uD83C\uDDE8\uD83C\uDDF3","CO":"\uD83C\uDDE8\uD83C\uDDF4","CZ":"\uD83C\uDDE8\uD83C\uDDFF","DK":"\uD83C\uDDE9\uD83C\uDDF0","EG":"\uD83C\uDDEA\uD83C\uDDEC","FI":"\uD83C\uDDEB\uD83C\uDDEE","FR":"\uD83C\uDDEB\uD83C\uDDF7","DE":"\uD83C\uDDE9\uD83C\uDDEA","GR":"\uD83C\uDDEC\uD83C\uDDF7","HK":"\uD83C\uDDED\uD83C\uDDF0","HU":"\uD83C\uDDED\uD83C\uDDFA","IN":"\uD83C\uDDEE\uD83C\uDDF3","ID":"\uD83C\uDDEE\uD83C\uDDE9","IE":"\uD83C\uDDEE\uD83C\uDDEA","IL":"\uD83C\uDDEE\uD83C\uDDF1","IT":"\uD83C\uDDEE\uD83C\uDDF9","JP":"\uD83C\uDDEF\uD83C\uDDF5","KR":"\uD83C\uDDF0\uD83C\uDDF7","MY":"\uD83C\uDDF2\uD83C\uDDFE","MX":"\uD83C\uDDF2\uD83C\uDDFD","NL":"\uD83C\uDDF3\uD83C\uDDF1","NZ":"\uD83C\uDDF3\uD83C\uDDFF","NG":"\uD83C\uDDF3\uD83C\uDDEC","NO":"\uD83C\uDDF3\uD83C\uDDF4","PK":"\uD83C\uDDF5\uD83C\uDDF0","PH":"\uD83C\uDDF5\uD83C\uDDED","PL":"\uD83C\uDDF5\uD83C\uDDF1","PT":"\uD83C\uDDF5\uD83C\uDDF9","RO":"\uD83C\uDDF7\uD83C\uDDF4","RU":"\uD83C\uDDF7\uD83C\uDDFA","SA":"\uD83C\uDDF8\uD83C\uDDE6","SG":"\uD83C\uDDF8\uD83C\uDDEC","ZA":"\uD83C\uDDFF\uD83C\uDDE6","ES":"\uD83C\uDDEA\uD83C\uDDF8","SE":"\uD83C\uDDF8\uD83C\uDDEA","CH":"\uD83C\uDDE8\uD83C\uDDED","TW":"\uD83C\uDDF9\uD83C\uDDFC","TH":"\uD83C\uDDF9\uD83C\uDDED","TR":"\uD83C\uDDF9\uD83C\uDDF7","UA":"\uD83C\uDDFA\uD83C\uDDE6","AE":"\uD83C\uDDE6\uD83C\uDDEA","GB":"\uD83C\uDDEC\uD83C\uDDE7","US":"\uD83C\uDDFA\uD83C\uDDF8","VN":"\uD83C\uDDFB\uD83C\uDDF3"};

  function isIPv6(ip) {
    return ip.indexOf(":") !== -1;
  }

  function detectIpType(ip) {
    if (isIPv6(ip)) return "IPv6";
    return "IPv4";
  }

  // Detect user IP on load
  function detectUserIp() {
    fetch("https://api.ipify.org?format=json")
      .then(function(r) { return r.json(); })
      .then(function(data) {
        userIp = data.ip;
        document.getElementById("ipYourIp").textContent = userIp;
        var typeEl = document.getElementById("ipYourType");
        typeEl.textContent = detectIpType(userIp);
        typeEl.style.display = "inline-block";
        // Auto-lookup geolocation for user IP
        fetchGeo(userIp);
      })
      .catch(function() {
        // Fallback: try ipv4 specific
        fetch("https://api4.ipify.org?format=json")
          .then(function(r) { return r.json(); })
          .then(function(data) {
            userIp = data.ip;
            document.getElementById("ipYourIp").textContent = userIp;
            var typeEl = document.getElementById("ipYourType");
            typeEl.textContent = "IPv4";
            typeEl.style.display = "inline-block";
            fetchGeo(userIp);
          })
          .catch(function() {
            document.getElementById("ipYourIp").textContent = "Could not detect IP";
          });
      });
  }

  function showLoading(show) {
    document.getElementById("ipLoading").classList.toggle("visible", show);
  }

  function showError(msg) {
    var el = document.getElementById("ipError");
    if (msg) {
      el.textContent = msg;
      el.classList.add("visible");
    } else {
      el.classList.remove("visible");
    }
  }

  function fetchGeo(ip) {
    showLoading(true);
    showError(null);
    document.getElementById("ipResults").classList.remove("visible");

    // ip-api.com free tier is HTTP only
    fetch("http://ip-api.com/json/" + encodeURIComponent(ip) + "?fields=status,message,country,countryCode,region,regionName,city,zip,lat,lon,timezone,isp,org,as,query")
      .then(function(r) { return r.json(); })
      .then(function(data) {
        showLoading(false);
        if (data.status === "fail") {
          showError("Lookup failed: " + (data.message || "Unknown error") + ". The IP may be private or invalid.");
          return;
        }
        renderResults(data);
      })
      .catch(function() {
        showLoading(false);
        // Fallback: try ipapi.co (HTTPS, limited free tier)
        fetch("https://ipapi.co/" + encodeURIComponent(ip) + "/json/")
          .then(function(r) { return r.json(); })
          .then(function(data) {
            if (data.error) {
              showError("Geolocation lookup failed. The free API may be rate-limited or the IP may be private. Your IP is still shown above.");
              return;
            }
            renderResultsFallback(data);
          })
          .catch(function() {
            showError("Geolocation lookup failed. This may be due to HTTPS restrictions on the free API tier, or you may be rate-limited. Your IP is still displayed above.");
          });
      });
  }

  function renderResults(data) {
    var flag = countryFlags[data.countryCode] || "";
    var cards = [
      { label: "IP Address", value: data.query, highlight: true },
      { label: "City", value: data.city || "N/A" },
      { label: "Region / State", value: data.regionName || "N/A" },
      { label: "Country", value: flag + " " + (data.country || "N/A") + (data.countryCode ? " (" + data.countryCode + ")" : "") },
      { label: "ZIP / Postal", value: data.zip || "N/A" },
      { label: "Latitude", value: data.lat != null ? String(data.lat) : "N/A" },
      { label: "Longitude", value: data.lon != null ? String(data.lon) : "N/A" },
      { label: "Timezone", value: data.timezone || "N/A" },
      { label: "ISP", value: data.isp || "N/A" },
      { label: "Organization", value: data.org || "N/A" },
      { label: "AS Number", value: data.as || "N/A" },
      { label: "IP Version", value: detectIpType(data.query) }
    ];
    renderCards(data.query, cards);
  }

  function renderResultsFallback(data) {
    var flag = countryFlags[data.country_code] || "";
    var cards = [
      { label: "IP Address", value: data.ip, highlight: true },
      { label: "City", value: data.city || "N/A" },
      { label: "Region / State", value: data.region || "N/A" },
      { label: "Country", value: flag + " " + (data.country_name || "N/A") + (data.country_code ? " (" + data.country_code + ")" : "") },
      { label: "ZIP / Postal", value: data.postal || "N/A" },
      { label: "Latitude", value: data.latitude != null ? String(data.latitude) : "N/A" },
      { label: "Longitude", value: data.longitude != null ? String(data.longitude) : "N/A" },
      { label: "Timezone", value: data.timezone || "N/A" },
      { label: "ISP", value: data.org || "N/A" },
      { label: "Organization", value: data.org || "N/A" },
      { label: "AS Number", value: data.asn ? "AS" + data.asn : "N/A" },
      { label: "IP Version", value: data.version || detectIpType(data.ip) }
    ];
    renderCards(data.ip, cards);
  }

  function renderCards(ip, cards) {
    document.getElementById("ipResultsIp").textContent = ip;
    var container = document.getElementById("ipCards");
    var html = "";
    for (var i = 0; i < cards.length; i++) {
      var cls = cards[i].highlight ? " highlight" : "";
      html += '<div class="ip-card">';
      html += '<div class="ip-card-label">' + cards[i].label + '</div>';
      html += '<div class="ip-card-value' + cls + '">' + escapeHtml(cards[i].value) + '</div>';
      html += '</div>';
    }
    container.innerHTML = html;
    document.getElementById("ipResults").classList.add("visible");
  }

  function escapeHtml(str) {
    var div = document.createElement("div");
    div.appendChild(document.createTextNode(str));
    return div.innerHTML;
  }

  // Copy your IP
  window.ipCopyYourIp = function() {
    if (!userIp) return;
    navigator.clipboard.writeText(userIp).then(function() {
      var btn = document.getElementById("ipCopyYourBtn");
      btn.textContent = "Copied";
      btn.classList.add("copied");
      setTimeout(function() {
        btn.textContent = "Copy IP";
        btn.classList.remove("copied");
      }, 2000);
    });
  };

  // Lookup
  window.ipLookup = function() {
    var input = document.getElementById("ipSearchInput").value.trim();
    if (!input) {
      showError("Enter an IP address to look up.");
      return;
    }
    // Basic validation
    var ipv4 = /^(\d{1,3}\.){3}\d{1,3}$/;
    var ipv6 = /^([0-9a-fA-F]{0,4}:){2,7}[0-9a-fA-F]{0,4}$/;
    if (!ipv4.test(input) && !ipv6.test(input)) {
      showError("That does not look like a valid IPv4 or IPv6 address.");
      return;
    }
    fetchGeo(input);
  };

  window.ipLookupSelf = function() {
    if (userIp) {
      document.getElementById("ipSearchInput").value = userIp;
      fetchGeo(userIp);
    }
  };

  // Tab switching
  window.ipSwitchTab = function(tab) {
    document.getElementById("ipTabConv").classList.toggle("active", tab === "conv");
    document.getElementById("ipTabSubnet").classList.toggle("active", tab === "subnet");
    document.getElementById("ipPanelConv").classList.toggle("active", tab === "conv");
    document.getElementById("ipPanelSubnet").classList.toggle("active", tab === "subnet");
  };

  // IP Converter
  window.ipConvert = function() {
    var input = document.getElementById("ipConvInput").value.trim();
    if (!input) return;

    var parts = input.split(".");
    if (parts.length !== 4) {
      document.getElementById("ipConvResults").style.display = "none";
      return;
    }

    var valid = true;
    var octets = [];
    for (var i = 0; i < 4; i++) {
      var n = parseInt(parts[i], 10);
      if (isNaN(n) || n < 0 || n > 255) { valid = false; break; }
      octets.push(n);
    }
    if (!valid) {
      document.getElementById("ipConvResults").style.display = "none";
      return;
    }

    var binary = octets.map(function(o) {
      return ("00000000" + o.toString(2)).slice(-8);
    }).join(".");

    var hex = octets.map(function(o) {
      return ("00" + o.toString(16).toUpperCase()).slice(-2);
    }).join(".");

    var integer = ((octets[0] << 24) >>> 0) + (octets[1] << 16) + (octets[2] << 8) + octets[3];

    document.getElementById("ipConvDecimal").textContent = input;
    document.getElementById("ipConvBinary").textContent = binary;
    document.getElementById("ipConvHex").textContent = "0x" + hex.replace(/\./g, "");
    document.getElementById("ipConvInt").textContent = integer.toString();
    document.getElementById("ipConvResults").style.display = "block";
  };

  // Subnet Calculator
  window.ipCalcSubnet = function() {
    var ipInput = document.getElementById("ipSubnetIp").value.trim();
    var cidrInput = document.getElementById("ipSubnetCidr").value.trim();

    if (!ipInput || !cidrInput) return;

    var parts = ipInput.split(".");
    if (parts.length !== 4) return;

    var cidr = parseInt(cidrInput, 10);
    if (isNaN(cidr) || cidr < 0 || cidr > 32) return;

    var octets = [];
    for (var i = 0; i < 4; i++) {
      var n = parseInt(parts[i], 10);
      if (isNaN(n) || n < 0 || n > 255) return;
      octets.push(n);
    }

    var ipInt = ((octets[0] << 24) >>> 0) + (octets[1] << 16) + (octets[2] << 8) + octets[3];

    // Subnet mask
    var mask = cidr === 0 ? 0 : (0xFFFFFFFF << (32 - cidr)) >>> 0;
    var network = (ipInt & mask) >>> 0;
    var broadcast = (network | (~mask >>> 0)) >>> 0;
    var wildcard = (~mask) >>> 0;

    var hostBits = 32 - cidr;
    var totalHosts = hostBits >= 2 ? Math.pow(2, hostBits) - 2 : (hostBits === 1 ? 2 : 1);

    var firstHost = hostBits >= 2 ? network + 1 : network;
    var lastHost = hostBits >= 2 ? broadcast - 1 : broadcast;

    function intToIp(n) {
      return [(n >>> 24) & 255, (n >>> 16) & 255, (n >>> 8) & 255, n & 255].join(".");
    }

    document.getElementById("ipSubNet").textContent = intToIp(network);
    document.getElementById("ipSubBcast").textContent = intToIp(broadcast);
    document.getElementById("ipSubMask").textContent = intToIp(mask);
    document.getElementById("ipSubWild").textContent = intToIp(wildcard);
    document.getElementById("ipSubFirst").textContent = intToIp(firstHost);
    document.getElementById("ipSubLast").textContent = intToIp(lastHost);
    document.getElementById("ipSubTotal").textContent = totalHosts.toLocaleString();
    document.getElementById("ipSubCidrOut").textContent = intToIp(network) + "/" + cidr;
    document.getElementById("ipSubnetResults").style.display = "grid";
  };

  // Enter key triggers lookup
  document.getElementById("ipSearchInput").addEventListener("keydown", function(e) {
    if (e.key === "Enter") {
      e.preventDefault();
      ipLookup();
    }
  });

  document.getElementById("ipConvInput").addEventListener("keydown", function(e) {
    if (e.key === "Enter") { e.preventDefault(); ipConvert(); }
  });

  document.getElementById("ipSubnetIp").addEventListener("keydown", function(e) {
    if (e.key === "Enter") { e.preventDefault(); ipCalcSubnet(); }
  });

  document.getElementById("ipSubnetCidr").addEventListener("keydown", function(e) {
    if (e.key === "Enter") { e.preventDefault(); ipCalcSubnet(); }
  });

  // Init
  detectUserIp();
})();
</script>
