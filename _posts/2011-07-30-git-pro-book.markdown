---
layout: default
title: Pro Git Notes
categories: git
type: blog
---

git diff
--------
`git diff` - check what you've changed but not yet staged.

`git diff --cached` - compare your staged changes to your last commit.

git rm
------
`git rm test.c` - remove the the file.

`git rm --cached test.c` - remove the file from staging area but keep it file system.

git mv
------
`git mv file_from file_to` - move the file.

git log
-------

`git log` - view the commit history.

`git log -p 2` - shows the diff introduced in each commit limited the output to the only last two entries.

`git log --stat` - show some abbreviated stats for each commit.

`git log --pretty=oneline` - change the log output to show it in one line each.

`git log --pretty=format:"%h - %an, %ar : %s"` - format the output using options like:
- %H Commit hash
- %h Abbreviated commit hash
- %T Tree hash
- %t Abbreviated tree hash
- %P Parent hashes
- %p Abbreviated parent hashes
- %an Author name
- %ae Author e-mail
- %ad Author date (format respects the –date= option)
- %ar Author date, relative
- %cn Committer name
- %ce Committer email
- %cd Committer date
- %cr Committer date, relative
- %s Subject


