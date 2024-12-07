# git-link

## What it does

`git-link` creates a link to a code hosting platform (Github, Ggitlab) for the
given file, at the current revision, possibly highlighting a line or a range of
lines, if 1 or 2 line numbers are provided too.  
It may be called from anywhere, and will automatically detect the root
of the repository.

## How to install it?

1. Clone this repository or just download the script.
2. Add the script to your `PATH`.

## How to use it?

Let's ask git-link:

```bash
> git-link --help

Creates a link to a code hosting platform (github|gitlab) for the
given file, at the current revision, possibly highlighting a line or 
a range of lines, if 1 or 2 line numbers are provided too.
It may be called from anywhere, and will automatically detect the root
of the repository.

Usage: git-link FILE [LINE_NUMBER [END_LINE_NUMBER]]
   or: git-link -r REMOTE_TO_USE FILE [LINE_NUMBER [END_LINE_NUMBER]]

Options:
   -r REMOTE_TO_USE   the remote to use to detect the platform for which
                      to create a link (github|gitlab)

Example:
    # Let's say I cloned git repositories under my "Workspaces" directory.

    # 1. It works from anywhere outside the repository:

    > git-link ~/Workspaces/some-repo/path/to/some-file.txt 18 25
    https://github.com/organization/some-repo/blob/1a037ecae82f1f6ef672e0cdc102467cdd583e97/path/to/some-file.txt#L18-L25

    # or, if using Gitlab:
    https://gitlab.com/organization/group/subgroup/some-repo/-/blob/1a037ecae82f1f6ef672e0cdc102467cdd583e97/path/to/some-file.txt#L18-25

    # 2. It works from anywhere inside the repository too:

    > cd ~/Workspaces/some-repo/path
    > git-link to/some-file.txt 18 25
    # -> same output
```

## Limitations

I haven't tested it on MacOS, and I suspect it won't work on it for people who
haven't installed [coreutils](https://formulae.brew.sh/formula/coreutils)  or a
similar package, since `git-link` uses the `realpath` command for now.

