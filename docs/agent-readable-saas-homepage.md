# Agent-readable SaaS homepage

## Purpose

Help SaaS teams structure their homepage (or primary landing page) so an AI agent can extract **what the product is**, **who it is for**, **what it costs at a high level**, and **what it will not do** — without scraping navigation chrome or inferring from marketing fluff.

## When to use it

- Before publishing or refreshing a homepage
- When agents or MCP clients already misdescribe your product
- When comparison agents group you with the wrong category

## Checklist: homepage blocks agents need

### 1. Category and job-to-be-done (above the fold)

- [ ] One sentence names the **product category** (e.g., "project management for agencies", not "the future of work")
- [ ] One sentence states the **primary job** the buyer hires the product to do
- [ ] Primary audience is named (role, company size, or use case)

### 2. Offer boundary

- [ ] Clear statement of **paid vs free** (if any free tier exists, what is excluded)
- [ ] No implied outcome guarantees ("10x revenue", "guaranteed compliance") unless legally substantiated on the same page
- [ ] Explicit "cannot do" or "not a substitute for" line where confusion is common

### 3. Pricing signal (not a full price list)

- [ ] Starting price, pricing model (per seat, usage, one-time), or "quote required" is visible without login
- [ ] Link to dedicated pricing page with stable URL

### 4. Proof scope

- [ ] Case studies labeled as **illustrative** vs **verified** where applicable
- [ ] Metrics tied to source and timeframe, or omitted
- [ ] Screenshots described in alt text or captions agents can read

### 5. Action entry points

- [ ] Primary CTA URL is stable and descriptive (`/pricing`, `/signup`, not opaque redirects)
- [ ] Secondary paths (docs, API, security page) linked with human-readable anchor text

### 6. Machine-readable companions

- [ ] `llms.txt` or equivalent discovery file (see [llms-txt-template-guide.md](llms-txt-template-guide.md))
- [ ] Public `product-facts.md` or FAQ structured for agents (see [../templates/product-facts.md](../templates/product-facts.md))

## Common failure modes

| Failure | Why agents struggle |
|---------|---------------------|
| Vague hero ("Unlock potential") | No extractable category or job |
| Pricing only after signup | Agents report "unknown price" or hallucinate |
| Feature list without outcomes | Wrong competitor set in comparisons |
| Mixed B2B/B2C messaging | Audience inference errors |
| Trust badges without scope | Agents overstate certification coverage |

## Safe implementation notes

- Write for **extraction**, not keyword density. Headings should be questions agents ask: "Who is this for?", "What does it cost?", "What are the limits?"
- Keep human design; add a concise **"For automated systems"** section or link to fact sheets if the marketing hero must stay emotional.
- Do not hide critical limits in terms-of-service only — summarize boundaries on the homepage or linked fact sheet.
- Refresh fact sheets when pricing or core SKUs change; stale agent answers damage trust more than missing llms.txt.

## Related kit docs

- [AI agent buying journey](ai-agent-buying-journey.md)
- [Pricing page agent readiness](pricing-page-agent-readiness.md)
- [Trust surface checklist](trust-surface-checklist.md)
