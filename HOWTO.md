# Inspect the Governor Atlas

Install claimdocs from its public repository, then run global options before
the command name:

```sh
claimdocs --project /path/to/governor-atlas --today YYYY-MM-DD lint
claimdocs --project /path/to/governor-atlas --today YYYY-MM-DD report
claimdocs --project /path/to/governor-atlas --today YYYY-MM-DD \
  verify-basis --repo agent_gov=/path/to/agent_governor
```

`lint` validates configured graph and receipt shapes. `report` lists recorded
edges without executing the systems they describe. `verify-basis` resolves the
declared source artifacts and compares the cited body where a receipt includes a
body hash.

Interpret the outputs in separate layers:

- an edge is a recorded claim at its declared mode, not observed runtime state;
- resolution establishes that the cited artifact exists;
- cited-body freshness establishes only that cited bytes have not changed;
- freshness does not cover callees, fixtures, dependencies, or datasets;
- adequacy is the recorded human judgment that a basis supports an edge;
- none of these grants operational authority or proves current integration.

The `internals-standing-spendability` case is a bounded classic Agent Governor
specimen. The `constellation` case records requested interfaces. Do not present
either as a complete map of Agent Governor NG or the current Constellation.

`claimdocs render` rewrites generated files under `docs/`. Review that diff
before committing it. Rendering preserves modes; it does not strengthen claims.
