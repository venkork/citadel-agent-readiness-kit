# Pricing page agent readiness

## Purpose

Ensure pricing pages expose **structured, honest price facts** so agents quote accurately and do not invent tiers, discounts, or billing models.

## When to use it

- Launching or redesigning `/pricing`
- After agents misquoted your product in user conversations
- Before connecting billing APIs to MCP or agent checkout experiments

## Checklist

### Price facts

- [ ] Each SKU/plan has a **name**, **price**, **currency**, **billing period**
- [ ] Usage-based components define unit and typical floor ("from $X" only if true minimum)
- [ ] One-time vs subscription clearly separated
- [ ] Taxes, fees, and regional variance addressed or deferred to checkout with explicit note
- [ ] Enterprise/custom pricing says **quote required**, not hidden zero

### Limits and entitlements

- [ ] Seat limits, usage caps, and feature gates listed per plan
- [ ] Overage behavior stated (hard stop vs bill vs downgrade)
- [ ] Free trial duration and auto-convert rules explicit

### Agent-specific

- [ ] Mirror pricing in [`pricing-facts.md`](../templates/pricing-facts.md) with `last_reviewed` date
- [ ] FAQ entry: "Can an AI agent purchase for me?" aligned with [action boundaries](action-boundaries-for-agentic-products.md)
- [ ] Stable anchor IDs or headings agents can cite (`## Pro plan`)

### Trust

- [ ] Refund policy linked
- [ ] No fake urgency counters or fabricated "teams joined today" stats

## Common failure modes

| Failure | Agent behavior |
|---------|----------------|
| "Contact sales" only | Omits you from budget-filtered shortlists |
| JavaScript-only price render | Misses price entirely |
| Conflicting prices across pages | Picks arbitrary number |
| Credits + subscription mix unexplained | Wrong total cost estimate |

## Safe implementation notes

- Server-render core price numbers; do not hide sole pricing behind client-only widgets.
- When using credits or tokens, publish **conversion to currency** on the pricing page or linked facts doc.
- Date-stamp breaking pricing changes in changelog or facts file.
- If agents should not complete checkout, say so plainly — link to human checkout URL.

## Related kit docs

- [Proof and telemetry ledger](proof-and-telemetry-ledger.md)
- [Agent-readable SaaS homepage](agent-readable-saas-homepage.md)
