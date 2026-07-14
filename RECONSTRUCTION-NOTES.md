# Reconstruction notes (build provenance)

These two zips were rebuilt from the CMP "SHIP THIS" edition attachments (Claude v23, Codex v24) exported on 2026-07-14. The CMP export flattened the folder tree, renamed every file, and turned the `.py` scripts into generic `.txt` files. This build restores the real tree, filenames, and executable bit, and strips macOS junk.

## What was verified
- All 10 scripts (5 per edition) pass `python3 -m py_compile`.
- `build_review_packet.py` does `from render_harness_map import …`; the import target is present.
- Every `references/…`, `assets/…`, and `scripts/…` path referenced in each `SKILL.md` and `audit-protocol.md` exists in the tree.
- File counts match the source-of-truth handoff: Claude 22, Codex 23.

## Two repairs / decisions worth knowing
1. **Claude `scripts/validate_run_trace.py` was backfilled from the Codex edition.** The Claude CMP export dropped it and duplicated `scan_visible_harness.py` instead. The run-trace validator is edition-agnostic ("validate a run-trace JSON file without dependencies"), so the Codex copy is correct for Claude. Claude's `assets/run-trace.schema.json` (which the validator checks against) was present in the export.
2. **The Codex plugin manifest filename is a best guess: `plugin.yaml`.** The export destroyed its real name. Content is intact (`interface: display_name / short_description / default_prompt`, `policy: allow_implicit_invocation: false`). The skill's core behavior runs off `SKILL.md` frontmatter regardless, so this only affects Codex's display-name/default-prompt registration. **Verify this filename against a real Codex install before relying on it.**

## Not yet done
- Neither zip has been through a live end-to-end install-and-run test. Scripts compile and all references resolve, but a real install on Claude and Codex is the final check before wide distribution.
