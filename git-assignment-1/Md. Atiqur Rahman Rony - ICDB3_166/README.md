
Generates a new SSH key pair (public and private keys) for authentication with remote repositories.

```bash
ssh-keygen
```

Tests the SSH connection to GitHub. GitHub acknowledges the connection if successful.

```bash
ssh -T git@github.com
```

---

### Git Init, Branch Rename, and Remote Add Commands

```bash
# Initialize a new Git repository in the current directory. This creates a .git folder.
git init
```

```bash
# Rename the default branch from 'master' to 'main' (this is the standard convention now).
git branch -m main
```

```bash
# Add a remote repository named 'origin' with the specified GitHub URL. This links your local repo to the remote.
git remote add origin git@github.com:atikrony/Poribesh.git
```




### Git Remote, Commit, Amend, and Rebase Commands

# 1. Checking Git Remotes
#Lists all configured remote repositories and shows details about the `origin` remote.

```bash
git remote
git remote -v
git remote show origin
```

Rewrites the last commit message. Useful when you want to modify the message or content of the last commit.

```bash
git commit --amend -m "New commit message"
```

Opens an interactive rebase to edit the last commit. Allows modification or combination of recent commits.

```bash
git rebase -i HEAD~1
```

Edits the rebase script or continues the rebase process after resolving conflicts or editing commits.

```bash
git rebase --edit-todo
git rebase --continue
```

---


### Git Clone, Add, Init, Commit, Push, and Pull Commands

```bash
# Clone the repository from GitHub to your local machine. This creates a new directory with the repo's files.
git clone git@github.com:atikrony/box.git
```

```bash
# Navigate to the cloned repository directory.
cd box
```

```bash
# Initialize a new Git repository (only if there’s no .git folder already, otherwise, this reinitializes it).
git init
```

```bash
# Stage all changes in the repository for the next commit.
git add .
```

```bash
# Commit the staged changes with a descriptive message. Here, it’s the "first commit".
git commit -m "first commit"
```

```bash
# Push the committed changes to the 'main' branch on the remote GitHub repository.
git push origin main
```

```bash
# Pull the latest changes from the 'main' branch on the remote repository.
git pull origin main
```
---



## Soft and Hard Reset, Push, and Revert
Creates new files, stages all changes, and commits them with specific messages.

```bash
touch xyz.txt
git add .
git commit -m "sec"

touch yex.txt
git add .
git commit -m "third"
```

Moves the branch pointer to a specified commit, either keeping changes staged (soft reset) or removing them entirely (hard reset).

```bash
git reset --soft <commit-hash>
git reset --hard <commit-hash>
```

Pushes changes to the remote repository forcefully, which can overwrite remote history.

```bash
git push origin main --force
```

Creates a new commit that undoes the changes introduced by a specified commit.

```bash
git revert <commit-hash>
```

---


Sets the global username and email address for Git commits.

```bash
git config --global user.name "atikrony"
git config --global user.email "atiqrony.aiub@gmail.com"
```




### Git Checkout and Cherry-Pick Commands

```bash
# Switch to the branch 'gitassignment1' to start working on it.
git checkout gitassignment1
```

```bash
# Display the commit history to identify the commit you want to cherry-pick.
git log
```

```bash
# Stage all changes in the current branch. This prepares them for committing.
git add .
```

```bash
# Attempt to cherry-pick a specific commit by its hash (replace <commit-hash> with the actual hash).
# This applies the changes from that commit onto the current branch.
git cherry-pick <commit-hash>
```

```bash
# If there's a conflict, stash your local changes temporarily to proceed with the cherry-pick.
git stash
```

```bash
# Retry the cherry-pick after stashing. This re-applies the commit from the specified hash.
git cherry-pick <commit-hash>
```

```bash
# Commit an empty commit if necessary (e.g., after resolving conflicts with no actual code changes).
git commit --allow-empty
```

```bash
# Switch back to the 'main' branch to finalize or continue other work.
git checkout main
```

```bash
# Stage all changes on the main branch.
git add .
```

```bash
# Commit the changes with a message. Here, the message is "final".
git commit -m "final"
```

---
