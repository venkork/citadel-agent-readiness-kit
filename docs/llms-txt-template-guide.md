# llms.txt template guide

## Purpose

Explain how to publish an `llms.txt` file — a proposed convention for pointing LLMs and crawlers to **authoritative, agent-readable documentation** on your domain.

## When to use it

- After you have stable fact sheets (`product-facts.md`, `pricing-facts.md`, FAQ)
- When agents repeatedly cite wrong pages from your marketing site
- As a complement to (not replacement for) good on-page structure

## What llms.txt is — and is not

**Is:**

- A small, plain-text index at `https://yourdomain.com/llms.txt`
- A curated list of URLs you want automated systems to prefer
- A way to reduce ambiguity about canonical product docs

**Is not:**

- A guaranteed SEO or AI ranking mechanism
- A secret lever to override search engine policies
- A place for keyword stuffing or hidden promotional links
- A substitute for clear homepage and pricing copy

Treat llms.txt as **documentation hygiene**, similar to `robots.txt` or sitemap discipline — useful, optional, and subordinate to actual content quality.

## Recommended structure

See the copyable template: [`../templates/llms.txt`](../templates/llms.txt)

Typical sections:

1. **Title and one-line description** of the product
2. **Primary fact sheets** (product, pricing, FAQ)
3. **Trust and security** (public security page, privacy summary)
4. **Optional** — API docs, MCP server README URL, changelog
5. **Contact or support** for factual corrections

## Checklist before publishing

- [ ] Every linked URL returns 200 and matches current positioning
- [ ] Fact sheets dated with `last_reviewed`
- [ ] No credentials, internal admin URLs, or staging hosts
- [ ] Same product name spelling as homepage and pricing
- [ ] File stays under ~10 KB; link out instead of inlining novels
- [ ] robots.txt does not contradict intentional public docs paths

## Common failure modes

| Failure | Consequence |
|---------|-------------|
| Pointing to blog hype posts | Agents repeat unbounded marketing claims |
| Stale pricing links | Wrong quotes in agent answers |
| llms.txt only, no fact sheets | Index with no substance |
| Blocking all bots globally | llms.txt never fetched |

## Safe implementation notes

- Publish llms.txt **after** fact sheets, not before.
- Update llms.txt in the same release train as pricing changes.
- Do not claim compliance or certifications in llms.txt unless the linked page substantiates scope.
- Monitor 404s on listed URLs; broken llms.txt erodes agent trust faster than omitting the file.

## Related kit docs

- [Agent-readable SaaS homepage](agent-readable-saas-homepage.md)
- [Proof and telemetry ledger](proof-and-telemetry-ledger.md)
