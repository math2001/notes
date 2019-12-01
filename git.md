# Git

## Terminology

> Index (also known as the cache or staging area): the index is the place where
> you prepare your next commit

## Remove file from the git tree, but keep locally

    $ git rm --cached <filename>

Note that the file will still be kept in the previous commits

> TODO: how do you remove a file *completely* from git history

## Undo `git add <filename>`

    $ git reset <filename>

Removes the `<filename>` from the staging area, before the commit. It goes back
to being `not stagged`.

## Remove commit but keep changes

    git reset HEAD^


> git reset without a --hard or --soft moves your HEAD to point to the
> specified commit, without changing any files.
