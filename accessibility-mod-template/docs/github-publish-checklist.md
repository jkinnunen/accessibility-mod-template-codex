# GitHub publish checklist (Codex CLI)

Use this checklist when publishing a project created from this template.

1. Verify authentication (user runs outside Codex):
   - `gh auth login`
   - `gh auth status`

2. Confirm repository intent:
   - Repository name
   - Owner (user/org)
   - Public or private

3. Confirm content safety:
   - No sensitive files under `accessibility-mod-template/workspace-input/`
   - Logs/dumps are sanitized or excluded if needed

4. Configure git remote (approval required):
   - `git remote add origin <URL>`
   - `git branch -M main`

5. Push (approval required):
   - `git push -u origin main`
