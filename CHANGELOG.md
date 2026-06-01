# Changelog

All notable changes to this plugin are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.1] - 2026-06-01

### Fixed

- Bind the skill to a write-capable agent so it can actually produce its
  documented `docs/audits/AUDIT_REPORT_YYYY-MM-DD.md` deliverable. The skill
  pinned `agent: Plan`, but Claude Code's `Plan` subagent ships without
  `Write`/`Edit`/`NotebookEdit` (and without `Agent`), so runs silently
  degraded to chat-only output and could not spawn the parallel per-document
  extraction agents. Switched to `agent: general-purpose`, preserving the
  `context: fork` isolation that was the actual rationale for the binding.
  ([#1](https://github.com/2389-research/documentation-audit/issues/1))
- Update `CLAUDE.md` and `plugin.json` prose that named the "Plan agent" so the
  docs no longer misdescribe the binding.

## [2.0.0]

### Added

- Initial release of the documentation-audit plugin: two-pass extraction
  (direct claim verification, pattern expansion, gap detection) with parallel
  per-document extraction agents.
