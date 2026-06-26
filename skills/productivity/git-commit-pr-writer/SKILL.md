---
name: "git-commit-pr-writer"
description: "Generates a conventional commit message (or commitlint-style), PR title, and structured PR description with business value from staged git changes or branch diff. Perfect for release-ready developer workflow."
argument-hint: "Use current repo staged changes, or specify the repo/branch/JIRA scope"
agent: "agent"
tools: [execute, read, search]
---

Review the current repository changes and generate release-ready git and PR copy.

Your job is to produce:
1. One git commit message that follows commitlint or conventional commit style
2. One PR title
3. One short PR description with business value

Use this workflow:
1. Inspect `git status --short` first.
2. Inspect `git diff --cached` next.
3. If there are no staged changes, inspect the branch diff against the default branch and clearly say that you used branch diff instead of staged diff.
4. If repository commit message style is visible from git history, align with it.
5. If no stricter repo-specific style is visible, default to conventional commit style:
   - `<type(scope)>`: short imperative rule summary
6. If a JIRA key is present in the branch name, user prompt, or recent commits, include it in the commit message and PR title when that matches the repo's existing pattern.
7. If the diff scope looks mixed, misleading, or inconsistent with the claimed task, say that before proposing the final copy.

Rules:
- Keep wording concise and specific.
- Use imperative mood in commit messages.
- Do not add a trailing period to the commit subject.
- Prefer lowercase commit types such as `fix`, `feat`, `chore`, `refactor`, `test`, or `docs`.
- Make the PR title readable for reviewers, not just a copy of the commit message.
- Include business value in the PR description.
- Mention validation commands if they are visible from the current session or repo history.
- Do not run destructive git commands.

Return the result **exactly** in this format:

## Commit message
<commit message>

## PR title
<pr title>

## PR description
**Summary**
...

**Business value**
...

**Changes**
...

**Validation**
...

**Out of scope**
...