# Next — governor-atlas (the case)

This repo is a claimdocs *case*, not the engine. Its work is graph content + AG-specific
readouts. Engine-side work lives in `claimdocs/NEXT.md`.

## 1. Broaden the graph
Two cases (standing-spendability internals + constellation) are a thin slice of AG. The
graph is only as honest as its coverage. Candidate next cases, each with real `wired`
basis to cite:
- **receipt-kernel invariants** — the 13 constitutional invariants as nodes; "X invariant
  gates ledger.append" edges. Rich `wired` material.
- **runtime supervisor fail-closed gate** — the Tock-1 pre-tool gate; a gate edge with a
  typed refusal, mirrors the internals case shape.
- **standing validator chain (C2–C5)** — the supersession lineage as `derived`/`deprecated`
  edges once `deprecated` lands engine-side.

Each new case widens the conjunction — every admitted seam is a new term that must hold.
Prefer exhaustive coverage of a tight boundary over scattered breadth.

## 2. The manpage first slice
The standing-spendability chain → `docs/man/ag-standing-spendability-gate.7.md`,
`ag-origin-fence.7.md`, `ag-recomposition-receipt.5.md`, `ag-constellation.7.md`.
**Blocks on: doc-normalization, which blocks on re-admission** (see `claimdocs/NEXT.md`).
Don't hand-write these — they're the first consumer of the normalizer.

## 3. gh-pages deploy
`docs/` is currently committed by hand (matches the sibling atlases). Wire a CI step that
runs `claimdocs render` and publishes, so the published site can't drift from the claim
graph. First settle how CI gets claimdocs (submodule / editable sibling / published) — the
placeholder in `.github/workflows/ci.yml` names the options.

## Settled (don't re-litigate)
- **Vocabulary:** `wired` aliased to canonical `documented` via `canonical:` in
  `claimdocs.yml`. Dialect at the edge, boring spine in the core.
- **docs/ is a readout, the graph is the artifact** — re-render freely.

## Keeping it honest over time
Receipts go stale as agent_gov moves. `REFRESH.md` is the procedure: re-run
`claimdocs verify-basis --repo agent_gov=~/git/agent_gov` and re-admit on
`BASIS_BODY_CHANGED`. A stale graph is a lie with a timestamp.
