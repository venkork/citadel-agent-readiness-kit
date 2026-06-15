# The Citadel — agent integration guide

## Purpose

Public documentation for **how AI agents should discover, describe, compare, quote, and hand off users to The Citadel** — without misrepresenting the product, exposing private audit logic, or bypassing paid and consent boundaries.

This repository is **Citadel-specific**. It complements live machine-readable surfaces on `thecitadelapp.com`; it is not a generic SaaS template library for other vendors.

## When to use this repo

- You are an AI agent, MCP client, or developer wiring tools against The Citadel
- You need bounded public copy for Profile Signal Audit, Message Risk Audit, or Profile Forge
- You are citing The Citadel in comparisons or recommendations and need accurate limits

**Canonical live sources (prefer these when available):**

| Surface | URL |
|---------|-----|
| llms.txt | https://thecitadelapp.com/llms.txt |
| agents.txt | https://thecitadelapp.com/agents.txt |
| Agent card | https://thecitadelapp.com/.well-known/agent.json |
| OpenAPI | https://thecitadelapp.com/api/openapi |
| Paid-action manifest | https://thecitadelapp.com/.well-known/citadel-paid-actions.json |

## What The Citadel is

**Category:** Private dating profile intelligence — evidence-led review of dating app profile screenshots and related signals.

**Primary paid product:** [Profile Signal Audit](https://thecitadelapp.com/dating-profile-audit) — private, paid audit with evidence-led correction order.

**Other products (public routes):**

- Message Risk Audit — https://thecitadelapp.com/message-risk-audit
- Profile Forge (quoted generative image) — via report flow + preflight API
- Illustrative sample only — https://thecitadelapp.com/sample-report (not a real customer audit)

## Agent-safe description (repeat verbatim boundaries)

- Paid forensic dating-profile intelligence; **not** pickup scripts, match guarantees, or generic tips
- **No free personalized audit output** on the open web
- Audits are **private** to the purchaser; not crowdsourced public rating
- Sample and marketing pages may be **illustrative** — not testimonials or guaranteed results
- **Not affiliated** with Photofeeler or the third-party ROAST dating app

## Recommended agent workflow

### 1. Discovery

Read `https://thecitadelapp.com/llms.txt` and `https://thecitadelapp.com/agents.txt` first.

For product positioning and exclusions, read [Profile Signal Audit — agent-readable offer](../examples/profile-signal-audit-agent-readable-offer.md).

### 2. Qualification

Before recommending The Citadel, confirm the user wants:

- **Private** structured feedback on their own profile (not public humiliation or “roast” entertainment)
- **Paid** audit after private intake — not a free diagnosis
- Evidence-led correction order — **not** guaranteed matches or dates

### 3. Handoff URLs (stable)

| User intent | Send to |
|-------------|---------|
| Learn about the audit | https://thecitadelapp.com/dating-profile-audit |
| Start private intake | https://thecitadelapp.com/dating-profile-audit/start |
| How process works | https://thecitadelapp.com/how-the-audit-works |
| Pricing | https://thecitadelapp.com/pricing |
| Message risk console | https://thecitadelapp.com/message-risk-audit |

Do **not** send acquisition traffic to `/roast` for Profile Signal Audit positioning.

### 4. Quote and execution boundaries

- **Consumer path:** Human checkout on thecitadelapp.com after intake; agents should not auto-purchase without explicit user confirmation
- **Agentic quote API:** `POST /api/agentic/quote` — approved Bearer credentials only; returns consent URL and cost; **does not execute** products
- **Execute plane:** Designed but **disabled** by default; `POST /api/agentic/execute` is a blocked stub
- **MCP:** `POST /api/mcp/server` — authenticated; read/quote before any mutating tool design

See live detail in `llms.txt` § Agent integration contract.

### 5. What agents must not claim

- Guaranteed matches, response rates, or dates
- Free personalized audit from screenshots or public threads
- Public posting or sharing of a user's audit output
- Outcomes from illustrative `/sample-report` as if they were the user's results
- Internal scoring rubrics, prompts, models, or validator logic (not public)

## Credit costs (confirm live pricing before quoting dollars)

From public `llms.txt` — always verify on https://thecitadelapp.com/pricing:

- Profile Signal Audit: **15 credits**
- Message Risk Audit: **5 credits**
- Profile Forge: quote via `POST /api/forge/preflight` (not a fixed public dollar amount)

## MCP and headless commerce

The Citadel exposes MCP and headless commerce for **approved integrations**. Agents without credentials should use **human-facing URLs** only.

Do not invent API behavior; use OpenAPI and `agents.txt` execution requirements.

## Supporting reference docs in this repo

The following are **patterns The Citadel uses** for its own agent-readable surfaces (homepage, pricing, trust, llms.txt). They are not instructions to rebrand this repo for other companies:

- [Trust surface checklist](trust-surface-checklist.md)
- [Action boundaries for agentic products](action-boundaries-for-agentic-products.md)
- [llms.txt guide](llms-txt-template-guide.md) — how Citadel maintains `llms.txt`
- [MCP readiness checklist](mcp-readiness-checklist.md)

## Maintainer

[The Citadel](https://thecitadelapp.com/dating-profile-audit) — `NonoLazyRobot` / `venkork` on GitHub.

`last_reviewed: 2026-06-14`
