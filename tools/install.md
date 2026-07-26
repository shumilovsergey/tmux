# Install

Two parts: **install tmux**, then **link this repo's config** so editing the
repo edits your live config.

## 1. Install tmux

### macOS (Homebrew)
```sh
brew --version        # if "command not found", install Homebrew first (below)
brew install tmux
tmux -V               # expect: tmux 3.5a or newer
```

Don't have Homebrew?
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Then follow the PATH instructions it prints (Apple Silicon needs this).

### Linux (Debian / Ubuntu — apt)
```sh
sudo apt update
sudo apt install tmux
tmux -V
```

## 2. Link the config (repo → live)

This makes the repo file *become* your real config, so every edit here is live —
no copying, ever:

```sh
ln -sf ~/Developer/tmux/tmux.conf ~/.tmux.conf
```

Already have a `~/.tmux.conf`? Back it up first:
```sh
cp ~/.tmux.conf ~/.tmux.conf.backup
```

> `-s` = symlink, `-f` = replace whatever's there. After this, `~/.tmux.conf`
> is just a pointer to the repo file.

## 3. First run
```sh
tmux
```
You'll see a dark status bar with `nanomux` on the left and window `1`.
To leave everything running: press `` ` `` then `d` (detach). To quit: type `exit`.

## 4. After you edit tmux.conf — deliver the changes

Because it's symlinked, your edits are already saved to the live file. Just
reload from **inside** tmux:

```
`  =
```

(tap backtick, then `=`). You'll see "nanomux reloaded" at the bottom.

### Reload vs. restart
`` ` `` `=` **reloads** (re-reads the config) without closing your panes — that's
all you normally need. A true *restart* would close everything, so we don't bind
one. If you ever change something that a reload can't pick up, quit all tmux
(`exit` every window) and start `tmux` again.
