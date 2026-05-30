# rm-safely

> `rm` safely.

Let's `rm` safely with no anxiety.

Because the rm command does not come with any personal protective equipment.

This light shell function makes rm safer, especially the default MacOS `rm`.

By wraping you a safe rm from any accidental deletion of files or directories
e.g. accidental autocomplete, sub-shell or script bugs etc.

_Keys_,

- Zero dependencies — pure shell script
- Save files in `~/.local/share/Trash` and in `/.Trash-$(id-u)` for mounted volumes.
- Tested on:
  - Shell
    - zsh
    - bash
  - OS:
    - macOS 15.5+
    - Linux arch-linux 6.17.1-2-cachyos

# Demo

![demo.gif](./docs/demo.gif)

# Install

Via homebrew:

```bash
brew install zdk/tools/rm-safely
```

Or, via curl:

`curl -fsSL https://raw.githubusercontent.com/zdk/rm-safely/main/rm-safely | bash -s install`

# Usage

Use `rm` command to delete things as usual, but safer ＼(◎o◎)／

In other words when you run `rm -rf file directory/`

You will have the copied of files/dir in the trash first,
then you can decide to delete or clean them later on.

# Additional features

```
rm --rm                      Skip trash!, really execute 'rm'
rm --list-trash, -l          Show trash contents from all filesystems
rm --restore <hash>, -s      Restore a file from trash using its hash
rm --undo, -u                Restore the last deleted files
rm --empty-trash             Empty all trash directories
rm --show-trash-path, -p     Display all trash directory paths
rm --version                 Show version information
rm --help                    Show this help
```

# Really Remove

Well, if you don't really care to move it to Trash first.

You could just `/bin/rm` directly it's always there for you.

Or, you can also use `--rm` option of rm-safely to bypass rm-safely protection.

That means, use `rm --rm`

For examples:

- remove files and directy with OS rm.

`rm --rm file directory/`

- see the OS rm --help

```
rm --rm --help
/bin/rm: illegal option -- -
usage: rm [-f | -i] [-dIPRrvWx] file ...
       unlink [--] file
```

`--rm` is nothing special other than execute `/bin/rm` from current shell.

# Uninstall

`curl -fsSL https://raw.githubusercontent.com/zdk/rm-safely/main/rm-safely | bash -s uninstall`

# Notes

- Main goal of rm-safely is to write it in a pure shell script
  as a gateway and a suppliment to rm, not a replacement.

- Another goal is to help and ease your quick day-to-day work as a thin protective layer
  (So, don't forget that you will still need a proper backup strategy for your really important data)

- Alternative tools:

  - https://github.com/MilesCranmer/rip2 (rust)
  - https://github.com/Byron/trash-rs (rust)
  - https://github.com/andreafrancia/trash-cli (python)
  - https://github.com/kaelzhang/shell-safe-rm (bash)
  - https://github.com/hitzhangjie/rm (go)

[Important Reminder],

Regarding the normal bahaviour of unix alias,

- Please keep in mind, _the rm-safely alias is available in current user only_.

And, you have a few options to make the alias available in another user like so:

1. Make sure you install in each user you need to have alias available.
   (Either manually or dotfiles should work)

2. Always use `sudo -s` to switch to root or another,
   then run `rm` in the next step as a good habit anyway.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=zdk/rm-safely&type=date&legend=top-left)](https://www.star-history.com/#zdk/rm-safely&type=date&legend=top-left)
