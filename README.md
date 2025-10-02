README file done in main branch


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
  user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$ git add .

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$ git stash
Saved working directory and index state WIP on (no branch): 99747f6 chore: Create initial file

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$ git stash list
stash@{0}: WIP on (no branch): 99747f6 chore: Create initial file

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$ git stash pop
HEAD detached at 99747f6
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   .vscode/settings.json
        new file:   README.md

Dropped refs/stash@{0} (4e70d99a1bdc445fe255ccf1d5735e51eaf386df)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$
```

## Branch Merging Conflicts (Continued):

```bash
 
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((99747f6...))
$ git switch main
A       .vscode/settings.json
A       README.md
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ echo "Hello from main branch" > conflict.txt

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git add conflict.txt
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git commit -m "I added a conflict.txt on main branch"
[main c396f1c] I added a conflict.txt on main branch
 3 files changed, 135 insertions(+)
 create mode 100644 .vscode/settings.json
 create mode 100644 README.md
 create mode 100644 conflict.txt

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git checkout -b ft/conflict-branch
Switched to a new branch 'ft/conflict-branch'

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/conflict-branch)
$ echo "Hello from feature branch" > conflict.txt

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/conflict-branch)
$ git add conflict.txt
warning: in the working copy of 'conflict.txt', LF will be replaced by CRLF the next time Git touches it

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/conflict-branch)
$ git commit -m "Edit conflict.txt on feature branch"
[ft/conflict-branch f7a12e6] Edit conflict.txt on feature branch
 1 file changed, 1 insertion(+), 1 deletion(-)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/conflict-branch)
$ git switch main
M       README.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git merge ft/conflict-branch
Updating c396f1c..f7a12e6
Fast-forward
 conflict.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git add conflict.txt

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git commit "."
Aborting commit due to empty commit message.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git commit "."
Aborting commit due to empty commit message.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$
```
## Resolving Merge Conflicts with a Merge Tool:

```bash
 user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
No files need merging


```

## Understanding Detached HEAD State:

```bash
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git checkout HEAD~1
M       README.md
Note: switching to 'HEAD~1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at c396f1c I added a conflict.txt on main branch

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb ((c396f1c...))
$ git switch main
M       README.md
Previous HEAD position was c396f1c I added a conflict.txt on main branch
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$
```

## Ignoring Files/Directories:

```bash
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ echo "/tmp" >> .gitignore

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git add .gitignore
warning: in the working copy of '.gitignore', LF will be replaced by CRLF the next time Git touches it

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git commit -m "Add .gitignore to exclude tmp folder"
[main 402145a] Add .gitignore to exclude tmp folder
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$
```

## Working with Tags:

```bash

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git tag v1.0

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$
```

## Listing and Deleting Tags:

```bash
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git tag
v1.0

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git tag -d v1.0
Deleted tag 'v1.0' (was 402145a)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
```

## Pushing Local Work to Remote Repositories:

```bash 
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$ git push origin ft/conflict-branch
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 16 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (9/9), 1.81 KiB | 462.00 KiB/s, done.
Total 9 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
remote:
remote: Create a pull request for 'ft/conflict-branch' on GitHub by visiting:
remote:      https://github.com/caleb-tuyisingize/git-exercises-caleb/pull/new/ft/conflict-branc 
remote:
To https://github.com/caleb-tuyisingize/git-exercises-caleb
 * [new branch]      ft/conflict-branch -> ft/conflict-branch

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (main)
$
```

## Pulling Changes from Remote Repositories:

```bash 

```
