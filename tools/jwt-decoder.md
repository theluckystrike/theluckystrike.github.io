---
layout: page
title: "JWT Decoder - Free Online JWT Token Decoder | Zovo"
description: "Free JWT decoder online -- paste a JSON Web Token and instantly see the decoded header, payload, and expiration status. Runs entirely in your browser."
permalink: /tools/jwt-decoder/
keywords: "jwt decoder, jwt decoder online, jwt token decoder, decode jwt, json web token decoder, jwt parser, jwt validator"
date: 2026-03-18
last_modified_at: 2026-03-18
categories: [tools]
tags: [jwt decoder, json web token, jwt parser, developer tools, online tools]
author: Michael Lip
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  :root {
    --jd-primary: #6C5CE7;
    --jd-primary-dark: #5A4BD1;
    --jd-bg: #F8F9FE;
    --jd-surface: #FFFFFF;
    --jd-text: #2D3436;
    --jd-text-muted: #636E72;
    --jd-border: #DFE6E9;
    --jd-success: #00B894;
    --jd-error: #D63031;
    --jd-warning: #FDCB6E;
    --jd-radius: 12px;
  }
  .jd-wrapper { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--jd-text); max-width: 900px; margin: 0 auto; padding: 0 16px; line-height: 1.6; }
  .jd-wrapper * { box-sizing: border-box; }
  .jd-hero { text-align: center; padding: 40px 0 28px; }
  .jd-hero h1 { font-size: 2.2rem; font-weight: 700; margin: 0 0 16px; line-height: 1.2; }
  .jd-hero h1 span { color: var(--jd-primary); }
  .jd-intro { font-size: 1.05rem; color: var(--jd-text-muted); max-width: 720px; margin: 0 auto; line-height: 1.7; }
  .jd-panel { background: var(--jd-surface); border: 1px solid var(--jd-border); border-radius: var(--jd-radius); overflow: hidden; margin-bottom: 20px; box-shadow: 0 2px 12px rgba(108,92,231,0.06); }
  .jd-panel-header { display: flex; align-items: center; justify-content: space-between; padding: 10px 16px; background: var(--jd-bg); border-bottom: 1px solid var(--jd-border); font-size: 0.8rem; font-weight: 600; color: var(--jd-text-muted); text-transform: uppercase; letter-spacing: 0.05em; }
  .jd-input-area { width: 100%; min-height: 120px; border: none; padding: 16px; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; line-height: 1.6; resize: vertical; outline: none; color: var(--jd-text); background: var(--jd-surface); word-break: break-all; }
  .jd-input-area::placeholder { color: #B2BEC3; }
  .jd-decoded { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px; }
  .jd-output-area { width: 100%; min-height: 200px; padding: 16px; font-family: 'JetBrains Mono', monospace; font-size: 0.82rem; line-height: 1.7; overflow: auto; white-space: pre-wrap; word-break: break-word; background: var(--jd-surface); color: var(--jd-text); }
  .jd-string { color: #00B894; }
  .jd-number { color: #6C5CE7; }
  .jd-boolean { color: #E17055; }
  .jd-null { color: #B2BEC3; font-style: italic; }
  .jd-key { color: #0984E3; }
  .jd-status { display: flex; align-items: center; gap: 12px; padding: 14px 20px; margin-bottom: 20px; border-radius: var(--jd-radius); font-size: 0.9rem; font-weight: 600; flex-wrap: wrap; }
  .jd-status-valid { background: rgba(0,184,148,0.1); border: 1px solid rgba(0,184,148,0.2); color: var(--jd-success); }
  .jd-status-expired { background: rgba(214,48,49,0.1); border: 1px solid rgba(214,48,49,0.2); color: var(--jd-error); }
  .jd-status-no-exp { background: var(--jd-bg); border: 1px solid var(--jd-border); color: var(--jd-text-muted); }
  .jd-status-error { background: rgba(214,48,49,0.1); border: 1px solid rgba(214,48,49,0.2); color: var(--jd-error); }
  .jd-status-detail { font-weight: 400; font-size: 0.85rem; }
  .jd-btn { display: inline-flex; align-items: center; gap: 6px; padding: 6px 14px; border: none; border-radius: 6px; font-family: 'Inter', sans-serif; font-size: 0.8rem; font-weight: 500; cursor: pointer; transition: all 0.15s; }
  .jd-btn-sm { background: var(--jd-bg); color: var(--jd-text); border: 1px solid var(--jd-border); }
  .jd-btn-sm:hover { background: var(--jd-border); }
  .jd-btn-sm.copied { background: var(--jd-success); color: #fff; border-color: var(--jd-success); }
  .jd-btn-primary { padding: 8px 16px; background: var(--jd-primary); color: #fff; font-size: 0.875rem; font-weight: 600; border-radius: 8px; }
  .jd-btn-primary:hover { background: var(--jd-primary-dark); }
  .jd-btn-secondary { padding: 8px 16px; background: var(--jd-bg); color: var(--jd-text); border: 1px solid var(--jd-border); font-size: 0.875rem; font-weight: 600; border-radius: 8px; }
  .jd-btn-secondary:hover { background: var(--jd-border); }
  .jd-toolbar { display: flex; gap: 8px; padding: 12px 16px; flex-wrap: wrap; }
  .jd-claims { margin-bottom: 20px; }
  .jd-claims-grid { display: grid; grid-template-columns: auto 1fr; gap: 0; border: 1px solid var(--jd-border); border-radius: var(--jd-radius); overflow: hidden; }
  .jd-claim-key, .jd-claim-val { padding: 8px 14px; font-size: 0.85rem; border-bottom: 1px solid var(--jd-border); }
  .jd-claim-key { background: var(--jd-bg); font-weight: 600; font-family: 'JetBrains Mono', monospace; color: var(--jd-primary); white-space: nowrap; }
  .jd-claim-val { font-family: 'JetBrains Mono', monospace; word-break: break-all; }
  .jd-claims-grid > :nth-last-child(-n+2) { border-bottom: none; }
  .jd-meta { display: flex; justify-content: space-between; align-items: center; padding-top: 12px; font-size: 0.8rem; color: var(--jd-text-muted); border-top: 1px solid var(--jd-border); margin-bottom: 40px; }
  .jd-faq { max-width: 820px; margin: 0 auto 60px; }
  .jd-faq h2 { font-size: 1.5rem; font-weight: 700; margin: 0 0 24px; text-align: center; }
  .jd-faq-item { border: 1px solid var(--jd-border); border-radius: var(--jd-radius); padding: 20px 24px; margin-bottom: 12px; background: var(--jd-surface); box-shadow: 0 1px 4px rgba(108,92,231,0.04); }
  .jd-faq-item h3 { font-size: 1.05rem; font-weight: 600; margin: 0 0 10px; }
  .jd-faq-item p { margin: 0; font-size: 0.95rem; color: var(--jd-text-muted); line-height: 1.7; }
  @media (max-width: 768px) {
    .jd-hero h1 { font-size: 1.6rem; }
    .jd-decoded { grid-template-columns: 1fr; }
  }
</style>

<div class="jd-wrapper" itemscope itemtype="https://schema.org/WebApplication">
  <meta itemprop="name" content="JWT Decoder">
  <meta itemprop="applicationCategory" content="DeveloperApplication">
  <meta itemprop="operatingSystem" content="Any">
  <meta itemprop="offers" itemscope itemtype="https://schema.org/Offer" content="">
  <meta itemprop="price" content="0">

  <div class="jd-hero">
    <h1><span>JWT Decoder</span> Online</h1>
    <p class="jd-intro">Decode JSON Web Tokens instantly with this free JWT decoder online. Paste your JWT token to see the decoded header, payload, and expiration status -- all processed locally in your browser with nothing sent to any server.</p>
  </div>

  <div class="jd-panel">
    <div class="jd-panel-header"><span>Encoded JWT Token</span></div>
    <textarea id="jdInput" class="jd-input-area" placeholder="Paste your JWT token here...&#10;&#10;eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6Ikpv..." spellcheck="false"></textarea>
    <div class="jd-toolbar">
      <button class="jd-btn jd-btn-primary" onclick="jdDecode()">Decode Token</button>
      <button class="jd-btn jd-btn-secondary" onclick="jdLoadSample()">Load Sample</button>
      <button class="jd-btn jd-btn-secondary" onclick="jdClear()">Clear</button>
    </div>
  </div>

  <div id="jdStatus"></div>

  <div class="jd-decoded">
    <div class="jd-panel">
      <div class="jd-panel-header">
        <span>Header</span>
        <button class="jd-btn jd-btn-sm" onclick="jdCopySection('header', this)">Copy</button>
      </div>
      <div id="jdHeader" class="jd-output-area" style="min-height:120px;"></div>
    </div>
    <div class="jd-panel">
      <div class="jd-panel-header">
        <span>Payload</span>
        <button class="jd-btn jd-btn-sm" onclick="jdCopySection('payload', this)">Copy</button>
      </div>
      <div id="jdPayload" class="jd-output-area" style="min-height:120px;"></div>
    </div>
  </div>

  <div id="jdClaimsSection" class="jd-claims" style="display:none;">
    <div style="font-size:0.8rem;font-weight:600;color:#636E72;text-transform:uppercase;letter-spacing:0.05em;margin-bottom:12px;">Registered Claims</div>
    <div class="jd-claims-grid" id="jdClaimsGrid"></div>
  </div>

  <div class="jd-meta">
    <span>All decoding happens in your browser</span>
    <span>Zovo Tools</span>
  </div>

  <div class="jd-faq" itemscope itemtype="https://schema.org/FAQPage">
    <h2>Frequently Asked Questions</h2>

    <div class="jd-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">What is a JWT token?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">A JWT (JSON Web Token) is a compact, URL-safe token format defined by RFC 7519. It consists of three Base64url-encoded parts separated by dots: a header (algorithm and type), a payload (claims about a user or session), and a signature. JWTs are commonly used for authentication, authorization, and secure information exchange between services. This JWT decoder lets you inspect the header and payload without needing a secret key.</p>
      </div>
    </div>

    <div class="jd-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Can this tool verify the JWT signature?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">This tool decodes and displays the header and payload, but it does not verify the cryptographic signature. Signature verification requires the secret key (HMAC) or public key (RSA/ECDSA), which should never be shared with a web tool. This decoder is designed for inspecting token contents, checking expiration times, and debugging claims -- tasks that do not require the signing key.</p>
      </div>
    </div>

    <div class="jd-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">How does the expiration check work?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">When a JWT payload contains an "exp" (expiration time) claim, this decoder compares that Unix timestamp to your current system time. If the expiration time is in the past, the token is marked as expired. If it is in the future, you will see a "valid" status with the remaining time. Tokens without an "exp" claim are flagged accordingly since they never expire on their own.</p>
      </div>
    </div>

    <div class="jd-faq-item" itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
      <h3 itemprop="name">Is it safe to paste my JWT token into this decoder?</h3>
      <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
        <p itemprop="text">Yes. This JWT decoder runs entirely in your browser using JavaScript. Your token is never transmitted to any server, stored, or logged. You can confirm this by monitoring the Network tab in your browser's developer tools. However, as a general security practice, avoid sharing production tokens with any third-party service. If a token has been compromised, revoke it through your authentication provider.</p>
      </div>
    </div>
  </div>

  <footer style="text-align:center;padding:2rem 0;color:#8888a0;font-size:0.85rem;border-top:1px solid #2a2a3a;margin-top:3rem;">
    <p>Built by <a href="https://zovo.one" style="color:#6C5CE7;text-decoration:none;">Michael Lip</a>. More tools at <a href="https://zovo.one/tools" style="color:#6C5CE7;text-decoration:none;">zovo.one</a></p>
  </footer>
</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "JWT Decoder Online",
  "url": "https://zovo.one/tools/jwt-decoder/",
  "applicationCategory": "DeveloperApplication",
  "operatingSystem": "Any",
  "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
  "author": { "@type": "Person", "name": "Michael Lip" }
}
</script>

<script>
(function() {
  "use strict";

  var inputEl = document.getElementById("jdInput");
  var headerEl = document.getElementById("jdHeader");
  var payloadEl = document.getElementById("jdPayload");
  var statusEl = document.getElementById("jdStatus");
  var claimsSection = document.getElementById("jdClaimsSection");
  var claimsGrid = document.getElementById("jdClaimsGrid");

  var decoded = { header: null, payload: null };

  var SAMPLE = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiZW1haWwiOiJqb2huQGV4YW1wbGUuY29tIiwicm9sZSI6ImFkbWluIiwiaWF0IjoxNzQyMjUyODAwLCJleHAiOjE3NDIzMzkyMDB9.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c";

  var CLAIM_NAMES = {
    iss: "Issuer",
    sub: "Subject",
    aud: "Audience",
    exp: "Expiration Time",
    nbf: "Not Before",
    iat: "Issued At",
    jti: "JWT ID"
  };

  function base64UrlDecode(str) {
    var base64 = str.replace(/-/g, "+").replace(/_/g, "/");
    while (base64.length % 4) base64 += "=";
    return decodeURIComponent(atob(base64).split("").map(function(c) {
      return "%" + ("00" + c.charCodeAt(0).toString(16)).slice(-2);
    }).join(""));
  }

  function escapeHtml(str) {
    return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
  }

  function highlightJson(jsonStr) {
    var formatted = JSON.stringify(JSON.parse(jsonStr), null, 2);
    var html = escapeHtml(formatted);
    html = html.replace(/("(?:[^"\\]|\\.)*")\s*:/g, '<span class="jd-key">$1</span>:');
    html = html.replace(/:\s*("(?:[^"\\]|\\.)*")/g, ': <span class="jd-string">$1</span>');
    html = html.replace(/:\s*(-?\d+(?:\.\d+)?(?:[eE][+-]?\d+)?)/g, ': <span class="jd-number">$1</span>');
    html = html.replace(/:\s*(true|false)/g, ': <span class="jd-boolean">$1</span>');
    html = html.replace(/:\s*(null)/g, ': <span class="jd-null">$1</span>');
    return html;
  }

  function formatTimestamp(ts) {
    var d = new Date(ts * 1000);
    return d.toLocaleString() + " (UTC" + (d.getTimezoneOffset() > 0 ? "-" : "+") + Math.abs(d.getTimezoneOffset() / 60) + ")";
  }

  function timeAgo(ts) {
    var now = Math.floor(Date.now() / 1000);
    var diff = ts - now;
    if (diff <= 0) {
      var ago = Math.abs(diff);
      if (ago < 60) return ago + " seconds ago";
      if (ago < 3600) return Math.floor(ago / 60) + " minutes ago";
      if (ago < 86400) return Math.floor(ago / 3600) + " hours ago";
      return Math.floor(ago / 86400) + " days ago";
    } else {
      if (diff < 60) return "in " + diff + " seconds";
      if (diff < 3600) return "in " + Math.floor(diff / 60) + " minutes";
      if (diff < 86400) return "in " + Math.floor(diff / 3600) + " hours";
      return "in " + Math.floor(diff / 86400) + " days";
    }
  }

  function showStatus(type, msg, detail) {
    var cls = "jd-status jd-status-" + type;
    statusEl.innerHTML = '<div class="' + cls + '">' + msg + (detail ? ' <span class="jd-status-detail">' + detail + '</span>' : '') + '</div>';
  }

  function renderClaims(payload) {
    var keys = Object.keys(payload);
    var registeredKeys = keys.filter(function(k) { return CLAIM_NAMES[k]; });
    if (registeredKeys.length === 0) {
      claimsSection.style.display = "none";
      return;
    }
    claimsSection.style.display = "block";
    var html = "";
    registeredKeys.forEach(function(k) {
      var val = payload[k];
      var display = String(val);
      if ((k === "exp" || k === "iat" || k === "nbf") && typeof val === "number") {
        display = formatTimestamp(val) + " (" + timeAgo(val) + ")";
      }
      html += '<div class="jd-claim-key">' + k + '</div><div class="jd-claim-val">' + escapeHtml(CLAIM_NAMES[k]) + ': ' + escapeHtml(display) + '</div>';
    });
    claimsGrid.innerHTML = html;
  }

  window.jdDecode = function() {
    var token = inputEl.value.trim();
    headerEl.innerHTML = "";
    payloadEl.innerHTML = "";
    statusEl.innerHTML = "";
    claimsSection.style.display = "none";
    decoded = { header: null, payload: null };

    if (!token) return;

    var parts = token.split(".");
    if (parts.length < 2 || parts.length > 3) {
      showStatus("error", "Invalid JWT format", "-- expected 3 dot-separated parts, got " + parts.length);
      return;
    }

    try {
      var headerJson = base64UrlDecode(parts[0]);
      decoded.header = headerJson;
      headerEl.innerHTML = highlightJson(headerJson);
    } catch (e) {
      showStatus("error", "Failed to decode header", "-- " + e.message);
      return;
    }

    try {
      var payloadJson = base64UrlDecode(parts[1]);
      decoded.payload = payloadJson;
      payloadEl.innerHTML = highlightJson(payloadJson);

      var payloadObj = JSON.parse(payloadJson);
      renderClaims(payloadObj);

      if (payloadObj.exp) {
        var now = Math.floor(Date.now() / 1000);
        if (payloadObj.exp < now) {
          showStatus("expired", "Token Expired", "-- expired " + timeAgo(payloadObj.exp));
        } else {
          showStatus("valid", "Token Valid", "-- expires " + timeAgo(payloadObj.exp));
        }
      } else {
        showStatus("no-exp", "No Expiration", "-- this token has no exp claim");
      }
    } catch (e) {
      showStatus("error", "Failed to decode payload", "-- " + e.message);
      return;
    }
  };

  window.jdCopySection = function(section, btn) {
    var text = decoded[section];
    if (!text) return;
    var formatted = JSON.stringify(JSON.parse(text), null, 2);
    navigator.clipboard.writeText(formatted).then(function() {
      btn.classList.add("copied");
      btn.textContent = "Copied!";
      setTimeout(function() {
        btn.classList.remove("copied");
        btn.textContent = "Copy";
      }, 2000);
    });
  };

  window.jdLoadSample = function() {
    inputEl.value = SAMPLE;
    jdDecode();
  };

  window.jdClear = function() {
    inputEl.value = "";
    headerEl.innerHTML = "";
    payloadEl.innerHTML = "";
    statusEl.innerHTML = "";
    claimsSection.style.display = "none";
    decoded = { header: null, payload: null };
  };

  inputEl.addEventListener("input", function() {
    if (this.value.trim()) jdDecode();
  });
})();
</script>
