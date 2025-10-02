
# TASK 2

## Branch Deletion

```bash 
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git pull origin dev
From https://github.com/caleb-tuyisingize/git-exercises-caleb
 * branch            dev        -> FETCH_HEAD
Already up to date.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git branch -d ft/new-feature
error: the branch 'ft/new-feature' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D ft/new-feature'
hint: Disable this message with "git config set advice.forceDeleteBranch false"

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git branch -D ft/new-feature
Deleted branch ft/new-feature (was ddeedb5).

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$

```

## Create Branch from commit

```bash

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git log --oneline
c28d90a (HEAD -> dev) Updated project readme
d7cffa5 (origin/dev, ft/add-test4-file, ft/add-test2-file) initializing README file
99747f6 (origin/main, origin/HEAD) chore: Create initial file

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git checkout -b ft/new-branch-from-commit commit-hash
fatal: 'commit-hash' is not a commit and a branch 'ft/new-branch-from-commit' cannot be created from it

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git checkout -b ft/new-branch-from-commit 99747f6
Switched to a new branch 'ft/new-branch-from-commit'

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/new-branch-from-commit)
$
```

## Branch Merging

```bash 
   user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/new-branch-from-commit)
$ git switch main
branch 'main' set up to track 'origin/main'.
Switched to a new branch 'main'
Your branch is up to date with 'origin/main'.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git merge ft/new-branch-from-commit
Already up to date.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git merge ft/new-branch-from-commit
Already up to date.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$

```

## Branch Rebasing:

```bash

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git switch ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/new-branch-from-commit)
$ git rebase main
Current branch ft/new-branch-from-commit is up to date.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/new-branch-from-commit)
$

```
## Renaming Branches:

```bash 
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/improved-branch-name)
$
```

## Checking Out Detached HEAD:

```bash

  user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/improved-branch-name)
$ git checkout 99747f6
Note: switching to '99747f6'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 99747f6 chore: Create initial file

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$
```

# PART 3

## Stashing Changes:

```bash
