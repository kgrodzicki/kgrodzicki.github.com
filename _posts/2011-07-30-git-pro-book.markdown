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

`git log --pretty=format:"%h %s" --graph` - format the log and show the graph

### More options for `git log`:

- -p Show the patch introduced with each commit.
- --stat Show statistics for files modified in each commit.
- --shortstat Display only the changed/insertions/deletions line from the --stat command.
- --name-only Show the list of files modified after the commit information.
- --name-status Show only names and status of changed files. See the description of the `--diff-filter` option on what the status letters mean.
- --abbrev-commit Show only the first few characters of the SHA-1 checksum instead of all.
- --relative-date Shows dates relative to the current time, e.g. "2 hours ago".
- --graph Display an ASCII graph of the branch and merge history beside the log output.
- --pretty Show commits in an alternate format.

`git log --since=2.weeks` - limit the list of commits made int he last two weeks.

### Options for limitg the log aoutput:

- -(n) Show only the last n commits
- --since, --after Limit the commits to those made after the specified date.
- --until, --before Limit the commits to those made before the specified date.
- --author Only show commits in which the author entry matches the specified string.
- --committer Only show commits in which the committer entry matches the specified string.

`git log --pretty="%h - %s" --author=gitster --since="2008-10-01" --before="2008-11-01" --no-merges -- t` - more advanced example of limiting log output.

