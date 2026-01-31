# Accessibility Mod Template (Codex) – v1.4.6

## Documentation integrity update

This release formally records the consolidation and verification of the
`game-api.md.template` file.

### game-api.md.template status

- The current `game-api.md.template` is a **content-complete superset** of the former
  `game-api.md.template.old`.
- All sections from the old template have been:
  - preserved,
  - modernized, and/or
  - expanded into clearer, more explicit structures.
- No accessibility-relevant, reverse-engineering-relevant, or modding-relevant
  information from the old template is missing.

### Notable consolidated areas

- Core game systems (game state, player, controllers)
- UI systems, focus handling, and interaction patterns
- Input system documentation
- Scene management and lifecycle effects
- Save system flows and UI dialogs
- Localization and text resolution
- MelonLoader lifecycle hooks
- Reverse engineering constraints (IL2CPP) and runtime-only observations
- Tooling and build context metadata

### Stability notice

The `game-api.md.template` file should now be considered **structurally stable**.
Future changes should be additive and justified; simplification or removal of
sections risks loss of critical accessibility context.

Status: Stable
