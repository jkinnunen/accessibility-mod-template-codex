# Welcome!

This repository is a starting point for building game accessibility mods (primarily for Unity games via MelonLoader) with help from OpenAI Codex.

It is designed for blind screen reader users (NVDA, JAWS, etc.) and focuses on repeatable patterns:
- Extract UI/game state
- Provide keyboard navigation
- Announce meaningful changes via screen reader
- Keep gameplay as close as possible to how sighted players play

## Important disclaimer

This template is work in progress. Use it as a foundation, then adapt it to the specific game you are modding.

## What you need

### 1. A Unity game (recommended)

MelonLoader is for Unity. If the target game is not Unity, you will likely need a different modding approach.

### 2. Modding toolchain

- MelonLoader (installed into the game directory)
- .NET SDK (for building the mod project generated from this template)
- Git (recommended, so you can track changes Codex makes)

### 3. Codex

You can use Codex in ChatGPT (cloud tasks) or locally via Codex CLI.

Project-level instructions for Codex are in:
- `AGENTS.md` (project guidance; Codex reads this automatically)
- `.codex/config.toml` (optional project config; loaded when the project is trusted)

## Getting started

1. Copy this template into a new repository for your mod project.
2. Open the repository in your Codex environment (ChatGPT Codex or Codex CLI).
3. Start with a greeting message (for example: "New project").
4. Follow the setup interview in `accessibility-mod-template/docs/setup-guide.md`.

## Documentation

All core guidance is under `accessibility-mod-template/docs/`:
- `setup-guide.md` (first-time setup interview)
- `ACCESSIBILITY_MODDING_GUIDE.md` (architecture and patterns)
- `menu-accessibility-checklist.md` (menu navigation checklist)
- `localization-guide.md` (multi-language announcements and UI text)
- `technical-reference.md` (MelonLoader/Harmony/Tolk reference)

## License

See `LICENSE`.

## Codex CLI profiles

This template ships with three Codex CLI profiles (default, research, deps) in `.codex/config.toml`. For usage and commands, see `docs/codex-workflow.md`.

## Getting started (Codex CLI)

These steps are intended for humans to follow **before Codex is installed**.

### 1) Install Codex CLI

Prerequisite: Node.js (includes npm).

Install Codex CLI:

```
npm i -g @openai/codex
```

Update Codex CLI later:

```
npm i -g @openai/codex@latest
```

### 2) First run / sign-in

From a terminal, run:

```
codex
```

Follow the on-screen prompts to authenticate.

### 3) Start a new accessibility mod project from this template

1. Extract this template ZIP into a new folder (for example `C:\Projects\MyGame-AccessibilityMod\`).
2. Open a terminal in the project root (the folder that contains `AGENTS.md` and `.codex/`).
3. Start Codex:

```
codex
```

4. Before any analysis, send the pre-analysis message:
- `accessibility-mod-template/docs/pre-analysis-message.md`

5. Run the setup interview:
- `accessibility-mod-template/docs/setup-guide.md`

6. For detailed workflows (profiles, approvals, sandbox, Cloud tasks), see:
- `accessibility-mod-template/docs/codex-workflow.md`

## Attribution

Original template repository:

- https://github.com/HappyStarfish/Accessibility-mod-template

This repository is based on the "Accessibility Mod Template" by Happy Starfish (CC BY 4.0). See LICENSE and NOTICE.md.

## Codex usage

This repository includes detailed Codex instructions:

- Codex CLI installation + quick start: `accessibility-mod-template/docs/codex-workflow.md`
- Pre-analysis message: `accessibility-mod-template/docs/pre-analysis-message.md`
- Setup interview: `accessibility-mod-template/docs/setup-guide.md`
- IL2CPP strategy: `accessibility-mod-template/docs/il2cpp-accessibility-strategy.md`

- Codex Cloud task template: `accessibility-mod-template/docs/codex-cloud-task-template.md`
