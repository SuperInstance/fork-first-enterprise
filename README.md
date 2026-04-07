# Fork-First Enterprise
You run AI agents on your Cloudflare account. Not ours. Every API key, log entry, and byte of data stays inside your infrastructure.

## Why This Exists
Teams can spend months auditing vendors just to run a simple internal AI agent. You shouldn't need legal signoff to test code. This model puts you in control from the start.

## Quick Start
1.  **Fork** this repository to your GitHub account.
2.  From your fork, **deploy** using `npx wrangler deploy` while logged into your Cloudflare account.
3.  **Configure** your external API keys and settings via environment variables in the Cloudflare dashboard.

Your independent instance is live, typically in under ten minutes. There are zero ongoing fees.

## What This Provides
*   **No Data Transit**: We never see requests, logs, or keys. Your Cloudflare Worker communicates directly with your configured services.
*   **Forked Ownership**: You own the deployed copy. The upstream repository could disappear without affecting your live instance.
*   **Zero Runtime Dependencies**: The Worker uses no external npm packages, eliminating a common source of breaking updates.

## Architecture
A single Cloudflare Worker functions as an autonomous agent runtime. It uses your Cloudflare KV namespace for agent memory and state, and your R2 bucket for file storage. You control the entire stack.

## Features
- **Full Control**: You own all code and data. Merge updates from this upstream repo only if you choose to.
- **Your Keys**: Configure OpenAI, Anthropic, or other API keys solely in your Cloudflare environment.
- **Configurable Access**: Set user roles and permissions within the code of your fork.
- **Action Logging**: Agent actions are logged to your KV store. (Default configuration retains the last 10,000 entries).
- **Custom Branding**: Serve from your own domain and adjust the interface to match your organization.

## One Clear Limitation
The provided setup is designed for low-to-moderate traffic. On Cloudflare's free tier, your instance is limited to 100,000 requests per day. For higher volumes, you must upgrade your Cloudflare Workers plan.

## The Fork-First Model
You maintain the primary deployment of your forked instance. You can modify it freely for your team's needs. We may publish improvements to this upstream repository, which you can review and merge at your discretion.

Open source, MIT licensed.

<div style="text-align:center;padding:16px;color:#64748b;font-size:.8rem"><a href="https://the-fleet.casey-digennaro.workers.dev" style="color:#64748b">The Fleet</a> &middot; <a href="https://cocapn.ai" style="color:#64748b">Cocapn</a></div>