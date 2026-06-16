# governor-atlas

**The [Agent Governor](https://github.com/unpingable) architecture as a typed,
receipt-backed claim graph — the first serious specimen of [claimdocs](../claimdocs).**

This is a **claimdocs case repo**. The engine (lint / verify / render) lives in
[claimdocs](../claimdocs); everything here is the Agent Governor *vocabulary pack*
(`claimdocs.yml`) plus the claim graph (`cases/` + `receipts/`). claimdocs core knows
nothing about "standing" or "spend walls" — the specimen must not contaminate the
primitive.

The recursion is the point. AG's whole thesis is **NLAI — language is a proposal, not an
authority.** A doc that *describes* an edge is a proposal; the code that *runs* it is the
authority. claimdocs refuses to let a proposal masquerade as the authority — so AG is
documented in its own grammar.

## Run it

```bash
pip install -e ../claimdocs          # or: PYTHONPATH=../claimdocs/src python -m claimdocs ...
claimdocs lint                       # citation-shape validation
claimdocs verify-basis --repo agent_gov=~/git/agent_gov   # resolve code/test bases + freshness
claimdocs report                     # the fail-closed instrument panel
claimdocs render && claimdocs serve  # build + serve the site at localhost:8000
```

## The two cases

- **`internals-standing-spendability`** — the three-gate spend wall (origin fence,
  standing-spendability gate, operational spend wall). Every edge `wired` to code + test,
  each `gates` edge names the typed refusal it emits, each carries an adequacy admission
  pinned to an agent_gov sha. The hero specimen: the default filter changes nothing,
  because the seam is finished. `verify-basis` resolves all five symbols *and* confirms
  their bodies are unchanged since admission.
- **`constellation`** — what AG asks of its siblings (standing, linear accountant, wicket,
  night shift, NQ). Nearly every edge is `specified` — the adapter files exist but
  self-describe as SPEC-honoring harness stubs. Filter to `wired` and the graph nearly
  empties. That emptiness is the honest finding.

## Claim modes (this project's vocabulary)

Declared in `claimdocs.yml`. `wired / specified / derived / candidate` — AG-native names
for claimdocs's witnessing / spec / derivation / reserved modes.

- **`wired`** — witnessed in running, tested code. The only mode in the default view.
- **`specified`** — a spec or stub names it; not witnessed. `spec_is_not_wired`: a stub
  file existing (e.g. `standing_client.py`, self-described "SPEC-honoring harness stub")
  is named, not wired — claimdocs refuses to promote it.
- **`derived`** — composition of other edges (depth-1).
- **`candidate`** — a reserved name, no forcing case yet. Hidden by default, capped.

## Doctrine

The general doctrine — `resolved ≠ supported`, `spec_is_not_wired`, mode-preserving
rendering, "pages explain the graph, they don't outrank it" — lives in
[claimdocs/CHARTER.md](../claimdocs/CHARTER.md). It was discovered here and promoted up so
the primitive carries it. This repo keeps only the AG-specific framing above.

> Docs that fail closed.

Apache 2.0.
