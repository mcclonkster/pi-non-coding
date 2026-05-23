---
record_type: handoff
status: current
origin: codex
created_by: codex
producer_type: agent
created_date: 2026-05-23
last_updated_by: codex
source_files_checked:
  - AGENTS.md
  - README.md
  - docs/context/README.md
  - docs/context/scans/2026-05-22_194850_repo-scan.md
related_records:
  - docs/context/scans/2026-05-22_194850_repo-scan.md
supersedes: []
superseded_by: []
confidence: confirmed
---

# Non-coding fork checkpoint

## Current goal

Turn the private fork at `/Users/computerk/github/pi-non-coding` into its own non-coding product rather than a contribution fork for upstream Pi.

## Current branch and Git state

- Branch: `non-coding`
- Baseline commit: `a4b1c4e4 Add initial repo scan`
- `main`, `origin/main`, and `upstream/main` were previously observed at upstream baseline commit `c85dbb16`.
- Current uncommitted changes:
  - `.gitignore` modified to allow `docs/context/plans/`
  - root scan path deleted because the scan was moved
  - `docs/context/` files added
  - `tasks/README.md` added

## Completed work

- Created branch `non-coding`.
- Committed the initial repo scan:
  - `a4b1c4e4 Add initial repo scan`
- Created lightweight workspace coordination lanes:
  - `docs/context/`
  - `docs/context/scans/`
  - `docs/context/plans/`
  - `tasks/`
- Moved the scan from the repo root to:
  - `docs/context/scans/2026-05-22_194850_repo-scan.md`
- Added lane README files with provenance metadata.
- Found that `.gitignore` ignored any `plans/` directory and added a narrow exception for `docs/context/plans/`.

## Key decisions

- This private repo is becoming its own product, not a staging fork for upstream PRs.
- `non-coding` is the current product-direction branch.
- `main` should remain the clean upstream baseline until the product direction is stable enough to make the fork's `main` diverge deliberately.
- Use the inactive Git-specific skills as references for safety and review:
  - `gstack-main/careful`
  - `gstack-main/review`
  - `gstack-main/context-save`
  - `downloaded-skill-repos/ECC-main/skills/git-workflow`
  - `downloaded-skill-repos/wshobson-agents-main/plugins/developer-essentials/skills/git-advanced-workflows`

## User preferences stated in chat

- Do not recommend active-folder skills when the user asks specifically for inactive skills.
- Verify exact skill paths before naming them.
- For Git work, use Git-specific workflow skills and show evidence.
- Keep explanations direct and beginner-friendly.
- Do not treat this private fork like a normal upstream contribution workflow.

## Important corrections

- The inactive path `/Users/computerk/.agents/skills-inactive/downloaded-skill-repos/guided-git-workflow/SKILL.md` was checked and does not exist.
- The verified inactive Git workflow candidates include:
  - `/Users/computerk/.agents/skills-inactive/downloaded-skill-repos/ECC-main/skills/git-workflow/SKILL.md`
  - `/Users/computerk/.agents/skills-inactive/downloaded-skill-repos/Awesome-Agent-Skills-for-Empirical-Research-main/skills/33-Galaxy-Dawn-claude-scholar/skills/git-workflow/SKILL.md`
  - `/Users/computerk/.agents/skills-inactive/downloaded-skill-repos/wshobson-agents-main/plugins/developer-essentials/skills/git-advanced-workflows/SKILL.md`

## Checks already run

- `git status --short --branch`
- `git log --oneline --decorate -5`
- `git remote -v`
- `git worktree list --porcelain`
- `find docs/context tasks -maxdepth 3 -type f -print | sort`
- `git check-ignore -v docs/context/plans/README.md`
- `rg` searches under `/Users/computerk/.agents/skills-inactive` for Git-specific inactive skills

## Next action

Review the current uncommitted workspace-lane changes before committing:

1. Inspect `git status --short --branch`.
2. Inspect `git diff -- .gitignore`.
3. Inspect the new files under `docs/context/` and `tasks/`.
4. Stage exact paths only.
5. Confirm staged name/status with the user.
6. Commit only after the user approves the staged set and commit message.

## Suggested following phase

Define the non-coding product direction:

1. Read the repo scan.
2. Define who the non-coding product serves.
3. Decide what changes from Pi: name, prompts, default tools, docs, examples, commands, and package identity.
4. Decide what stays: runtime, provider layer, TUI, extensions, sessions.
5. Write the product-direction plan in `docs/context/plans/`.
6. Add initial actionable tasks in `tasks/`.
