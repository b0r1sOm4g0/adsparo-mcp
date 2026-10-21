# 🚀 Adsparo MCP — Competitor Ad Intelligence & Creative Spy

[![MCP Standard](https://img.shields.io/badge/MCP-Protocol-blue.svg)](https://modelcontextprotocol.io)
[![Runtime](https://img.shields.io/badge/Node.js-22+-green.svg)](https://nodejs.org/)
[![Storefront](https://img.shields.io/badge/Marketplace-Wise%20Tools-purple.svg)](https://mcpmarket.com/sellers/wisetools)
[![License](https://img.shields.io/badge/License-Commercial-orange.svg)](#license)

> **Supercharge Claude, Cursor, and AI agents with autonomous ad intelligence.** Search, scrape, and deconstruct competitor ad campaigns, winning hooks, angles, and landing page funnels directly from Adsparo.

---

### 🛒 Official Release & Agent Skill

The complete **Adsparo MCP Server** and the accompanying **Ad Intelligence Competitor Spy Skill** are distributed exclusively via Wise Tools:

👉 **[Get the Full Toolkit on MCP Market](https://mcpmarket.com/sellers/wisetools)**

---

## ⚡ Key Capabilities

* **Targeted Ad Search:** Query competitor campaigns by keywords, advertiser page titles, or destination landing page links.
* **Granular Market Filters:** Filter by country (`BR`, `US`, `GB`, etc.), language, media format (Video / Image), active date ranges, and min/max total ad variations.
* **Hook & Angle Extraction:** Automatically isolate headlines, opening lines, pain points, and call-to-actions (CTAs) for your creative team.
* **Funnel Forensics:** Trace advertiser destination URLs, tracking parameters (Shopify, ClickBank, Hotmart), and advertorial/VSL structures.
* **Safe Local Session Management:** Operates through a dedicated, isolated Chromium instance via Playwright. Cookies and sessions stay strictly local on your machine — credentials are never transmitted to LLM providers.
* **Anti-Injection Guardrails:** Scraped ad copy and links are treated as untrusted data payloads to prevent prompt injections during synthesis.

---

## 🏗️ Architecture

```
┌─────────────────────────────────┐
│     AI Agent (Claude / Cursor)  │
└────────────────┬────────────────┘
                 │ MCP JSON-RPC (stdio)
┌────────────────▼────────────────┐
│       Adsparo MCP Server        │
└────────────────┬────────────────┘
                 │ Playwright Automation
┌────────────────▼────────────────┐
│      Dedicated Chromium         │
│  (Isolated Profile & Cookies)   │
└────────────────┬────────────────┘
                 │ Authenticated Session
┌────────────────▼────────────────┐
│       Adsparo Platform          │
└─────────────────────────────────┘
```

---

## 🛠️ Tool Specifications

The MCP server exposes the following specialized tools:

| Tool | Purpose |
| :--- | :--- |
| `adsparo_open` | Launches dedicated browser instance and manages authenticated session. |
| `adsparo_status` | Reports browser state, authentication status, and last active query. |
| `adsparo_filters` | Discovers real filter options (categories, platforms, technologies). |
| `adsparo_search` | Executes targeted search with complete filtering and sorting. |
| `adsparo_next` | Triggers pagination ("Load More") to harvest subsequent ad batches. |
| `adsparo_collect` | Reads and groups loaded ads by advertiser domain and longevity. |
| `adsparo_details` | Inspects full ad card details, destination URLs, and creative assets. |
| `adsparo_screenshot` | Captures authenticated viewport evidence locally. |
| `adsparo_pause` / `adsparo_resume` | Facilitates manual intervention (CAPTCHAs, filters) without losing session. |
| `adsparo_window` | Minimizes or restores browser window during agent execution. |
| `adsparo_close` | Safely terminates automation while preserving persistent login. |

---

## 🤖 Pairing with the "Ad Intelligence" Skill

When paired with the **Wise Tools Ad Intelligence Skill** on MCP Market, your agent doesn't just pull data — it acts as a senior media buyer:
1. Identifies the prevailing hook archetype (Negative Urgency, Curiosity Gap, Counter-Intuitive, Social Proof).
2. Generates ready-to-use Swipe Files and copy adaptations for your product.
3. Rates competitor campaigns by scalability (ads running 30+ days = scaled winner).

---

## 🔒 Security & Privacy

* **Credentials:** Username and password can be loaded via local `.env` only to prefill login fields. The server never outputs passwords or auth cookies to the AI model.
* **Session Storage:** Saved with strict local filesystem permissions (`0600`) inside `~/.local/share/adsparo-mcp/`.
* **Rate Limiting:** Enforces polite request intervals to prevent account flags or rate limits.

---

## ⚖️ Legal Disclaimer

This repository and the Adsparo MCP server are unofficial tools developed independently by Wise Tools. This software is not affiliated, endorsed, authorized, or certified by Adsparo. Users are solely responsible for adhering to Adsparo's Terms of Service and respecting platform usage guidelines.

---

## 📦 Distribution & Support

Maintained with ❤️ by **Wise Tools**.  
For commercial licenses, managed bundles, and skill toolkits, visit [Wise Tools on MCP Market](https://mcpmarket.com/sellers/wisetools).
