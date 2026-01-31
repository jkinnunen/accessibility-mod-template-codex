# Accessibility Mod Template (Codex) – v1.4.0

This release finalizes the Codex-based accessibility modding template and resolves all
structural, naming, and workflow ambiguities identified since the initial Claude-based
template.

## Highlights

- Fully migrated from Claude to Codex (terminology, workflows, and enforcement)
- Clear separation of responsibilities:
  - AGENTS.md: mandatory Codex behavior
  - setup-guide.md: authoritative setup instructions (human + Codex)
  - codex-workflow.md: operational runbook
- Approval-gated automatic copying of required artifacts into workspace-input
- Explicit trusted-project prerequisite for local filesystem access
- IL2CPP-aware documentation and accessibility strategy
- Workspace-input structure made explicit and reproducible

## Breaking / structural changes since 1.0

- Claude-specific files and assumptions removed
- CODEX.md replaces CLAUDE.md
- workspace-input introduced as canonical analysis input location
- AGENTS.md now enforces accessibility goals and filesystem behavior
- setup-guide.md restructured as authoritative configuration source
- dnSpy replaced with dnSpyEx
- ILSpy CLI usage clarified (ilspycmd is separate)

## Intended usage

This template is intended to be used as a GitHub template repository for:
- Accessibility mods
- Screen reader support
- IL2CPP Unity games (e.g., The Long Dark)

Status: Stable
