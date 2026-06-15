# Proof and telemetry ledger

## Purpose

Give SaaS teams a **disciplined format** for claims agents and buyers can repeat — with scope, date, and source — without inventing benchmarks or testimonials.

## When to use it

- Before publishing case studies, ROI pages, or "results" sections
- When rebuilding trust after agents hallucinated stats about your product
- When coordinating marketing, product, and finance on what can be said publicly

## Concept

A **proof ledger** is an internal-or-public register of **allowed public claims**. Each row is something you are willing to stand behind on a specific page. Anything not in the ledger should not appear in agent-facing fact sheets.

Use the template: [`../templates/proof-ledger.md`](../templates/proof-ledger.md)

## Checklist: ledger row quality

For each claim:

- [ ] **Claim text** — exact sentence suitable for public reuse
- [ ] **Scope** — population, geography, product SKU, time window
- [ ] **Source** — customer permission, internal telemetry job, third-party study (with link)
- [ ] **Evidence class** — `verified`, `illustrative`, `directional`, `withheld`
- [ ] **Last verified date**
- [ ] **Allowed surfaces** — homepage, pricing, comparison, docs, MCP description
- [ ] **Forbidden paraphrases** — what agents must not infer (e.g., no "guaranteed" from "median uplift")

## Telemetry vs proof

| Type | Example | Agent guidance |
|------|---------|----------------|
| Operational telemetry | "Median API latency 120ms (30d, p50)" | Cite with metric definition |
| Product usage | "Teams create 3 projects in first week (median)" | Not an outcome guarantee |
| Customer outcome | "Customer X reduced ticket volume 18% in Q1" | Needs permission + scope |
| Illustrative demo | "Sample dashboard shows example data" | Must label non-real |

Do not move telemetry into **outcome guarantees** without explicit ledger approval.

## Common failure modes

- **Vanity metrics without denominator** — "10,000 users" with no active definition
- **Cherry-picked windows** — best week presented as typical
- **Synthetic examples presented as live results**
- **Ledger exists but marketing ignores it** — agents scrape old blog posts instead

## Safe implementation notes

- Prefer **fewer, scoped claims** over many vague ones.
- Separate **illustrative** screenshots from **customer** screenshots in captions and alt text.
- If you lack permission for named logos, use anonymized industry labels.
- Refresh ledger on pricing, SKU, or major feature launches.
- Public ledger excerpt is optional; even an internal ledger improves agent doc consistency.

## Related kit docs

- [Trust surface checklist](trust-surface-checklist.md)
- [Comparison page readiness](comparison-page-readiness.md)
