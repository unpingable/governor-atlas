# Provenance

This project is human-directed and AI-assisted. Final design authority,
acceptance criteria, and editorial control rest with the human author.
AI contributions were material and are categorized below by function.

## Human authorship

The author owns the Agent Governor system this case documents, defined the
thesis (NLAI — "language is a proposal, not an authority"), and set the
acceptance criterion that the documentation be admitted in AG's own grammar.
AI systems contributed claim extraction, case drafting, and implementation
under author supervision; they did not independently determine what is true
about the system. The author reviewed, revised, or rejected AI output throughout.

## AI-assisted collaboration

### Claim graph, receipts, and case assembly

Lead collaboration: Claude (Anthropic) via Claude Code. Built the
`claimdocs.yml` vocabulary pack, the two cases (standing-spendability internals
and the constellation seams), and the receipts — each grounded by reading the
actual `agent_gov` source and pinning a file + symbol + body hash, not by
asserting relationships. Where a seam was only a stub (e.g. `standing_client.py`,
self-described "SPEC-honoring harness stub"), the edge was recorded as
`specified`, not `wired`.

### Doctrine framing and adversarial critique

Lead collaboration: ChatGPT (OpenAI), with a separate Claude (Anthropic) review
session. Developed the typed-edge framing, the `spec_is_not_wired` rule, and the
`resolved ⊬ supported` correction that this case dogfoods (every `wired` edge
carries an adequacy admission, verified against the live tree).

## Provenance basis and limits

This document is a functional attribution record based on commit history,
co-author trailers (where present), project notes, and documented working
sessions. It is not a complete forensic account of all contributions.

Some AI contributions (especially design critique, rejected alternatives,
and footguns avoided) may not appear in repository artifacts or commit
metadata.

Model names/tools are recorded at the platform level (e.g., ChatGPT,
Claude Code); exact model versions may vary across sessions.

## What this document does not claim

- No exact proportional attribution. Contributions are categorized by
  function, not quantified by token count or lines of code.
- The claim graph's correctness is bounded by its receipts. An edge is only as
  true as the basis it cites resolves and is admitted to support — see the
  engine's CHARTER (`claimdocs/CHARTER.md`).

---

This document reflects the project state as of 2026-06-16 and may be revised.
