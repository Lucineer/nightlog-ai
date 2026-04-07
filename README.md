# Nightlog

A privacy-focused sleep and dream journal that runs on your infrastructure. Built as an agent for the Cocapn Fleet, it helps you track sleep patterns and record dreams, keeping all your data under your control.

It runs on Cloudflare Workers, is open source under the MIT license, and follows a fork-first model with no vendor lock-in.

## Why Use This?

Most sleep and wellness apps require you to surrender your personal data to a third-party service. This project offers an alternative. When you fork and deploy this repository, your data remains in your own Cloudflare KV storage. You can export it at any time, and the agent's behavior only changes when you decide to update the code. There is no central service, account, or company behind it.

## How It Works

This is a statically-hosted web application paired with a Cloudflare Worker agent. The agent manages all data operations and provides conversational insights via an AI API you configure.

**Note:** You must provide your own API key for the AI features (e.g., from DeepSeek, OpenAI, or Anthropic). No analytics or telemetry are included.

## Features

*   **Sleep Tracking:** Log sleep times, quality, and notes. View calculated sleep debt and consistency scores.
*   **Dream Journal:** Record dreams with tags and mood. All entries are fully searchable.
*   **Data Privacy:** All data is stored in your own Cloudflare KV namespace and is never sent elsewhere.
*   **Conversational Interface:** Ask questions about your sleep patterns in a chat interface. The agent can reference your historical data to provide context-aware insights.
*   **Self-Hosted:** You control the deployment and all associated data.

## Quick Start

1.  **Fork this repository** to your own GitHub account.
2.  Clone your fork locally.
3.  Install the [Wrangler CLI](https://developers.cloudflare.com/workers/wrangler/install-and-update/).
4.  Run `wrangler login` to authenticate with Cloudflare.
5.  In the project directory, run `npm run setup`. This script will guide you through creating the required KV namespace and setting your AI API key as a secret.
6.  Deploy with `npm run deploy`.

Your agent will be live on your `*.workers.dev` subdomain. You can then deploy the frontend to any static host (like GitHub Pages) by serving the contents of the `/web` directory.

**Limitation:** Setting up and maintaining this project requires basic comfort with developer tools and the Cloudflare dashboard.

## Development

*   Agent logic is in `/src`.
*   The web interface is in `/web`.
*   Use `npm run dev` to run a local preview of the agent.

## Learn More

This is an agent built for the Cocapn Fleet.
*   [The Fleet](https://the-fleet.casey-digennaro.workers.dev)
*   [Cocapn](https://cocapn.ai)

---
Attribution: Superinstance & Lucineer (DiGennaro et al.).