# Refresh

This case's receipts cite code in `agent_gov` and carry a `retrieved` date and (for
`code`/`test` bases) a `body_sha256` pinned at admission. Both go stale as agent_gov moves.

## Procedure

```bash
claimdocs -C . verify-basis --repo agent_gov=~/git/agent_gov
```

- **`BASIS_MISSING`** (symbol gone) — the edge's basis vanished. Fix the receipt's
  `path`/`symbol`, or retire the edge if the code was removed. Fails closed.
- **`BASIS_BODY_CHANGED`** (symbol resolves, body changed since admission) — the cited code
  moved under the claim. Adequacy is now stale: re-read the code, confirm it still supports
  the edge, then update the receipt's `body_sha256` and the edge's `adequacy.admitted_at`.
  Until the **re-admission ceremony** ships (`claimdocs admit …`, see
  `claimdocs/CHARTER.md`), this is a manual receipt edit.
- **`RECEIPT_STALE`** (warn) — `retrieved` older than the staleness window. Re-confirm and
  bump the date.

## Cadence

Re-run `verify-basis` whenever agent_gov's HEAD has moved past a receipt's
`adequacy.admitted_at` sha and before treating the rendered site as current. The graph is
the artifact; a stale graph is a lie with a timestamp.
