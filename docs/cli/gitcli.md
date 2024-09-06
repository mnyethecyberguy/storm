# Git CLI

## Configuration
Configure user name and email
``` 
git config --global user.name "Your Name"
git config --global user.email "your@email"
```

Set automatic command line coloring
```
git config --global color.ui auto
```

Show the global git configuration
```
git config --global --list
```

## Repository Creation & Cloning
Initialize a new git repository
```
git init
```

Clone a remote repository to your local machine
```
git clone <url>
```

## Basic Workflow
Add changes to the staging area
```
git add <file>
git add .
```

Commit changes with a message
```
git commit -m "message"
```

Check the status of your repository
```
git status
```

Show changes between working directory and staging
```
git diff
```

Show changes staged but not yet committed
```
git diff --staged
```

Delete file from project and stage removal for commit
```
git rm <file>
```

## Remote Repositories
List all remote repositories and their URLs
```
git remote -v
```

Add a remote repository (Use SSH URLs for remotes to enhance security)
```
git remote add <name> <url>
```

Fetch changes from a remote repository
```
git fetch <remote>
```

Fetch and merge changes from a remote repository
```
git pull <remote> <branch>
```

Push changes to a remote repository
```
git push <remote> <branch>
```

Reset local repository to match remote
```
git reset --hard origin/<branch>
```

## Branching & Merging
List all branches in the repository
```
git branch
```

Create a new branch
```
git branch <branch>
```

Switch to a different branch
```
git checkout <branch>
```

Create and switch to a new branch
```
git checkout -b <branch>
```

Merge changes from one branch into another
```
git merge <branch>
```

Rebase changes interactively
```
git rebase -i <branch>
```

Squash multiple (3) commits into one
```
git rebase -i HEAD~3
```

## Undoing Changes
Discard changes in the working directory
```
git checkout -- <files>
```

Unstage changes
```
git reset HEAD <files>
```

Undo the last commit (local)
```
git reset --soft HEAD^
```

Undo the last commit and discard changes
```
git reset --hard HEAD^
```

Change the commit message of the last commit
```
git commit --amend -m "New message"
```

Revert to a previous commit
```
git revert <hash>
```

Unstage files staged for commit
```
git restore --staged <file>
```

## Tagging
Create a lightweight tag
```
git tag <tag>
```

Create an annotated tag
```
git tag -a <tag> -m "Tag message"
```

Push tags to a remote repository
```
git push <name> --tags
```

## Stashing Changes
Stash changes in the working directory
```
git stash
```

Stash changes with a custom message
```
git stash save "message"
```

List all stashes
```
git stash list
```

Apply the most recent stash without removing it
```
git stash apply
```

Apply the and remove the most recent stash
```
git stash pop
```

## Cherry-Picking
Apply changes from a specific commit
```
git cherry-pick <commit>
```

Apply changes, include a reference to original commit
```
git cherry-pick -x <commit>
```

## History & Logs
View the commit history
```
git log
```

Show concise commit history
```
git log --oneline
```

Show the commit history with references
```
git reflog
```

## Miscellaneous
Show the git version
```
git --version
```

Clean untracked files and directories
```
git clean -fdX
```

Add all and insert them in the latest commit
```
git add . && git commit --amend --no-edit
```

## Ignoring Files
Create or edit the .gitignore file
```
echo -e "*.log\nnode_modules/" > .gitignore
```