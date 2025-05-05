General Commands
Make a directory:mkdir
Change the directory: cd "name of the directory"
Create a file: touch "file name"
See git changes: git status
Go to root in terminal: wmic
Terminal help: /?
Show the folders: ls
Show the git folders also: ls -a
Basic Git Workflow
 Taking and edit and  pushing a file to github =  github repo=>clone=>changes=>add=>comment=>push
Clone a GitHub repository:git clone "repository link" e.g., <https://github.com/BNsrujan>
Make changes to files.
Add changes to staging:
Add all files, it will add all the  untracked file or fill which we have created files git: git add .
Add a specific file: git add "file location"
Commit changes:git commit -m "comment on what you have changed"
Push changes:git push origin "branch name" (e.g., main or master)
Initializing and Pushing to a New Repository
Initialize a git repository:git init
Link to remote:git remote add origin "GitHub repository link"
Verify connection:git remote -v
Push changes:git push origin "branch name"
Shortcut for pushing to main:git push -u origin main
git push -u origin main = -u”upstream(shortcut)for origin main”
Handling Git Push Errors
Error solution 1:git pull --rebase origin master
Error solution 2:git push origin main -f
Removing Git Configurations
You cannot have two git files in the same folder
Remove git folder:rm -rf .git
Branch Commands
Create a new branch:git checkout -b "new branch name"
List all branches:git branch
Rename current branch:git branch -M "new name"
Switch branches:git checkout "branch name"
Delete a branch:git branch -d "branch name"
Merging Branches
Compare commits/branches/files: git diff " branch name which we have to compare with "  
Press q to exit git diff.
Resolving Merge Conflicts
Merge conflicts occur when Git cannot automatically resolve code differences between two commits.

Merge branches:git merge "branch name" = add the branch name which we want to merge with and resolve the error
Pull Requests
Pull request: Allows others to review and discuss changes pushed to a repository.
Fetch updates from remote:git pull origin main =used to fetch and download content from a remote repo and immediately update the local repo
Rebasing Branches
Switch to the branch to rebase:git checkout "branch name"
Rebase:git rebase "main"
Undoing Changes
Case 1: Staged but not committed
Unstage specific file:git reset "file name"
Unstage all:git reset
Case 2: Committed changes (for one commit)
Undo the last commit:git reset HEAD~1  (HEAD~1) =>latest edit
Case 3: Committed changes (multiple commits)
View commit history:git log
Press q to exit.
Reset to specific commit:git reset "commit hash"
Git Logs and History
View commit history:git log
Check commit names only:git reflog
Remote Commands
Add a remote:git remote add upstream git://github.com/some-url
Fetch updates:git fetch upstream
Rebase:git rebase upstream/master
Deleting a Branch in a Remote Repository
Delete a remote branch:git push origin --delete <branch-name>

Tracking Branches
First, I created a remote branch as an origin/feature/login
And imported the branch as a feature/login
Git branch –track feature/login origin/feature/login
Import and track remote branch:git branch --track "local-branch-name" origin/"remote-branch-name"
Or
You can also import by not naming the branch
Git checkout –trach origin/feature/login = This will create a branch in locally and connect it to a branch that is in remote (online)

It will show you where you compare to the remote branch
Forking
A fork is a new repository sharing code and visibility settings with the original repository.
Notes on Commit History
You can check differences between branches or commits using git diff.
Ahead: Indicates extra changes compared to the remote branch.
Behind: Indicates the need to pull updates from the remote branch.
It is used to change the account name of the git
Git config –global user. name “name”
Git config –global user.email “name@gmail.com”
Git rebasing branches
Git branch
Main
feature/uploader
Now to update the feature/uploader you have to switch to feature/uploader the run this command
Git branch
Main
feature/uploader
Git rebase main

Git merge
Git switch main = switching to the main branch
Git merge feature/uploader = merge the feature /uploader to the main brach
