# Git and Terminal Command Reference

## General Commands

- **Make a directory:** `mkdir`
- **Change the directory:** `cd "name of the directory"`
- **Create a file:** `touch "file name"`
- **See git changes:** `git status`
- **Go to root in terminal:** `wmic`
- **Terminal help:** `/?`
- **Show the folders:** `ls`
- **Show the git folders also:** `ls -a`

---

## Basic Git Workflow

Taking and edit and pushing a file to github = github repo => clone => changes => add => comment => push

1. Clone a GitHub repository: `git clone "repository link" e.g., <https://github.com/BNsrujan>`
2. Make changes to files.
3. Add changes to staging:
    - Add all files, it will add all the untracked file or fill which we have created files git: `git add .`
    - Add a specific file: `git add "file location"`
4. Commit changes: `git commit -m "comment on what you have changed"`
5. Push changes: `git push origin "branch name"` (e.g., main or master)

---

## Initializing and Pushing to a New Repository

1. Initialize a git repository: `git init`
2. Link to remote: `git remote add origin "GitHub repository link"`
3. Verify connection: `git remote -v`
4. Push changes: `git push origin "branch name"`
5. Shortcut for pushing to `main`: `git push -u origin main`
6. `git push -u origin main` = `-u` “upstream (shortcut) for origin main”

---

## Handling Git Push Errors

- **Error solution 1:** `git pull --rebase origin master`
- **Error solution 2:** `git push origin main -f`

---

## Removing Git Configurations

- You cannot have two git files in the same folder
- **Remove git folder:** `rm -rf .git`

---

## Branch Commands

- **Create a new branch:** `git checkout -b "new branch name"`
- **List all branches:** `git branch`
- **Rename current branch:** `git branch -M "new name"`
- **Switch branches:** `git checkout "branch name"`
- **Delete a branch:** `git branch -d "branch name"`

---

## Merging Branches

1. Compare commits/branches/files: `git diff "branch name which we have to compare with"`  
    - Press `q` to exit `git diff`.

---

## Resolving Merge Conflicts

- Merge conflicts occur when Git cannot automatically resolve code differences between two commits.

[Merge Conflict Example Image Placeholder]

1. Merge branches: `git merge "branch name"` = add the branch name which we want to merge with and resolve the error

---

## Pull Requests

- **Pull request:** Allows others to review and discuss changes pushed to a repository.
- **Fetch updates from remote:** `git pull origin main` = used to fetch and download content from a remote repo and immediately update the local repo

---

## Rebasing Branches

1. Switch to the branch to rebase: `git checkout "branch name"`
2. Rebase: `git rebase "main"`

---

## Undoing Changes

### Case 1: Staged but not committed

- Unstage specific file: `git reset "file name"`
- Unstage all: `git reset`

### Case 2: Committed changes (for one commit)

- Undo the last commit: `git reset HEAD~1`  (HEAD~1) => latest edit

### Case 3: Committed changes (multiple commits)

1. View commit history: `git log`
    - Press `q` to exit.
2. Reset to specific commit: `git reset "commit hash"`

---

## Git Logs and History

- View commit history: `git log`
- Check commit names only: `git reflog`

---

## Remote Commands

- Add a remote: `git remote add upstream git://github.com/some-url`
- Fetch updates: `git fetch upstream`
- Rebase: `git rebase upstream/master`

---

## Deleting a Branch in a Remote Repository

- Delete a remote branch: `git push origin --delete <branch-name>`

[Delete Remote Branch Image Placeholder]

---

## Tracking Branches

First, I created a remote branch as an `origin/feature/login`  
And imported the branch as `feature/login`

```bash
git branch --track feature/login origin/feature/login
