---
title: "Git Fixup and Advanced Git Techniques"
date: 2025-12-14
categories: ["Coding", "Productivity"]
tags: ["git", "github", "productivity", "version-control"]
description: "Master advanced Git techniques including fixup commits, git absorb, worktrees, and more for a cleaner commit history"
draft: false
---

## Git Fixup: Amending Commits in a Chain

Ever made a commit, continued working, and then realized you need to fix something in an earlier commit? `git commit --fixup` is your friend.

### The Problem

You have a chain of commits:
```
A -> B -> C -> D (HEAD)
```

You realize commit B needs a small fix. Creating a new commit E would clutter history. What do you do?

### The Solution: Git Fixup

#### Step 1: Stage Your Changes
```bash
git add <files-with-fixes>
```

#### Step 2: Create a Fixup Commit
```bash
git commit --fixup <commit-hash-of-B>
```

This creates a commit with the message `fixup! <original commit message>`.

#### Step 3: Squash with Interactive Rebase
```bash
git rebase -i --autosquash <commit-before-B>
```

Git automatically reorders and marks the fixup commit for squashing. Save and close the editor, and your fix is merged into the original commit.

## Git Absorb: Automation Magic

Tired of manually finding which commit to fixup? **git-absorb** automatically figures it out!

```bash
# Install git-absorb
brew install git-absorb  # macOS

# Stage changes and run
git add .
git absorb --and-rebase
```

It analyzes your staged changes, creates fixup commits for the appropriate parent commits, and rebases automatically. Magic! ✨

## Git Worktree: Multiple Checkouts

Need to work on multiple branches simultaneously without stashing or committing WIP?

```bash
# Create a new worktree
git worktree add ../feature-branch feature-branch

# List worktrees
git worktree list

# Remove when done
git worktree remove ../feature-branch
```

Each worktree is a separate directory with its own checkout. Perfect for:
- Reviewing PRs while working on features
- Running tests on one branch while coding on another
- Comparing implementations side-by-side

## Git Path Ref: Release Branch Management

For managing release branches with selective commits:

```bash
# Cherry-pick specific commits to release branch
git checkout release/v1.0
git cherry-pick <commit-hash>

# Or use path-based references
git show main:path/to/file > file_from_main.txt
```

## Bonus: Playwright Automation

While not strictly Git, I've been using **Playwright** for browser automation in my workflows. Combined with Git hooks, you can:

- Auto-generate screenshots for documentation
- Run E2E tests before push
- Automate repetitive browser tasks

## Quick Reference

| Command | Purpose |
|---------|---------|
| `git commit --fixup <hash>` | Create fixup commit |
| `git rebase -i --autosquash` | Squash fixups |
| `git absorb` | Auto-create fixups |
| `git worktree add` | Create parallel checkout |

Master these techniques for a cleaner, more professional Git history!

