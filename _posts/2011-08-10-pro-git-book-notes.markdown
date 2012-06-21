---
layout: default
title: Pro Git Notes
categories: git
type: blog
updated: 21 June 2012
---

Notes from ['Pro Git'](http://bit.ly/nXGq5j) book.

git commit
----------
`git commit -am "msg"` - automatically "add" changes from all known files (i.e. all files that are already listed in the index) and to automatically "rm" files in the index that have been removed from the working tree, and then perform the actual commit. `-m` Use the given `msg` as the commit message.

`git commit --amend` - change your last commit. Takes your staging area and uses it for the commit. Use it to change your last commit.

git reset
---------

`git reset HEAD^1` - unstage last commit.

`git reset --hard master` - reset your branch to where `master` is now.

git pull
--------
`git pull --rebase` - pull changes and rebase.

git push
--------
`git push <remote> <branch>` - push to `<remote> <branch>` repository.

`git push <remote> <branch> --tags` - push to `<remote> <branch>` including all tags.

`git push -u <remote> <branch>` - push to `<remote> <branch>` repository and set up tracking (for "git pull" etc.) automatically.

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
`git mv file_from file_to` - move/rename the file.

git log
-------

`git log` - view the commit history.

`git log -p 2` - shows the diff introduced in each commit limited the output to the only last two entries.

`git log --stat` - show some abbreviated stats for each commit.

`git log --pretty=oneline` - change the log output to show it in one line each.

`git log --pretty=format:"%h - %an, %ar : %s"` - format the output using options like:
- `%H` Commit hash
- `%h` Abbreviated commit hash
- `%T` Tree hash
- `%t` Abbreviated tree hash
- `%P` Parent hashes
- `%p` Abbreviated parent hashes
- `%an` Author name
- `%ae` Author e-mail
- `%ad` Author date (format respects the –date= option)
- `%ar` Author date, relative
- `%cn` Committer name
- `%ce` Committer email
- `%cd` Committer date
- `%cr` Committer date, relative
- `%s` Subject

`git log --pretty=format:"%h %s" --graph` - format the log and show the graph

`git log -p filename` - change history of a file. 

`git log --all --grep='ala ma kota'` - list commits that contain a given text.

`gitk filename` - as before.

### More options for `git log`:

- `-p` Show the patch introduced with each commit.
- `--stat` Show statistics for files modified in each commit.
- `--shortstat` Display only the changed/insertions/deletions line from the --stat command.
- `--name-only` Show the list of files modified after the commit information.
- `--name-status` Show only names and status of changed files. See the description of the `--diff-filter` option on what the status letters mean.
- `--abbrev-commit` Show only the first few characters of the SHA-1 checksum instead of all.
- `--relative-date` Shows dates relative to the current time, e.g. "2 hours ago".
- `--graph Display` an ASCII graph of the branch and merge history beside the log output.
- `--pretty` Show commits in an alternate format.

`git log --since=2.weeks` - limit the list of commits made int he last two weeks.

### Options for limitg the log aoutput:

- `-(n)` Show only the last n commits
- `--since`, `--after` Limit the commits to those made after the specified date.
- `--until`, `--before` Limit the commits to those made before the specified date.
- `--author` Only show commits in which the author entry matches the specified string.
- `--committer` Only show commits in which the committer entry matches the specified string.

`git log --pretty="%h - %s" --author=gitster --since="2008-10-01" --before="2008-11-01" --no-merges -- t` - more advanced example of limiting log output.

`gitk` - show the visual `git log`.

git checkout
------------
`git checkout -- test.c` - revert your changes to last commited version.

git remote
----------
`git remote -v` - List the remote repositores with URL and shortname. `-v` - e a little more verbose and show remote url after name. NOTE: This must be placed between `remote` and `subcommand`.

`git remote add test git://github.com/kgrodzicki/test.git` - add remote repository.

`git remote show origin` - inspecting `origin` repository.

`git remote rename test newName` - rename the remote repository.

`git remote rm test` - remove remote repository.

`git remote show origin` - inspect a remote branch.

git fetch
---------

`git fetch test` - fetch changes form `test` repository.

git tag
-------
`git tag` - list tags.

`git tag -l 'v1.4.2.*'` - show the tags started from `v1.4.2.`.

`git tag -a v1.4 -m 'my version 1.4'` - create annotated tag.

`git tag -s v1.5 -m 'my signed 1.5 tag'` - create signed tag.

`git tag v1.4-1w` - create lightweight tag.

`git tag -v v1.4.2.1` - verify the `v1.4.2.1` tag.

`git tag -a v1.2 checksum` - create the tag for specific commit.

`git tag -d v1` - delete tag v1 from local repository.

`git push origin :refs/tags/v1` - delete tag v1 from local remote repository.

git branch
----------
`git branch newTest` - create new `newTest` branch.

`git branch -d newTest` - delete branch `newTest`.

`git push origin :newTest` - delete remote branch.

`git branch --merged` - show all branches that are already merged into the current branch.

`git branch --no-merged` - show all branches that contains work you haven't yet merged.

`git branch -m oldName newName` - rename branch.

git checkout
------------
`git checkout newTest` - change the current branch to `newTest`.

`git checkout -b newTest` - create new branch `newTest` and set it as current working branch.

git merge
---------

`git merge test` - merge `test` branch into current branch. Do not generate a merge commit if the merge resolved as a fast-forward, only update the branch pointer. This is the default behavior of `git-merge`.

`git merge --no-off test` - almost the same as command above, but with `--no-ff` generate a merge commit even if the merge resolved as a `fast-forward`.

`git mergetool` - run merge conflict resolution tools to resolve merge conflicts.

git stash
---------
`git stash` - push a ner stash onto your stack.

`git stash list` - list stashes.

`git stash apply` - apply last stash.

`git stash apply <stash-name>` - apply stash with name `<stash-name>`

`git stash show -p stash@{0} | git apply -R` - unapply stashed changes.

`git stash branch testchanges` - create branch from stash.

git rebase
----------
`git rebase -i HEAD^5` - interactive rebase.

git blame
---------

`git blame filename` - discover why and when a certain line was added.

git reflog
----------

`git reflog` - list branch history.

`git checkout aaaaa` - switch to correct branch

`git reset --hard 33aa59` - hard reset.

git archive
-----------

`git archive master | bzip2 > archive.tar.bz2` - export master branch from git and remove git configuration from it.

git config
----------

`git config --get gc.auto` - check configuration for gc.auto.

`git config --global gc.auto 1` - run automatically git gc.

git clean
---------
`git clean -xdf` - removing files that are not under version control.

Aliases
-------
Pretty git branch graphs

lg1 = `log --graph --all --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%cr)%C(reset) %C(white)%s%C(reset) %C(bold white)— %cn%C(reset)%C(bold yellow)%d%C(reset)' --abbrev-commit --date=relative`

lg2 = `log --graph --all --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%cD%C(reset) %C(bold green)(%cr)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(bold white)— %cn%C(reset)' --abbrev-commit`

Undo last commit
----------------
- `git commit` ...
- `git reset --soft HEAD^`
- `edit`
- `git add ...`
- `git commit -c ORIG_HEAD`
