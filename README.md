# nanomux

A tiny, **nano-flavored tmux** config for one person, one session. It keeps only
the commands I actually use — splits, a bit of window-hopping, and comfortable
keyboard scrolling / searching / copying — with keys that feel like nano.

The prefix is the backtick **`` ` ``**: tap it, release, then press the next key.

## What's here

| Path | What it is |
|------|-----------|
| [`tmux.conf`](tmux.conf) | The config. Symlinked to `~/.tmux.conf`. |
| [`tools/install.md`](tools/install.md) | Install tmux (macOS/brew + Linux/apt) and link the config |
| [`tools/shortcuts.md`](tools/shortcuts.md) | Every key, grouped and compact |
| [`tools/scroll-world.md`](tools/scroll-world.md) | Scrolling, searching, select / copy / paste |
| [`tools/micro.md`](tools/micro.md) | The `micro` editor: install, file-tree sidebar, editing keys |
| [`backup/`](backup/) | The original full-featured config + docs, kept for when I want to learn more tmux |
| [`task.md`](task.md) | The original brief |

## Get going

1. **[Install & link](tools/install.md)** — brew/apt, then one symlink command.
2. **[Learn the keys](tools/shortcuts.md)** — there aren't many.
3. **[Scroll world](tools/scroll-world.md)** — the one concept worth reading twice.

## The idea

If I don't use a shortcut, it's not in the config. When I find I need one, I add
it by hand — so I end up with exactly my commands, nothing more.
