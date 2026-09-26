---
name: pre-action-review
description: "Get a neutral second opinion BEFORE an irreversible action: sending funds or tokens, signing or broadcasting an on-chain transaction, deploying code, running a destructive shell command, deleting data, changing production config. Use the invinoveritas `review` tool with sign=true, act on the verdict (approve / approve_with_concerns / reject), and keep the signed proof with the result so anyone can check it later with `verify_proof` (free). Keywords - before sending, before deploying, irreversible, second opinion, approve, reject, risk, sign off."
license: Apache-2.0
metadata:
  author: invinoveritas
  homepage: https://api.babyblueviper.com
  mcp_endpoint: https://api.babyblueviper.com/mcp/verify
---

# Pre-action review: a second opinion before you can't take it back

Some actions can't be undone: a transfer, a signed transaction, a production deploy, a `rm -rf`, a dropped table. The party doing
the work is the wrong one to grade it. Ask a checker with no stake in the outcome, before acting.

## When to use
Before any action that moves money or assets, changes production, deletes or overwrites data, or grants permissions, and whenever a
user says "double-check this first".

## How
1. Describe the exact proposed action in `artifact`: what, how much, where, why, and the stop/limit if any. Set `artifact_type`
   (`trade`, `onchain_action`, `shell_command`, `code_diff`, `config_change`, `plan`, ...).
2. Call `review` with `sign=true`.
3. Act on the verdict:
   - `reject` -> do not proceed; show the issues to the user.
   - `approve_with_concerns` -> tell the user the concerns and proceed only if they accept them.
   - `approve` -> proceed, and keep the signed proof with the result.
4. Anyone (a user, an auditor, another agent) can check the proof later with `verify_proof`, free and without trusting us.

## What a verdict is not
A verdict is a second opinion with stated reasons, not a guarantee. A signed proof shows who judged what and when, and that the
record hasn't changed. It does not show the outcome will be good.

## Cost
`review` is a paid call (sign in with the connector's OAuth; new accounts include a few free calls). `verify_proof`
and `ledger` are free.
