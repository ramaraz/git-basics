# Very commonly used git commands

Any git task begins with a status check

```
git status
```

Creating a new branch for task/bug is a two step process. 
    - Take latest
    - Then cut a branch

```
git pull origin master
git checkout -b dev
```

Once you modified the code. Make a commit.
```
git add .
git commit -m 'Good message'
```

Once commit has been made, push to origin/upstream
```
git status
git push origin master
```

To see the history of commit
```
git log --oneline
```

If your history looks like this

xxx399 WIP
xxx233 Fix
xxx222 JIRA-233 Fixed cross axis swing

then make sure you remove bad commits using git rebase

```
git rebase -i HEAD~3
```

use `squash/fixup` to remove dud commits.


To add origin ref

```
git remote add origin git@github.com:tinit-trainings/git-basics.git
```

To check remotes

```
git remote -v
```


## Errors

```
C:\Code\tinit\git-training>git push origin master
To github.com:tinit-trainings/git-basics.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:tinit-trainings/git-basics.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
Fix: do a git pull & do a push

```
C:\Code\tinit\git-training>git pull origin master
From github.com:tinit-trainings/git-basics
 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories
```

Fix `git pull origin master --allow-unrelated-histories`
