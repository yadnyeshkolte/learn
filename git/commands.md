---
layout: default
title: Git Commands
parent: Git
nav_order: 1
---

# Git Commands

| NO. | Git Commands | Description |
| --- | ------------ | ----------- |
| 1 | `git init` | Initialize git in current folder |
| 2 | `git status` | Show status of current git repository |
| 3 | `git add .` | All files will go in staging |
| 4 | `git add names.txt` | Names.txt will go in staging |
| 5 | `git commit -m "message"` | Commit all files in git repository |
| 6 | `git restore --staged names.txt` | Remove from staging |
| 7 | `git log` | History of git commits |
| 8 | `git reset ffffjfjfddtfkgf` | History of the commit will modify as our will, and all the files changes will go in staged area |
| 9 | `git stash` | Back stage concept after staging, like changes are made but it will not show in commit logs |
| 10 | `git stash pop` | Bring back files from stash area to staging |
| 11 | `git stash clear` | Files and history deleted that was in stash area (Dangerous) |
| 12 | `cat names.txt` | Shows available things in names.txt |
| 13 | `git remote add origin #url` | Connect the online repository to folder |
| 14 | `git remote -v` | Show the connected url to the given folder |
| 15 | `git push origin main` | Push the files in main repository |
| 16 | `git checkout branch1` | Head of workflow will be selected as branch1 |
| 17 | `git branch branch1` | Create branch1 |
| 18 | `git merge branch1` | Merge branch code to main code |
| 19 | `git clone #url` | Able to download forked project local folder |
| 20 | `git remote add upstream #url` | Original project url to local project folder |
| 21 | `git push origin branch1 -f` | Force push |
| 22 | `git fetch --all --prune` | Fetching to forked repository |
| 23 | `git reset --hard upstream/main` | Fetching to origin repository |
| 24 | `git push origin main` | Fetching to forked repository |
| 25 | `git pull upstream main` | Steps 29-30 in single step |
| 26 | `git rebase -i ilafhkluhlhvna` | Merge commits pick and squash |
| 27 | `git branch -a` | Shows list of branches in project |
| 28 | `git branch --delete branch1` | Will delete branch1 |
| 29 | `git branch -m branch1 branch2` | Rename the branch |
| 30 | `git rm -r --cached files` | Remove the file from staging area |
| 31 | `git push -f origin <branch_name>` | Force push the branch to GitHub |
| 40 | `rm -rf files` | Delete files permanently |
| 41 | `git rm --cached gradle.properties` | Stop the tracking of this file |
| 42 | `git commit -m "Stop tracking gradle.properties"` | Commit after removing tracking of the file |
| 43 | `git config --list` | Displays all Git configuration settings |
