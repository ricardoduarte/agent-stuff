---
name: create-pr
description: Create a GitHub pull request for the current branch. Use when the user says "create PR", "open a pull request", or "create a pull request".
argument-hint: "[title]"
---

Create a GitHub pull request for the current branch against the main branch.

1. Run `git branch --show-current` to get the current branch name.
2. Run `git log origin/master..HEAD --pretty=format:"%s" 2>/dev/null || git log origin/main..HEAD --pretty=format:"%s"` to list commits in this branch.
3. Draft a short PR title and a bullet-point description based on the commits.
   - If $ARGUMENTS is provided, use it as the title.
   - Otherwise infer a concise title from the commit messages.
4. Run the following to create the PR:
   `gh pr create --title "<title>" --body "<description>"`
5. Output the resulting PR URL to the user.
