---
name: create-mr
description: Create a GitLab merge request for the current branch. Use when the user says "create MR", "open a merge request", or "create PR".
argument-hint: "[title]"
---

Create a GitLab merge request for the current branch against master.

1. Run `git branch --show-current` to get the current branch name.
2. Run `git log origin/master..HEAD --pretty=format:"%s"` to list commits in this branch.
3. Draft a short MR title and a bullet-point description based on the commits.
   - If $ARGUMENTS is provided, use it as the title.
   - Otherwise infer a concise title from the commit messages.
4. Run the following to create the MR:
   `glab mr create --target-branch master --title "<title>" --description "<description>"`
   using the remote hostname git.nosi.cv (origin remote).
5. Output the resulting MR URL to the user.
