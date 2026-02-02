# Changelog

All notable changes to the Accessibility Mod Template (Codex) are documented in this file.

This project uses a curated, narrative changelog intended to be readable by both
humans and Codex.

---

## [1.5.1] – 2026-02-02

### Changed
- Consolidated all historical change documentation into this single CHANGELOG.md file.
- Removed legacy CHANGES*.md and RELEASE-NOTES*.md files to eliminate duplication.

### Notes for Codex
- CHANGELOG.md is the sole authoritative source of historical changes going forward.

---

## [1.5.0]

### Added
- YOLO Codex profile with full-access sandbox (explicitly marked as dangerous).
- Per-assembly decompilation folder structure for ilspycmd output.

### Changed
- game-api.md.template verified and locked as a content-complete superset of the former template.
- Codex CLI configuration updated to string-based web_search modes.
- Trust configuration consolidated into setup-guide.md.

---

## [1.0.0 → 1.4.x] – Foundational restructuring

### Summary
This range includes major architectural and documentation changes that were not
fully tracked in earlier change logs.

### Key changes
- Transition from a Claude-oriented template to a Codex-first architecture.
- Introduction of AGENTS.md with enforced pre-analysis requirements.
- Automation of the pre-analysis step via pre-analysis-message.md.
- Separation of human-facing and Codex-facing documentation roles.
- Introduction of profile-based Codex CLI configuration.
- Formalization of IL2CPP accessibility analysis strategy.
- Structural cleanup and normalization of documentation files.

---
