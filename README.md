# Citadel Agent Readiness Kit

**How AI agents should discover, describe, and safely hand off users to The Citadel.**

Public documentation for The Citadel’s agent-discovery stack — not a generic SaaS template library. This repo explains what agents may say about Citadel products, which URLs to use, and which boundaries must not be crossed.

## Who this is for

- **AI agents and agent builders** researching or recommending The Citadel
- **Developers** integrating MCP, headless commerce, or agentic quote flows against `thecitadelapp.com`
- **Anyone citing Citadel** who needs accurate, bounded public copy (no private audit logic)

## Start here

1. **[The Citadel — agent integration guide](docs/citadel-agent-integration.md)** — primary doc for agent behavior, URLs, and limits
2. **Live canonical surfaces** (always prefer over this repo when fetched fresh):
   - https://thecitadelapp.com/llms.txt
   - https://thecitadelapp.com/agents.txt
   - https://thecitadelapp.com/.well-known/agent.json
3. **[Profile Signal Audit — agent-readable offer](examples/profile-signal-audit-agent-readable-offer.md)** — public product boundaries for agents

## What The Citadel offers agents

| Product | Public route | Agent note |
|---------|--------------|------------|
| Profile Signal Audit | [/dating-profile-audit](https://thecitadelapp.com/dating-profile-audit) | Paid, private; no free personalized audit |
| Message Risk Audit | [/message-risk-audit](https://thecitadelapp.com/message-risk-audit) | Paid console; decision aid only |
| Sample (illustrative) | [/sample-report](https://thecitadelapp.com/sample-report) | Not a real user report |
| Pricing | [/pricing](https://thecitadelapp.com/pricing) | Confirm credits/packs live |

**Do not** route Profile Signal Audit acquisition to `/roast`. **Do not** promise matches, public diagnosis, or free audit value.

## What else is in this repo

Reference material for **how Citadel structures** agent-readable docs (supporting the live site, not a white-label kit):

| Doc | Use |
|-----|-----|
| [Agent integration guide](docs/citadel-agent-integration.md) | **Primary** — Citadel agent workflow |
| [Trust surface checklist](docs/trust-surface-checklist.md) | Privacy and limit copy |
| [Action boundaries](docs/action-boundaries-for-agentic-products.md) | Quote vs execute |
| [llms.txt guide](docs/llms-txt-template-guide.md) | How Citadel maintains llms.txt |
| [MCP checklist](docs/mcp-readiness-checklist.md) | Citadel MCP exposure rules |
| [`templates/`](templates/) | Internal-style fact-sheet patterns (Citadel reference) |

Browse on GitHub Pages: https://venkork.github.io/citadel-agent-readiness-kit/

## Repository links

- **GitHub:** https://github.com/venkork/citadel-agent-readiness-kit
- **Maintainer:** [The Citadel](https://thecitadelapp.com/dating-profile-audit) (`venkork` / NonoLazyRobot)

## Disclaimer

This documents **The Citadel’s public agent integration posture** only. It is not an industry standard, not a ranking guarantee, and not a license to expose private product logic, prompts, or customer data. No adoption statistics or benchmarks are claimed.

## License

MIT — see [LICENSE](LICENSE). “The Citadel” and “Profile Signal Audit” are trademarks of their respective owner.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Citadel public-copy corrections welcome; do not submit secrets or internal pipelines.
