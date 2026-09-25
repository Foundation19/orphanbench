# Repository rules

| Path | Put here | Not here |
|---|---|---|
| root | `README.md` `CHANGELOG.md` `LICENSE` `LICENSE-DATA` `CLAUDE.md` | anything else |
| `docs/` | normative design documents, one topic per file, UPPER_SNAKE names | run outputs, data |
| `harness/` | schemas, prompts, scorer, quote checker (Apache-2.0) | data files |
| `baselines/` | published baseline runs, one folder per model and date | unreleased runs |
| `_local_archive/` | local-only material, ignored by git | anything meant to be public |

Naming: design versions `v0.N` in `CHANGELOG.md`; run folders `YYYY-MM-DD_<model>`; items and keys `*.jsonl`.

Never: commit data before its error-rate audit is disclosed (`docs/VERIFICATION.md`) · commit `_local_archive/` · write private paths or names · edit a registered hypothesis in place.
