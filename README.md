# governor-atlas

**A bounded classic [Agent Governor](https://github.com/unpingable/agent_governor)
specimen and its proposed constellation interfaces, represented as a typed,
receipt-backed claim graph for [claimdocs](https://github.com/unpingable/claimdocs).**

This is not a complete map of current [Constellation AG](https://github.com/unpingable/constellation-ag) or of the current
Constellation topology. It records a narrow classic-AG standing/spendability
boundary and a second case of requested cross-repository interfaces.

This is a **claimdocs case repo**. The engine (lint / verify / render) lives in
[claimdocs](https://github.com/unpingable/claimdocs); everything here is the Agent Governor *vocabulary pack*
(`claimdocs.yml`) plus the claim graph (`cases/` + `receipts/`). claimdocs core knows
nothing about "standing" or "spend walls" — the specimen must not contaminate the
primitive.

The recursion is the point. AG's whole thesis is **NLAI — language is a proposal, not an
authority.** A doc that *describes* an edge is a proposal; the code that *runs* it is the
authority. claimdocs refuses to let a proposal masquerade as the authority — so AG is
documented in its own grammar.

## Run it

```bash
pip install -e /path/to/claimdocs
claimdocs --project . lint
claimdocs --project . verify-basis --repo agent_gov=/path/to/agent_governor
claimdocs --project . report
claimdocs --project . render
claimdocs --project . serve
```

## The two cases

- **`internals-standing-spendability`** — a classic-AG three-gate specimen (origin fence,
  standing-spendability gate, operational spend wall). Its five `wired` edges cite their
  declared bases, each `gates` edge names the typed refusal it emits, and each carries an adequacy admission
  pinned to an agent_gov sha. The hero specimen: the default filter changes nothing,
  because the recorded specimen's witnessing edges are included. `verify-basis` checks
  basis existence and the cited bodies that carry hashes; it does not prove the edges or
  check their full dependency closures.
- **`constellation`** — what AG asks of its siblings (standing, linear accountant, wicket,
  Nightshift, NQ, and Continuity). Its relations are `specified` or `candidate`, not
  present-runtime wiring: adapter and stub files name requests without proving consumers.
  Nearly every edge is `specified` — the adapter files exist but
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
[claimdocs/CHARTER.md](https://github.com/unpingable/claimdocs/blob/main/CHARTER.md). It was discovered here and promoted up so
the primitive carries it. This repo keeps only the AG-specific framing above.

> Docs that fail closed.

Apache 2.0.

For a reproducible read-only inspection and the interpretation limits, see
[HOWTO.md](HOWTO.md).
