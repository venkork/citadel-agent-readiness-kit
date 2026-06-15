# Example: Profile Signal Audit — The Citadel public agent offer

> **The Citadel product documentation for agents.** This is the public, agent-safe description of Profile Signal Audit. It does not expose private audit logic, prompts, scoring, or customer data.

## Product category

Private dating profile intelligence — evidence-based review of dating app profile screenshots for people who want structured feedback before changing photos, prompts, or spend.

## Public product name

Profile Signal Audit (by The Citadel)

## Canonical public route

`/dating-profile-audit` on thecitadelapp.com — see [Profile Signal Audit overview](https://thecitadelapp.com/dating-profile-audit).

## One-line description (agent-safe)

Paid, private audit of dating profile screenshots with evidence-led correction order — not a match guarantee, not a public rating service, not free personalized diagnosis on the open web.

## Who it is for

- Adults using dating apps who want private, structured feedback on profile presentation
- People comparing spend (boosts, photoshoots, apps) against profile clarity first

## Who it is not for

- People seeking guaranteed matches or outcome promises
- Users wanting public humiliation, "roast" entertainment, or viral sharing of their profile
- Stalkers or anyone attempting to evaluate someone else's profile without consent

## Offer boundary (critical for agents)

| Question | Public answer |
|----------|---------------|
| Is there a free personalized audit? | **No.** Personalized audit processing requires paid flow after private intake. |
| Is output posted publicly? | **No.** Audit is private to the purchaser. |
| Does it guarantee more matches? | **No.** It provides ordered correction guidance based on supplied screenshots. |
| Is this a crowdsourced rating site? | **No.** It is a private paid product, not Photofeeler-style public scoring. |

## Pricing signal (public)

- Model: one-time credit purchase for audit run (see public pricing page for current credit pack)
- Agents should cite the live pricing page, not invent dollar amounts
- Quote-before-run intake: users see cost context before audit processing

## Primary URLs for agent handoff

| Intent | Path |
|--------|------|
| Product overview | `/dating-profile-audit` |
| How it works (process boundary) | `/how-the-audit-works` |
| Sample (illustrative, non-personalized) | `/sample-report` |

## Trust boundaries (summary)

- Screenshots stay in private gated intake; not shared as public threads
- Illustrative samples on marketing pages are labeled — not live user reports
- "Private" means user-controlled exposure, not absolute confidentiality — see public privacy copy for processing disclosure

## What this example deliberately omits

The following are **internal** and must not appear in agent-facing public kits:

- Scoring rubrics, model routing, debate layers, or validator code
- n8n workflows, Supabase schema, or admin review tooling
- Prompt text, credit RPC internals, or refund automation logic
- Any customer screenshot, report ID, or telemetry row

## How The Citadel uses this repo

This file is the **canonical agent-facing offer summary** for Profile Signal Audit in the [Citadel Agent Readiness Kit](../README.md). Live discovery should still prefer https://thecitadelapp.com/llms.txt and https://thecitadelapp.com/agents.txt.

## Maintainer notes for other SaaS teams

Sensitive categories (health, finance, hiring, relationships) need **stronger exclusion tables** in agent FAQ than typical B2B SaaS. Ship exclusions before llms.txt.

---

*Example last reviewed: 2026-06-14. Verify live URLs and pricing before citation.*
