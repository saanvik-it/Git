# Git – Complete Beginner to Advanced Guide

## Table of Contents
1. Introduction to Git
2. Why Git?
3. Git Architecture
4. Git Workflow
5. Installing Git
6. Git Configuration
7. Git Repository Basics
8. Important Git Commands
9. Git Branching
10. Git Merging
11. Git Rebase
12. Git Stash
13. Git Tags
14. Git Remote Repositories
15. Git Internals
16. Git Hooks
17. Git Best Practices
18. Git with CI/CD
19. Git Troubleshooting
20. Git Interview Questions and Answers
21. Advanced Git Concepts
22. Git Cheat Sheet
23. Real-World Git Workflow
24. Git vs GitHub vs GitLab
25. Conclusion

---

# 1. Introduction to Git

Git is a distributed version control system (DVCS) used to:
- Track code changes
- Collaborate with teams
- Maintain version history
- Manage source code efficiently

Git was created by:
- Linus Torvalds (creator of Linux)

---

# 2. Why Git?

Without Git:
- Code overwrites happen
- Difficult collaboration
- No rollback mechanism
- No history tracking

Git solves:
- Version management
- Team collaboration
- Branching
- Rollbacks
- Change tracking

---

# 3. Git Architecture

## Git Distributed Architecture

```text
+------------------+
| Working Directory|
+------------------+
          |
          v
+------------------+
| Staging Area     |
| (Index)          |
+------------------+
          |
          v
+------------------+
| Local Repository |
+------------------+
          |
          v
+------------------+
| Remote Repository|
| (GitHub/GitLab)  |
+------------------+
```

---

# 4. Git Workflow

```text
Create/Modify Files
        ↓
git add
        ↓
git commit
        ↓
git push
        ↓
Remote Repository
```

---

# 5. Installing Git

## Linux

```bash
sudo apt install git
```

---

## Mac

```bash
brew install git
```

---

## Windows

Download from:
- https://git-scm.com

---

# 6. Git Configuration

## Configure Username

```bash
git config --global user.name "John Doe"
```

---

## Configure Email

```bash
git config --global user.email "john@example.com"
```

---

## Verify Configuration

```bash
git config --list
```

---

## Set Default Editor

```bash
git config --global core.editor vim
```

---

# 7. Git Repository Basics

## Initialize Repository

```bash
git init
```

---

## Clone Repository

```bash
git clone https://github.com/user/repo.git
```

---

## Check Status

```bash
git status
```

---

## Add Files

```bash
git add file.txt
```

Add all files:

```bash
git add .
```

---

## Commit Changes

```bash
git commit -m "Initial commit"
```

---

## View Commit History

```bash
git log
```

Compact view:

```bash
git log --oneline
```

---

# 8. Important Git Commands

## Push Changes

```bash
git push origin main
```

---

## Pull Changes

```bash
git pull origin main
```

---

## Fetch Changes

```bash
git fetch
```

---

## Compare Changes

```bash
git diff
```

---

## Show Branches

```bash
git branch
```

---

## Create Branch

```bash
git branch feature-login
```

---

## Switch Branch

```bash
git checkout feature-login
```

OR

```bash
git switch feature-login
```

---

## Create and Switch Branch

```bash
git checkout -b feature-login
```

OR

```bash
git switch -c feature-login
```

---

## Delete Branch

```bash
git branch -d feature-login
```

Force delete:

```bash
git branch -D feature-login
```

---

# 9. Git Branching

Branching allows isolated development.

---

## Example Workflow

```text
main
 ├── feature-login
 ├── feature-payment
 └── bugfix-auth
```

---

## Best Practice

- Never work directly on main/master
- Use feature branches

---

# 10. Git Merging

## Merge Branch

```bash
git merge feature-login
```

---

## Fast Forward Merge

Occurs when no divergence exists.

---

## Merge Conflict

Happens when:
- Same lines modified in multiple branches

---

## Resolve Conflict

```text
<<<<<<< HEAD
Current code
=======
Incoming code
>>>>>>> feature-branch
```

Steps:
1. Edit file
2. Remove markers
3. Commit changes

---

# 11. Git Rebase

Rebase rewrites commit history.

---

## Example

```bash
git rebase main
```

---

## Difference Between Merge and Rebase

| Merge | Rebase |
|---|---|
| Preserves history | Rewrites history |
| Creates merge commit | Cleaner history |

---

## Interactive Rebase

```bash
git rebase -i HEAD~5
```

Used for:
- Squashing commits
- Renaming commits
- Reordering commits

---

# 12. Git Stash

Temporarily saves uncommitted changes.

---

## Stash Changes

```bash
git stash
```

---

## List Stashes

```bash
git stash list
```

---

## Apply Stash

```bash
git stash apply
```

---

## Remove Stash

```bash
git stash drop
```

---

# 13. Git Tags

Used for releases/versioning.

---

## Create Tag

```bash
git tag v1.0
```

---

## Annotated Tag

```bash
git tag -a v1.0 -m "Release version 1.0"
```

---

## Push Tags

```bash
git push origin --tags
```

---

# 14. Git Remote Repositories

## Add Remote

```bash
git remote add origin https://github.com/user/repo.git
```

---

## View Remotes

```bash
git remote -v
```

---

## Remove Remote

```bash
git remote remove origin
```

---

# 15. Git Internals

Git stores data as:
- Blobs
- Trees
- Commits
- Tags

---

## Git Object Model

```text
Commit
  ↓
Tree
  ↓
Blob
```

---

# 16. Git Hooks

Scripts triggered by Git events.

---

## Examples

- pre-commit
- post-commit
- pre-push
- post-merge

---

## Hook Location

```text
.git/hooks/
```

---

# 17. Git Best Practices

## Recommended Practices

### 1. Commit Frequently

Small meaningful commits.

---

### 2. Use Meaningful Commit Messages

Good:

```text
Fix login authentication bug
```

Bad:

```text
changes
```

---

### 3. Pull Before Push

```bash
git pull
```

---

### 4. Protect Main Branch

Use PR approvals.

---

### 5. Use .gitignore

Ignore:
- Logs
- Secrets
- Build files

---

# 18. Git with CI/CD

Git integrates with:
- Jenkins
- GitHub Actions
- GitLab CI
- Azure DevOps

---

## CI/CD Workflow

```text
Developer Push
      ↓
Git Repository
      ↓
Pipeline Trigger
      ↓
Build/Test/Deploy
```

---

# 19. Git Troubleshooting

## Undo Last Commit

Keep changes:

```bash
git reset --soft HEAD~1
```

Remove changes:

```bash
git reset --hard HEAD~1
```

---

## Remove File from Git

```bash
git rm file.txt
```

---

## Restore Deleted File

```bash
git checkout -- file.txt
```

---

## Rename Branch

```bash
git branch -m new-branch-name
```

---

# 20. Git Interview Questions and Answers

---

## Q1. What is Git?

Git is a distributed version control system used for source code management.

---

## Q2. Difference between Git and GitHub?

| Git | GitHub |
|---|---|
| Version control tool | Hosting platform |
| Local system | Cloud platform |

---

## Q3. What is git add?

Moves changes to staging area.

---

## Q4. Difference between git fetch and git pull?

| Fetch | Pull |
|---|---|
| Downloads changes | Downloads + merges |

---

## Q5. What is HEAD in Git?

HEAD points to current branch/commit.

---

## Q6. Difference between merge and rebase?

Merge preserves history while rebase rewrites history.

---

## Q7. What is a merge conflict?

Occurs when same lines are modified in multiple branches.

---

## Q8. What is git stash?

Temporarily stores uncommitted changes.

---

## Q9. What is cherry-pick?

Apply specific commit to another branch.

```bash
git cherry-pick <commit-id>
```

---

## Q10. What is detached HEAD?

HEAD pointing directly to commit instead of branch.

---

## Q11. What is .gitignore?

Defines files ignored by Git.

---

## Q12. Difference between local and remote repository?

| Local | Remote |
|---|---|
| On developer machine | Hosted server |

---

## Q13. What is git reset?

Moves branch pointer backward.

---

## Q14. What is git revert?

Creates new commit to undo changes.

---

## Q15. What are Git hooks?

Scripts triggered automatically by Git events.

---

# 21. Advanced Git Concepts

## Cherry Pick

```bash
git cherry-pick <commit-id>
```

---

## Bisect

Used to identify problematic commits.

```bash
git bisect start
```

---

## Reflog

Shows reference logs.

```bash
git reflog
```

---

## Squash Commits

```bash
git rebase -i HEAD~5
```

---

## Submodules

Embed repositories inside repositories.

```bash
git submodule add <repo-url>
```

---

# 22. Git Cheat Sheet

## Most Used Commands

```bash
git init
git clone
git status
git add .
git commit -m "msg"
git push
git pull
git fetch
git branch
git checkout
git switch
git merge
git rebase
git stash
git log
git diff
git tag
git reset
git revert
```

---

# 23. Real-World Git Workflow

## Feature Branch Workflow

```text
main
  ↓
feature branch
  ↓
Pull Request
  ↓
Code Review
  ↓
Merge to main
```

---

## GitFlow Model

Branches:
- main
- develop
- feature/*
- release/*
- hotfix/*

---

# 24. Git vs GitHub vs GitLab

| Tool | Purpose |
|---|---|
| Git | Version control |
| GitHub | Git hosting platform |
| GitLab | Git hosting + DevOps |

---

# 25. Common Git Commands by Scenario

---

## Start New Project

```bash
git init
git add .
git commit -m "Initial commit"
```

---

## Work on New Feature

```bash
git checkout -b feature-login
```

---

## Save Changes

```bash
git add .
git commit -m "Added login API"
```

---

## Push Changes

```bash
git push origin feature-login
```

---

## Update Local Branch

```bash
git pull origin main
```

---

## Resolve Merge Conflict

```bash
git status
```

Edit files manually then:

```bash
git add .
git commit
```

---

# 26. Important Files in Git

## .gitignore

Example:

```text
node_modules/
*.log
.env
dist/
```

---

## .git/config

Repository-specific configuration.

---

# 27. Git Security Best Practices

- Never commit secrets
- Use SSH keys
- Enable branch protection
- Use signed commits
- Scan repositories regularly

---

# 28. SSH Authentication with Git

## Generate SSH Key

```bash
ssh-keygen -t rsa -b 4096
```

---

## Add Key to SSH Agent

```bash
ssh-add ~/.ssh/id_rsa
```

---

## Test Connection

```bash
ssh -T git@github.com
```

---

# 29. GitHub Pull Request Workflow

```text
Developer
   ↓
Feature Branch
   ↓
Push Changes
   ↓
Create Pull Request
   ↓
Code Review
   ↓
Merge
```

---

# 30. Common Git Errors

## Permission Denied (publickey)

Fix:
- Add SSH key to GitHub

---

## Merge Conflict

Fix:
- Resolve manually
- Commit again

---

## Non-fast-forward Error

Fix:

```bash
git pull origin main
```

Then push again.

---

# 31. Git Architecture Summary

```text
Working Directory
        ↓
Staging Area
        ↓
Local Repository
        ↓
Remote Repository
```

---

# Conclusion

Git is one of the most essential tools for:
- DevOps Engineers
- Developers
- Cloud Engineers
- SREs
- Platform Engineers

Mastering Git helps with:
- Collaboration
- Code management
- CI/CD
- Release management
- Faster recovery
- Better development workflows

Strong Git knowledge is mandatory for modern software engineering and DevOps practices.

---
