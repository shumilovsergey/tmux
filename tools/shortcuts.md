# Shortcuts

Prefix is the backtick **`` ` ``**. "Press `` ` `` `x`" = tap backtick, release,
then tap `x`. Scrolling, searching, and copying live in their own page:
**[scroll-world.md](scroll-world.md)**.

## Splits (panes)
| Keys        | Does                                             |
|-------------|--------------------------------------------------|
| `` ` `` `\` | split **side-by-side** (you call it vertical)    |
| `` ` `` `-` | split **stacked** (horizontal)                   |
| `` ` `` `←` `↓` `↑` `→` | move to the split in that direction  |
| `` ` `` `z` | **zoom** a split to fullscreen; press again to undo |
| `` ` `` `x` | close the current split — **asks y/n first**     |

## Windows (you rarely touch these)
| Keys           | Does                                          |
|----------------|-----------------------------------------------|
| `` ` `` `n`    | **new** window                                |
| `` ` `` `o`    | close the active window — **asks y/n first**  |
| `` ` `` `1`…`9`| jump straight to window 1–9                   |

Windows auto-label themselves **1, 2, 3, …** — no naming to do, and closing one
renumbers the rest so there are never gaps. (Closing the *last* window quits tmux.)

## Scroll / search / copy  → enters the scroll world
| Keys        | Does                                             |
|-------------|--------------------------------------------------|
| `` ` `` `y` | scroll **up** a page (nano `Ctrl-Y`)             |
| `` ` `` `v` | scroll **down** a page (nano `Ctrl-V`)           |
| `` ` `` `w` | search the scrollback for a word (nano "Where is") |
| `` ` `` `^` | start a selection (nano mark)                    |
| `` ` `` `u` | paste into the terminal (nano `Ctrl-U`)          |

Full flow explained in **[scroll-world.md](scroll-world.md)**.

## Housekeeping
| Keys           | Does                                          |
|----------------|-----------------------------------------------|
| `` ` `` `=`    | reload the config — delivers your edits       |
| `` ` `` `` ` ``| type a real backtick                          |

## Nano ↔ nanomux
| Nano       | nanomux            | Action        |
|------------|--------------------|---------------|
| `Ctrl-Y`   | `` ` `` `y`        | page up       |
| `Ctrl-V`   | `` ` `` `v`        | page down     |
| `Ctrl-W`   | `` ` `` `w`        | search        |
| `Ctrl-^`   | `` ` `` `^` / `^`  | start select  |
| `Ctrl-K`   | `k` (in scroll)    | copy          |
| `Ctrl-U`   | `` ` `` `u`        | paste         |
