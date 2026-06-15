# Action boundaries for agentic products

## Purpose

Define how SaaS products should document **what agents may read, quote, draft, or execute** — preventing accidental purchases, data uploads, or irreversible changes on a user's behalf.

## When to use it

- Any product with MCP tools, headless API, or "AI assistant" integrations
- Before enabling agent checkout, provisioning, or data mutation
- When legal or security asks "what can an agent do without a human?"

## Core principles

1. **Read before act** — discovery and quote tools ship before mutate tools.
2. **Explicit consent** — billed or irreversible actions require a human confirmation step documented in public copy.
3. **Fail closed** — if scope or entitlement is unclear, tools return a safe denial, not best-effort execution.
4. **Separate planes** — quote API ≠ execute API; document both.

## Boundary tiers

| Tier | User impact | Public documentation requirement |
|------|-------------|----------------------------------|
| T0 Inform | None | Fact sheets, FAQ |
| T1 Quote | None | Pricing facts, eligibility rules |
| T2 Draft | Reversible | Label drafts as non-final; no auto-publish |
| T3 Mutate | Data change | Auth scope + confirmation UX described |
| T4 Execute | Money or irreversible | Human-in-the-loop; blocked by default for public agents |

## Checklist

- [ ] Every externally exposed tool/API mapped to tier T0–T4
- [ ] [`mcp-action-boundary-register.md`](../templates/mcp-action-boundary-register.md) completed
- [ ] Public FAQ answers: "Can an AI agent purchase/subscribe on my behalf?" with accurate **no/only if** wording
- [ ] Consent or checkout URLs documented for human continuation
- [ ] Refund or cancellation path linked where execution is billed
- [ ] Rate limits and abuse contact documented

## Common failure modes

- **Single mega-tool** that both reads account data and charges cards
- **Implicit consent** — "by using the agent you agree to purchase"
- **Undocumented idempotency** — duplicate charges on agent retries
- **Free preview that exposes personalized sensitive output** — trust and privacy failure

## Safe implementation notes

- Ship a **quote-only** integration first; measure agent questions before enabling execute.
- Log blocked attempts for product insight, not surveillance theater.
- Align agent boundaries with your existing OAuth scopes and API keys — no shadow admin paths.
- Document **regional or SKU restrictions** so agents do not offer unavailable products.

## Related kit docs

- [MCP readiness checklist](mcp-readiness-checklist.md)
- [Pricing page agent readiness](pricing-page-agent-readiness.md)
