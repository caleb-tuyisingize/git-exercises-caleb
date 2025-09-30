
# PART 1 OF EXERCISES
```bash
user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (dev)
$ git pull origin dev
From https://github.com/caleb-tuyisingize/git-exercises-caleb
 * branch            dev        -> FETCH_HEAD
Already up to date.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (dev)
$ git checkout -b ft/test-files
Switched to a new branch 'ft/test-files'

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ touch test2.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git add .

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git commit -m "chore: Create another file"
[ft/test-files 9554fb8] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git push origin ft/test-files
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 264 bytes | 264.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'ft/test-files' on GitHub by visiting:
remote:      https://github.com/caleb-tuyisingize/git-exercises-caleb/pull/new/ft/test-files     
remote:
To https://github.com/caleb-tuyisingize/git-exercises-caleb
 * [new branch]      ft/test-files -> ft/test-files

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ touch test3.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git add test3.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git commit -m "chore: Create third file"
[ft/test-files 2a18bde] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git push origin ft/test-files
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 268 bytes | 268.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/caleb-tuyisingize/git-exercises-caleb
   9554fb8..2a18bde  ft/test-files -> ft/test-files

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ touch test4.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git add test4.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git commit -m "chore: Create fourth file"
[ft/test-files 520434d] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git push origin ft/test-files
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 262 bytes | 262.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/caleb-tuyisingize/git-exercises-caleb
   2a18bde..520434d  ft/test-files -> ft/test-files


user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git rebase -i HEAD~4
[detached HEAD ce08efc] chore: Add and update test files
 Date: Mon Sep 29 22:27:59 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/ft/test-files.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git log --oneline
ce08efc (HEAD -> ft/test-files) chore: Add and update test files
9554fb8 chore: Create another file
99747f6 (origin/main, origin/HEAD) chore: Create initial file

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git push origin ft/test-files --force-with-lease
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 284 bytes | 284.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/caleb-tuyisingize/git-exercises-caleb
 + b4faf50...ce08efc ft/test-files -> ft/test-files (forced update)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git reset HEAD~1

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git add test3.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git commit -m "chore: Create third file"
[ft/test-files ec8b435] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git add test4.md

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git commit -m "chore: Create fourth file"
[ft/test-files b83bdb0] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md


 # This is a combination of 2 commits.




# This is the commit message #2:

chore: Create third and fourth files

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Tue Sep 30 14:36:27 2025 +0200
#
# interactive rebase in progress; onto 9554fb8
# Last commands done (2 commands done):
#    pick ec8b435 # chore: Create third file
#    squash b83bdb0 # chore: Create fourth file
# No commands remaining.
# You are currently rebasing branch 'ft/test-files' on '9554fb8'.
#
# Changes to be committed:

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git rebase -i HEAD~2
[detached HEAD d14f261] chore: Create third and fourth files
 Date: Tue Sep 30 14:36:27 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/ft/test-files.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$

Successfully rebased and updated refs/heads/ft/test-files.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ echo "test" > unwanted.txt

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the next time Git touches it

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git commit -m "Unwanted commit"
[ft/test-files 35bd1e2] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/ft/test-files.

user@LAPTOP-Q6O9PDFL MINGW64 /c/gymer/git-exercises-caleb (ft/test-files)
$



```