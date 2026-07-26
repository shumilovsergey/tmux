# Scroll world — scrolling, searching, selecting, copying

tmux has two states. Knowing which one you're in explains every key.

1. **Normal** — your everyday shell. Every command starts with the backtick.
2. **Scroll world** — you enter it to look back at old output, search, or
   select + copy text. **Inside it you drop the backtick** — keys are bare.
   Press `q` or `Esc` to return to Normal.

You enter scroll world with `` ` `` `y` (or `v` / `w` / `^`), or just by
scrolling the mouse wheel up.

---

## 1. Scroll page by page
The live shell only shows the latest output. To look back:

- **`` ` `` `y`** → jump **up a page** into the history (this puts you in scroll world).
- Now, bare keys: **`y`** = another page up, **`v`** = a page down.
  `PageUp` / `PageDown` and the **mouse wheel** work too.
- **`q`** or **`Esc`** → back to normal.

## 2. Search for a line with a word
- **`` ` `` `w`** → a `search:` prompt appears at the bottom. Type the word, `Enter`.
- tmux jumps to the nearest match **above**. Search again for the next one.
- This is nano's `Ctrl-W` ("Where is").

## 3. Select / copy / paste

**Easy way — mouse:**
- **Drag** across text → selected *and* already copied to the macOS clipboard.
  Paste anywhere with the normal `Cmd-V`.

**Keyboard way — nano style:**
| Step | Key            | What happens                                  |
|------|----------------|-----------------------------------------------|
| 1    | `` ` `` `y`    | enter scroll world                            |
| 2    | arrows / `y` `v` | move the cursor to the **start** of the text |
| 3    | `^` (or `Space`) | drop a mark — selection starts here          |
| 4    | arrows         | stretch the selection to the **end**          |
| 5    | `k` (or `Enter`) | **copy** to the macOS clipboard, and leave   |
| 6    | `` ` `` `u`    | **paste** it back into the terminal           |

## Paste, the two clipboards
- **`` ` `` `u`** pastes into the *terminal*.
- To paste into another Mac app, use **`Cmd-V`** — the copy already went to the
  real macOS clipboard. `Cmd-V` also pastes *from* other apps into tmux.

---

### The 6-word version
Scroll: `` ` `` `y`. Search: `` ` `` `w`. Copy: mark `^`, grab `k`. Paste: `` ` `` `u`.

> **Non-macOS note:** copying uses `pbcopy`, which is macOS-only. On Linux,
> swap `pbcopy` for `xclip -selection clipboard` (X11) or `wl-copy` (Wayland)
> in `tmux.conf`.
