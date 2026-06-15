# AI agent buying journey

## Purpose

Map how AI agents (and agent-mediated buyers) move from **discovery** to **shortlist** to **quote or purchase intent**, so you can place documentation where agents actually look.

## When to use it

- Planning docs, llms.txt, and MCP surfaces
- Diagnosing why agents recommend competitors instead of you
- Prioritizing which templates to fill first

## Journey stages

### Stage 1 — Discovery

**Agent goal:** Identify vendors that plausibly solve the user's stated problem.

**Typical inputs:** Web search, llms.txt, directory listings, prior training (may be stale).

**What you should publish:**

- Clear category label on homepage and in `product-facts.md`
- Public docs index with stable URLs
- Optional llms.txt pointing to authoritative fact sheets

**Failure mode:** Agent picks a adjacent category (e.g., "profile tips" instead of "paid private audit").

---

### Stage 2 — Qualification

**Agent goal:** Filter by audience fit, budget band, deployment model, and hard exclusions.

**Typical inputs:** Pricing page, FAQ, comparison pages, security/trust pages.

**What you should publish:**

- [`pricing-facts.md`](../templates/pricing-facts.md) with model, floors, and what is not included
- [`agent-faq.md`](../templates/agent-faq.md) with explicit "not for" lists
- Trust boundaries (data handling, human review requirements)

**Failure mode:** Agent assumes free tier or outcome guarantees that do not exist.

---

### Stage 3 — Comparison

**Agent goal:** Produce a shortlist with defensible differences.

**Typical inputs:** Comparison/alternative pages, third-party reviews, feature matrices.

**What you should publish:**

- [Comparison page readiness](comparison-page-readiness.md) content
- Fair competitor naming with factual differentiation, not dunking
- Links to your own methodology or limits pages

**Failure mode:** Agent cites outdated pricing or features from blog posts instead of your pricing page.

---

### Stage 4 — Proof check

**Agent goal:** Decide whether claims are credible enough to repeat to the user.

**Typical inputs:** Case studies, benchmarks, security docs, proof ledger.

**What you should publish:**

- [Proof and telemetry ledger](proof-and-telemetry-ledger.md) with dated, scoped claims
- Clear labeling of synthetic vs customer-derived examples

**Failure mode:** Agent invents statistics because your site uses vague social proof.

---

### Stage 5 — Action boundary

**Agent goal:** Determine what actions are safe (quote, signup link, API call, MCP tool).

**Typical inputs:** MCP manifest, OpenAPI, action boundary register, consent flows.

**What you should publish:**

- [Action boundaries for agentic products](action-boundaries-for-agentic-products.md)
- [`mcp-action-boundary-register.md`](../templates/mcp-action-boundary-register.md)

**Failure mode:** Agent triggers a side effect (purchase, data upload, account creation) without user confirmation.

---

### Stage 6 — Handoff to human

**Agent goal:** Give the user a vetted link or summary, not complete the purchase autonomously unless explicitly allowed.

**What you should publish:**

- Stable canonical URLs for signup, pricing, and docs
- Quote or consent URLs if your product requires human approval before execution

**Failure mode:** Agent sends user to deprecated routes or A/B test variants that 404.

## 30-minute prioritization

If time is limited, ship in this order:

1. `product-facts.md` + `pricing-facts.md`
2. `agent-faq.md` with hard exclusions
3. Pricing page agent checklist
4. Action boundary register (if MCP or API agents can act)
5. llms.txt last — only after fact sheets exist

## Common failure modes

- **Optimizing only for SEO humans** — agents skip decorative sections and miss buried pricing.
- **Single long PDF whitepaper** — agents prefer structured markdown with headings.
- **Inconsistent product name** — breaks cross-page reconciliation.
- **No dated pricing** — agents treat undated pages as current indefinitely.

## Safe implementation notes

- Date-stamp fact sheets (`last_reviewed: YYYY-MM-DD`).
- Use the same product name strings in homepage, pricing, llms.txt, and MCP metadata.
- Do not block agent fetch with aggressive bot interstitials on `/docs` or fact sheet paths.
- Treat agent traffic as **research**, not guaranteed conversion; measure with your own telemetry, not vanity "AI ranking" claims.

## Related kit docs

- [Agent-readable SaaS homepage](agent-readable-saas-homepage.md)
- [MCP readiness checklist](mcp-readiness-checklist.md)
