# Codex Cloud task template (safe with this repository)

Use this template when you create a Codex Cloud task for this project.
It forces correct assumptions about local game data.

---

## Task context (mandatory)

- This project uses the Accessibility Mod Template.
- You MUST follow `AGENTS.md` and the docs under `accessibility-mod-template/docs/`.
- The ONLY local game artifacts you may rely on are under:
  `accessibility-mod-template/workspace-input/`

## Artifacts available (fill in)

- logs/: [what is included]
- managed/: [what is included]
- managed/il2cpp/: [what is included, if any]
- loader/net6/: [what is included, if any]
- decompiled/: [present / not present]
- ui/: [what is included, if any]

## Restrictions (mandatory)

- Do NOT assume access to my local filesystem.
- Do NOT assume any artifacts exist unless listed above.
- If more artifacts are required, say exactly what is needed and why, and where it should be copied within `workspace-input/`.

## What I want you to do (fill in)

[Describe the exact change you want in the repository.]