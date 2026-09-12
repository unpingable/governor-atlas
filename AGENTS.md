# Documentation guidance

Governor Atlas is a claimdocs case repository, not a runtime implementation.
Keep public wording grounded in `cases/`, `receipts/`, and `claimdocs.yml`.

- Describe the classic Agent Governor standing/spendability case as a bounded
  specimen, not a complete current Agent Governor NG topology.
- Describe constellation edges at their recorded modes. `specified` and
  `candidate` do not mean implemented, integrated, or consumed.
- Keep basis existence, cited-body freshness, human adequacy, runtime behavior,
  and operational authority distinct.
- Put claimdocs global options such as `--project` and `--today` before the
  subcommand. Put `verify-basis --repo` after that subcommand.
- Use public absolute links for other repositories. Do not publish local paths,
  campaign records, private notes, or credentials.
- Do not regenerate `docs/` unless the requested change includes the generated
  readout; inspect the complete generated diff before committing it.
