# 📚 Git Commands Learning Guide

A comprehensive and structured list of Git commands for all levels — from setup to advanced workflows.

---

# 1. Setup and Configuration

#### Check Git version
```bash
git --version
```

#### Configure user identity globally
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

#### Set default branch name for new repositories
```bash
git config --global init.defaultBranch main
```

#### View current Git configuration
```bash
git config --list
```

---

# 2. Create or Clone a Repository

#### Initialize a new Git repo in current directory
```bash
git init
```

#### Clone an existing remote repository
```bash
git clone <repository-url>
```

---

# 3. Inspect Status and History

#### Show working tree status
```bash
git status
```

#### Show detailed commit history
```bash
git log
```

#### Show compact commit history graph with decorations
```bash
git log --oneline --graph --decorate
```

#### See changes not staged for commit
```bash
git diff
```

#### See changes staged for commit
```bash
git diff --staged
```

---

# 4. Stage and Commit Changes

#### Stage a specific file
```bash
git add <file>
```

#### Stage all changes (new, modified, deleted)
```bash
git add -A
```

#### Commit staged changes with a message
```bash
git commit -m "meaningful message"
```

#### Amend last commit with new message or staged changes
```bash
git commit --amend
```

---

# 5. Branching and Switching

#### List all local branches
```bash
git branch
```

#### Create a new branch
```bash
git branch <branch-name>
```

#### Create and switch to new branch
```bash
git checkout -b <branch-name>
```

#### Switch to an existing branch
```bash
git checkout <branch-name>
```
or (newer syntax)
```bash
git switch <branch-name>
```

#### Rename current branch
```bash
git branch -m <new-name>
```

#### Delete a local branch
```bash
git branch -d <branch-name>
```

---

# 6. Merging and Rebasing

#### Merge a branch into current branch
```bash
git merge <branch-name>
```

#### Rebase current branch onto another base branch (linear history)
```bash
git rebase <base-branch>
```

#### Abort ongoing merge
```bash
git merge --abort
```

#### Abort ongoing rebase
```bash
git rebase --abort
```

---

# 7. Stash Work-in-Progress

#### Stash uncommitted changes
```bash
git stash
```

#### List all stashed changes
```bash
git stash list
```

#### Apply latest stash and remove it from stash list
```bash
git stash pop
```

#### Apply stash but keep it in stash list
```bash
git stash apply
```

#### Clear all stashes
```bash
git stash clear
```

---

# 8. Work with Remotes

#### Add a remote repository
```bash
git remote add origin <remote-url>
```

#### Show remote URLs
```bash
git remote -v
```

#### Change remote URL
```bash
git remote set-url origin <remote-url>
```

---

# 9. Sync: Fetch, Pull, Push

#### Fetch updates from remote without merging
```bash
git fetch
```

#### Pull remote changes and merge into current branch
```bash
git pull
```

#### Push current branch commits to remote
```bash
git push
```

#### Push and set upstream tracking for the branch (first time)
```bash
git push -u origin <branch-name>
```

#### Delete remote branch
```bash
git push origin --delete <branch-name>
```

---

# 10. Reset and Restore (Undo Changes)

#### Unstage a file but keep changes
```bash
git restore --staged <file>
```

#### Discard local changes to a file (unstaged)
```bash
git restore <file>
```
Older syntax:
```bash
git checkout -- <file>
```

#### Soft reset HEAD to previous commit (keeps changes staged)
```bash
git reset --soft HEAD~1
```

#### Mixed reset to previous commit (keeps changes unstaged)
```bash
git reset HEAD~1
```

#### Hard reset to specific commit (discard changes)
```bash
git reset --hard <commit-hash>
```

#### Remove file from Git tracking but keep locally
```bash
git rm --cached <file>
```

#### Remove file from both repo and local folder
```bash
git rm <file>
```

---

# 11. Compare Changes

#### Diff working directory vs index (unstaged changes)
```bash
git diff
```

#### Diff staged changes vs last commit
```bash
git diff --cached
```

#### Diff between two branches
```bash
git diff <branchA> <branchB>
```

---

# 12. Tagging Releases

#### Create lightweight tag
```bash
git tag v1.0.0
```

#### Create annotated tag with message
```bash
git tag -a v1.0.0 -m "Release 1.0.0"
```

#### Push tags to remote
```bash
git push --tags
```

---

# 13. Advanced Tools

#### Start binary search to find bad commit
```bash
git bisect start
git bisect good <good_commit>
git bisect bad <bad_commit>
```

#### Cherry-pick a specific commit from another branch
```bash
git cherry-pick <commit-hash>
```

#### Interactive rebase to edit, squash, reorder commits
```bash
git rebase -i <commit-hash-before-first>
```

#### Clean untracked files (dry-run first)
```bash
git clean -n
```

#### Clean untracked files and directories (use with caution)
```bash
git clean -fd
```

#### Remove Git history and start fresh (dangerous)
```bash
rm -rf .git
git init
```

---

# 14. Helpful Logs and Grep

#### Compact history graph view including all branches
```bash
git log --oneline --graph --all
```

#### Search commit messages matching pattern
```bash
git log --grep "<pattern>"
```

#### Search code content across commits
```bash
git grep "<pattern>"
```

---

# 15. Common Git Workflows (Quick Recipes)

#### New feature branch workflow
```bash
git checkout -b feature/x
git add -A
git commit -m "Start feature x"
git push -u origin feature/x
```

#### Update local main branch from remote
```bash
git checkout main
git pull origin main
```

#### Sync feature branch with latest main branch
```bash
git checkout feature/x
git fetch origin
git rebase origin/main
```

#### Fix last commit message
```bash
git commit --amend -m "Better message"
```

#### Revert a specific commit (creates new revert commit)
```bash
git revert <commit-hash>
```

---

# ⚠️ Tips:

- Always pull before pushing to avoid conflicts.
- Use branches for new features and fixes.
- Use descriptive commit messages.
- Add a `.gitignore` file to exclude node_modules, logs, etc.
- Be careful with destructive commands like `reset --hard` and `push --force`.

---

Happy Git Learning! 🚀
