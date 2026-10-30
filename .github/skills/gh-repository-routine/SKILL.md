---
name: gh-repository-routine
description: "Use when using GitHub CLI (gh) to authenticate, create a repository, file issues, publish changes, or close issues after approval."
---

# GitHub Repository Routine

Use this workflow for a repository the user controls. Ask before creating a repository, creating or changing issues, or publishing commits. Explain whether the repository is public and who can see it. Never create an account, spend money, expose a token, or proceed without approval for the requested GitHub changes.

## Check the lane

1. Check for `gh` with `command -v gh` and inspect its version with `gh --version`.
2. If it is missing, ask before installing it; use an available package manager only after approval.
3. Check `gh auth status`. If sign-in is needed, explain the browser flow and ask before starting it.
4. After sign-in, check `gh auth status` again and confirm the active account before acting.

## Create or use a repository

1. Confirm the repository owner, name, and visibility with the user.
2. For a new repository, create it with `gh repo create OWNER/NAME --public` or `--private`, only as approved.
3. Clone the repository and inspect its current state before editing.

## File issues

1. Inspect the source records and group them by distinct underlying problem.
2. Deduplicate overlapping records by stable report ID before counting coverage.
3. Prepare one issue per verified problem; include its report count, cause, and a few representative IDs.
4. Show the planned issue changes to the user and obtain approval before running `gh issue create`.
5. Verify issue numbers and URLs with `gh issue list`.

## Publish changes

1. Review the staged diff and run relevant validation.
2. Ask before committing or pushing changes that have not already been approved.
3. Push only to the confirmed repository and verify the remote branch and working tree afterward.

## Close issues

Close issues only when the user or task confirms the underlying work is complete. Ask before closing them, use `gh issue close` with an accurate reason, then verify each status with `gh issue view`.
