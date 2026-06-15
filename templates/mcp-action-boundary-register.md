# MCP action boundary register — {{PRODUCT_NAME}}

`last_reviewed: {{YYYY-MM-DD}}`  
`mcp_server_version: {{semver}}`

Document every externally exposed MCP tool (or agent-callable API) before public listing.

## Global policy

- Default tier for new tools: **T0 Read** or **T1 Quote** until reviewed
- **T4 Execute** tools: disabled for anonymous agents; human confirmation required
- Logging: {{summary — no secrets in logs}}

## Tool register

| Tool name | Tier | Description | Side effects | Auth required | Agent may call without human? | Notes |
|-----------|------|-------------|--------------|---------------|-------------------------------|-------|
| {{tool_id}} | T0/T1/T2/T3/T4 | {{human readable}} | {{none / draft / charge / delete}} | {{OAuth/API key/none}} | **Yes/No** | {{idempotency, rate limit}} |
| | | | | | | |

### Tier key

- **T0 Read** — fetch public or authorized read-only data
- **T1 Quote** — price/eligibility estimate, no mutation
- **T2 Draft** — creates revocable draft
- **T3 Mutate** — changes user data
- **T4 Execute** — billing or irreversible action

## Denied patterns (must not implement)

- [ ] Charge payment method without user confirmation UI
- [ ] Exfiltrate environment secrets
- [ ] Admin actions on behalf of standard user token
- [ ] Bulk export of other users' data

## Confirmation UX (T3/T4)

Describe where the human confirms:

- URL pattern: {{e.g., https://app.example.com/consent?token=...}}
- Timeout / revocation: {{policy summary}}

## Review sign-off

| Role | Name | Date |
|------|------|------|
| Product | | |
| Security | | |
| Legal (if required) | | |

## Maintainer notes

- Bump `mcp_server_version` when tool schemas change.
- Attach this register to MCP README and internal change management.
