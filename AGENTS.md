# Accessibility Mod Template (Codex)

Codex reads this file before doing any work.

## Codex client

- Primary: Codex CLI (local)
- Profiles for this repository are in `.codex/config.toml` and selected with:
  - `codex --profile default`
  - `codex --profile research`
  - `codex --profile deps`
- Detailed CLI workflow notes: `docs/codex-workflow.md`

## User

- Blind, uses a screen reader
- The user provides direction; Codex writes code independently and explains decisions
- For uncertainties: ask briefly, then proceed with the best-supported assumption
- Screen reader-friendly output: do not use markdown tables that contain the '|' character; use headings and lists instead

## Project start

When the user greets you in this repository (for example: "Hello", "New project", "Let's go"):
- Read `accessibility-mod-template/docs/setup-guide.md`
- Run the "setup interview" described there

## Environment (fill during setup)

- OS: Windows (PowerShell; optionally Git Bash if installed)
- Game directory: [FILL IN DURING SETUP]
- Architecture: [32-BIT OR 64-BIT]
- Runtime: [net35 / net6 / etc. from MelonLoader log]

## Coding rules

- Handler classes: `[Feature]Handler`
- Private fields: `_camelCase`
- Logs and comments: English
- Build command: `dotnet build [ModName].csproj`

## Coding principles

- Playability, not simplification: make the game playable as sighted players play it; only suggest cheats when unavoidable
- Modular: separate input handling, UI extraction, announcements, and game state
- Maintainable: consistent patterns, easily extensible
- Efficient: cache objects; avoid unnecessary per-frame processing
- Robust: use utility classes; handle edge cases; announce state changes
- Respect game controls: never override game keys; handle rapid key presses

Code patterns and architecture: `accessibility-mod-template/docs/ACCESSIBILITY_MODDING_GUIDE.md`

## Before implementation

Always do the following before writing new code:

1. Search `decompiled/` for the real class and method names; never guess
2. Check `docs/game-api.md` for documented keys, methods, and patterns
3. Use only the "Safe Keys for Mod" section (see `docs/game-api.md` -> "Game Key Bindings")

## References

- `accessibility-mod-template/docs/setup-guide.md` - project setup interview
- `accessibility-mod-template/docs/ACCESSIBILITY_MODDING_GUIDE.md` - code patterns and architecture
- `accessibility-mod-template/docs/localization-guide.md` - localization for announcements and UI text
- `accessibility-mod-template/docs/menu-accessibility-checklist.md` - keyboard navigation checklist for menus
- `accessibility-mod-template/docs/game-api.md` - keys, methods, documented patterns (generated from template)
- `accessibility-mod-template/templates/` - code templates
- `accessibility-mod-template/scripts/` - PowerShell helper scripts

## Requesting additional local game files (mandatory protocol)

If Codex requires files that are not yet present in the repository workspace, it MUST:

1. Explicitly state **why** the files are needed (what question cannot be answered without them).
2. Specify **exact source paths** relative to the game installation directory.
3. Specify **exact destination paths** under `accessibility-mod-template/workspace-input/`.
4. List **exact filenames or directories** to be copied (no wild guesses, no globbing).
5. Stop and wait for the user to confirm the copy before continuing analysis.

Codex MUST NOT:
- Assume access to the user's local filesystem outside the repository.
- Request broad scans (e.g. “entire game folder”, “whole disk”).
- Proceed as if requested files exist before the user confirms the copy.

Example of a correct request:

“I need `globalgamemanagers` from `<GAME_INSTALL_DIR>/<GAME_NAME>_Data/` to inspect UI initialization order.
Please copy it to `accessibility-mod-template/workspace-input/ui/` and confirm when done.”

## Pre-analysis message requirement (hard gate)

Codex MUST refuse to begin any analysis unless the user has sent the pre-analysis message template:

- `accessibility-mod-template/docs/pre-analysis-message.md`

If the user has not sent it yet, Codex MUST respond with:
- A short request to send the template message, and
- A reminder that only `accessibility-mod-template/workspace-input/` contents can be analyzed.

Codex MUST NOT proceed with “best effort” analysis without this gate being satisfied.

## Git and GitHub operations (mandatory approvals)

Codex MUST treat repository publishing as a high-risk action.

Rules:
- Always ask for explicit approval BEFORE running any `git` or `gh` command that can modify state outside the workspace, including:
  - `git init`, `git add`, `git commit`, `git tag`, `git push`, `git pull`, `git fetch`
  - `git remote add|set-url|remove|rename`
  - any `git config` changes (local or global)
  - any `gh ...` command (GitHub CLI), including `gh auth ...` and `gh repo ...`
- Never request or handle secrets in chat (tokens, passwords). Do not ask the user to paste a PAT.
  - Preferred: the user runs `gh auth login` interactively on their machine.
- Before configuring a remote, ask the user for:
  - the intended GitHub repository URL (HTTPS or SSH)
  - whether they want SSH or HTTPS
  - which branch name they want to use (`main` recommended)
- Before any push, confirm:
  - the target remote name (usually `origin`)
  - the target branch
  - whether the repository is public or private
- If required info is missing, stop and ask. Do not guess.

## Git operations (mandatory approvals)

Codex MUST distinguish between read-only Git commands and mutating/network-affecting Git commands.

### Allowed without explicit approval (read-only)

The following commands may be executed without asking for approval, as they do not modify
repository state or communicate with remotes:

- git status
- git diff
- git diff --cached
- git log
- git show
- git branch (listing only)
- git rev-parse
- git describe

### Always require explicit approval (mutating or network)

Codex MUST ask for explicit approval before executing ANY of the following:

#### Repository state / history
- git commit
- git commit --amend
- git tag
- git reset (any mode)
- git rebase
- git cherry-pick
- git merge

#### Working tree cleanup
- git clean (any flags)
- git checkout
- git switch
- git restore

#### Remotes and network
- git remote add/remove/set-url
- git fetch
- git pull
- git push

#### Configuration
- git config (ANY scope)
  - global and system scope MUST be refused unless explicitly justified and approved

Codex MUST always state:
- the exact command it intends to run
- why it is needed
- what files, branches, or remotes it will affect

## Accessibility goal compliance (MANDATORY)

Codex MUST explicitly respect and adhere to the stated Accessibility goal defined in
`docs/pre-analysis-message.md`.

- Codex MUST NOT propose solutions that contradict the stated Accessibility goal.
- Codex MUST treat the Accessibility goal as a hard constraint, not a suggestion.
- If a requested action or proposed solution would violate the Accessibility goal,
  Codex MUST stop and ask for clarification before proceeding.

## Workspace input ingestion (Codex CLI) (MANDATORY)

When required analysis inputs (logs, assemblies, UI dumps) are NOT present in
`accessibility-mod-template/workspace-input/`, Codex MUST:

1) Follow the trusted-project prerequisite documented in:
   `docs/setup-guide.md` → section
   **"Codex CLI: enabling safe local file access (trusted project)"**

2) Request ONLY the minimum set of files required for the task.

3) Prefer approved auto-copy:
   - Ask for explicit approval to create missing subfolders under `workspace-input/`
     and copy the required files into them.
   - If approval is denied, provide exact manual copy instructions (what, from where, to where).

This document defines mandatory behavior for Codex.
All concrete user-facing setup steps live in `docs/setup-guide.md`.
