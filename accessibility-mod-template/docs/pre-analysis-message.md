# Pre-analysis message (MANDATORY)

This message MUST be sent before Codex performs any analysis.
Unknown values are allowed and expected. Do NOT guess.

Use one of:
- known
- unknown
- unknown (needs verification)

---

## 1) Facts (what is known)

### Project / game
- Game:
- Game version:
- Engine (e.g. Unity Mono / Unity IL2CPP):
- Mod loader (and version):

### Platform
- OS:
- Architecture (x64 / arm64 / unknown):

---

## 2) Accessibility intent

Describe the accessibility problem or goal in plain language.
(What should work for a screen reader user?)

- Accessibility goal:

---

## 3) Available artifacts (workspace-input)

List ONLY files that are currently present.

- Files currently present in workspace-input:
  - none yet

---

## 4) Source locations used (if known)

If files were copied from non-standard locations, list them.
If not yet copied, use unknown.

- logs source path:
- managed / il2cpp source path:
- loader / net6 source path:

---

## 5) Analysis scope and permissions (CRITICAL)

Explicitly state what Codex is allowed to do in THIS session.

- Allowed actions:
  - Read files: [yes/no]
  - Propose changes (no writes): [yes/no]
  - Write code or docs: [yes/no]
  - Run commands: [yes/no]

- If commands are allowed:
  - git read-only commands allowed: [yes/no]
  - git mutating/network commands allowed (with approval): [yes/no]
  - GitHub CLI (gh) commands allowed (with approval): [yes/no]
  - Web search allowed: [yes/no]

---

## 6) IL2CPP realism check (if applicable)

Confirm understanding of IL2CPP limitations.

- I understand that IL2CPP assemblies may NOT contain:
  - method bodies
  - full UI event handler implementations
  - complete accessibility logic
- I understand runtime observation or hooks may be required.

Confirmation: [yes / no / not applicable]

---

## 7) Git & GitHub status (optional)

- Repository initialized (git init done): [yes/no/unknown]
- Current branch:
- Remote configured: [yes/no/unknown]

### GitHub publishing intent
- I intend to push to GitHub in this session: [yes/no/unknown]
- GitHub CLI auth already configured: [yes/no/unknown]
- Remote URL (if known):

---

## 8) Stop conditions

Codex MUST stop and ask before proceeding if:
- required files are missing
- permissions above are insufficient
- assumptions would be required
- IL2CPP limitations block requested analysis

---

End of pre-analysis message.
