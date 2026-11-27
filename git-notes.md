# Git notes

Commands I reach for, with what each one is for.

## Look before you change
- `git status` — what changed and what is staged.
- `git diff` / `git diff --staged` — the exact lines, before and after staging.
- `git log --oneline --graph -20` — recent history as a picture.

## Branches and worktrees
- `git switch -c feature/x origin/main` — a new branch from the latest main.
- `git worktree add ../x feature/x` — a second checkout, so two tasks never share files.
- `git worktree list` — every checkout and its branch.

## Merging safely
- `git fetch origin` then `git merge origin/main` — bring in others' work; never rebase shared branches.
- `git -c merge.conflictStyle=diff3 merge …` — conflicts also show the common base, so you can tell who changed what.
- `git merge --abort` — back out of a merge that went wrong.

## Undo without losing work
- `git restore <file>` — drop unstaged changes in one file.
- `git commit --amend` — fix the last commit (only before pushing).
- `git revert <sha>` — undo a pushed commit with a new commit.
