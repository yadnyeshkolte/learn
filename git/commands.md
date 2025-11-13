---
layout: default
title: Git Commands
parent: Git
nav_order: 1
---

# Git Commands

| NO. | Git Commands | Description |
| --- | ------------ | ----------- |
| 1 | `cd Desktop` | Move to the desktop folder |
| 2 | `cd -` | Move back to first location |
| 3 | `cd ~` | Move back to home directory |
| 4 | `ls Desktop` | List all folders and files in Desktop Folder |
| 5 | `ls -a` | Show hidden file in current folder |
| 6 | `touch names.txt` | Create file in current active location |
| 7 | `rm -rf names.txt` | Names.txt file is deleted |
| 8 | `mkdir project` | Create project folder in active location |
| 9 | `git init` | Initialize git in current folder |
| 10 | `git status` | Show status of current git repository |
| 11 | `git add .` | All files will go in staging |
| 12 | `git add names.txt` | Names.txt will go in staging |
| 13 | `git commit -m "message"` | Commit all files in git repository |
| 14 | `git restore --staged names.txt` | Remove from staging |
| 15 | `git log` | History of git commits |
| 16 | `git reset ffffjfjfddtfkgf` | History of the commit will modify as our will, and all the files changes will go in staged area |
| 17 | `git stash` | Back stage concept after staging, like changes are made but it will not show in commit logs |
| 18 | `git stash pop` | Bring back files from stash area to staging |
| 19 | `git stash clear` | Files and history deleted that was in stash area (Dangerous) |
| 20 | `cat names.txt` | Shows available things in names.txt |
| 21 | `git remote add origin #url` | Connect the online repository to folder |
| 22 | `git remote -v` | Show the connected url to the given folder |
| 23 | `git push origin main` | Push the files in main repository |
| 24 | `git checkout branch1` | Head of workflow will be selected as branch1 |
| 25 | `git branch branch1` | Create branch1 |
| 26 | `git merge branch1` | Merge branch code to main code |
| 27 | `git clone #url` | Able to download forked project local folder |
| 28 | `git remote add upstream #url` | Original project url to local project folder |
| 29 | `git push origin branch1 -f` | Force push |
| 30 | `git fetch --all --prune` | Fetching to forked repository |
| 31 | `git reset --hard upstream/main` | Fetching to origin repository |
| 32 | `git push origin main` | Fetching to forked repository |
| 33 | `git pull upstream main` | Steps 29-30 in single step |
| 34 | `git rebase -i ilafhkluhlhvna` | Merge commits pick and squash |
| 35 | `git branch -a` | Shows list of branches in project |
| 36 | `git branch --delete branch1` | Will delete branch1 |
| 37 | `git branch -m branch1 branch2` | Rename the branch |
| 38 | `git rm -r --cached files` | Remove the file from staging area |
| 39 | `git push -f origin <branch_name>` | Force push the branch to GitHub |
| 40 | `rm -rf files` | Delete files permanently |
| 41 | `git rm --cached gradle.properties` | Stop the tracking of this file |
| 42 | `git commit -m "Stop tracking gradle.properties"` | Commit after removing tracking of the file |
