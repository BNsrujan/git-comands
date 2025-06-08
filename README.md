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
6. `git push -u origin main` = `-u` "upstream (shortcut) for origin main"

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

![image](https://github.com/user-attachments/assets/6e8b7017-9db5-46cc-9ac3-dfc2c740e17d)


1. Merge branches: `git merge "branch name"` = add the branch name which we want to merge with and resolve the error

---

## Pull Requests

- **Pull request:** Allows others to review and discuss changes pushed to a repository.
- **Fetch updates from remote:** `git pull origin main` = used to fetch and download content from a remote repo and immediately update the local repo

---

## Rebasing Branches

1. Switch to the branch to rebase: `git checkout "branch name"`
2. Rebase: `git rebase "main"`

![image](https://github.com/user-attachments/assets/7ae0ecbb-9f4a-4a9c-ac14-baa0a90f9941)

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

![image](https://github.com/user-attachments/assets/5b21228c-0636-4b27-aeeb-944cf76ad155)

---

## Deleting a Branch in a Remote Repository

- Delete a remote branch: `git push origin --delete <branch-name>`

---

## Tracking Branches

First, I created a remote branch as an `origin/feature/login`  
And imported the branch as `feature/login`

```bash
git branch --track feature/login origin/feature/login

```
![image](https://github.com/user-attachments/assets/cb871300-3a87-42e4-a57b-cff1a6429ef7)

## Git tags
git tag v1.0
git push origin v1.0

## Git Tags

Git tags are used to mark specific points in your repository's history as being important, typically for version releases.

- **Create a tag:** `git tag v1.0`
- **Push a tag to remote:** `git push origin v1.0`
- **List all tags:** `git tag`
- **Delete a tag:** `git tag -d v1.0`
- **Delete remote tag:** `git push origin --delete v1.0`

---

## Forking Repositories

A fork is a copy of a repository that allows you to freely experiment with changes without affecting the original project.

1. **Create a fork:**
   - Click the "Fork" button on the GitHub repository page
   - This creates your own copy of the repository

2. **Keep your fork updated:**
   
```bash
   # Add the original repository as upstream
   git remote add upstream <original-repo-url>
   
   # Fetch changes from upstream
   git fetch upstream
   
   # Merge upstream changes into your local branch
   git merge upstream/main
```

3. **Submit changes:**
   - Make changes in your fork
   - Create a pull request to the original repository

---

## Git Configuration

Essential Git configuration commands for setting up your environment:

- **Set your name:** `git config --global user.name "Your Name"`
- **Set your email:** `git config --global user.email "your.email@example.com"`
- **View your configuration:** `git config --list`
- **Set default editor:** `git config --global core.editor "vim"`

---

## Git Stash

Git stash temporarily saves your uncommitted changes:

- **Save changes:** `git stash save "message"`
- **List stashes:** `git stash list`
- **Apply latest stash:** `git stash apply`
- **Apply specific stash:** `git stash apply stash@{n}`
- **Drop a stash:** `git stash drop stash@{n}`
- **Clear all stashes:** `git stash clear`

---

## Git Ignore

The `.gitignore` file tells Git which files to ignore:

1. **Create .gitignore:**
   ```bash
   touch .gitignore
   ```

2. **Common patterns to ignore:**
   ```
   # Dependencies
   node_modules/
   vendor/

   # Environment files
   .env
   .env.local

   # Build outputs
   dist/
   build/

   # IDE files
   .idea/
   .vscode/
   *.swp

   # OS files
   .DS_Store
   Thumbs.db
   ```

---


