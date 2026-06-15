# MCP readiness checklist

## Purpose

Help teams expose [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) servers or tool integrations **safely** — with clear scopes, confirmation rules, and documentation agents can cite.

## When to use it

- Designing your first MCP server for a SaaS product
- Auditing an existing MCP integration before public listing
- Responding to enterprise security review for agent access

## Important framing

MCP is a **protocol for connecting agents to tools and data**. It is not a substitute for product design, authentication policy, or billing. Listing an MCP server does not mean agents should execute paid or irreversible actions without explicit user consent.

## Checklist

### Documentation

- [ ] Public README for the MCP server: purpose, install, required env vars (names only, no secrets)
- [ ] Tool catalog with **human-readable descriptions** per tool
- [ ] Link to [`mcp-action-boundary-register.md`](../templates/mcp-action-boundary-register.md) filled for each tool
- [ ] Versioning policy when tool schemas change

### Authentication and tenancy

- [ ] Document which auth modes are supported (OAuth, API key, none for read-only public data)
- [ ] State whether tools act on **user-delegated** credentials vs service account
- [ ] Multi-tenant isolation described at a high level (no internal schema dumps)

### Action classification

For each tool, classify:

| Class | Description | Default agent policy |
|-------|-------------|----------------------|
| Read | Fetch public or user-authorized data | May call with user context |
| Quote | Return price or eligibility estimate | May call; no side effects |
| Draft | Create revocable draft content | User review required before publish |
| Mutate | Change production data or spend money | **Blocked** without explicit confirmation |
| Execute | Irreversible or billed operation | **Blocked** without human-in-the-loop |

- [ ] Every tool assigned a class
- [ ] Mutate/Execute tools require documented confirmation UX

### Rate limits and abuse

- [ ] Documented rate limits (even if "contact sales for higher limits")
- [ ] No tools that exfiltrate secrets from the host environment
- [ ] Logging policy stated (what is logged, retention, PII handling) at summary level

### Discovery metadata

- [ ] Server name and description match `product-facts.md` naming
- [ ] Canonical install/docs URL
- [ ] Optional registration in public MCP directories **only after** boundary review passes

### Testing

- [ ] Negative tests: agent prompts that should **not** trigger purchase/upload/delete
- [ ] Idempotency notes for tools that create resources
- [ ] Rollback or support path documented for failed mutations

## Common failure modes

- **"Helpful" tools that checkout or subscribe** — highest-risk pattern for trust and chargebacks.
- **Undocumented side effects** — e.g., tool sends email or writes CRM without description.
- **Schema drift** — agents cache old tool definitions; version your server.
- **Over-broad read tools** — exposing admin-only data through a general MCP server.

## Safe implementation notes

- Prefer **quote-only** and **read-only** tools for early public MCP pilots.
- Separate **discovery** (what the product is) from **execution** (what changes state).
- Mirror enterprise API auth patterns; do not invent a weaker MCP auth path.
- If unsure, ship documentation and a dry-run tool before any mutating tool.

## Related kit docs

- [Action boundaries for agentic products](action-boundaries-for-agentic-products.md)
- [Trust surface checklist](trust-surface-checklist.md)
