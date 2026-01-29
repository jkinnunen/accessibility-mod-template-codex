# Breaking / structural changes since version 1.0

This document summarizes **non-trivial structural changes** introduced after the original
Claude-oriented template (v1.0.x).

---

## Documentation architecture

- Clear separation of responsibilities:
  - README.md: human-facing, pre-install and project creation instructions
  - setup-guide.md: project-specific setup interview (no install steps)
  - codex-workflow.md: Codex-only runbook (post-install)
  - AGENTS.md: mandatory behavioral rules for Codex

- Removal of all Codex installation and quick-start instructions from codex-workflow.md.
- Introduction of explicit pre-analysis gating via `docs/pre-analysis-message.md`.

---

## Codex-specific infrastructure

- Added `.codex/config.toml` with selectable profiles.
- Mandatory use of `gpt-5.2-codex` across all profiles.
- Explicit approval and network access policies.

---

## Workspace model

- Introduced `workspace-input/` as the ONLY location for external game artifacts.
- Added explicit subfolders for:
  - loader/net6
  - managed/il2cpp
- Documented IL2CPP + MelonLoader layouts (Unity 6 compatible).

---

## IL2CPP strategy

- Added `docs/il2cpp-accessibility-strategy.md`.
- Explicitly documents what analysis is and is not possible with IL2CPP builds.
- Shifts focus from source analysis to runtime observation and hooks.

---

## Codex Cloud discipline

- Added `docs/codex-cloud-task-template.md`.
- Enforces artifact listing and forbids assumptions about local filesystem access.

---

## Licensing and attribution

- Added NOTICE.md with proper CC BY 4.0 attribution.
- Linked original template repository.

---

These changes are intentional and designed to prevent incorrect assumptions
about Codex capabilities, filesystem access, and IL2CPP analysis.