# workspace-input checklist

This directory contains **all external artifacts** copied from the local game installation
for Codex analysis.

Before asking Codex to analyze anything, verify:

- [ ] Files were copied from the correct game version.
- [ ] Source paths are documented in your message to Codex.
- [ ] Files are placed in the correct subfolder:
  - logs/          -> MelonLoader and runtime logs
  - managed/       -> Managed assemblies (DLLs)
  - decompiled/    -> Decompiled source output
  - ui/            -> UI hierarchies, screenshots, UI dumps
- loader/        -> Mod loader runtime DLLs (e.g. MelonLoader/net6)
- managed/il2cpp -> IL2CPP-related assemblies provided by the loader
- [ ] No unrelated personal files are present.
- [ ] Codex has been explicitly told what was copied and why.

Codex MUST treat this directory as the **only source of truth** for local game data.
