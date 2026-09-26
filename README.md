# invinoveritas for Claude

**The verification layer for autonomous agents.** A neutral verdict before an irreversible action, a signed proof after, free
verification of any proof, and a public track record of verdicts, so an agent's judgment can be checked without trusting us.

## What's inside
- **MCP server** (remote, OAuth 2.1): `https://api.babyblueviper.com/mcp/verify`. Tools: `review` (pre-action verdict, optional
  signed proof), `witness` (signed, timestamped third-party claims), `verify_proof` (free, offline-checkable),
  `ledger` (free, public verdict track record), `ledger_submit`, `validate`, `conformance_certify`, `audit_agent_readiness`.
- **Skills**: `pre-action-review` (ask for a second opinion before anything irreversible) and `verification-handshake`
  (demand a proof on what you receive, attach one to what you ship).

## Free vs paid
Free, no account: `verify_proof`, `ledger`. Paid calls (`review`, `witness`, ...) need a linked account: sign in when
Claude asks (you can create a free account on the consent screen), then fund with Lightning, USDC (x402) or card.

## What a verdict is not
A verdict is a reasoned second opinion, not a guarantee of outcome. A proof establishes who asserted what and when, and that it
hasn't changed; it does not establish that the underlying event happened as described.

## Links
Service: https://api.babyblueviper.com · MCP card: https://api.babyblueviper.com/mcp/verify · Verify a proof: https://api.babyblueviper.com/verify-proof
