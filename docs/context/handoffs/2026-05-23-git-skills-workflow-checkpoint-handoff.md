---
record_type: handoff
status: current
origin: codex
created_by: codex
producer_type: agent
created_date: 2026-05-23
last_updated_by: codex
source_files_checked:
  - /Users/computerk/.agents/skills/strategic-compact/SKILL.md
  - /Users/computerk/.agents/skills/git-skills/summary.md
  - docs/context/handoffs/2026-05-23-non-coding-fork-checkpoint-handoff.md
related_records:
  - docs/context/handoffs/2026-05-23-non-coding-fork-checkpoint-handoff.md
  - /Users/computerk/.agents/skills/git-skills/summary.md
supersedes: []
superseded_by: []
confidence: confirmed
---

# Git skills workflow checkpoint

## Current goal

Build a beginner-safe, private-fork-aware Git workflow for `/Users/computerk/github/pi-non-coding`, using selected inactive Git skills as reference material without activating them.

## Current branch and Git state

- Branch: `non-coding`
- Last committed project checkpoint: `a4b1c4e4 Add initial repo scan`
- Current uncommitted repo state observed on 2026-05-23:
  - `.gitignore` modified
  - root `2026-05-22_194850_repo-scan.md` deleted because it was moved
  - untracked `docs/`
  - untracked `tasks/`

## Completed work

- Reviewed Git-focused inactive/reference skills under `/Users/computerk/.agents/skills/git-skills/`.
- Renamed active-risk `SKILL.md` files under that folder to `SKILL-experimenting.md` so they can be read without being accidentally activated.
- Walked through the following reference packages:
  - `git-workflow-ecc`
  - `git-workflow-empirical-research`
  - `git-advanced-workflows-wshobson`
  - `careful-gstack`
  - `monorepo-management-wshobson`
  - `review-gstack`
  - `ship-gstack`
  - `context-restore-gstack`
  - `context-save-gstack`
- User created `/Users/computerk/.agents/skills/git-skills/summary.md` to collect the analyses in one place and fixed a duplicated section.

## Decisions made

- Do not activate these Git reference skills directly.
- Treat the private fork as a product fork, not as a default upstream contribution fork.
- Treat upstream as historical/reference input, not the default target for changes.
- Avoid GitFlow, `develop`, hotfix/release branch machinery, auto-shipping, routine rebase, and upstream sync as defaults.
- Favor exact-path staging and explicit approval over automation.
- Keep `ship-gstack` as reference only because it auto-commits, auto-pushes, and creates PRs.
- Borrow strongly from:
  - `careful-gstack` for destructive-command guardrails.
  - `review-gstack` for scope/diff review before commit or merge.
  - `context-save-gstack` and `context-restore-gstack` for durable handoff shape.
  - `git-advanced-workflows-wshobson` only for worktree and reflog concepts, not routine rebase/force-push behavior.

## Git elements explained to the user

- Fork: a copy of another repo, with `origin` as the user's private fork and possibly `upstream` as the original repo.
- Remote: a saved server location such as `origin` or `upstream`.
- Branch: a movable name for a line of commits.
- Product-divergence branch: a meaning assigned to `non-coding`, not a special Git feature.
- Worktree: a second checkout of the same repo in another folder for isolated branch work.
- Commit: a saved snapshot with a message.
- Staging: selecting what goes into the next commit.
- Exact-path staging: staging named files instead of `git add .`.
- Diff: the visible change set.
- Status: the current branch and changed-file state.
- Untracked, modified, deleted, staged, and unstaged files.
- Merge versus rebase.
- Force push, reflog, cherry-pick, bisect, stash, upstream sync, push, PR, and handoff/context save.

## Emerging workflow elements

- Start every Git action with live status.
- Make one coherent change at a time.
- Review the actual diff before staging.
- Stage exact paths only.
- Review the staged diff before committing.
- Ask before committing and use an approved commit message.
- Treat commit, push, PR, version bump, changelog, and release as separate decisions.
- Stop before destructive or history-rewriting commands and name the risk.
- Save durable handoffs in `docs/context/handoffs/`.

## User preferences stated in chat

- Do not recommend active-folder skills when the request is specifically about inactive skills.
- Verify exact skill paths before naming them.
- For Git work, use Git-specific workflow references.
- Explain concepts so the user can learn, not just receive recommendations.
- Do not use `review-a-skill` when the user asks for a walkthrough.
- Keep explanations direct, beginner-friendly, and evidence-backed.

## Checks already run in this phase

- `git status --short --branch`
- `find docs/context -maxdepth 3 -type f | sort`
- `sed` reads of the existing handoff and strategic compact template
- `wc -l` and `sed` reads of `/Users/computerk/.agents/skills/git-skills/summary.md`
- `find`, `wc`, `sed`, and `rg` reads across the Git reference skill folders

## Next phase

Turn the Git element analysis into one small repo-appropriate Git workflow artifact or skill.

## Next action

Decide the target artifact:

1. A repo-local workflow note under `docs/context/plans/`.
2. A new active skill under `/Users/computerk/.agents/skills/`.
3. A rule section for an existing Git workflow skill.

Then draft the minimal workflow around private-fork stance, status-first inspection, exact-path staging, review-before-commit, human approval gates, destructive-command guardrails, and repo-local handoffs.

## Open questions

- Should the new workflow live as a durable project document first, or become an active reusable skill immediately?
- Should it replace or supplement the existing `guided-git-workflow` and `human-agent-git-workflow` skills?
- Should the current uncommitted workspace-lane changes be committed before creating a new Git workflow artifact?
