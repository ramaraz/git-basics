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