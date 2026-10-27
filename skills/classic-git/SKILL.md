---
name: classic-git
description: Git commit message format, branch naming, and when commits are allowed. Use when writing commit messages, creating branches, or making commits.
---

# Classic Git

## Commit Messages

- Write in English.
- Use the Conventional Commits format, `<type>: <subject>`.
- Use only these types:
  - `feat`: a new feature, or a small change that does not affect existing functionality.
  - `fix`: a bug fix.
  - `refactor`: a code change that does not alter behavior.
  - `test`: a change to test code only.
  - `chore`: maintenance work that does not change behavior.
  - `docs`: a documentation change.
  - `style`: code formatting only, not UI style.
  - `revert`: reverts an earlier commit.
- The body is optional. State only the core, significant change; do not describe the details.

## Branch Names

A feature branch name is a prefix, a date, a short description, and an author suffix:

```text
feature/<date>-<description>-<author>
```

The date uses `yymmdd`. The description is a short English phrase with words joined by underscores. The suffix identifies the branch owner.

For example, `feature/261025-add_feature-alice`.

Other allowed branches:

```text
main
develop
release/<version>
hotfix/<version>
bugfix/<version>
```

## Commit Permissions

- Do not create commits by default. Commit only when the current turn explicitly allows it, and that permission applies to that turn alone.
- Amending the latest commit does not need permission. Never amend a commit that has been pushed.
- Do not add the agent itself as `Co-authored-by` in the commit message.
