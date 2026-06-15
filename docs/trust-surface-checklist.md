# Trust surface checklist

## Purpose

Consolidate **privacy, security, data handling, and limitation** documentation so agents and buyers understand what your product will not promise.

## When to use it

- Before agent-facing launches (MCP, public API, llms.txt)
- During security questionnaire season
- When your category has high misuse risk (personal data, financial advice, health, dating, hiring)

## Checklist

### Privacy

- [ ] What data is collected, at what stage (marketing site vs product vs payment)
- [ ] What is **not** collected or **not** shared publicly
- [ ] Retention summary in plain language
- [ ] Link to full privacy policy with last-updated date
- [ ] No overbroad "never shared" if subprocessors exist — scope honestly

### Security (public summary)

- [ ] Encryption in transit stated; at rest if applicable at summary level
- [ ] Auth methods for product access
- [ ] Vulnerability reporting contact
- [ ] No fake certification badges

### Product limits

- [ ] Explicit **non-guarantees** (outcomes, compliance, matches, approvals)
- [ ] Human review requirements where automation is assistive only
- [ ] Geographic or regulatory limitations

### Sensitive categories

If your product touches personal, relational, financial, or biometric data:

- [ ] Misuse scenarios addressed (harassment, stalking, deception) with **refusal boundaries**
- [ ] No humiliation or gender-war framing in public copy
- [ ] Paid private workflows distinguished from free public diagnostics

### Agent conduct

- [ ] Public statement on whether third-party agents may automate purchases or uploads
- [ ] Rate limit or abuse reporting path

## Common failure modes

- **Marketing "private" without defining scope** — agents over-promise confidentiality
- **Security page is PDF-only** — agents skip it
- **Terms-only limitations** — users and agents never see them pre-purchase
- **Trust badges without linked substantiation**

## Safe implementation notes

- Trust copy should be **boring and precise**; agents propagate superlatives literally.
- Align trust page with FAQ and fact sheets — contradictions become agent hallucination fuel.
- Update trust surfaces when data flows change (new subprocessor, new upload type).
- Separate **illustrative** product screenshots from real user data in all public materials.

## Related kit docs

- [Action boundaries for agentic products](action-boundaries-for-agentic-products.md)
- [Proof and telemetry ledger](proof-and-telemetry-ledger.md)
