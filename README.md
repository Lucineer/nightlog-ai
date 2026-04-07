# Nightlog

> Live instance: https://nightlog-ai.casey-digennaro.workers.dev

A privacy-first sleep and dream journal agent for the Cocapn Fleet. Your entries stay on your infrastructure.

This is open source MIT software deployed to Cloudflare Workers. It operates on a fork-first ownership model—you control your copy.

---

## Why this exists
Many mainstream sleep and wellness apps monetize personal data. Nightlog was built as an alternative that doesn't.

## How it's different
This is an agent, not a service.
- No central server. You fork and deploy your own instance.
- All data is written to your private Cloudflare KV storage.
- Code is auditable and contains no telemetry.
- No accounts, terms of service, or subscription changes.

---

## How it works
A static web interface pairs with a Cloudflare Worker agent. Data is stored in your KV namespace. AI insights use an API key you provide—requests are never proxied or logged.

No analytics. No error reporting. Data only leaves your instance when you export it.

> **Note:** AI features require your own LLM API key (DeepSeek, OpenAI, Anthropic, or compatible).

---

## Features
*   **Sleep tracking:** Log times, quality, and notes. View calculated sleep debt and patterns.
*   **Dream journal:** Record entries with tags and mood. Full text search runs locally in your browser.
*   **Conversational agent:** Ask questions about your sleep history. Responses reference only your entries.
*   **Data control:** Export all entries as JSON. Delete everything with one click.
*   **No lock-in:** Move your deployment or stop using it at any time.

---

## Quick start
1.  Fork this repository to your GitHub account.
2.  Clone your fork locally.
3.  Install [Wrangler CLI](https://developers.cloudflare.com/workers/wrangler/install-and-update/).
4.  Run `wrangler login` to authenticate with Cloudflare.
5.  Run `npm run setup` to create a KV namespace and set your API key.
6.  Deploy with `npm run deploy`.

Your agent will be live on your `*.workers.dev` subdomain. Host the frontend from `/web` on any static host if desired.

> **Limitation:** Requires comfort with developer tools and a Cloudflare account. AI features depend on your chosen provider's availability and costs.

---

<div>
  Part of the <a href="https://the-fleet.casey-digennaro.workers.dev">Cocapn Fleet</a> · 
  <a href="https://cocapn.ai">Cocapn</a> · 
  Attribution: Superinstance & Lucineer (DiGennaro et al.)
</div>