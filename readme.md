This project demonstrates advanced Git operations and exercises.
 

 part 1

 # Git Exercise Session

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git
$ git clone https://github.com/samuel-ishimwe203/Git-exercise.git
Cloning into 'Git-exercise'...
warning: You appear to have cloned an empty repository.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git
$ cd 'c:/Users/user/Desktop/git/Git-exercise'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git checkout -b dev
Switched to a new branch 'dev'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ touch test{1..4}.md

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git add test1.md
git commit -m "chore: Create initial file"

git add test2.md
git commit -m "chore: Create another file"

git add test3.md
git commit -m "chore: Create third and fourth files"

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git add test4.md
$ git commit --amend -m "chore: Create third and fourth files"

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git log --oneline
0d48548 (HEAD -> dev) chore: Create third and fourth files
bc6bae1 chore: Create another file
6bcf477 chore: Create initial file

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/dev.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git rebase --continue
fatal: no rebase in progress

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git log --oneline
0d48548 (HEAD -> dev) chore: Create third and fourth files
bc6bae1 chore: Create another file
6bcf477 chore: Create initial file

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/branch)
$ echo "This is test 5" > test5.md
git add test5.md
git commit -m "Implemented test 5"

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/branch)
$ git checkout dev
Switched to branch 'dev'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git push origin dev

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git checkout ft/branch
Switched to branch 'ft/branch'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/branch)
$ git checkout -b main
Switched to a new branch 'main'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git cherry-pick 2144430
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

You are currently cherry-picking commit 2144430.
(all conflicts fixed: run "git cherry-pick --continue")
(use "git cherry-pick --skip" to skip this patch)
(use "git cherry-pick --abort" to cancel the cherry-pick operation)

Untracked files:
(use "git add <file>..." to include in what will be committed)
        test2.md

nothing added to commit but untracked files present (use "git add" to track)
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:
    git commit --allow-empty
Otherwise, please use 'git cherry-pick --skip'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main|CHERRY-PICKING)
$ git log --oneline --graph --all --decorate
* 2144430 (HEAD -> main, ft/branch) Implemented test 5
* c7ba922 (origin/dev, dev) chore: Create initial file
* b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main|CHERRY-PICKING)
$ git reflog
2144430 (HEAD -> main, ft/branch) HEAD@{0}: checkout: moving from main to main
2144430 (HEAD -> main, ft/branch) HEAD@{1}: checkout: moving from ft/branch to main
2144430 (HEAD -> main, ft/branch) HEAD@{2}: checkout: moving from dev to ft/branch
c7ba922 (origin/dev, dev) HEAD@{3}: checkout: moving from ft/branch to dev
2144430 (HEAD -> main, ft/branch) HEAD@{4}: commit: Implemented test 5
c7ba922 (origin/dev, dev) HEAD@{5}: checkout: moving from dev to ft/branch
c7ba922 (origin/dev, dev) HEAD@{6}: rebase (finish): returning to refs/heads/dev
c7ba922 (origin/dev, dev) HEAD@{7}: rebase: fast-forward
b1f535b HEAD@{8}: rebase: fast-forward
0545ffa HEAD@{9}: rebase (start): checkout 0545ffaa1d8231182c53e86854f22fdfa7d57029
c7ba922 (origin/dev, dev) HEAD@{10}: rebase (finish): returning to refs/heads/dev

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main|CHERRY-PICKING)
$ git push origin main

 part 2
...bash
user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git
$ cd 'c:/Users/user/Desktop/git/Git-exercise'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git reflog
93a2e9f (HEAD -> dev, origin/dev) HEAD@{0}: commit: readme file added
c7ba922 HEAD@{1}: checkout: moving from main to dev
2144430 (origin/main, main, ft/new-feature, ft/branch) HEAD@{2}: checkout: moving from ft/new-feature to main
2144430 (origin/main, main, ft/new-feature, ft/branch) HEAD@{3}: checkout: moving from main to ft/new-feature
2144430 (origin/main, main, ft/new-feature, ft/branch) HEAD@{4}: checkout: moving from main to main
2144430 (origin/main, main, ft/new-feature, ft/branch) HEAD@{5}: checkout: moving from ft/branch to main
2144430 (origin/main, main, ft/new-feature, ft/branch) HEAD@{6}: checkout: moving from dev to ft/branch
c7ba922 HEAD@{7}: checkout: moving from ft/branch to dev
2144430 (origin/main, main, ft/new-feature, ft/branch) HEAD@{8}: commit: Implemented test 5
c7ba922 HEAD@{9}: checkout: moving from dev to ft/branch
c7ba922 HEAD@{10}: rebase (finish): returning to refs/heads/dev

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git checkout  ft/new-feature
Switched to branch 'ft/new-feature'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-feature)
$ git add feature.txt
fatal: pathspec 'feature.txt' did not match any files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-feature)
$ echo "This is the core functionality for the new feature." > feature.txt

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-feature)
$ git add feature.txt
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the next time Git touches it

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-feature)
$ git commit -m "Implemented core functionality for new feature"
[ft/new-feature 2991611] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ echo "This project demonstrates advanced Git operations and exercises." > readme.txt

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git add readme.txt
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git commit -m "Updated project readme"
[main ad24764] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git log --oneline
ad24764 (HEAD -> main) Updated project readme
2144430 (origin/main, ft/branch) Implemented test 5
c7ba922 chore: Create initial file
b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git branch
  dev
  ft/branch
  ft/new-feature
* main

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git push origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 350 bytes | 175.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/samuel-ishimwe203/Git-exercise/pull/new/ft/new-feature
remote:
To https://github.com/samuel-ishimwe203/Git-exercise.git
 * [new branch]      ft/new-feature -> ft/new-feature

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git checkout main
Already on 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git branch -d ft/new-feature
error: the branch 'ft/new-feature' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D ft/new-feature'
hint: Disable this message with "git config advice.forceDeleteBranch false"

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git push -u origin ft/new-feature
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.
Everything up-to-date

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git fetch

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git pull
Already up to date.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git branch -d ft/new-feature
warning: deleting branch 'ft/new-feature' that has been merged to
         'refs/remotes/origin/ft/new-feature', but not yet merged to HEAD
Deleted branch ft/new-feature (was 2991611).

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git push origin --delete ft/new-feature
To https://github.com/samuel-ishimwe203/Git-exercise.git
 - [deleted]         ft/new-feature

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git log --oneline
ad24764 (HEAD -> main) Updated project readme
2144430 (origin/main, ft/branch) Implemented test 5
c7ba922 chore: Create initial file
b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git checkout -b ft/new-branch-from-commit h7i8j9k
fatal: 'h7i8j9k' is not a commit and a branch 'ft/new-branch-from-commit' cannot be created from it

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git checkout -b ft/new-branch-from-commit c7ba922
Switched to a new branch 'ft/new-branch-from-commit'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git log --oneline --decorate --graph
* c7ba922 (HEAD -> ft/new-branch-from-commit) chore: Create initial file
* b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git merge ft/new-branch-from-commit
Already up to date.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git log --oneline --graph --decorate
* c7ba922 (HEAD -> ft/new-branch-from-commit) chore: Create initial file
* b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git checkout ft/new-branch-from-commit
Already on 'ft/new-branch-from-commit'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git rebase --continue
fatal: no rebase in progress

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git rebase --abort
fatal: no rebase in progress

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git log --oneline --graph --decorate
* ad24764 (HEAD -> ft/new-branch-from-commit, main) Updated project readme
* 2144430 (origin/main, ft/branch) Implemented test 5
* c7ba922 chore: Create initial file
* b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git branch -m ft/improved-branch-name

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git branch
  dev
  ft/branch
* ft/improved-branch-name
  main

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$   main
* ft/improved-branch-name
bash: main: command not found
bash: readme.txt: command not found

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git log --oneline
ad24764 (HEAD -> ft/improved-branch-name, main) Updated project readme
2144430 (origin/main, ft/branch) Implemented test 5
c7ba922 chore: Create initial file
b1f535b chore: Create third and fourth files

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git checkout <commit-hash>
bash: syntax error near unexpected token `newline'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git checkout dev
error: The following untracked working tree files would be overwritten by checkout:
        readme.md
Please move or remove them before you switch branches.
Aborting

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git switch dev
error: The following untracked working tree files would be overwritten by checkout:
        readme.md
Please move or remove them before you switch branches.
Aborting

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git checkout dev
error: The following untracked working tree files would be overwritten by checkout:
        readme.md
Please move or remove them before you switch branches.
Aborting

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git add .

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git commit readme.md
hint: Waiting for your editor to close the file... unix2dos: converting file C:/Users/user/Desktop/git/Git-exercise/.git/COMMIT_EDITMSG to DOS format...
dos2unix: converting file C:/Users/user/Desktop/git/Git-exercise/.git/COMMIT_EDITMSG to Unix format...
Aborting commit due to empty commit message.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git add .

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git commit readme.md
hint: Waiting for your editor to close the file... unix2dos: converting file C:/Users/user/Desktop/git/Git-exercise/.git/COMMIT_EDITMSG to DOS format...
dos2unix: converting file C:/Users/user/Desktop/git/Git-exercise/.git/COMMIT_EDITMSG to Unix format...
Aborting commit due to empty commit message.

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git checkout dev
error: Your local changes to the following files would be overwritten by checkout:
        readme.md
Please commit your changes or stash them before you switch branches.
Aborting

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git add .

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git commit -m"."
[ft/improved-branch-name 13601a0] .
 1 file changed, 322 insertions(+)
 create mode 100644 readme.md

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (ft/improved-branch-name)
$ git checkout dev
Switched to branch 'dev'

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git add .

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git commit -m"Branching Basics "
On branch dev
nothing to commit, working tree clean

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git push origin dev
Everything up-to-date

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (dev)
$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git add .

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git commit -m"Branching Basics "
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

user@LAPTOP-7PT2H9GQ MINGW64 ~/Desktop/git/Git-exercise (main)
$ git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 343 bytes | 343.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/samuel-ishimwe203/Git-exercise.git
   2144430..ad24764  main -> main
