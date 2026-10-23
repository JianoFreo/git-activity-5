# git-activity-5
# Project Nova - Git Mastery & Troubleshooting Activity

## Overview

This activity demonstrates the use of Git and GitHub for version control, repository management, branching, merging, and troubleshooting common Git errors.

## Part 1: Core Repository Management

The following tasks were performed to establish and manage the Project Nova repository.

### 1. Repository Initialization

Initialized a local Git repository and connected it to the remote GitHub repository.

```bash
git init
git branch -M main
git remote add origin <repository-url>
```

### 2. Staging and Committing

Created `auth-service.js`, staged the file, and committed it with a descriptive commit message.

```bash
git add auth-service.js
git commit -m "Added initial auth service logic."
git push -u origin main
```

### 3. Branching

Created and switched to the `feature/payment-gateway` branch to work on the payment gateway configuration separately from `main`.

```bash
git branch feature/payment-gateway
git checkout feature/payment-gateway
```

### 4. Publishing the Feature Branch

Published the feature branch to GitHub and configured it to track the remote branch.

```bash
git push --set-upstream origin feature/payment-gateway
```

### 5. Synchronization and Merge Conflict Resolution

Simulated a collaborator's changes to `config.js` on the remote `main` branch. Pulled the remote changes, inspected the repository status, manually resolved the merge conflict, and committed the resolution.

```bash
git pull origin main
git status
git add config.js
git commit -m "Resolved conflict in config.js"
git push
```

## Part 2: Git Troubleshooting

The following commands address common Git mistakes and repository emergencies.

| Scenario | Command |
|---|---|
| Unstage a sensitive file | `git restore --staged .env` |
| Correct the latest commit message | `git commit --amend -m "Fixed authentication typo"` |
| Include a forgotten file in the previous commit | `git add styles.css` then `git commit --amend --no-edit` |
| Discard uncommitted file changes | `git restore index.html` |
| Move commits to a new branch | `git branch new-feature` then `git reset HEAD~3 --hard` then `git checkout new-feature` |
| Recover a detached HEAD commit | `git switch -c recovery-branch` |
| Reverse a pushed commit | `git revert <buggy-commit-hash>` |
| Recover a deleted branch | `git reflog` then `git branch <deleted-branch-name> <commit-hash>` |
| Stage deleted files | `git add -u` |
| Delete a remote branch | `git push origin --delete testing-junk` |
